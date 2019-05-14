---
title: Apprenez à automatiser des tâches répétitives avec les flux de bouton acceptant les entrées utilisateur | Microsoft Docs
description: Microsoft Flow permet d’automatiser facilement les tâches répétitives. Votre flux peut même accepter l’entrée d’un utilisateur lors de l’exécution d’une tâche répétitive.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5c1aed64ad5ac8fc1cced9290b376cb54f97e65a
ms.sourcegitcommit: c1b32d32eed29ab2e0b76a852c273eb4def0be7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/02/2019
ms.locfileid: "64992316"
---
# <a name="introducing-button-flows-with-user-input"></a>Présentation des flux de bouton avec entrée utilisateur
Créez un flux de bouton pour exécuter des tâches de routine en appuyant simplement sur un bouton. Personnalisez votre flux en autorisant l’utilisateur à fournir des détails spécifiques à utiliser lors de l’exécution du flux. Cette rubrique vous guide lors de la création d’un flux de bouton qui accepte une entrée de l’utilisateur, lors de l’exécution du flux de bouton, puis lors de la mise en surbrillance de la façon de fournir l’entrée d’utilisateur.

Vous pouvez créer un flux de bouton dans le site web Microsoft Flow ou l’application mobile pour Microsoft Flow. Pour cette rubrique, vous allez utiliser le site web.

### <a name="prerequisites"></a>Prérequis
* Un compte sur le site web Microsoft Flow.

## <a name="open-the-template"></a>Ouvrir le modèle
1. Connectez-vous au [site web Microsoft Flow](https://flow.microsoft.com), entrez **Visual Studio** dans la zone de recherche, puis cliquez ou appuyez sur l’icône de recherche pour rechercher tous les modèles liés à Visual Studio :
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Sélectionnez le modèle **Open a Priority 2 Bug in Visual Studio** (Ouvrir un bogue de priorité 2 dans Visual Studio) :
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Sélectionnez le bouton **Utiliser ce modèle** :
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Ce modèle utilise Visual Studio Team Services (VSTS) et les services de notification Push. Vous devez vous connecter à ces services si vous n’êtes connecté à aucun d’eux. Le bouton **Se connecter** s’affiche uniquement si vous avez besoin de vous connecter à un service.
4. Une fois que vous êtes connecté à tous les services requis, sélectionnez le bouton **Continuer** :
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (facultatif) Modifiez le nom du flux en tapant le nom de votre choix dans la zone en haut du portail :
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personnaliser l’entrée de l’utilisateur
1. Dans la fiche de déclencheur, sélectionnez **Edit** (Modifier) :
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Sélectionnez l’icône **+** pour développer la page afin que vous puissiez ajouter des champs avec entrée personnalisée :
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Entrez le **titre** et la **description** de chaque champ personnalisé que vous souhaitez rendre disponible lorsqu’un utilisateur exécute votre flux.  
   
    Dans cet exemple, vous allez créer deux champs d’entrée personnalisés (**Étapes de reproduction du bogue** et **Gravité du bogue**) afin que les personnes qui utilisent ce flux puissent entrer les étapes pour reproduire le bogue et évaluer le niveau de gravité de celui-ci :  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personnaliser le bogue
1. Appuyez sur la barre de titre de la carte **Créer un élément de travail** (Create a new work item) :
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Effectuez les sélections appropriées pour votre environnement VSTS, puis sélectionnez **Edit** (Modifier) :
   
    Par exemple, connectez-vous à myinstance.visualstudio.com en tapant **myinstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Sélectionnez **Show advanced options** (Afficher les options avancées) pour afficher les autres champs de cette carte :
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Placez le curseur avant le jeton **Bug title** (Titre du bogue), puis entrez « Gravité : » dans le champ de texte **Title** (Titre).
5. Avec le curseur dans le champ de texte Titre, sélectionnez le jeton **Gravité du bogue**, puis entrez « -- ».  
6. Dans le champ de texte **Description**, placez le curseur juste après le jeton **Bug description** (Description du bogue), puis appuyez sur Entrée pour commencer une nouvelle ligne.
7. Placez votre curseur sur la nouvelle ligne, puis sélectionnez le jeton **Bug Repro steps** (Étapes de reproduction du bogue) :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personnaliser la notification Push
1. Appuyez sur la barre de titre de la carte **Send a push notification (Envoyer une notification Push)** pour la développer.
2. Dans la liste des jetons de contenu dynamique, sélectionnez **Voir plus**, puis ajoutez le jeton **URL** dans le champ de texte **Lien**.
3. Dans le champ de texte **Link label** (Étiquette du lien), ajoutez le jeton **ID** :
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Appuyez sur **Créer un flux** dans le menu pour créer votre flux : ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Exécuter votre flux
Dans cette procédure pas à pas, vous allez utiliser l’application mobile Microsoft Flow pour exécuter le flux de bouton que vous venez de créer. Vous allez fournir toutes les entrées utilisateur nécessaires pour créer un bogue contenant un titre, une description, les étapes de reproduction et le niveau de gravité.  

1. Dans l’application mobile Microsoft Flow, appuyez sur l’onglet **Boutons**, puis appuyez sur le bouton **Create bug report with steps** (Créer un rapport de bogue avec des étapes).
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Entrez le titre du bogue signalé, puis appuyez sur **Suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Entrez la description du bogue signalé, puis appuyez sur **Suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Entrez les étapes de reproduction du bogue signalé, puis appuyez sur **Suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Entrez la gravité du bogue signalé, puis appuyez sur **Terminé** :  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Le flux s’exécute.
6. (facultatif) Appuyez sur l’onglet **Activité** pour afficher les résultats.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (facultatif) Affichez les résultats détaillés de l’exécution de flux en appuyant sur l’étape **Create a new work item** (Créer un élément de travail).
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Utiliser différents types d’entrée

Les flux de votre bouton peuvent également accepter des types de données enrichis. Voici la liste des types d’entrée de données que les flux de bouton acceptent : 

- Texte
- Listes déroulantes (comme des boutons radio)
- Adresse e-mail
- Fichier (par exemple, une photo sur votre téléphone)
- Case à cocher Oui ou Non
- Nombre
- Date (avec un sélecteur de calendrier)

Pour utiliser ces types d’entrée, ajoutez le déclencheur **Déclencher manuellement un flux** et ajoutez un de ces types à votre flux :

![Options d’entrée](media/button-flow-with-user-input-tokens/input-options.png)

Vous pouvez également désigner certaines entrées comme obligatoires et d’autres comme facultatives. Utilisez le menu d’action (... sur le côté droit) dans chaque champ d’entrée. Il existe une limite de cinq entrées par bouton.

![Sélectionner des jetons facultatifs](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Étapes suivantes
* [Partager des flux de bouton](share-buttons.md)
* [En savoir plus sur les flux de bouton](introduction-to-button-flows.md)  
* [En savoir plus sur les flux de bouton avec jetons de déclencheur](introduction-to-button-trigger-tokens.md)  

