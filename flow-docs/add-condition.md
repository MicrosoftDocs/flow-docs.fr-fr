---
title: Ajouter une condition à un Flow | Microsoft Docs
description: Spécifiez qu’un workflow effectue une ou plusieurs tâches uniquement si une condition a la valeur true.
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
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544710"
---
# <a name="add-a-condition-to-a-flow"></a>Ajouter une condition à un Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Spécifiez qu’un workflow effectue une ou plusieurs tâches uniquement si une condition a la valeur true. Par exemple, spécifiez que vous recevrez un e-mail uniquement si un tweet contenant un mot clé est retweeté au moins 10 fois.

## <a name="prerequisites"></a>Conditions préalables

* [Créer un workflow](get-started-logic-template.md) à partir d’un modèle : ce didacticiel [utilise ce modèle](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) comme exemple

## <a name="add-a-condition"></a>Ajouter une condition

1. Dans [Microsoft Flow](https://flow.microsoft.com), sélectionnez **mes flux** dans la barre de navigation supérieure.

    Vous devrez peut-être vous connecter si vous n’êtes pas déjà connecté.

1. Dans la liste des flux, sélectionnez l’un des flux que vous avez créés.

    Ce didacticiel utilise un exemple avec un déclencheur Twitter et une action SharePoint.

1. Sélectionnez **modifier le Flow**.

1. Sous la dernière action, sélectionnez **nouvelle étape**.

1. Sélectionnez **Ajouter une condition**.

    ![Bouton condition](./media/add-condition/add-condition.png)

1. Sur la carte **condition** , sélectionnez une zone vide dans la zone de gauche.

    La liste de **contenu dynamique** s’ouvre.

1. Sélectionnez le paramètre **nombre de retweets** pour l’ajouter à la zone.

1. Dans la zone au milieu de la carte **condition** , sélectionnez **est supérieur ou égal à**.

1. Dans la zone de droite, entrez **10**.

    ![Zone nom de l’objet avec un paramètre dans celui-ci](./media/add-condition/specify-condition.png)

1. Sélectionnez l’en-tête de l’action que vous souhaitez utiliser dans la condition (par exemple, **créer un élément**) et faites-le glisser sous le texte qui indique **si oui**.

    Lorsque vous relâchez le curseur, l’action se déplace dans cette zone.

    ![Action glisser](./media/add-condition/drag-action.png)

1. Configurez l’action si nécessaire.

1. Enregistrez le Flow.

## <a name="edit-in-advanced-mode"></a>Modifier en mode avancé

Vous pouvez également sélectionner **modifier en mode avancé** pour écrire des conditions plus avancées. Vous pouvez utiliser n’importe quelle expression du *langage de définition de workflow* en mode avancé. En savoir plus sur toutes les [expressions](https://msdn.microsoft.com/library/azure/mt643789.aspx)disponibles.

## <a name="next-steps"></a>Étapes suivantes

Découvrez comment [utiliser des expressions](use-expressions-in-conditions.md) dans des conditions en mode avancé.
