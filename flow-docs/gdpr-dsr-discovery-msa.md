---
title: Microsoft Flow les demandes de découverte des objets de données RGPD pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de découverte des objets de données RGPD pour les comptes Microsoft.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548098"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Répondre aux demandes de découverte de l’objet des données RGPD 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La première étape pour répondre à une demande DSR consiste à rechercher les données personnelles qui sont le sujet de la demande.
Voici un résumé des ressources Microsoft Flow qui contiennent des données personnelles pour un utilisateur qui s’authentifie avec son compte Microsoft (MSA).

|Ressource|Objectif|
|-----|-----|
|historique des exécutions|Fournit l’historique de l’exécution de chaque Flow au cours des 28 derniers jours. Ces données incluent l’heure de début, l’heure de fin, l’État et toutes les informations d’entrée/sortie pour chaque exécution de Workflow. En savoir plus sur [l’historique des exécutions de fluides](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Flux d’activités| Fournit un récapitulatif des activités de chaque Flow, y compris l’état d’exécution, les échecs et les notifications.|
|Trouvent|Logique de flux de travail pour un [flux](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Connexions|Utilisé par les connecteurs et permet la connectivité aux API, systèmes, bases de données, et bien plus encore. En savoir plus sur les [connexions](add-manage-connections.md).|

