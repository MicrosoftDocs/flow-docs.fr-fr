---
title: Filtrer et copier des données | Microsoft Docs
description: Apprenez à filtrer et à copier des données d’une source vers une destination avec Microsoft Flow
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 702fd695a91fdf267f166d5162570b39505dbc91
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690419"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Filtrer et copier des données avec Microsoft Flow
Cette procédure pas à pas montre comment créer un flux qui surveille une source afin de détecter l’ajout ou la modification d’éléments, puis copie ces changements vers une destination. Vous pouvez créer un tel flux si vos utilisateurs entrent des données dans un emplacement, alors que votre équipe doit pouvoir y accéder ailleurs ou dans un autre format.

Si la procédure pas à pas décrite ici copie des données d’une [liste](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) Microsoft SharePoint (source) vers une table [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) (destination), vous pouvez copier des données entre les plus de [150 services](https://flow.microsoft.com/connectors/) que Microsoft Flow prend en charge.

> [!IMPORTANT]
> Les modifications que vous apportez à la destination ne sont pas recopiées vers la source, car les synchronisations bidirectionnelles ne sont pas prises en charge. Si vous tentez de configurer une synchronisation bidirectionnelle, vous créez une boucle infinie dans laquelle les modifications sont échangées indéfiniment entre la source et la destination.
> 
> 

## <a name="prerequisites"></a>Prérequis
* Accès à une source et à une destination de données. Cette procédure pas à pas n’inclut pas les étapes de création de la source et de la destination.
* Accédez à [Microsoft Flow](https://flow.microsoft.com).
* Compréhension élémentaire de la façon dont vos données sont stockées.
* Bonne maîtrise des principes fondamentaux de la création de flux. Nous vous invitons à réviser la manière d’ajouter [des actions, des déclencheurs](multi-step-logic-flow.md#add-another-action) et [des conditions](add-condition.md). Les étapes suivantes supposent que vous savez comment effectuer ces actions.

> [!TIP]
> Les noms de colonnes ne doivent pas nécessairement correspondre dans la source et la destination, mais vous devez fournir des données pour toutes les colonnes *obligatoires* lorsque vous insérez ou mettez à jour un élément. Microsoft Flow identifie les champs obligatoires à votre place.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Vue d’ensemble rapide des étapes
Si vous êtes familiarisé avec Microsoft Flow, utilisez les étapes rapides suivantes pour copier des données d’une source à une autre :

1. Identifiez la source à surveiller et la destination vers laquelle copier les données modifiées. Vérifiez que vous avez accès aux deux.
2. Repérez au moins une colonne identifiant de façon unique les éléments dans la source et la destination. Dans l’exemple qui suit, nous utilisons la colonne **Titre**, mais vous pouvez utiliser les colonnes de votre choix.
3. Configurez un déclencheur qui surveille les modifications apportées à la source.
4. Recherchez dans la destination pour déterminer si l’élément modifié s’y trouve.
5. Utilisez une **Condition** telle que celles-ci :
   * Si l’élément nouveau ou modifié n’existe pas dans la destination, le créer.
   * Si l’élément nouveau ou modifié existe dans la destination, le mettre à jour.
6. Déclenchez votre flux, puis vérifiez que les éléments nouveaux ou modifiés sont copiés de la source vers la destination.

> [!NOTE]
> Si vous n’avez pas créé de connexion à SharePoint ou à Azure SQL Database précédemment, suivez les instructions lorsque vous êtes invité à vous connecter.
> 
> 

Voici la procédure détaillée de création du flux.

## <a name="monitor-the-source-for-changes"></a>Surveiller les modifications apportées à la source
1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), sélectionnez **Mes flux** > **Créer entièrement**.
2. Recherchez **SharePoint** > sélectionnez le déclencheur **SharePoint - Lorsqu’un élément est créé ou Lorsqu’un élément existant est modifié** dans la liste des déclencheurs.
3. Entrez l’**Adresse de Site**, puis sélectionnez le **Nom de la liste** sur la carte **Lorsqu’un élément est créé ou Lorsqu’un élément existant est modifié**.
   
    Sélectionnez l’**Adresse du site** et le **Nom de la liste** SharePoint dans laquelle votre flux surveille les éléments nouveaux ou mise à jour.
   
    ![configurer un déclencheur sharepoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Rechercher la destination de l’élément nouveau ou modifié
Nous utilisons l’action **SQL Server - Obtenir les lignes** pour rechercher la destination de l’élément nouveau ou modifié.

1. Sélectionnez **Nouvelle étape** > **Ajouter une action**.
2. Recherchez **Obtenir les lignes**, sélectionnez **SQL Server - Obtenir les lignes**, puis choisissez la table à surveiller dans la liste **Nom de la table**.
3. Sélectionnez **Afficher les options avancées**.
4. Dans le champ **Requête de filtre**, entrez **Title eq ’**, sélectionnez le jeton **Titre** dans la liste de contenu dynamique, puis entrez **’**.
   
    L’étape précédente suppose que vous établissiez une correspondance entre les Titres des lignes dans la source et la destination.
   
    La carte **Obtenir les lignes** doit à présent ressembler à cette image :
   
    ![essayer d’obtenir l’élément à partir de la base de données de destination](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Vérifier si l’élément nouveau ou modifié a été trouvé
Sélectionnez **Nouvelle étape** > **Ajouter une condition** pour ouvrir la carte **Condition**.

Sur la carte de condition :

1. Activez la case à cocher à gauche.
   
    La liste **Ajoutez du contenu dynamique des applications et des connecteurs utilisés dans ce flux** s’ouvre.
2. Sélectionnez **value** dans la catégorie **Obtenir les lignes**.
   
   > [!TIP]
   > Vérifiez que vous avez sélectionné **value** dans la catégorie **Obtenir les lignes**. Ne sélectionnez pas **value** dans la catégorie **Lorsqu’un élément est créé ou Lorsqu’un élément existant est modifié**.
   > 
   > 
3. Sélectionnez **is equal to** (est égal à) dans la liste de la zone centrale.
4. Entrez **0** (zéro) dans le champ à droite.
   
    La carte **Condition** ressemble à présent à cette image :
   
    ![configurer une condition](media/odata-filters/configure-condition.png)
5. Sélectionnez **Modifier en mode Avancé**.
   
    Lorsque le mode Avancé s’ouvre, vous voyez l’expression **\@equals(body('Get_rows')?['value'], 0)** dans la zone. Modifiez cette expression en ajoutant **length()** à la fonction **body(’Get_items’)?[’value’]**. L’expression entière est à présent : **@equals(length(body(’Get_rows’)?[’value’]), 0)**
   
    La carte **Condition** ressemble à présent à cette image :
   
    ![configurer une condition](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > L’ajout de la fonction **length()** permet au flux de vérifier la liste **value** afin de déterminer si elle contient des éléments.
   > 
   > 

Lorsque votre flux « obtient » des éléments de la destination, deux résultats sont possibles.

| Résultat | Étape suivante |
| --- | --- |
| L’élément existe |[Mettre à jour l’élément](odata-filters.md#update-the-item-in-the-destination) |
| L’élément n’existe pas |[Créer un élément](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> Les images des cartes **Insérer une ligne** et **Mettre à jour la ligne** présentées ci-après peuvent différer des vôtres, car elles affichent les noms des colonnes de la table Azure SQL Database utilisée dans le flux.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Créer l’élément dans la destination
Si l’élément n’existe pas dans la destination, créez-le à l’aide de l’action **SQL Server - Insérer une ligne**.

Dans la branche **Si Oui** de la **Condition** :

1. Sélectionnez **Ajouter une action**, recherchez **Insérer une ligne**, puis choisissez **SQL Server - Insérer une ligne**.
   
    La carte **Insérer une ligne** s’ouvre.
2. Dans la liste **Nom de la table**, sélectionnez la table dans laquelle insérer le nouvel élément.
   
    La carte **Insérer une ligne** se développe pour afficher tous les champs de la table sélectionnée. Les champs assortis d’un astérisque (*) sont obligatoires et doivent être remplis pour que la ligne soit valide.
3. Sélectionnez chaque champ à remplir, puis entrez les données.
   
    Dans les champs, vous pouvez saisir les données manuellement, sélectionner un ou plusieurs jetons du **Contenu dynamique**, ou entrer une combinaison quelconque de texte et de jetons.
   
    La carte **Insérer une ligne** ressemble maintenant à l’image suivante :
   
    ![configurer une condition](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Mettre à jour l’élément dans la destination
Si l’élément existe dans la destination, mettez-le à jour avec les modifications.

1. Ajoutez l’action **SQL Server - Mettre à jour la ligne** à la branche **Si Non** de la **Condition**.
2. Suivez les étapes décrites dans la section [Créer l’élément](odata-filters.md#create-the-item-in-the-destination) de ce document pour remplir les champs de la table.
   
    ![afficher les environnements](media/odata-filters/update-row.png)
3. En haut de la page, entrez un nom pour votre flux dans le champ **Nom de flux**, puis sélectionnez **Créer un flux** pour l’enregistrer.
   
    ![nommer votre flux](media/odata-filters/give-the-flow-a-name.png)

Désormais, chaque fois qu’un élément figurant dans votre liste SharePoint (source) change, votre flux est déclenché et insère un nouvel élément ou met à jour un élément existant dans votre table Azure SQL Database (destination).

> [!NOTE]
> Votre flux n’est pas déclenché en cas de suppression d’un élément dans la source. Si ce scénario est important, envisagez d’ajouter une colonne distincte indiquant quand un élément n’est plus nécessaire.
> 
> 

## <a name="learn-more"></a>En savoir plus
Utilisez des [opérations sur les données](data-operations.md) dans vos flux.

