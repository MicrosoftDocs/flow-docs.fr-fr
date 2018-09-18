---
title: Automatiser les tâches en créant un flux | Microsoft Docs
description: Créez un flux qui effectue automatiquement une ou plusieurs actions (par exemple, envoyer un e-mail) quand des événements comme l’ajout d’une ligne à une liste SharePoint se produisent.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: db0d7003017eb9929b03a89f697defb40c5ed6e4
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690832"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Créer un flux dans Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Créez un flux qui effectue une ou plusieurs tâches automatiquement une fois qu’il est déclenché par un événement. Par exemple, créez un flux qui vous avertit par courrier électronique dès que quelqu’un envoie un tweet contenant un mot clé que vous spécifiez. Dans cet exemple, l’envoi d’un tweet est l’événement et l’envoi d’un message électronique est l’action.

## <a name="prerequisites"></a>Prérequis

* Un compte sur [flow.microsoft.com](https://flow.microsoft.com)
* Un compte Twitter
* Informations d’identification Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Spécifier un événement qui déclenche le flux

Tout d’abord, vous devez sélectionner l’événement ou le *déclencheur* qui lance votre flux.

1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure, puis **Créer entièrement**.

    ![Option Flux dans la barre de navigation gauche](./media/get-started-logic-flow/create-logic-flow.png)
1. Cochez la case **Rechercher des centaines de connecteurs et de déclencheurs**en bas de l’écran, entrez **Twitter** dans la zone qui indique **Rechercher tous les connecteurs et les déclencheurs**, puis sélectionnez **Twitter - Quand un nouveau tweet est posté**.

    ![Événement Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Si vous n’avez pas déjà connecté votre compte Twitter à Microsoft Flow, sélectionnez **Se connecter à Twitter**, puis entrez vos informations d’identification.

1. Dans la zone **Texte de recherche**, tapez le mot clé que vous souhaitez rechercher.

    ![Mot clé Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Spécifier une action

1. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.

    ![Ajouter une action](./media/get-started-logic-flow/add-action-icon.png)

1. Dans la zone intitulée **Rechercher dans l’ensemble des connecteurs et des actions**, tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook - Envoyer un message électronique**.

    ![Liste d’actions](./media/get-started-logic-flow/send-email.png)

1. Si vous y êtes invité, sélectionnez le bouton de connexion, puis fournissez vos informations d’identification.

1. Dans le formulaire qui apparaît, tapez ou collez votre adresse de messagerie dans la zone **À**, puis sélectionnez votre nom dans la liste de contacts qui s’affiche.

    ![Message électronique vide](./media/get-started-logic-flow/blank-email.png)
1. Dans la zone **Objet**, tapez ou collez **New tweet from:** (Nouveau tweet de :), puis tapez une espace.

    ![Ligne d’objet avec espace réservé](./media/get-started-logic-flow/message-token.png)
1. Dans la liste des jetons, sélectionnez le jeton **Tweeté par** pour ajouter un espace réservé pour celui-ci.

    ![Ajouter un paramètre](./media/get-started-logic-flow/add-parameter.png)
1. Sélectionnez la zone **Corps**, puis le jeton **Texte du tweet** pour ajouter un espace réservé pour celui-ci.
1. (facultatif) Ajoutez davantage de jetons, d’autres contenus ou les deux dans le corps du message électronique.
1. Près du haut de l’écran, nommez votre flux, puis sélectionnez **Créer un flux**.

    ![Sélectionner le bouton Créer un flux](./media/get-started-logic-flow/create-button.png)
1. Sélectionnez **Terminé** pour mettre à jour la liste de flux.

     ![Sélectionner le bouton Terminé](./media/get-started-logic-flow/done-button.png)
1. Envoyez un tweet avec le mot clé que vous avez indiqué ou attendez que quelqu'un d’autre poste un tweet de ce type.

     Une minute après l’envoi du tweet, un e-mail vous informe du nouveau tweet.

## <a name="manage-a-flow"></a>Gérer un flux

1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure.
1. Dans la liste de flux, effectuez l’une des opérations suivantes :

   * Pour suspendre un flux, réglez son bouton bascule sur **Désactivé**.

       ![Suspendre un flux](./media/get-started-logic-flow/pause-flow.png)
   * Pour reprendre un flux, réglez son bouton bascule sur **Activé**.

       ![Reprendre un flux](./media/get-started-logic-flow/resume-flow.png)
   * Pour modifier un flux, sélectionnez l’icône de crayon qui correspond au flux à modifier.

       ![Sélectionner un flux](./media/get-started-logic-flow/select-flow.png)
   * Pour supprimer un flux, sélectionnez l’icône **...**, sélectionnez **Supprimer**, puis **Supprimer** dans la zone de message qui apparaît.

       ![Icône Supprimer](./media/get-started-logic-flow/delete-icon.png)
   * Pour afficher l’historique d’exécution d’un flux, sélectionnez le flux à partir de la page **Mes flux**, puis affichez l’historique sous la section **Historique d’exécution** de la page qui s’ouvre.

       ![historique d’exécution](./media/get-started-logic-flow/run-history.png)

     Sélectionnez une exécution de flux dans la liste des exécutions pour voir les entrées et sorties de chaque étape.

> [!NOTE]
> Votre compte peut avoir jusqu’à 50 flux. Si vous en avez déjà 50, supprimez-en un avant de pouvoir en créer un autre.
>
>

## <a name="next-steps"></a>Étapes suivantes

* [Ajoutez des étapes](multi-step-logic-flow.md) à votre flux, par exemple les différentes façons d’être averti.
* [Exécutez des tâches selon une planification](run-scheduled-tasks.md), lorsque vous souhaitez qu’une action s’exécute chaque jour, à une certaine date ou après un certain nombre de minutes.
* [Ajoutez un flux à une application](https://powerapps.microsoft.com/tutorials/using-logic-flows/) pour permettre à cette dernière de lancer la logique dans le cloud.
* [Prenez en main les flux d’équipe](create-team-flows.md) et invitez des personnes à collaborer avec vous lors de la conception de flux.
