---
title: "Attendre l’approbation dans un flux | Microsoft Docs"
description: "Les flux peuvent attendre qu’un événement externe se produise (comme un utilisateur qui approuve ou rejette une modification) avant d’effectuer une action (telle que l’envoi d’une notification concernant la décision)."
services: 
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
ms.author: merwanhade
ms.openlocfilehash: b75cacf14da7d1b339e8a2f9e35eece389c2a6f7
ms.sourcegitcommit: 22a883c30c859b6193fc2a619e753d71247f5e15
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2018
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Attendre l’approbation dans Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Créez un flux qui, si vous créez un élément dans SharePoint, envoie un e-mail d’approbation et vous indique si l’élément a été approuvé ou rejeté. Pour suivre précisément ce didacticiel, créez une liste SharePoint simple comme action de déclencheur, mais vous pouvez utiliser une autre source de données telle que Dropbox ou OneDrive.

**Conditions préalables**

* Créez une liste SharePoint simple nommée **Outil de suivi de projets** avec une colonne nommée **Titre**, puis ajoutez une colonne Personne ou Groupe nommée **Affecté à**.

   ![Image de la liste SPO d’outil de suivi de projets](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Ajouter un événement pour déclencher le flux

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure, puis **Créer entièrement**.

1. Sélectionnez la zone **Rechercher des centaines de connecteurs et de déclencheurs**, entrez un **nouvel élément**, puis accédez à **SharePoint - quand un élément est créé**.

1. Si vous y êtes invité, connectez-vous à SharePoint.
1. Sous **Adresse du site**, entrez l’URL du site SharePoint qui contient votre liste.

1. Sous **Nom de la liste**, sélectionnez la liste que vous avez créée. Si vous appliquez l’exemple, le nom est **Outil de suivi de projets**.

    ![Image du nom de liste SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Ajouter l’action résultante

1. Sélectionnez le bouton **Nouvelle étape**, puis **Ajouter une action.**

1. Dans la zone **Rechercher dans l’ensemble des connecteurs et des actions**, tapez ou collez **Envoyer un e-mail**, puis sélectionnez **Office 365 Outlook - Envoyer un e-mail avec des options**.

1. Si vous y êtes invité, connectez-vous à Office 365 Outlook.

1. Sélectionnez le champ **À**, puis sélectionnez le jeton **Affecté à - E-mail**.

    L’utilisateur dans la colonne **Affecté à** reçoit l’e-mail qui lui permet d’approuver ou de rejeter les éléments. Quand vous créez un élément pour tester le flux, spécifiez votre propre nom dans ce champ. De cette façon, vous pouvez approuver ou rejeter l’élément, et également recevoir l’e-mail de notification.

    > [!NOTE]
    > Vous pouvez personnaliser les champs **Objet** et **Options de l’utilisateur** selon vos besoins.

    ![Image du champ Envoyer un message électronique d’approbation à](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Ajouter une condition

1. Sélectionnez le bouton **Nouvelle étape**, puis **Ajouter une conditions**.

    ![Image Ajouter une condition](./media/wait-for-approvals/add-a-condition.png)
1. Sélectionnez la première zone, puis le jeton **SelectedOption**.
1. Sélectionnez la dernière zone, puis tapez **Approuver**.

    ![Image de la carte de condition](./media/wait-for-approvals/condition-card-2.png)

1. Dans la zone **Si oui**, sélectionnez **Ajouter une action**.

1. Dans la zone **Rechercher dans l’ensemble des connecteurs et des actions**, tapez ou collez **Envoyer un e-mail**, puis sélectionnez **Office 365 Outlook - Envoyer un e-mail**.

1. Dans le champ **À**, entrez un destinataire de type **Créé par - E-mail**.

1. Dans la zone **Objet**, spécifiez un objet.

    Par exemple, sélectionnez **Affecté à Nom d’affichage**, tapez **a approuvé** avec un espace de chaque côté, puis sélectionnez **Titre**.

1. Dans la zone **Corps**, spécifiez un corps de message électronique, tel que **Procéder à la phase suivante du projet**.

    > [!NOTE]
    > La personne qui a créé l’élément dans la liste SharePoint est informé si le projet a été approuvé ou refusé.

    ![Image Oui, envoyer un message électronique](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Dans la zone **Si non**, répétez les cinq dernières étapes, sauf que vous modifiez les zones **Objet** et **Corps** pour qu’elles reflètent que le projet a été rejeté.

     ![Image Non, envoyer un message électronique](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Terminer et tester votre flux

1. Donnez un nom à votre flux, puis sélectionnez **Créer le flux**.

     ![Image Créer le flux](./media/wait-for-approvals/create-flow.png)
1. Créez un élément dans votre liste SharePoint.

    Un e-mail d’approbation est envoyé au destinataire que vous avez spécifié. Quand le destinataire sélectionne **Approuver** ou **Rejeter** dans l’e-mail, vous recevez un e-mail qui indique la réponse.

## <a name="learn-more"></a>En savoir plus

* [Procédure pas à pas pour les approbations modernes avec un seul approbateur](modern-approvals.md)
* Créer des [approbations séquentielles](sequential-modern-approvals.md)
* Créer des [approbations parallèles](parallel-modern-approvals.md)
* Approuver des [demandes en déplacement](mobile-approvals.md)
