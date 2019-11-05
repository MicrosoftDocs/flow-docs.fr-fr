---
title: Attendre l’approbation d’un Flow | Microsoft Docs
description: Les flux peuvent attendre qu’un événement externe se produise, tel qu’un utilisateur qui approuve ou rejette une modification, avant d’effectuer une action, telle que l’envoi d’une notification de la décision.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea6be2d1deae080df58afd94c1f1e8d0c13c9fcd
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548350"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Attendre l’approbation dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Créez un Flow qui, si vous créez un élément dans SharePoint, envoie un e-mail d’approbation, puis vous indique si l’élément a été approuvé ou rejeté. Pour suivre exactement ce didacticiel, créez une liste SharePoint simple en tant qu’action de déclencheur, mais vous pouvez utiliser une autre source de données telle que Dropbox ou OneDrive.

**Conditions préalables**

* Créez une liste SharePoint simple nommée suivi de **projet**, ajoutez une colonne nommée **titre**, puis ajoutez une colonne personne ou groupe nommée **affecté à**.

   ![Image de la liste SPO du suivi de projet](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Ajouter un événement pour déclencher le Flow

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com), sélectionnez **mes flux** dans la barre de navigation supérieure, puis **créer à partir d’un espace**.

1. Sélectionnez la zone **Rechercher des centaines de connecteurs et de déclencheurs** , entrez **nouvel élément**, puis accédez à **SharePoint-quand un élément est créé**.

1. Si vous y êtes invité, connectez-vous à SharePoint.
1. Sous **adresse du site**, entrez l’URL du site SharePoint qui contient votre liste.

1. Sous **nom**de la liste, sélectionnez la liste que vous avez créée précédemment. Si vous effectuez cette procédure, le nom est **suivi de projet**.

    ![Image du nom de la liste SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Ajouter l’action résultante

1. Sélectionnez le bouton **nouvelle étape** , puis sélectionnez **Ajouter une action.**

1. Dans la zone **Rechercher tous les connecteurs et actions** , tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook-envoyer un e-mail avec les options**.

1. Si vous y êtes invité, connectez-vous à Office 365 Outlook.

1. Sélectionnez le champ **à** , puis sélectionnez le jeton **assigné à un e-mail** .

    L’utilisateur dans la colonne **affecté à** reçoit l’e-mail pour approuver ou rejeter des éléments. Lorsque vous créez un élément pour tester le Flow, spécifiez-le dans ce champ. Cela vous permet non seulement d’approuver ou de rejeter l’élément, mais également de recevoir l’e-mail de notification.

    > [!NOTE]
    > Vous pouvez personnaliser les champs **objet** et **options utilisateur** en fonction de vos besoins.

    ![Image du champ envoyer un e-mail d’approbation à](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Ajouter une condition

1. Sélectionnez le bouton **nouvelle étape** , puis **Ajouter une condition**.

    ![Image de l’ajout d’une condition](./media/wait-for-approvals/add-a-condition.png)
1. Sélectionnez la première zone, puis sélectionnez le jeton **SelectedOption** .
1. Sélectionnez la dernière zone, puis tapez **Approve**.

    ![Image de la carte de condition](./media/wait-for-approvals/condition-card-2.png)

1. Dans la zone **si oui** , sélectionnez **Ajouter une action**.

1. Dans la zone **Rechercher tous les connecteurs et actions** , tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook-envoyer un message électronique**.

1. Dans le champ **à** , entrez un destinataire tel que **créé par e-mail**.

1. Dans la zone **objet** , spécifiez un objet.

    Par exemple, sélectionnez **affecté à DisplayName**, le type **a approuvé** avec un espace de chaque côté, puis sélectionnez **titre**.

1. Dans la zone **corps** , spécifiez le corps de l’e-mail, par exemple **prêt à passer à la phase suivante du projet.**

    > [!NOTE]
    > La personne qui a créé l’élément dans la liste SharePoint est avertie si le projet a été approuvé ou rejeté.

    ![Image de Yes-Send-email](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Dans la zone **si non** , répétez les cinq dernières étapes, à l’exception de modifier l' **objet** et le **corps** pour refléter que le projet a été rejeté.

     ![Image de no-Send-email](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Terminer et tester votre Flow

1. Donnez un nom à votre Flow, puis sélectionnez **créer un Flow**.

     ![Image de Create-Flow](./media/wait-for-approvals/create-flow.png)
1. Créez un élément dans votre liste SharePoint.

    Un e-mail d’approbation est envoyé au destinataire que vous avez spécifié. Lorsque le destinataire sélectionne **approuver** ou **rejeter** dans cet e-mail, vous recevez un e-mail qui indique la réponse.

## <a name="learn-more"></a>Pour en savoir plus

* [Procédure pas à pas d’approbations modernes d’un seul approbateur](modern-approvals.md)
* Créer des [approbations séquentielles](sequential-modern-approvals.md)
* Créer des [approbations parallèles](parallel-modern-approvals.md)
* Approuver [les demandes en déplacement](mobile-approvals.md)
