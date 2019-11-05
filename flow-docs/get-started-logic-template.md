---
title: Créer un workflow à partir d’un modèle | Microsoft Docs
description: Créez un workflow à partir de plusieurs modèles intégrés.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 874a942c4422fb402bc564609aff6ea06449ef78
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548252"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Créer un fluide à partir d’un modèle dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Créez un workflow à partir de l’un des nombreux modèles intégrés qui peuvent, par exemple, vous envoyer un message de marge lorsque votre responsable vous envoie un e-mail dans Office 365.

**Remarque :** [créez un flot à partir de zéro](get-started-logic-flow.md) si vous avez déjà un processus à l’esprit et que vous ne trouvez pas de modèle pour celui-ci.

**Conditions préalables**

* Un compte sur [Flow.Microsoft.com](https://flow.microsoft.com)
* Un compte de marge
* Informations d’identification Office 365

## <a name="choose-a-template"></a>Choisir un modèle
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Dans [Flow.Microsoft.com](https://flow.microsoft.com), sélectionnez **modèles** dans la barre de navigation supérieure.
2. Dans la barre de recherche, tapez **mou**, puis sélectionnez l’icône de recherche.
3. Vous ne verrez que les modèles liés à la marge. vous pouvez donc sélectionner **Envoyer un message sur la marge quand mon responsable m’envoie une notification par courrier électronique**.
   
    ![Nouvelle option dans la barre de navigation de gauche](./media/get-started-logic-template/select-template.png)
4. Vérifiez que ce modèle fera ce que vous voulez, puis sélectionnez **utiliser ce modèle**.
5. Si vous n’êtes pas connecté à Office ou à la marge, sélectionnez **se connecter** , puis suivez les invites.
   
    ![Liste des connexions requises par le modèle](./media/get-started-logic-template/confirm-connections.png)
6. Après avoir confirmé vos connexions, sélectionnez **Continuer**.
   
    Votre fluide s’affiche, affichant chaque action avec une barre de titre orange.
   
    ![Événements et actions par défaut à partir d’un modèle](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personnaliser votre Flow
1. Sélectionnez la barre de titre d’un événement pour la développer, puis personnalisez-la (par exemple, en spécifiant un filtre sur l’e-mail qui vous intéresse).
2. Les actions qui nécessitent une entrée de vous seront automatiquement développées.
   
    Par exemple, l’action **poster un message** est développée, car vous devez entrer un canal, tel que votre *nom d’utilisateur\@* . Vous pouvez également personnaliser le contenu du message. Par défaut, le message contient uniquement l’objet, mais vous pouvez inclure d’autres informations.
   
    ![Spécifier le canal pour la marge](./media/get-started-logic-template/specify-keyword.png)
3. Près du haut de l’écran, spécifiez un nom pour votre Flow, puis sélectionnez **créer un Flow**.
4. Enfin, si vous êtes satisfait de votre Flow, sélectionnez **terminé**.
   
    ![Bouton terminé](./media/get-started-logic-template/done.png)

Désormais, lorsque votre responsable vous envoie un e-mail, vous recevez un message de marge qui contient les informations que vous avez spécifiées.

## <a name="next-steps"></a>Étapes suivantes
* [Regardez votre Flow en action](see-a-flow-run.md)
* [Publier votre propre modèle](publish-a-template.md)
* [Utiliser un modèle pour le Common Data Service](common-data-model-intro.md)
* [Commencez avec les flux d’équipe](create-team-flows.md) et invitez d’autres personnes à collaborer avec vous pour concevoir des flux.

