---
title: Gérer les approbations de page de SharePoint avec Microsoft Flow | Microsoft Docs
description: Découvrez comment gérer les approbations de page de SharePoint avec Microsoft Flow...
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
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061339"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gérer les approbations de page de SharePoint avec Microsoft Flow

Administrateurs du site SharePoint peuvent utiliser Microsoft Flow pour exiger des pages de site nouveau ou mis à jour doivent être approuvées avant d’être publiées.

Dans cet article, vous allez apprendre à configurer votre site SharePoint pour utiliser un flux pour exiger des modifications du site doivent être approuvées avant leur mise en service.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurer SharePoint pour les approbations de la page

### <a name="prerequisites"></a>Prérequis 

Vous devez être un administrateur de site SharePoint pour effectuer les activités dans cet article.

1. Connexion à SharePoint en tant qu’un administrateur de site.
1. Sélectionnez **Pages** à partir de la barre de navigation.

    ![Sélectionnez le flux d’approbation de page](media/customize-sharepoint-page-approvals/pages.png)

1. Sélectionnez **flux** , puis sélectionnez **configurer des flux d’approbation de page**.
    
    ![Sélectionnez le flux d’approbation de page](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Fournir un **le nom du flux**, au moins un nom dans la **approbateurs** zone, puis sélectionnez **créer**.
    
    ![Sélectionnez le flux d’approbation de page](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Voilà ! Chaque fois une page est ajoutée ou modifiée, une demande d’approbation accède à présent à la **approbateurs** vous répertorié dans le flux.

Le flux d’approbation de page s’apparente à un autre flux, donc il est répertorié dans le **mes flux** onglet.

![Sélectionnez le flux d’approbation de page](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Soumettre une page pour approbation

Maintenant que vous avez créé un flux d’approbation de page, toute personne qui ajoute ou modifie une page devrez effectuer les opérations suivantes :

 - Apportez une modification au site (ajouter une nouvelle page, par exemple), puis enregistrez la modification.

     ![Envoyer la page pour approbation](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Attendez que quelqu'un approuver la modification.
    
    ![Envoyer la page pour approbation](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Approuver une page

Les approbateurs reçoivent un e-mail chaque fois qu’une demande d’approbation de page. Ils peuvent approuver les demandes directement dans le courrier électronique (si leur client de messagerie prend en charge les messages actionnables) ou ouvrez la page à partir de l’e-mail, et puis approuve la page dans SharePoint.

## <a name="customize-page-approval-flows"></a>Personnaliser le flux d’approbation de page

Étant donné que les approbations de la page utilisent Microsoft Flow dans les coulisses, le flux d’approbation de page est disponible pour les propriétaires de site modifier et ajouter une logique métier personnalisée dans le flux. Pour modifier le flux, le propriétaire de site peut sélectionner **flux** , puis sélectionnez **consultez vos flux** dans la bibliothèque de pages pour rechercher le flux d’approbation de page.

## <a name="learn-more"></a>En savoir plus

- [Flux d’approbation de page](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurer l’approbation de page](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
