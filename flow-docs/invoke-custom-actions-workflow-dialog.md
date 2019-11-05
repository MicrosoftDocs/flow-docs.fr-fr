---
title: Appeler des actions personnalisées à partir d’un flux de travail | MicrosoftDocs
description: Découvrez comment appeler une action personnalisée à partir d’un flux de travail
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
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547408"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Appeler des actions personnalisées à partir d’un Workflow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les flux de travail offrent de nombreuses fonctionnalités qui prennent en charge les scénarios d’entreprise. L’appel d’actions de données de base pour un enregistrement, telles que la création, la mise à jour et la suppression, à partir d’un flux de travail résout un certain nombre de scénarios d’entreprise. Toutefois, si vous associez les fonctionnalités des workflows à la puissance des actions personnalisées appelées directement à partir d’un flux de travail, vous ajoutez une toute nouvelle plage de scénarios d’entreprise à votre application sans avoir à écrire du code.  
  
 Examinons le scénario dans lequel une action personnalisée est appelée à partir d’un Workflow. Nous allons invoquer une action personnalisée pour demander l’approbation du responsable lorsqu’une remise pour une opportunité particulière dépasse 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Exemple : créer une action personnalisée à l’aide de l’entité opportunité
  
1. Dans l' [Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , sélectionnez **processus**.  
  
2.  Dans la barre de navigation, choisissez **nouveau**. Donnez un nom au processus et choisissez la catégorie **action** .  
  
 Pour demander une approbation pour la remise, nous utilisons une action personnalisée appelée **processus d’approbation**. Nous avons ajouté un paramètre d’entrée, **SpecialNotes**, et une étape **Envoyer un e-mail** pour créer un message et envoyer une demande d’approbation du responsable, comme illustré ici.  
  
 ![Ajouter une étape &#45; envoyer un message électronique](media/enable-custom-action-approval-proces-sadd-email.png "Ajouter une étape-envoyer un message électronique")  
  
 Pour configurer le message électronique, choisissez **définir les propriétés**. Lorsque le formulaire s’ouvre, utilisez l' **Assistant formulaire** pour ajouter des notes spéciales et d’autres informations à l’e-mail, comme indiqué dans la capture d’écran. Pour ajouter les remarques spéciales, placez le curseur à l’endroit où vous souhaitez qu’elles apparaissent dans le message, puis, dans l' **Assistant formulaire**, sous **Rechercher**, choisissez **arguments** dans la première liste déroulante et choisissez **SpecialNotes** dans la seconde. dans la liste déroulante, puis choisissez **OK**.  
  
 ![Configurer la messagerie](media/enable-custom-action-approval-process-setup-email.png "Configurer la messagerie")  
  
 Avant de pouvoir appeler l’action à partir d’un flux de travail, vous devez l’activer. Une fois que vous avez activé l’action, vous pouvez afficher ses propriétés en choisissant **afficher les propriétés**.  
  
 ![Activer le processus &#45; d’approbation des actions personnalisées](media/enable-custom-action-approval-process-activate-action.png "Activer le processus d’approbation des actions personnalisées")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Appeler une action personnalisée à partir d’un Workflow  
  
1. Dans l' [Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , sélectionnez **processus**.   
  
2.  Dans la barre de navigation, choisissez **nouveau**. Donnez un nom au processus et choisissez la catégorie **Workflow** .  
  
 Nous avons créé un flux de travail qui appelle l’action personnalisée **processus d’approbation** chaque fois que l’approbation du responsable pour une remise supérieure à 20% pour une opportunité est requise.  
  
 ![Définir les propriétés des actions à partir du flux de travail](media/enable-custom-action-from-workflow.png "Définir les propriétés des actions à partir du flux de travail")  
  
 Vous pouvez définir les propriétés d’entrée de l’action en choisissant **définir les propriétés**. Nous avons ajouté un nom pour le compte associé à l’opportunité dans les notes spéciales. Dans l' **Assistant formulaire**, sous **Rechercher**, choisissez **compte** dans la première liste déroulante, choisissez **nom du compte** dans la deuxième liste déroulante, puis choisissez **OK**. La propriété **cible** est obligatoire et elle est remplie par le système. La **{opportunité (opportunité)}** dans la propriété **cible** est la même que celle sur laquelle le flux de travail appelant s’exécute. Vous pouvez également choisir une opportunité spécifique pour la propriété cible à l’aide de la recherche.  
  
 ![Définir les paramètres d’entrée pour l’action ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Définir les paramètres d’entrée pour l’action ApprovalProcess")  
  



