---
title: Découvrez comment automatiser des tâches répétitives avec des flux de bouton qui acceptent les entrées utilisateur | Microsoft Docs
description: Microsoft Flow permet d’automatiser facilement les tâches répétitives. Vos flux peuvent même prendre des entrées utilisateur lors de l’exécution d’une tâche répétitive.
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
ms.openlocfilehash: a1bc5161bdd0e6a098d57cefafba99d3c89e6c97
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546459"
---
# <a name="introducing-button-flows-with-user-input"></a>Présentation des flux de bouton avec entrée d’utilisateur
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Créez un déroulement de bouton pour exécuter des tâches de routine en appuyant simplement sur un bouton. Personnalisez votre Flow en permettant à l’utilisateur de fournir des détails spécifiques qui seront utilisés lors de l’exécution du Workflow. Cette rubrique vous guide dans la création d’un workflow de bouton qui prend en entrée l’utilisateur, puis exécute le déroulement du bouton, en mettant en évidence la façon de fournir les entrées utilisateur.

Vous pouvez créer un workflow de bouton dans le site Web Microsoft Flow ou l’application mobile pour Microsoft Flow. Pour cette rubrique, vous allez utiliser le site Web.

### <a name="prerequisites"></a>Conditions préalables
* Un compte sur le site Web Microsoft Flow.

## <a name="open-the-template"></a>Ouvrir le modèle
1. Connectez-vous au [site web Microsoft Flow](https://flow.microsoft.com), entrez **Visual Studio** dans la zone de recherche, puis cliquez ou appuyez sur l’icône de recherche pour rechercher tous les modèles liés à Visual Studio :
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Sélectionnez le **bogue ouvrir un bogue de priorité 2 dans le modèle Visual Studio** :
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Cliquez sur **le bouton utiliser ce modèle** :
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Ce modèle utilise le Visual Studio Team Services (VSTS) et les services de notifications push. Vous devez vous connecter à ces services si vous n’avez pas de connexion à l’un d’eux. Le bouton **se connecter** s’affiche uniquement si vous devez vous connecter à un service.
4. Une fois que vous êtes connecté à tous les services requis, cliquez sur le bouton **continue** :
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. facultatif Modifiez le nom du Flow en tapant le nom de votre choix dans la zone située en haut du portail :
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personnaliser les entrées utilisateur
1. Dans la carte de déclencheur, sélectionnez **modifier**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Sélectionnez l’icône **+** pour développer la page afin de pouvoir ajouter des champs d’entrée personnalisés :
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Entrez le **titre d’entrée** et la **Description d’entrée** pour chaque champ personnalisé que vous souhaitez rendre disponible lorsqu’un utilisateur exécute votre workflow.  
   
    Dans cet exemple, vous allez créer deux champs d’entrée personnalisés (**étapes de reproduction des bogues** et **gravité des bogues**) afin que toute personne qui utilise ce Flow puisse entrer les étapes permettant de reproduire le bogue et de noter la gravité du bogue :  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personnaliser le bogue
1. Appuyez sur la barre de titre **créer une nouvelle** carte d’élément de travail :
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Effectuez les sélections appropriées pour votre environnement VSTS, puis sélectionnez **modifier**:
   
    Par exemple, connectez-vous à myinstance.visualstudio.com en tapant **MyInstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Sélectionnez **afficher les options avancées** pour afficher les autres champs de cette carte :
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Placez le curseur avant le jeton de **titre du bogue** , puis entrez « gravité : » dans le champ texte du **titre** .
5. Avec le curseur toujours dans le champ texte du titre, sélectionnez le jeton de **gravité du bogue** , puis entrez « -- ».  
6. Dans le champ de texte **Description** , placez votre curseur juste après le jeton de **Description du bogue** , puis appuyez sur entrée pour démarrer une nouvelle ligne.
7. Placez le curseur sur la nouvelle ligne, puis sélectionnez le jeton **étapes de reproduction du bogue** :
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personnaliser la notification push
1. Appuyez sur la barre de titre de la carte **Envoyer une notification push** pour la développer.
2. Dans la liste des jetons de contenu dynamique, sélectionnez **afficher plus**, puis ajoutez le jeton d' **URL** dans le champ de texte **lien** .
3. Dans le champ texte de l' **étiquette de lien** , ajoutez le jeton d' **ID** :
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Appuyez sur **créer un Flow** dans le menu pour créer votre flow : ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Exécuter votre Flow
Dans cette procédure pas à pas, vous allez utiliser l’application mobile pour Microsoft Flow pour exécuter le workflow de bouton que vous venez de créer. Vous allez fournir toutes les entrées utilisateur nécessaires pour créer un bogue avec un titre, une description, des étapes de reproduction et un niveau de gravité.  

1. Dans l’application mobile pour Microsoft Flow, appuyez sur l’onglet **boutons** , puis sur le bouton **créer un rapport de bogues avec des étapes** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Entrez le titre du bogue que vous signalez, puis appuyez sur **suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Entrez la description du bogue que vous signalez, puis appuyez sur **suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Entrez les étapes pour reproduire le bogue que vous signalez, puis appuyez sur **suivant**. Par exemple :
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Entrez la gravité du bogue que vous signalez, puis appuyez sur **terminé**:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Le workflow s’exécute.
6. facultatif Appuyez sur l’onglet **activité** pour afficher les résultats.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. facultatif Affichez les résultats détaillés de l’exécution du workflow en appuyant sur l’étape **créer un nouvel élément de travail** .
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Utiliser des types d’entrée différents

Vos flux de bouton peuvent également accepter des types de données enrichis. Voici la liste des types d’entrée de données que les flux de bouton acceptent : 

- Financière
- Listes déroulantes (telles que les cases d’option)
- Adresse de messagerie
- Fichier (par exemple, une photo sur votre téléphone)
- Case à cocher Oui ou non
- Certain
- Date (avec un sélecteur de calendrier)

Pour utiliser ces types d’entrée, ajoutez **manuellement** le déclencheur de Flow, puis ajoutez l’un de ces types à votre Flow :

![Options d’entrée](media/button-flow-with-user-input-tokens/input-options.png)

En outre, vous souhaiterez peut-être désigner certaines entrées comme obligatoires et d’autres comme facultatives. Utilisez le menu Action (... sur le côté droit) sur chaque champ d’entrée. Il y a une limite de cinq entrées par bouton.

![Sélectionner des jetons facultatifs](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Étapes suivantes
* [Partager des flux de bouton](share-buttons.md)
* [En savoir plus sur les flux de bouton](introduction-to-button-flows.md)  
* [En savoir plus sur les flux de bouton avec jetons de déclencheur](introduction-to-button-trigger-tokens.md)  

