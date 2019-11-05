---
title: Utiliser les entrées et les sorties dans les flux d’interface utilisateur Web | Microsoft Docs
description: Utilisez les entrées et les sorties dans les flux d’interface utilisateur Web.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549343"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Utiliser les entrées et les sorties dans les flux d’interface utilisateur Web

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Définir des entrées pour un workflow d’interface utilisateur Web

Les entrées d’un workflow d’interface utilisateur vous permettent de transmettre des informations à partir d’une source externe telle qu’une base de données ou d’un autre workflow d’interface utilisateur vers le logiciel hérité cible que vous allez automatiser.

Toute variable utilisée (lecture) avant l’initialisation (généralement effectuée via des commandes de **magasin** ) sera automatiquement traitée comme une variable d’entrée et sera affichée sur la carte d’action **exécuter un workflow d’interface utilisateur pour le Web** .

Vous pouvez utiliser des variables par le biais de l’interpolation de chaîne, par exemple, remplacer le champ cible de la commande Click par « ID =\${elementId} ». Ou modifiez le champ de valeur de la commande type en «\${inputText} ».

La commande **définir la taille** de la fenêtre et le **type** de commande dans les captures d’écran suivantes utilisent des variables non initialisées \${Width}, \${hauteur} et \${Search}. Ces variables deviennent des valeurs d’entrée.

![Définir la taille et le type de la fenêtre](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Définir la taille et le type de la fenêtre")

Vous pouvez utiliser des variables directement dans certaines commandes, par exemple, les champs cible/valeur de la commande forEach sont à la fois des variables, vous n’avez pas besoin de l’entourer de «\${}».

Consultez les informations de référence sur les [commandes de sélénium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) pour déterminer les commandes qui prennent directement le nom de la variable.

## <a name="define-outputs-for-a-web-ui-flow"></a>Définir des sorties pour un workflow d’interface utilisateur Web

Toute variable définie dans le script de sélénium devient automatiquement une valeur de sortie. Utilisez les commandes suivantes pour déclarer des variables :

[Magasin](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Attribut Store](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Stocker JSON](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Titre du magasin](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[valeur du magasin](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Handle de fenêtre du magasin](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Nombre de XPath de magasin](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Exécuter le script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(ajoutez la syntaxe’return’pour retourner l’objet que vous souhaitez stocker à la fin du script)

## <a name="next-steps"></a>Étapes suivantes

- Découvrez comment [créer des flux d’interface utilisateur Web](create-web.md).
- Découvrez comment [déclencher des flux d’interface utilisateur](run-ui-flow.md).

