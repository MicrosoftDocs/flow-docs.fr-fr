---
title: Créer des connecteurs personnalisés et incorporer des flux | Microsoft Docs
description: Créer un connecteur personnalisé, le partager, incorporer un fluide et en faire plus.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548262"
---
# <a name="start-to-build-with-microsoft-flow"></a>Commencez à créer avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Voici quelques-unes des façons dont vous pouvez étendre votre application avec Microsoft Flow :

* Créer un connecteur personnalisé et s’y connecter.
* Partagez votre connecteur personnalisé avec tous les utilisateurs de Microsoft Flow.
* Incorporez l’expérience de Flow dans une application.
* Mettez en surbrillance tous les connecteurs personnalisés afin que les utilisateurs puissent interagir avec Microsoft Flow dans le meilleur des cas.

## <a name="prerequisites"></a>Conditions préalables

* Un compte [Microsoft Flow](https://flow.microsoft.com) .

## <a name="create-a-custom-connector"></a>Créer un connecteur personnalisé

Si vous avez un service Web auquel vous souhaitez vous connecter à partir de Microsoft Flow, vous devez d’abord créer un connecteur personnalisé. Lorsque vous inscrivez un connecteur personnalisé, vous enseignez Microsoft Flow sur les caractéristiques de votre service Web, y compris l’authentification requise, les déclencheurs et les actions qu’il prend en charge, ainsi que les paramètres et les sorties pour chacune de ces actions.

Suivez ce didacticiel pour apprendre à [inscrire et utiliser des connecteurs personnalisés](https://powerapps.microsoft.com/tutorials/register-custom-api/). Une fois que vous avez inscrit votre connecteur personnalisé, vous pouvez le partager au sein de votre organisation à des fins de test.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Partager un connecteur personnalisé avec tous les utilisateurs Microsoft Flow

Après avoir entièrement testé votre connecteur personnalisé, démarrez le [processus de révision](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) pour qu’il soit approuvé par Microsoft pour le partage avec tous les autres utilisateurs Microsoft Flow.

Voici ce dont vous aurez besoin pour le processus de révision :

* Un fichier OpenAPI qui représente votre API et les informations d’authentification.
* Icône pour votre connecteur.
* Description de votre connecteur.
* Environ 10 idées sur la façon dont votre connecteur peut tirer profit d’autres utilisateurs par le biais de modèles.

Une fois que vous avez envoyé ces informations, Microsoft commence à évaluer les fonctionnalités de votre API dans Microsoft Flow et Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Incorporer l’expérience de Flow dans votre site Web ou votre application

Vous pouvez [incorporer](developer/embed-flow-dev.md) des Microsoft Flow dans votre application pour permettre une intégration profonde et en contexte entre votre application et tous les autres services pris en charge par Microsoft Flow. Par exemple, vous pouvez :

* Parcourir tous les modèles liés à votre service et permettre aux utilisateurs de sélectionner un modèle.
* Gérer les flux que les utilisateurs ont associés à votre application.

## <a name="next-steps"></a>Étapes suivantes

Découvrez comment [incorporer](developer/embed-flow-dev.md) des Microsoft Flow dans votre application.
