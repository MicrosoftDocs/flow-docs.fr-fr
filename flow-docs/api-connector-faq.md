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
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="api-connector-faq-microsoft-flow"></a>FAQ Connecteur API (Microsoft Flow)
## <a name="requirements"></a>Configuration requise
**Q :** Puis-je créer un connecteur sans API REST ? </br>
**R :** Non. Pour créer un connecteur, vous devez prendre en charge les API REST HTTP stables pour votre service. 

**Q :** Quels outils puis-je utiliser pour créer un connecteur ? </br>
**R :** Azure dispose de fonctionnalités et services que vous pouvez utiliser pour exposer en tant qu’API tout service tel qu’Azure App Service pour l’hébergement, Gestion des API, et bien plus encore.

**Q :** Quels types d’authentifications sont pris en charge ? </br>
**R :** Vous pouvez utiliser les normes d’authentification prises en charge suivantes :

* [OAuth 2.0](https://oauth.net/2/), y compris [Azure Active Directory](https://azure.microsoft.com/develop/identity/) ou des services spécifiques tels que Dropbox, GitHub et Salesforce
* OAuth 2.0 générique
* [Authentification De base](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [Clé API](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Déclencheurs
**Q :** Puis-je créer des déclencheurs sans webhooks ? </br>
**R :** Non. Les connecteurs personnalisés pour Azure Logic Apps et Microsoft Flow prennent en charge uniquement les déclencheurs basés sur webhook. Si vous souhaitez demander d’autres modèles d’implémentation, contactez [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) avec plus de détails sur votre API.

## <a name="certification"></a>Certification
**Q**: Je ne suis ni un partenaire Microsoft ni un éditeur de logiciels indépendant. Puis-je créer des connecteurs ? </br>
**R** : Oui. Vous pouvez inscrire ces connecteurs pour un usage au sein dans votre organisation mais, si vous souhaitez certifier et publier un connecteur, vous devez soit être propriétaire du service sous-jacent, soit présenter des droits explicites d’utiliser l’API.

## <a name="other"></a>Autres
**Q :** Mes API utilisent un hôte dynamique. Comment les implémenter avec OpenAPI ? </br>
**R :** Les connecteurs personnalisés ne prennent pas en charge les hôtes dynamiques. Utilisez plutôt un hôte statique pour le développement et les tests. Si vous voulez certifier votre connecteur, interrogez votre contact Microsoft sur l’implémentation dynamique.

**Q :** Prenez-vous en charge Postman Collection V2 ? </br>
**R :** Non. Seul Postman Collection V1 est actuellement pris en charge.

**Q :** Prenez-vous en charge OpenAPI 3.0 ? </br>
**R :** Non. Seul OpenAPI 2.0 est actuellement pris en charge.

