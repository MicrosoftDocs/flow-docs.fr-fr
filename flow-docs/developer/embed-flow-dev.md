---
title: Intégrer Microsoft Flow à des sites web et applications | Microsoft Docs
description: Incorporez les expériences Microsoft Flow dans votre application ou site web.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 47d44b2c97275add492153d85138b7d11b554530
ms.sourcegitcommit: 3c7822c7207cfa51d0274e9647ef02e5ea1d999f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58321407"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Intégrer Microsoft Flow à des sites web et applications

Intégrez Microsoft Flow à votre application ou site web à l’aide de *widgets de flux* afin de donner aux utilisateurs un moyen simple d’automatiser leurs tâches personnelles ou professionnelles.

Les widgets de flux sont des iFrames situés dans un document hôte. Ce document pointe vers une page dans le concepteur Microsoft Flow. Ces widgets intègrent des fonctionnalités spécifiques de Microsoft Flow dans l’application tierce.

Il y a des widgets simples, comme ceux qui affichent une liste de modèles sans aucune communication entre l’hôte et l’iFrame. Et il y a des widgets complexes. C’est le cas, par exemple, des widgets qui provisionnent un flux à partir d’un modèle et déclenchent ensuite le flux via une communication bidirectionnelle entre l’hôte et le widget.

## <a name="prerequisites"></a>Prérequis

- Un **compte Microsoft** ou
- Un compte professionnel ou scolaire

## <a name="use-the-unauthenticated-widget"></a>Utiliser le widget non authentifié
Pour utiliser un temple non authentifié, incorporez-le directement à l’application hôte dans un iFrame. Vous n’avez pas besoin d’un SDK JS ni d’un jeton d’accès. 

### <a name="show-templates-for-your-scenarios"></a>Afficher les modèles pour vos scénarios
Pour commencer, ajoutez le code suivant pour afficher les modèles Microsoft Flow sur votre site web :

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

| Paramètre | Description |
| --- | --- |
| paramètres régionaux |Code de langue et de région de quatre lettres pour la vue du modèle. Par exemple, `en-us` représente l’anglais des États-Unis et `de-de` correspond à l’allemand. |
| terme de recherche |Terme de recherche pour les modèles que vous souhaitez afficher dans la vue. Par exemple, recherchez `wunderlist` pour afficher les modèles pour Wunderlist. |
| nombre de modèles |Nombre de modèles que vous souhaitez afficher dans la vue. |
| destination |Page qui s’affiche quand les utilisateurs sélectionnent le modèle. Entrez `details` pour afficher les détails relatifs au modèle, ou `new` pour ouvrir le concepteur Microsoft Flow. |
| parameters.{name} |Contexte supplémentaire à transmettre au flux. |
| templateCategory | Filtre sur la catégorie de modèle spécifiée                     | 

Si le paramètre de destination est `new`, le concepteur Microsoft Flow s’ouvre quand les utilisateurs sélectionnent un modèle. Les utilisateurs peuvent ensuite créer un flux dans le concepteur. Consultez la section suivante pour voir le fonctionnement complet depuis le widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passer des paramètres supplémentaires au modèle de flux

Si l’utilisateur se trouve dans un contexte particulier de votre site web ou application, vous pouvez passer ce contexte au flux. Par exemple, un utilisateur peut ouvrir un modèle *M’avertir lorsqu’un élément est ajouté à une liste* quand il consulte une liste donnée dans Wunderlist. Effectuez ces étapes pour passer l’ID de liste comme *paramètre* au flux :

1. Définissez le paramètre dans le modèle de flux avant de le publier. Voici à quoi ressemble un paramètre : `@{parameters('parameter_name')}`.
1. Transmettez le paramètre dans iframe src. Par exemple, ajoutez `&parameters.listName={the name of the list}` si vous avez un paramètre appelé **listName**.

### <a name="full-sample"></a>Exemple complet

Pour afficher les quatre premiers modèles Wunderlist en allemand et présenter **myCoolList** en premier à l’utilisateur, utilisez ce code :

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Utiliser les widgets de flux authentifiés

Le tableau suivant liste les widgets Microsoft Flow qui prennent en charge les fonctionnalités de widget complètes avec le jeton d’accès d’authentification utilisateur. Vous avez besoin du Kit de développement logiciel JavaScript (SDK JS) de Microsoft Flow pour incorporer les widgets et fournir le jeton d’accès utilisateur nécessaire.

| Type de widget    | Fonctionnalité prise en charge                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Flux          | Affiche une liste des flux personnels et partagés dans un onglet. Vous pouvez modifier un flux existant, ou créer un autre flux à partir d’un modèle ou de zéro. | 
| Création de flux   | Crée un flux à partir d’un ID de modèle fourni par l’application hôte.                                                                | 
| Exécution        | Déclenche un flux avec déclencheur manuel ou hybride fourni par l’application hôte.                                                        | 
| Centre d’approbations | Incorpore les demandes d’approbations et les approbations envoyées.                                                                                        | 
| Modèles      | Affiche une liste de modèles. L’utilisateur en choisit un pour créer un flux.                                                                         | 

Utilisez le SDK Flow authentifié pour permettre aux utilisateurs de créer et gérer des flux directement depuis votre application ou site web (au lieu de passer par le portail Microsoft Flow). Vous devez connecter les utilisateurs avec leur compte Microsoft ou Azure Active Directory pour utiliser le SDK authentifié.

> [!NOTE]
> Il n’existe aucun moyen de masquer la marque Microsoft Flow quand vous utilisez des widgets.

## <a name="widget-architecture"></a>Architecture d’un widget

Les widgets Microsoft Flow incorporent des iFrames référençant Microsoft Flow dans une application hôte. L’hôte fournit le jeton d’accès qui est demandé par le widget Microsoft Flow. Le SDK JS de Microsoft Flow permet à l’application hôte d’initialiser et de gérer le cycle de vie du widget.

![architecture d’un widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Présentation du SDK JS

L’équipe Microsoft Flow fournit le SDK JS pour faciliter l’intégration des widgets Flow dans les applications tierces. Le SDK JS de Microsoft Flow est disponible par le biais d’un lien public dans le service Flow. Avec ce SDK, l’application hôte peut traiter les événements reçus du widget et interagir avec l’application Flow en envoyant des actions au widget. Les événements et actions du widget sont différents selon le type du widget utilisé.

### <a name="widget-initialization"></a>Initialisation du widget

La référence au SDK JS de Microsoft Flow doit être ajoutée dans l’application hôte avant d’initialiser le widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Créez une instance du SDK JS en passant les valeurs facultatives hostName et locale dans un objet JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US',
}); 
```

| Nom     | Obligatoire/Facultatif | Description                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Facultatif          | Nom d’hôte Microsoft Flow, par exemple, https://flow.microsoft.com        | 
| `locale`   | Facultatif          | Code de langue du client pour le widget (`en-Us` par défaut si aucune valeur n’est passée) | 


Une fois que vous avez créé l’instance du SDK JS, vous pouvez initialiser et incorporer un widget Microsoft Flow dans un élément parent dans l’application hôte. Pour cela, ajoutez un élément div HTML :

```html
<div id="flowDiv" class="flowContainer"></div>
```

Ensuite, initialisez le widget Microsoft Flow avec la méthode renderWidget() du SDK JS. N’oubliez pas de spécifier le type de widget et les paramètres correspondants.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flow-div',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {},
});
```

Voici un exemple de style de conteneur que vous pouvez adapter aux dimensions de l’application hôte.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

La méthode `renderWidget()` prend les paramètres suivants : 

| Paramètre        | Obligatoire/Facultatif | Description                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obligatoire          | ID d’un élément div dans la page hôte où le widget sera incorporé                      | 
| `environmentId`    | Facultatif          | Un ID d’environnement doit être spécifié pour le widget. Si vous n’en indiquez pas, un environnement par défaut est utilisé. | 
| `flowsSettings`    | Facultatif          | Objet de paramètres de Microsoft Flow                                                                        | 
| `templateSettings` | Facultatif          | Objet de paramètres de modèle                                                                    | 
| `approvalSettings` | Facultatif          | Objet de paramètres d’approbation                                                                    | 

### <a name="access-tokens"></a>Jetons d’accès

Après l’exécution de la méthode `renderWidget()` du SDK JS, le SDK JS initialise un iFrame qui pointe vers l’URL du widget Microsoft Flow. Cette URL contient tous les paramètres définis dans les paramètres de la chaîne de requête. L’application hôte doit obtenir un jeton d’accès de Microsoft Flow pour l’utilisateur (jeton JWT Azure Active Directory avec l’audience https://service.flow.microsoft.com)) avant d’initialiser le widget. Le widget déclenche un événement `GET_ACCESS_TOKEN` pour demander un jeton d’accès à l’hôte. L’hôte doit traiter l’événement et passer le jeton au widget :

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

L’application hôte doit gérer le jeton et le passer au widget demandeur avant la date d’expiration du jeton. Si le widget reste ouvert pendant une période plus longue, l’hôte doit vérifier si le jeton a expiré et, le cas échéant, actualiser le jeton avant de le passer au widget.

### <a name="detecting-if-the-widget-is-ready"></a>Détecter si le widget est prêt

Une fois qu’il a été initialisé, le widget déclenche un événement pour signaler que le widget est prêt. L’hôte peut alors écouter l’événement `WIDGET_READY` et exécuter le code supplémentaire éventuel de l’hôte.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Paramètres du widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings permet de personnaliser les fonctionnalités du widget Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Paramètre | Obligatoire/Facultatif | Description | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obligatoire | Utilise le GUID du modèle quand l’utilisateur sélectionne le bouton **Créer entièrement** sur le widget Flow | 
| `flowsFilter` | Facultatif | Le widget Microsoft Flow applique le filtre spécifié pour afficher les flux. Par exemple, vous pouvez choisir d’afficher les flux qui référencent un site SharePoint spécifique. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Facultatif | Définit l’onglet actif à afficher par défaut dans le widget Microsoft Flow. <br /> Par exemple, <br /> ```tab:'sharedFlows' ``` affiche l’onglet Team<br /> et ``` tab:'myFlows' ``` affiche l’onglet My flows. |   

### <a name="templatessettings"></a>TemplatesSettings 

Ces paramètres s’appliquent à tous les widgets qui vous permettent de créer des flux à partir d’un modèle, y compris les widgets de flux, de création de flux et de modèles.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Paramètre |Obligatoire/Facultatif | Description                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Facultatif          | Paramètres de conception à utiliser pour créer un flux à partir d’un modèle. Par exemple : <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Facultatif          | Les valeurs valides sont 'new' ou 'details'. Quand la valeur est définie à 'details', une page de détails s’affiche lors de la création d’un flux à partir d’un modèle.     |
| `pageSize` | Facultatif          | Nombre de modèles à afficher. La valeur par défaut est 6 | 
| `searchTerm` | Facultatif          | Affiche les modèles correspondant au terme de recherche spécifié| 
| `templateCategory` | Facultatif          | Affiche les modèles d’une catégorie spécifique| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

S’applique aux widgets du Centre d’approbations.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Paramètre | Obligatoire/Facultatif | Description | 
|------------|-------------------|--------------| 
| `hideLink`| Facultatif | Quand la valeur est `true`, le widget masque les liens d’approbation reçus et envoyés | 
| `autoNavigateToDetails`| Facultatif | Quand la valeur est `true`, le widget ouvre automatiquement les détails de l’approbation (s’il n’y a qu’une seule approbation) | 
| `approvalsFilter`| Facultatif | Le widget d’approbation applique le filtre d’approbation spécifié pour afficher les approbations. Par exemple :    Le widget d’approbation applique le filtre d’approbation spécifié pour afficher les approbations. Par exemple : <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Facultatif | Définit l’onglet actif à afficher par défaut dans le widget Flow. <br/> Valeurs valides : 'receivedApprovals', 'sentApprovals' | 
| `showSimpleEmptyPage`| Facultatif | Affiche une page vide s’il n’y a aucune approbation | 
| `hideInfoPaneCloseButton` | Facultatif | Masque le bouton Fermer dans le volet d’informations (ou si l’hôte a déjà un bouton Fermer) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Événements du widget

Le widget Microsoft Flow prend en charge les événements qui permettent à l’hôte d’écouter les événements de cycle de vie du widget. Le widget Microsoft Flow prend en charge deux types d’événements : les événements de notification unidirectionnels (par exemple, Widget\_Ready) et les événements déclenchés à partir du widget pour récupérer (fetch) des données de l’hôte (Get\_Access\_Token). L’hôte doit utiliser la méthode widget.listen() pour écouter les événements spécifiques déclenchés à partir du widget.

### <a name="usage"></a>Utilisation

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Événements pris en charge par type de widget

| Événement du widget      | Détails                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget chargé correctement                                      | 
| `WIDGET_RENDERED`   | Widget chargé et rendu de l’interface utilisateur terminé                      | 
| `GET_ACCESS_TOKEN`  | Demande du widget pour incorporer le jeton d’accès utilisateur                      | 
| `GET_STRINGS`       | Permet à l’hôte de substituer un ensemble de chaînes d’interface utilisateur affichées dans le widget | 

### <a name="runtime-widget"></a>Widget d’exécution

| Événement du widget                    | Détails                                     | Données                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Exécution du flux déclenchée et démarrée      |           | 
| `RUN_FLOW_COMPLETED`              | Exécution du flux déclenchée et terminée avec succès             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Bouton Terminé sélectionné par l’utilisateur à l’exécution du flux       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Bouton Annuler sélectionné par l’utilisateur à l’exécution du flux     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Création du flux réussie           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Déclenché quand l’hôte doit fermer le widget |       | 

### <a name="flow-creation-widget"></a>Widget de création de flux

| Événement du widget             | Détails                                  | Données  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Échec de la création du flux                     |       | 
| `WIDGET_CLOSE`             | Déclenché quand l’hôte doit fermer le widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Échec du chargement du modèle              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Création du flux réussie        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget d’approbation

| Événement du widget                      | Détails                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Changement de l’état de l’approbation reçue  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Changement de l’état de l’approbation envoyée      | 

Avec l’événement **GET\_STRINGS**, vous pouvez personnaliser le texte de certaines chaînes d’interface utilisateur affichées dans le widget. Voici les chaînes personnalisables :

| Clé de chaîne                     | Utilisation dans le widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texte affiché sur le bouton Créer un flux dans le widget de création de flux et le widget d’exécution                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Valeur initiale à utiliser pour le nom du flux dans le widget de création de flux. Utilisée uniquement quand le paramètre allowCustomFlowName est activé. | 
| `FLOW_CREATION_HEADER`           | En-tête à utiliser pour créer un flux dans le widget de création de flux et le widget d’exécution                                                    | 
| `INVOKE_FLOW_HEADER`             | En-tête à utiliser pour appeler un flux dans le widget d’exécution                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texte affiché sur le bouton utilisé pour appeler/exécuter un flux dans le widget d’exécution                                                       | 

### <a name="example"></a>Exemple

Appelez `widgetDoneCallback` en passant un objet JSON avec des paires clé-valeur de la clé de chaîne et du texte devant remplacer la valeur par défaut.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Actions du widget

L’hôte utilise des actions de widget pour envoyer un message ou une action spécifique au widget. Le SDK JS du widget fournit la méthode `notify()` pour envoyer un message ou une charge utile JSON au widget. Chaque action de widget prend en charge une signature de charge utile spécifique.

### <a name="usage"></a>Utilisation

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Exemple 

Appelez un flux en envoyant la commande suivante à un widget d’exécution : 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget d’exécution

| Action du widget                               | Détails                                                      | Interface de paramètre  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Déclenche l’exécution d’un flux                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Déclenche l’exécution d’un flux à partir d’un modèle                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtient le schéma du déclencheur d’un flux                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Annule toute activité en attente et déclenche un événement WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget de création de flux

| Action du widget                               | Détails                                                      | Interface de paramètre  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crée un flux pour le modèle sélectionné                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crée un flux pour la définition de modèle sélectionnée          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Annule toute activité en attente et déclenche un événement WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget d’approbation

| Action du widget  | Détails                                           | Interface de paramètre  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Ferme le volet d’informations où sont affichés les détails de l’approbation  | Non applicable                  | 

## <a name="configuring-your-client-application"></a>Configurer votre application cliente

Vous devez configurer votre application cliente avec des cadres (scopes) du service Flow (permissions déléguées). Si l’application AAD (Azure Active Directory) utilisée pour l’intégration de widget utilise un flux d’autorisation « octroi d’un code », l’application AAD doit être préconfigurée avec des permissions déléguées prises en charge par Microsoft Flow. Ces permissions déléguées permettent à l’application d’effectuer ces opérations :

-   Gérer les approbations
-   Lire les approbations
-   Lire les activités
-   Gérer les flux
-   Lire les flux

Effectuez ces étapes pour sélectionner une ou plusieurs permissions déléguées :

1.  Accédez à https://portal.azure.com 
2.  Sélectionnez **Azure Active Directory**.
3.  Sélectionnez **Inscriptions d’applications** sous **Gérer**.
4.  Entrez l’application tierce à configurer avec des cadres du service Flow.
5.  Sélectionnez **Paramètres**.
      ![architecture d’un widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Sélectionnez **Autorisations requises** sous **Accès API**/
7. Sélectionnez **Ajouter**.
8. Choisissez **Sélectionner une API**.
      ![architecture d’un widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Recherchez l’entrée **Service Microsoft Flow** et sélectionnez-la. Remarque : Le service Microsoft Flow est listé uniquement si votre locataire a au moins un utilisateur AAD connecté au portail Flow (<https://flow.microsoft.com>)
10. Choisissez les cadres du service Flow nécessaires pour votre application, puis sélectionnez **Enregistrer**.
      ![architecture d’un widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Votre application obtient maintenant un jeton du service Flow qui contient les permissions déléguées dans la revendication \'scp' définie dans le jeton JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Exemple d’application pour l’incorporation de widgets de flux 

L’exemple d’application monopage (SPA) JavaScript fourni dans la section Ressources vous permettra d’expérimenter l’incorporation de widgets de flux dans une page hôte. L’utilisation de l’exemple d’application nécessite l’inscription d’une application AAD avec le flux d’octroi implicite activé.

### <a name="registering-an-aad-app"></a>Inscription d’une application AAD

1.  Connectez-vous au [portail Azure](https://portal.azure.com/).
2.  Dans le volet de navigation de gauche, sélectionnez **Azure Active Directory**, puis sélectionnez **Inscriptions d’applications** (préversion) \>Nouvelle inscription.
3.  Quand la page **Inscrire une application** s’affiche, entrez un nom pour votre application.
4.  Sous **Types de comptes pris en charge**, sélectionnez **Comptes** dans l’annuaire organisationnel de votre choix.
5.  Sous la section **URL de redirection**, sélectionnez la plateforme web et définissez la valeur sur l’URL de l’application appropriée pour votre serveur web.  Définissez cette valeur sur http://localhost:30662/ pour exécuter l’exemple d’application.
6.  Sélectionnez **Inscrire**.
7.  Dans la page **Vue d’ensemble** de l’application, notez la valeur de l’ID de l’application (cliente).
8.  L’exemple nécessite que le [flux d’octroi implicite](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) soit activé. Dans le volet de navigation de gauche de l’application inscrite, sélectionnez **Authentification**.
9.  Dans **Paramètres avancés**, sous **Octroi implicite**, cochez les cases **Jetons d’ID** et **Jetons d’accès**. Les jetons d’ID et les jetons d’accès sont nécessaires dans la mesure où cette application doit connecter les utilisateurs et appeler l’API Flow.
10. Sélectionnez **Enregistrer**.

### <a name="running-the-sample"></a>Exécution de l’exemple
<!-- todo where should I download from? -->
<!-- todo is this a misspelling: applicaionConfig -->
1.  Téléchargez l’exemple et copiez-le dans un dossier local sur votre appareil.
2.  Ouvrez le fichier index.html situé sous le dossier FlowSDKSample et modifiez l’objet `applicaionConfig` pour changer la valeur `clientID` par l’ID de l’application que vous avez inscrite précédemment.
    ![architecture d’un widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  L’exemple d’application est configuré pour utiliser les cadres du service Flow **Flows.Read.All** et **Flow.Manage.All**. Vous pouvez configurer des cadres supplémentaires en modifiant la propriété **flowScopes** dans l’objet **applicationConfig**.
4.  Exécutez les commandes suivantes pour installer la dépendance et exécuter l’exemple d’application :
    > \> npm install \> node server.js
5. Ouvrez le navigateur et entrez http://localhost:30662
6. Sélectionnez le bouton **Connexion** pour vous authentifier auprès d’AAD et obtenir un jeton d’accès de Flow.
7. La zone de texte **Jeton d’accès** contient le jeton d’accès.
    ![architecture d’un widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Sélectionnez **Charger le widget de flux** ou **Charger le widget de modèles** pour incorporer les widgets correspondants.
    ![architecture d’un widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Lien de téléchargement](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) de l’exemple d’application.

## <a name="resources"></a>Ressources

### <a name="widget-test-pages"></a>Pages de test des widgets

Pour en savoir plus sur les paramètres et l’intégration de widgets, consultez :

- Widget de modèles : <[https://flow.microsoft.com/en-us/test/templateswidget/](https://flow.microsoft.com/en-us/test/templateswidget/)>
- Widget de création de flux : <[https://flow.microsoft.com/en-us/test/flowcreationwidget/](https://flow.microsoft.com/en-us/test/flowcreationwidget/)>
- Widget d’exécution : <[https://flow.microsoft.com/en-us/test/runtimewidget/](https://flow.microsoft.com/en-us/test/runtimewidget/)>
- Widget du Centre d’approbations : <[https://flow.microsoft.com/en-us/test/approvalcenterwidget/](https://flow.microsoft.com/en-us/test/approvalcenterwidget/)>
- Widget de flux : <[https://flow.microsoft.com/en-us/test/managewidget/](https://flow.microsoft.com/en-us/test/managewidget/)>

### <a name="supported-widget-locales"></a>Langues prises en charge pour les widgets

Si la langue initialisée n’est pas listée, Flow utilise par défaut la langue prise en charge la plus proche.

| Code de langue     | Langue                   | 
|------------|----------------------------| 
| bg-bg      | Bulgare (Bulgarie)       | 
| ca-es      | Catalan (Espagne)            | 
| cs-cz      | Tchèque (République tchèque)     | 
| da-dk      | Danois (Danemark)           | 
| de-de      | Allemand (Allemagne)           | 
| el-gr      | Grec (Grèce)             | 
| en-Us      | Anglais (États-Unis)    | 
| es-es      | Espagnol (Castillan)        | 
| et-ee      | Estonien (Estonie)         | 
| eu-es      | Basque (Espagne)             | 
| fi-fi      | Finnois (Finlande)          | 
| fr-fr      | Français (France)            | 
| gl-es      | Galicien (Espagne)           | 
| hi-HU      | Hongrois (Hongrie)        | 
| hi-in      | Hindi (Inde)              | 
| hr-hr      | Croate (Croatie)         | 
| id-Id      | Indonésien (Indonésie)     | 
| it-It      | Italien (Italie)            | 
| jp-Jp      | Japonais (Japon)           | 
| kk-kz      | Kazakh (Kazakhstan)        | 
| ko-kr      | Coréen (Corée)             | 
| lt-LT      | Lituanien (Lituanie)     | 
| lv-lv      | Letton (Lettonie)           | 
| ms-my      | Malais (Malaisie)           | 
| nb-no      | Norvégien (Bokmål)         | 
| nl-nl      | Néerlandais (Pays-Bas)        | 
| pl-pl      | Polonais (Pologne)            | 
| pt-br      | Portugais (Brésil)        | 
| pt-pt      | Portugais (Portugal)      | 
| ro-ro      | Roumain (Roumanie)         | 
| ru-ru      | Russe (Russie)           | 
| sk-sk      | Slovaque (Slovaquie)          | 
| sl-si      | Slovène (Slovénie)       | 
| sr-cyrl-rs | Serbe (cyrillique, Serbie) | 
| sr-latn-rs | Serbe (latin, Serbie)    | 
| sv-se      | Suédois (Suède)           | 
| th-th      | Thaï (Thaïlande)            | 
| tr-tr      | Turc (Turquie)           | 
| uk-ua      | Ukrainien (Ukraine)        | 
| vi-vn      | Vietnamien (Vietnam)      |
