---
title: En savoir plus sur les environnements de Microsoft Flow | Microsoft Docs
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547936"
---
# <a name="choosing-an-environment"></a>Choix d’un environnement
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cet article présente les Microsoft Flow **environnements** dans lesquels vous pouvez créer et isoler en toute sécurité vos flux, passerelles, connexions et autres ressources.

Vous en apprendrez plus sur les éléments suivants :

* Fonctionnalités fournies par les environnements.
* Basculement entre les environnements.
* Comment créer un fluide dans l’environnement approprié.

## <a name="environments-overview"></a>Vue d’ensemble des environnements

Lorsque vous créez un fluide, vous choisissez un environnement pour héberger le Flow et les ressources que le Flow utilise. Vous pouvez utiliser des environnements distincts pour différents scénarios.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Voici quelques scénarios d’utilisation des environnements

Consiste|Recommandés
-----|-----
Vous souhaitez créer un fluide qui utilise une connexion à l’Common Data Service Microsoft.|Placez votre Flow et le Common Data Service dans le même environnement. Cela garantit que toutes les données sont isolées dans cet environnement (limite d’isolation).
Vous créez un Flow pour votre service des ressources humaines. Vous souhaitez vous assurer que seuls les utilisateurs de votre département ressources humaines ont accès au Flow.|Créez un environnement et ajoutez uniquement les utilisateurs RH à ce dernier. Placez le Flow et toutes les autres ressources que le Flow utilise dans cet environnement.
Il existe des utilisateurs en Europe qui utilisent un Flow pour afficher les données SharePoint.|Créez un environnement en Europe, puis créez votre Flow et la connexion SharePoint dans celui-ci. Cet environnement en Europe offre aux utilisateurs européens les meilleures performances, étant donné que toutes les ressources sont locales à l’Europe (localité des données).

Pour créer des environnements, vous devez être un administrateur de Microsoft Flow. Les administrateurs contrôlent qui a accès aux environnements. Pour plus d’informations sur la façon dont vous pouvez créer et gérer des environnements, consultez la rubrique [administrer des environnements](environments-overview-admin.md) .

## <a name="switching-environments"></a>Changer d’environnement

Microsoft Flow permet de basculer facilement entre les environnements. Lorsque vous changez d’environnement, vous voyez uniquement les éléments qui sont créés dans cet environnement spécifique. vous ne voyez pas ou n’avez pas accès aux éléments dans un autre environnement.

Voici un exemple.

Vous avez créé un workflow nommé *nouvel employé* dans l’environnement *ressources humaines* . Dans [Microsoft Flow](https://flow.microsoft.com), vous ouvrez l’environnement *Sales* . Le *nouvel employé* Flow n’est pas listé. Pour afficher le Flow *nouvel employé* , ouvrez l’environnement *ressources humaines* . N’oubliez pas que les mêmes règles s’appliquent à tous les autres éléments que vous avez créés dans l’environnement, y compris les connexions, les passerelles, les flux, etc.

Pour changer d’environnement, procédez comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com).
1. Dans le coin supérieur droit, vous voyez une image qui représente votre profil.

   ![image de profil](./media/environments-overview-maker/default-environment.png)

1. Sélectionnez l’image. Une liste déroulante affiche tous les environnements disponibles. L’environnement dans lequel vous êtes actuellement connecté est activé :

   ![image de la liste d’environnements](./media/environments-overview-maker/all-environments.png)
1. Pour basculer vers un autre environnement, sélectionnez cet environnement dans la liste :

   ![sélectionner un environnement vers lequel basculer](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow bascule vers le nouvel environnement.

## <a name="create-flows-in-the-right-environment"></a>Créer des flux dans l’environnement approprié

Avant de créer un fluide, sélectionnez l’environnement dans lequel vous allez ajouter le Flow et ses ressources.

> [!NOTE]
> Si vous créez un workflow dans un environnement incorrect, vous devez le supprimer, puis le créer dans l’environnement approprié.

Lorsque vous choisissez un environnement pour héberger vos flux, tenez compte des facteurs suivants :

* Vous pouvez uniquement créer des passerelles dans l’environnement par défaut. Par conséquent, si vous souhaitez utiliser une passerelle pour connecter votre Flow à des données locales, vous devez utiliser l’environnement par défaut.
* Les bases de données Microsoft Common Data Service sont liées à un environnement spécifique. Par conséquent, si vous souhaitez créer un fluide qui utilise la Common Data Service, vous devez créer le Flow dans l’environnement qui héberge la base de données.
* Vous verrez tous les environnements dans lesquels vous pouvez modifier des ressources. Toutefois, vous devez demander à un administrateur de vous ajouter en tant que créateur à tous les environnements dans lesquels vous souhaitez créer des flux.

> [!NOTE]
> Vous serez toujours en mesure de créer des flux dans l’environnement par défaut.

## <a name="next-steps"></a>Étapes suivantes

* [Créer un fluide à partir d’un modèle](get-started-logic-template.md)
* [Créer un Flow](get-started-logic-flow.md)
* [Vue d’ensemble de l’environnement pour les administrateurs](environments-overview-admin.md)
