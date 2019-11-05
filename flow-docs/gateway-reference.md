---
title: Passerelle de données locale | Microsoft Docs
description: Cet article est une vue d’ensemble de la passerelle de données locale pour Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544634"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Qu’est-ce qu’une passerelle de données locale ?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La passerelle de données locale agit comme un pont pour assurer un transfert de données rapide et sécurisé entre les données locales (les données qui ne se trouvent pas dans le Cloud) et plusieurs services Cloud Microsoft. Ces services de Cloud Computing incluent Power BI, PowerApps, Microsoft Flow, Azure Analysis Services et Azure Logic Apps. En utilisant une passerelle, les organisations peuvent conserver des bases de données et d’autres sources de données sur leurs réseaux locaux, tout en utilisant en toute sécurité ces données locales dans les services Cloud.

## <a name="how-the-gateway-works"></a>Fonctionnement de la passerelle

![Vue d’ensemble de la passerelle](media/gateway-reference/on-premises-data-gateway.png)

Pour plus d’informations sur le fonctionnement de la passerelle, consultez [architecture de la passerelle de données locale](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Types de passerelles

Il existe deux types différents de passerelles, chacun pour un scénario différent :

- La **passerelle de données locale** permet à plusieurs utilisateurs de se connecter à plusieurs sources de données locales. Vous pouvez utiliser une passerelle de données locale avec tous les services pris en charge, avec une seule installation de passerelle. Cette passerelle est bien adaptée aux scénarios complexes avec plusieurs personnes accédant à plusieurs sources de données.

- La **passerelle de données locale (mode personnel)** permet à un utilisateur de se connecter aux sources et ne peut pas être partagé avec d’autres utilisateurs. Une passerelle de données locale (mode personnel) peut uniquement être utilisée avec Power BI. Cette passerelle est bien adaptée aux scénarios où vous êtes la seule personne qui crée des rapports, et que vous n’avez pas besoin de partager des sources de données avec d’autres personnes.

## <a name="use-a-gateway"></a>Utiliser une passerelle

Il existe quatre étapes principales pour l’utilisation d’une passerelle.

1. [Téléchargez et installez la passerelle](/data-integration/gateway/service-gateway-install) sur un ordinateur local.
2. [Configurez](/data-integration/gateway/service-gateway-app) la passerelle en fonction de votre pare-feu et d’autres exigences réseau.
3. [Ajoutez des administrateurs de passerelle](/data-integration/gateway/service-gateway-manage) qui peuvent également gérer et administrer d’autres exigences réseau.
4. [Résolvez les problèmes liés](/data-integration/gateway/service-gateway-tshoot) à la passerelle en cas d’erreur.

## <a name="next-steps"></a>Étapes suivantes

- [Installer la passerelle de données locale](/data-integration/gateway/service-gateway-install)
