---
title: "Ajouter une condition à un flux | Microsoft Docs"
description: "Spécifiez qu’un flux effectue une ou plusieurs tâches uniquement si une condition est remplie."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>Ajouter une condition à un flux
Spécifiez qu’un flux effectue une ou plusieurs tâches uniquement si une condition est remplie. Par exemple, spécifiez que vous recevez un message électronique uniquement si un tweet contenant un mot clé est retweeté au moins 10 fois.

**Conditions préalables**

* [Créez un flux](get-started-logic-template.md) à partir d’un modèle : ce didacticiel [utilisera ce modèle](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) comme exemple

## <a name="add-a-condition"></a>Ajouter une condition
1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure.
2. Dans la liste des flux, sélectionnez un flux que vous avez créé. Ce didacticiel utilise un exemple avec un déclencheur Twitter et une action SharePoint.
3. Sous la dernière action, cliquez sur le bouton **Nouvelle étape**.
4. Sélectionnez **Ajouter une condition**.
   
    ![Bouton Condition](./media/add-a-condition/add-condition.png)
5. Sélectionnez une zone vide dans **Nom de l’objet**, puis sélectionnez **Ajouter du contenu dynamique** pour ouvrir le menu de contenu dynamique.
6. Sélectionnez le paramètre **Retweet count** (Nombre de retweets) pour l’ajouter à la zone.
7. Dans la zone **Relation**, sélectionnez **est supérieur ou égal à**.
8. Dans la zone **Valeur**, tapez **10**.
   
    ![Zone Nom de l’objet incluant un paramètre](./media/add-a-condition/specify-condition.png)
9. Cliquez sur l’en-tête de l’action que vous souhaitez placer à l’intérieur de la condition (p. ex. **Créer un élément**) et faites-le glisser sous la zone intitulée **SI OUI**. Lorsque vous relâchez le curseur, l’action doit être déplacée dans cette zone.
   
    ![Action de glissement](./media/add-a-condition/drag-action.png)
10. Enregistrez le flux.

## <a name="edit-in-advanced-mode"></a>Modifier en mode Avancé
Vous pouvez également sélectionner le lien **Modifier en mode Avancé** pour écrire des conditions plus avancées. Vous pouvez utiliser n’importe quelle expression à partir du *langage de définition du workflow* ici. [En savoir plus](https://msdn.microsoft.com/library/azure/mt643789.aspx) sur les fonctions qui sont disponibles.

