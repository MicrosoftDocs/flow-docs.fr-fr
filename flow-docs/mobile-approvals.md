---
title: Approuver des demandes sur un appareil mobile | Microsoft Docs
description: Utilisez un appareil mobile pour approuver les demandes créées dans Microsoft Flow.
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548670"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Approuver des demandes sur votre appareil mobile à l’aide de Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Si un workflow vous identifie en tant qu’approbateur et que vous avez installé l’application mobile pour Microsoft Flow, vous recevez une notification push chaque fois que votre approbation est demandée.

Cet article vous guide tout au long des scénarios courants que vous êtes susceptible de rencontrer lorsque vous gérez des demandes d’approbation dans l’application mobile pour Microsoft Flow.

> [!NOTE]
> Les images de cette rubrique proviennent d’un appareil Android. Toutefois, l’expérience sur iOS est similaire.
> 
> 

## <a name="prerequisites"></a>Conditions préalables
Pour effectuer cette procédure pas à pas, vous avez besoin des éléments suivants :

* Un appareil [Android](https://aka.ms/flowmobiledocsandroid) ou [iOS](https://aka.ms/flowmobiledocsios) exécutant l’application mobile pour Microsoft Flow.
* À désigner en tant qu’approbateur dans un workflow d’approbation.
* Demandes en attente d’approbation.

## <a name="view-pending-requests"></a>Afficher les demandes en attente
1. Ouvrez l’application mobile pour Microsoft Flow.
   
    ![démarrer l’application mobile](./media/mobile-approvals/open-app.png)
2. Sélectionnez **approbations** dans l’angle supérieur droit.
   
    ![sélectionner les approbations](./media/mobile-approvals/select-approvals.png)
3. Afficher toutes les approbations en attente :
   
    ![afficher les demandes d’approbation en attente](./media/mobile-approvals/show-pending-approval-requests.png)

Si vous n’avez pas de demandes d’approbation en attente, créez un [Workflow d’approbation](modern-approvals.md), définissez-vous comme approbateur, puis déclenchez le Flow. Les demandes d’approbation apparaissent dans le centre d’approbation quelques secondes après que le workflow a été déclenché et envoie une demande d’approbation.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Approuver les demandes et laisser un commentaire facultatif
1. Si vous ne l’avez pas fait, suivez les étapes ci-dessus pour [afficher les demandes en attente](mobile-approvals.md#view-pending-requests).
2. Sélectionnez **approuver** dans la demande que vous souhaitez approuver.
   
    ![Sélectionnez approuver](./media/mobile-approvals/select-approve.png)
3. (Facultatif) sélectionnez **Ajouter un commentaire (facultatif)** .
   
    ![sélectionnez Ajouter un commentaire](./media/mobile-approvals/select-add-comment.png)
   
    Entrez un commentaire sur l’écran **Ajouter un commentaire** .
   
    ![Entrez votre commentaire](./media/mobile-approvals/enter-comment-for-approval.png)
4. Sélectionnez **confirmer** dans l’angle supérieur droit.
   
    ![Vérifiez que vous avez terminé](./media/mobile-approvals/tap-confirm-button.png)
   
    L’écran de réussite s’affiche une fois que le Flow enregistre votre décision.
   
    ![écran de réussite](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rejeter les demandes et conserver un commentaire facultatif
Suivez les [étapes pour approuver une demande](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), mais sélectionnez **rejeter** à la deuxième étape.

## <a name="learn-more"></a>Pour en savoir plus
[Créer des flux d’approbation modernes](modern-approvals.md).

