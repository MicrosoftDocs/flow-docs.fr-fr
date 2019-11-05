---
title: Vue d’ensemble des régions pour Microsoft Flow | Microsoft Docs
description: Vue d’ensemble avec questions et réponses sur les régions dans Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548462"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>FAQ pour les régions dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Ce document fournit une liste des questions fréquemment posées sur Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Comment faire de savoir où est déployé mon Flow ?
Votre Flow est déployé dans la [région](https://azure.microsoft.com/regions/) qui héberge l' [environnement](environments-overview-admin.md). Par exemple, si votre environnement est créé dans la région Europe, votre fluide est déployé dans les centres de données européens.

Les administrateurs peuvent identifier la région s’ils se connectent au [Centre d’administration](https://admin.flow.microsoft.com)Microsoft Flow. L’onglet **environnements** répertorie tous les environnements existants et leurs régions.

![afficher les environnements](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quelles sont les régions disponibles ?
* États-Unis
* Europe
* Asiatiques
* Australie
* Inde
* Japon
* Canada
* Amérique du Sud
* Royaume-Uni
* Gouvernement des États-Unis (GCC)
* France

## <a name="what-features-are-specific-to-a-given-region"></a>Quelles sont les fonctionnalités spécifiques à une région donnée ?
Les environnements peuvent être créés dans différentes régions et sont liés à cet emplacement géographique. Lorsque vous créez un workflow dans un environnement, ce Flow est déployé dans les centres de données de cet emplacement géographique. Cela s’applique à tous les éléments que vous créez dans cet environnement, y compris le modèle de données commun, les flux, les connexions, les passerelles, les applications et les connecteurs personnalisés.

Pour des performances optimales, créez votre environnement dans la région la plus proche de vos utilisateurs. Par exemple, si vos utilisateurs sont en Europe, créez vos environnements dans la région Europe. Si vos utilisateurs se trouvent dans le États-Unis, créez vos environnements dans la région États-Unis.

## <a name="gateways"></a>Passerelles
Les passerelles sont les suivantes :

* Non disponible dans la région Inde.
* Pris en charge dans l’environnement par défaut uniquement, pas dans les environnements personnalisés.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow est-il disponible dans les clouds nationaux ?
Oui. [En savoir plus](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quelles adresses IP sortantes sont utilisées dans chaque région ?
Consultez [limites et configuration](limits-and-config.md).

