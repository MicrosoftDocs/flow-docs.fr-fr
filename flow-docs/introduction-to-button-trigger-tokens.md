---
title: Introduction aux jetons de déclencheur de bouton | Microsoft Docs
description: Introduction aux jetons de déclencheur de bouton pour les flux de bouton Microsoft.
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
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4746fa74911126f3e23ed009dd109a2766dae12a
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690925"
---
# <a name="get-started-with-button-trigger-tokens"></a>Bien démarrer avec les jetons de déclencheur de bouton
## <a name="what-are-button-trigger-tokens"></a>Que sont les jetons de déclencheur de bouton ?
Les jetons de déclencheur de bouton sont des points de données connus et disponibles pour l’appareil sur lequel un [flux de bouton](introduction-to-button-flows.md) est en cours d’exécution. Ces jetons changent en fonction de facteurs tels que l’heure actuelle ou l’emplacement géographique de l’appareil à un moment donné.  

Par exemple, si vous exécutez un flux de bouton sur un smartphone, il est probable que le **téléphone connaît l’heure** à votre emplacement actuel, ainsi que la date et l’adresse actuelle. Dans ce contexte, l’heure, la date et l’adresse où se trouve le téléphone sont toutes déterminées au moment où le flux de bouton s’exécute. Ces informations sont automatiquement disponibles pour une utilisation dans les flux de bouton qui sont exécutés sur l’appareil. Vous pouvez utiliser ces jetons de déclencheur pour générer des flux utiles qui permettent de minimiser les tâches répétitives comme fournir votre emplacement à une personne ou suivre le temps passé sur un appel de service/travail particulier.

### <a name="list-of-button-trigger-tokens"></a>Liste des jetons de déclencheur de bouton
Voici la liste des jetons de déclencheur de bouton disponibles que vous pouvez utiliser lors de la création de vos flux de bouton.

| Paramètre | Description |
| --- | --- |
| Ville |Ville dans laquelle se trouve l’appareil qui exécute le flux. |
| Pays/région |Pays/région où se trouve l’appareil qui exécute le flux. |
| Adresse complète |Adresse complète à laquelle se trouve l’appareil qui exécute le flux. |
| Latitude |Latitude à laquelle se trouve l’appareil qui exécute le flux. |
| Longitude |Longitude à laquelle se trouve l’appareil qui exécute le flux. |
| Code postal |Code postal où se trouve l’appareil qui exécute le flux. |
| État |État où se trouve l’appareil qui exécute le flux. |
| Rue |Rue où se trouve l’appareil qui exécute le flux. |
| Horodatage |Heure de la zone où se trouve l’appareil qui exécute le flux. |
| Date |Date de la zone où se trouve l’appareil qui exécute le flux. |
| Nom d’utilisateur |Nom d’utilisateur de la personne connectée à l’appareil qui exécute le flux. |
| E-mail de l’utilisateur |Adresse e-mail de la personne connectée à l’appareil qui exécute le flux. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Créer un flux de bouton qui utilise les jetons de déclencheur
Lorsque vous créez un bouton, vous pouvez utiliser les jetons de déclencheur pour ajouter des fonctionnalités enrichies à votre bouton.

Dans cette procédure pas à pas, vous allez créer un flux de bouton sur un appareil Android. Le flux de bouton utilise les jetons de déclencheur pour envoyer la date et votre adresse complète dans un message électronique intitulé « **Travaille depuis la maison** » à votre patron.

Dans cette procédure pas à pas, les captures d’écran sont issues d’un appareil Android, mais l’expérience est semblable sur des appareils iOS et Windows Phone.

### <a name="prerequisites"></a>Prérequis
* Une adresse de messagerie scolaire ou professionnelle ou un [compte Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) ayant accès à Microsoft Flow.
* Application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).

Commençons :

1. Lancez Flow et sélectionnez **Parcourir**   
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/1.png)  
2. Sélectionnez le service **Envoyer un e-mail « Travaille à domicile aujourd’hui » à votre responsable** sous la catégorie **Bouton**.   
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/2.png)  
3. Sélectionnez **UTILISER CE MODÈLE**.  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/3.png)  
4. Sélectionnez **Modifier** sur la carte **Send an email** (Envoyer un e-mail)  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Cliquez sur la zone de texte **Objet** et entrez : « **aujourd’hui -**  » dans la zone de texte après le texte « WFH » (TDA). Notez que lorsque vous avez cliqué sur la zone de texte, une liste de paramètres/jetons s’est également ouverte. Vous allez utiliser un de ces jetons à l’étape suivante pour ajouter la date à l’objet du message électronique.  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/4.png)  
6. Avec le curseur dans la zone de texte Objet, défilez vers la liste **manuelle** de paramètres et appuyez sur **Date**. Notez que le paramètre de date est à présent dans la zone de texte **Objet** :  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/6.png)  
7. Défilez vers la zone de texte **Corps** et appuyez après le message par défaut afin que des jetons supplémentaires puissent être inclus ici.  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/7.png)  
8. Appuyez sur le paramètre **Adresse complète**, puis sur **Créer**.  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/8.png)  
9. Appuyez sur **Terminé**. Votre flux de bouton est à présent créé.  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Exécuter le flux de bouton
**REMARQUE** : ce flux de bouton envoie votre emplacement actuel par courrier électronique.  

1. Appuyez sur la catégorie **Boutons** en bas de l’écran. La liste des boutons que vous êtes autorisé à utiliser s’affiche. Appuyez sur le bouton qui représente le flux de bouton que vous venez de créer :  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/10.png)  
2. Appuyez sur **AUTORISER** pour indiquer que le flux de bouton peut accéder aux informations sur l’emplacement de votre appareil :  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/11.png)  
3. Dans quelques instants, vous allez voir que le message électronique a été envoyé à votre patron :  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/12.png)  

Félicitations ! Vous venez de créer un flux de bouton qui utilise les jetons de déclencheur de date et d’adresse complète. 

## <a name="next-steps"></a>Étapes suivantes
* [Partager des flux de bouton](share-buttons.md)
* [En savoir plus sur les flux de bouton](introduction-to-button-flows.md)  
* [En savoir plus sur les flux](guided-learning/get-started.yml?tutorial-step=1)

