---
title: Détection des demandes de l’objet des données Microsoft Flow RGPD | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de découverte des objets de données RGPD.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548122"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Réponse aux demandes de découverte des objets de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La première étape de la réponse à un DSR consiste à rechercher des données personnelles faisant l’objet de la demande. Cette première étape vous aide à déterminer si un DSR répond aux exigences de votre organisation en matière de respect ou de refus d’une demande DSR. Par exemple, après avoir trouvé et examiné les données personnelles en question, vous pouvez déterminer que la demande ne répond pas aux exigences de votre organisation, car cela peut nuire aux droits et libertés des autres.

Vous trouverez ci-dessous un résumé des types de ressources de Microsoft Flow qui contiennent des données personnelles pour un utilisateur spécifique.

|**Ressources contenant des données personnelles**|**Objectif**|
|-----|-----|
|Journaux générés par le système|Télémétrie qui capture les événements système et l’historique.|
|historique des exécutions|Historique de chaque exécution de workflow au cours des 28 derniers jours. Ces données incluent l’heure de début, l’heure de fin, l’État et toutes les informations d’entrée/sortie du Workflow. [Pour en savoir plus](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Flux d’activités| Fournit un récapitulatif des activités de Flow, y compris l’état d’exécution, les échecs et les notifications.|
|Travaux utilisateur|Non visible pour l’utilisateur, travaux système qui s’exécutent pour le compte d’un utilisateur afin que les flux soient exécutés.|
|Trouvent|Logique de workflow qui existe pour un flux. [Pour en savoir plus](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Autorisations de Flow|Les flux peuvent être partagés et réaffectés à d’autres utilisateurs. Les listes d’autorisations existent pour tous les flux. [Pour en savoir plus](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Détails de l’utilisateur|Détails, qui ne sont pas visibles par l’utilisateur, qui prennent en charge l’exécution du Workflow.|
|Connexions|Utilisé par les connecteurs et permet la connectivité aux API, systèmes, bases de données, etc. [Pour en savoir plus](https://docs.microsoft.com/flow/add-manage-connections)|
|Autorisations de connexion|Autorisations pour une connexion spécifique. [Pour en savoir plus](https://docs.microsoft.com/flow/add-manage-connections)|
|Connecteurs personnalisés|Connecteurs personnalisés qu’un utilisateur a créés et publiés pour permettre la connectivité à des systèmes tiers ou personnalisés. [Pour en savoir plus](https://docs.microsoft.com/connectors/custom-connectors/)|
|Autorisations de connecteur personnalisées|Listes d’autorisations pour les connecteurs personnalisés. [Pour en savoir plus](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Les passerelles sont des services de données locaux qui peuvent être installés par un utilisateur pour transférer des données rapidement et en toute sécurité entre Microsoft Flow et une source de données qui ne se trouve pas dans le Cloud. [Pour en savoir plus](https://docs.microsoft.com/flow/gateway-manage)|
|Autorisations de la passerelle|Les passerelles peuvent être partagées avec les utilisateurs au sein d’une organisation. [Pour en savoir plus](https://go.microsoft.com/fwlink/?linkid=872249)|
