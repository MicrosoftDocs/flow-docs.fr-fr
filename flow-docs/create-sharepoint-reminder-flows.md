---
title: Créer un flux de rappel pour les éléments SharePoint | Microsoft Docs
description: Créer des flux qui vous rappellent d’échéance dates pour les éléments SharePoint.
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
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061109"
---
# <a name="sharepoint-remind-me"></a>SharePoint me le rappeler

Listes et bibliothèques SharePoint autorisaient vous permettent de définir les colonnes de métadonnées personnalisées pour effectuer le suivi des dates. Avec l’intégration de Microsoft Flow avec SharePoint, vous pouvez facilement créer des flux de rappel, en fonction de colonnes DateTime dans SharePoint. Avec les flux de rappel, vous recevez une alerte de messagerie personnelle un nombre prédéterminé de jours à l’avance une date sur n’importe quel document ou un élément dans SharePoint.

## <a name="prerequisites"></a>Prérequis
- Accès à Microsoft SharePoint Online.
- Une liste SharePoint, ou une bibliothèque avec une colonne DateTime.
- Accédez à Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Créer un flux de rappel

 1. Créer un [liste SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) au moins une colonne de date/heure dans la vue actuelle. 
 1. Sélectionnez **flux** > **définir un rappel** > **Date désactivé** (il s’agit de la colonne avec la valeur DateTime pour le rappel).

     ![Sélectionnez le flux de rappel](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Fournir un **le nom du flux** et le nombre de jours avant l’entrée de colonne de date/heure lorsque vous souhaitez recevoir l’alerte de rappel sur le **définir un rappel** carte.

    ![Définir les détails de flux de rappel](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Sélectionnez **créer** sur le **définir un rappel** carte.

1. Vous recevrez le message suivant, indiquant que le flux a été créé :

    ![Flux de rappel créé](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmer les rappels reçus

Vous recevrez un rappel par courrier électronique, selon le **me le rappeler ce nombre jour (s) à l’avance** entrée effectuée sur le **définir un rappel** flux que vous avez créé précédemment. 

## <a name="edit-your-flow"></a>Modifier votre flux

Le flux de rappel ressemble à un autre flux, afin de pouvoir accéder et modifier par le biais de [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>En savoir plus

- Prise en main [Microsoft Flow](https://flow.microsoft.com).
- Définir un [flux de rappel](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) dans SharePoint.


