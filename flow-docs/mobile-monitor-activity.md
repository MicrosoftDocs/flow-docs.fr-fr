---
title: Surveiller l’activité à partir de votre téléphone | Microsoft Docs
description: Affichez le nombre de fois où chaque flux a réussi ou échoué, le moment où chaque exécution s’est produite et la durée de celle-ci
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3ba49aff12118d79d41a7b76f7c8a0f7e3f1d01b
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689683"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Surveiller l’activité à partir de votre téléphone dans Microsoft Flow
Affichez un résumé du nombre de fois où chaque flux a réussi ou échoué aujourd’hui, hier et les jours précédents. Découvrez plus d’informations sur chaque exécution, comme le moment de l’exécution, la durée de chaque étape et la raison éventuelle de l’échec.

**Conditions préalables**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows) sur un [appareil pris en charge](getting-started.md#use-the-mobile-app). Les illustrations de cette rubrique reflètent la version iPhone de l’application, mais les graphiques sur l’interface Android et Windows Phone lui ressemblent.
* Si vous ne disposez pas d’un flux, créez-en un sur [le site web de Microsoft Flow](https://flow.microsoft.com/). Pour faciliter les tests, utilisez-en un que vous pouvez déclencher vous-même au lieu d’attendre un événement externe.

Le flux présenté dans ce didacticiel s’exécute lorsque vous recevez des messages provenant d’une adresse spécifique :

![Déclencher un flux à la réception d’un message électronique provenant d’une adresse spécifique](./media/mobile-monitor-activity/create-trigger.png)

Vous pouvez configurer un tel flux avec votre adresse de messagerie personnelle pour les tests et une adresse différente (par exemple, celle de votre responsable) lorsque le flux est prêt pour une utilisation réelle.

Lorsque le flux est exécuté, il envoie une notification Push personnalisée à votre téléphone avec la syntaxe suivante :

![Envoyer une notification Push](./media/mobile-monitor-activity/create-event.png)

**Remarque :** vous pouvez également [gérer votre flux](mobile-manage-flows.md) à partir de l’application mobile.

## <a name="display-a-summary-of-activity"></a>Afficher un résumé de l’activité
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Si votre flux n’a pas encore été exécuté, déclenchez une exécution pour générer des données.
   
    L’affichage des données dans l’application peut prendre un certain temps.
2. Ouvrez l’application mobile, qui affiche l’onglet **Activité**.
   
    Cet onglet organise les données par jour, le jour en cours étant présenté en haut.
   
    ![Activité organisée par jour](./media/mobile-monitor-activity/activity-day2.png)
   
    Chaque entrée indique le nom d’un flux avec des icônes qui correspondent aux événements et actions de déclencheur associés.
   
    ![Nom et icônes pour chaque flux](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Si au moins une exécution de flux a réussi au cours d’une journée, une entrée indique le nombre de réussites et l’heure de la réussite la plus récente. Une autre entrée affiche des informations similaires si un flux a échoué.
   
    ![Résumé des réussites ou échecs](./media/mobile-monitor-activity/activity-summary.png)
   
    Si un flux envoie une notification Push, le texte de la dernière notification s’affiche en bas de l’entrée pour les exécutions réussies.
   
    ![Exemple de notification Push](./media/mobile-monitor-activity/activity-notification.png)
3. Si plusieurs notifications Push ont été envoyées au cours d’une journée, balayez vers la gauche sur la notification pour afficher des notifications correspondant au maximum à trois exécutions précédentes. Si plus de quatre notifications ont été envoyées dans une journée, balayez vers la gauche jusqu’à ce que **Voir plus** s’affiche, puis appuyez dessus pour afficher une liste de toutes les notifications.
   
    ![Exemple de notification Push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Cliquez sur **Précédent** pour revenir au résumé de l’activité.
5. Pour filtrer le résumé de l’activité, appuyez sur l’icône dans le coin supérieur droit.
   
    Vous pouvez afficher toutes les entrées, uniquement celles relatives aux échecs ou uniquement celles contenant des notifications Push.
   
    ![Afficher toutes les exécutions, uniquement les échecs ou seulement les notifications](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Afficher les détails d’une exécution
1. Dans le résumé de l’activité, appuyez sur une entrée pour afficher les détails de l’exécution la plus récente.
   
     Chaque événement et action s’affichent avec une icône qui indique sa réussite ou son échec. En cas de réussite, la durée qui a été nécessaire (en secondes) s’affiche également.
   
    ![Détails d’une exécution](./media/mobile-monitor-activity/activity-icons.png)
2. En bas de l’écran, appuyez sur **Voir les précédentes exécutions** pour répertorier toutes les exécutions du flux, puis appuyez sur une exécution pour afficher les détails associés.
   
    ![Historique des réussites/échecs](./media/mobile-monitor-activity/history-mixed.png)

