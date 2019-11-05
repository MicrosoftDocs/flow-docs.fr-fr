---
title: Résumé des demandes de l’objet des données RGPD | Microsoft Docs
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548222"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Réponse aux demandes de l’objet de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cet article prépare votre organisation et vous-même à la Règlement général sur la protection des données de l’Union européenne (RGPD). Cet article décrit non seulement ce que Microsoft fait pour préparer le RGPD, mais également des exemples d’étapes que vous pouvez effectuer aujourd’hui pour prendre en charge la conformité RGPD lors de l’utilisation de PowerApps, Microsoft Flow et Common Data Service.

## <a name="prerequisites"></a>Conditions préalables

Les utilisateurs et les administrateurs peuvent effectuer les actions décrites dans cet article.

### <a name="users"></a>Utilisateurs

Un utilisateur doit disposer d’un compte Azure Active Directory actif avec une [licence Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Les utilisateurs qui ne répondent pas à cette exigence doivent demander à un administrateur d’effectuer ces actions.

### <a name="administrators"></a>Groupes

Vous pouvez effectuer les opérations qui requièrent des privilèges d’administrateur, présentées dans cet article si vous vous connectez au [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com/) ou à l' [administrateur powerapps PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) avec un compte disposant des deux autorisations suivantes :

- Une licence payante ou d’essai pour PowerApps plan 2.

    [Une licence d’évaluation](http://web.powerapps.com/trial) expire dans 30 jours.

- Administrateur [général Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) ou [administrateur général de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Locataires non gérés
Si vous êtes membre d’un [locataire non géré](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), ce qui signifie que votre locataire Azure ad ne dispose pas d’un administrateur général, vous pourrez toujours suivre les étapes décrites dans cet article pour exporter et supprimer vos propres données personnelles. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Réponse à retours directs pour Microsoft Flow données client

Le RGPD donne des droits aux personnes (connues dans le RGPD en tant que sujets de données) pour gérer les données personnelles qui ont été collectées par un employeur ou tout autre type d’agence ou d’organisation (connu sous le nom de contrôleur de données ou juste de contrôleur). Les données personnelles sont définies très largement sous le RGPD en tant que données relatives à une personne physique identifiée ou identifiable. Le RGPD donne aux objets de données des droits spécifiques sur leurs données personnelles ; ces droits incluent l’obtention de copies de données personnelles, la demande de corrections, la restriction du traitement de l’informatique, sa suppression ou sa réception dans un format électronique afin de pouvoir être déplacée vers un autre contrôleur. Une demande formelle d’une donnée soumise à un contrôleur pour effectuer une action sur ses données personnelles est appelée demande de droits de l’objet des données (DSR).

Cet article explique comment utiliser les produits, services et outils d’administration de Microsoft pour aider les contrôleurs à rechercher et agir sur les données personnelles lors de la réponse à retours directs. Plus précisément, cet article explique comment rechercher, accéder et agir sur les données personnelles qui résident dans le Cloud de Microsoft. Voici une vue d’ensemble rapide des processus décrits dans ce guide :

1. Découvrir : utilisez les outils de recherche et de découverte pour trouver plus facilement les données client susceptibles de faire l’objet d’un DSR. Une fois les documents potentiellement réactifs collectés, vous pouvez effectuer une ou plusieurs des actions DSR décrites dans les étapes suivantes pour répondre à la demande. Vous pouvez également décider que la demande ne répond pas aux directives de votre organisation en matière de réponse à retours directs. [Microsoft Flow de la documentation sur la détection du DSR](gdpr-dsr-discovery.md)

1. Accès : Récupérez les données personnelles qui résident dans le Cloud Microsoft et, si nécessaire, faites-en une copie qui peut être disponible pour l’objet des données.

1. Rectifier : apporter des modifications ou implémenter d’autres actions demandées sur les données personnelles, le cas échéant.

    Si un sujet de données vous demande de rectifier les données personnelles qui se trouvent dans votre organisation, vous et votre organisation devez déterminer s’il convient d’honorer la demande.  La correction des données peut inclure des actions telles que la modification, la rédaction ou la suppression des données personnelles.

    Vous pouvez utiliser Azure Active Directory pour gérer les identités des utilisateurs de Microsoft Flow. Les clients d’entreprise peuvent gérer les demandes de rectification du DSR, y compris les fonctionnalités d’édition limitées, en fonction de la nature d’un service Microsoft donné.  En tant que processeur de données, Microsoft n’offre pas la possibilité de corriger les journaux générés par le système, car ces journaux reflètent les activités factuelles et constituent un enregistrement historique des événements dans les services Microsoft.  [En savoir plus sur DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Restreindre : restreindre le traitement des données personnelles, soit en supprimant des licences pour différentes services en ligne, soit en désactivant les services souhaités dans la mesure du possible. Vous pouvez également supprimer des données du Cloud Microsoft et les conserver localement ou à un autre emplacement.

    Les sujets de données peuvent demander que vous restreigniez le traitement de leurs données personnelles.  Microsoft fournit des interfaces de programmation d’applications (API) et des interfaces utilisateur (UI) à cet effet.  Ces interfaces permettent à l’administrateur client de l’entreprise de gérer ces retours directs à l’aide d’une combinaison d’exportation de données et de suppression de données. Un client peut (1) exporter une copie électronique des données personnelles de l’utilisateur, y compris les comptes, les journaux générés par le système et les journaux associés, suivi (2) la suppression du compte et des données associées résidant dans les systèmes Microsoft.

1. Supprimer : supprimer définitivement les données personnelles qui résident dans le Cloud de Microsoft. [En savoir plus sur la suppression des données personnelles](gdpr-dsr-delete.md).

1. Exportation : fournissez une copie électronique (dans un format lisible par machine) de données personnelles à la personne donnée. Chaque section de cet article décrit les procédures techniques qu’une organisation de contrôleur de données peut prendre pour répondre à un DSR pour des données personnelles dans le Cloud de Microsoft. [En savoir plus sur l’exportation de données personnelles](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Journaux générés par le système

Reportez-vous à ce [Guide](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) pour plus d’informations sur les journaux générés par le système pour Microsoft Flow.
