---
title: "Inscrire et utiliser des connecteurs personnalisés | Microsoft Docs"
description: "Inscrivez et utilisez des connecteurs personnalisés dans Microsoft Flow, à l’aide de OpenAPI et Postman."
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: sunayv
ms.openlocfilehash: 94d46b2948f03316162e1c1d45860ae94feb897c
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="register-and-use-custom-connectors-in-microsoft-flow"></a>Inscrire et utiliser des connecteurs personnalisés dans Microsoft Flow
Microsoft Flow vous permet de créer des flux de travail sans code. Mais dans certains cas, vous devez étendre les capacités de Microsoft Flow et les services web sont parfaits pour cela. Votre flux peut se connecter à un service, effectuer des opérations et obtenir des données. Lorsque vous disposez d’un service web que vous souhaitez connecter à Microsoft Flow, inscrivez-le en tant que connecteur personnalisé. Ce processus fournit à Microsoft Flow les caractéristiques de votre API web, y compris l’authentification requise, les opérations prises en charge, ainsi que les paramètres et les sorties pour chacune de ces opérations.

Dans cette rubrique, nous allons étudier les étapes requises pour inscrire et utiliser un connecteur personnalisé et nous allons utiliser l’[API Analyse de texte](https://www.microsoft.com/cognitive-services/text-analytics-api) Azure Cognitive Services. Cette API identifie la langue, les sentiments et les expressions clés dans le texte que vous lui transmettez.

## <a name="prerequisites"></a>Conditions préalables
* Un [compte Microsoft Flow](https://flow.microsoft.com).
* Un fichier OpenAPI 2.0 (anciennement Swagger) au format JSON, une URL pointant vers une définition OpenAPI ou un fichier Postman Collection pour votre API. Si vous n’avez aucun de ces éléments, nous vous guiderons.
* Une image à utiliser comme icône du connecteur personnalisé (facultatif).

## <a name="steps-in-the-custom-connector-process"></a>Étapes du processus de création de connecteurs personnalisés
Le processus de création de connecteurs personnalisés comporte plusieurs étapes, que nous décrivons brièvement ci-dessous. Cet article suppose que vous disposez déjà d’une API RESTful avec un certain type d’accès authentifié. Nous allons donc nous concentrer sur les étapes 3 à 6 dans le reste de l’article. Pour un exemple des étapes 1 et 2, consultez [Créer une API web personnalisée pour Microsoft Flow](customapi-web-api-tutorial.md).

1. **Créez une API RESTful** dans le langage et la plateforme de votre choix. Pour les technologies Microsoft, nous vous recommandons l’une des plateformes suivantes (mais le choix vous est propre) :
   
   * Azure Functions
   * Azure Web Apps
   * Azure API Apps
2. **Sécurisez votre API** à l’aide d’un des mécanismes d’authentification suivants. Vous pouvez autoriser l’accès non authentifié à vos connecteurs, mais cela est déconseillé.
   
   * Azure Active Directory. Pour plus d’informations, voir[ Utiliser Azure Active Directory avec un connecteur personnalisé dans Microsoft Flow](customapi-azure-resource-manager-tutorial.md).
   * OAuth 2.0 pour des services spécifiques tels que SalesForce, Facebook et Dropbox
   * OAuth 2.0 générique
   * Clé API
   * Authentification de base
3. **Décrivez votre API** en suivant une des deux méthodes standard du secteur afin que Microsoft Flow puisse s’y connecter.
   
   * Fichier OpenAPI
   * Fichier Postman Collection
     
     Vous pouvez également générer un fichier OpenAPI à l’étape 4 dans le cadre du processus d’inscription.
4. **Inscrivez votre connecteur personnalisé** à l’aide d’un Assistant dans Microsoft Flow, où vous spécifiez une description de l’API, les détails de la sécurité et d’autres informations.
5. **Utilisez votre connecteur personnalisé** dans une application. Créez une connexion au connecteur dans votre application et appelez les opérations fournies par l’API, tout comme vous appelez des connexions standard dans Microsoft Flow.
6. **Partagez votre connecteur personnalisé** comme vous le faites avec d’autres ressources Microsoft Flow. Cette étape est facultative, mais il est souvent judicieux de partager des connecteurs personnalisés entre plusieurs créateurs d’application.

## <a name="describe-your-api"></a>Décrire votre API
En supposant que vous disposez d’une API avec un certain type d’accès authentifié, vous devez décrire l’API afin que Microsoft Flow puisse s’y connecter. Pour ce faire, créez un fichier OpenAPI ou Postman Collection à partir d’*un* point de terminaison d’API REST, y compris :

* Connecteurs disponibles publiquement. En voici quelques exemples : [Spotify](https://developer.spotify.com/), [Uber](https://developer.uber.com/), [Slack](https://api.slack.com/), [Rackspace](http://docs.rackspace.com/), etc.
* Une API que vous créez et déployez sur un fournisseur d’hébergement cloud, notamment Azure, Amazon Web Services (AWS), Heroku, Google Cloud, etc.
* Une API métier personnalisée déployée sur votre réseau, à condition que l’API soit exposée sur l’Internet public.

Les fichiers OpenAPI 2.0 (anciennement Swagger) et Postman Collections utilisent des formats différents, mais les deux sont des documents lisibles indépendants du langage qui décrivent les opérations et les paramètres de votre API :

* Vous pouvez générer ces documents à l’aide d’un large éventail d’outils en fonction du langage et de la plateforme sur lesquels repose votre API. Consultez la [documentation sur l’API Analyse de texte](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure) pour obtenir un exemple de fichier OpenAPI.
* Si vous ne disposez pas de fichier OpenAPI pour votre API et que vous ne souhaitez pas en créer un, vous pouvez facilement créer un connecteur personnalisé à l’aide d’un fichier Postman Collection. Pour plus d’informations, consultez [Créer un fichier Postman Collection](postman-collection.md).
* Comme Microsoft Flow utilise au final OpenAPI en arrière-plan, un fichier Postman Collection est analysé et converti en fichier de définition OpenAPI.

**Remarque** : la taille du fichier doit être inférieure à 1 Mo.

### <a name="getting-started-with-openapi-and-postman"></a>Bien démarrer avec OpenAPI et Postman
* Si vous débutez avec OpenAPI, consultez [Bien démarrer avec OpenAPI](http://swagger.io/getting-started/) sur le site swagger.io.
* Si vous débutez avec Postman, installez l’[application Postman](https://www.getpostman.com/apps) disponible sur leur site.
* Si votre API est générée avec Azure API Apps ou Azure Functions, consultez [Exportation d’une API hébergée sur Azure vers Microsoft Flow](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow) pour plus d’informations.

## <a name="register-your-custom-connector"></a>Inscrire votre connecteur personnalisé
Vous allez utiliser le fichier OpenAPI ou Postman Collection pour créer un connecteur personnalisé dans Microsoft Flow.

1. Dans [flow.microsoft.com](https://flow.microsoft.com), dans la barre supérieure, sélectionnez l’engrenage pour ouvrir le menu Paramètres. Sélectionnez l’option **Connecteurs personnalisés**.
   
    ![Créer un connecteur personnalisé](./media/register-custom-api/managecustomapi.png)  
2. Sélectionnez **Créer un connecteur personnalisé**.
   
    ![Propriétés du connecteur personnalisé](./media/register-custom-api/newcustomapi.png)
3. Sous l’onglet **Général**, choisissez comment vous souhaitez créer un connecteur personnalisé.
   
   * Charger un fichier OpenAPI
   * Coller l’URL OpenAPI
   * Télécharger Postman Collection V1
     
     ![Créer un connecteur personnalisé](./media/register-custom-api/choosehowtocreate.png)
     
     Chargez une icône pour votre connecteur personnalisé. Les champs Description, Hôte et URL de base sont en général automatiquement remplis avec les informations provenant du fichier OpenAPI. S’ils ne sont pas remplis automatiquement, vous pouvez y ajouter des informations. Sélectionnez **Continuer**.
4. Sous l’onglet **Sécurité**, entrez les propriétés d’authentification.
   
    ![Types d’authentification](./media/register-custom-api/authenticationtypes.png)
   
   * Le type d’authentification est rempli automatiquement selon ce qui est défini dans votre objet `securityDefinitions` OpenAPI. Voici un exemple utilisant OAuth2.0.
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "tokenUrl": "https://login.windows.net/common/oauth2/token"
           "scopes": {}
           }
       },
       ```
   * Si le fichier OpenAPI n’utilise pas l’objet `securityDefintions`, il est possible qu’aucune autre valeur ne soit requise.
   * Lorsque vous utilisez un fichier Postman Collection, le type d’authentification est rempli automatiquement uniquement lorsque les types d’authentification pris en charge, tels que OAuth 2.0 ou De base, sont utilisés.
   * Pour obtenir un exemple de configuration de l’authentification Azure Active Directory (AAD), consultez [Créer une API web personnalisée pour Microsoft Flow](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication).
5. Sous l’onglet **Définitions**, toutes les opérations définies dans votre fichier OpenAPI ou Postman Collection, ainsi que les valeurs de demande et de réponse, sont remplies automatiquement. Si toutes vos opérations requises sont définies, vous pouvez passez à l’étape 6 du processus d’inscription sans apporter de modifications à l’écran.
   
    ![Onglet Définition](./media/register-custom-api/definitiontab.png)
   
    Si vous souhaitez modifier les actions existantes ou ajouter de nouvelles actions à votre connecteur personnalisé, poursuivez la lecture de ce document.
   
   1. Si vous souhaitez ajouter une action qui n’était pas déjà dans votre fichier OpenAPI ou Postman Collection, sélectionnez **Nouvelle action** dans le volet gauche et remplissez la section **Général** avec le nom, la description et la visibilité de votre opération.
   2. Dans la section **Demande**, sélectionnez **Importer à partir de l’exemple** dans le coin supérieur droit. Dans le formulaire sur la droite, collez un exemple de demande. Les exemples de demandes sont généralement disponibles dans la documentation de l’API, où vous pouvez obtenir des informations pour remplir les champs **Verbe**, **URL de la demande**, **En-têtes** et **Corps**. Consultez la [documentation sur l’API Analyse de texte](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6) pour obtenir un exemple.
      
      > [!IMPORTANT]
      > Veillez à supprimer l’en-tête `Content-type` des actions, car il est automatiquement ajouté par Microsoft Flow. Les en-têtes d’authentification qui ont été définis dans la section **Sécurité** doivent également être supprimés des actions et déclencheurs. 
      > 
      > 
      
      ![Importer à partir de l’exemple](./media/register-custom-api/importfromsample.png)
   3. Sélectionnez **Importer** pour terminer la définition de la demande. Définissez la réponse de la même façon.
6. Une fois que vous avez défini toutes vos opérations, sélectionnez **Créer** pour créer votre connecteur personnalisé.
7. Une fois que vous avez créé votre connecteur personnalisé, accédez à l’onglet **Tester** pour tester les opérations définies dans l’API. Choisissez une connexion et indiquez des paramètres d’entrée pour tester une opération.
   
    ![Tester un connecteur personnalisé](./media/register-custom-api/testcustomapi.png)
   
    Si l’appel réussit, vous obtenez une réponse valide.
   
    ![Tester la réponse du connecteur](./media/register-custom-api/testapiresponse.png)

### <a name="quota-and-throttling"></a>Quota et limitation
* Consultez la page sur la [tarification de Microsoft Flow](https://flow.microsoft.com/pricing/) pour plus d’informations sur les quotas relatifs à la création de connecteurs personnalisés. Les connecteurs personnalisés qui sont partagés avec vous n’entrent pas dans ce quota.
* Pour chaque connexion créée sur un connecteur personnalisé, les utilisateurs peuvent effectuer jusqu’à 500 demandes par minute.

## <a name="share-your-custom-connector"></a>Partager votre connecteur personnalisé
Maintenant que vous avez un connecteur personnalisé, vous pouvez le partager avec d’autres utilisateurs de votre organisation. N’oubliez pas que lorsque vous partagez un connecteur personnalisé, d’autres utilisateurs peuvent commencer à en dépendre et la suppression d’un connecteur personnalisé supprime toutes les connexions à celui-ci. Si vous souhaitez fournir un connecteur pour les utilisateurs en dehors de votre organisation, consultez la page [Vue d’ensemble de la certification des connecteurs personnalisés dans Microsoft Flow](api-connector-overview.md).

1. Dans [flow.microsoft.com](https://flow.microsoft.com), dans la barre supérieure, sélectionnez l’engrenage pour ouvrir le menu Paramètres. Sélectionnez l’option **Connecteurs personnalisés**.
   
    ![Nouvelle connexion](./media/register-custom-api/managecustomapi.png)
2. Sélectionnez les points de suspension (**...**) en regard de votre connecteur, puis sélectionnez **Afficher les propriétés**.  
   
    ![Afficher les propriétés du connecteur](./media/register-custom-api/view-properties.png)
3. Sélectionnez **Partager**, puis entrez les utilisateurs ou les groupes auxquels vous souhaitez accorder l’accès à votre connecteur.  
   
    ![Partager un connecteur personnalisé](./media/register-custom-api/sharecustomapi.png)
4. Sélectionnez **Enregistrer**.

## <a name="next-steps"></a>Étapes suivantes
[Découvrez comment créer un fichier Postman Collection](postman-collection.md)

[En savoir plus sur les extensions OpenAPI personnalisées](customapi-how-to-swagger.md).

[Utiliser une API web ASP.NET](customapi-web-api-tutorial.md).

[Inscrire une API Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

