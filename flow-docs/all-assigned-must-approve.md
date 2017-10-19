---
title: "Créer un flux d’approbation nécessitant l’approbation de tout le monde | Microsoft Docs"
description: "Créez un flux d’approbation de demande nécessitant l’approbation de tout le monde, et entraînant le rejet de la demande en cas de refus d’une seule personne."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/22/2017
ms.author: deonhe
ms.openlocfilehash: 0e0309793cfcb45ca7ee72910803a4abc27d2f26
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Créer un flux d’approbation nécessitant l’approbation de tout le monde
Cette procédure pas à pas décrit comment créer un flux de travail d’approbation nécessitant que tout le monde (l’ensemble des approbateurs affectés) consente à une demande de congé pour que celle-ci soit approuvée, et entraînant son rejet si un seul approbateur s’y oppose.

Ce type de flux de travail d’approbation est utile au sein d’une organisation qui exige que toute demande de congé soit approuvée tant par le responsable du demandeur, que par le responsable du responsable. Chaque responsable peut refuser la demande de son côté.

## <a name="prerequisites"></a>Conditions préalables
* Accès à [Microsoft Flow](https://flow.microsoft.com), à Office 365 Outlook et à Utilisateurs d’Office 365.
* [List](https://support.office.com/en-us/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) SharePoint Online.
  
    Cette procédure pas à pas suppose que vous avez créé une liste SharePoint Online est utilisée pour les demandes de congés. Pour un exemple détaillé de liste SharePoint, voir la procédure pas à pas [Approbations parallèles](parallel-modern-approvals.md).
* Bonne maîtrise des principes fondamentaux de la création de flux.
  
    Nous vous invitons à réviser la manière d’ajouter [des actions, des déclencheurs](multi-step-logic-flow.md#add-another-action) et [des conditions](add-a-condition.md). Les étapes suivantes supposent que vous savez comment effectuer ces actions.

> [!NOTE]
> Bien que nous utilisions SharePoint Online et Office 365 Outlook dans cette procédure pas à pas, vous pouvez utiliser d’autres services, tels que Zendesk, Salesforce, Gmail, n’importe lequel des plus de [150 services](https://flow.microsoft.com/connectors/) que Microsoft Flow prend en charge.
> 
> 

## <a name="create-the-flow"></a>Créer le flux
> [!NOTE]
> Si vous n’avez pas créé de connexion à SharePoint ou à Office 365 précédemment, suivez les instructions lorsque vous êtes invité à vous connecter.
> 
> 

Cette procédure pas à pas utilise des jetons. Pour afficher la liste de jetons, appuyez ou cliquez sur n’importe quel contrôle d’entrée, puis recherchez le jeton dans la liste **Contenu dynamique** qui s’ouvre.

Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis procédez comme suit pour créer le flux.

1. Sélectionnez **Mes flux** > **Créer entièrement**.
2. Ajoutez le déclencheur **SharePoint - Lorsqu’un élément est créé ou Lorsqu’un élément existant est modifié**.
3. Entrez l’**Adresse du site** SharePoint hébergeant la liste des demandes de congés, puis sélectionnez la liste dans la zone **Nom de la liste**.
4. Ajoutez l’action **Utilisateurs d’Office 365 - Obtenir le responsable**, puis ajoutez le jeton **Créé par l’adresse électronique** à la zone **Utilisateur (UPN)**.
   
    Le jeton **Créé par l’adresse électronique** figure dans la catégorie **Lorsqu’un élément est créé ou Lorsqu’un élément existant est modifié** de la liste **Contenu dynamique**.
5. Ajoutez l’action **Utilisateurs d’Office 365 - Obtenir le responsable**, puis ajoutez le jeton **E-mail** à la zone **Utilisateur (UPN)**.
   
    Le jeton **E-mail** figure dans la catégorie **Obtenir le responsable** de la liste **Contenu dynamique**.
   
    Vous pouvez également renommer la carte **Obtenir le responsable 2** en lui attribuant un nom descriptif tel que « Responsable de niveau supérieur ».
6. Ajoutez l’action **Démarrer une approbation**, puis, dans la liste **Type d’approbation**, sélectionnez **Tout le monde dans la liste affectée**.
   
   > [!IMPORTANT]
   > En cas de refus d’un seul approbateur, la demande d’approbation est considérée comme rejetée par tous les approbateurs.
   > 
   > 
7. Utilisez le tableau suivant comme guide pour remplir la carte **Démarrer une approbation**.
   
   | Champ | Description |
   | --- | --- |
   |  Type d’approbation |Utilisez **N’importe qui dans la liste affectée** pour indiquer que tout approbateur peut approuver ou rejeter la demande. </p>Utilisez **Tout le monde dans la liste affectée** pour indiquer qu’une demande n’est approuvée que si tous les approbateurs l’acceptent, et qu’elle est refusée si une seule personne la rejette. |
   |  Titre |Titre de la demande d’approbation. |
   |  Affectée à |Adresses de messagerie des approbateurs. |
   |  Détails |Toute information supplémentaire à envoyer aux approbateurs répertoriés dans le champ **Affectée à**. |
   |  Lien vers l’élément |URL de l’élément de l’approbation. Dans cet exemple, il s’agit d’un lien vers l’élément dans SharePoint. |
   |  Description du lien vers l’élément |Texte décrivant le **Lien vers l’élément**. |
   
   > [!TIP]
   > L’action **Démarrer une approbation** fournit plusieurs jetons, dont **Réponse** et **Résumé de la réponse**. Utilisez ces jetons dans votre flux pour produire des rapports détaillés des résultats de l’exécution d’un flux de demande d’approbation.
   > 
   > 
   
    La carte **Démarrer une approbation** est un modèle de demande d’approbation à envoyer aux approbateurs. Configurez-la d’une manière utile pour votre organisation. Voici un exemple.
   
    ![démarrer une approbation](media/all-assigned-must-approve/start-an-approval-card.png)
8. Ajoutez l’action **Office 365 Outlook - Envoyer un courrier**, puis configurez-la pour envoyer un e-mail contenant les résultats de la demande.
   
    Voici un exemple de ce à quoi peut ressembler la carte **Envoyer un courrier**.
   
    ![envoyer un courrier](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Toute action postérieure à l’action **Démarrer une approbation** s’exécute en fonction de la sélection que vous avez opérée dans la liste **Type d’approbation** sur la carte **Démarrer une approbation**. Le tableau suivant indique le comportement en fonction de votre sélection.
> 
> 

| Type d’approbation | Comportement |
| --- | --- |
| N’importe qui dans la liste affectée |Les actions postérieures à l’action **Démarrer une approbation** s’exécutent après la décision de n’importe lequel des approbateurs. |
| Tout le monde dans la liste affectée |Les actions postérieures à l’action **Démarrer une approbation** s’exécutent après qu’un approbateur a décliné ou que tous les approbateurs ont approuvé la demandé. |

En haut de l’écran, dans le champ **Nom de flux**, entrez un nom pour votre flux, puis sélectionnez **Créer un flux** pour enregistrer celui-ci.

Félicitations, votre flux est terminé. Si vous avez suivi la procédure, votre flux ressemble à cette image.

![image de flux global](media/all-assigned-must-approve/overall-flow.png)

Désormais, chaque fois qu’un élément de votre liste SharePoint change, votre flux est déclenché et envoie des demandes d’approbation à tous les approbateurs répertoriés dans la zone **Affectée à** de la carte **Démarrer une approbation**. Votre flux envoie des demandes d’approbation via l’application mobile Microsoft Flow et par e-mail. La personne qui crée l’élément dans SharePoint reçoit un e-mail résumant les résultats, et indiquant clairement si la demande a été approuvée ou rejetée.

Voici un exemple de demande d’approbation envoyée à chaque approbateur.

![demande d’approbation](media/all-assigned-must-approve/approval-request.png)

Voici un exemple de réponse et de résumé de la réponse après l’exécution du flux.

![jetons de réponse](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>En savoir plus sur les approbations
* [Approbations modernes d’un seul approbateur](modern-approvals.md)
* [Approbations modernes séquentielles](sequential-modern-approvals.md)
* [Approbations modernes parallèles](sequential-modern-approvals.md)
