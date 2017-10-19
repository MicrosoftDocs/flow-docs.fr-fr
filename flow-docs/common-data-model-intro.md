---
title: Common Data Service | Microsoft Docs
description: "Créez un flux qui permet d’importer des données, d’en exporter ou de créer des approbations avec le service Common Data Service."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: a63ccacb1e6d9bd63d5a11a8db6ea01a9fc37333
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Créer un flux qui utilise le service Common Data Service
Améliorez l’efficacité opérationnelle avec une vue unifiée des données métier en créant un flux qui utilise le service [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Déployez cette base de données d’entreprise sécurisée qui comprend des entités métier standard bien formées (par exemple, Ventes, Achat, Service clientèle et Productivité) dans votre organisation. Stockez les données de l’organisation dans une ou plusieurs [entités personnalisées](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), qui offrent plusieurs avantages par rapport aux sources de données externes telles que Microsoft Excel et Salesforce.

Par exemple, utilisez le service Common Data Service au sein de Microsoft Flow des manières suivantes :

* Créez un flux qui permet d’importer des données, d’en exporter ou d’agir sur les données (comme l’envoi d’une notification). Notez que cette approche n’est pas un service de synchronisation complet. Elle permet simplement de déplacer les données par entité.
  
    Pour des instructions détaillées, consultez les procédures plus loin dans cette rubrique.
* Au lieu de [créer une chaîne d’approbation par courrier électronique](wait-for-approvals.md), créez un flux qui stocke l’état d’approbation dans une entité, puis générez une application personnalisée dans laquelle les utilisateurs peuvent approuver ou rejeter des éléments.
  
    Pour des instructions détaillées, consultez [Créer une chaîne d’approbation avec le service Common Data Service](common-data-model-approve.md).

**Conditions préalables**

* Inscrivez-vous à [Microsoft Flow](https://flow.microsoft.com) et [PowerApps](https://web.powerapps.com).
  
    Si vous rencontrez des problèmes, vérifiez si [Microsoft Flow](sign-up-sign-in.md) et [PowerApps](https://powerapps.microsoft.com/en-us/tutorials/signup-for-powerapps/) prennent en charge le type de compte que vous utilisez et si votre organisation n’a pas bloqué l’inscription.
* Si vous n’avez pas utilisé le service Common Data Service avant, ouvrez l’onglet **Entités** de [powerapps.com](https://web.powerapps.com/#/entities), puis cliquez ou appuyez sur **Créer ma base de données**.

## <a name="sign-in-to-your-environment"></a>Se connecter à l’environnement
1. Dans le [portail Microsoft Flow](https://flow.microsoft.com), cliquez ou appuyez sur **Se connecter** dans le coin supérieur droit.
   
    **Remarque** : vous devrez peut-être ouvrir le menu en haut à gauche pour afficher le bouton **Se connecter**.
   
    ![Se connecter](./media/common-data-model-intro/signin-flow.png)
2. Dans le menu en haut à droite, vous sélectionnez l’environnement dans lequel vous avez créé la base de données dans powerapps.com.
   
    **Remarque** : si vous ne sélectionnez pas le même environnement, vous ne verrez pas vos entités.
   
    ![Sélectionner l’environnement](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Ouvrir un modèle
1. Dans la zone **Rechercher des modèles** située en haut de l’écran, tapez ou collez **common**, puis appuyez sur Entrée.
   
    ![Rechercher des modèles](./media/common-data-model-intro/template-search.png)
2. Dans la liste des modèles, cliquez ou appuyez sur le modèle qui permet d’importer des données de la source souhaitée dans l’entité (ou l’*objet*) de votre choix.
   
    Par exemple, cliquez ou appuyez sur le modèle qui copie des coordonnées de Dynamics 365 dans le service Common Data Service.
   
    ![Choisir un modèle](./media/common-data-model-intro/choose-template.png)
3. Cliquez ou appuyez sur **Utiliser ce modèle**.
   
    ![Utiliser un modèle](./media/common-data-model-intro/use-template.png)
4. Si vous n’avez pas déjà créé de connexion de Microsoft Flow vers Dynamics 365, cliquez ou appuyez sur **Se connecter**, puis fournissez vos informations d’identification si vous y êtes invité.
   
    ![Se connecter à Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Cliquez ou appuyez sur **Continuer**.
   
    ![Confirmer les comptes](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Créer votre flux
1. Dans la première carte, spécifiez l’événement qui déclenchera le flux.
   
    Par exemple, vous créez un flux qui copie de nouveaux contacts d’une instance Dynamics 365 dans le service Common Data Service. Sous **Lorsqu’un enregistrement est créé**, spécifiez l’instance en cliquant ou en appuyant sur la flèche vers le bas, puis sur une option dans la liste qui s’affiche.
   
    ![Spécifier l’instance de Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (facultatif) Près du haut de l’écran, spécifiez un nom différent pour le flux que vous créez.
   
    **Remarque** : si votre fenêtre de navigateur est réduite, l’apparence de interface peut différer légèrement.
   
    ![Nommer le flux](./media/common-data-model-intro/name-flow.png)
3. Cliquez ou appuyez sur **Créer un flux**.
   
    **Remarque** : si votre fenêtre de navigateur est réduite, il se peut que seule la coche apparaisse.
   
    ![Créer un flux](./media/common-data-model-intro/create-flow.png)

Maintenant, chaque fois que cet objet est créé dans le système source, il est importé dans le service Common Data Service. Si vous ne trouvez pas de modèle qui effectue les tâches que vous souhaitez, vous pouvez [créer un flux à partir de zéro](get-started-logic-flow.md) qui fonctionne sur le service Common Data Service.

Vous pouvez effectuer des actions sur les modifications apportées dans la base de données. Par exemple, vous pouvez envoyer un message de notification chaque fois que des données sont modifiées.

