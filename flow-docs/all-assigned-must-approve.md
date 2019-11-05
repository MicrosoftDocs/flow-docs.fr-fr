---
title: Créer un workflow d’approbation nécessitant l’approbation de tout le monde | Microsoft Docs
description: Créez un workflow d’approbation nécessitant que tout le monde approuve ou qu’une personne rejette une demande.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 191792c356dc6b5e3a285a16050a306d4e6039f2
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545202"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Créer un workflow d’approbation nécessitant l’approbation de tout le monde
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cette procédure pas à pas vous montre comment créer un flux de travail d’approbation qui exige que tout le monde (tous les approbateurs affectés) accepte une demande de congés à approuver, mais que tout approbateur puisse rejeter l’intégralité de la requête.

Ce type de flux de travail d’approbation est utile au sein d’une organisation qui requiert le responsable d’une personne et le responsable du responsable, pour accepter les demandes de congés pour qu’elles soient approuvées. Toutefois, l’un des gestionnaires peut refuser la demande sans l’entrée de l’autre personne.

> [!NOTE]
> Bien que cette procédure pas à pas met en évidence un scénario d’approbation des vacances, vous pouvez utiliser ce type de workflow d’approbation dans toutes les situations où plusieurs approbateurs sont requis pour approuver une demande.
>
>

## <a name="prerequisites"></a>Conditions préalables

* Accès aux utilisateurs [Microsoft Flow](https://flow.microsoft.com), Microsoft Office Outlook 365 et Microsoft Office 365.
* [Liste](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194)SharePoint.

    Cette procédure pas à pas suppose que vous avez créé une liste SharePoint utilisée pour demander des congés. Consultez la procédure pas à pas relative aux [approbations parallèles](parallel-modern-approvals.md) pour obtenir un exemple détaillé qui vous explique ce à quoi votre liste SharePoint peut ressembler.
* Vous êtes familiarisé avec les principes de base de la création de flux.

    Vous pouvez voir comment ajouter des [actions, des déclencheurs](multi-step-logic-flow.md#add-another-action)et des [conditions](add-condition.md). Les étapes suivantes supposent que vous savez comment effectuer ces actions.

> [!NOTE]
> Bien que nous utilisons SharePoint et Office 365 Outlook dans cette procédure pas à pas, vous pouvez utiliser d’autres services tels que Zendesk, Salesforce, Gmail ou l’un des plus de [200 services](https://flow.microsoft.com/connectors/) pris en charge par Microsoft Flow.
>
>

## <a name="create-the-flow"></a>Créer le Flow

> [!NOTE]
> Si vous n’avez pas créé de connexion à SharePoint ou Office 365 précédemment, suivez les instructions lorsque vous êtes invité à vous connecter.
>
>

Cette procédure pas à pas utilise des jetons. Pour afficher la liste des jetons, appuyez ou cliquez sur un contrôle d’entrée, puis recherchez le jeton dans la liste de **contenu dynamique** qui s’ouvre.

Connectez-vous [Microsoft Flow](https://flow.microsoft.com), puis procédez comme suit pour créer votre fluide.

1. Sélectionnez **mes flux** > **créer à partir d’un espace**, en haut à droite de l’écran.
1. Ajoutez le déclencheur **SharePoint-lors de la création ou de la modification d’un élément** .
1. Entrez l' **adresse du site** SharePoint qui héberge votre liste de demandes de congés, puis sélectionnez le **nom**de la liste de listes.
1. Ajoutez l’action **utilisateurs Office 365-accéder au gestionnaire v2** , sélectionnez la zone **utilisateur (UPN)** , puis ajoutez le jeton **créé par e-mail** à ce dernier.

    Le jeton **créé par e-mail** se trouve sous la catégorie lors de la **création ou de la modification d’un élément** de la liste de **contenu dynamique** . Ce jeton fournit dynamiquement un accès aux données relatives au responsable de la personne qui a créé l’élément dans SharePoint.

1. Ajoutez une autre action **Office 365 Users-obtient le gestionnaire v2** , puis ajoutez le jeton de **messagerie** à la zone **utilisateur (UPN)** .

    Le jeton de **messagerie** se trouve sous la catégorie **accéder au gestionnaire v2 2** de la liste de **contenu dynamique** . Ce jeton fournit dynamiquement l’accès à l’adresse de messagerie du responsable du responsable.

    Vous pouvez également renommer la carte d' **extraction v2 2** en une valeur explicite comme « ignorer le gestionnaire de niveau ».
1. Ajoutez l’action **Démarrer une approbation** , puis sélectionnez **tout le monde dans la liste attribué** de la liste type d' **approbation** .

   > [!IMPORTANT]
   > Si un approbateur rejette, la demande d’approbation est considérée comme rejetée pour tous les approbateurs.
   >
   >
1. Utilisez le tableau suivant comme guide pour terminer la carte **Démarrer une approbation** .

   | case | Descriptive |
   | --- | --- |
   |  Type d’approbation |Utilisez n’importe qui **dans la liste affectée** pour indiquer que l’un des approbateurs peut approuver ou rejeter la demande. </p>Utilisez **tout le monde de la liste affectée** pour indiquer qu’une demande est approuvée uniquement si tout le monde l’accepte, et que la demande est refusée si une seule personne la rejette. |
   |  Bonhomme |Titre de la demande d’approbation. |
   |  Affecté à |Adresses de messagerie des approbateurs. |
   |  Plus |Toutes les informations supplémentaires que vous souhaitez envoyer aux approbateurs figurant dans le champ **affecté à** . |
   |  Lien vers l’élément |URL de l’élément d’approbation. Dans cet exemple, il s’agit d’un lien vers l’élément dans SharePoint. |
   |  Description du lien vers l’élément |Description textuelle pour le lien de l' **élément**. |

   > [!TIP]
   > L’action **Démarrer une approbation** fournit plusieurs jetons, y compris le **Résumé**des **réponses** et des réponses. Utilisez ces jetons dans votre Flow pour fournir des rapports enrichis des résultats à partir de l’exécution d’un workflow de demande d’approbation.
   >
   >

    La carte **Démarrer une approbation** est un modèle pour la demande d’approbation envoyée aux approbateurs. Configurez-le de façon utile pour votre organisation. Voici un exemple.

    ![démarrer une approbation](media/all-assigned-must-approve/start-an-approval-card.png)

1. Ajoutez l’action **Office 365 Outlook-envoyer un message électronique** , puis configurez-la pour envoyer un e-mail avec les résultats de la demande.

    Voici un exemple de ce à quoi peut ressembler la carte **Envoyer un e-mail** .

    ![Envoyer un e-mail](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Toute action qui suit l’action **Démarrer une approbation** s’exécute en fonction de votre sélection dans la liste **type d’approbation** de la carte **Démarrer une approbation** . Le tableau suivant répertorie le comportement en fonction de votre sélection.
>
>

| Type d’approbation | Comportement |
| --- | --- |
| N’importe qui dans la liste affectée |Les actions qui suivent l’action **Démarrer une approbation** s’exécutent après la décision de l’un des approbateurs. |
| Tout le monde de la liste affectée |Les actions qui suivent l’action **Démarrer une approbation** s’exécutent après que l’approbateur a refusé ou que tout le monde approuve la demande. |

En haut de l’écran, entrez un nom pour votre Flow dans la zone **nom** du cours, puis sélectionnez **créer un Flow** pour l’enregistrer.

Félicitations, votre Flow est terminé. Si vous avez suivi le, votre Flow ressemble à cette image.

![image de Flow globale](media/all-assigned-must-approve/overall-flow.png)

Désormais, chaque fois qu’un élément est ajouté à votre liste SharePoint, ou si un élément est modifié, votre workflow déclenche et envoie des demandes d’approbation à tous les approbateurs répertoriés dans la zone **affecté à** de la carte **Démarrer une approbation** . Votre Flow envoie des demandes d’approbation via l’application mobile Microsoft Flow et par courrier électronique. La personne qui crée l’élément dans SharePoint reçoit un message électronique qui résume les résultats, indiquant clairement si la demande a été approuvée ou rejetée.

Voici un exemple de demande d’approbation envoyée à chaque approbateur.

![demande d’approbation](media/all-assigned-must-approve/approval-request.png)

Voici un exemple de ce à quoi peut ressembler une réponse et un résumé de réponse après l’exécution de votre workflow.

![jetons de réponse](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>En savoir plus sur les approbations

* [Approbations modernes d’un seul approbateur](modern-approvals.md)
* [Approbations modernes séquentielles](sequential-modern-approvals.md)
* [Approbations modernes parallèles](parallel-modern-approvals.md)
* [Approbations et Microsoft Common Data Service](common-data-model-approve.md)
* [Approuver les demandes en déplacement](mobile-approvals.md)
