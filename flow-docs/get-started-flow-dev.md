---
title: "Commencer à créer | Microsoft Docs"
description: "Créez un connecteur personnalisé, partagez-le, incorporez un flux et bien plus encore."
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Commencer à créer avec Microsoft Flow
Développez votre application avec Microsoft Flow des façons suivantes (entre autres) :

* créer un connecteur personnalisé et s’y connecter ;
* partager cette API avec tous les utilisateurs de Microsoft Flow ;
* incorporer l’expérience de flux à partir d’une application ;
* tirer parti de toutes les API de développeur afin que les utilisateurs peuvent interagir avec Microsoft Flow de façon optimale.

## <a name="prerequisites"></a>Conditions préalables
* Un compte sur [flow.microsoft.com](https://flow.microsoft.com)

## <a name="create-a-custom-connector"></a>Créer un connecteur personnalisé
Lorsque vous disposez d’un service web que vous souhaitez automatiser avec Microsoft Flow, vous devez tout d’abord créer un connecteur personnalisé. En inscrivant un connecteur personnalisé, vous fournissez à Microsoft Flow les caractéristiques de votre API web, y compris l’authentification requise, les déclencheurs et actions pris en charge, ainsi que les paramètres et les sorties pour chacune de ces actions.

Suivez [ce tutoriel](https://powerapps.microsoft.com/tutorials/register-custom-api/) pour inscrire un connecteur personnalisé. Une fois que vous l’avez inscrite, vous pouvez la partager au sein de votre organisation afin que d’autres utilisateurs puissent vous aider à la tester.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Partager un connecteur personnalisé avec tous les utilisateurs de Microsoft Flow
Une fois que vous avez complètement testé votre connecteur personnalisé, démarrez le processus de révision, comme indiqué dans ce [billet de blog](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) :

* un fichier OpenAPI qui représente votre API et les informations d’authentification ;
* une icône pour votre connecteur ;
* une description de votre API ;
* environ 10 idées sur la façon dont votre API peut constituer un avantage pour d’autres utilisateurs grâce à des modèles.

Une fois que vous avez envoyé ces informations, Microsoft commence à évaluer la fonction de votre API dans Microsoft Flow et Microsoft PowerApps.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>Incorporer l’expérience de flux dans votre application ou site web
Enfin, vous pouvez incorporer Microsoft Flow à partir de votre application pour permettre une intégration en contexte approfondie entre votre application et tous les autres services pris en charge par Microsoft Flow. Par exemple, vous pouvez :

* parcourir tous les modèles liés à votre service et permettent aux utilisateurs de sélectionner un modèle ;
* gérer les flux que les utilisateurs ont associés à votre application.

Suivez [ce didacticiel](embed-flow-dev.md) pour plus d’informations sur la façon d’intégrer Microsoft Flow au sein d’une application.

