---
title: Partagez vos boutons avec d’autres utilisateurs. | Microsoft Docs
description: Partagez vos boutons avec d’autres utilisateurs pour qu’ils puissent utiliser vos boutons et gagner du temps.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 098ebf9d8e02ede22a7914a2458375eb3641544a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548428"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Partager des flux de bouton dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dans l’application mobile Microsoft Flow, vous pouvez partager des [flux de bouton](introduction-to-button-flows.md) (boutons) avec d’autres utilisateurs ou groupes au sein de votre organisation. Lorsque vous partagez un bouton, la personne ou le groupe avec lequel vous partagez peut exécuter le bouton, de la même façon qu’il exécute ses propres boutons. Vous pouvez également [partager un lien](share-buttons.md#re-share-a-button) vers des boutons qu’une autre personne a partagés avec vous. Vous pouvez [cesser de partager](share-buttons.md#stop-sharing-a-button) vos boutons à tout moment.

> Les captures d’écran utilisées dans ce document proviennent d’un appareil Android. Si vous utilisez un iPhone, les images peuvent apparaître différemment, mais la fonctionnalité est la même.
> 
> 

Procédez comme [suit](share-buttons.md#use-shared-buttons) pour utiliser un bouton que quelqu’un a partagé avec vous.

## <a name="prerequisites"></a>Conditions préalables
Pour partager des boutons, vous avez besoin des éléments suivants :

* Un compte ayant accès à [Microsoft Flow](https://flow.microsoft.com).
* Un Flow à partager.
* Un appareil mobile avec l’Microsoft Flow application mobile pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Groupe ou utilisateur au sein de votre organisation avec lequel partager votre bouton.

## <a name="share-a-button"></a>Partager un bouton
Vous pouvez partager un bouton à partir de l’onglet **boutons** de l’application mobile Microsoft Flow.

1. Appuyez sur la petite icône en regard du bouton que vous souhaitez partager.
   
    ![bouton partager](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Appuyez sur **inviter d’autres personnes** à partir de la page des **utilisateurs du bouton** .
   
    ![bouton partager](./media/share-buttons/share-button-flows-button-users.png)
3. Recherchez, puis sélectionnez le groupe ou la personne avec qui vous souhaitez partager le bouton.
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Appuyez sur **Envoyer** dans la page **inviter d’autres personnes** .
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Appuyez sur **terminé** sur la page pour indiquer que l’opération de partage de bouton s’est terminée avec succès.
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Demander aux utilisateurs d’utiliser leurs propres connexions
> [!NOTE]
> Lorsque vous partagez un bouton, vous pouvez autoriser les personnes avec lesquelles vous avez partagé le bouton à utiliser toutes les connexions utilisées par votre bouton. Vous pouvez également leur demander d’utiliser leurs propres connexions. Si vous permettez à d’autres utilisateurs d’utiliser vos connexions, ils ne peuvent pas accéder aux informations d’identification de votre connexion ou les réutiliser dans un autre Flow.
> 
> 

Procédez comme suit pour exiger que les personnes avec lesquelles vous avez partagé vos boutons utilisent leurs propres connexions.

1. Sélectionnez **gérer les connexions** sur l’écran qui s’affiche immédiatement après avoir partagé un bouton.
2. Sélectionnez **modifier** sur le bouton que vous souhaitez gérer.
3. Sélectionnez **fourni par l’utilisateur** ou votre adresse de messagerie.
   
    Votre choix indique les connexions qui doivent être utilisées dans le bouton partagé.
   
    ![bouton partager](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Vous pouvez afficher ou modifier votre choix à tout moment. Pour ce faire, sélectionnez l’onglet **flux** > le flux que vous avez partagé > **utilisateurs et connexions** > l’onglet **connexions** > **modifier** sur le bouton que vous souhaitez gérer.
   
    ![bouton partager](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Afficher la liste des utilisateurs du bouton
Vous pouvez afficher tous les groupes ou utilisateurs avec lesquels un bouton est partagé en procédant comme suit à partir de l’onglet **boutons** :

1. Appuyez sur la petite icône en regard du bouton qui vous intéresse.
2. Dans la page **utilisateurs de bouton** , affichez tous les groupes ou utilisateurs avec lesquels le bouton est partagé.
   
    ![afficher les utilisateurs du bouton](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Arrêter le partage d’un bouton
Vous pouvez arrêter le partage d’un bouton en procédant comme suit à partir de l’onglet **boutons** :

1. Appuyez sur la petite icône en regard du bouton que vous ne souhaitez plus partager.
2. Dans la page **utilisateurs du bouton** , cliquez sur l’utilisateur ou le groupe dont vous souhaitez arrêter le partage du bouton.
   
    ![bouton arrêter le partage](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Appuyez sur **Supprimer l’utilisateur** lorsque la page de l’utilisateur s’affiche.
   
    ![bouton arrêter le partage](./media/share-buttons/share-button-flows-remove-user.png)
4. Attendez la fin de l’opération de suppression. Notez que le bouton liste des **utilisateurs** est actualisé et que l’utilisateur ou le groupe que vous avez supprimé n’est plus répertorié.
   
    ![bouton arrêter le partage](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Surveiller l’historique des exécutions
L’intégralité de l’historique des exécutions, y compris les exécutions lancées par une personne avec laquelle un bouton est partagé, apparaît uniquement sous l’onglet **activité** de l’application mobile du créateur de boutons Microsoft Flow.

## <a name="use-shared-buttons"></a>Utiliser des boutons partagés
Avant de pouvoir exécuter un bouton que quelqu’un a partagé avec vous, vous devez l’ajouter à l’onglet **boutons** de la page **Ajouter des boutons** .

1. Appuyez sur **obtenir plus** (ou la bannière **nouveaux boutons sont disponibles** si elle apparaît) sous l’onglet **boutons** .
   
    ![nouveau bouton partagé avec moi](./media/share-buttons/share-button-flows-banner.png)
2. Appuyez sur le bouton que vous souhaitez utiliser.
   
    Le bouton taraudé est immédiatement ajouté à l’onglet **boutons** de l’application Microsoft Flow. Vous pouvez ensuite utiliser le bouton à partir de l’onglet **boutons** , comme n’importe quel autre bouton qui y figure.
   
    ![nouveau bouton partagé avec moi](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Partager à nouveau un bouton
Vous pouvez partager un lien vers un bouton qui a été partagé avec vous.

1. Sélectionnez **...** en regard du bouton que vous souhaitez partager.
2. Sélectionnez **partager le lien du bouton**.
   
    ![repartager le lien du bouton](./media/share-buttons/re-share-button.png)
3. Sélectionnez l’application que vous souhaitez utiliser pour partager le bouton, puis suivez les étapes pour envoyer le bouton à la personne avec qui vous souhaitez partager.

## <a name="stop-using-a-shared-button"></a>Arrêter d’utiliser un bouton partagé
Si vous ne souhaitez plus utiliser un bouton qui a été partagé avec vous, supprimez-le de l’onglet **boutons** en effectuant les étapes suivantes :

1. Sous l’onglet **boutons** , appuyez sur **...** en regard du bouton que vous ne souhaitez plus utiliser.
   
    ![bouton supprimer](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Appuyez sur **supprimer** dans le menu qui s’affiche.

Voilà. Le bouton n’apparaît plus sous l’onglet **boutons** de l’application Microsoft Flow.

> [!NOTE]
> Après avoir supprimé un bouton partagé, vous pouvez le rajouter en sélectionnant **obtenir plus d’informations** dans l’onglet **boutons** .
> 
> 

