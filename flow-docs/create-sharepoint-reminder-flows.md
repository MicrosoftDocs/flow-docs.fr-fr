---
title: Créer un fluide de rappel pour les éléments SharePoint | Microsoft Docs
description: Créez des flux qui vous rappellent les dates d’échéance pour les éléments SharePoint.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547565"
---
# <a name="sharepoint-remind-me"></a>Me rappeler SharePoint
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les listes et les bibliothèques SharePoint vous permettaient de définir des colonnes de métadonnées personnalisées pour effectuer le suivi des dates. Avec l’intégration d’Microsoft Flow à SharePoint, vous pouvez facilement créer des flux de rappel, basés sur des colonnes DateTime dans SharePoint. Avec les flux de rappel, vous recevez une alerte par courrier électronique personnel un nombre prédéterminé de jours à l’avance d’une date sur un document ou un élément dans SharePoint.

## <a name="prerequisites"></a>Conditions préalables
- Accès à Microsoft SharePoint Online.
- Une liste SharePoint ou une bibliothèque avec une colonne DateTime.
- Accès aux Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Créer un workflow de rappel

 1. Créez une [liste SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) avec au moins une colonne DateTime dans l’affichage actuel. 
 1. Sélectionnez **Flow** > **définir un rappel** > **Date de désactivation** (il s’agit de la colonne avec la valeur DateTime pour le rappel).

     ![Sélectionner un flot de rappel](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Spécifiez un **nom de workflow** et le nombre de jours avant l’entrée de colonne DateTime lorsque vous souhaitez recevoir l’alerte de rappel sur la carte **définir un rappel** .

    ![Définir les détails du flot de rappel](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Sélectionnez **créer** sur la carte **définir un rappel** .

1. Vous recevrez le message suivant, indiquant que le Flow a été créé :

    ![Flow de rappel créé](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmer les rappels reçus

Vous recevrez un rappel par e-mail, en vous appuyant sur l’entrée « **me rappeler ce nombre de jours » à l’avance** que vous avez créée dans la rubrique **définir un** Flow de rappel que vous avez créé précédemment. 

## <a name="edit-your-flow"></a>Modifier votre Flow

Le workflow de rappel est comme n’importe quel autre Flow, afin que vous puissiez y accéder et le modifier via [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Pour en savoir plus

- Prise en main de [Microsoft Flow](https://flow.microsoft.com).
- Définissez un [Workflow de rappel](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) dans SharePoint.


