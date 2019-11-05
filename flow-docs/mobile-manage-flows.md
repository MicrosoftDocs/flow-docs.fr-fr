---
title: Gérer les flux à partir de votre téléphone | Microsoft Docs
description: Afficher une liste de vos flux, les activer ou les désactiver, et afficher les événements, les actions et l’historique d’exécution de chaque flux
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
ms.openlocfilehash: 6f452f52d654d6f03a3262de8888c68cb2480704
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548637"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gérer les flux dans Microsoft Flow à partir de votre téléphone
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Affichez la liste de tous les flux que vous avez créés et, pour chaque flux, affichez ses événements et actions, activez-le ou désactivez-le, puis explorez son historique d’exécution.

**Conditions préalables**

* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows) sur un [appareil pris en charge](getting-started.md#use-the-mobile-app). Les graphiques de cette rubrique reflètent la version iPhone de l’application, mais les graphiques sur Android et les Windows Phone ressemblent à ce qui est similaire.
* Si vous n’avez pas encore de fluide, créez-en un sur [le site Web pour Microsoft Flow](https://flow.microsoft.com/). Pour faciliter les tests, utilisez-en un que vous puissiez déclencher vous-même au lieu d’attendre un événement externe.

Le déroulement de ce didacticiel s’exécute lorsque vous recevez des messages d’une adresse spécifique :

![Déclencher le workflow lors de la réception d’un courrier électronique à partir d’une adresse spécifique](./media/mobile-manage-flows/create-trigger.png)

Vous pouvez configurer un tel Flow avec votre adresse de messagerie personnelle à des fins de test et une autre adresse (par exemple, le de votre responsable) lorsque le workflow est prêt pour une utilisation réelle.

Lorsque le workflow s’exécute, il envoie une notification push personnalisée, avec cette syntaxe, à votre téléphone :

![Envoyer un message à la marge](./media/mobile-manage-flows/create-event.png)

**Remarque**: vous pouvez également [surveiller l’activité de Flow](mobile-monitor-activity.md) à partir de l’application mobile.

## <a name="manage-a-flow"></a>Gérer un Flow
1. Ouvrez l’application mobile, puis appuyez sur **mes flux** en bas de l’écran pour répertorier tous vos flux.
   
    Chaque entrée indique le nom du Flow, les icônes pour ses événements et actions, l’heure à laquelle il s’est exécuté le plus récemment et une icône qui indique si l’exécution la plus récente a réussi.
   
    ![Liste des flux](./media/mobile-manage-flows/flow-list.png)
2. Appuyez sur un Flow pour afficher les options de gestion de celui-ci.
   
    ![Options de gestion d’un Flow](./media/mobile-manage-flows/flow-details.png)
3. Appuyez sur **activer** /désactiver le déroulement pour activer ou désactiver le Flow.
4. Appuyez sur **afficher le Flow** pour afficher les événements et actions pour ce Flow, appuyez sur chaque événement ou sur une action pour le développer, puis sur **précédent**.
   
    ![Événements et actions pour un Workflow](./media/mobile-manage-flows/flow-event-action.png)
5. Appuyez sur **historique d’exécution** pour afficher les réussites, les échecs ou les deux.
   
    ![Liste des exécutions](./media/mobile-manage-flows/history-mixed.png)
6. Appuyez sur une exécution pour indiquer si chaque événement et action ont réussi et, le cas échéant, le temps écoulé (en secondes).
   
    ![Détails de l’exécution](./media/mobile-manage-flows/flow-run.png)

