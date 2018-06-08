---
title: Lancer des flux avec des boutons Flic | Microsoft Docs
description: Démarrez facilement les flux de bouton avec des boutons physiques à partir de Flic, proposé par Shortcut Labs.
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
ms.date: 05/19/2017
ms.author: deonhe
ms.openlocfilehash: 518834103c1a17ef2f5af218eae43ccab4e5fda2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440836"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Exécuter vos flux en appuyant sur un bouton intelligent Flic (préversion)
Déclenchez vos flux en appuyant sur un bouton physique, appelé Flic, proposé par Shortcut Labs. Par exemple, appuyez sur un bouton Flic pour effectuer le suivi de vos heures de travail, bloquer votre calendrier, compter le nombre de visiteurs lors d’un événement ou enregistrer des emplacements géographiques.

> [!IMPORTANT]
> Configurez toutes les propriétés de Flic à l’aide de l’application mobile Flic pour [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) avant de créer votre flux.
> 
> 

## <a name="prerequisites"></a>Prérequis
Voici les prérequis pour utiliser des boutons Flic avec Microsoft Flow :

* Accédez à [Microsoft Flow](https://flow.microsoft.com).
* Téléchargez l’application mobile Flic [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) et utilisez-la pour apparier un ou plusieurs boutons Flic.

## <a name="configure-flic-properties"></a>Configurer les propriétés de Flic
Utilisez l’application mobile Flic pour programmer les événements liés aux boutons Flic. Voici les événements concernés :

* clic (une seule pression rapide)
* double-clic (deux pressions rapides)
* appui prolongé (une seule pression longue)

Cette capture d’écran montre un exemple de processus de configuration de bouton Flic :

![configurer des boutons Flic](./media/flic-button-flows/configure-flic-actions.png)

Une fois que vous avez lié un événement Flic à Microsoft Flow, vous pouvez le sélectionner comme déclencheur pour votre flux. Vous sélectionnerez des déclencheurs plus loin dans cette procédure pas à pas.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Créer un flux déclenché par un bouton Flic
Dans cette procédure pas à pas, vous allez utiliser un bouton Flic pour exécuter un flux qui enregistre le temps qu’un consultant passe avec chaque client. Le consultant appuie sur le bouton Flic une fois qu’il est arrivé chez le client, puis appuie de nouveau dessus juste avant de partir. Chaque appui sur le bouton Flic démarre une exécution du flux auquel il est connecté. Le flux enregistre l’heure actuelle dans Google Sheets, puis envoie une notification par courrier. Le courrier contient des détails sur l’exécution du flux.

Remarque : veillez à utiliser l’application mobile Flic pour appairer et configurer au moins une action de **clic** pour déclencher Microsoft Flow. Dans cette capture d’écran, j’ai configuré l’action de **clic** pour déclencher Microsoft Flow. Plus loin dans cette procédure pas à pas, vous allez configurer le déclenchement du flux lorsque le bouton Flic est activé une fois.

   ![configuration du bouton flic](./media/flic-button-flows/flic-configured-for-flow.png)

Commencez à créer le flux.

### <a name="start-with-a-template"></a>Commencer avec un modèle
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
   
    ![se connecter](./media/flic-button-flows/sign-into-flow.png)
2. Entrez **flic** dans la zone de recherche, puis sélectionnez l’icône de recherche.
   
    ![recherche flic](./media/flic-button-flows/search-flic.png)
3. Sélectionnez le modèle **Track your working hours with Flic smart button (Suivre vos heures de travail avec le bouton intelligent Flic)**.
   
    ![sélectionner un modèle](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Créer une feuille de calcul dans Google Sheets
1. Passez en revue les détails du modèle. Notez que ce dernier nécessite une feuille de calcul Google Sheets.
   
   ![passer en revue les détails du modèle](./media/flic-button-flows/flic-template-details.png)
2. Dans Google Sheets, créez une feuille de calcul qui contient une table avec des colonnes nommées **ClickType** et **TimeStamp**.
   
      Conseil : nommez les colonnes dans Google Sheets en entrant leur nom en haut de la colonne. Votre feuille doit donc apparaître comme dans la capture d’écran suivante :
   
   ![Google Sheets](./media/flic-button-flows/flic-google-sheet.png)
   
   Remarque : vous utiliserez cette feuille plus loin dans cette procédure pas à pas.

### <a name="add-the-flic-trigger-to-your-flow"></a>Ajouter le déclencheur Flic à votre flux
1. Connectez-vous aux services du modèle, puis sélectionnez **Continuer**.
   
     Le bouton **Continuer** est activé une fois que vous êtes connecté à tous les services requis pour le modèle :
   
    ![indiquer les informations d’identification](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Entrez **flic** dans la zone de recherche, puis sélectionnez le déclencheur **Flic - When a Flic is pressed (Flic - Lors de l’appui sur un bouton Flic)**.
   
    ![rechercher un déclencheur flic](./media/flic-button-flows/flic-search-trigger.png)
3. Sélectionnez le bouton Flic que vous souhaitez utiliser à partir de la liste **Flic button (Bouton Flic)** sur la carte **Flic - When a Flic is pressed (Flic - Lors de l’appui sur un bouton Flic)** .
4. Sélectionnez **clic** dans la liste des **événements** pour indiquer que vous souhaitez déclencher le flux lorsque vous appuyez une fois sur le bouton Flic.
   
    ![sélectionner l’action du bouton flic](./media/flic-button-flows/select-flic.png)
   
   Vous pouvez également sélectionner **any (tous)** pour indiquer que chaque événement Flic (clic, double-clic ou appui prolongé) déclenche le flux.
   
   **Double-clic** indique que le flux se déclenche lorsque l’utilisateur appuie deux fois rapidement sur le bouton Flic. **Appui prolongé** indique qu’une pression longue sur le bouton Flic déclenche le flux.
   
   Vous pouvez créer d’autres flux et les déclencher à l’aide d’autres événements de la liste **Événements**. Par exemple, vous pouvez utiliser l’événement **Double-clic** pour enregistrer l’heure à laquelle vous quittez un client.

### <a name="configure-the-sheet"></a>Configurer la feuille
   Sur la carte **Insert row (Insérer une ligne)**  :

1. Sélectionnez la feuille de calcul créée précédemment dans la liste **Fichier**.
2. Sélectionnez la feuille dans la liste **Feuille de calcul**.
   
   Remarque : deux cases supplémentaires apparaissent dans la carte **Insert row (Insérer une ligne)** une fois que vous avez sélectionné la feuille. Ces cases représentent les deux colonnes de la feuille créée précédemment.
3. Sélectionnez la zone **ClickType**, puis sélectionnez le jeton **Click type (Type de clic)**.
4. Sélectionnez la zone **Timestamp**, puis sélectionnez le jeton **Click time (Heure du clic)**.
   
    ![configurer les données Google Sheets](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirmer que les paramètres de courrier sont corrects
1. Confirmez que la carte **M’envoyer une notification par e-mail** ressemble à cette capture d’écran.
   
    ![confirmer la notification par courrier](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Enregistrer le flux et le tester
1. Donnez un nom à votre flux, puis enregistrez-le.
   
    ![enregistrer votre flux](./media/flic-button-flows/save.png)

Si vous avez tout fait correctement, appuyer sur le bouton Flic une fois déclenche le flux. Le flux enregistre ensuite le type de clic et l’heure actuelle dans la feuille, puis vous envoie un courrier.

1. Appuyez sur votre bouton Flic une fois.
2. Ouvrez votre feuille de calcul dans Google Sheets. Vous devez voir les colonnes **ClickType** et **Timestamp** remplies avec le « clic » et l’heure, respectivement.
   
    ![voir les résultats de l’exécution](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Vous pouvez également voir les résultats de l’exécution à partir du site web Microsoft Flow ou de l’application mobile Microsoft Flow. Voici une capture d’écran de mon exécution de test.
   
    ![enregistrer votre flux](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Voici à quoi ressemble le corps du courrier de notification que vous avez reçu suite à l’exécution du flux.
   
    ![enregistrer votre flux](./media/flic-button-flows/flic-email-body.png)

Vous pouvez aussi envisager d’étendre le flux pour qu’il enregistre automatiquement votre emplacement (latitude et longitude) lors de l’appui sur le bouton Flic.

## <a name="more-information"></a>Plus d’informations
* [Partager des flux de bouton](share-buttons.md).
* Apprenez à utiliser les [jetons de déclencheur de bouton](introduction-to-button-trigger-tokens.md) pour envoyer les données actuelles lorsque vos flux de bouton sont exécutés.
* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

