---
title: Exécuter des flux selon une planification | Microsoft Docs
description: Automatisez les tâches récurrentes en exécutant des flux selon une planification, par exemple tous les jours ou toutes les heures.
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
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548843"
---
# <a name="run-flows-on-a-schedule"></a>Exécuter des flux selon une planification
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Créer un Flow qui effectue une ou plusieurs tâches (telles que l’envoi d’un rapport par courrier électronique) :

* une fois par jour, une heure ou une minute
* à une date que vous spécifiez
* après un nombre de jours, d’heures ou de minutes que vous spécifiez

## <a name="create-a-recurring-flow"></a>Créer un flot périodique
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **mes flux** dans la barre de navigation supérieure.
   
    ![Option mes flux](./media/run-scheduled-tasks/create-flow.png)
2. Sélectionnez **créer à partir d’un espace vide**.
   
    ![Créer un flot vide](./media/run-scheduled-tasks/create-from-blank.png)
3. Dans la zone **Rechercher tous les connecteurs et déclencheurs** , tapez **Recurrence**, puis sélectionnez **planification-récurrence**.
   
    ![Rechercher un déclencheur de périodicité](./media/run-scheduled-tasks/select-recurrence.png)
4. Dans la boîte de dialogue **périodicité** , spécifiez la fréquence à laquelle vous souhaitez que le flow s’exécute.
   
    Par exemple, spécifiez **2** sous **intervalle** et **semaine** sous **fréquence** si vous souhaitez que le workflow s’exécute toutes les deux semaines.
   
    ![Spécifier la périodicité](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Spécifier des options avancées
1. Suivez les étapes de la section précédente, puis sélectionnez **afficher les options avancées**.
   
    **Remarque**: ces options changent en fonction des valeurs auxquelles l' **intervalle** et la **fréquence** sont définis. Si votre écran ne correspond pas au graphique ci-dessous, assurez-vous que l' **intervalle** et la **fréquence** sont définis sur les mêmes valeurs que celles affichées dans le graphique.
2. Sélectionnez un **fuseau horaire** pour indiquer si l' **heure de début** reflète un fuseau horaire local, le temps universel coordonné (UTC, Universal Coordinated Time), etc.
3. Spécifiez une **heure de début** au format suivant :
   <br>YYYY-MM-DDTHH : MM : SSZ
4. Si vous avez spécifié **jour** sous **fréquence**, spécifiez l’heure de la journée à laquelle le Workflow doit s’exécuter.
5. Si vous avez spécifié **semaine** sous **fréquence**, spécifiez le ou les jours de la semaine auxquels le Flow doit s’exécuter, ainsi que l’heure ou les heures de la journée où le Workflow doit s’exécuter.
   
    Par exemple, configurez les options comme indiqué pour démarrer un Flow au plus tôt à midi (heure du Pacifique) le lundi 1er janvier 2018, puis exécutez-le toutes les deux semaines le mardi à 5:30p (heure du Pacifique).
   
    ![Spécifier des options avancées](./media/run-scheduled-tasks/advanced-options.png)
6. Ajoutez l’action ou les actions que vous souhaitez que le Flow prenne, comme décrit dans [créer un flot à partir de zéro](get-started-logic-flow.md) .

## <a name="delay-a-flow"></a>Retarder un Flow
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **mes flux** dans la barre de navigation supérieure.
   
    ![Créer un flot vide](./media/run-scheduled-tasks/create-flow.png)
2. Sélectionnez **créer à partir d’un espace vide**.
   
    ![Créer un flot vide](./media/run-scheduled-tasks/create-from-blank.png)
3. Spécifiez un événement comme décrit [à la rubrique créer un flot à partir de zéro](get-started-logic-flow.md) .
4. Sélectionnez **nouvelle étape**, puis **Ajouter une action**.
   
    ![Option permettant d’ajouter une action à un Flow](./media/run-scheduled-tasks/add-action.png)
5. Dans la liste des actions, effectuez l’une des opérations suivantes :
   
   * Sélectionnez **délai**, spécifiez un **nombre**et spécifiez une **unité** de temps telle que seconde, minute ou heure.
   * Sélectionnez **différer jusqu’à**, puis spécifiez une date dans ce format.<br>YYYY-MM-DDTHH : MM : SSZ
     
     ![ajouter un délai](./media/run-scheduled-tasks/add-delay.png)
     ![spécifier un délai en unités de temps](./media/run-scheduled-tasks/delay.png)
     ![spécifier le délai jusqu’à](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Pour en savoir plus

En savoir plus sur les [Options avancées](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) et sur la façon de les configurer.

