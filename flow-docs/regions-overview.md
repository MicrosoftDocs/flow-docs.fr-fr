---
title: Vue d’ensemble des régions de Microsoft Flow | Microsoft Docs
description: Vue d’ensemble avec questions et réponses sur les régions de Microsoft Flow
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
ms.openlocfilehash: dce9fa4bb838f931acdcd95710d82d15bdc7dd24
ms.sourcegitcommit: 3bdd6c6b9df40f53e52c31130abaa93ba09a0e9b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60120715"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>FAQ sur les régions de Microsoft Flow
Ce document fournit une liste de questions fréquemment posées sur Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Comment savoir où mon flux est déployé ?
Votre flux est déployé dans la [région](https://azure.microsoft.com/regions/) qui héberge l’[environnement](environments-overview-admin.md). Par exemple, si votre environnement est créé dans la région Europe, votre flux est déployé dans les centres de données en Europe.

Les administrateurs peuvent identifier la région s’ils se connectent au [centre d’administration](https://admin.flow.microsoft.com) de Microsoft Flow. L’onglet **Environnements** répertorie tous les environnements existants et leurs régions.

![afficher les environnements](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quelles régions sont disponibles ?
* États-Unis
* Europe
* Asie
* Australie
* Inde
* Japon
* Canada
* Amérique du Sud
* Royaume-Uni
* Gouvernement des États-Unis (GCC)

## <a name="what-features-are-specific-to-a-given-region"></a>Quelles fonctionnalités sont spécifiques à une région donnée ?
Les environnements peuvent être créés dans différentes régions et sont liés à cet emplacement géographique. Lorsque vous créez un flux dans un environnement, ce flux est déployé dans les centres de données de cet emplacement géographique. Cela s’applique à tous les éléments que vous créez dans l’environnement, y compris les modèles de données courants, les flux, les connexions, les passerelles, les applications et les connecteurs personnalisés.

Pour des performances optimales, créez votre environnement dans la région la plus proche de vos utilisateurs. Par exemple, si vos utilisateurs sont en Europe, créez vos environnements dans la région Europe. Si vos utilisateurs sont aux États-Unis, créez vos environnements dans la région États-Unis.

## <a name="gateways"></a>Passerelles
Les passerelles sont les suivantes :

* Non disponibles dans la région Inde.
* Prises en charge dans l’environnement par défaut uniquement, pas dans des environnements personnalisés.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow est-il disponible dans les clouds nationaux ?
Non, Microsoft Flow n’est pas disponible dans les clouds nationaux. La prise en charge des clouds nationaux est prévue pour 2018.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quelles adresses IP sortantes sont utilisées dans chaque région ?
Voir [Limites et configuration](limits-and-config.md).

