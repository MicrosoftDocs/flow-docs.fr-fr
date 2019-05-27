---
title: Créer des flux basés sur une solution | Microsoft Docs
description: Découvrez comment créer des flux basés sur une solution.
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
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456616"
---
# <a name="create-a-flow-in-a-solution"></a>Créer un flux dans une solution

Les flux créés dans une solution sont appelés flux *basés sur une solution*. Effectuez les étapes suivantes pour créer un flux basé sur une solution.

## <a name="prerequisites"></a>Prérequis

Vous devez avoir au moins une solution existante pour pouvoir créer un flux basé sur une solution.

## <a name="create-the-flow"></a>Créer le flux 

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **Solutions** à partir de la barre de navigation.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Sélectionnez la solution dans laquelle vous allez créer le flux.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Sélectionnez **+ Nouveau**, puis sélectionnez **Flux**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow s’ouvre.

1. Utilisez les connecteurs et déclencheurs disponibles pour créer votre flux.

   Dans cet exemple, nous allons créer un flux simple qui envoie une notification quand un e-mail arrive dans votre boîte de réception.
1. Recherchez et sélectionnez **Office 365 Outlook**.
1. Sélectionnez le déclencheur **À la réception d’un e-mail**.
1. Sélectionnez **+ Nouvelle étape**.
1. Sélectionnez l’action **M’envoyer une notification mobile**.
1. Ajoutez le jeton dynamique **Objet** au champ **Texte** dans la zone **M’envoyer une notification mobile**.
1. Nommez le nouveau flux, puis enregistrez-le.

   Votre flux doit ressembler à ceci :

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Sélectionnez **Solutions** pour voir votre flux dans la solution :

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>En savoir plus

* [Créer une solution](./overview-solution-flows.md)
* [Exporter une solution](./export-flow-solution.md)
* [Importer une solution](./import-flow-solution.md)
* [Modifier un flux basé sur une solution](./edit-solution-aware-flow.md)
* [Supprimer un flux basé sur une solution](./remove-solution-aware-flow.md)
