---
title: "Développer un connecteur API | Microsoft Docs"
description: "Décrivez votre API, spécifiez le type d’authentification, créez des déclencheurs et des actions et testez."
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
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 8731e8a90a62bac4a05068386d23d2449952860b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="develop-an-api-connector-microsoft-flow"></a>Développer un connecteur API (Microsoft Flow)
Le processus de création d’un connecteur est constitué de plusieurs étapes. Pour commencer, dans [Microsoft Flow](https://flow.microsoft.com/), cliquez ou appuyez sur le bouton **Paramètres** (icône d’engrenage) dans l’angle supérieur droit de la page. Cliquez ou appuyez ensuite sur **Connecteurs personnalisés**.

![Trouver des connecteurs API](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>Décrire votre API
Les connecteurs API sont décrits à l’aide du [standard OpenAPI](https://swagger.io/) pour définir l’interface d’une API HTTP. Vous pouvez commencer avec un fichier OpenAPI existant ou vous pouvez importer un fichier [Postman Collection](https://www.getpostman.com/docs/collections), qui génère automatiquement le fichier OpenAPI pour vous. 

![Définir votre schéma d’API](./media/api-connectors-dev/build-your-api-updated.png)

Si vous démarrez à partir d’une de ces descriptions d’API, les champs de métadonnées de l’Assistant sont remplis automatiquement. Vous pouvez les modifier à tout instant.  

## <a name="build-security"></a>Intégrer la sécurité
Choisissez le type d’authentification pris en charge par votre service et fournissez des détails supplémentaires pour permettre à l’identité de transiter entre votre service et les clients de façon appropriée. 

![Schéma de sécurité](./media/api-connectors-dev/security.png)

[En savoir plus](register-custom-api.md) sur la sécurité des connecteurs.

## <a name="build-triggers-and-actions"></a>Créer des actions et déclencheurs
1. Pour créer les déclencheurs et les actions de votre connecteur, basculez vers l’onglet **Définition**. 
   
    ![Schéma de la définition](./media/api-connectors-dev/definition.png)
2. À l’aide de l’Assistant, vous pouvez ajouter de nouvelles opérations ou modifier le schéma et la réponse des opérations existantes. Les propriétés **générales** de chaque opération vous permettent de contrôler l’expérience utilisateur de votre connecteur. En savoir plus sur les différents types d’opérations à l’aide des liens ci-dessous :
   
   * [Déclencheurs](customapi-webhooks.md) (non visibles dans PowerApps)
   * [Actions](register-custom-api.md)
     
     Pour implémenter des fonctionnalités avancées pour Microsoft Flow, reportez-vous à [Extensions OpenAPI pour les connecteurs API](https://flow.microsoft.com/documentation/customapi-how-to-swagger/). 
3. Enfin, cliquez ou appuyez sur **Créer un connecteur** pour inscrire le connecteur API.

Pour des fonctionnalités supplémentaires non disponibles dans l’Assistant, contactez [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com).

## <a name="test-the-connector"></a>Tester le connecteur
Avant la soumission, testez votre connecteur API d’une ou plusieurs façons : 

* À l’aide du connecteur API [Assistant de test](https://flow.microsoft.com/blog/new-updates-custom-api/), vous pouvez appeler chaque opération afin de vérifier ses fonctionnalités et son schéma de réponse.
* Dans le concepteur Microsoft Flow, vous pouvez concevoir visuellement des flux à l’aide de votre connecteur API. Cette méthode de test vous donne une visibilité sur les fonctionnalités d’interface utilisateur de votre connecteur.
* Dans PowerApps Studio, vous pouvez appeler chaque opération à l’aide de la barre de formule, puis lier la réponse à des contrôles sur votre écran.

Cette rubrique présente une vue d’ensemble. Pour plus d’informations, consultez [Inscrire et utiliser un connecteur personnalisé](register-custom-api.md).

