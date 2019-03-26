---
title: Vue d’ensemble des flux basés sur une solution | Microsoft Docs
description: Découvrez les avantages de créer des flux dans les solutions.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8b0e64317b868dc32ede173329fa2f88ed53de76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352990"
---
# <a name="overview"></a>Présentation

Les flux hébergés dans une [solution](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview) offrent l’avantage d’être portables, ce qui vous permet de déplacer facilement les flux et tous leurs composants d’un environnement à un autre. Voici un cas d’usage courant pour un éditeur de logiciels indépendant (ISV) : l’éditeur développe les flux dans un environnement bac à sable, puis les déplace vers un environnement de test. Après le test, il doit déplacer les flux vers un environnement de production pour les mettre à disposition des clients qui les achètent. Ce processus est beaucoup plus simple quand vous créez les flux dans des solutions, puis que vous déplacez ces solutions et leur contenu.

Les flux créés au sein d’une solution sont appelés flux *basés sur une solution*. Vous pouvez ajouter plusieurs flux dans la même solution.

> [!NOTE] 
> Vous ne pouvez pas déplacer des flux non basés sur une solution (flux qui n’ont pas été créés dans une solution) dans une solution.

## <a name="prerequisites"></a>Prérequis

Pour créer des solutions et des flux basés sur une solution, vous avez besoin des composants suivants :

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Environnement avec la version 9.1.0.267 ou ultérieure.

  Pour vérifier votre version, accédez au [Centre d’administration de Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **Environnements**, sélectionnez l’environnement souhaité, puis sélectionnez l’onglet **Détails**.

## <a name="create-a-solution"></a>Créer une solution

Pour créer une solution, effectuez les étapes suivantes :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **Solutions** à partir de la barre de navigation.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Sélectionnez **+ Nouvelle solution**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Entrez toutes les informations demandées pour la nouvelle solution dans les champs correspondants, notamment **Nom complet**, **Éditeur**, **Version** et **Nom**. Il est également conseillé d’entrer une description pour votre solution.

   ![](./media/overview-solution-flows/new-solution.png)

1. Sélectionnez **Enregistrer et fermer** dans le menu en haut.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   La nouvelle solution doit s’afficher comme dans cette image :

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Sélectionnez **Solutions** pour actualiser la liste des solutions si votre nouvelle solution n’apparaît pas.

## <a name="learn-more"></a>En savoir plus

- [Créer un flux dans une solution](./create-flow-solution.md)
- [Exporter une solution](./export-flow-solution.md)
- [Importer une solution](./import-flow-solution.md)
- [Modifier un flux basé sur une solution](./edit-solution-aware-flow.md)
- [Supprimer un flux basé sur une solution](./remove-solution-aware-flow.md)
