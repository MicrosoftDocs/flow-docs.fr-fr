---
title: "Gérer des flux à partir de votre téléphone | Microsoft Docs"
description: "Affichez la liste de vos flux, activez ou désactivez des flux et affichez les événements, actions et historiques d’exécution de chaque flux"
services: 
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
ms.openlocfilehash: 4a04fec70ae70ff17ddf6e1f93e6461ec432e8d2
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gérer des flux à partir de votre téléphone dans Microsoft Flow
Affichez la liste de tous les flux que vous avez créés. En outre, affichez les événements et actions de chaque flux, activez ou désactivez un flux ou explorez un historique d’exécution.

**Conditions préalables**

* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows) sur un [appareil pris en charge](getting-started.md#use-the-mobile-app). Les illustrations de cette rubrique reflètent la version iPhone de l’application, mais les graphiques sur l’interface Android et Windows Phone lui ressemblent.
* Si vous ne disposez pas d’un flux, créez-en un sur [le site web de Microsoft Flow](https://flow.microsoft.com/). Pour faciliter les tests, utilisez-en un que vous pouvez déclencher vous-même au lieu d’attendre un événement externe.

Le flux présenté dans ce didacticiel s’exécute lorsque vous recevez des messages provenant d’une adresse spécifique :

![Déclencher un flux à la réception d’un message électronique provenant d’une adresse spécifique](./media/mobile-manage-flows/create-trigger.png)

Vous pouvez configurer un tel flux avec votre adresse de messagerie personnelle pour les tests et une adresse différente (par exemple, celle de votre responsable) lorsque le flux est prêt pour une utilisation réelle.

Lorsque le flux est exécuté, il envoie une notification Push personnalisée à votre téléphone avec la syntaxe suivante :

![Envoyer un message à Slack](./media/mobile-manage-flows/create-event.png)

**Remarque :** vous pouvez également [surveiller l’activité du flux](mobile-monitor-activity.md) à partir de l’application mobile.

## <a name="manage-a-flow"></a>Gérer un flux
1. Ouvrez l’application mobile, puis appuyez sur **Mes flux** en bas de l’écran pour afficher tous vos flux.
   
    Chaque entrée indique le nom du flux, des icônes pour les événements et actions associés, l’heure de la dernière exécution et une icône qui indique si la dernière exécution a réussi.
   
    ![Liste de flux](./media/mobile-manage-flows/flow-list.png)
2. Appuyez sur un flux pour afficher ses options de gestion.
   
    ![Options de gestion de flux](./media/mobile-manage-flows/flow-details.png)
3. Appuyez sur le bouton bascule **Activer le flux** pour activer ou désactiver le flux.
4. Appuyez sur **Voir le flux** pour afficher les événements et actions associés, appuyez sur chaque événement ou action que vous voulez développer et appuyez sur **Précédent**.
   
    ![Événements et actions d’un flux](./media/mobile-manage-flows/flow-event-action.png)
5. Appuyez sur **Historique d’exécution** pour afficher les réussites et/ou échecs du flux.
   
    ![Liste d’exécutions](./media/mobile-manage-flows/history-mixed.png)
6. Appuyez sur une exécution pour indiquer si chaque événement et action a réussi et, dans ce cas, la durée (en secondes) nécessaire pour la réussite du flux.
   
    ![Détails de l’exécution](./media/mobile-manage-flows/flow-run.png)

