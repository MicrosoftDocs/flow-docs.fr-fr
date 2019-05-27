---
title: Découvrez comment créer et gérer les flux dans Microsoft Teams | Microsoft Docs
description: Créez et gérez des flux pour publier des messages à la demande, des utilisateurs et des canaux @mention, des cartes postales avec des options de réponse et bien plus encore.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061845"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow dans Teams

### <a name="prerequisites"></a>Prérequis

1. Accédez à Microsoft Teams.
1. Accédez à Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Installer l’application Microsoft Flow dans Teams

Suivez ces étapes pour installer l’application Microsoft Flow dans Microsoft Teams.

1. Connectez-vous à Microsoft Teams.

1. Touchez l’icône **Applications** dans le coin inférieur gauche de la barre de navigation Teams.

    ![Sélectionner les applications](media/flows-teams/apps.png)

1. Sélectionnez l’application **Flow**. Vous devrez peut-être rechercher **Flow** si vous ne la voyez.

    ![Sélectionner l’application Flow](media/flows-teams/select-flow-app.png)

1. Sélectionnez **Installer**.

    ![Bouton Installer](media/flows-teams/select-install.png)

1. Microsoft Flow est maintenant installé.

    ![Installation effectuée](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Créer un flux dans Teams

1. Connectez-vous à Microsoft Teams.

1. Sélectionnez le lient **Autres applications ajoutées** (...) dans la barre de navigation, puis sélectionnez l’application **Flow**.

    ![Icône d’applications ajoutées](media/flows-teams/added-apps-icon.png)

1. Si ce n’est déjà fait, vous devrez peut-être vous connecter et accorder des autorisations.

    ![Se connecter](media/flows-teams/grant-permissions-sign-in.png)


    Prenez en compte les onglets suivants :

    ![Page d’arrivée de Flow](media/flows-teams/flow-landing-page.png)

    Nom|Objectif
    ----|-----|
    Conversation|Interagissez avec le bot Flow.
    Flux|Créez et gérez des flux.
    Approbations|Répertorie les demandes d’approbations reçues et envoyées.
    À propos de|Affiche la version et d’autres informations concernant Microsoft Flow.


    Vous voyez maintenant tous les flux que vous avez créés à partir du concepteur Microsoft Flow (le cas échéant). 

    Vous pouvez également créer des flux à partir d’un modèle personnalisé ou d’un modèle vide, comme vous le feriez dans le concepteur Microsoft Flow. 

## <a name="manage-approvals"></a>Gérer les approbations

Vous pouvez gérer les [approbations](modern-approvals.md) dans Microsoft Teams, comme vous le feriez dans Microsoft Flow. Suivez ces étapes pour gérer vos approbations :

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez l’onglet **Approbations**.

    ![Onglet Approbations](media/flows-teams/approvals-tab.png)

    Vous remarquerez les sous-onglets suivants :

    Onglet|Objectif
    ----|-----|
    Reçu|Répertorie les demandes d’approbation vous avez reçues et qui sont en attente d’une action de votre part.
    Envoyé|Répertorie les demandes d’approbation vous avez envoyées et qui sont en attente d’une action d’autres personnes.
    Historique|Répertorie les demandes d’approbations reçues et envoyées.
    Créer un flux d’approbation|Créez des flux d’approbation.

1. Sélectionnez l’onglet **Reçu**, **Envoyé** ou **Historique** pour en savoir plus.

    ![Onglet Approbations](media/flows-teams/approvals-tab-2.png)

1. Sélectionnez **Créer un flux d’approbation** pour créer un flux d’approbation.

    ![Onglet Approbations](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Utiliser le bot avec des flux

### <a name="list-and-launch-flows-with-the-bot"></a>Répertorier et lancer des flux avec le bot

> [!TIP]
> Le bot répertorie et exécute les flux qui sont déclenchés par une planification ou déclenchés manuellement sans entrée utilisateur.

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez le lient **Autres applications ajoutées** (...) dans la barre de navigation, puis sélectionnez l’application **Flow**.

    ![Icône d’applications ajoutées](media/flows-teams/added-apps-icon.png)
    
1. Sélectionnez l’onglet **Conversation**.

    ![Onglet Conversation](media/flows-teams/conversations-tab.png)

Dans l’onglet **Conversation**, vous pouvez envoyer des commandes au bot, qui répond en effectuant les actions que vous lui demandez d’exécuter. Par exemple, pour répertorier vos flux et exécuter le flux avec l’index 1, exécutez les commandes suivantes :

- ```List flows``` - Le bot affiche la liste de vos flux, préfixée par un numéro d’index.
- ```Run flow 1``` - Exécute flux numéro 1. Ici, *1* est le numéro d’index du flux que vous souhaitez exécuter.

   ![Commandes du bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obtenir la description des flux

Pour obtenir la description du flux avec l’index 1 dans votre liste de flux, exécutez ```describe flow 1```. La réponse du bot sera semblable à cette image :

   ![Décrire les flux](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obtenir la liste des commandes pour le bot

Pour obtenir la liste des commandes gérées par le bot, demandez-la avec cette commande : ```learn more``` 

La réponse du bot sera semblable à cette image :

![Décrire les flux](media/flows-teams/bot-learn-more.png) 
