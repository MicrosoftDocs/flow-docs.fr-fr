---
title: "Exécuter un flux selon une planification | Microsoft Docs"
description: "Automatisez les tâches récurrentes en exécutant des flux selon une planification, par exemple tous les jours ou toutes les heures."
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
ms.date: 09/14/2017
ms.author: stepsic
ms.openlocfilehash: 1c36abb44be31795e7d458628cc7ec7483187f49
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="run-flows-on-a-schedule"></a>Exécuter des flux selon une planification
Créez un flux qui effectue une ou plusieurs tâches, telles que l’envoi d’un rapport par e-mail :

* une fois par jour, heure ou minute
* à une date que vous spécifiez
* après un certain nombre de jours, d’heures ou de minutes que vous spécifiez.

## <a name="create-a-recurring-flow"></a>Créer un flux périodique
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **Mes flux** dans la barre de navigation supérieure.
   
    ![Option Mes flux](./media/run-tasks-on-a-schedule/create-flow.png)
2. Sélectionnez **Créer entièrement**.
   
    ![Créer entièrement un flux](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. Dans la zone **Rechercher dans l’ensemble des connecteurs et des déclencheurs**, tapez **Récurrence**, puis sélectionnez **Planification - Récurrence**.
   
    ![Trouver le déclencheur de récurrence](./media/run-tasks-on-a-schedule/select-recurrence.png)
4. Dans la boîte de dialogue **Récurrence**, spécifiez la fréquence à laquelle vous souhaitez que le flux s’exécute.
   
    Par exemple, spécifiez **2** sous **Intervalle** et **Semaine** sous **Fréquence** si vous souhaitez que le flux s’exécute toutes les deux semaines.
   
    ![Spécifier la récurrence](./media/run-tasks-on-a-schedule/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Spécifier des options avancées
1. Suivez les étapes décrites dans la section précédente, puis sélectionnez **Afficher les options avancées**.
   
    **Remarque** : ces options varient selon les valeurs sur lesquelles **Intervalle** et **Fréquence** sont définis. Si votre écran ne correspond pas à l’illustration ci-dessous, vérifiez que **Intervalle** et **Fréquence** ont les mêmes valeurs que le graphique.
2. Sélectionnez un **fuseau horaire** pour spécifier si l’**heure de début** reflète un fuseau horaire local, l’heure UTC, etc.
3. Spécifiez l’**heure de début** au format suivant :
   <br>YYYY-MM-DDTHH:MM:SSZ
4. Si vous avez spécifié **Jour** sous **Fréquence**, spécifiez l’heure où le flux doit s’exécuter.
5. Si vous avez spécifié **Semaine** sous **Fréquence**, spécifiez le ou les jours où le flux doit s’exécuter, ainsi que l’heure ou les heures de la journée où le flux doit s’exécuter.
   
    Par exemple, configurez les options comme indiqué pour démarrer un flux au plus tôt à midi (heure du Pacifique) le lundi 1er janvier 2018 et l’exécuter toutes les deux semaines le mardi à 17 h 30 (heure du Pacifique).
   
    ![Spécifier des options avancées](./media/run-tasks-on-a-schedule/advanced-options.png)
6. Ajoutez la ou les actions que vous souhaitez que le flux effectue (voir [Créer un flux à partir de zéro](get-started-logic-flow.md)).

## <a name="delay-a-flow"></a>Différer un flux
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **Mes flux** dans la barre de navigation supérieure.
   
    ![Créer entièrement un flux](./media/run-tasks-on-a-schedule/create-flow.png)
2. Sélectionnez **Créer entièrement**.
   
    ![Créer entièrement un flux](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. Spécifiez un événement (voir [Créer un flux à partir de zéro](get-started-logic-flow.md)).
4. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.
   
    ![Possibilité d’ajouter une action à un flux](./media/run-tasks-on-a-schedule/add-action.png)
5. Dans la liste des actions, effectuez l’une des opérations suivantes :
   
   * Sélectionnez **Délai**, spécifiez un **nombre** et une **unité** de temps, telle que heure, minute ou seconde.
   * Sélectionnez **Différer jusqu’à**, puis spécifiez une date au format suivant.<br>YYYY-MM-DDTHH:MM:SSZ
     
     ![Ajouter un délai](./media/run-tasks-on-a-schedule/add-delay.png)
     ![Spécifier un délai en unités de temps](./media/run-tasks-on-a-schedule/delay.png)
     ![Spécifier le report jusqu’au](./media/run-tasks-on-a-schedule/delay-until.png)

