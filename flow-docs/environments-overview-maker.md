---
title: "Basculer entre des environnements lors de la création d’un flux Microsoft | Microsoft Docs"
description: "Découvrez comment un créateur utilise différents environnements lors de la création d’un flux Microsoft"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>Choix d’un environnement
Avec Microsoft Flow, vous pouvez travailler dans différents environnements et basculer facilement entre ces derniers. Cet article aborde les sujets suivants relatifs à l’environnement :

* Informations sur le rôle des environnements
* Changer d’environnement
* Créer un flux dans l’environnement approprié

## <a name="environments-overview"></a>Vue d’ensemble des environnements
Les environnements fournissent une limite d’isolation pour vos flux, connexions, passerelles et autres ressources. Lorsque vous créez un flux, vous choisissez l’environnement qui l’héberge et les ressources utilisées par ce flux. Vous pouvez utiliser différents environnements pour différents scénarios.

Voici quelques exemples :

* Vous créez un flux qui utilise une connexion au service Common Data Service de Microsoft. Dans ce scénario, le flux et le service Common Data Service se trouvent dans le même environnement. Cela garantit que toutes les données sont isolées dans cet environnement (limite d’isolation).
* Vous créez un flux pour votre service des ressources humaines. Vous souhaitez vous assurer que seuls les utilisateurs de votre service des ressources humaines ont accès au flux. Par exemple, vous ne souhaitez pas que votre groupe Ventes utilise le flux. Dans ce scénario, vous pouvez utiliser un environnement séparé, pour lequel seuls les utilisateurs des ressources humaines ont des autorisations, afin d’héberger le flux et toutes les ressources qu’il utilise, y compris les connexions ou les passerelles.
* Il existe des utilisateurs en Europe qui utilisent un flux pour afficher les données SharePoint. Dans ce scénario, créez un environnement en Europe qui héberge le flux et la connexion SharePoint. Cet environnement en Europe offre aux utilisateurs européens les meilleures performances, comme toutes les ressources se trouvent en Europe (localité des données).

Les environnements sont créés par les administrateurs Microsoft Flow. Ces derniers contrôlent également qui a accès aux différents environnements.

Cette rubrique montre comment naviguer entre les différents environnements. Pour plus d’informations sur la façon dont vous pouvez créer et gérer les environnements, consultez la rubrique sur [l’administration des environnements](environments-overview-admin.md).

## <a name="switching-environments"></a>Changer d’environnement
Microsoft Flow permet de basculer relativement facilement entre les environnements. Lorsque vous changez d’environnement, vous voyez tous les éléments de cet environnement spécifique. Vous ne voyez pas les éléments des autres environnements.

Voici un exemple.

Vous créez un flux nommé *Nouvel employé* dans l’environnement *Ressources humaines*. Dans [flow.microsoft.com](http://flow.microsoft.com), ouvrez l’environnement *Ventes*. Le flux *Nouvel employé* n’est pas répertorié. Pour voir le flux *Nouvel employé*, ouvrez l’environnement *Ressources humaines*. Rappelez-vous, cela s’applique à tous les éléments que vous créez dans l’environnement, y compris les connexions, les passerelles, PowerApps, etc.

1. Ouvrez [flow.microsoft.com](http://flow.microsoft.com).
2. En haut à droite, vous voyez votre nom et l’environnement dans lequel vous êtes :  
   ![](./media/environments-overview-maker/default-environment.png)
   
    Dans l’image, notez les notifications. Celles-ci sont propres au flux dans cet environnement par défaut.
3. Sélectionnez votre nom. Dans la liste déroulante, tous les environnements disponibles sont répertoriés. Votre environnement actuel est sélectionné :  
   ![](./media/environments-overview-maker/all-environments.png)
4. Pour basculer vers un autre environnement, sélectionnez ce dernier dans la liste :  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow bascule automatiquement vers le nouvel environnement :  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    Dans l’image, notez l’absence de notifications. Le nouvel environnement Europe n’a aucune notification.

## <a name="create-flows-in-the-right-environment"></a>Créer des flux dans l’environnement approprié
Avant de créer un flux, assurez-vous toujours de sélectionner l’environnement dans lequel vous souhaitez placer le flux. Sinon, vous allez devoir supprimer le flux et le recréer dans l’environnement approprié.

Lorsque vous choisissez l’environnement pour créer vos flux, tenez compte des facteurs suivants :

* Les passerelles sont créées dans l’environnement par défaut. Les passerelles ne peuvent pas être créées dans d’autres environnements. Par conséquent, si vous souhaitez vous connecter aux données locales, vous devrez utiliser l’environnement par défaut.
* Les flux peuvent uniquement utiliser les connexions et d’autres ressources dans le même environnement. Ils ne peuvent pas utiliser de ressources dans un autre environnement. Par exemple, vous créez un flux qui utilise un connecteur personnalisé. Ce connecteur personnalisé doit être dans le même environnement que le flux.
* La base de données du service Common Data Service de Microsoft est toujours liée à un seul environnement. Cela signifie que si vous voulez travailler avec les données du service Common Data Service, vous devez sélectionner le même environnement que celui dans lequel se trouve la base de données.
* Vous verrez tous les environnements dans lesquels vous pouvez modifier les ressources. Toutefois, cela ne signifie pas que vous pouvez créer des ressources dans tous les environnements. Par conséquent, dans certains environnements, vous ne pouvez pas créer de flux. Vous devez demander à l’administrateur de vous ajouter comme **créateur** de cet environnement ou, choisir un autre environnement pour y créer le flux (vous serez toujours en mesure de créer des flux dans l’environnement par défaut).

## <a name="what-you-did"></a>Ce que vous avez fait
En suivant ces étapes, vous basculez entre les environnements que vous êtes autorisé à utiliser. Commencez maintenant à créer vos flux.

## <a name="next-steps"></a>Étapes suivantes
[Créer un flux à partir d’un modèle](get-started-logic-template.md)  
[Créer un flux](get-started-logic-flow.md)  
[Vue d’ensemble de l’environnement pour les administrateurs](environments-overview-admin.md)

