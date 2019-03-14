---
title: Créer un flux automatisé avec Common Data Service for Apps | Microsoft Docs
description: Créer des workflows à l’aide d’une connexion Common Data Service for Apps et Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: brandonsimons
manager: ryjones
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: brandonsimons
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f9a417f99b6ea4105a451b65f7ccabbf36922d78
ms.sourcegitcommit: 61f0eb1fdc54da02eb57dadf09899fa6f308b00d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57524494"
---
# <a name="create-an-automated-flow-by-using-common-data-service-for-apps"></a>Créer un flux automatisé à l’aide de Common Data Service for Apps

Avec le connecteur Common Data Service for Apps, vous pouvez créer des flux qui sont démarrés par des événements de création et de mise à jour dans votre base de données Common Data Service. De plus, vous pouvez effectuer des actions de création, de mise à jour, de récupération et de suppression sur des enregistrements de la base de données Common Data Service for Apps.

## <a name="initiate-a-flow-from-common-data-service-for-apps"></a>Démarrer un flux à partir de Common Data Service for Apps

Vous pouvez utiliser n’importe lequel des déclencheurs suivants pour démarrer votre flux :

- Quand un enregistrement est sélectionné
- Quand un enregistrement est créé
- Quand un enregistrement est supprimé
- Quand un enregistrement est mis à jour


> [!div class="mx-imgBorder"]
> ![Sélectionner un déclencheur](./media/cds-connector/Triggers.png)

Si le déclencheur choisi nécessite qu’un environnement soit sélectionné, vous pouvez choisir `(Current)`, qui utilise toujours la base de données dans l’environnement dans lequel s’exécute Microsoft Flow. Si vous voulez que votre flux se déclenche toujours suite à un événement dans un environnement spécifique, sélectionnez cet environnement.

> [!div class="mx-imgBorder"]
> ![Choisir un environnement](./media/cds-connector/Environments.png)

Vous pouvez utiliser des étendues pour déterminer si votre flux s’exécute quand vous créez un enregistrement, quand un enregistrement est créé par un utilisateur au sein de votre division ou quand un enregistrement est créé par un utilisateur de votre organisation.

> [!div class="mx-imgBorder"]
> ![Choisir une étendue](./media/cds-connector/Scopes.png)

|Étendue|Moment d’activation du déclencheur|
| --- | --- |
|Division|Une action est effectuée sur un enregistrement appartenant à votre division|
|Organisation|Une action est effectuée par tout utilisateur de l’organisation ou de la base de données|
|Divis. mère : sous-division|Une action est effectuée sur un enregistrement appartenant à votre division ou à une sous-division|
|Utilisateur|Une action est effectuée sur un enregistrement dont vous êtes le propriétaire|

Les déclencheurs qui s’exécutent quand un enregistrement est mis à jour peuvent également utiliser des attributs de filtrage. Cela garantit que le flux s’exécute uniquement quand tous les attributs définis sont mis à jour.

> [!IMPORTANT]
> Utilisez des attributs de filtre pour empêcher votre flux de s’exécuter inutilement.

Ce flux se déclenche dès que le premier ou le dernier nom de contact détenu par l’utilisateur du flux est mis à jour.

> [!div class="mx-imgBorder"]
> ![Attributs de filtre](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilèges des déclencheurs

Pour créer un flux qui se déclenche suite à une action de création, de mise à jour ou de suppression sur un enregistrement, l’utilisateur doit disposer d’autorisations de niveau utilisateur pour effectuer des opérations de création, de lecture, d’écriture et de suppression sur l’entité d’inscription de rappel. De plus, en fonction des étendues définies, l’utilisateur peut devoir disposer au moins de ce niveau de lecture sur la même entité.  [Découvrez des informations supplémentaires](https://docs.microsoft.com/power-platform/admin/database-security) sur la sécurité des environnements.

## <a name="write-data-into-common-data-service-for-apps"></a>Écrire des données dans Common Data Service for Apps

Pour écrire des données dans Common Data Service for Apps, utilisez l’une des actions suivantes :

- Créer un enregistrement
- Mettre à jour un enregistrement

Voici un exemple de création d’une tâche de suivi quand un utilisateur donné crée un enregistrement de compte.  

> [!div class="mx-imgBorder"]
> ![Tâche de suivi](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Concepts avancés

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Écrire des données dans le client, le propriétaire et les champs de type Concernant

Pour écrire des données dans le client, le propriétaire et les champs de type Concernant, deux champs doivent être remplis.

| Catégorie du champ | Exemples de paramètres |
| --- | --- |
| Concernant | Concernant = ID de l’enregistrement (par exemple, un ID de compte) et Type Concernant comme sélectionné dans la liste. |
| Client | Représente l’ID de l’enregistrement et le type de client comme sélectionné dans la liste. |
| Propriétaire | Représente l’ID de l’équipe ou de l’utilisateur système, et le type de propriétaire comme sélectionné dans la liste. |

### <a name="enable-upsert-behavior"></a>Activer le comportement d’upsert

Vous pouvez exploiter la commande **Mettre à jour un enregistrement** pour fournir des actions d’upsert, ce qui met à jour l’enregistrement s’il existe déjà ou en crée un nouveau. Pour appeler upsert, fournissez l’entité et une clé GUID. Si l’enregistrement avec le type et la clé spécifiés existe, une mise à jour se produit. Sinon, un enregistrement avec la clé spécifiée est créé.

### <a name="trigger-behavior"></a>Comportement des déclencheurs

Si vous avez un déclencheur inscrit sur la mise à jour d’un enregistrement, le flux s’exécute pour chaque mise à jour *validée* sur l’enregistrement donné. Le service appelle votre flux de façon asynchrone et avec la charge utile qu’il capture au moment où l’appel se produit.

> [!NOTE]
> Si vous avez deux mises à jour qui se produisent à quelques secondes d’intervalles, le flux peut être déclenché plusieurs fois avec le contenu avec version le plus récent.

Les exécutions de flux peuvent être retardées s’il existe un backlog de tâches système dans votre environnement.  Si ce retard se produit, votre flux est déclenché quand la tâche système destinée à appeler le flux s’exécute.
