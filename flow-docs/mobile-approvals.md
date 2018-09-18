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
ms.openlocfilehash: b41397d74c7396081154526ad2e248cb293e2460
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689591"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Approuver des demandes sur votre appareil mobile à l’aide de Microsoft Flow
Si un flux vous identifie en tant qu’approbateur et que vous avez installé l’application mobile pour Microsoft Flow, vous recevez une notification Push chaque fois que votre approbation est requise.

Cet article vous guide tout au long de quelques scénarios courants que vous êtes susceptible de rencontrer lorsque vous gérez les demandes d’approbation dans l’application mobile pour Microsoft Flow.

> [!NOTE]
> Les images de cette rubrique proviennent d’un appareil Android. Toutefois, l’expérience sur iOS est similaire.
> 
> 

## <a name="prerequisites"></a>Prérequis
Pour effectuer cette procédure pas à pas, vous avez besoin de ce qui suit :

* Un appareil [Android](https://aka.ms/flowmobiledocsandroid) ou [iOS](https://aka.ms/flowmobiledocsios) exécutant l’application mobile pour Microsoft Flow.
* Être désigné en tant qu’approbateur dans un flux d’approbation.
* Avoir des demandes en attente d’approbation

## <a name="view-pending-requests"></a>Afficher les demandes en attente
1. Ouvrez l’application mobile pour Microsoft Flow.
   
    ![démarrer l’application mobile](./media/mobile-approvals/open-app.png)
2. Dans l’angle supérieur droit, sélectionnez **APPROBATIONS**.
   
    ![sélectionner des approbations](./media/mobile-approvals/select-approvals.png)
3. Affichez toutes les approbations en attente :
   
    ![voir les demandes d’approbation en attente](./media/mobile-approvals/show-pending-approval-requests.png)

Si vous n’avez aucune demande d’approbation en attente, créez un [flux d’approbation](modern-approvals.md), définissez-vous en tant qu’approbateur, puis déclenchez le flux. Les demandes d’approbation apparaissent dans le centre d’approbation quelques secondes après que le flux se déclenche et envoie une demande d’approbation.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Approuver les demandes et laisser un commentaire facultatif
1. Si vous ne l’avez pas encore fait, suivez les étapes précédentes pour [voir les demandes en attente](mobile-approvals.md#view-pending-requests).
2. Sélectionnez **APPROUVER** dans la demande que vous souhaitez approuver.
   
    ![sélectionner approuver](./media/mobile-approvals/select-approve.png)
3. (Facultatif) Sélectionnez **Ajouter un commentaire (facultatif)**.
   
    ![sélectionner ajouter un commentaire](./media/mobile-approvals/select-add-comment.png)
   
    Entrez un commentaire sur l’écran **Ajouter un commentaire**.
   
    ![entrer votre commentaire](./media/mobile-approvals/enter-comment-for-approval.png)
4. Sélectionnez **CONFIRMER** dans l’angle supérieur droit.
   
    ![confirmer que vous avez terminé](./media/mobile-approvals/tap-confirm-button.png)
   
    L’écran de réussite s’affiche une fois que le flux a enregistré votre décision.
   
    ![écran de réussite](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Refuser des demandes et laisser un commentaire facultatif
Suivez les [étapes d’approbation d’une demande](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), mais sélectionnez **REFUSER** à la deuxième étape.

## <a name="learn-more"></a>En savoir plus
[Créer des flux d’approbation modernes](modern-approvals.md).

