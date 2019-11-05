---
title: Présentation des jetons de déclencheur de bouton | Microsoft Docs
description: Présentation des jetons de déclencheur de bouton pour les flux de bouton Microsoft.
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
ms.openlocfilehash: 1b439a972393f800ea550480b883945664e17e53
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547456"
---
# <a name="get-started-with-button-trigger-tokens"></a>Prise en main des jetons de déclencheur de bouton
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>Que sont les jetons de déclencheur de bouton ?
Les jetons de déclencheur de bouton sont des points de données connus et disponibles pour l’appareil sur lequel un [Workflow de bouton](introduction-to-button-flows.md) est exécuté. Ces jetons changent en fonction de facteurs tels que l’heure actuelle ou l’emplacement géographique de l’appareil à un moment donné.  

Par exemple, si vous exécutez un Flow sur un smartphone, il est probable que le **téléphone connaisse l’heure** à votre emplacement actuel, ainsi que la date et l’adresse actuelle. Dans ce contexte, l’heure, la date et l’adresse où le téléphone est localisé sont toutes déterminées au moment de l’exécution du workflow de bouton. Elles sont automatiquement disponibles pour une utilisation dans les flux de bouton qui sont exécutés sur l’appareil. Vous pouvez utiliser ces jetons de déclencheur pour créer des flux utiles qui réduiront les tâches répétitives, telles que la fourniture de votre emplacement à une personne ou le suivi du temps passé sur un travail ou un appel de service particulier.

### <a name="list-of-button-trigger-tokens"></a>Liste des jetons de déclencheur de bouton
Voici la liste des jetons de déclencheur de bouton que vous pouvez utiliser lors de la création de vos flux de bouton.

| Paramètre | Descriptive |
| --- | --- |
| Urbain |Ville dans laquelle se trouve l’appareil qui exécute le fluide. |
| Pays/région |Pays/région dans lequel se trouve l’appareil qui exécute le fluide. |
| Adresse complète |Adresse complète à laquelle se trouve l’appareil qui exécute le Workflow. |
| Latitude |Latitude dans laquelle se trouve l’appareil qui exécute le fluide. |
| Longitude |Longitude dans laquelle se trouve l’appareil qui exécute le fluide. |
| Postal |Code postal dans lequel se trouve l’appareil qui exécute le fluide. |
| Département |État dans lequel se trouve l’appareil qui exécute le Workflow. |
| Postal |Rue sur laquelle se trouve l’appareil qui exécute le fluide. |
| Confirmé |L’heure dans la zone où se trouve le périphérique qui exécute le fluide. |
| Date |Date dans la zone où se trouve l’appareil qui exécute le fluide. |
| Nom d’utilisateur |Nom d’utilisateur de la personne connectée à l’appareil qui exécute le Flow. |
| E-mail de l’utilisateur |Adresse de messagerie de la personne connectée à l’appareil qui exécute le Workflow. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Créer un Flow qui utilise des jetons de déclencheur
Lorsque vous créez un bouton, vous pouvez utiliser des jetons de déclencheur pour ajouter des fonctionnalités riches à votre bouton.

Dans cette procédure pas à pas, nous allons créer un tableau de bord sur un appareil Android. Le déroulement du bouton utilise des jetons de déclencheur pour envoyer la date et votre adresse complète dans un message «**travail à partir de l’hôte**» à votre patron.

Dans cette procédure pas à pas, vous verrez des captures d’écran d’un appareil Android. Toutefois, l’expérience est similaire sur les appareils iOS et Windows Phone.

### <a name="prerequisites"></a>Conditions préalables
* Une adresse e-mail professionnelle ou scolaire ou un [compte Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) ayant accès à Microsoft Flow.
* L’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

Commençons :

1. Lancer le Flow et sélectionner **parcourir**   
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/1.png)  
2. Sélectionnez l' **E-mail envoyer un message « travail à la page d’aujourd’hui » à votre service de gestion** sous la catégorie de **bouton**   
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/2.png)  
3. Sélectionnez **utiliser ce modèle**  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/3.png)  
4. Sélectionnez **modifier** dans la carte **Envoyer un e-mail**  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Appuyez sur la zone de texte **objet** et entrez « **Today-** » dans la zone de texte après le texte « télétravail ». Notez que lorsque vous avez appuyé sur la zone de texte, une liste de paramètres/jetons est également ouverte. Nous allons utiliser l’un de ces jetons à l’étape suivante pour ajouter la date à l’objet de l’e-mail.  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/4.png)  
6. Avec le curseur toujours dans la zone de texte objet, faites défiler jusqu’à la liste **manuelle** des paramètres et appuyez sur **Date**. Notez que le paramètre date se trouve maintenant dans la zone de texte **objet** :  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/6.png)  
7. Faites défiler jusqu’à la zone de texte **corps** et appuyez sur après le message par défaut afin que des jetons supplémentaires puissent y être inclus.  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/7.png)  
8. Appuyez sur le paramètre **adresse complète** , puis sur **créer** .  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/8.png)  
9. Appuyez sur **terminé**. Votre workflow de bouton est maintenant créé.  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Exécuter le déroulement du bouton
**Remarque**: ce Flow permet d’envoyer votre emplacement actuel par courrier électronique.  

1. Appuyez sur la catégorie **boutons** au bas de l’écran. Vous verrez une liste des boutons que vous avez l’autorisation d’utiliser. Appuyez sur le bouton qui représente le workflow de bouton que vous venez de créer :  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/10.png)  
2. Appuyez sur **autoriser** pour indiquer qu’il est OK pour que le workflow accède aux informations relatives à l’emplacement de votre appareil :  
   jeton de déclencheur de bouton ![](./media/introduction-to-button-trigger-tokens/11.png)  
3. Au bout de quelques instants, vous remarquerez que le message électronique a été envoyé à votre patron :  
   ![jeton de déclencheur de bouton](./media/introduction-to-button-trigger-tokens/12.png)  

Félicitations, vous venez de créer un workflow qui utilise à la fois les jetons de déclencheur de date et d’adresse complète. 

## <a name="next-steps"></a>Étapes suivantes
* [Partager des flux de bouton](share-buttons.md)
* [En savoir plus sur les flux de bouton](introduction-to-button-flows.md)
