---
title: Découvrez comment créer des flux sensibles à la solution | Microsoft Docs
description: Découvrez comment créer des flux sensibles à la solution.
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
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546467"
---
# <a name="create-a-flow-in-a-solution"></a>Créer un fluide dans une solution
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les flux que vous créez dans une solution sont appelés flux sensibles à la *solution* . Procédez comme suit pour créer un fluide qui prend en compte la solution.

## <a name="prerequisites"></a>Conditions préalables

Vous devez disposer d’au moins une solution pour pouvoir créer un fluide qui prend en compte la solution.

## <a name="create-the-flow"></a>Créer le Flow 

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **solutions** dans la barre de navigation.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Sélectionnez la solution dans laquelle vous allez créer votre fluide.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Sélectionnez **+ nouveau**, puis **Flow**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow s’ouvre.

1. Utilisez les connecteurs et les déclencheurs disponibles pour créer votre Flow.

   Dans cet exemple, nous allons créer un fluide simple qui envoie une notification lorsqu’un e-mail arrive dans votre boîte de réception.
1. Recherchez, puis sélectionnez **Office 365 Outlook**.
1. Sélectionnez le déclencheur à l' **arrivée d’un nouveau message électronique** .
1. Sélectionnez **+ nouvelle étape**.
1. Sélectionnez l’action **m’envoyer une notification mobile** .
1. Ajoutez le jeton dynamique **Subject** au champ **Text** de la zone **m’envoyer une notification mobile** .
1. Donnez un nom à votre Flow, puis enregistrez le Workflow.

   Votre Flow doit se présenter comme suit :

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Sélectionnez des **solutions** pour voir votre Flow dans la solution :

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Pour en savoir plus

* [Créer une solution](./overview-solution-flows.md)
* [Exporter une solution](./export-flow-solution.md)
* [Importer une solution](./import-flow-solution.md)
* [Modifier un Flow sensible à la solution](./edit-solution-aware-flow.md)
* [Supprimer un Flow sensible à la solution](./remove-solution-aware-flow.md)
