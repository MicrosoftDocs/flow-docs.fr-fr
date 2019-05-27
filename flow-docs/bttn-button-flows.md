---
title: Démarrer des flux avec des boutons bttn | Microsoft Docs
description: Découvrez comment démarrer votre flux avec un bouton bttn
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 813ad16dbc9514975daadac456b73d98fc30db79
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461895"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Exécuter vos flux avec des boutons physiques (bttns) à partir de Button Corporation (préversion)
Déclenchez vos flux en appuyant sur un bouton bttn (bouton physique développé par [The Button Corporation](https://my.bt.tn/)). Par exemple, vous pouvez appuyer sur un bouton bttn qui déclenche un flux qui effectue les tâches suivantes :

* contacte le support technique avec les informations sur le lieu ;
* envoie un courrier à votre équipe ;
* bloque votre calendrier ;
* commande des fournitures.

> [!IMPORTANT]
> Vous devez [inscrire](https://my.bt.tn/) votre bouton bttn avant de pouvoir l’utiliser dans un flux.
> 
> [!TIP]
> Configurez toutes les propriétés du bouton bttn, telles que le nom, l’emplacement et l’adresse de courrier sur le [site web bttn](https://my.bt.tn/) avant de créer votre flux.
> 
> 

Vous pouvez également déclencher un flux en utilisant un [bouton physique Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Prérequis
* Accédez à [Microsoft Flow](https://flow.microsoft.com).
* Au moins un [bouton bttn inscrit](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Créer un flux déclenché par un bouton bttn
Dans cette procédure pas à pas, nous utilisons un modèle de support technique pour créer un flux que vous pouvez déclencher en appuyant simplement sur un bouton [bttn](https://my.bt.tn/). Lorsque le flux est exécuté, il génère une demande de support et l’envoie au support technique. La demande de support fournit au support technique l’emplacement de la salle où l’aide est requise. Cette procédure pas à pas montre comment créer ce flux à partir d’un modèle, mais vous pouvez utiliser le modèle vide, ce qui vous donne un contrôle total sur tous les aspects de votre flux.

Vous pouvez utiliser un de ces modèles pour créer rapidement des flux pour votre bouton bttn et vous connecter à Zendesk, Google et SharePoint, entre autres :

![modèles bttn](./media/bttn-button-flows/bttn-templates.png)

Conseil : Dans le cadre de cette procédure pas à pas, nommez votre bouton bttn qui représente une salle de conférence dans un immeuble de bureaux classique.

Les paramètres de votre bouton bttn doivent ressembler à cet exemple (issu du site web bttn) :

![modèles bttn](./media/bttn-button-flows/bttn-config.png)

Maintenant que vous avez inscrit et configuré votre bouton bttn, vous pouvez commencer à créer votre flux.

### <a name="sign-in-and-select-a-template"></a>Se connecter et sélectionner un modèle
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
   
    ![se connecter](./media/bttn-button-flows/sign-into-flow.png)
   
    Remarque : Comme alternative, vous pouvez créer des flux dans l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).
2. Entrez **bttn** dans la zone de recherche, puis sélectionnez l’icône de recherche.
   
    ![recherche](./media/bttn-button-flows/bttn-search-template.png)
   
    Une fois que vous avez sélectionné l’icône de recherche, tous les modèles que vous pouvez utiliser avec des boutons bttn apparaissent.
3. Sélectionnez le modèle **Use Bttn to call technical support for meeting room** (Utiliser Bttn pour appeler le support technique pour une intervention dans une salle de réunion).
   
    ![modèle de support](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autoriser Microsoft Flow à se connecter à votre bouton bttn
1. Si vous y êtes invité, connectez-vous à bttn et aux services Outlook Office 365. Le bouton **Continuer** s’active alors.
   
    ![informations d’identification](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Lorsque vous vous connectez au service bttn, autorisez Microsoft Flow à utiliser vos boutons bttn.
   
    **Important**: Si vous n’autorisez Microsoft Flow à utiliser vos boutons bttn, vous ne pouvez pas voir ou s’y connecter à partir de Microsoft Flow.
   
    ![autoriser](./media/bttn-button-flows/authorize-bttn.png)
3. Une fois que vous êtes connecté aux deux services, sélectionnez le bouton **Continuer**.
   
    ![Continuer](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Sélectionner le bouton bttn qui déclenche le flux
1. Dans la carte **When a bttn is pressed** (Lors de l’appui sur un bouton bttn), ouvrez la liste des ID de bttn et sélectionnez le bouton bttn que vous souhaitez utiliser.
   
    ![sélectionner un bttn](./media/bttn-button-flows/bttn-id.png)
   
    Votre flux doit maintenant ressembler à cet exemple.
   
    ![vue d’ensemble du flux](./media/bttn-button-flows/bttn-done.png)
2. Donnez un nom à votre flux, puis sélectionnez **Créer un flux** pour l’enregistrer.
   
    ![enregistrer le flux](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Tester votre flux et vérifier les résultats
1. Appuyez sur votre bouton bttn.
2. Affichez l’historique d’exécution de votre flux pour confirmer qu’il a été correctement exécuté.
   
    Vous pouvez consulter l’historique des exécutions sur le site web Microsoft Flow ou sur votre appareil mobile.
   
    Remarque : L’état d’exécution a la valeur **en cours d’exécution** jusqu'à ce qu’un utilisateur sélectionne **accusé de réception** dans l’e-mail de demande de support.
3. Vous pouvez également vérifier que le courrier a été envoyé à l’équipe de support.
   
    Si vous avez respecté cette procédure, l’adresse de courrier de support est similaire à l’exemple suivant :
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Résolution des problèmes
* Si votre flux ne s’est pas déclenché, connectez-vous au site Button Corporation et vérifiez si l’activité de bouton (appui) est enregistrée.
* Vous pouvez également explorer en détail l’activité d’exécution sur le site Microsoft Flow et rechercher les messages d’erreur.

## <a name="more-information"></a>Plus d’informations
* [Partager des flux de bouton](share-buttons.md).
* Apprenez à utiliser les [jetons de déclencheur de bouton](introduction-to-button-trigger-tokens.md) pour envoyer les données actuelles lorsque vos flux de bouton sont exécutés.
* [Installer l’application Microsoft Flow pour Android](https://aka.ms/flowmobiledocsandroid)
* [Installer l’application Microsoft Flow pour iOS](https://aka.ms/flowmobiledocsios)

