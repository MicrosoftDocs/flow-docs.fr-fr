---
title: Meilleures pratiques relatives à l’utilisation des attributs d’entité de workflow de processus d’entreprise | MicrosoftDocs
description: Découvrez les meilleures pratiques pour l’utilisation des attributs d’entité Business Process Flow.
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
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545279"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Meilleures pratiques en matière d’utilisation des attributs de workflow de processus d’entreprise
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Les attributs hérités liés au processus dans les entités sont déconseillés. Voici quelques-unes des meilleures pratiques pour l’utilisation de l’attribut *stage actif* (activestageid) sur l’entité Business Process Flow. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Création de rapports sur l’étape active d’un workflow de processus d’entreprise

Supposons que vous souhaitiez obtenir une vue de votre pipeline de ventes en signalant l’étape active à laquelle est situé le **prospect dans le processus de vente des opportunités** .

Auparavant, pour créer des rapports sur les processus d’entreprise par étape, vous pouvez définir une vue sur chaque entité associée du workflow du processus d’entreprise, puis créer un rapport sur le champ *étape active* (activestageid).

Avec la dépréciation du champ *étape active* (activestageid) sur les entités associées, il existe deux façons de rendre compte des flux de processus d’entreprise.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Option 1 : affichages et graphiques sur l’entité de workflow de processus d’entreprise **(recommandé)**

Dans les versions 9,0 et ultérieures, chaque workflow de processus d’entreprise crée sa propre Common Data Service entité, généralement avec le même nom que le workflow du processus d’entreprise. Pour créer un rapport sur le workflow du processus d’entreprise, sélectionnez l’entité du workflow de processus d’entreprise sur lequel vous souhaitez créer un rapport, puis créez des affichages et des graphiques, comme vous l’avez fait précédemment.

Dans notre exemple, suivez les étapes ci-dessous pour accéder à l’entité **lead to opportunité Sales process** :
1. Accédez à https://web.powerapps.com.
1. Sélectionnez les **données**.
1. Sélectionnez les **entités**.
1. Définissez le filtre sur **tout**.
1. Recherchez, puis sélectionnez l’entité **lead to opportunité Sales process** .

   ![diriger vers l’entité de processus de vente d’opportunités](media/best-practices-entity-attributes/lead-opportunity-process.png)

Ici, vous pouvez définir des vues et des graphiques comme vous le feriez sur n’importe quelle autre entité.

![Détails de l’entité processus de traduction](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

L’un des avantages de cette approche est que vous pouvez utiliser une vue ou un graphique unique pour effectuer un rapport sur les flux de processus d’entreprise qui s’étendent sur plusieurs entités.

En outre, comme l’entité de workflow de processus d’entreprise n’est pas différente de celle d’une autre entité personnalisée dans Common Data Service, vous pouvez ajouter des champs personnalisés à l’entité pour suivre toutes les informations supplémentaires dont vous avez besoin.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Option 2 : copier l’étape active vers une entité associée

Sinon, pour poursuivre la création de rapports à partir de l’entité associée, créez un Flow pour copier le champ d' *étape active* (activestageid) à partir de l’entité de workflow de processus d’entreprise dans un champ personnalisé sur les entités Common Data Service associées.

Voici quelques éléments à prendre en compte lorsque vous utilisez cette approche :

1.  Il est possible d’exécuter plusieurs workflows de processus d’entreprise sur une seule entité. Avec cette approche, il est préférable d’avoir un champ personnalisé qui stocke l’étape active pour chaque workflow de processus d’entreprise qui s’exécute sur l’entité. Cette approche garantit l’intégrité de la création de rapports.

1.  Comme la création de rapports est motivée par l’entité associée, il n’est pas possible de créer une vue unique qui signale des flux de processus d’entreprise qui s’étendent sur plusieurs entités.

## <a name="using-the-active-stage-to-run-logic"></a>Utilisation de l’étape active pour exécuter la logique

Voici quelques cas dans lesquels vous pouvez souhaiter exécuter une logique basée sur l’étape active :

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Utilisation de l’étape active pour exécuter une logique côté client

À mesure que vous utilisez le processus d’entreprise, vous souhaiterez peut-être effectuer automatiquement plusieurs opérations. Par exemple :

-   Modifiez le workflow de processus d’entreprise actif en fonction des informations récemment disponibles sur le formulaire ou le processus d’entreprise.

-   Déplacer l’étape active vers l’étape suivante ou précédente, en fonction des valeurs entrées par les utilisateurs pour les étapes ou les champs de formulaire.

-   Masquer ou afficher les onglets et les champs de formulaire en fonction de la phase sélectionnée.

-   Affichez des messages informatifs et exécutez des calulations en fonction des flux de processus d’entreprise actifs, de l’étape active ou sélectionnée ou des événements tels que le déplacement de l’étape active.

> [!TIP]
> Pour des scénarios comme ceux-ci, utilisez l’ensemble d' [API client](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) pris en charge pour les flux de processus d’entreprise.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Utilisation de l’étape active pour exécuter une logique côté serveur

Il peut y avoir des cas où l’automatisation basée sur le processus d’entreprise doit être effectuée côté serveur. Par exemple :

-   Envoyer un e-mail à un utilisateur si l’étape de **qualification** du **processus de vente** est active pendant plus de 15 jours.

-   Créer automatiquement un ensemble d’activités en rapport avec l’étape active du **processus d’opportunité de vente** à chaque fois qu’il change.

-   Terminez automatiquement le **processus d’opportunité de vente** lorsque l’activité appel téléphonique pour la clôture se termine.

> [!TIP]
> Utilisez les flux de travail Common Data Service classiques ou les flux que vous définissez sur l’entité pour le flux du processus d’entreprise.
> 

Pour créer un flux de travail de Common Data Service classique qui crée des activités pour les révisions de solutions internes et pour le suivi du client dans la phase **proposer** du **processus de vente d’opportunités**:

1. Créez-le sur l’entité de **processus opportunité Sales** et définissez-le pour qu’il s’exécute chaque fois que le champ **étape active** de l’entité change. 
1. Définissez une condition pour vérifier si le champ d' **étape active** est **proposer**. 
1. Créez un enregistrement de rendez-vous et d’appel téléphonique pour la révision interne de la solution et l’appel client pour passer en revue la solution, respectivement.

   ![fermer le suivi de l’étape](media/best-practices-entity-attributes/close-stage-followup.png)
