---
title: Créer un Flow automatisé avec Common Data Service | Microsoft Docs
description: Créer des flux de travail à l’aide d’une connexion Common Data Service et Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547114"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Créer un workflow automatisé à l’aide de Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Avec le connecteur Common Data Service, vous pouvez créer des flux initiés par les événements de création et de mise à jour dans votre base de données Common Data Service. En outre, vous pouvez effectuer des actions de création, de mise à jour, de récupération et de suppression sur des enregistrements au sein de la base de données Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Lancer un Flow à partir de Common Data Service

Vous pouvez utiliser l’un des déclencheurs suivants pour initier votre Flow :

- Quand un enregistrement est sélectionné
- Lors de la création d’un enregistrement
- Lorsqu’un enregistrement est supprimé
- Quand un enregistrement est mis à jour


> [!div class="mx-imgBorder"]
> ![sélectionner un déclencheur](./media/cds-connector/Triggers.png)

Si le déclencheur sélectionné nécessite la sélection d’un environnement, vous pouvez choisir `(Current)`, qui utilisera toujours la base de données dans l’environnement dans lequel Microsoft Flow s’exécute. Si vous souhaitez que votre Flow soit toujours déclenché en fonction d’un événement dans un environnement spécifique, sélectionnez cet environnement.

> [!div class="mx-imgBorder"]
> ![choisir l’environnement](./media/cds-connector/Environments.png)

Vous pouvez utiliser des étendues pour déterminer si votre workflow s’exécute si vous créez un nouvel enregistrement, si un nouvel enregistrement est créé par un utilisateur au sein de votre division, ou si un nouvel enregistrement est créé par un utilisateur de votre organisation.

> [!div class="mx-imgBorder"]
> ![choisir une étendue](./media/cds-connector/Scopes.png)

|Étendue|Synchronisation du déclencheur|
| --- | --- |
|Division|Une action est effectuée sur un enregistrement détenu par votre division|
|Dernière|Une action est effectuée par toute personne au sein de l’organisation ou de la base de données|
|Parent : Division enfant|Une action est effectuée sur un enregistrement détenu par votre division ou une division enfant|
|Utilisateur|Une action est effectuée sur un enregistrement dont vous êtes propriétaire|

Les déclencheurs qui s’exécutent lorsqu’un enregistrement est mis à jour peuvent également utiliser des attributs de filtrage. Cela garantit que le workflow s’exécute uniquement lorsque l’un des attributs définis est mis à jour.

> [!IMPORTANT]
> Utilisez les attributs de filtre pour empêcher l’exécution inutile de votre workflow.

Ce processus déclenche chaque fois que le nom ou le prénom du contact auquel appartient l’utilisateur de Flow est mis à jour.

> [!div class="mx-imgBorder"]
> attributs de filtre de ![](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilèges de déclencheur

Pour créer un Flow qui se déclenche à partir de Create, Update ou DELETE sur un enregistrement, l’utilisateur doit disposer des autorisations de niveau utilisateur pour Create, Read, Write et Delete sur l’entité d’inscription de rappel. En outre, selon les étendues définies, l’utilisateur peut avoir besoin au moins de ce niveau de lecture sur la même entité.  [En savoir plus](https://docs.microsoft.com/power-platform/admin/database-security) sur la sécurité de l’environnement.

## <a name="write-data-into-common-data-service"></a>Écrire des données dans Common Data Service

Utilisez l’une des actions suivantes pour écrire des données dans Common Data Service :

- Créer un nouvel enregistrement
- Mettre à jour un enregistrement

Voici un exemple de création d’une tâche de suivi lorsque l’utilisateur donné crée un nouvel enregistrement de compte.  

> [!div class="mx-imgBorder"]
> tâche de suivi ![](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Concepts avancés

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Écrire des données dans les champs client, propriétaire et à propos de

Pour écrire des données dans les champs Customer, owner et relative, deux champs doivent être remplis.

| Catégorie de champ | Exemples de paramètres |
| --- | --- |
| Agissant | Concernant = ID de l’enregistrement (par exemple, ID de compte) et concernant le type sélectionné dans la liste. |
| Assistance | Représente l’ID de l’enregistrement et le type de client sélectionné dans la liste. |
| Du | Représente l’ID de l’utilisateur ou de l’équipe système, et le type de propriétaire sélectionné dans la liste. |

### <a name="enable-upsert-behavior"></a>Activer le comportement upsert

Vous pouvez utiliser la commande **mettre à jour un enregistrement** pour fournir des actions Upsert, qui met à jour l’enregistrement s’il existe déjà, ou crée un enregistrement. Pour appeler Upsert, fournissez l’entité et une clé GUID. S’il existe un enregistrement avec le type et la clé spécifiés, une mise à jour se produit. Dans le cas contraire, un enregistrement avec la clé spécifiée est créé.

### <a name="trigger-behavior"></a>Comportement du déclencheur

Si un déclencheur est inscrit sur la mise à jour d’un enregistrement, le workflow s’exécute pour chaque mise à jour *validée* de l’enregistrement donné. Le service appelle votre Flow de façon asynchrone et avec la charge utile qu’il capture au moment où l’appel se produit.

> [!NOTE]
> Si vous avez deux mises à jour qui se produisent dans les secondes les unes des autres, le workflow peut être déclenché plusieurs fois avec le contenu avec version le plus récent.

Les exécutions de Flow peuvent être retardées en cas de retard de travail système dans votre environnement.  Si ce délai se produit, votre workflow est déclenché lorsque le travail système est appelé à s’exécuter.
