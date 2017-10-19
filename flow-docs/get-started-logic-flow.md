---
title: "Automatiser les tâches en créant un flux | Microsoft Docs"
description: "Créez un flux pour effectuer automatiquement une ou plusieurs actions (telles que l’envoi d’un message électronique) lorsque des événements se produisent (par exemple si une ligne est ajoutée à une liste SharePoint)."
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Créer un flux dans Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Créez un flux qui effectue une ou plusieurs tâches automatiquement une fois qu’il est déclenché par un événement. Par exemple, créez un flux qui vous avertit par courrier électronique dès que quelqu’un envoie un tweet contenant un mot clé que vous spécifiez. Dans cet exemple, l’envoi d’un tweet est l’événement et l’envoi d’un message électronique est l’action.

## <a name="prerequisites"></a>Conditions préalables
* Un compte sur [flow.microsoft.com](https://flow.microsoft.com)
* Un compte Twitter
* Informations d’identification Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Spécifier un événement qui déclenche le flux
Tout d’abord, vous devez sélectionner l’événement ou le *déclencheur* qui lance votre flux.

1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure, puis **Créer entièrement**.
   
    ![Option Flux dans la barre de navigation gauche](./media/get-started-logic-flow/create-logic-flow.png)
2. Dans la zone intitulée **Rechercher dans l’ensemble des connecteurs et des déclencheurs**, tapez ou collez **Twitter**, puis sélectionnez **Twitter - Lors de la publication d’un nouveau tweet**.
   
    ![Événement Twitter](./media/get-started-logic-flow/twitter-search.png)
3. Si vous n’avez pas déjà connecté votre compte Twitter à Microsoft Flow, sélectionnez **Se connecter à Twitter**, puis entrez vos informations d’identification.
   
    ![Connexion à Twitter](./media/get-started-logic-flow/twitter-signin.png)
4. Dans la zone **Texte de recherche**, tapez le mot clé que vous souhaitez rechercher.
   
    ![Mot clé Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Spécifier une action
1. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.
   
    ![Ajouter une action](./media/get-started-logic-flow/add-action-icon.png)
2. Dans la zone intitulée **Rechercher dans l’ensemble des connecteurs et des actions**, tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook - Envoyer un message électronique**.
   
    ![Liste d’actions](./media/get-started-logic-flow/send-email.png)
3. Si vous y êtes invité, sélectionnez le bouton de connexion, puis fournissez vos informations d’identification.
4. Dans le formulaire qui apparaît, tapez ou collez votre adresse de messagerie dans la zone **À**, puis sélectionnez votre nom dans la liste de contacts qui s’affiche.
   
    ![Message électronique vide](./media/get-started-logic-flow/blank-email.png)
5. Dans la zone **Objet**, tapez ou collez **New tweet from:** (Nouveau tweet de :), puis tapez une espace.
   
    ![Ligne d’objet avec espace réservé](./media/get-started-logic-flow/message-token.png)
6. Dans la liste des jetons, sélectionnez le jeton **Tweeté par** pour ajouter un espace réservé pour celui-ci.
   
    ![Ajouter un paramètre](./media/get-started-logic-flow/add-parameter.png)
7. Cliquez ou appuyez sur la zone **Corps**, puis sur le jeton **Texte du tweet** pour ajouter un espace réservé pour celui-ci.
8. (facultatif) Ajoutez davantage de jetons, d’autres contenus ou les deux dans le corps du message électronique.
9. Près du haut de l’écran, nommez votre flux, puis sélectionnez **Créer un flux**.
   
    ![Sélectionner le bouton Créer un flux](./media/get-started-logic-flow/create-button.png)
10. Sélectionnez **Terminé** pour mettre à jour la liste de vos flux.
    
     ![Sélectionner le bouton Terminé](./media/get-started-logic-flow/done-button.png)
11. Envoyez un tweet avec le mot clé que vous avez indiqué.
    
     Au bout d’une minute, un message vous informe du nouveau tweet.

## <a name="manage-a-flow"></a>Gérer un flux
1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure.
2. Dans la liste de flux, effectuez l’une des opérations suivantes :
   
   * Pour suspendre un flux, réglez son bouton bascule sur **Désactivé**.
     
       ![Suspendre un flux](./media/get-started-logic-flow/pause-flow.png)
   * Pour reprendre un flux, réglez son bouton bascule sur **Activé**.
     
       ![Reprendre un flux](./media/get-started-logic-flow/resume-flow.png)
   * Pour modifier un flux, sélectionnez l’icône de crayon qui correspond au flux que vous souhaitez modifier.
     
       ![Sélectionner un flux](./media/get-started-logic-flow/select-flow.png)
   * Pour supprimer un flux, sélectionnez l’icône **...**, sélectionnez **Supprimer**, puis **Supprimer** dans la zone de message qui apparaît.
     
       ![Icône Supprimer](./media/get-started-logic-flow/delete-icon.png)
   * Pour afficher l’historique d’exécution d’un flux, sélectionnez le flux à partir de la page **Mes flux**, puis affichez l’historique sous la section **Historique d’exécution** de la page qui s’ouvre.
     
       ![historique d’exécution](./media/get-started-logic-flow/run-history.png)
     
     Sélectionnez une exécution de flux dans la liste des exécutions pour voir les entrées et sorties de chaque étape.

**Remarque** : votre compte peut avoir jusqu’à 50 flux. Si vous en avez déjà 50, supprimez-en un avant de pouvoir en créer un autre.

## <a name="next-steps"></a>Étapes suivantes
* [Ajoutez des étapes](multi-step-logic-flow.md) à votre flux, par exemple les différentes façons d’être averti.
* [Exécutez des tâches selon une planification](run-tasks-on-a-schedule.md), lorsque vous souhaitez qu’une action s’exécute chaque jour, à une certaine date ou après un certain nombre de minutes.
* [Ajoutez un flux à une application](https://powerapps.microsoft.com/tutorials/using-logic-flows/) pour permettre à cette dernière de lancer la logique dans le cloud.
* [Prenez en main les flux d’équipe](create-team-flows.md) et invitez des personnes à collaborer avec vous lors de la conception de flux.

