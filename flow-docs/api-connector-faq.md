---
title: FAQ Connecteur API | Microsoft Docs
description: "Trouvez des réponses aux questions sur la configuration requise, les déclencheurs et d’autres thèmes."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-faq-microsoft-flow"></a>FAQ Connecteur API (Microsoft Flow)
## <a name="requirements"></a>Configuration requise
**Q :** Puis-je créer un connecteur sans API REST ? </br>
**R :** Non. Pour créer un connecteur, vous devez prendre en charge les API REST HTTP stables pour votre service. 

**Q :** Quels outils puis-je utiliser pour créer un connecteur ? </br>
**R :** Azure propose des fonctionnalités et des services qui permettent d’exposer en tant qu’API n’importe quel service, par exemple, Azure App Service pour l’hébergement, Gestion des API, et bien plus encore.

**Q :** Quels types d’authentifications sont pris en charge ? </br>
**R :** Vous pouvez utiliser les normes d’authentification prises en charge suivantes :

* [OAuth 2.0](https://oauth.net/2/), y compris [Azure Active Directory](https://azure.microsoft.com/develop/identity/) ou des services spécifiques tels que Dropbox, GitHub et Salesforce
* OAuth 2.0 générique
* [Authentification De base](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [Clé API](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Déclencheurs
**Q :** Puis-je créer des déclencheurs sans webhooks ? </br>
**R :** Non. Les connecteurs personnalisés d’Azure Logic Apps et de Microsoft Flow prennent en charge uniquement les déclencheurs basés sur Webhook. Si vous souhaitez demander d’autres modèles d’implémentation, contactez [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) avec plus de détails sur votre API.

## <a name="certification"></a>Certification
**Q**: Je ne suis ni un partenaire Microsoft ni un éditeur de logiciels indépendant. Puis-je créer des connecteurs ? </br>
**R** : Oui. Vous pouvez inscrire ces connecteurs pour un usage en interne dans votre organisation mais, si vous souhaitez certifier et publier un connecteur, vous devez soit être propriétaire du service sous-jacent, soit présenter des droits explicites d’utilisation de l’API.

## <a name="other"></a>Autres
**Q :** Mes API utilisent un hôte dynamique. Comment les implémenter avec OpenAPI ? </br>
**R :** Les connecteurs personnalisés ne prennent pas en charge les hôtes dynamiques. Utilisez plutôt un hôte statique pour le développement et les tests. Si vous voulez certifier votre connecteur, interrogez votre contact Microsoft sur l’implémentation dynamique.

**Q :** Prenez-vous en charge Postman Collection V2 ? </br>
**R :** Non. Seul Postman Collection V1 est actuellement pris en charge.

**Q :** Prenez-vous en charge OpenAPI 3.0 ? </br>
**R :** Non. Seul OpenAPI 2.0 est actuellement pris en charge.

