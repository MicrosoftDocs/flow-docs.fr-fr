---
title: Surveiller l’activité à partir de votre téléphone | Microsoft Docs
description: Afficher le nombre de réussites ou d’échecs de chaque workflow, le moment où chaque exécution s’est produite et le temps nécessaire
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
ms.openlocfilehash: 9696ff09f41822b9daeb84b748f32e1babaf5af1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549023"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Surveiller l’activité en Microsoft Flow à partir de votre téléphone
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Affichez un résumé du nombre de réussites ou d’échecs de chaque Flow, aujourd’hui, hier et des jours précédents. Explorez les détails de chaque exécution, par exemple lors de son exécution, la durée de chaque étape et, si elle a échoué, pourquoi.

**Conditions préalables**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows) sur un [appareil pris en charge](getting-started.md#use-the-mobile-app). Les graphiques de cette rubrique reflètent la version iPhone de l’application, mais les graphiques sur Android et les Windows Phone sont similaires.
* Si vous n’avez pas encore de fluide, créez-en un sur [le site Web pour Microsoft Flow](https://flow.microsoft.com/). Pour faciliter les tests, utilisez-en un que vous puissiez déclencher vous-même au lieu d’attendre un événement externe.

Le déroulement de ce didacticiel s’exécute lorsque vous recevez des messages d’une adresse spécifique :

![Déclencher le workflow lors de la réception d’un courrier électronique à partir d’une adresse spécifique](./media/mobile-monitor-activity/create-trigger.png)

Vous pouvez configurer un tel Flow avec votre adresse de messagerie personnelle à des fins de test et une autre adresse (par exemple, le de votre responsable) lorsque le workflow est prêt pour une utilisation réelle.

Lorsque le workflow s’exécute, il envoie une notification push personnalisée, avec cette syntaxe, à votre téléphone :

![Envoyer une notification push](./media/mobile-monitor-activity/create-event.png)

**Remarque :** Vous pouvez également [gérer vos flux](mobile-manage-flows.md) à partir de l’application mobile.

## <a name="display-a-summary-of-activity"></a>Afficher un résumé de l’activité
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Si votre Flow n’a pas encore été exécuté, déclenchez une exécution pour générer des données.
   
    L’affichage des données dans l’application peut prendre un certain temps.
2. Ouvrez l’application mobile, qui affiche l’onglet **activité** par défaut.
   
    Cet onglet organise les données par jour, avec les données actuelles en haut.
   
    ![Activité organisée par jour](./media/mobile-monitor-activity/activity-day2.png)
   
    Chaque entrée indique le nom d’un Flow avec des icônes qui correspondent à ses événements déclencheurs et à ses actions.
   
    ![Nom et icônes pour chaque Flow](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Si au moins une exécution d’un workflow a réussi dans une journée, une entrée indique le nombre de réussites et l’heure de la dernière réussite. Une autre entrée affiche des informations similaires en cas d’échec d’un Workflow.
   
    ![Résumé des réussites ou des échecs](./media/mobile-monitor-activity/activity-summary.png)
   
    Si un Flow envoie une notification push, le texte de la notification la plus récente s’affiche en bas de l’entrée pour les exécutions réussies.
   
    ![Exemple de notification push](./media/mobile-monitor-activity/activity-notification.png)
3. Si plusieurs notifications push ont été envoyées dans une journée, balayez vers la gauche sur la notification pour afficher les notifications des trois dernières exécutions. Si plus de quatre notifications ont été envoyées dans une journée, balayez vers la gauche jusqu’à ce que **afficher plus** , puis appuyez dessus pour afficher une liste de toutes les notifications.
   
    ![Exemple de notification push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Appuyez sur **précédent** pour revenir au Résumé de l’activité.
5. Pour filtrer le résumé de l’activité, appuyez sur l’icône dans le coin supérieur droit.
   
    Vous pouvez afficher toutes les entrées, uniquement les entrées d’échec ou uniquement les entrées qui incluent des notifications push.
   
    ![Afficher toutes les exécutions, uniquement les échecs ou uniquement les notifications](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Afficher les détails d’une exécution
1. Dans le résumé de l’activité, appuyez sur une entrée pour afficher les détails de la dernière exécution.
   
     Chaque événement et action apparaît avec une icône qui indique si l’événement ou l’action a réussi ou échoué. En cas de réussite, la durée (en secondes) s’affiche également.
   
    ![Détails d’une exécution](./media/mobile-monitor-activity/activity-icons.png)
2. En bas de l’écran, cliquez sur **afficher les exécutions précédentes** pour répertorier toutes les exécutions du workflow, puis appuyez sur une exécution pour afficher ses détails.
   
    ![Historique des réussites/échecs](./media/mobile-monitor-activity/history-mixed.png)

