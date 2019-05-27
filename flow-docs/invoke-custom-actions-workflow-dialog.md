---
title: Appeler des actions personnalisées à partir d’un workflow | Microsoft Docs
description: Découvrez comment appeler une action personnalisée à partir d’un workflow
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 938410cf4484f8bed6509beee1d36c8cb3718e6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461398"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Appeler des actions personnalisées à partir d’un workflow

Les workflows ont de nombreuses fonctionnalités prenant en charge les scénarios métier. L’appel d’actions d’opération de base sur les données pour un enregistrement, telles que la création, la mise à jour et la suppression, à partir d’un workflow résout un certain nombre de scénarios métier. Toutefois, si vous combinez les fonctionnalités des workflows avec la puissance des actions personnalisées appelées directement à partir d’un workflow, vous ajoutez une toute nouvelle plage de scénarios métier à votre application sans avoir à écrire de code.  
  
 Examinons le scénario dans lequel une action personnalisée est appelée à partir d’un workflow. Nous allons appeler une action personnalisée pour demander l’approbation du responsable quand une remise sur une opportunité particulière dépasse 20 %.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Exemple Dynamics 365 Customer Engagement : Créer une action personnalisée à l’aide de l’entité Opportunité
  
1. Dans [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), sélectionnez **Processus**.  
  
2.  Dans la barre de navigation, choisissez **Nouveau**. Nommez le processus, puis choisissez le catégorie **Action**.  
  
 Pour demander une approbation de la remise, nous utilisons une action personnalisée appelée **Approval Process** (Processus d’approbation). Nous avons ajouté un paramètre d’entrée, **SpecialNotes** (Remarques particulières) et une étape **Send email** (Envoyer un e-mail) pour créer un message et envoyer une demande d’approbation du responsable, comme illustré ici.  
  
 ![Ajouter une étape &#45; Envoyer un e-mail](media/enable-custom-action-approval-proces-sadd-email.png "Ajouter une étape - Envoyer un e-mail")  
  
 Pour configurer le message d’e-mail, choisissez **Définir les propriétés**. Quand le formulaire s’ouvre, utilisez **l’Assistant Formulaire** pour ajouter des remarques particulières et d’autres informations à l’e-mail, comme celles mises en surbrillance dans la capture d’écran. Pour ajouter des remarques particulières, placez le curseur où vous souhaitez les faire apparaître dans le message, puis, dans **l’Assistant Formulaire**, sous **Rechercher**, choisissez **Arguments** dans la première liste déroulante et choisissez **SpecialNotes** (Remarques particulières) dans la deuxième liste déroulante, puis choisissez **OK**.  
  
 ![Configurer l’e-mail](media/enable-custom-action-approval-process-setup-email.png "Configurer l’e-mail")  
  
 Pour pouvoir appeler l’action à partir d’un workflow, vous devez l’activer. Une fois que vous avez activé l’action, vous pouvez afficher ses propriétés en choisissant **Afficher les propriétés**.  
  
 ![Activer l’action personnalisée : processus d’approbation](media/enable-custom-action-approval-process-activate-action.png "Activer l’action personnalisée : processus d’approbation")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Appeler une action personnalisée à partir d’un workflow  
  
1. Dans [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), sélectionnez **Processus**.   
  
2.  Dans la barre de navigation, choisissez **Nouveau**. Nommez le processus, puis choisissez le catégorie **Workflow**.  
  
 Nous avons créé un workflow qui appelle l’action personnalisée **Approval Process** (Processus d’approbation) chaque fois que l’approbation du responsable pour une remise de plus de 20 % sur une opportunité est requise.  
  
 ![Définir les propriétés de l’action à partir d’un workflow](media/enable-custom-action-from-workflow.png "Définir les propriétés de l’action à partir d’un workflow")  
  
 Vous pouvez définir les propriétés d’entrée de l’action en choisissant **Définir les propriétés**. Nous avons ajouté un nom du compte associé à l’opportunité dans les remarques particulières. Dans **l’Assistant Formulaire**, sous **Rechercher**, choisissez **Compte** dans la première liste déroulante, choisissez **Nom du compte** dans la seconde liste déroulante, puis choisissez **OK**. La propriété **Cible** est obligatoire et est remplie par le système. Dans la propriété **Cible**, **{Opportunity(Opportunity)}** ({Opportunité(Opportunité)}) est la même opportunité que celle sur laquelle le workflow appelant est en cours d’exécution. Vous pouvez également choisir une opportunité spécifique pour la propriété cible en effectuant une recherche.  
  
 ![Définir les paramètres d’entrée de l’action ApprovalProcess (Processus d’approbation)](media/enable-customaction-workflow-set-properties.png "Définir les paramètres d’entrée de l’action ApprovalProcess (Processus d’approbation)")  
  



