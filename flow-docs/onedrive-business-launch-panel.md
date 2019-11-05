---
title: Créer des flux à partir du panneau de lancement de OneDrive entreprise | Microsoft Docs
description: Créez des flux à partir du panneau de lancement de OneDrive entreprise.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548595"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Créer des flux à partir du panneau de lancement de OneDrive entreprise
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

À l’instar du [panneau de lancement Microsoft Flow dans SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), vous pouvez exécuter des flux sur des fichiers spécifiques dans OneDrive entreprise. 

Cette fonctionnalité permet à la personne qui exécute le flux d’utiliser ses propres informations d’identification, ce qui est particulièrement applicable pour les flux qui ont été créés par un service informatique. 

Les utilisateurs peuvent également obtenir des invites pour les entrées d’exécution comme **approbateur** ou **message**, qui peuvent être de type texte, fichier, courrier électronique, valeur booléenne ou numérique.

Dans cette procédure pas à pas, nous allons créer un fluide simple qui utilise l’un des nombreux [modèles OneDrive entreprise](https://flow.microsoft.com/search/?q=OneDrive) pour demander l’approbation d’un fichier par le responsable du demandeur.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Créer un Flow qui demande l’approbation du gestionnaire pour un fichier dans OneDrive entreprise

1. Connectez-vous à OneDrive entreprise.
1. Recherchez, puis sélectionnez le fichier sur lequel vous souhaitez créer le Workflow.
1. Sélectionnez le lien **afficher les actions** (trois points).
1. Sélectionnez **flow** > **créer un Flow**.

     ![créer un Flow](./media/onedrive-launch-panel/create-flow.png) 

1. Sélectionnez l’un des modèles.

    Dans cet exemple, sélectionnez l' **approbation de l’animateur de la demande pour le modèle de fichier sélectionné** .

     >[!TIP]
     >Connectez-vous à tous les connecteurs qui demandent à vous connecter.

1. Sélectionnez **Continuer**.
1. Apportez les modifications souhaitées au modèle, puis enregistrez votre Flow avec un nom dont vous vous souviendrez facilement.

## <a name="run-the-flow"></a>Exécuter le Flow

1. Connectez-vous à OneDrive entreprise.
1. Recherchez, puis sélectionnez le fichier sur lequel l’approbation du gestionnaire de demandes est approuvée.
1. Sélectionnez le lien **afficher les actions** (trois points).
1. Sélectionnez **Flow**. Vous verrez le Flow que vous avez créé précédemment.
1. Sélectionnez le Flow que vous avez créé précédemment.

     ![Exécuter votre Flow](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Bien que cette procédure pas à pas montre comment créer un fluide à partir d’un modèle, vous pouvez également créer un flot vide pour utiliser l’un des centaines de connecteurs disponibles dans Microsoft Flow.

## <a name="learn-more"></a>Pour en savoir plus

- [Prise en main de Microsoft Flow](getting-started.md) 
- [Générer des flux à plusieurs étapes](multi-step-logic-flow.md)
