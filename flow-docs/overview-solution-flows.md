---
title: Vue d’ensemble des flux sensibles à la solution | Microsoft Docs
description: Découvrez les avantages de la création de flux dans les solutions.
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
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548557"
---
# <a name="overview"></a>Vue
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Lorsque vous hébergez vos flux dans une [solution](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), ils deviennent portables, ce qui permet de les déplacer facilement et de tous leurs composants d’un environnement à un autre. Un cas d’utilisation classique est qu’un éditeur de logiciels indépendant (ISV) développe des flux dans un environnement de bac à sable (sandbox), puis déplace ces flux vers un environnement de test. Après le test, l’ISV déplace ensuite les flux vers un environnement de production pour les clients qui achètent ces flux. Ce processus est beaucoup plus facile lorsque vous créez vos flux dans des solutions, puis déplacez les solutions et leur contenu.

Les flux que vous créez à l’intérieur d’une solution sont appelés flux sensibles à la *solution* . Vous pouvez ajouter plusieurs flux dans une solution unique.

> [!NOTE] 
> Vous ne pouvez pas déplacer des flux non sensibles à la solution (flux non créés dans une solution) dans une solution.

## <a name="prerequisites"></a>Conditions préalables

Vous devez disposer des composants suivants pour créer des solutions et des flux sensibles à la solution :

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Un environnement avec la version 9.1.0.267 ou ultérieure.

  Pour vérifier votre version, accédez à [Microsoft Flow Centre d’administration](https://admin.flow.microsoft.com), sélectionnez **environnements**, sélectionnez l’environnement qui vous intéresse, puis sélectionnez l’onglet **Détails** .

## <a name="create-a-solution"></a>Créer une solution

Pour créer une solution, procédez comme suit :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **solutions** dans la barre de navigation.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Sélectionnez **+ nouvelle solution**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Fournissez toutes les informations requises pour votre nouvelle solution, notamment le **nom complet**, le serveur de **publication**, la **version**et le **nom**. Il est également judicieux de fournir une description de votre solution.

   ![](./media/overview-solution-flows/new-solution.png)

1. Sélectionnez **enregistrer et fermer** dans le menu en haut.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Votre nouvelle solution peut apparaître comme cette image :

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Sélectionnez **solutions** pour actualiser la liste des solutions si votre nouvelle solution n’apparaît pas.

## <a name="learn-more"></a>Pour en savoir plus

- [Créer un fluide dans une solution](./create-flow-solution.md)
- [Exporter une solution](./export-flow-solution.md)
- [Importer une solution](./import-flow-solution.md)
- [Modifier un Flow sensible à la solution](./edit-solution-aware-flow.md)
- [Supprimer un Flow sensible à la solution](./remove-solution-aware-flow.md)
