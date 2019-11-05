---
title: Créer des flux d’approbation avec des réponses personnalisées | Microsoft Docs
description: Créer des flux d’approbation avec des réponses personnalisées.
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547220"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Créer des options de réponse personnalisées pour les flux d’approbation
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Supposons que vous souhaitiez envoyer une demande d’approbation chaque fois qu’un employé charge un état de dépenses dans SharePoint, puis autoriser l’approbateur à répondre avec l’une des trois options suivantes : accepter, demander plus d’informations ou rejeter.


## <a name="prerequisites"></a>Conditions préalables

- Un compte Microsoft Flow.
- Liste SharePoint permettant aux employés d’entrer leurs notes de frais.

## <a name="create-approval-flow"></a>Créer un workflow d’approbation
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **mes flux** dans la barre de navigation de gauche.
1. Sélectionnez **nouveau** > **créer à partir d’un espace**.

    ![Créer à partir d’une option vide](media/create-approval-response-options/create-approval-response-options.png)

1. Dans l’écran qui s’ouvre, sélectionnez **créer à partir d’un espace**. 

    ![Sélectionnez créer à partir d’un espace](media/create-approval-response-options/create-from-blank.png)

1. Recherchez **SharePoint** , puis sélectionnez le **moment où un élément est créé** à partir de la liste des déclencheurs. 

1. Fournissez l' **adresse du site** SharePoint et le nom de la **liste**. 

1. Sélectionnez **nouvelle étape**, recherchez **approbation**, puis sélectionnez **Démarrer et attendre une approbation (v2)** .

1. Sur la carte **Démarrer et attendre une approbation (v2)** , sélectionnez la liste **type d’approbation** .

    ![Type d’approbation](media/create-approval-response-options/select-approval-type.png)

1. Sélectionner **des réponses personnalisées-attendre une réponse (Premium)** .

    ![Réponses personnalisées](media/create-approval-response-options/select-custom-responses.png)

    Ensuite, vous allez créer les réponses personnalisées qui seront utilisées par vos approbateurs lorsqu’ils répondront à une demande d’approbation pour les frais d’un employé.


1. Dans la zone **options de réponse, élément-1** , entrez **accepter** , puis sélectionnez **Ajouter un nouvel élément**. 

    ![Réponse personnalisée 1](media/create-approval-response-options/enter-response-1.png)

1. Dans la zone **options de réponse, élément-2** , entrez **rejeter** , puis sélectionnez **Ajouter un nouvel élément**.

    ![Réponse personnalisée 2](media/create-approval-response-options/enter-response-2.png)

1. Dans la zone **options de réponse, élément-3** , entrez **des informations supplémentaires**.

    ![Réponse personnalisée 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Entrez un **titre**, **affecté à** (e-mail pour l’approbateur) et **Détails** (détails à faire figurer dans la demande d’approbation).

    Voici un exemple de ce que vous pouvez inclure pour votre organisation.

    ![Détails des réponses personnalisées](media/create-approval-response-options/enter-title-assigned-to-details.png)


Maintenant que vous avez créé vos réponses personnalisées, vous souhaiterez peut-être effectuer différentes opérations dans votre workflow, en fonction de la réponse de l’approbateur.


## <a name="use-approval-responses"></a>Utiliser les réponses d’approbation 

Si la réponse à la demande est **acceptée**, vous souhaiterez peut-être envoyer un e-mail au service comptabilité, lui demandant de rembourser l’employé pour la dépense. 

Si la réponse est **rejetée**, vous souhaiterez peut-être envoyer un e-mail à l’employé, en lui indiquant que la demande a été rejetée.

Enfin, si la réponse de l’approbateur a **besoin d’informations supplémentaires**, vous souhaiterez peut-être envoyer un e-mail à l’employé pour demander à l’employé de fournir plus d’informations.

Pour effectuer l’une des opérations suivantes dans le Flow, ajoutez une [**condition**](add-condition.md) ou une action de **commutation** à votre Flow, puis sélectionnez le champ de **résultat** de la demande d’approbation dans le sélecteur de contenu dynamique. Veillez à confirmer si la valeur est accepter, si vous avez besoin d’informations supplémentaires ou de rejet.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Répondre aux demandes d’approbation avec une réponse personnalisée

Les approbateurs reçoivent les demandes d’approbation par courrier électronique. Les demandes sont également affichées dans le centre d’approbation sur Microsoft Flow. 

![E-mail de demande d’approbation](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Pour en savoir plus
- Créer des [flux d’approbateur uniques](modern-approvals.md)
- Créer des [flux d’approbateur séquentiels](sequential-modern-approvals.md)
