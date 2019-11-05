---
title: Créer un Flow avec Dynamics 365 (Online) | Microsoft Docs
description: Créer des flux de travail utiles à l’aide d’une connexion Dynamics 365 et Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546914"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Créer un workflow à l’aide de Dynamics 365 (en ligne)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
À l’aide d’un connecteur Dynamics 365, vous pouvez créer des flux qui démarrent lorsqu’un événement se produit dans Dynamics 365, ou un autre service, qui exécute ensuite une action dans Dynamics 365 ou un autre service. 

Dans Microsoft Flow, vous pouvez configurer des flux de travail automatisés entre vos applications et services favoris pour synchroniser des fichiers, obtenir des notifications, collecter des données et bien plus encore. Pour plus d’informations, consultez la page [prise en main de Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Pour appeler un déclencheur de Flow, l’entité Common Data Service utilisée avec le Flow doit avoir **change Tracking** activée. Informations supplémentaires : [activer le suivi des modifications pour contrôler la synchronisation des données](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Créer un fluide à partir d’un modèle
Vous pouvez créer un fluide à l’aide de l’un des nombreux modèles disponibles, tels que les exemples suivants :

* Quand un objet est créé dans Dynamics 365, créez un élément de liste dans SharePoint.
* Créez des enregistrements de prospect Dynamics 365 à partir d’un tableau Excel.
* Copiez les comptes Dynamics 365 aux clients dans Dynamics 365 pour les opérations.

Pour créer un fluide à partir d’un modèle, procédez comme suit.

1. Connectez-vous au [site web Microsoft Flow](https://flow.microsoft.com/).
2. Cliquez ou appuyez sur **services**, puis cliquez ou appuyez sur **Dynamics 365**.
3. Plusieurs modèles sont disponibles. Pour commencer, sélectionnez le modèle souhaité.

## <a name="create-a-task-from-a-lead"></a>Créer une tâche à partir d’un prospect
Si un modèle n’est pas disponible pour ce dont vous avez besoin, créez un flot à partir de zéro. Cette procédure pas à pas vous montre comment créer une tâche dans Dynamics 365 chaque fois qu’un prospect est créé dans Dynamics 365.

1. Connectez-vous au [site web Microsoft Flow](https://flow.microsoft.com/).
2. Cliquez ou appuyez sur **mes flux**, puis cliquez ou appuyez sur **créer à partir d’un espace**.
3. Dans la liste des déclencheurs de workflow, cliquez ou appuyez sur **Dynamics 365-quand un enregistrement est créé**.
4. Si vous y êtes invité, connectez-vous à Dynamics 365.
5. Sous **nom**de l’organisation, sélectionnez l’instance Dynamics 365 dans laquelle vous souhaitez que le workflow écoute.
6. Sous **nom**de l’entité, sélectionnez l’entité que vous souhaitez écouter, qui agira comme un déclencheur déclenchant le Workflow.
   
     Pour cette procédure pas à pas, sélectionnez des **clients**.
   
    ![Détails du Flow](./media/connection-dynamics365/flow-details.png)
    > PRÉCIEUSE Pour que le workflow se déclenche sur l’entité Dynamics 365, la définition de l’entité doit avoir **change Tracking** activé. Consultez [activer le suivi des modifications pour contrôler la synchronisation des données](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Cliquez ou appuyez sur **nouvelle étape**, puis cliquez ou appuyez sur **Ajouter une action**.
8. Cliquez ou appuyez sur **Dynamics 365 – créer un nouvel enregistrement**.
9. Sous **nom**de l’organisation, sélectionnez l’instance Dynamics 365 dans laquelle vous souhaitez que le Flow crée l’enregistrement. Notez qu’il n’est pas nécessaire qu’il s’agit de la même instance que celle à partir de laquelle l’événement est déclenché.
10. Sous **nom**de l’entité, sélectionnez l’entité qui créera un enregistrement lorsque l’événement se produit.
    
     Pour cette procédure pas à pas, sélectionnez **tâches**.
11. Une zone **objet** s’affiche. Lorsque vous cliquez ou appuyez dessus, un volet de contenu dynamique s’affiche pour vous permettre de sélectionner l’un de ces champs.
    
    * **Nom**. Si vous sélectionnez ce champ, le nom du prospect est inséré dans le champ **objet** de la tâche lors de sa création.
    * **Rubrique**. Si vous sélectionnez ce champ, le champ de **rubrique** du prospect est inséré dans le champ **objet** de la tâche lors de sa création.
    
    Pour cette procédure pas à pas, sélectionnez une **rubrique**.
    
    ![Rubrique ajouter un Flow](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Conseil :** Dans le volet de contenu dynamique, cliquez ou appuyez sur **afficher plus** pour afficher plus de champs associés à l’entité. Par exemple, vous pouvez également renseigner le champ **objet** de la tâche avec le champ **nom**de la société, **client**, **Description**ou **e-mail** du prospect.
    > 
    > 
12. Cliquez ou appuyez sur **créer un Flow**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Créer une tâche Wunderlist à partir d’une tâche Dynamics 365
Cette procédure pas à pas vous montre comment créer une tâche dans [Wunderlist](https://www.wunderlist.com) chaque fois qu’une tâche est créée dans Dynamics 365. Wunderlist est un service basé sur Internet que vous pouvez utiliser pour créer des listes de tâches, ajouter des rappels ou suivre des courses.

1. Connectez-vous au [site web Microsoft Flow](https://flow.microsoft.com/).
2. Cliquez ou appuyez sur **mes flux**, puis cliquez ou appuyez sur **créer à partir d’un espace**.
3. Dans la liste des déclencheurs de workflow, cliquez ou appuyez sur **Dynamics 365-quand un enregistrement est créé**.
4. Sous **nom**de l’organisation, sélectionnez l’instance Dynamics 365 dans laquelle vous souhaitez que le workflow écoute.
5. Sous **nom**de l’entité, sélectionnez l’entité que vous souhaitez écouter, qui agira comme un déclencheur pour initier le Workflow.
   
    Pour cette procédure pas à pas, sélectionnez **tâches**.
6. Cliquez ou appuyez sur **nouvelle étape**, puis cliquez ou appuyez sur **Ajouter une action**.
7. Tapez *créer une tâche*, puis cliquez ou appuyez sur **Wunderlist – créer une tâche**.
8. Sous **ID**de la liste, sélectionnez **boîte de réception**.
9. Sous **titre**, sélectionnez **objet** dans le volet de contenu dynamique.
10. Cliquez ou appuyez sur **créer un Flow**.  

## <a name="trigger-based-logic"></a>Logique basée sur un déclencheur
Se déclenche comme **lors de la création d’un enregistrement**, lors de la **mise à jour**d’un enregistrement, et lors de la **Suppression d’un enregistrement** , initiez votre Flow dans les quelques minutes qui suivent l’événement.  Dans de rares cas, le déclenchement de votre fluide peut prendre jusqu’à 2 heures.

Lorsque le déclencheur se produit, le workflow reçoit une notification, mais le workflow s’exécute sur les données qui existent au moment de l’exécution de l’action.  Par exemple, si votre workflow se déclenche lors de la création d’un enregistrement et que vous mettez à jour l’enregistrement à deux reprises avant que le workflow ne s’exécute, votre workflow ne s’exécute qu’une seule fois avec les données les plus récentes.

## <a name="specify-advanced-options"></a>Spécifier des options avancées
Lorsque vous ajoutez une étape à un Flow, vous pouvez cliquer ou appuyer sur **afficher les options avancées** pour ajouter un filtre ou une requête d’ordre par requête qui contrôle la façon dont les données sont filtrées dans le Flow.

Par exemple, vous pouvez utiliser une requête de filtre pour récupérer uniquement les contacts actifs, et les trier par nom de famille. Pour ce faire, entrez la requête de filtre OData **statusCode EQ 1** et sélectionnez **Last Name** dans le volet de contenu dynamique. Pour plus d’informations sur le filtrage et l’ordre des requêtes, consultez [MSDN : $Filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) et [MSDN : $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Requête Flow OrderBy](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Meilleures pratiques lors de l’utilisation des options avancées
Lorsque vous ajoutez une valeur à un champ, vous devez faire correspondre le type de champ si vous tapez une valeur ou en sélectionnez une dans le volet de contenu dynamique.

| Type de champ | Procédure d’utilisation | Emplacement de recherche | Nomme | Type de données |
| --- | --- | --- | --- | --- |
| Champs de texte |Les champs de texte nécessitent une seule ligne de texte ou du contenu dynamique qui est un champ de type texte. Les exemples incluent les champs de **catégorie** et de **sous-catégorie** . |**Paramètres** > **personnalisations** > **personnaliser les** **entités** > du système > les **champs** > des **tâches** |**catégorie** |**Une seule ligne de texte** |
| Champs de type entier |Certains champs nécessitent un entier ou un contenu dynamique qui est un champ de type entier. Les exemples incluent le **pourcentage terminé** et la **durée**. |**Paramètres** > **personnalisations** > **personnaliser les** **entités** > du système > les **champs** > des **tâches** |**PourcentageAchevé** |**Nombre entier** |
| Champs de date |Certains champs nécessitent une date entrée au format mm/jj/aaaa ou un contenu dynamique qui est un champ de type date. Exemples : **créé le**, **Date de début**, **début réel**, **heure de la dernière suspension**, **fin réelle**et **Date d’échéance**. |**Paramètres** > **personnalisations** > **personnaliser les** **entités** > du système > les **champs** > des **tâches** |**created** |**Date et heure** |
| Champs nécessitant à la fois un ID d’enregistrement et un type de recherche |Certains champs qui font référence à un autre enregistrement d’entité nécessitent l’ID d’enregistrement et le type de recherche. |**Paramètres** > **personnalisations** > **personnaliser les** **entités** > du système > compte ** > ** |**accountid** |**Clé primaire** |
|Groupe d’options|Les champs de groupe d’options nécessitent la transmission d’une valeur entière connue dans ce type de champ.  Dans la zone personnalisation de Dynamics 365, vous pouvez afficher l’option définir le champ de type entier en même temps que son étiquette respective.|Paramètres > Personnalisation > personnaliser les entités > du système > compte > | Méthode de contact préférée| Nombre entier|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Autres exemples de champs qui nécessitent à la fois un ID d’enregistrement et un type de recherche
En développant le tableau précédent, Voici d’autres exemples de champs qui ne fonctionnent pas avec les valeurs sélectionnées à partir de la liste de contenu dynamique. Au lieu de cela, ces champs nécessitent à la fois un ID d’enregistrement et un type de recherche entrés dans les champs de PowerApp.

* **Propriétaire** et **type de propriétaire**.
  
  * Le champ **propriétaire** doit être un ID d’enregistrement d’utilisateur ou d’équipe valide.
  * Le **type de propriétaire** doit être **systemusers** ou **teams**.
* **Client** et **type de client**.
  
  * Le champ **client** doit être un ID d’enregistrement de contact ou de compte valide.
  * Le **type de client** doit être un **compte** ou un **contact**.
* **Concernant** le **type et concernant**.
  
  * Le champ **concernant** doit être un ID d’enregistrement valide, tel qu’un ID d’enregistrement de contact ou de compte.
  * Le **type concernant** doit être le type de recherche pour l’enregistrement, tel que **comptes** ou **contacts**.

Cet exemple ajoute un enregistrement de compte qui correspond à l’ID d’enregistrement, en l’ajoutant au champ **concernant** de la tâche.

  ![Type de transmission recordId et compte de type](./media/connection-dynamics365/flow-recordid-account.png)

Cet exemple affecte également la tâche à un utilisateur spécifique en fonction de l’ID d’enregistrement de l’utilisateur.

  ![Le type de transmission recordId et l’utilisateur de type](./media/connection-dynamics365/flow-recordid-user.png)

Pour Rechercher l’ID d’un enregistrement, consultez [Rechercher l’ID d’enregistrement](#find-the-records-id) plus loin dans cette rubrique.

> **Important :** Les champs ne doivent pas contenir de valeur s’ils ont une description de « à usage interne uniquement ». Ces champs incluent le **chemin parcouru**, les **paramètres supplémentaires**et le numéro de version de la **règle de fuseau horaire.**
> 
> 

## <a name="find-the-records-id"></a>Rechercher l’ID de l’enregistrement
1. Dans l’application Web Dynamics 365, ouvrez un enregistrement, tel qu’un enregistrement de compte.
2. Dans la barre d’outils actions, cliquez ou **Appuyez sur ouvrir
   ![** enregistrement fenêtre indépendante](./media/connection-dynamics365/popout.png) (ou appuyez sur **Envoyer un lien par courrier électronique** pour copier l’URL complète dans votre programme de messagerie par défaut).
   
    Dans la barre d’adresses du navigateur Web, l’URL contient l’ID d’enregistrement entre les caractères d’encodage% 7B et% 7D.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Rubriques connexes
[Résolution des problèmes d’un Flow](fix-flow-failures.md)

[Flow dans votre organisation Q & A](organization-q-and-a.md)

[Forum aux questions](frequently-asked-questions.md)

