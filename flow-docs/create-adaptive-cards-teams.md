---
title: Apprenez à créer des flux qui publient des cartes adaptatives à Microsoft Teams | Microsoft Docs
description: Apprenez à créer des flux qui publier du contenu enrichi avec des cartes adaptatives sur Microsoft Teams.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061569"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Utiliser des cartes adaptatives dans Microsoft Teams

Vous pouvez créer un flux qui publie [des cartes adaptatives](https://adaptivecards.io) à un canal Microsoft Teams. Avec des cartes adaptatives, vous pouvez utiliser la mise en forme enrichie pour rendre vos publications plus claires, interactives et attrayantes. Des cartes adaptatives peuvent contenir des composants tels que des images, graphiques, texte enrichi et bien plus encore.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Créer un flux qui publie des cartes adaptatives à une équipe

Suivez ces étapes pour créer un flux qui publie une carte adaptative au canal général dans l’équipe de stratégie et de planification. Le flux que nous créons utilise le **publier votre propre carte adaptative en tant qu’au robot de flux d’un canal (version préliminaire)** action pour valider le contenu de la carte adaptative au canal de l’équipe chaque semaine.

1. Connectez-vous à Microsoft Teams.
1. Sélectionnez le **équipes** icône dans le volet de navigation de la barre de gauche, puis sélectionnez le **stratégie and Planning** équipe.

    ![Sélectionnez les équipes](media/create-adaptive-cards-teams/select-teams-team.png)

1. Sélectionnez le **flux** onglet en haut de l’écran.
1. Sélectionnez le **+** icône (créer entièrement).
1. Recherchez **périodicité**, puis sélectionnez le **périodicité** déclencheur.

    ![Carte de périodicité](media/create-adaptive-cards-teams/select-recurrence.png)

1. Définissez la planification comme suit pour répéter chaque semaine, à une heure et le fuseau horaire de votre choix :
    
    ![Carte de périodicité](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Sélectionnez **Nouvelle étape**.
1. Recherchez **adaptive**, sélectionnez **Microsoft Teams**, puis sélectionnez le **publier votre propre carte adaptative en tant qu’au robot de flux d’un canal (version préliminaire)** action.

   ![Carte adaptative](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Fournir un **équipe**, **canal**, et **Message** sur le **publier votre propre carte adaptative en tant qu’au robot de flux d’un canal (version préliminaire)** carte pour indiquer l’équipe et le canal auquel la carte adaptative **Message** sera publiée.

   ![Carte adaptative](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Vous pouvez utiliser cet exemple de contenu JSON pour le **Message**:

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


1. Donnez un nom à votre flux et enregistrez-le.


## <a name="run-the-flow"></a>Exécuter le flux

Notez que, une fois que la périodicité du temps écoulé, le flux de billets de contenu de la carte adaptative au canal d’équipe que vous avez défini.

![Exécuter le flux](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>En savoir plus

- Prise en main [exemples de carte adaptative](https://adaptivecards.io/samples/).
- Créer [contenu de la carte adaptative](https://adaptivecards.io) facilement.



