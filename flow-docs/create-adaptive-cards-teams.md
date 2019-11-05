---
title: Apprenez à créer des flux qui publient des cartes adaptatives dans Microsoft teams | Microsoft Docs
description: Apprenez à créer des flux qui publient du contenu richement mis en forme avec des cartes adaptatives vers Microsoft Teams.
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
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546499"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Utiliser des cartes adaptatives dans Microsoft teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Vous pouvez créer un Flow qui publie des [cartes adaptatives](https://adaptivecards.io) sur un canal Microsoft Teams. Avec les cartes adaptatives, vous pouvez utiliser une mise en forme enrichie pour rendre vos publications plus claires, interactives et attrayantes. Les cartes adaptatives peuvent contenir des composants tels que des images, des graphiques, du texte enrichi et bien plus encore.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Créer un Flow qui publie des cartes adaptatives dans une équipe

Procédez comme suit pour créer un Flow qui publie une carte adaptative sur le canal général de l’équipe stratégie et planification. Le Flow que nous créons utilise la **carte adaptative poster votre propre en tant que moteur de flow sur une action Channel (** préversion) pour envoyer le contenu de la carte adaptative au canal hebdomadaire de l’équipe.

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez l’icône **équipes** dans la barre de navigation sur la gauche, puis sélectionnez l’équipe **stratégie et planification** .

    ![Sélectionner des équipes](media/create-adaptive-cards-teams/select-teams-team.png)

1. Sélectionnez l’onglet **Flow** en haut de l’écran.
1. Sélectionnez l’icône **+** (créer à partir d’un espace vide).
1. Recherchez **récurrence**, puis sélectionnez le déclencheur de **périodicité** .

    ![Carte de récurrence](media/create-adaptive-cards-teams/select-recurrence.png)

1. Définissez la planification comme suit pour répéter chaque semaine, à un fuseau horaire de votre choix :
    
    ![Carte de récurrence](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Sélectionnez **nouvelle étape**.
1. Recherchez **Adaptive**, sélectionnez **Microsoft teams**, puis sélectionnez l’action **poster votre propre carte adaptative en tant que robot de canal (version préliminaire)** .

   ![Carte adaptative](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Fournissez une **équipe**, un **canal**et un **message** sur la carte d' **envoi de votre propre carte adaptative en tant que robot de canal (version préliminaire)** pour indiquer l’équipe et le canal sur lequel le **message** de carte adaptative sera publié.

   ![Carte adaptative](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Vous pouvez utiliser cet exemple de contenu JSON pour le **message**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Donnez un nom à votre Flow et enregistrez-le.


## <a name="run-the-flow"></a>Exécuter le Flow

Notez que, une fois l’heure de périodicité écoulée, le workflow publie le contenu de la carte adaptative sur le canal d’équipe que vous avez défini.

![Exécuter le Flow](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Pour en savoir plus

- Prise en main des [exemples de cartes adaptatives](https://adaptivecards.io/samples/).
- Créez un [contenu de carte adaptative](https://adaptivecards.io) de manière simple.



