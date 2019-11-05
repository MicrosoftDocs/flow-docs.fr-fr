---
title: Créer un Flow à partir de votre téléphone | Microsoft Docs
description: Créez un workflow à partir d’un modèle qui, par exemple, envoie une notification push lorsque vous recevez des messages à partir d’une adresse que vous spécifiez.
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
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549057"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Créer un fluide à partir de votre téléphone à l’aide de Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Créez un fluide à partir de votre téléphone à l’aide d’un modèle, que vous pouvez trouver en parcourant une liste de services, en recherchant des catégories ou en spécifiant des mots clés. Suivez les étapes de cette rubrique pour créer un Flow qui envoie une notification push à votre téléphone quand vous recevez du courrier de votre responsable.

Si vous n’êtes pas familiarisé avec Microsoft Flow, [consultez la présentation](getting-started.md).

## <a name="prerequisites"></a>Conditions préalables
* Un [compte pour Microsoft Flow](sign-up-sign-in.md).
* L’Microsoft Flow application mobile pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows) sur un [appareil pris en charge](getting-started.md#use-the-mobile-app). Les graphiques de cette rubrique reflètent la version iPhone de l’application, mais l’interface sur un appareil Android ou Windows Phone est similaire.
* Pour utiliser le modèle présenté dans cette rubrique, vous aurez également besoin des éléments suivants :
  
  * Informations d’identification Office 365.
  * Notifications push activées sur votre téléphone.

## <a name="find-a-template"></a>Rechercher un modèle
1. Ouvrez l’application mobile, puis appuyez sur **Parcourir** en bas de l’écran.
   
    ![Icône parcourir](./media/mobile-create-flow/browse-icon.png)
   
    Vous pouvez trouver un modèle de l’une des manières suivantes :
   
   * Spécifiez un mot clé dans la zone de recherche en haut de l’écran.
   * Appuyez sur une option dans la liste des services.
   * Faites défiler l’affichage pour afficher diverses catégories, puis appuyez sur un modèle dans n’importe quelle catégorie.
     
       ![Onglet Parcourir](./media/mobile-create-flow/browse-tab.png)
     
     Pour ce didacticiel, vous allez ouvrir le modèle qui envoie une notification push lorsque vous recevez un message de votre responsable.
2. Dans la liste des services, cliquez sur **Afficher tout**.
   
    ![Afficher la liste des services](./media/mobile-create-flow/list-services.png)
3. Appuyez sur l’icône de **notification push**.
   
    ![Notifications push](./media/mobile-create-flow/push-notifications.png)
4. Dans la barre de recherche, tapez **e-mail**, puis appuyez sur le modèle pour envoyer une notification push lorsque vous recevez un message de votre responsable.
   
    ![Choisir un modèle](./media/mobile-create-flow/choose-template.png)
5. Dans l’écran qui donne des détails sur le modèle que vous avez sélectionné, appuyez sur **utiliser ce modèle**.
   
    ![Confirmer le modèle](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Terminer le Flow
1. Si vous y êtes invité, appuyez sur **se connecter**et indiquez vos informations d’identification pour Office 365 Outlook, Office 365 utilisateurs ou les deux.
   
    ![Connectez-vous à Office 365](./media/mobile-create-flow/office-signin.png)
   
    Vous pouvez utiliser les mêmes connexions quand vous créez d’autres flux.
2. Dans l’angle supérieur droit, appuyez sur **suivant**.
   
    ![Appuyez sur suivant](./media/mobile-create-flow/next.png)
   
    L’écran suivant montre l’événement déclencheur et toutes les actions qui en résultent.
   
    ![Événements déclencheurs et actions](./media/mobile-create-flow/flow-structure.png)
   
    Pour ce modèle, un nouveau message déclenche le Flow, qui récupère vos informations (y compris l’adresse de votre responsable) et vous envoie une notification push lorsque vous recevez du courrier électronique à partir de cette adresse. Certains modèles requièrent une certaine personnalisation pour fonctionner correctement, mais ce modèle ne l’est pas.
3. facultatif Vers le haut de l’écran, tapez un nom différent pour le Flow.
   
    ![Renommer le Flow](./media/mobile-create-flow/rename-flow.png)
4. Dans l’angle supérieur droit, appuyez sur **créer**.
   
    ![créer un Flow](./media/mobile-create-flow/create-flow.png)
   
    Votre Flow est créé et vérifie la messagerie électronique de votre responsable jusqu’à ce que vous suspendiez ou supprimiez le Workflow.

## <a name="next-steps"></a>Étapes suivantes
* [Surveillez votre activité de Flow](mobile-monitor-activity.md).
* [Gérez vos flux](mobile-manage-flows.md).

