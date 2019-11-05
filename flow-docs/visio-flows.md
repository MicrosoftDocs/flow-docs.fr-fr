---
title: Concevoir des flux avec Microsoft Visio | Microsoft Docs
description: Tirez parti de l’expertise de Visio de votre organisation pour créer des modèles communs comme point de départ pour créer des flux.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0ffe9fbf8c29682bbcb941dbb48f9986f3c7144d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548778"
---
# <a name="design-flows-in-microsoft-visio"></a>Flux de conception dans Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le concepteur de Microsoft Flow est un outil riche dans lequel vous pouvez configurer chaque détail de votre logique. Toutefois, il peut arriver que vous souhaitiez simplement ébaucher votre logique de Flow avant de commencer à créer votre fluide. Pour ce faire, utilisez Microsoft Visio directement à partir de Microsoft Flow.

>[!TIP]
> De nombreux processus partagent un modèle commun mais ont des variations mineures au sein d’une organisation. Vous pouvez gagner du temps au sein de votre organisation à l’aide de Visio pour créer un modèle de flux de travail principal qui sera ensuite ajusté par d’autres avec des paramètres spécialisés.

## <a name="prerequisites"></a>Conditions préalables

- Un compte Microsoft Flow.
- Application de bureau Microsoft Visio (version anglaise).
- Expertise dans l’utilisation de Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Concevoir un flux de travail dans Visio

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com).
1. Dans le volet gauche, sélectionnez **modèles** .

     ![Sélectionner des modèles dans le volet gauche](./media/visio-flows/templates-from-left-panel.png)

1. Sélectionnez **Visio** dans la liste.

     ![Filtrer sur les modèles Visio](./media/visio-flows/select-visio.png) 

1. Sélectionnez le modèle **diagramme BPMN de base Flow** dans la liste des modèles **Visio** qui s’affiche.

     ![Sélectionner un modèle Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio vous avertit que les fichiers d’Internet peuvent endommager votre appareil. Si vous êtes à l’aise, sélectionnez **Oui** dans le message d’avertissement.

     ![Remarque Avertissement concernant les fichiers à partir d’Internet](./media/visio-flows/visio-warning.png)

1. Le concepteur Visio démarre.

     ![Vue du concepteur Visio](./media/visio-flows/visio-designer.png)


1. Utilisez les formes de base BPMN pour [concevoir votre flux de travail](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Formes de base BPMN](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-microsoft-flow"></a>Préparer l’exportation de votre flux de travail vers Microsoft Flow

Procédez comme suit pour préparer votre flux de travail afin de pouvoir l’exporter vers Microsoft Flow.

1. Sélectionnez l’onglet **processus** .
1. Sélectionnez **préparer l’exportation** à partir du groupe d' **Microsoft Flow** d’icônes.

   ![Sélectionner l’icône préparer l’exportation](./media/visio-flows/prepare-export-icon.png)
   
   Le groupe **préparer l’exportation** s’ouvre.

   ![Préparer le groupe d’exportation](./media/visio-flows/prepare-export-group.png)

1. Sous l’onglet **mappage de Flow** du groupe **préparer pour l’exportation** , mappez votre diagramme BPMN à des contrôles de Microsoft Flow. 

1. Sous l’onglet **déclencheurs et actions** du groupe **préparer l’exportation** , mappez votre diagramme BPMN à Microsoft Flow déclencheurs et actions en sélectionnant chaque forme, puis en sélectionnant un déclencheur ou une action pour représenter cette forme dans Microsoft Flow.

Votre flux de travail est prêt à être exporté lorsqu’il n’y a aucun problème restant sur le contrôle **préparer l’exportation** .

![Aucun problème](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Exporter votre flux de travail
1. Sélectionnez le bouton **Exporter vers le flux** pour exporter votre diagramme de flux de travail vers Microsoft Flow.
1. Nommez votre Flow, puis sélectionnez le bouton **créer un Flow** .
   
   ![Créer le Flow](./media/visio-flows/export-create-flow.png)

1. Vous devez voir un rapport de réussite semblable à celui-ci.

    ![Fructueux](./media/visio-flows/export-create-flow-success.png)

Vous pouvez maintenant exécuter ou apporter des modifications à votre Flow à partir du concepteur de Microsoft Flow, comme n’importe quel autre fluide.

>[!TIP]
> Utilisez les fonctionnalités de partage et de commentaire de Visio pour collaborer avec plusieurs parties prenantes et créer rapidement un flux de travail complet.

## <a name="learn-more"></a>Pour en savoir plus

- [Prise en main de Microsoft Flow](getting-started.md) 
- [Générer des flux à plusieurs étapes](multi-step-logic-flow.md)
- [Concevoir un fluide avec Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
