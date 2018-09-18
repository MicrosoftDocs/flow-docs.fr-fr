---
title: Créer un flux à partir d’un modèle | Microsoft Docs
description: Créez un flux à partir d’un des modèles intégrés.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689453"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Créer un flux à partir d’un modèle dans Microsoft Flow
Créez un flux à partir d’un des nombreux modèles intégrés qui peuvent, par exemple, vous envoyer un message Slack lorsque votre responsable vous envoie un message électronique dans Office 365.

**Remarque :** [créez un flux de zéro](get-started-logic-flow.md) si vous avez déjà un processus à l’esprit et que vous ne trouvez aucun modèle correspondant.

**Conditions préalables**

* Un compte sur [flow.microsoft.com](https://flow.microsoft.com)
* Un compte Slack
* Informations d’identification Office 365

## <a name="choose-a-template"></a>Choisir un modèle
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Modèles** dans la barre de navigation supérieure.
2. Dans la barre de recherche, tapez **Slack**, puis sélectionnez l’icône de recherche.
3. Seuls les modèles associés à Slack s’affichent. Vous pouvez maintenant sélectionner **Envoyer un message sur Slack quand mon responsable m’envoie des e-mails**.
   
    ![Nouvelle option dans la barre de navigation gauche](./media/get-started-logic-template/select-template.png)
4. Vérifiez que ce modèle correspond à que vous souhaitez faire, puis sélectionnez **Utiliser ce modèle**.
5. Si vous n’êtes pas connecté à Office ou Slack, sélectionnez **Se connecter**, puis suivez les invites.
   
    ![Liste des connexions requises par le modèle](./media/get-started-logic-template/confirm-connections.png)
6. Après avoir vérifié vos connexions, sélectionnez **Continuer**.
   
    Votre flux s’ouvre. Il affiche chaque action avec une barre de titre orange.
   
    ![Actions et événements par défaut à partir d’un modèle](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personnaliser votre flux
1. Sélectionnez la barre de titre d’un événement pour la développer, puis personnalisez-la (par exemple en spécifiant un filtre sur la messagerie qui vous intéresse).
2. Les actions qui nécessitent une intervention de votre part sont automatiquement développées.
   
    Par exemple, l’action **Publier un message** est développée, car vous devez entrer un canal, tel que votre *\@nom_utilisateur*. Vous pouvez également personnaliser le contenu du message. Par défaut, le message contient simplement l’objet, mais vous pouvez inclure d’autres informations.
   
    ![Spécifier le canal Slack](./media/get-started-logic-template/specify-keyword.png)
3. Près du haut de l’écran, spécifiez le nom de votre flux, puis sélectionnez **Créer un flux**.
4. Enfin, si vous êtes satisfait de votre flux, sélectionnez **Terminé**.
   
    ![Bouton Terminé](./media/get-started-logic-template/done.png)

Maintenant, lorsque votre responsable vous envoie un message électronique, vous recevez un message de Slack contenant les informations que vous avez spécifiées.

## <a name="next-steps"></a>Étapes suivantes
* [Voir votre flux en action](see-a-flow-run.md)
* [Publier votre propre modèle](publish-a-template.md)
* [Utiliser un modèle pour Common Data Service](common-data-model-intro.md)
* [Prenez en main les flux d’équipe](create-team-flows.md) et invitez des personnes à collaborer avec vous lors de la conception de flux.

