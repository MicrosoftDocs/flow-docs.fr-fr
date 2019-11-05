---
title: Intégrer des Microsoft Flow avec des sites Web et des applications | Microsoft Docs
description: Incorporez les expériences Microsoft Flow dans votre site Web ou votre application.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547708"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Intégrer des Microsoft Flow avec des sites Web et des applications
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Incorporez Microsoft Flow dans votre application ou site Web à l’aide de *widgets de Flow* pour offrir aux utilisateurs un moyen simple d’automatiser leurs tâches personnelles ou professionnelles.

Les widgets de flow sont des iframes situés dans un document hôte. Ce document pointe vers une page dans le concepteur de Microsoft Flow. Ces widgets intègrent des fonctionnalités de Microsoft Flow spécifiques dans l’application tierce.

Les widgets peuvent être simples. Par exemple, un widget qui effectue le rendu d’une liste de modèles sans communication entre l’hôte et l’IFRAME. Les widgets peuvent également être complexes. Par exemple, un widget qui configure un workflow à partir d’un modèle, puis déclenche le canal via une communication bidirectionnelle entre l’hôte et le widget.

## <a name="prerequisites"></a>Conditions préalables

- Un **compte Microsoft** ou
- Un compte professionnel ou scolaire

## <a name="use-the-unauthenticated-widget"></a>Utiliser le widget non authentifié
Pour utiliser le widget modèles non authentifiés, incorporez-le directement dans l’application hôte à l’aide d’un IFRAME. Vous n’avez pas besoin du kit de développement logiciel (SDK) JS ou d’un jeton d’accès. 

### <a name="show-templates-for-your-scenarios"></a>Afficher les modèles pour vos scénarios
Pour commencer, ajoutez le code suivant pour afficher les modèles de Microsoft Flow sur votre site Web :

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Paramètre | Descriptive |
| --- | --- |
| paramètres régionaux |Code de langue et de région à quatre lettres pour la vue de modèle. Par exemple, `en-us` représente l’anglais américain et `de-de` représente l’allemand. |
| terme de recherche |Terme de recherche pour les modèles que vous souhaitez afficher dans la vue. Par exemple, recherchez `wunderlist` pour afficher les modèles pour Wunderlist. |
| nombre de modèles |Nombre de modèles que vous souhaitez afficher dans la vue. |
| Destination |Page qui s’ouvre lorsque les utilisateurs sélectionnent le modèle. Entrez `details` pour afficher les détails sur le modèle, ou entrez `new` pour ouvrir le concepteur de Microsoft Flow. |
| catégorie |Filtre la catégorie de modèle donnée. | 
| paramètres. nomme |Contexte supplémentaire à transmettre au Flow. |


Si le paramètre de destination est `new`, le concepteur de Microsoft Flow s’ouvre lorsque les utilisateurs sélectionnent un modèle. Les utilisateurs peuvent ensuite créer un fluide dans le concepteur. Consultez la section suivante si vous souhaitez obtenir une expérience complète à partir du widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passage de paramètres supplémentaires au modèle de Flow

Si l’utilisateur se trouve dans un contexte spécifique dans votre site Web ou votre application, vous pouvez passer ce contexte au Flow. Par exemple, un utilisateur peut ouvrir un modèle pour *m’avertir lorsqu’un élément est ajouté à une liste* lors de la consultation d’une liste spécifique dans Wunderlist. Procédez comme suit pour transmettre l’ID de liste en tant que *paramètre* au Flow :

1. Définissez le paramètre dans le modèle de Flow avant de le publier. Un paramètre ressemble à `@{parameters('parameter_name')}`.
1. Transmettez le paramètre dans la chaîne de requête du type de source de l’IFRAME. Par exemple, ajoutez `&parameters.listName={the name of the list}` si vous avez un paramètre appelé **ListName**.

### <a name="full-sample"></a>Exemple complet

Pour afficher les quatre premiers modèles Wunderlist en allemand et démarrer l’utilisateur avec **myCoolList**, utilisez ce code :

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Utiliser les widgets de Flow authentifié

Le tableau suivant présente la liste des widgets de Microsoft Flow qui prennent en charge l’expérience complète dans le widget à l’aide du jeton d’accès d’authentification utilisateur. Vous devrez utiliser le kit de développement logiciel (SDK) JavaScript de Microsoft Flow pour incorporer les widgets et fournir le jeton d’accès utilisateur requis.

| Type de widget    | Fonctionnalité prise en charge                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Trouvent          | Affiche une liste de flux dans un onglet pour les flux personnels et partagés. Modifier un fluide existant ou créer un nouveau workflow à partir d’un modèle ou vide. | 
| flowCreation   | Crée un workflow à partir d’un ID de modèle fourni par l’application hôte.                                                                | 
| Language        | Déclenche un workflow manuel ou de déclenchement hybride fourni par l’application hôte.                                                        | 
| approvalCenter | Incorpore les demandes d’approbation et les approbations envoyées.                                                                                        | 
| Ceux      | Affiche une liste de modèles. L’utilisateur en choisit un pour créer un nouveau Workflow.                                                                         | 

Utilisez le kit de développement logiciel (SDK) Flow authentifié pour permettre aux utilisateurs de créer et de gérer des flux directement à partir de votre site Web ou de votre application (au lieu de naviguer vers Microsoft Flow). Vous devez connecter l’utilisateur à l’aide de son compte Microsoft ou Azure Active Directory pour utiliser le kit de développement logiciel (SDK) authentifié.

> [!NOTE]
> Il n’existe aucun moyen de masquer la Microsoft Flow de personnalisation lorsque vous utilisez des widgets.

## <a name="widget-architecture"></a>architecture du widget

Microsoft Flow widgets fonctionnent en incorporant un IFRAME qui référence des Microsoft Flow dans une application hôte. L’hôte fournit le jeton d’accès requis par le widget Microsoft Flow. Le kit de développement logiciel (SDK) JS de Microsoft Flow permet à l’application hôte d’initialiser et de gérer le cycle de vie du widget.

![architecture du widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Détails du SDK JS

L’équipe Microsoft Flow fournit le kit de développement logiciel (SDK) JS pour faciliter l’intégration des widgets de Flow dans les applications tierces. Le kit de développement logiciel (SDK) Flow JS est disponible en tant que lien public dans le service Flow et permet à l’application hôte de gérer les événements du widget et d’interagir avec l’application Flow en envoyant des actions au widget. Les événements et les actions des widgets sont spécifiques au type de widget.

### <a name="widget-initialization"></a>Initialisation du widget

La référence du kit de développement logiciel (SDK) Flow JS doit être ajoutée à l’application hôte avant l’initialisation du widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Créez une instance du kit de développement logiciel (SDK) JS en passant des valeurs facultatives de nom d’hôte et de paramètres régionaux dans un objet JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Nomme     | Obligatoire/facultatif | Descriptive                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Facultatif          | Microsoft Flow nom d’hôte, par exemple, https://flow.microsoft.com        | 
| `locale`   | Facultatif          | Paramètres régionaux du client pour le widget (valeur par défaut `en-Us` si non spécifié) | 


Une fois l’instance du kit de développement logiciel (SDK) JS créée, vous pouvez initialiser et incorporer un widget Microsoft Flow dans un élément parent de l’application hôte. Pour ce faire, ajoutez une balise div HTML :

```html
<div id="flowDiv" class="flowContainer"></div>
```

Ensuite, initialisez le widget Microsoft Flow avec la méthode `renderWidget()` du kit de développement logiciel (SDK) JS. Veillez à fournir le type de widget et les paramètres correspondants.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Voici un exemple de style pour le conteneur que vous pouvez modifier pour qu’il corresponde aux dimensions de l’application hôte.

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

Voici les paramètres de `renderWidget()`: 

| Paramètre        | Obligatoire/facultatif | Descriptive                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Obligatoire          | ID d’un élément DIV sur la page hôte où le widget sera incorporé.                   | 
| `environmentId`    | Facultatif          | Les widgets ont besoin d’un ID d’environnement. Si vous ne fournissez pas d’ID, un environnement par défaut est utilisé. | 
| `flowsSettings`    | Facultatif          | Objet paramètres Microsoft Flow                                                                        | 
| `templateSettings` | Facultatif          | Objet de paramètres de modèle                                                                    | 
| `approvalSettings` | Facultatif          | Objet des paramètres d’approbation                                                                    | 

### <a name="access-tokens"></a>Jetons d’accès

Après l’exécution du kit de développement logiciel (`renderWidget()` SDK) JS, le kit de développement logiciel (SDK) JS Initialise un IFRAME qui pointe vers l’URL du widget Microsoft Flow. Cette URL contient tous les paramètres des paramètres de chaîne de requête. L’application hôte doit obtenir un jeton d’accès Microsoft Flow pour l’utilisateur (Azure Active Directory jeton JWT avec l' https://service.flow.microsoft.com) d’audience avant d’initialiser le widget. Le widget déclenche un événement `GET_ACCESS_TOKEN` pour demander un jeton d’accès à l’hôte. L’hôte doit gérer l’événement et transmettre le jeton au widget :

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

L’application hôte est responsable de la gestion du jeton et de sa transmission avec une date d’expiration valide au widget lorsque cela est demandé. Si le widget est ouvert pendant des périodes plus longues, l’hôte doit vérifier si le jeton a expiré et actualiser le jeton s’il est nécessaire avant de le passer au widget.

### <a name="detecting-if-the-widget-is-ready"></a>Détection de l’état prêt du widget

Une fois l’initialisation réussie, le widget déclenche un événement pour signaler que le widget est prêt. L’hôte peut écouter l’événement `WIDGET_READY` et exécuter tout code hôte supplémentaire.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Paramètres du widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings peut être utilisé pour personnaliser les fonctionnalités du widget Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Paramètre | Obligatoire/facultatif | Descriptive | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Obligatoire | Utiliser le GUID du modèle lorsque l’utilisateur sélectionne le bouton **créer à partir d’un espace vide** sur le widget de Flow | 
| `flowsFilter` | Facultatif | Le widget Microsoft Flow applique le filtre fourni lors de la liste des flux. Par exemple, affichez les flux qui font référence à un site SharePoint spécifique. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Facultatif | Par défaut, l’onglet actif est affiché dans le widget Microsoft Flow. <br /> Par exemple, <br /> ```tab:'sharedFlows' ``` affiche l’onglet équipe<br /> et ``` tab:'myFlows' ``` affiche l’onglet mes flux. |   

### <a name="templatessettings"></a>TemplatesSettings 

Cela s’applique à tous les widgets qui vous permettent de créer des flux à partir d’un modèle, y compris des widgets flux, FlowCreation et modèles.

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

| Paramètre |Obligatoire/facultatif | Descriptive                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Facultatif          | Paramètres au moment du design à utiliser lors de la création d’un workflow à partir d’un modèle, par exemple : <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Facultatif          | Les valeurs valides sont « nouveau » ou « détails ». Quand la valeur est définie sur « Details », une page de détails s’affiche lors de la création d’un fluide à partir d’un modèle.     |
| `pageSize` | Facultatif          | Nombre de modèles à afficher. Taille par défaut = 6 | 
| `searchTerm` | Facultatif          | Afficher les modèles qui correspondent au terme de recherche fourni| 
| `templateCategory` | Facultatif          | Afficher les modèles dans une catégorie spécifique| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

S’applique aux widgets ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Paramètre | Obligatoire/facultatif | Descriptive | 
|------------|-------------------|--------------| 
| `hideLink`| Facultatif | Lorsque la valeur `true`, le widget masque les liens d’approbation reçus et envoyés | 
| `autoNavigateToDetails`| Facultatif | Lorsqu’il a la valeur `true`, le widget ouvre automatiquement les détails de l’approbation lorsqu’il n’existe qu’une seule approbation | 
| `approvalsFilter`| Facultatif | Le widget approbation appliquera le filtre d’approbation spécifié lors de la liste des approbations. par exemple, le widget approbation appliquera le filtre d’approbation spécifié lors de la liste des approbations, par exemple : <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Facultatif | Onglet actif par défaut à afficher dans le widget de Flow. <br/> Valeurs valides : « receivedApprovals », « sentApprovals » | 
| `showSimpleEmptyPage`| Facultatif | Affiche une page vide lorsqu’il n’y a aucune approbation | 
| `hideInfoPaneCloseButton` | Facultatif | Masque le bouton Fermer du volet d’informations (ou l’hôte a déjà un bouton Fermer) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Événements widget

Le widget Microsoft Flow prend en charge les événements qui permettent à l’hôte d’écouter les événements du cycle de vie du widget. Le widget Microsoft Flow prend en charge deux types d’événements : les événements de notification unidirectionnels (par exemple, widget\_Ready) et les événements déclenchés à partir du widget pour extraire des données de l’hôte (obtenir\_jeton d’accès\_). L’hôte doit utiliser la méthode widget. Listen () pour écouter les événements spécifiques déclenchés à partir du widget.

### <a name="usage"></a>Syntaxe

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Événements pris en charge par type de widget

| Widget (événement)      | Plus                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget correctement chargé                                      | 
| `WIDGET_RENDERED`   | Le widget chargé et le rendu de l’interface utilisateur sont terminés                      | 
| `GET_ACCESS_TOKEN`  | Demande de widget pour incorporer un jeton d’accès utilisateur                      | 
| `GET_STRINGS`       | Permet à l’hôte de remplacer un ensemble de chaînes d’interface utilisateur figurant dans le widget | 

### <a name="runtime-widget"></a>Widget Runtime

| Widget (événement)                    | Plus                                     | Métadonnée                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Déclenché et l’exécution du workflow a démarré      |           | 
| `RUN_FLOW_COMPLETED`              | Exécution du passage correctement déclenchée             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Bouton terminé sélectionné par l’utilisateur sur l’exécution du Workflow       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Bouton Annuler sélectionné par l’utilisateur sur l’exécution du Workflow     |           | 
| `FLOW_CREATION_SUCCEEDED`         | Le Flow a été créé avec succès           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Déclenché lorsque l’hôte doit fermer le widget |       | 

### <a name="flow-creation-widget"></a>Widget de création de Flow

| Widget (événement)             | Plus                                  | Métadonnée  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Échec de la création du Workflow                     |       | 
| `WIDGET_CLOSE`             | Déclenché lorsque l’hôte doit fermer le widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Échec du chargement du modèle              |       | 
| `FLOW_CREATION_SUCCEEDED`  | Le Flow a été créé avec succès        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget d’approbation

| Widget (événement)                      | Plus                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | État d’approbation reçu modifié  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Envoi de l’état d’approbation modifié      | 

L’événement **obtenir\_Strings** vous permet de personnaliser du texte pour certains des éléments d’interface utilisateur affichés dans le widget. Les chaînes suivantes peuvent être personnalisées :

| Clé de chaîne                     | Utilisation dans le widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texte affiché sur le bouton créer un Flow à la fois dans la création de Flow et dans le widget Runtime                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | Valeur initiale à utiliser pour le nom du workflow dans le widget de création de Flow. Utilisé uniquement lorsque le paramètre allowCustomFlowName est activé. | 
| `FLOW_CREATION_HEADER`           | En-tête à utiliser lors de la création d’un fluide dans le widget de création et d’exécution de Flow                                                    | 
| `INVOKE_FLOW_HEADER`             | En-tête à utiliser lors de l’appel d’un Flow dans le widget Runtime                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texte affiché sur le bouton utilisé pour appeler/exécuter un Flow dans le widget Runtime                                                       | 

### <a name="example"></a>Tels

Appelez `widgetDoneCallback` passant un objet JSON avec des paires clé-valeur de clé de chaîne et de texte pour remplacer la valeur par défaut.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Actions du widget

L’hôte utilise des actions de widget pour envoyer une action ou un message spécifique au widget. Le kit de développement logiciel (SDK) widget JS fournit la méthode `notify()` pour envoyer un message ou une charge utile JSON au widget. Chaque action de widget prend en charge une signature de charge utile spécifique.

### <a name="usage"></a>Syntaxe

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Tels 

Appeler un Flow en envoyant la commande suivante à un widget Runtime 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget Runtime

| Action du widget                               | Plus                                                      | Interface de paramètre  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Déclenche une exécution de workflow                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Déclenche un Flow exécuté par modèle                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtient le schéma du déclencheur pour un Flow                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Annule toute activité en attente et déclenche un événement WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget de création de Flow

| Action du widget                               | Plus                                                      | Interface de paramètre  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Crée un fluide pour le modèle sélectionné                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Crée un Flow pour la définition de modèle sélectionnée          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Annule toute activité en attente et déclenche un événement WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget d’approbation

| Action du widget  | Plus                                           | Interface de paramètre  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Ferme le volet d’informations affichant les détails de l’approbation  | NON APPLICABLE                  | 

## <a name="configuring-your-client-application"></a>Configuration de votre application cliente

Vous devrez configurer votre application cliente avec des étendues de service de Flow (autorisations déléguées). Si l’application Azure Active Directory (AAD) utilisée pour l’intégration du widget utilise un workflow d’autorisation « octroi de code », l’application AAD doit être préconfigurée avec des autorisations déléguées prises en charge par Microsoft Flow. Cela fournit des autorisations déléguées qui permettent à l’application :

-   Gérer les approbations
-   Approbations de lecture
-   Lire les activités
-   Gérer les flux
-   Lire les flux

Procédez comme suit pour sélectionner une ou plusieurs autorisations déléguées :

1.  Accéder à https://portal.azure.com 
2.  Sélectionnez **Azure Active Directory**.
3.  Sélectionnez **inscriptions d’applications** sous **gérer**.
4.  Entrez l’application tierce à configurer pour les étendues de service de Flow.
5.  Sélectionnez **paramètres**.
      architecture du widget ![](../media/embed-flow-dev/AAD-App-Settings.png)
6. Sélectionnez les **autorisations requises** sous **accès de l’API**/
7. Sélectionnez **Ajouter**.
8. Choisissez **Sélectionner une API**.
      architecture du widget ![](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Recherchez **Microsoft Flow service** et sélectionnez-le. Remarque : pour que vous puissiez voir Microsoft Flow service, votre locataire doit avoir au moins un utilisateur AAD connecté au portail Flow (<https://flow.microsoft.com>)
10. Choisissez les étendues de Flow requises pour votre application, puis sélectionnez **Enregistrer**.
      architecture du widget ![](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Votre application obtiendra à présent un jeton de service de Flow qui contient des autorisations déléguées dans la revendication \'SCP dans le jeton JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Exemples de widgets de flow d’incorporation d’application 

Un exemple d’application à page unique JavaScript (SPA) est fourni dans la section ressources afin que vous puissiez expérimenter les widgets d’incorporation de Flow dans une page hôte. L’utilisation de l’exemple d’application nécessite l’inscription d’une application AAD avec un workflow d’octroi implicite activé.

### <a name="registering-an-aad-app"></a>Inscription d’une application AAD

1.  Connectez-vous au [portail Azure](https://portal.azure.com/).
2.  Dans le volet de navigation gauche, sélectionnez **Azure Active Directory**, puis sélectionnez **inscriptions d’applications** (version préliminaire) \> nouvelle inscription.
3.  Lorsque la page **inscrire une application** s’affiche, entrez un nom pour votre application.
4.  Sous **types de comptes pris en charge**, sélectionnez **comptes** dans n’importe quel annuaire d’organisation.
5.  Sous la section **URL de redirection** , sélectionnez la plateforme Web et définissez la valeur sur l’URL d’application\'s en fonction de votre serveur Web.  Configurez cette valeur sur http://localhost:30662/ pour exécuter l’exemple d’application.
6.  Sélectionnez **inscrire**.
7.  Sur la page **vue d’ensemble** de l’application, notez la valeur de l’ID de l’application (client).
8.  L’exemple requiert l’activation du [Workflow d’octroi implicite](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) . Dans le volet de navigation de gauche de l’application inscrite, sélectionnez **authentification**.
9.  Dans **Paramètres avancés**, sous **octroi implicite**, activez les cases à cocher **jetons d’ID** et **jetons d’accès** . Les jetons d’ID et les jetons d’accès sont requis, car cette application a besoin de connecter les utilisateurs et d’appeler l’API Flow.
10. Sélectionnez **Enregistrer**.

### <a name="running-the-sample"></a>Exécution de l’exemple
<!-- todo where should I download from? -->
1.  Téléchargez l’exemple et copiez-le dans un dossier local sur votre appareil.
2.  Ouvrez le fichier index. html dans le dossier FlowSDKSample et modifiez le `applicationConfig` pour mettre à jour le `clientID` avec l’ID d’application que vous avez enregistré précédemment.
    architecture du widget ![](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  L’exemple d’application est configuré pour utiliser des flux d’étendues de flux **. Read. All** et **Flow. Manage. All.** Vous pouvez configurer des étendues supplémentaires en mettant à jour la propriété **flowScopes** dans l’objet **applicationConfig** .
4.  Exécutez les commandes suivantes pour installer la dépendance et exécuter l’exemple d’application :
    > \> installer NPM \> node Server. js
5. Ouvrez le navigateur, puis entrez http://localhost:30662
6. Sélectionnez le bouton **se connecter pour vous** authentifier sur AAD et obtenir un jeton d’accès au workflow.
7. La zone de texte **jeton d’accès** contient le jeton d’accès.
    architecture du widget ![](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Sélectionnez le widget **charger les flux** ou **charger les modèles** pour incorporer les widgets correspondants.
    architecture du widget ![](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Lien de [Téléchargement](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)de l’exemple d’application.

## <a name="resources"></a>Situées

### <a name="widget-test-pages"></a>Pages de test du widget

En savoir plus sur l’intégration des widgets et les paramètres :

- Widget de modèles : <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation : <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget Runtime : <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widget du centre d’approbations : <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget flux : <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Paramètres régionaux des widgets pris en charge

Si les paramètres régionaux initialisés ne sont pas listés, Flow prend par défaut les paramètres régionaux pris en charge les plus proches.

| paramètres régionaux     | sous                   | 
|------------|----------------------------| 
| BG-BG      | Bulgare (Bulgarie)       | 
| ca-es      | Catalan (Espagne)            | 
| CS-CZ      | Tchèque (République tchèque)     | 
| da-DK      | Danois (Danemark)           | 
| De-de      | Allemand (Allemagne)           | 
| El-gr      | Grec (Grèce)             | 
| en-US      | Anglais (États-Unis)    | 
| Es-es      | Espagnol (castillan)        | 
| et-ee      | Estonien (Estonie)         | 
| UE-es      | Basque (Espagne)             | 
| fi-fi      | Finnois (Finlande)          | 
| Fr-fr      | Français (France)            | 
| GL-es      | Galicien (Espagne)           | 
| HI-HU      | Hongrois (Hongrie)        | 
| haut de la      | Hindi (Inde)              | 
| RH-RH      | Croate (Croatie)         | 
| ID ID      | Indonésien (Indonésie)     | 
| informatique-informatique      | Italien (Italie)            | 
| JP-JP      | Japonais (Japon)           | 
| KK-KZ      | Kazakh (Kazakhstan)        | 
| Ko-KR      | Coréen (Corée)             | 
| lt-LT      | Lituanien (Lituanie)     | 
| LV-LV      | Letton (Lettonie)           | 
| MS-My      | Malais (Malaisie)           | 
| NB-non      | Norvégien (Bokmål)         | 
| NL-NL      | Néerlandais (Pays-Bas)        | 
| Pl-pl      | Polonais (Pologne)            | 
| PT-BR      | Portugais (Brésil)        | 
| PT-PT      | Portugais (Portugal)      | 
| RO-RO      | Roumain (Roumanie)         | 
| Ru-RU      | Russe (Russie)           | 
| SK-SK      | Slovaque (Slovaquie)          | 
| SL-si      | Slovène (Slovénie)       | 
| SR-Cyrl-RS | Serbe (cyrillique, Serbie) | 
| SR-LATN-RS | Serbe (latin, Serbie)    | 
| SV-se      | Suédois (Suède)           | 
| th-TH      | Thaï (Thaïlande)            | 
| TR-TR      | Turc (Turquie)           | 
| Royaume-Uni-UA      | Ukrainien (Ukraine)        | 
| vi-VN      | Vietnamien (Vietnam)      |
