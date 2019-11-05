---
title: Common Data Service | Microsoft Docs
description: Créez un Flow pour importer des données, exporter des données ou créer des approbations avec le Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546964"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Créer un fluide qui utilise le Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Améliorez l’efficacité opérationnelle grâce à une vue unifiée des données d’entreprise en créant un fluide qui utilise les [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Déployez cette base de données d’entreprise sécurisée qui comprend des entités métier standard bien formées (telles que les ventes, les achats, le service clientèle et la productivité) de votre organisation. Stockez les données organisationnelles dans une ou plusieurs [entités personnalisées](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), qui offrent plusieurs avantages par rapport aux sources de données externes telles que Microsoft Excel et Salesforce.

Par exemple, tirez parti de la Common Data Service dans Microsoft Flow de la façon suivante :

* Créer un Flow pour importer des données, exporter des données ou agir sur des données (par exemple, envoyer une notification). Notez que cette approche n’est pas un service de synchronisation complet. elle vous permet simplement de déplacer des données en fonction de l’entité.
  
    Pour obtenir des instructions détaillées, consultez les procédures plus loin dans cette rubrique.
* Au lieu de créer une [boucle d’approbation par courrier électronique](wait-for-approvals.md), créez un workflow qui stocke l’état d’approbation dans une entité, puis créez une application personnalisée dans laquelle les utilisateurs peuvent approuver ou rejeter des éléments.
  
    Pour obtenir des instructions détaillées, consultez [créer une boucle d’approbation avec le Common Data Service](common-data-model-approve.md).

**Conditions préalables**

* Inscrivez-vous à [Microsoft Flow](https://flow.microsoft.com) et [powerapps](https://web.powerapps.com).
  
    Si vous rencontrez des problèmes, vérifiez si [Microsoft Flow](sign-up-sign-in.md) et [powerapps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) prend en charge le type de compte que vous possédez et si votre organisation n’a pas bloqué l’inscription.
* Si vous n’avez pas encore utilisé la Common Data Service, ouvrez l’onglet **entités** de [powerapps.com](https://web.powerapps.com/#/entities), puis cliquez ou appuyez sur **créer ma base de données**.

## <a name="sign-in-to-your-environment"></a>Connectez-vous à votre environnement
1. Ouvrez le [portail Microsoft Flow](https://flow.microsoft.com), puis cliquez ou appuyez sur **se connecter** dans le coin supérieur droit.
   
    **Remarque**: vous devrez peut-être ouvrir le menu en haut à gauche pour afficher le bouton **se connecter** .
   
    ![Connexion](./media/common-data-model-intro/signin-flow.png)
2. Dans le menu en haut à droite, sélectionnez l’environnement dans lequel vous avez créé la base de données dans powerapps.com.
   
    **Remarque**: Si vous ne sélectionnez pas le même environnement, vous ne verrez pas vos entités.
   
    ![Sélectionner l’environnement](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Ouvrir un modèle
1. Dans la zone Rechercher dans les **modèles** en haut de l’écran, tapez ou collez **Common**, puis appuyez sur entrée.
   
    ![Rechercher des modèles](./media/common-data-model-intro/template-search.png)
2. Dans la liste des modèles, cliquez ou appuyez sur le modèle qui importe les données de la source souhaitée dans l’entité (ou l' *objet*) de votre choix.
   
    Par exemple, cliquez ou appuyez sur le modèle qui copie les informations de contact à partir de Dynamics 365 dans le Common Data Service.
   
    ![Choisir un modèle](./media/common-data-model-intro/choose-template.png)
3. Cliquez ou appuyez sur **utiliser ce modèle**.
   
    ![Utiliser un modèle](./media/common-data-model-intro/use-template.png)
4. Si vous n’avez pas encore créé de connexion à partir de Microsoft Flow vers Dynamics 365, cliquez ou appuyez sur **se connecter**, puis fournissez vos informations d’identification si vous y êtes invité.
   
    ![Connectez-vous à Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Cliquez ou appuyez sur **Continuer**.
   
    ![Confirmer les comptes](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Créer votre Flow
1. Dans la première carte, spécifiez l’événement qui déclenchera le Flow.
   
    Par exemple, vous créez un fluide qui copiera les nouveaux contacts d’une instance de Dynamics 365 vers le Common Data Service. Sous **lors de la création d’un enregistrement**, spécifiez l’instance en cliquant ou en appuyant sur la flèche orientée vers le bas, puis en cliquant ou en appuyant sur une option dans la liste qui s’affiche.
   
    ![Spécifier l’instance de Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. facultatif Près du haut de l’écran, spécifiez un autre nom pour le Flow que vous créez.
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, l’interface utilisateur peut paraître légèrement différente.
   
    ![Nom du Workflow](./media/common-data-model-intro/name-flow.png)
3. Cliquez ou appuyez sur **créer un Flow**.
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, seule la coche peut apparaître.
   
    ![créer un Flow](./media/common-data-model-intro/create-flow.png)

Désormais, chaque fois que cet objet est créé dans le système source, il est importé dans le Common Data Service. Si vous ne trouvez pas un modèle qui fait ce dont vous avez besoin, vous pouvez [créer un flot](get-started-logic-flow.md) qui fonctionne en plus de la common data service.

Vous pouvez effectuer des actions sur les modifications apportées à la base de données. Par exemple, vous pouvez envoyer un courrier électronique de notification chaque fois que des données sont modifiées.

