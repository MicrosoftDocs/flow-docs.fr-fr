---
title: "Partagez vos boutons avec d’autres utilisateurs. | Microsoft Docs"
description: "Partagez vos boutons avec d’autres utilisateurs de votre choix pour leur faire gagner du temps."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
ms.openlocfilehash: 2804c683defb94f87c40452a27382bc143c11f10
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="share-button-flows-in-microsoft-flow"></a>Partager des flux de bouton dans Microsoft Flow
L’application mobile pour Microsoft Flow vous permet de partager des [flux de bouton](introduction-to-button-flows.md) (boutons) avec d’autres utilisateurs ou groupes au sein de votre organisation. Quand vous partagez un bouton, la personne ou le groupe bénéficiaires du partage peuvent exécuter ce bouton comme s’il était le leur. Vous pouvez également [partager un lien](share-buttons.md#re-share-a-button) vers un bouton qu’une autre personne a partagé avec vous. Vous pouvez [cesser de partager](share-buttons.md#stop-sharing-a-button) vos boutons à tout moment.

> Les captures d’écran figurant dans ce document ont été prises sur un appareil Android. Si vous utilisez un iPhone, les images peuvent s’afficher différemment, mais la fonctionnalité est la même.
> 
> 

Procédez [comme suit](share-buttons.md#use-shared-buttons) pour utiliser un bouton qu’un autre utilisateur a partagé avec vous.

## <a name="prerequisites"></a>Conditions préalables
Pour partager des boutons, vous avez besoin des éléments suivants :

* Un compte ayant accès à [Microsoft Flow](https://flow.microsoft.com).
* Un flux à partager.
* Appareil mobile avec l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Un groupe ou un utilisateur au sein de votre organisation avec qui partager votre bouton.

## <a name="share-a-button"></a>Partager un bouton
Vous pouvez partager un bouton à partir de l’onglet **Boutons** de l’application mobile Microsoft Flow.

1. Appuyez sur la petite icône en regard du bouton que vous voulez partager.
   
    ![bouton partager](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Appuyez sur **Inviter d’autres personnes** à partir de la page **Button users** (Utilisateurs de bouton).
   
    ![bouton partager](./media/share-buttons/share-button-flows-button-users.png)
3. Recherchez et sélectionnez le groupe ou la personne avec qui vous voulez partager le bouton.
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Appuyez sur **ENVOYER** dans la page **Inviter d’autres personnes**.
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Appuyez sur **TERMINÉ** dans la page qui indique que l’opération de partage de bouton a bien abouti.
   
    ![bouton partager](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Demander aux utilisateurs d’utiliser leurs propres connexions
> [!NOTE]
> Lorsque vous partagez un bouton, vous pouvez autoriser les personnes bénéficiaires du partage à se servir de toutes les connexions que votre bouton utilise. Vous pouvez également exiger qu’elles utilisent leurs propres connexions. Les personnes que vous autorisez à utiliser vos connexions ne peuvent pas accéder aux informations d’identification de votre connexion ou réutiliser celles-ci dans un autre flux.
> 
> 

Pour exiger des personnes avec lesquelles vous partagez vos boutons qu’elles utilisent leurs propres connexions, procédez comme suit.

1. Sélectionnez **Gérer les connexions** sur l’écran qui s’affiche immédiatement après que vous avez partagé un bouton.
2. Sélectionnez **Modifier** sur le bouton que vous souhaitez gérer.
3. Sélectionnez **Fourni par l’utilisateur** ou votre adresse e-mail.
   
    Votre choix indique les connexions à utiliser dans le bouton partagé.
   
    ![bouton partager](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Vous pouvez afficher ou modifier votre choix à tout moment. Pour ce faire, sélectionnez l’onglet **Flux** > le flux partagé > **Utilisateurs/connexions** > l’onglet **Connexions** > **Modifier** sur le bouton à gérer.
   
    ![bouton partager](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Afficher la liste des utilisateurs de bouton
Vous pouvez visualiser tous les groupes ou utilisateurs avec lesquels un bouton est partagé en procédant comme suit dans l’onglet **Boutons** :

1. Appuyez sur la petite icône en regard du bouton qui vous intéresse.
2. Dans la page **Button users** (Utilisateurs de bouton), affichez tous les groupes ou utilisateurs avec lesquels le bouton est partagé.
   
    ![afficher les utilisateurs d’un bouton](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Arrêter le partage d’un bouton
Vous pouvez arrêter le partage d’un flux de bouton en effectuant les étapes suivantes à partir de l’onglet **Boutons** :

1. Appuyez sur la petite icône en regard du bouton que vous voulez cesser de partager.
2. Dans la page **Button users** (Utilisateurs de bouton), appuyez sur l’utilisateur ou le groupe avec lequel vous souhaitez arrêter le partage du bouton.
   
    ![arrêter le partage d’un bouton](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Appuyez sur **Supprimer l’utilisateur** dans la page de l’utilisateur qui s’affiche.
   
    ![arrêter le partage d’un bouton](./media/share-buttons/share-button-flows-remove-user.png)
4. Attendez que l’opération de suppression se termine. Notez que la liste **Button users** (Utilisateurs de bouton) s’actualise et que l’utilisateur ou le groupe que vous avez supprimé n’est plus répertorié.
   
    ![arrêter le partage d’un bouton](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Analyser l’historique d’exécution
L’historique de toutes les exécutions, notamment de celles initiées par une personne avec qui un bouton a été partagé, apparaît uniquement sous l’onglet **Activité** de l’application mobile Microsoft Flow du créateur du bouton.

## <a name="use-shared-buttons"></a>Utiliser des boutons partagés
Avant de pouvoir exécuter un bouton que quelqu’un a partagé avec vous, vous devez l’ajouter à votre onglet **Boutons** de la page **Ajouter des boutons**.

1. Appuyez sur **EN VOIR D’AUTRES** (ou sur la bannière **New buttons are available** (De nouveaux boutons sont disponibles) si elle apparaît) dans l’onglet **Buttons** (Boutons).
   
    ![nouveau bouton partagé avec vous](./media/share-buttons/share-button-flows-banner.png)
2. Appuyez sur le bouton que vous souhaitez utiliser.
   
    Le bouton sur lequel vous appuyez est immédiatement ajouté à l’onglet **Boutons** de l’application Microsoft Flow. Vous pouvez ensuite utiliser le bouton sous l’onglet **Boutons**, comme les autres boutons qui y figurent.
   
    ![nouveau bouton partagé avec vous](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Re-partager un bouton
Vous pouvez partager un lien vers un bouton qui a été partagé avec vous.

1. Appuyez sur **...** en regard du bouton que vous voulez partager.
2. Sélectionnez **Partager un lien de bouton**.
   
    ![Re-partager un lien de bouton](./media/share-buttons/re-share-button.png)
3. Sélectionnez l’application à utiliser pour partager le bouton, puis suivez la procédure pour envoyer le bouton à la personne avec laquelle vous souhaitez le partager.

## <a name="stop-using-a-shared-button"></a>Arrêter d’utiliser un bouton partagé
Si vous ne voulez plus utiliser un bouton qui a été partagé avec vous, supprimez-le de l’onglet **Boutons** en procédant comme suit :

1. Dans l’onglet **Boutons**, appuyez sur **...** en regard du bouton que vous ne voulez plus utiliser.
   
    ![supprimer un bouton](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Appuyez sur **Supprimer** dans le menu qui s’affiche.

Voilà. Le bouton n’apparaît plus sous l’onglet **Boutons** de l’application Microsoft Flow.

> [!NOTE]
> Si nécessaire, vous pouvez le rajouter en sélectionnant **EN VOIR D’AUTRES** sous ce même onglet **Boutons**
> 
> 

