---
title: Utilisez l’action apply to each pour parcourir un tableau d’éléments. | Microsoft Docs
description: Utilisez Microsoft Flow pour parcourir un tableau d’éléments afin de vérifier plusieurs conditions et d’effectuer des actions en fonction de ces conditions.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e2852de959f62d5c0ee76fabc9841e3fc9663f73
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545998"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Utiliser l’action appliquer à chaque Microsoft Flow pour traiter une liste d’éléments périodiquement
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
De nombreux déclencheurs peuvent démarrer immédiatement un workflow basé sur un événement, par exemple lorsqu’un nouvel e-mail arrive dans votre boîte de réception. Ces déclencheurs sont très utiles, mais parfois vous souhaitez exécuter un workflow qui interroge une source de données selon une planification prédéfinie, en effectuant certaines actions en fonction des propriétés des éléments de la source de données. Pour ce faire, votre Flow peut être démarré selon une planification (par exemple une fois par jour) et utiliser une action de boucle comme **apply to each** pour traiter une liste d’éléments. Par exemple, vous pouvez utiliser **apply to each** pour mettre à jour des enregistrements à partir d’une base de données ou d’une liste d’éléments à partir de Microsoft SharePoint.

Dans cette procédure pas à pas, nous allons créer un workflow qui s’exécute toutes les 15 minutes et effectue les opérations suivantes :

1. Obtient les 10 derniers messages non lus dans votre boîte de réception Office 365 Outlook.
2. Vérifie chacun des 10 messages afin de vérifier si un a **atteint** le sujet.
3. Vérifie si l’e-mail provient de votre patron ou s’il a été envoyé avec une importance haute.
4. Envoie une notification push et marque comme lu tous les e-mails qui ont la valeur **rencontrer maintenant** dans l’objet et qui est à partir de votre patron ou qui a été envoyé avec une importance haute.

Ce diagramme montre les détails du Flow que nous allons créer dans cette procédure pas à pas :

![vue d’ensemble du workflow en cours de génération](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Conditions préalables
Voici la configuration requise pour exécuter avec succès les étapes de cette procédure pas à pas :

* Un compte inscrit pour utiliser [Microsoft Flow](https://flow.microsoft.com).
* Un compte Office 365 Outlook.
* L’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Connexions à Office 365 Outlook et au service de notifications push.

## <a name="create-a-flow"></a>Créer un Flow
1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com):
2. Sélectionnez l’onglet **mes flux** , puis créez un flux à partir d’un espace vide :
   
    ![créer à partir d’un espace](./media/apply-to-each/foreach-1.png)
3. Entrez « planification » dans la zone de recherche pour rechercher tous les services et déclencheurs liés à la planification.
4. Sélectionnez le déclencheur **planification-récurrence** pour indiquer que votre flow s’exécutera selon une planification que vous fournirez ensuite :
   
    ![action planifier une récurrence](./media/apply-to-each/foreach-2.png)
5. Définir la planification pour qu’elle s’exécute toutes les 15 minutes :
   
    ![exécutions de planification](./media/apply-to-each/foreach-3.png)
6. Sélectionnez **+ nouvelle étape**, **Ajouter une action**, puis tapez **Outlook** dans la zone de recherche pour rechercher toutes les actions liées à Microsoft Outlook.
7. Sélectionnez l’action **Office 365 Outlook-recevoir des messages électroniques** :
   
    ![Sélectionnez l’action recevoir des courriers électroniques](./media/apply-to-each/foreach-4.png)
8. La carte recevoir des **e-mails** s’ouvre. Configurez la carte **obtenir des e-mails** pour sélectionner les 10 premiers e-mails non lus dans le dossier boîte de réception. N’incluez pas de pièces jointes, car elles ne seront pas utilisées dans le flow :
   
    ![configurer la carte de messagerie](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Jusqu’à présent, vous avez créé un simple fluide qui récupère certains courriers électroniques à partir de votre boîte de réception. Ces messages sont renvoyés dans un tableau. l’action **apply to each** requiert un tableau. c’est donc exactement ce qui est nécessaire.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Ajouter des actions et des conditions
1. Sélectionnez **+ nouvelle étape**, **plus**, puis **Ajoutez une action appliquer à chaque** :
   
    ![Sélectionnez appliquer à chaque](./media/apply-to-each/foreach-6.png)
2. Insérez le jeton de **corps** dans la zone **Sélectionnez une sortie à partir des étapes précédentes** de la carte **appliquer à chaque** . Cela extrait le corps des e-mails à utiliser dans l’action **apply to each** :
   
    ![Ajouter un jeton de corps](./media/apply-to-each/foreach-7.png)
3. Sélectionnez **Ajouter une condition**:
   
    ![Ajouter une condition](./media/apply-to-each/foreach-8.png)
4. Configurez la carte de **condition** pour rechercher les mots « rencontrer maintenant » dans l’objet de chaque e-mail :
   
   * Insérez le jeton du **sujet** dans la zone nom de l' **objet** .
   * Sélectionnez **contient** dans la liste **relation** .
   * Entrez « **rencontrer maintenant** » dans la zone **valeur** .
     
     ![configurer une condition](./media/apply-to-each/foreach-subject-condition.png)
5. Sélectionnez **plus**, puis **Ajouter une condition** dans la branche **si oui, ne rien faire** . La carte **condition 2** s’ouvre. Configurez cette carte comme suit :
   
   * Insérez le jeton **importance** dans la zone nom de l' **objet** .
   * SELECT **est égal à** dans la liste des **relations** .
   * Entrez **High** dans la zone **valeur** .
     
     ![Ajouter une condition](./media/apply-to-each/foreach-importance-condition.png)
6. Sélectionnez **Ajouter une action** sous la section **si oui, ne rien faire** . La carte **choisir une action** s’ouvre, dans laquelle vous allez définir ce qui doit se produire si la condition de recherche (l’e-mail de la **rencontre maintenant** a été envoyé avec une importance haute) est vraie :
   
    ![Ajouter une action](./media/apply-to-each/foreach-9.png)
7. Recherchez **notification**, puis sélectionnez l’action **notifications-m’envoyer une notification mobile** :
   
    ![Rechercher et sélectionner une notification](./media/apply-to-each/foreach-10.png)
8. Dans la carte **m’envoyer une notification mobile** , fournissez les détails de la notification push qui sera envoyée si le sujet d’un e-mail contient « répondre maintenant », puis sélectionnez **Ajouter une action**:
   
    ![configurer la notification](./media/apply-to-each/foreach-11.png)
9. Entrez **Read** comme terme de recherche, puis sélectionnez l’action **Office 365 Outlook-marquer comme lu** . Chaque e-mail est alors marqué comme lu après l’envoi de la notification push :
   
    ![Ajouter une marque en tant qu’action de lecture](./media/apply-to-each/foreach-12.png)
10. Ajoutez le jeton **ID de message** à la zone ID de **message** de la carte **marquer comme lu** . Vous devrez peut-être sélectionner **voir plus** pour trouver le jeton d' **ID de message** . Cela indique l’ID du message qui sera marqué comme lu :
    
     ![ID du message d’ajout](./media/apply-to-each/foreach-13.png)
11. En revenons à la carte **condition 2** , sur la branche **si non, ne rien faire** :
    
    * Sélectionnez **Ajouter une action**, puis tapez **accéder au gestionnaire** dans la zone de recherche.
    * Sélectionnez l’action **utilisateurs Office 365-obtenir le gestionnaire** dans la liste des résultats de la recherche.
    * Entrez votre adresse de messagerie *complète* dans la zone **utilisateur** de la carte **obtenir le responsable** .
      
      ![Ajouter et configurer l’action de récupération d’un gestionnaire](./media/apply-to-each/foreach-get-manager.png)
12. Sélectionnez **plus**, puis **Ajouter une condition** à partir de la branche **si non** . La carte **condition 3** s’ouvre. Configurez la carte pour vérifier si l’adresse e-mail de l’expéditeur de l’e-mail (le jeton from) est identique à celle de l’adresse e-mail de votre patron (le jeton de courrier électronique) :
    
    * Insérez le jeton de dans la zone nom **de** l' **objet** .
    * Sélectionnez **contient** dans la liste **relation** .
    * Entrez le jeton d' **e-mail** dans la zone **valeur** .
      
      ![configurer la condition de recherche](./media/apply-to-each/foreach-condition3-card.png)
13. Sélectionnez **Ajouter une action** sous la section **si oui, ne rien faire** de la carte **condition 3** . Cette opération ouvre la carte **si oui** , dans laquelle vous allez définir ce qui doit se produire si la condition de recherche (l’e-mail a été envoyé par votre patron) est vraie :
    
     ![configurer une condition](./media/apply-to-each/foreah-condition3-add-action.png)
14. Recherchez **notification**, puis sélectionnez l’action **notifications-m’envoyer une notification mobile** :
    
     ![Rechercher une action de notification](./media/apply-to-each/foreach-10.png)
15. Sur la carte **m’envoyer une notification mobile 2** , fournissez les détails de la notification push qui sera envoyée si le message provient de votre patron, puis sélectionnez **Ajouter une action**:
    
     ![configurer la carte de notification](./media/apply-to-each/foreach-boss-notification.png)
16. Ajoutez l’action **Office 365 Outlook-marquer comme lu** . Chaque e-mail est alors marqué comme lu après l’envoi de la notification push :
    
     ![Ajouter une marque en tant qu’action de lecture](./media/apply-to-each/foreach-12.png)
17. Ajoutez le jeton **ID de message** à la carte **Mark as Read 2** . Vous devrez peut-être sélectionner **voir plus** pour trouver le jeton d' **ID de message** . Cela indique l’ID du message qui sera marqué comme lu :
    
     ![configurer Mark comme action de lecture](./media/apply-to-each/foreach-mark-as-read2.png)
18. Nommez votre Flow, puis créez-le :
    
     ![Donnez un nom à votre Flow et enregistrez-le](./media/apply-to-each/foreach-14.png)

Si vous avez suivi le, votre Flow devrait ressembler à ce diagramme :

![vue d’ensemble du flow créé](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Exécuter le Flow
1. Envoyez-vous un e-mail à haute importance incluant la **fonction de rencontre** dans l’objet (ou demandez à une personne de votre organisation de vous envoyer un message électronique).
2. Confirmez que l’e-mail se trouve dans votre boîte de réception et qu’il n’est pas lu.
3. Connectez-vous Microsoft Flow, sélectionnez **mes flux**, puis sélectionnez **Exécuter maintenant**:
   
    ![Exécuter maintenant](./media/apply-to-each/foreach-run-1.png)
4. Sélectionnez **exécuter le Flow** pour confirmer que vous voulez vraiment exécuter le flow :
   
    ![confirmer l’exécution](./media/apply-to-each/foreach-run-2.png)
5. Après quelques instants, vous devriez voir les résultats de l’exécution réussie :
   
    ![exécuter les résultats](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Afficher les résultats de l’exécution
Maintenant que vous avez correctement exécuté le Flow, vous devez recevoir la notification push sur votre appareil mobile.

1. Ouvrez l’application Microsoft Flow sur votre appareil mobile, puis sélectionnez l’onglet **activité** . La notification push relative à la réunion s’affiche :
   
    ![Sélectionnez l’onglet activité](./media/apply-to-each/foreach-notification-1.png)
2. Pour afficher le contenu complet de la notification, vous devrez peut-être sélectionner la notification. La notification complète s’affiche, de la façon suivante :
   
    ![Détails de la notification](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Si vous ne recevez pas la notification push, vérifiez que votre appareil mobile dispose d’une connexion de données opérationnelle.
   > 
   > 

