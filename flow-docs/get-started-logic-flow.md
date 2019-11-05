---
title: Automatiser les tâches en créant un Flow | Microsoft Docs
description: Créez un Flow qui effectue automatiquement une ou plusieurs actions, telles que l’envoi de courrier électronique, lorsque des événements tels qu’une personne qui ajoute une ligne à une liste SharePoint se produisent.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548307"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Créer un Flow dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Créer un Flow qui effectue automatiquement une ou plusieurs tâches après qu’il a été déclenché par un événement. Par exemple, créez un Flow qui vous avertit par courrier électronique quand quelqu’un envoie un tweet contenant un mot clé que vous spécifiez. Dans cet exemple, l’envoi d’un tweet est l’événement et l’envoi d’un message est l’action.

## <a name="prerequisites"></a>Conditions préalables

* Un compte sur [Flow.Microsoft.com](https://flow.microsoft.com)
* Un compte Twitter
* Informations d’identification Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Spécifier un événement pour démarrer le workflow

Tout d’abord, vous devez sélectionner l’événement ou le *déclencheur*qui démarre votre workflow.

1. Dans [Flow.Microsoft.com](https://flow.microsoft.com), sélectionnez **mes flux** dans la barre de navigation supérieure, puis **créer à partir d’un espace**.

    ![Option flux dans la barre de navigation de gauche](./media/get-started-logic-flow/create-logic-flow.png)
1. Sélectionnez la zone **Rechercher des centaines de connecteurs et de déclencheurs** en bas de l’écran, entrez **Twitter** dans la zone intitulée **Rechercher dans tous les connecteurs et déclencheurs**, puis sélectionnez **Twitter-quand un nouveau Tweet est publié**.

    ![Événement Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Si vous n’avez pas encore connecté votre compte Twitter à Microsoft Flow, sélectionnez **se connecter à Twitter**, puis indiquez vos informations d’identification.

1. Dans la zone de **texte Rechercher** , tapez le mot clé que vous souhaitez rechercher.

    ![Mot clé Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Spécifier une action

1. Sélectionnez **nouvelle étape**, puis **Ajouter une action**.

    ![Ajouter une action](./media/get-started-logic-flow/add-action-icon.png)

1. Dans la zone qui affiche **Rechercher tous les connecteurs et actions**, tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook-envoyer un e-mail**.

    ![Liste des actions](./media/get-started-logic-flow/send-email.png)

1. Si vous y êtes invité, sélectionnez le bouton de connexion, puis indiquez vos informations d’identification.

1. Dans le formulaire qui s’affiche, tapez ou collez votre adresse de messagerie dans la zone **à** , puis sélectionnez votre nom dans la liste des contacts qui s’affiche.

    ![Message électronique vide](./media/get-started-logic-flow/blank-email.png)
1. Dans la zone **objet** , tapez ou collez **New Tweet from :** , puis tapez un espace.

    ![Ligne d’objet avec espace réservé](./media/get-started-logic-flow/message-token.png)
1. Dans la liste des jetons, sélectionnez le jeton **tweeté par** pour ajouter un espace réservé pour celui-ci.

    ![Ajouter un paramètre](./media/get-started-logic-flow/add-parameter.png)
1. Sélectionnez la zone **corps** , puis sélectionnez le jeton de **texte Tweet** pour ajouter un espace réservé pour celui-ci.
1. facultatif Ajoutez des jetons supplémentaires, d’autres contenus ou les deux dans le corps de l’e-mail.
1. Près du haut de l’écran, nommez votre Flow, puis sélectionnez **créer un Flow**.

    ![Sélectionner le bouton créer un Flow](./media/get-started-logic-flow/create-button.png)
1. Sélectionnez **terminé** pour mettre à jour la liste des flux.

     ![Sélectionner le bouton terminé](./media/get-started-logic-flow/done-button.png)
1. Envoyez un tweet avec le mot clé que vous avez indiqué, ou attendez qu’un autre utilisateur publie ce tweet.

     Au bout d’une minute après la publication du tweet, un message électronique vous avertit du nouveau tweet.

> [!TIP]
> Utilisez l’action **Envoyer un message électronique (v2)** pour mettre en forme le courrier électronique dans lequel vous personnalisez la police, utilisez le gras, l’italique ou le soulignement, personnalisez la couleur et la mise en surbrillance, créez des listes ou des liens, et bien plus encore.

![Messagerie Rich Edit](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Gérer un Flow

1. Dans [Flow.Microsoft.com](https://flow.microsoft.com), sélectionnez **mes flux** dans la barre de navigation supérieure.
1. Dans la liste des flux, effectuez l’une des opérations suivantes :

   * Pour suspendre un Flow, affectez la valeur **off**à son bouton bascule.

       ![Suspendre le workflow](./media/get-started-logic-flow/pause-flow.png)
   * Pour reprendre un Flow, affectez la valeur **on**à son bouton bascule.

       ![Reprendre le Flow](./media/get-started-logic-flow/resume-flow.png)
   * Pour modifier un fluide, sélectionnez l’icône représentant un crayon qui correspond au fluide que vous souhaitez modifier.

       ![Sélectionner un Flow](./media/get-started-logic-flow/select-flow.png)
   * Pour supprimer un fluide, sélectionnez l’icône **...** , sélectionnez **supprimer**, puis sélectionnez **supprimer** dans la boîte de message qui s’affiche.

       ![Icône Supprimer](./media/get-started-logic-flow/delete-icon.png)
   * Pour afficher l’historique des exécutions d’un flux, sélectionnez le flux à partir de la page **mes flux** , puis affichez l’historique sous la section **historique des exécutions** de la page qui s’ouvre.

       ![historique des exécutions](./media/get-started-logic-flow/run-history.png)

     Sélectionnez une exécution de workflow dans la liste des séries de tests pour afficher les entrées et les sorties de chaque étape.

> [!NOTE]
> Vous pouvez avoir jusqu’à 600 flux dans votre compte. Si vous avez déjà 600 flux, supprimez-en un avant de créer un autre flux.
>
>

## <a name="next-steps"></a>Étapes suivantes

* [Ajoutez des étapes](multi-step-logic-flow.md), telles que des méthodes différentes pour être notifiées, à votre Flow.
* [Exécuter des tâches selon une planification](run-scheduled-tasks.md), lorsque vous souhaitez qu’une action se produise quotidiennement, à une certaine date ou après un certain nombre de minutes.
* [Ajoutez un Flow à une application](https://powerapps.microsoft.com/tutorials/using-logic-flows/) pour permettre à votre application de démarrer la logique dans le Cloud.
* [Commencez avec les flux d’équipe](create-team-flows.md) et invitez d’autres personnes à collaborer avec vous pour concevoir des flux.
