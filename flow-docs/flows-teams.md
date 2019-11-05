---
title: En savoir plus sur la création et la gestion de flux dans Microsoft teams | Microsoft Docs
description: Créez et gérez des flux pour envoyer des messages à la demande, @mention des utilisateurs et des canaux, publiez des cartes avec des options de réponse, et bien plus encore.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547993"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow dans teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Conditions préalables

1. Accès à Microsoft Teams.
1. Accès aux Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Installer l’application Microsoft Flow dans teams

Procédez comme suit pour installer l’application Microsoft Flow dans Microsoft Teams.

1. Connectez-vous à Microsoft Teams.

1. Appuyez sur l’icône **applications** en bas à gauche de la barre de navigation équipes.

    ![Sélectionner les applications](media/flows-teams/apps.png)

1. Sélectionnez l’application **Flow** . Vous devrez peut-être Rechercher **Flow** si vous ne le voyez pas.

    ![Sélectionner une application de Flow](media/flows-teams/select-flow-app.png)

1. Sélectionnez **installer**.

    ![Bouton installer](media/flows-teams/select-install.png)

1. Microsoft Flow est maintenant installé.

    ![Ordinateur](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Créer un fluide dans teams

1. Connectez-vous à Microsoft Teams.

1. Sélectionnez le lien **autres applications ajoutées** (...) dans la barre de navigation, puis sélectionnez l’application **Flow** .

    ![Icône applications ajoutées](media/flows-teams/added-apps-icon.png)

1. Si vous ne l’avez pas déjà fait, vous devrez peut-être vous connecter et accorder des autorisations.

    ![Connexion](media/flows-teams/grant-permissions-sign-in.png)


    Notez les onglets suivants :

    ![Page d’arrivée de Flow](media/flows-teams/flow-landing-page.png)

    Nomme|Objectif
    ----|-----|
    Dirigé|Interagissez avec le robot de Flow.
    Trouvent|Créer et gérer des flux.
    Approbations|Répertorie les demandes d’approbation reçues et envoyées.
    Obtenir|Affiche la version et d’autres informations sur Microsoft Flow.


    Vous voyez maintenant tous les flux que vous avez créés à partir du Microsoft Flow Designer (le cas échéant). 

    Vous pouvez également créer des flux à partir d’un modèle personnalisé ou à partir d’un modèle vide, comme vous le feriez à partir du concepteur de Microsoft Flow. 

## <a name="manage-approvals"></a>Gérer les approbations

Vous pouvez gérer les [approbations](modern-approvals.md) dans Microsoft Teams, comme vous le feriez dans Microsoft Flow. Pour gérer vos approbations, procédez comme suit :

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez l’onglet **approbations** .

    ![Onglet Approbations](media/flows-teams/approvals-tab.png)

    Vous remarquerez les sous-onglets suivants :

    /|Objectif
    ----|-----|
    Lettré|Répertorie les demandes d’approbation que vous avez reçues et qui sont en attente d’une action de votre part.
    Échangé|Répertorie les demandes d’approbation que vous avez envoyées et qui sont en attente d’une action d’un autre utilisateur.
    Historique|Répertorie les demandes d’approbation reçues et envoyées.
    Créer un workflow d’approbation|Créer des flux d’approbation.

1. Sélectionnez les onglets **reçu**, **envoyé**ou **historique** pour en savoir plus.

    ![Onglet Approbations](media/flows-teams/approvals-tab-2.png)

1. Sélectionnez **créer un workflow d’approbation** pour créer un workflow d’approbation.

    ![Onglet Approbations](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Utiliser le robot avec des flux

### <a name="list-and-launch-flows-with-the-bot"></a>Liste et lancement de flux avec le bot

> [!TIP]
> Le robot répertorie et exécute les flux déclenchés par une planification, ou déclenché manuellement sans entrée d’utilisateur.

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez le lien **autres applications ajoutées** (...) dans la barre de navigation, puis sélectionnez l’application **Flow** .

    ![Icône applications ajoutées](media/flows-teams/added-apps-icon.png)
    
1. Sélectionnez l’onglet **conversation** .

    ![Onglet conversation](media/flows-teams/conversations-tab.png)

Dans l’onglet **conversation** , vous pouvez envoyer des commandes au bot, qui répond en effectuant les actions que vous exécutez. Par exemple, pour répertorier vos flux et exécuter le flux avec l’index 1, exécutez les commandes suivantes :

- ```List flows```-le bot affiche une liste de vos flux, précédée d’un numéro d’index.
- ```Run flow 1```-exécute le Flow numéro 1. Ici, *1* est le numéro d’index du Flow que vous souhaitez exécuter.

   ![Commandes bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obtenir la description des flux

Pour obtenir la description du flux avec l’index 1 de votre liste de flux, exécutez ```describe flow 1```. La réponse du bot sera similaire à celle-ci :

   ![Décrire les flux](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obtenir la liste des commandes du robot

Pour obtenir la liste des commandes gérées par le bot, demandez-le à l’aide de cette commande : ```learn more``` 

La réponse du bot sera similaire à celle-ci :

![Décrire les flux](media/flows-teams/bot-learn-more.png) 
