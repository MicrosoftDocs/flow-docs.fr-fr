---
title: Comprendre les opérations de données | Microsoft Docs
description: Apprenez à effectuer des opérations, telles que créer un tableau HTML, créer un tableau CSV, composer, joindre, sélectionner et filtrer un tableau avec Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 87d805fb7de5ee9688e9e89c201be00fda8fb319
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547786"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Utiliser des opérations de données avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dans cette procédure pas à pas, vous découvrirez certaines des opérations de données populaires de Microsoft Flow, telles que composer, joindre, sélectionner, filtrer un tableau, créer une table et analyser JSON qui sont disponibles pour manipuler des données lorsque vous créez des flux.

## <a name="prerequisites"></a>Conditions préalables
* Accès aux Microsoft Flow.
* Un outil tel que [poster](https://www.getpostman.com/postman) pour envoyer des requêtes http postales avec un tableau JSON à votre Flow.

## <a name="use-the-compose-action"></a>Utiliser l’action composer
Utilisez l’action opérations sur les **données-compose** (compose) pour vous éviter d’entrer plusieurs fois des données identiques lors de la conception d’un fluide. Par exemple, si vous devez entrer un tableau de chiffres : ````[0,1,2,3,4,5,6,7,8,9]```` plusieurs fois lors de la conception de votre Flow, vous pouvez utiliser l’action composer pour enregistrer le tableau comme suit :

1. Recherchez **compose**, puis sélectionnez l’action **opérations sur les données-compose** (compose).
   
    ![Rechercher et sélectionner l’action composer](./media/data-operations/search-select-compose.png)
2. Entrez le tableau dans la zone **entrées** que vous souhaitez référencer par la suite :
   
    ![configurer l’action composer](./media/data-operations/add-array-compose.png)

> [!TIP]
> Pour une référence plus simple ultérieurement, renommez la carte **compose** en cliquant sur le texte « composer » dans la barre de titre de la carte **compose** .
> 
> 

Lorsque vous avez besoin d’accéder au contenu de l’action compose, utilisez le jeton de **sortie** dans la liste **Ajouter du contenu dynamique à partir des applications et des connecteurs utilisés dans ce Flow** en procédant comme suit :

1. Ajoutez une action telle que **opérations sur les données – joindre**.
2. Sélectionnez le contrôle auquel vous souhaitez ajouter le contenu que vous avez enregistré dans l’action composer.
   
    Le **module ajouter du contenu dynamique à partir des applications et des connecteurs utilisés dans ce Flow** s’ouvre.
3. Dans la section **Ajouter du contenu dynamique des applications et des connecteurs utilisés dans ce Flow**, sélectionnez le jeton de **sortie** qui se trouve sous la catégorie **compose** de l’onglet **contenu dynamique** .
   
    ![utiliser la sortie de l’action composer](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Utiliser l’action de jointure
Utilisez l’action **Data Operations-Join** (jointure) pour délimiter un tableau avec un séparateur de votre choix. Par exemple, supposons que votre Flow reçoit une requête Web qui comprend le tableau suivant d’adresses de messagerie : ````["d@example.com", "k@example.com", "dal@example.com"]````. Toutefois, votre programme de messagerie requiert que les adresses soient une chaîne unique, séparée par des points-virgules. Pour ce faire, utilisez l’action **Data Operations-Join** (jointure) pour remplacer la virgule de séparation par un point-virgule « ; » en procédant comme suit :

1. Ajoutez une nouvelle action, recherchez **join**, puis sélectionnez **Data Operations-Join** (jointure).
   
    ![Rechercher et sélectionner l’action de jointure](./media/data-operations/search-select-join.png)
2. Entrez le tableau dans la zone **de** , puis entrez le nouveau délimiteur que vous souhaitez utiliser dans la zone **joindre avec** .
   
    Ici, j’ai utilisé le point-virgule (;) comme nouveau délimiteur.
   
    ![configurer l’action de jointure](./media/data-operations/add-array-join.png)
3. Enregistrez votre Flow, puis exécutez-le.
4. Après l’exécution de votre workflow, la sortie de l’action **Data Operations-Join** est la suivante :
   
    ![sortie de jointure](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Utiliser l’action Select
Utilisez les **opérations de données – SELECT** (Select) pour transformer la forme des objets dans un tableau. Par exemple, vous pouvez ajouter, supprimer ou renommer des éléments dans chaque objet d’un tableau.

> [!NOTE]
> Vous pouvez ajouter ou supprimer des éléments à l’aide de l’action Select, mais vous ne pouvez pas modifier le nombre d’objets dans le tableau.
> 
> 

Par exemple, vous pouvez utiliser l’action SELECT si des données entrent dans votre workflow via une requête Web au format suivant :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

et vous aimeriez remodeler les données entrantes en renommant « First » en « FirstName », « Last » en « LastName » et en ajoutant un nouveau membre nommé « FamilyName » qui combine « First » et « Last » (séparés par un espace) :

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Pour ce faire, procédez comme suit :

1. Ajoutez l’action **requête/réponse – réponse** (demande) à votre Flow.
2. Sélectionnez **utiliser l’exemple de charge utile pour générer le schéma** à partir de la carte de **demande** .
3. Dans la zone qui s’affiche, collez un exemple de votre tableau de données source, puis sélectionnez le bouton **terminé** .
4. Ajoutez les **opérations de données : sélectionnez** l’action (sélectionner), puis configurez-la comme l’image suivante.
   
    ![configurer l’action Select](./media/data-operations/select-card.png)
   
   > [!TIP]
   > La sortie de l’action Select est un tableau qui contient les objets nouvellement mis en forme. Vous pouvez ensuite utiliser ce tableau dans toute autre action, telle que **compose**, décrite précédemment.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Utiliser l’action filtrer le tableau
Utilisez les **opérations de données-tableau de filtres** (tableau de filtres) pour réduire le nombre d’objets d’un tableau à un sous-ensemble qui correspond aux critères que vous fournissez.

> [!NOTE]
> Le tableau de filtres ne peut pas être utilisé pour modifier la forme des objets dans un tableau. En outre, le texte sur lequel vous filtrez respecte la casse.
> 
> 

Par exemple, vous pouvez utiliser un tableau de filtres sur ce tableau :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

pour créer un tableau qui contient uniquement des objets dans lesquels *First* est défini sur « Deon ».

Allons-y.

1. Recherchez, puis ajoutez l’action **données-tableau de filtres** (tableau de filtres) à votre Flow.
2. Configurez l’action filtrer le tableau comme l’image suivante.
   
    ![configurer l’action filtrer le tableau](./media/data-operations/add-configure-filter-array.png)
3. Enregistrez, puis exécutez votre Flow.
   
    Vous pouvez utiliser le [billet](https://www.getpostman.com/postman) pour générer une requête Web qui envoie un tableau JSON à votre Flow.
4. Lorsque votre workflow s’exécute, en supposant que l’entrée JSON ressemble à ce tableau :
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    la sortie ressemble à ce tableau (vous remarquez que seuls les objets dans lesquels *First* est défini sur « Deon » sont inclus dans la sortie de l’action) :
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Utiliser l’action créer un tableau CSV
Utilisez les **opérations de données-créer une table CSV** (créer une table CSV) pour modifier une entrée de tableau JSON en une table de valeurs séparées par des virgules (CSV). Si vous le souhaitez, vous pouvez conserver les en-têtes visibles dans la sortie CSV. Par exemple, vous pouvez convertir le tableau suivant en table CSV en utilisant l’action **créer un tableau CSV** :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Recherchez, ajoutez et configurez les **opérations de données-créer une action de table CSV** pour ressembler à l’image suivante.
   
    ![configurer l’action créer un tableau CSV](./media/data-operations/create-csv-table.png)
   
    Remarque : le jeton de **corps** dans cette image provient d’une action de **réponse de requête/réponse-réponse** . Toutefois, vous pouvez obtenir l’entrée de l’action **créer une table CSV** à partir de la sortie d’une action précédente dans votre workflow, ou vous pouvez l’entrer directement dans le Zone **de** .
2. Enregistrez, puis exécutez votre Flow.
   
    Lors de l’exécution de votre workflow, la sortie **créer un tableau CSV** ressemble à l’image suivante :
   
    ![créer une sortie de table CSV](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Utiliser l’action créer un tableau HTML
Utilisation **des opérations de données-créer un tableau HTML** pour modifier une entrée de tableau JSON en tableau HTML. Si vous le souhaitez, vous pouvez conserver les en-têtes visibles dans la sortie HTML.

Pour ce faire, suivez les étapes de la [section créer un tableau CSV](#use-the-create-csv-table-action) pour obtenir un exemple détaillé. Veillez à utiliser l’action opérations sur les **données-créer un tableau HTML** , au lieu de l’action **opérations sur les données-créer un tableau CSV** .

> [!TIP]
> Si vous envisagez d’envoyer la table HTML par courrier électronique, n’oubliez pas de sélectionner « IsHtml » dans l’action de messagerie.
> 
> 

