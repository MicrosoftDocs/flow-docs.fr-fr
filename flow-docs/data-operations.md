---
title: Présentation des opérations sur les données | Microsoft Docs
description: Découvrez comment effectuer des opérations, telles que créer un tableau HTML, créer un tableau CSV, composer un message, joindre, sélectionner et filtrer un tableau avec Microsoft Flow.
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
ms.openlocfilehash: aa3f61d09cb5e9b8d07124838883da9b5b9794ab
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440908"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Utiliser des opérations sur les données avec Microsoft Flow
Dans cette procédure pas à pas, découvrez certaines opérations sur les données courantes de Microsoft Flow (telles que composer un message, joindre, sélectionner, filtrer un tableau, créer un tableau et analyser JSON) qui sont disponibles pour manipuler des données lorsque vous créez des flux.

## <a name="prerequisites"></a>Prérequis
* Accédez à Microsoft Flow.
* Un outil tel que [PostMan](https://www.getpostman.com/postman) pour envoyer des requêtes HTTP POST avec un tableau JSON à votre flux.

## <a name="use-the-compose-action"></a>Utiliser l’action « message »
Utilisez l’action **Opérations sur les données - Message** pour vous éviter de devoir saisir des données identiques plusieurs fois lorsque vous créez un flux. Par exemple, si vous devez entrer un tableau de chiffres : ````[0,1,2,3,4,5,6,7,8,9]```` plusieurs fois pendant la conception de votre flux, vous pouvez utiliser l’action « message » pour enregistrer le tableau comme suit :

1. Recherchez **Message**, puis sélectionnez l’action **Opérations sur les données - Message**.
   
    ![rechercher et sélectionner l’action « message »](./media/data-operations/search-select-compose.png)
2. Entrez le tableau dans la zone **Entrées** que vous souhaitez référencer ultérieurement :
   
    ![configurer l’action « message »](./media/data-operations/add-array-compose.png)

> [!TIP]
> Pour vous y référer facilement plus tard, renommez la carte **Message** en cliquant sur le texte « Message » dans la barre de titre de la carte **Message**.
> 
> 

Lorsque vous avez besoin d’accéder au contenu de l’action de message, faites-le via le jeton **Output** (Sortie) de la liste **Ajoutez du contenu dynamique des applications et connecteurs utilisés dans ce flux** en suivant les étapes ci-dessous :

1. Ajoutez une action telle que **Opérations sur les données - Rejoindre**.
2. Sélectionnez le contrôle auquel vous souhaitez ajouter le contenu que vous avez enregistré dans l’action « message ».
   
    La fenêtre **Ajoutez du contenu dynamique des applications et connecteurs utilisés dans ce flux** s’ouvre.
3. Dans **Ajouter du contenu dynamique des applications et connecteurs utilisés dans ce flux**, sélectionnez le jeton **Output** (Sortie) qui est situé sous la catégorie **Message** de l’onglet **Contenu dynamique**.
   
    ![utiliser la sortie à partir de l’action « message »](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Utiliser l’action « rejoindre »
Utilisez l’action **Opérations sur les données - Rejoindre** pour délimiter un tableau avec un séparateur de votre choix. Par exemple, supposons que votre flux reçoit une requête web qui inclut le tableau suivant composé d’adresses de courrier : ````["d@example.com", "k@example.com", "dal@example.com"]````. Toutefois, dans votre programme de messagerie, les adresses doivent être fournies sous la forme d’une chaîne unique dont les valeurs sont séparées par des points-virgules. Pour ce faire, utilisez l’action **Opérations sur les données - Rejoindre** pour remplacer la virgule par un point-virgule (« ; ») comme séparateur, en procédant comme suit :

1. Ajoutez une nouvelle action, recherchez **Rejoindre**, puis sélectionnez **Opérations sur les données - Rejoindre**.
   
    ![rechercher et sélectionner l’action « rejoindre »](./media/data-operations/search-select-join.png)
2. Entrez le tableau dans la zone **De** et entrez le nouveau délimiteur que vous souhaitez utiliser dans la zone **Joindre avec**.
   
    Ici, j’ai utilisé le point-virgule (;) comme nouveau délimiteur.
   
    ![configurer l’action « rejoindre »](./media/data-operations/add-array-join.png)
3. Enregistrez votre flux, puis exécutez-le.
4. Après l’exécution de votre flux, la sortie de l’action **Opérations sur les données - Rejoindre** est comme suit :
   
    ![sortie de l’action Rejoindre](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Utiliser l’action « sélectionner »
Utilisez l’action **Opérations sur les données - Sélectionner** pour transformer la forme des objets d’un tableau. Par exemple, vous pouvez ajouter, supprimer ou renommer des éléments dans chaque objet d’un tableau.

> [!NOTE]
> Même si vous pouvez ajouter ou supprimer des éléments à l’aide de l’action « sélectionner », vous ne pouvez pas modifier le nombre d’objets dans le tableau.
> 
> 

Par exemple, vous pouvez utiliser l’action « sélectionner » si les données entrent dans votre flux au moyen d’une requête web au format suivant :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

et que vous voulez remodeler les données entrantes en renommant « first » en « FirstName », « last » en « LastName » et ajouter un nouveau membre nommé « FamilyName » qui associe « first » et « last » (séparés par un espace) :

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Pour ce faire :

1. Ajoutez ’action **Requête/réponse - réponse** (requête) à votre flux.
2. Sélectionnez **Utiliser l’exemple de charge utile pour générer le schéma** dans la carte **Demande**.
3. Dans la zone qui s’affiche, collez un exemple de votre tableau de données source, puis sélectionnez le bouton **Terminé**.
4. Ajoutez l’action **Opérations sur les données - Sélectionner**, puis configurez-la comme dans l’image suivante.
   
    ![configurer l’action « sélectionner »](./media/data-operations/select-card.png)
   
   > [!TIP]
   > La sortie de l’action « sélectionner » est un tableau qui contient les objets qui viennent d’être mis en forme. Vous pouvez ensuite utiliser ce tableau dans une autre action, telle que **Message**, traitée plus haut.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Utiliser l’action « filtrer un tableau »
Utilisez l’action **Opérations sur les données - Filtrer un tableau** afin de réduire le nombre d’objets d’un tableau en un sous-ensemble qui correspond aux critères que vous fournissez.

> [!NOTE]
> L’action « Filtrer un tableau » ne peut pas être utilisée pour modifier la forme des objets dans un tableau. De plus, le texte que vous utilisez comme filtre respecte la casse.
> 
> 

Par exemple, vous pouvez utiliser l’action « Filtrer un tableau » sur le tableau suivant :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

pour créer un tableau qui contient uniquement les objets où *first* est défini sur « Deon ».

Pour ce faire :

1. Recherchez et ajoutez l’action **Opérations sur les données - Filtrer un tableau** à votre flux.
2. Configurez l’action Filtrer un tableau comme dans l’image suivante.
   
    ![configurer l’action « filtrer un tableau »](./media/data-operations/add-configure-filter-array.png)
3. Enregistrez et exécutez votre flux.
   
    Vous pouvez utiliser [PostMan](https://www.getpostman.com/postman) pour générer une requête web qui envoie un tableau JSON à votre flux.
4. Lorsque votre flux s’exécute, en supposant que l’objet JSON entré ressemble à ce tableau :
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    la sortie ressemble à ce tableau (notez que seuls les objets où *first* est défini sur « Deon » sont inclus dans la sortie de l’action) :
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Utiliser l’action « créer un tableau csv »
Utilisez l’action **Opérations sur les données - Créer un tableau CSV** pour convertir une entrée de tableau JSON en tableau CSV (valeurs séparées par des virgules). Si vous le souhaitez, vous pouvez conserver les en-têtes visibles dans la sortie CSV. Par exemple, vous pouvez convertir le tableau suivant en tableau CSV à l’aide de l’action **Créer un tableau CSV** :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Trouvez, ajoutez, puis configurez l’action **Opérations sur les données - Créer un tableau CSV** comme dans l’image suivante.
   
    ![configurer l’action « créer un tableau csv »](./media/data-operations/create-csv-table.png)
   
    Remarque : le jeton **Corps** de cette image provient d’une action **Requête/réponse - réponse**. Toutefois, vous pouvez obtenir l’entrée de l’action **Créer un tableau CSV** à partir de la sortie de l’action précédente de votre flux, ou vous pouvez la saisir directement dans la zone **De**.
2. Enregistrez et exécutez votre flux.
   
    Lors de l’exécution de votre flux, la sortie **Créer un tableau CSV** ressemble à l’image suivante :
   
    ![Sortie Créer un tableau csv](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Utiliser l’action « créer un tableau html »
Utilisez l’action **Opérations sur les données - Créer un tableau HTML** pour convertir une entrée de tableau JSON en tableau HTML. Si vous le souhaitez, vous pouvez conserver les en-têtes visibles dans la sortie HTML.

Pour ce faire, suivez les étapes de la section [Créer un tableau csv](#use-the-create-csv-table-action) pour obtenir un exemple détaillé. Veillez à utiliser l’action **Opérations sur les données - Créer un tableau HTML**, au lieu de l’action **Opérations sur les données - Créer un tableau CSV**.

> [!TIP]
> Si vous envisagez d’envoyer le tableau HTML par courrier, pensez à sélectionner « IsHtml » dans l’action de messagerie.
> 
> 

