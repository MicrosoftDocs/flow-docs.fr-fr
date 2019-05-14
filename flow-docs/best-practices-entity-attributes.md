---
title: Meilleures pratiques pour l’utilisation des attributs d’entité de flux de processus métier | MicrosoftDocs
description: Découvrez les meilleures pratiques pour l’utilisation des attributs d’entité de flux de processus métier.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 2931edb777c1ed57e040670fc8a1c55252ac95b1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64472969"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Meilleures pratiques pour l’utilisation des attributs de flux de processus métier


Les attributs liés aux processus hérités dans les entités sont déconseillés. Voici quelques meilleures pratiques pour l’utilisation de l’attribut *Active Stage* (activestageid) sur l’entité de flux de processus métier. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Création de rapport sur la phase active d’un flux de processus métier

Supposons que vous souhaitez obtenir un aperçu de votre pipeline des ventes en créant un rapport sur la phase active dans laquelle se trouve le **Processus de vente prospect-opportunité**.

Auparavant, pour créer un rapport sur les processus métier par phase, il était possible de définir une vue sur chaque entité connexe du flux de processus métier et créer un rapport sur le champ *Active Stage* (activestageid).

Le champ *Active Stage* (activestageid) étant déconseillé sur les entités connexes, il existe deux façons de créer des rapports sur les flux de processus métier.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Option 1 : Vues et graphiques sur l’entité de flux de processus métier **(recommandé)**

Dans les versions 9.0 et ultérieures, chaque flux de processus métier crée sa propre entité Common Data Service, généralement avec le même nom que le flux de processus métier. Pour créer des rapports sur le flux de processus métier, sélectionnez l’entité de flux de processus métier pour lequel vous voulez créer un rapport et créez des vues et des graphiques, comme vous le faisiez avant.

Dans notre exemple, procédez comme suit pour accéder à l’entité **Processus de vente prospect-opportunité** :
1. Accédez à https://web.powerapps.com.
1. Sélectionnez **Données**.
1. Sélectionnez **Entités**.
1. Définissez le filtre sur **Tout**.
1. Recherchez et sélectionnez l’entité **Processus de vente prospect-opportunité**.

   ![entité processus de vente prospect-opportunité](media/best-practices-entity-attributes/lead-opportunity-process.png)

Ici, vous pouvez définir des vues et graphiques comme vous le feriez sur n’importe quelle autre entité.

![détails de l’entité du processus de traduction](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

L’avantage de cette approche est que vous pouvez utiliser une vue ou un graphique unique pour créer un rapport sur les flux de processus métier qui s’étendent sur plusieurs entités.

En outre, comme l’entité de flux de processus métier n’est pas différente de toute autre entité personnalisée dans Common Data Service, vous pouvez ajouter des champs personnalisés à l’entité pour effectuer le suivi de toutes les informations dont vous avez besoin.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Option 2 : copier la phase active dans une entité connexe

Ou bien, pour continuer la création de rapports sur l’entité associée, créez un flux pour copier le champ *Active Stage* (activestageid) à partir de l’entité de flux de processus métier dans un champ personnalisé sur les entités Common Data Service associées.

Voici quelques éléments à prendre en compte lorsque vous utilisez cette approche :

1.  Il est possible d’avoir plusieurs flux de processus métier en cours d’exécution sur une seule entité. Avec cette approche, il est préférable d’avoir un champ personnalisé qui stocke la phase active pour chaque flux de processus métier qui s’exécute sur l’entité. Cette approche garantit l’intégrité de la création de rapports.

1.  Étant donné que la création de rapports est pilotée par l’entité associée, il n’est pas possible de créer une vue unique pour les rapports sur les flux de processus métier qui s’étendent sur plusieurs entités.

## <a name="using-the-active-stage-to-run-logic"></a>Utilisation de la phase active pour exécuter la logique

Voici quelques cas dans lesquels vous souhaiterez peut-être exécuter une logique qui est basée sur la phase active :

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Utilisation de la phase active pour exécuter la logique côté client

Lorsque vous utilisez le processus métier, il existe beaucoup de choses que vous pouvez vouloir effectuer automatiquement. Par exemple :

-   Modifier le flux de processus métier actif en fonction des informations nouvellement disponibles dans le formulaire ou le flux de processus métier.

-   Déplacer la phase active vers l’étape précédente ou suivante, en fonction des valeurs entrées par les utilisateurs pour les étapes ou les champs de formulaire.

-   Masquer ou afficher des champs et onglets de formulaire en fonction de la phase sélectionnée.

-   Afficher des messages d’information et exécuter des calculs en fonction des flux de processus métier actifs, de la phase active sélectionnée ou des événements, comme le déplacement de la phase active.

> [!TIP]
> Pour les scénarios comme ceux-ci, utilisez l’ensemble [d’API clientes](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) pris en charge pour les flux de processus métier.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Utilisation de la phase active pour exécuter la logique côté serveur

Il peut arriver que l’automatisation basée sur le flux de processus métier doit être effectuée côté serveur. Par exemple :

-   Envoyer un e-mail à un utilisateur si la phase **Qualify** du **Processus de vente Opportunité** est active pendant plus de 15 jours.

-   Créer automatiquement un ensemble d’activités pertinentes à la phase active du **Processus de vente Opportunité** chaque fois qu’il change.

-   Terminer automatiquement le **Processus de vente Opportunité** à l’issue de l’activité d’appel téléphonique de clôture.

> [!TIP]
> Utiliser des flux de travail Common Data Service classiques ou des flux que vous définissez sur l’entité pour le flux de processus métier.
> 

Pour créer un flux de travail Common Data Service classique qui crée des activités pour les révisions de solution interne et effectuer le suivi avec le client lors de la phase **Propose** du **Processus de vente Opportunité** :

1. Créez-le sur l’entité **Processus de vente Opportunité** et configurez-le pour s’exécuter chaque fois que le champ **Active Stage** pour l’entité change. 
1. Définissez une condition pour vérifier si le champ **Active Stage** est égal à **Propose**. 
1. Créez un enregistrement de rendez-vous et d’appel téléphonique pour la révision interne de la solution et l’appel du client pour passer en revue la solution respectivement.

   ![clôturer le suivi de la phase](media/best-practices-entity-attributes/close-stage-followup.png)
