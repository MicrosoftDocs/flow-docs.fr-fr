---
title: Résumé des demandes de l’objet de données RGPD pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment répondre aux demandes de l’objet de données RGPD pour Microsoft Flow.
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
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548182"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Répondre aux demandes de droits de l’objet des données RGPD (retours directs)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cet article décrit le Règlement général sur la protection des données de l’Union européenne (RGPD) et présente les étapes à suivre pour prendre en charge la conformité RGPD pour les utilisateurs Microsoft Flow qui s’authentifient avec les comptes Microsoft (MSA).

## <a name="prerequisites"></a>Conditions préalables

Vous avez besoin d’un MSA avec une [licence Microsoft Flow gratuite](https://flow.microsoft.com/pricing/) pour effectuer les étapes décrites dans cet article.

>[!TIP]
> Les informations de conformité RGPD sont également disponibles pour les utilisateurs qui s’authentifient avec des [comptes Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Répondre à retours directs pour Microsoft Flow données client

La demande formelle d’un objet de données à un contrôleur pour effectuer une action sur ses données personnelles est appelée demande de droits de l’objet des données (DSR). RGPD définit des données personnelles en tant que **données relatives à une personne physique identifiée ou identifiable**. Le RGPD offre aux personnes (appelées « sujets de données ») des droits pour gérer les données personnelles collectées par un employeur, une agence ou une organisation (également appelé contrôleur de données ou contrôleur). Ces droits sont les suivants :

* Obtenir des copies des données personnelles.
* Demande de corrections aux données personnelles.
* Restriction du traitement des données personnelles.
* Suppression des données personnelles.
* Réception de données personnelles dans un format électronique afin qu’elles puissent être déplacées vers un autre contrôleur.

Microsoft fournit des produits, des services et des outils pour aider les contrôleurs à rechercher et à agir sur les données personnelles lors de la réponse aux requêtes retours directs pour les données qui résident dans le Cloud.

Voici une vue d’ensemble des processus décrits dans ce guide :

1. **Découvrir**: utilisez les outils de recherche et de découverte pour rechercher facilement les données client susceptibles de faire l’objet d’une demande de DSR. Si vous déterminez que les documents que vous collectez remplissent les directives de votre contrôleur pour agir, vous pouvez effectuer une ou plusieurs des actions DSR décrites dans les étapes suivantes. Pour plus d’informations, consultez la [Microsoft Flow documentation sur la détection du DSR pour les comptes Microsoft](gdpr-dsr-discovery-msa.md). Vous pouvez également décider que la demande ne répond pas aux directives de votre contrôleur pour répondre aux demandes du DSR.

1. **Accès**: Récupérez les données personnelles qui résident dans le Cloud Microsoft et, si nécessaire, faites-en une copie afin que puisse être mis à la disposition de l’objet des données.

1. **Rectifier**: apporter des modifications ou implémenter d’autres actions demandées sur les données personnelles, le cas échéant.

1. **Restreindre**: restreindre le traitement des données personnelles, soit en supprimant des licences pour différentes services en ligne, soit en désactivant les services souhaités dans la mesure du possible. Vous pouvez également supprimer des données du Cloud Microsoft et les conserver localement ou à un autre emplacement.

1. **Supprimer**: supprimer définitivement les données personnelles qui résident dans le Cloud de Microsoft. En savoir plus sur [la suppression des données personnelles pour les comptes Microsoft](gdpr-dsr-delete-msa.md). En savoir plus sur [la fermeture d’un compte Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exporter**: fournir une copie électronique (dans un format lisible par machine) des données personnelles. [En savoir plus sur l’exportation de données personnelles pour les comptes Microsoft](gdpr-dsr-export-msa.md).
