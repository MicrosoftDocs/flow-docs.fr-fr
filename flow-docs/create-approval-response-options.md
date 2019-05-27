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
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061707"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Créer des options de réponse personnalisée pour le flux d’approbation

Supposons que vous souhaitez envoyer une demande d’approbation chaque fois qu’un employé télécharge une note de frais sur SharePoint, puis autoriser l’approbateur de répondre avec une des trois options : Accepter, vous avez besoin des informations plus ou rejeter.


## <a name="prerequisites"></a>Prérequis

- Un compte Microsoft Flow avec une licence de Plan 2 (Plan 2 est nécessaire pour utiliser des fonctionnalités premium. Approbations est une fonctionnalité premium.)
- Une liste SharePoint pour les employés à entrer leurs notes de frais.

## <a name="create-approval-flow"></a>Créer un flux d’approbation
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez **mes flux** à partir de la barre de navigation gauche.
1. Sélectionnez **New** > **créer entièrement**.

    ![Créer à partir de l’option vide](media/create-approval-response-options/create-approval-response-options.png)

1. Dans l’écran qui s’ouvre, sélectionnez **créer entièrement**. 

    ![Sélectionnez Créer entièrement](media/create-approval-response-options/create-from-blank.png)

1. Recherchez **sharepoint** , puis sélectionnez **lorsqu’un élément est créé** à partir de la liste des déclencheurs. 

1. Fournir le SharePoint **adresse du Site** et **liste nom**. 

1. Sélectionnez **nouvelle étape**, recherchez **approbation**, puis sélectionnez **Start et attendre qu’une approbation (V2)**.

1. Sur le **Start et attendre qu’une approbation (V2)** carte, sélectionnez le **type d’approbation** liste.

    ![Type d’approbation](media/create-approval-response-options/select-approval-type.png)

1. Sélectionnez **personnalisé réponses - attendre une réponse (Premium)**.

    ![Réponses personnalisées](media/create-approval-response-options/select-custom-responses.png)

    Ensuite, vous allez créer des réponses personnalisées qui utilisent le vos approbateurs quand ils répondent à une demande d’approbation d’une dépense de l’employé.


1. Dans le **réponse options élément - 1** , entrez **Accept** , puis sélectionnez **ajouter un nouvel élément**. 

    ![Réponse personnalisée 1](media/create-approval-response-options/enter-response-1.png)

1. Dans le **réponse options élément - 2** , entrez **rejeter** , puis sélectionnez **ajouter un nouvel élément**.

    ![Réponse personnalisée 2](media/create-approval-response-options/enter-response-2.png)

1. Dans le **réponse options élément - 3** , entrez **vous avez besoin des informations plus**.

    ![Réponse personnalisée 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Entrez un **titre**, **affectés à** (adresse e-mail de l’approbateur), et **détails** (les détails doivent être contenus dans la demande d’approbation).

    Voici un exemple de ce que vous pouvez inclure pour votre organisation.

    ![Détails des réponses personnalisées](media/create-approval-response-options/enter-title-assigned-to-details.png)


Maintenant que vous avez créé vos réponses personnalisées, vous souhaiterez effectuer différentes opérations dans votre flux, en fonction de la réponse de l’approbateur.


## <a name="use-approval-responses"></a>Utilisez les réponses d’approbation 

Si la réponse à la demande est **Accept**, vous pouvez souhaiter envoyer un e-mail au service de comptabilité, lui demandant de rembourser l’employé pour la dépense. 

Si la réponse est **rejeter**, vous souhaiterez peut-être envoyer un e-mail à l’employé, les informant que la demande a été rejetée.

Et enfin, si la réponse de l’approbateur est **vous avez besoin des informations plus**, vous souhaiterez peut-être envoyer un e-mail à l’employé, demandant l’employé pour fournir plus d’informations.

Pour effectuer l’une de ces éléments dans le flux, ajoutez un [ **Condition** ](add-condition.md) ou un **commutateur** action à votre flux, puis sélectionnez le **résultat** champ de l’approbation demander à partir du sélecteur de contenu dynamique. Vérifiez si la valeur est d’accepter, vous avez besoin des informations plus ou rejeter.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Répondre aux demandes d’approbation avec une réponse personnalisée

Les approbateurs reçoivent des demandes d’approbation par courrier électronique. Les demandes sont également affichés dans le centre d’approbation sur Microsoft Flow. 

![E-mail de demande d’approbation](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>En savoir plus
- Créer [unique de flux de l’approbateur](modern-approvals.md)
- Créer [approbateur séquentiel flux](sequential-modern-approvals.md)
