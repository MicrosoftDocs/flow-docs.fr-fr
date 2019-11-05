---
title: Démarrer des flux avec boutons BTTN | Microsoft Docs
description: Découvrez comment démarrer vos flux avec un bouton BTTN
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
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545688"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Exécuter vos flux avec des boutons physiques (boutons BTTN) à partir du bouton Corporation (version préliminaire)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Déclenchez vos flux en appuyant sur un bouton BTTN (un bouton physique effectué par [le bouton Corporation](https://my.bt.tn/)). Par exemple, vous pouvez appuyer sur un bouton BTTN qui déclenche un Flow pour effectuer les tâches suivantes :

* contacte votre support technique avec les informations relatives à l’emplacement
* envoie un e-mail à votre équipe
* bloque votre calendrier
* réorganiser les fournitures

> [!IMPORTANT]
> Vous devez [inscrire](https://my.bt.tn/) votre bouton BTTN pour pouvoir l’utiliser dans un Workflow.
> 
> [!TIP]
> Configurez toutes les propriétés bouton BTTN, telles que le nom, l’emplacement et l’adresse de messagerie sur le [site Web bouton BTTN](https://my.bt.tn/) avant de créer votre fluide.
> 
> 

Vous pouvez également déclencher un Flow à l’aide d’un [bouton physique flic](flic-button-flows.md).

## <a name="prerequisites"></a>Conditions préalables
* Accès aux [Microsoft Flow](https://flow.microsoft.com).
* Au moins un [bouton BTTN inscrit](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Créer un fluide qui est déclenché à partir d’un bouton BTTN
Dans cette procédure pas à pas, nous utilisons un modèle de support technique pour créer un Flow que vous pouvez déclencher avec une seule pression d’une [bouton BTTN](https://my.bt.tn/). Lorsque le workflow s’exécute, il génère une demande de support, puis l’envoie au support technique. La demande de support fournit au support technique l’emplacement de la salle où l’aide est nécessaire. Cette procédure pas à pas montre comment créer ce fluide à partir d’un modèle, mais vous pouvez utiliser le modèle vide, qui vous donne un contrôle total sur tous les aspects de votre Flow.

Vous pouvez utiliser n’importe lequel de ces modèles pour créer rapidement des flux pour votre bouton BTTN et vous connecter à Zendesk, Google et SharePoint, entre autres :

![modèles bouton BTTN](./media/bttn-button-flows/bttn-templates.png)

Conseil : pour les besoins de cette procédure pas à pas, donnez à votre bouton BTTN un nom qui représente une salle de conférence dans un immeuble de bureaux.

Les paramètres de votre bouton BTTN doivent ressembler à cet exemple (à partir du site Web bouton BTTN) :

![modèles bouton BTTN](./media/bttn-button-flows/bttn-config.png)

Maintenant que vous avez inscrit et configuré votre bouton BTTN, commençons à créer notre Flow.

### <a name="sign-in-and-select-a-template"></a>Se connecter et sélectionner un modèle
1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com).
   
    ![Connexion](./media/bttn-button-flows/sign-into-flow.png)
   
    Remarque : vous pouvez également créer des flux dans l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
2. Entrez **bouton BTTN** dans la zone de recherche, puis sélectionnez l’icône de recherche.
   
    ![Recherche](./media/bttn-button-flows/bttn-search-template.png)
   
    Une fois que vous avez sélectionné l’icône de recherche, tous les modèles que vous pouvez utiliser avec boutons BTTN s’affichent.
3. Sélectionnez le modèle **utiliser bouton BTTN pour appeler le support technique pour la salle de réunion** .
   
    ![modèle de prise en charge](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autoriser Microsoft Flow à se connecter à votre bouton BTTN
1. Si vous y êtes invité, connectez-vous à bouton BTTN et aux services Office 365 Outlook, ce qui activera le bouton **Continuer** .
   
    ![informations d’identification](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Lorsque vous vous connectez au service bouton BTTN, autorisez Microsoft Flow à utiliser votre boutons BTTN.
   
    **Important**: Si vous n’autorisez pas Microsoft Flow à utiliser votre boutons BTTN, vous ne pouvez pas les voir ou vous y connecter à partir de Microsoft Flow.
   
    ![autoriser](./media/bttn-button-flows/authorize-bttn.png)
3. Une fois que vous êtes connecté aux deux services, sélectionnez **Continuer**.
   
    ![Pouvoir](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Sélectionner le bouton BTTN qui déclenche le Flow
1. Dans la carte **lorsqu’un bouton BTTN est enfoncé** , ouvrez la liste des ID bouton BTTN, puis sélectionnez le bouton BTTN que vous souhaitez utiliser.
   
    ![Sélectionner bouton BTTN](./media/bttn-button-flows/bttn-id.png)
   
    Votre Flow doit maintenant ressembler à cet exemple.
   
    ![vue d’ensemble du Flow](./media/bttn-button-flows/bttn-done.png)
2. Donnez un nom à votre Flow, puis sélectionnez **créer un Flow** pour l’enregistrer.
   
    ![enregistrer le Flow](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Tester votre Flow et confirmer les résultats
1. Appuyez sur le bouton sur votre bouton BTTN.
2. Affichez l’historique des exécutions de votre Flow pour confirmer qu’il a été correctement exécuté.
   
    Vous pouvez consulter l’historique des exécutions sur le site Web Microsoft Flow ou sur votre appareil mobile.
   
    Remarque : l’état d’exécution est défini sur **en cours d’exécution** jusqu’à ce qu’un utilisateur sélectionne **accuser réception** dans l’e-mail de demande de support.
3. Vous pouvez également vérifier que le message électronique a été envoyé à l’équipe de support technique.
   
    Si vous avez suivi cette procédure, le courrier électronique de support ressemble à l’exemple suivant :
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Dépannage
* Si votre Flow n’est pas déclenché, connectez-vous au site Button Corporation et vérifiez si l’activité du bouton (presse) est en cours d’enregistrement.
* Vous pouvez également examiner l’activité d’exécution sur le site Microsoft Flow et rechercher les messages d’erreur.

## <a name="more-information"></a>Plus d’informations
* [Partager des flux de bouton](share-buttons.md).
* Apprenez à utiliser les [jetons de déclencheur de bouton](introduction-to-button-trigger-tokens.md) pour envoyer les données actuelles lorsque vos flux de bouton sont exécutés.
* [Installez l’application Microsoft Flow pour Android](https://aka.ms/flowmobiledocsandroid).
* [Installez l’application Microsoft Flow pour iOS](https://aka.ms/flowmobiledocsios).

