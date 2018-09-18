---
title: Ajouter une condition à un flux | Microsoft Docs
description: Spécifiez qu’un flux effectue une ou plusieurs tâches uniquement si une condition est remplie.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b4407238f9d1782db802b47060b156b8b77c328b
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689039"
---
# <a name="add-a-condition-to-a-flow"></a>Ajouter une condition à un flux

Spécifiez qu’un flux effectue une ou plusieurs tâches uniquement si une condition est remplie. Par exemple, spécifiez que vous recevez un message électronique uniquement si un tweet contenant un mot clé est retweeté au moins 10 fois.

## <a name="prerequisites"></a>Prérequis

* [Créez un flux](get-started-logic-template.md) à partir d’un modèle : ce tutoriel [utilise ce modèle](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) comme exemple

## <a name="add-a-condition"></a>Ajouter une condition

1. Dans [Microsoft Flow](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure.

    Vous devrez peut-être vous connecter si vous ne l’avez pas déjà fait.

1. Dans la liste des flux, sélectionnez un des flux que vous avez créés.

    Ce didacticiel utilise un exemple avec un déclencheur Twitter et une action SharePoint.

1. Sélectionnez **Modifier le flux**.

1. Sous la dernière action, sélectionnez **Nouvelle étape**.

1. Sélectionnez **Ajouter une condition**.

    ![Bouton Condition](./media/add-condition/add-condition.png)

1. Sur la carte **Condition**, sélectionnez une zone vide dans la zone située à gauche.

    La liste **Contenu dynamique** s’ouvre.

1. Sélectionnez le paramètre **Retweet count** (Nombre de retweets) pour l’ajouter à la zone.

1. Dans la zone centrale de la carte **Condition**, sélectionnez **est supérieur ou égal à**.

1. Dans la zone de droite, entrez **10**.

    ![Zone Nom de l’objet incluant un paramètre](./media/add-condition/specify-condition.png)

1. Sélectionnez l’en-tête de l’action que vous souhaitez placer à l’intérieur de la condition (p. ex. **Créer un élément**) et faites-le glisser sous la zone intitulée **Si oui**.

    Lorsque vous relâchez le curseur, l’action se déplace dans cette zone.

    ![Action de glissement](./media/add-condition/drag-action.png)

1. Configurez l’action telle que requis.

1. Enregistrez le flux.

## <a name="edit-in-advanced-mode"></a>Modifier en mode Avancé

Vous pouvez également sélectionner **Modifier en mode Avancé** pour écrire des conditions plus avancées. Vous pouvez utiliser n’importe quelle expression à partir du *langage de définition du workflow* en mode avancé. En savoir plus sur toutes les [expressions](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponibles.

## <a name="next-steps"></a>Étapes suivantes

Découvrez comment [utiliser des expressions](use-expressions-in-conditions.md) dans des conditions en mode Avancé.
