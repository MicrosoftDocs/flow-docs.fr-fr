---
title: En savoir plus sur la modification des flux d’interface utilisateur Web | Microsoft Docs
description: Découvrez comment modifier des flux d’interface utilisateur Web.
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
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549573"
---
# <a name="edit-web-ui-flows"></a>Modifier les flux d’interface utilisateur Web

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Les flux d’interface utilisateur Web automatisent les sites Web qui s’exécutent dans la [prochaine version de Microsoft Edge](https://www.microsoftedgeinsider.com/) ou Google Chrome. Une fois que vous avez [créé un workflow d’interface utilisateur Web](create-web.md), vous devrez peut-être le modifier. Suivez les étapes décrites dans ce document pour apprendre à modifier vos flux d’interface utilisateur Web.

## <a name="edit-in-selenium-ide"></a>Modifier dans l’IDE de sélénium

Utilisez l’IDE de sélénium pour modifier vos flux d’interface utilisateur Web.

>[!NOTE]
>La modification dans l’IDE de sélénium est destinée aux utilisateurs expérimentés et aux développeurs.

Vous pouvez vous référer aux [commandes de sélénium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) pour apprendre à modifier le script.

L’IDE de sélénium suggère des sélecteurs différents et un sélecteur par défaut lors du ciblage d’un élément d’interface utilisateur. Vous pouvez également définir un nouveau sélecteur si aucun des sélecteurs proposés n’est approprié. Cela se produit généralement lorsque la structure HTML du site Web est hautement dynamique.

Voici un exemple de sélecteurs que l’IDE de sélénium a identifiés :

![Sélecteurs possibles](../media/edit-web/possible-selectors.png "Sélecteurs possibles")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Accès à une propriété d’une variable objet ou d’un élément d’une variable tableau * *

Cette fonctionnalité avancée vous permet d’utiliser une syntaxe comme \${foo. bar} pour accéder à la propriété de barre de l’objet foo. Vous pouvez également écrire dans la propriété bar de foo en utilisant foo. bar comme propriété Value dans une commande Store. Vous pouvez également utiliser la syntaxe comme \${foo [0]} pour accéder à l’élément à l’index 0 dans le tableau foo.

## <a name="next-steps"></a>Étapes suivantes

- [Créer des flux d’interface utilisateur Web](create-web.md)
- [Exécuter des flux d’interface utilisateur](run-ui-flow.md)
