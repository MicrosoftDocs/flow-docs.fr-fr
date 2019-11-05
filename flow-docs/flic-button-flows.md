---
title: Démarrer des flux avec des boutons flic | Microsoft Docs
description: Démarrez facilement des flux de bouton avec des boutons physiques à partir de flic par les laboratoires de raccourcis.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e6430f78ad2eccecc5af7f6606bb56e1a7eb4599
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544807"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Exécuter vos flux en appuyant sur un bouton intelligent flic (version préliminaire)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Déclenchez vos flux en appuyant sur un bouton physique, connu sous le nom de flic, à partir des ateliers de raccourcis. Par exemple, appuyez sur un flic pour suivre vos heures de travail, bloquer votre calendrier, compter les visiteurs à un événement ou enregistrer des emplacements géographiques.

> [!IMPORTANT]
> Configurez toutes les propriétés de flic à l’aide de l’application mobile flic pour [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) avant de créer votre fluide.
> 
> 

## <a name="prerequisites"></a>Conditions préalables
Pour utiliser boutons flic avec Microsoft Flow, vous devez disposer des éléments suivants :

* Accès aux [Microsoft Flow](https://flow.microsoft.com).
* L’application mobile [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) de flic a été téléchargée et utilisée pour coupler un ou plusieurs boutons flic.

## <a name="configure-flic-properties"></a>Configurer les propriétés flic
Utilisez l’application mobile de flic pour programmer les événements du flic. Les événements sont les suivants :

* cliquer (une pression rapide)
* double-clic (deux pressions rapides)
* Hold (une longue pression)

Cette capture d’écran montre un exemple de ce à quoi peut ressembler votre processus de configuration flic :

![configurer boutons flic](./media/flic-button-flows/configure-flic-actions.png)

Une fois que vous avez lié un événement flic à Microsoft Flow, vous pouvez sélectionner ce flic en tant que déclencheur pour vos flux. Vous sélectionnez les déclencheurs plus loin dans cette procédure pas à pas.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Créer un fluide qui est déclenché par un flic
Dans cette procédure pas à pas, nous utilisons un flic pour exécuter un Flow qui enregistre le temps que le consultant consacre à chaque client. Le consultant appuie sur le flic une fois à l’arrivée, puis le retouche juste avant le départ du client. Chaque pression sur le flic démarre une exécution du processus auquel il est connecté. Le Flow enregistre l’heure actuelle dans Google Sheets, puis envoie une notification par courrier électronique. L’e-mail contient des détails sur l’exécution du Workflow.

Remarque : Assurez-vous que vous avez utilisé l’application mobile flic pour effectuer le couplage et configurez au moins une action de **clic** pour déclencher Microsoft Flow. Dans cette capture d’écran, j’ai configuré l’action de **clic** pour déclencher Microsoft Flow. Plus loin dans cette procédure pas à pas, nous allons configurer notre Flow pour déclencher lorsque le flic est activé une fois (clic).

   ![configuration de flic](./media/flic-button-flows/flic-configured-for-flow.png)

Nous allons commencer à créer notre Flow.

### <a name="start-with-a-template"></a>Démarrer avec un modèle
1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com).
   
    ![Connexion](./media/flic-button-flows/sign-into-flow.png)
2. Entrez **flic** dans la zone de recherche, puis sélectionnez l’icône de recherche.
   
    ![Rechercher flic](./media/flic-button-flows/search-flic.png)
3. Sélectionnez le modèle **suivi de vos heures de travail avec le bouton intelligent flic** .
   
    ![sélectionner un modèle](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Créer une feuille de calcul dans Google Sheets
1. Passez en revue les détails du modèle et notez que ce modèle nécessite une feuille de calcul dans Google Sheets.
   
   ![examiner les détails du modèle](./media/flic-button-flows/flic-template-details.png)
2. Dans Google Sheets, créez une feuille de calcul qui contient une feuille avec des colonnes nommées **ClickType** et **timestamp**.
   
      Conseil : vous nommez des colonnes dans Google sheets en entrant le nom de colonne en haut de la colonne. Par conséquent, votre feuille doit apparaître comme dans la capture d’écran suivante :
   
   ![Feuille Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Remarque : vous utilisez cette feuille plus loin dans cette procédure pas à pas.

### <a name="add-the-flic-trigger-to-your-flow"></a>Ajouter le déclencheur flic à votre Flow
1. Connectez-vous aux services du modèle, puis sélectionnez **Continuer**.
   
     **Continuer** est activé une fois que vous êtes connecté à tous les services requis pour le modèle.
   
    ![fournir les informations d’identification](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Entrez **flic** dans la zone de recherche, puis sélectionnez le déclencheur **flic-When a flic enfoncé** .
   
    ![Rechercher le déclencheur flic](./media/flic-button-flows/flic-search-trigger.png)
3. Sélectionnez le flic que vous souhaitez utiliser à partir de la liste de **boutons flic** sur le **flic-quand un flic est enfoncé** .
4. Sélectionnez **Cliquer** dans la liste des **événements** pour indiquer que vous souhaitez déclencher le workflow lorsque le flic est activé une fois.
   
    ![sélectionner l’action flic](./media/flic-button-flows/select-flic.png)
   
   Si vous le souhaitez, vous pouvez sélectionner **n’importe** lequel pour indiquer que chaque événement flic (clic, double-clic ou conservation) déclenche le Flow.
   
   Le **double-clic** indique que le workflow se déclenche quand le flic est rapidement enfoncé deux fois. **Hold** indique qu’une pression longue sur le flic déclenche le Flow.
   
   Vous êtes libre de créer d’autres flux et de les déclencher à l’aide des autres événements de la liste des **événements** . Par exemple, vous pouvez utiliser l’événement de **double-clic** pour enregistrer l’heure à laquelle vous laissez un client.

### <a name="configure-the-sheet"></a>Configurer la feuille
   Sur la carte **Insérer une ligne** :

1. Sélectionnez la feuille de calcul que vous avez créée précédemment dans la liste des **fichiers** .
2. Sélectionnez la feuille dans la liste **feuille de calcul** .
   
   Remarque : deux cases supplémentaires apparaissent sur la carte **Insérer une ligne** après la sélection de la feuille. Ces zones représentent les deux colonnes de la feuille que vous avez créée précédemment.
3. Activez la case à cocher **ClickType** , puis sélectionnez le jeton **type de clic** .
4. Sélectionnez la zone **horodateur** , puis sélectionnez le jeton **heure de clic** .
   
    ![configurer des données Google Sheets](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirmer que les paramètres de messagerie sont corrects
1. Confirmez que la carte **m’envoyer une notification par e-mail** ressemble à cette capture d’écran.
   
    ![confirmer la notification par courrier électronique](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Enregistrer votre Flow et le tester
1. Donnez un nom à votre Flow, puis enregistrez-le.
   
    ![enregistrer votre Flow](./media/flic-button-flows/save.png)

Si vous avez suivi la procédure, le fait d’appuyer sur la flic une fois déclenche le processus. Le Flow enregistre ensuite le type de clic et l’heure actuelle dans la feuille, puis vous envoie un e-mail.

1. Appuyez une fois sur votre flic.
2. Ouvrez votre feuille de calcul dans Google Sheets. Vous devez voir les colonnes **ClickType** et **timestamp** renseignées avec les colonnes « Click » et Time, respectivement.
   
    ![afficher les résultats de l’exécution](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Vous pouvez également voir les résultats de l’exécution à partir du site Web Microsoft Flow ou à partir de l’application mobile Microsoft Flow. Voici une capture d’écran de la série de tests.
   
    ![enregistrer votre Flow](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Voici à quoi ressemble le corps de l’e-mail de notification que j’ai reçu de l’exécution du Workflow.
   
    ![enregistrer votre Flow](./media/flic-button-flows/flic-email-body.png)

Pour un crédit supplémentaire, envisagez d’étendre le Flow pour enregistrer automatiquement votre emplacement (Latitude et longitude) quand vous appuyez sur le flic.

## <a name="more-information"></a>Plus d’informations
* [Partager des flux de bouton](share-buttons.md).
* Apprenez à utiliser les [jetons de déclencheur de bouton](introduction-to-button-trigger-tokens.md) pour envoyer les données actuelles lorsque vos flux de bouton sont exécutés.
* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

