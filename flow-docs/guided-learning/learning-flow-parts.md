---
title: "Principaux composants de Microsoft Flow | Microsoft Docs"
description: "Découvrez les différentes parties de Microsoft Flow et leur interaction. Créez des flux entièrement ou à partir de modèles."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 9U8jMRO-Jv0
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 6a7fe2d56c7bc3b2253b675ce26f3f29042a7a71
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="building-blocks-of-microsoft-flow"></a>Principaux composants de Microsoft Flow
Maintenant que vous connaissez les principes de base relatifs à Microsoft Flow, suivez **une visite guidée de Microsoft Flow**. Nous examinerons rapidement comment créer des flux entièrement ou à partir de modèles.

## <a name="check-out-the-templates"></a>Consulter les modèles
À l’adresse flow.microsoft.com, si vous cliquez sur le lien **Modèles** en haut de la page, plusieurs modèles sont disponibles. Vous pouvez les utiliser immédiatement avec vos services web. Explorez ces applications pour **avoir une idée de ce qui est possible** et de la manière dont Microsoft Flow peut vous aider dans votre entreprise.

![Modèles Flow](./media/learning-flow-parts/template-list.png)

Chaque modèle de flux est conçu dans un but spécifique, par exemple recevoir des notifications lorsqu’un problème survient, copier un fichier entre différents services ou assurer le suivi des approbations SharePoint. Ces modèles sont **prêts à être utilisés**.  Vous devez seulement **les configurer** pour ajouter des flux à votre compte. Pour cela, cliquez sur **Utiliser ce modèle**, connectez-vous aux services requis, puis complétez les écrans ci-dessous.  Par exemple, voici un flux créé à partir d’un modèle pour envoyer des notifications par courrier électronique lorsqu’une liste SharePoint est modifiée. 

![Exemple de modèle de flux](./media/learning-flow-parts/example-template.png)

Il existe des centaines de modèles disponibles dans **Microsoft Flow pour le web** ou **Microsoft Flow pour les appareils mobiles**.

![Flux web et mobile](./media/learning-flow-parts/flow-web-mobile.png)

## <a name="create-a-flow-from-scratch"></a>Créer entièrement un flux
Vous venez de voir comment créer un flux à l’aide d’un modèle, mais que se passe-t-il si aucun modèle approprié ne convient à la tâche que vous souhaitez automatiser ? Vous pouvez **créer entièrement un flux**.  Lorsque vous créez un flux à partir de zéro, vous démarrez à partir d’un canevas vide et ajoutez des **services, déclencheurs et actions** pour créer votre flux.  

![Flux vide](./media/learning-flow-parts/flow-from-blank.png)

## <a name="building-blocks-of-a-flow"></a>Principaux composants d’un flux
Vos flux créés entièrement ou à partir d’un modèle contiennent des **composants principaux** qui fonctionnent ensemble à certains égards, comme un organigramme.

* Les **services** sont les sources et destinations de données d’un flux.
* Les **déclencheurs** sont des événements qui démarrent un flux.
* Les **actions** sont des tâches exécutées par le flux.
* Les **conditions** permettent la création de branches if/then logiques dans un flux.
* Les **boucles** servent à itérer sur des actions plusieurs fois.

### <a name="services"></a>Services
Microsoft Flow peut se connecter à de nombreux **applications et services** différents.  **Twitter**, **Github**, **Wunderlist**, **Office 365** et **Google Docs** sont des exemples de service.  Il s’agit des **sources** qui fournissent des données à Microsoft Flow, mais ils servent également de **destinations** pour le travail effectué par Microsoft Flow.  Vous pouvez afficher la liste complète des services en cliquant sur le lien **Services** en haut de la page **flow.microsoft.com**.

![Connecteurs de flux](./media/learning-flow-parts/flow-connectors.png)

### <a name="triggers"></a>Déclencheurs
Chaque flux commence par un **déclencheur**.  Il existe de nombreux types de déclencheur.  Certains d’entre eux sont des événements dans vos services web connectés, par exemple **l’envoi d’un tweet par un utilisateur particulier** ou **l’enregistrement d’un fichier dans votre compte Dropbox**.  D’autres déclencheurs sont intégrés, par exemple l’**exécution d’un flux selon une planification périodique** ou l’**exécution d’un flux en réponse à une requête web**.  Enfin, il existe des déclencheurs manuels, tels que le lancement d’un flux en cliquant sur un **bouton dans Microsoft Flow ou Microsoft PowerApps**.  Les déclencheurs transmettent souvent **des informations sur l’événement qui s’est produit** à des actions de votre flux.

![Déclencheurs de flux](./media/learning-flow-parts/flow-triggers.png)  

### <a name="actions"></a>Actions
Une **action** représente ce que vous souhaitez **qu’il se passe** après le déclenchement du flux.  Il peut s’agir d’une **notification**, de la **copie de données ou de fichiers** d’une source vers une destination, ou d’autres actions, telles que **la publication sur des réseaux sociaux** ou **le report pendant une certaine période**.  Vous pouvez également utiliser des actions pour **récupérer des données à partir d’un service** afin de les utiliser avec d’autres actions.

![Actions de flux](./media/learning-flow-parts/flow-actions.png) 

### <a name="conditions"></a>Conditions
Les **conditions** permettent d’ajouter des décisions à votre flux.  Lorsqu’une condition est évaluée, le flux crée une branche **Oui** et une branche **Non**.   Par exemple, si vous souhaitez copier les photos de vacances que vous avez publiées dans **Dropbox** vers **OneDrive**, vous pouvez créer une condition après un déclencheur de **nouveau fichier Dropbox** afin de vérifier si le nom de fichier contient le mot *vacances* et, si oui, de copier le fichier vers **OneDrive**, ou dans le cas contraire de ne rien faire.

![Condition de flux](./media/learning-flow-parts/flow-condition.png) 

### <a name="loops"></a>Boucles
Les **boucles** vous permettent d’exécuter une action plusieurs fois, par exemple lorsqu’une action doit se produire à plusieurs reprises ou une fois par élément dans une collection d’éléments.

## <a name="next-lesson"></a>Leçon suivante
Dans cette rubrique, nous avons présenté Microsoft Flow.  Nous avons parcouru les **modèles** et nous avons vu comment **créer entièrement un flux**.  Vous créez des flux en vous connectant à des applications et services, des **déclencheurs** pour lancer le flux, des **actions** pour que quelque chose se produise dans le flux, des **conditions** pour prendre des décisions et des **boucles** pour effectuer une itération dans un flux.  **Pour découvrir comment utiliser Microsoft Flow, le plus simple est de démarrer avec un modèle** et de vous connecter aux applications et services que vous utilisez déjà. 

Nous allons maintenant passer en revue ce que nous avons appris jusqu’à présent dans cette formation guidée.

