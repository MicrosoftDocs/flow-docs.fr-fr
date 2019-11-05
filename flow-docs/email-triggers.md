---
title: Exécuter des flux en fonction des propriétés de messagerie | Microsoft Docs
description: Démarrez un workflow basé sur des propriétés telles que l’objet, l’adresse de l’expéditeur ou l’adresse du destinataire d’un e-mail.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544931"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Déclencher un Flow en fonction des propriétés de l’e-mail
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Utilisez le déclencheur lors de l' **arrivée d’un nouveau message électronique** pour créer un fluide qui s’exécute lorsqu’une ou plusieurs des propriétés de messagerie suivantes correspondent aux critères que vous fournissez :

| Propriété | Quand l’utiliser |
| --- | --- |
| Répertoire |Déclencher un Flow chaque fois que des e-mails arrivent dans un dossier spécifique. Cette propriété peut être utile si vous avez des règles qui acheminent les e-mails vers différents dossiers. |
| À |Déclenchez un workflow en fonction de l’adresse à laquelle un e-mail a été envoyé. Cette propriété peut être utile si vous recevez un e-mail envoyé à différentes adresses de messagerie dans la même boîte de réception. |
| De |Déclenchez un workflow basé sur l’adresse e-mail de l’expéditeur. |
| Importance |Déclenchez un workflow en fonction de l’importance avec laquelle les e-mails ont été envoyés. Le courrier électronique peut être envoyé avec une importance élevée, normale ou faible. |
| A une pièce jointe |Déclencher un workflow en fonction de la présence de pièces jointes dans les e-mails entrants. |
| Filtre objet |Recherchez la présence de mots spécifiques dans l’objet d’un e-mail. Votre Flow exécute ensuite des *actions* basées sur les résultats de votre recherche. |

> [!IMPORTANT]
> Chaque [plan de Microsoft Flow](https://flow.microsoft.com/pricing/) comprend un quota d’exécution. Vérifiez toujours les propriétés dans le déclencheur du Flow lorsque cela est possible. Cela évite d’utiliser le quota d’exécution inutilement. Si vous vérifiez une propriété dans une condition, chaque exécution compte sur le quota d’exécution de votre plan, même si la condition de filtre que vous avez définie n’est pas remplie. 

Par exemple, si vous vérifiez l’adresse *d'* un e-mail dans une condition, chaque exécution compte sur le quota d’exécution de votre plan, même s’il ne s’agit pas *de* l’adresse qui vous intéresse.
> 
> 

Dans les procédures pas à pas suivantes, nous vérifions toutes les propriétés du déclencheur lors de l' **arrivée d’un nouveau message électronique** . Pour en savoir plus, consultez les [questions fréquemment posées](billing-questions.md#what-counts-as-a-run) sur la facturation et la page de [tarification](https://ms.flow.microsoft.com/pricing/) .

## <a name="prerequisites"></a>Conditions préalables
* Un compte ayant accès à [Microsoft Flow](https://flow.microsoft.com)
* Un compte Office 365 Outlook
* L’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows)
* Connexions à Office, Outlook et au service de notifications push

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Déclencher un workflow en fonction de l’objet d’une adresse de messagerie
Dans cette procédure pas à pas, nous créons un Flow qui envoie une notification push à votre téléphone mobile si le sujet d’un nouveau message électronique contient le mot « loterie ». Votre Flow marque ensuite un tel message comme *lu*.

>[!NOTE]
>Bien que cette procédure pas à pas envoie une notification push, vous pouvez utiliser toute autre action adaptée à vos besoins en matière de flux de travail. Par exemple, vous pouvez stocker le contenu de l’e-mail dans un autre référentiel tel que Google Sheets ou un fichier Microsoft Excel stocké sur Dropbox.

Bon, commençons :

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Dans la zone **filtre objet** , entrez le texte utilisé par votre Flow pour filtrer les e-mails entrants.
   
     Dans cet exemple, nous nous intéressons à tous les e-mails qui ont le mot « loterie » dans l’objet.
   
    ![Options avancées](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Entrez les détails de la notification mobile que vous souhaitez recevoir quand vous recevez un e-mail qui correspond au **filtre objet** que vous avez spécifié précédemment.
   
    ![Détails de la notification](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Donnez un nom à votre Flow. Ensuite, enregistrez-le en sélectionnant **créer un Flow** en haut de la page.
   
    ![enregistrer le Flow](./media/email-triggers/email-triggers-subject-notification.png)

Félicitations! Vous recevez maintenant une notification push chaque fois que vous recevez un e-mail contenant le mot « loterie » dans l’objet.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Déclencher un workflow en fonction de l’expéditeur d’un e-mail
Dans cette procédure pas à pas, nous créons un Flow qui envoie une notification push à votre téléphone mobile si un nouvel e-mail arrive d’un expéditeur spécifique (adresse e-mail). Le Flow marque également tout message de ce type comme étant *lu*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Dans la zone **de** , entrez l’adresse de messagerie de l’expéditeur. 
   
     Votre Flow entreprend des actions sur les e-mails envoyés à partir de cette adresse.
   
    ![Propriété de l’e-mail](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Entrez les détails de la notification mobile que vous souhaitez recevoir chaque fois qu’un message arrive à partir de l’adresse e-mail que vous avez entrée précédemment.
   
    ![Détails de la notification](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Donnez un nom à votre Flow, puis enregistrez-le en sélectionnant **créer un Flow** en haut de la page.
   
    ![enregistrer le Flow](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Déclencher un Flow lorsque des e-mails arrivent dans un dossier spécifique
Si vous avez des règles qui acheminent les courriers électroniques vers différents dossiers en fonction de certaines propriétés, telles que l’adresse, vous souhaiterez peut-être ce type de Flow.

Commençons :

> [!NOTE]
> Si vous ne disposez pas d’une règle qui achemine le courrier vers un dossier autre que celui de votre boîte de réception, créez une telle règle et confirmez qu’elle fonctionne en envoyant un message électronique de test.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Sélectionnez le dossier vers lequel vous acheminez des e-mails spécifiques. Pour afficher tous les dossiers de courrier électronique, sélectionnez d’abord l’icône **afficher le sélecteur** , qui se trouve sur le côté droit de la zone **dossier** de la carte lors de l' **arrivée d’un nouvel e-mail** .
   
    ![Sélectionner un dossier](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Entrez les détails de la notification mobile que vous souhaitez recevoir lorsqu’un courrier électronique arrive dans le dossier que vous avez sélectionné précédemment. Si vous ne l’avez pas déjà fait, entrez les informations d’identification du service de notifications.
   
    ![Détails de la notification](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Donnez un nom à votre Flow, puis enregistrez-le en sélectionnant **créer un Flow** en haut de la page.
   
    ![enregistrer le Flow](./media/email-triggers/email-triggers-7.png)

Testez le Flow en envoyant un e-mail qui est acheminé vers le dossier que vous avez sélectionné précédemment dans cette procédure pas à pas.

