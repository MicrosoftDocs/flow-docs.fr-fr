---
title: En savoir plus sur les environnements Microsoft Flow | Microsoft Docs
description: Découvrez comment utiliser des environnements pour isoler vos flux
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
ms.openlocfilehash: e6667c1c1999c36177d40d52fa657edadd063516
ms.sourcegitcommit: d00c10759d4afb54517a0b1032f8d0a509006d5b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-an-environment"></a>Choix d’un environnement

Cet article vous présente les **environnements** Microsoft Flow dans lesquels vous pouvez créer, et en toute sécurité isoler vos flux, passerelles, connexions et autres ressources.

Voici ce que vous allez apprendre :

* Fonctionnalités fournies par les environnements.
* Changer d’environnement.
* Créer un flux dans l’environnement approprié.

## <a name="environments-overview"></a>Vue d’ensemble des environnements

Lorsque vous créez un flux, vous choisissez l’environnement qui l’héberge et les ressources utilisées par le flux. Vous pouvez utiliser différents environnements pour différents scénarios.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Voici quelques scénarios pour l’utilisation des environnements

Scénario|Recommandation
-----|-----
Vous voulez créer un flux qui utilise une connexion au service Common Data Service de Microsoft.|Placez le flux et le service Common Data Service dans le même environnement. Cela garantit que toutes les données sont isolées dans cet environnement (limite d’isolation).
Vous créez un flux pour votre service des ressources humaines. Vous souhaitez vous assurer que seuls les utilisateurs de votre service des ressources humaines ont accès au flux.|Créez un environnement et ajoutez-y uniquement des utilisateurs des ressources humaines. Placez le flux et les autres ressources utilisées par le flux dans cet environnement.
Des utilisateurs en Europe utilisent un flux pour afficher les données SharePoint.|Créez un environnement en Europe, puis créez votre flux et la connexion SharePoint associée. Cet environnement en Europe offre aux utilisateurs européens les meilleures performances, car toutes les ressources se trouvent en Europe (localité des données).

Pour créer des environnements, vous devez être administrateur de Microsoft Flow. Les administrateurs contrôlent également qui a accès aux environnements. Pour plus d’informations sur la façon dont vous pouvez créer et gérer les environnements, consultez la rubrique sur [l’administration des environnements](environments-overview-admin.md).

## <a name="switching-environments"></a>Changer d’environnement

Microsoft Flow permet de basculer facilement entre les environnements. Lorsque vous changez d’environnement, vous voyez uniquement les éléments qui sont créés dans cet environnement spécifique ; vous ne voyez pas les éléments des autres environnements.

Voici un exemple.

Vous avez créé un flux nommé *Nouvel employé* dans l’environnement *Ressources humaines*. Dans [Microsoft Flow](https://flow.microsoft.com), ouvrez l’environnement *Ventes*. Le flux *Nouvel employé* n’est pas répertorié. Pour voir le flux *Nouvel employé*, ouvrez l’environnement *Ressources humaines*. Rappelez-vous que les mêmes règles s’appliquent à tous les éléments que vous créez dans l’environnement, y compris les connexions, passerelles, flux, etc.

Suivez ces instructions pour changer d’environnement :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Dans l’angle supérieur droit, vous voyez une image qui représente votre profil.

   ![image de profil](./media/environments-overview-maker/default-environment.png)

1. Sélectionnez l’image. Une liste déroulante affiche tous les environnements disponibles. L’environnement dans lequel vous êtes actuellement connecté est coché :

   ![image de liste d’environnements](./media/environments-overview-maker/all-environments.png)
1. Pour basculer vers un autre environnement, sélectionnez ce dernier dans la liste :

   ![sélectionner l’environnement vers lequel basculer](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow bascule vers le nouvel environnement.

## <a name="create-flows-in-the-right-environment"></a>Créer des flux dans l’environnement approprié

Avant de créer un flux, sélectionnez l’environnement dans lequel vous allez ajouter le flux et ses ressources.

> [!NOTE]
> Si vous créez un flux dans l’environnement incorrect, vous devrez le supprimer, puis le créer dans l’environnement approprié.

Lorsque vous choisissez l’environnement pour héberger vos flux, tenez compte des facteurs suivants :

* Vous pouvez créer des passerelles uniquement dans l’environnement par défaut. Aussi, si vous voulez utiliser une passerelle pour connecter votre flux aux données locales, vous devez utiliser l’environnement par défaut.
* Les bases de données du service Common Data Service de Microsoft sont liées à un environnement spécifique. Par conséquent, si vous souhaitez créer un flux qui utilise Common Data Service, vous devez le créer dans l’environnement qui héberge la base de données.
* Vous voyez tous les environnements dans lesquels vous pouvez modifier les ressources. Toutefois, vous devez demander à un administrateur de vous ajouter en tant que créateur à tous les environnements dans lesquels vous souhaitez créer des flux.

> [!NOTE]
> Vous pouvez toujours créer des flux dans l’environnement par défaut.

## <a name="next-steps"></a>Étapes suivantes

* [Créer un flux à partir d’un modèle](get-started-logic-template.md)
* [Créer un flux](get-started-logic-flow.md)
* [Vue d’ensemble de l’environnement pour les administrateurs](environments-overview-admin.md)