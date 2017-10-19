---
title: "Attendre l’approbation dans un flux | Microsoft Docs"
description: "Les flux peuvent attendre qu’un événement externe se produise (comme un utilisateur qui approuve ou rejette une modification) avant d’effectuer une action (telle que l’envoi d’une notification concernant la décision)."
services: 
suite: flow
documentationcenter: na
author: merwanhade
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/24/2016
ms.author: merwanhade
ms.openlocfilehash: a26566486cf6310dc1c33ef226bfc37b30a5ad16
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Attendre l’approbation dans Microsoft Flow
<iframe width="560" height="315" src="https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Créez un flux qui, si vous créez un élément dans SharePoint, envoie un message d’approbation et vous avertit si l’élément a été approuvé ou rejeté. Pour suivre précisément ce didacticiel, créez une liste SharePoint simple comme action de déclencheur, mais vous pouvez utiliser une autre source de données telle que Dropbox ou OneDrive.

**Conditions préalables**

* Créez une liste SharePoint Online simple nommée **Outil de suivi de projets** avec une colonne nommée **Titre**, puis ajoutez une colonne Personne ou Groupe nommée **Assigné à**.
  
   ![Image de la liste SPO d’outil de suivi de projets](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Ajouter un événement pour déclencher le flux
1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure, puis **Créer un flux**.
   
    ![Image du bouton Créer un flux](./media/wait-for-approvals/create-a-new-flow.png)
2. Dans la zone **Comment souhaitez-vous démarrer ?**, tapez ou collez **nouvel élément**, puis sélectionnez **SharePoint Online - Lorsqu’un élément est créé**.
   
    ![Image du déclencheur SPO](./media/wait-for-approvals/send-approval-email-select-2.png)
3. Si vous y êtes invité, connectez-vous à SharePoint Online.
4. Sous **URL du site**, tapez ou collez l’URL du site contenant la liste.
   
    ![Image de l’URL du site SPO](./media/wait-for-approvals/SPO-site-url.png)
5. Sous **Nom de la liste**, sélectionnez une liste comme **Outil de suivi de projets**.
   
    ![Image de nom de liste SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Ajouter l’action résultante
1. Sélectionnez le bouton **+**, puis **Ajouter une action**.
   
    ![Image Ajouter une action](./media/wait-for-approvals/add-an-action.png)
2. Dans la zone **Que voulez-vous faire ensuite ?**, tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook - Envoyer un message électronique d’approbation**.
   
    ![Image Envoyer un message électronique d’approbation](./media/wait-for-approvals/send-approval-mail.png)
3. Si vous y êtes invité, connectez-vous à Office 365 Outlook.
4. Sélectionnez le champ **À** , puis sélectionnez **Affecté à Adresse électronique**.
   
    L’utilisateur dans la colonne **Affecté à** reçoit le message qui lui permet d’approuver ou de rejeter l’élément. Lorsque vous créez un élément pour tester le flux, vous devez spécifier votre propre nom dans ce champ. De cette façon, vous allez non seulement approuver ou rejeter l’élément, mais également recevoir le message de notification.
   
    **Remarque** : vous pouvez personnaliser les champs **Objet** et **Options de l’utilisateur** selon vos besoins.
   
    ![Image du champ Envoyer un message électronique d’approbation à](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Ajouter une condition
1. Sélectionnez le bouton **+**, puis **Ajouter une condition**.
   
    ![Image Ajouter une condition](./media/wait-for-approvals/add-a-condition.png)
2. Dans le champ **Nom de l’objet**, sélectionnez **OptionSélectionnée**.
3. Dans le champ **Valeur**, tapez ou collez **Approuver**.
   
    ![Image de la carte de condition](./media/wait-for-approvals/condition-card-2.png)
4. Dans la zone **Si oui**, sélectionnez **Ajouter une action**.
   
    ![Image de la zone Si oui, ajouter une action](./media/wait-for-approvals/yes-add-an-action.png)
5. Dans la zone **Que voulez-vous faire ensuite ?**, tapez ou collez **Envoyer un message électronique**, puis sélectionnez **Office 365 Outlook - Envoyer un message électronique**.
   
    ![Image Oui, envoyer un message électronique](./media/wait-for-approvals/yes-send-email.png)
6. Dans la zone **Objet**, spécifiez un objet.
   
    Par exemple, sélectionnez **Affecté à Nom d’affichage**, tapez **a approuvé** avec un espace de chaque côté, puis sélectionnez **Titre**.
7. Dans la zone **Corps**, spécifiez un corps de message électronique, tel que **Procéder à la phase suivante du projet**.
8. Dans le champ **À**, entrez un destinataire comme **Créé par Adresse de messagerie**.
   
    La personne qui a créé l’élément dans la liste SharePoint est informé si le projet a été approuvé ou refusé.
   
    ![Image Oui, envoyer un message électronique](./media/wait-for-approvals/if-yes-send-email-card-3.png)
9. Dans la zone **Si non**, répétez les cinq dernières étapes, sauf que vous modifiez les zones **Objet** et **Corps** pour qu’elles reflètent que le projet a été rejeté.
   
     ![Image Non, envoyer un message électronique](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Terminer et tester votre flux
1. Donnez un nom à votre flux, puis sélectionnez **Créer le flux**.
   
     ![Image Créer le flux](./media/wait-for-approvals/create-flow.png)
2. Créez un élément dans votre liste SharePoint.
   
    Un message d’approbation est envoyé au destinataire que vous avez spécifié. Lorsque le destinataire sélectionne **Approuver** ou **Rejeter** dans ce message, vous recevez un courrier électronique qui indique la réponse. 

