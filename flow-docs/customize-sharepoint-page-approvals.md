---
title: Gérer les approbations de pages SharePoint avec Microsoft Flow | Microsoft Docs
description: Découvrez comment gérer les approbations de pages SharePoint avec Microsoft Flow.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547646"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gérer les approbations de pages SharePoint avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les administrateurs de site SharePoint peuvent utiliser Microsoft Flow pour exiger l’approbation des pages de site nouvelles ou mises à jour avant leur publication.

Dans cet article, vous allez apprendre à configurer votre site SharePoint pour qu’il utilise un Flow pour exiger que les modifications apportées au site soient approuvées avant leur mise en ligne.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurer SharePoint pour les approbations de pages

### <a name="prerequisites"></a>Conditions préalables 

Pour effectuer les activités de cet article, vous devez être administrateur de site SharePoint.

1. Connectez-vous à SharePoint en tant qu’administrateur de site.
1. Sélectionnez **pages** dans la barre de navigation.

    ![Sélectionner un workflow d’approbation de page](media/customize-sharepoint-page-approvals/pages.png)

1. Sélectionnez **Flow** , puis sélectionnez **configurer le workflow d’approbation de page**.
    
    ![Sélectionner un workflow d’approbation de page](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Indiquez un **nom de workflow**, au moins un nom dans la zone **approbateurs** , puis sélectionnez **créer**.
    
    ![Sélectionner un workflow d’approbation de page](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Voilà! À présent, chaque fois qu’une page est ajoutée ou modifiée, une demande d’approbation est envoyée aux **approbateurs** que vous avez listés dans le Flow.

Le flux d’approbation de page est comme n’importe quel autre flux. il est donc indiqué sous l’onglet **mes flux** .

![Sélectionner un workflow d’approbation de page](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Soumettre une page pour approbation

Maintenant que vous avez créé un workflow d’approbation de page, toute personne qui ajoute ou modifie une page doit effectuer les opérations suivantes :

 - Modifiez le site (ajoutez une nouvelle page, par exemple), puis enregistrez la modification.

     ![Envoyer la page pour approbation](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Attendez qu’une personne approuve la modification.
    
    ![Envoyer la page pour approbation](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Approuver une page

Les approbateurs reçoivent un e-mail chaque fois qu’une demande d’approbation de page est envoyée. Ils peuvent approuver les demandes directement dans l’e-mail (si leur client de messagerie prend en charge les messages actionnables) ou ouvrir la page de l’e-mail à consulter, puis approuver la page dans SharePoint.

## <a name="customize-page-approval-flows"></a>Personnaliser les flux d’approbation de page

Étant donné que les approbations de page utilisent Microsoft Flow en arrière-plan, le processus d’approbation de page est disponible pour les propriétaires de site afin de modifier et d’ajouter toute logique métier personnalisée dans le Workflow. Pour modifier le flux, le propriétaire du site peut sélectionner des **flux** , puis sélectionner **afficher vos flux** dans la bibliothèque de pages pour trouver le flux d’approbation de page.

## <a name="learn-more"></a>Pour en savoir plus

- [Workflow d’approbation de page](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurer l’approbation de la page](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
