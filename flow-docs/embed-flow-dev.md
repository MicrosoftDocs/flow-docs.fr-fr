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
ms.date: 05/09/2017
ms.author: barathb
ms.openlocfilehash: af03ee70b09ba5ee1164a9a7ea5019b13c19eec6
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440044"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Intégrer Microsoft Flow à des sites web et applications
Intégrez Microsoft Flow à votre application ou site web afin de donner aux utilisateurs un moyen simple d’automatiser les tâches de leur vie personnelle ou professionnelle.

Pour créer des flux, les utilisateurs doivent avoir un **compte Microsoft** ou un compte professionnel ou scolaire dans **Azure Active Directory**. Microsoft Flow ne prend pas en charge, par exemple, une solution de marque blanche qui prend en charge toute identité que votre système utilise (sauf si elle utilise déjà des comptes Microsoft ou AAD).

## <a name="prerequisites"></a>Prérequis
* [Créez un connecteur personnalisé](register-custom-api.md) qui connecte votre service à Microsoft Flow.
* [Créez et publiez un ou plusieurs modèles](publish-a-template.md) qui utilisent votre API.

## <a name="show-templates-for-your-scenarios"></a>Afficher les modèles pour vos scénarios
Pour commencer, ajoutez le code suivant pour afficher les modèles de flux directement dans votre site web :

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Remarque** : nous avons ajouté un saut de ligne afin que le code s’affiche mieux sur la page.

| Paramètre | Description |
| --- | --- |
| paramètres régionaux |Code de langue et de région de quatre lettres pour la vue du modèle. Par exemple, `en-us` représente l’anglais des États-Unis et `de-de` correspond à l’allemand. |
| terme de recherche |Terme de recherche pour les modèles que vous souhaitez afficher dans la vue. Par exemple, recherchez `wunderlist` pour afficher les modèles pour Wunderlist. |
| nombre de modèles |Nombre de modèles que vous souhaitez afficher dans la vue. |
| destination |Page qui s’affiche lorsque les utilisateurs cliquent sur le modèle. Spécifiez `details` pour afficher les détails relatifs au modèle ou `new` pour ouvrir le concepteur Microsoft Flow. |
| parameters.{name} |Contexte supplémentaire à transmettre au flux. |

Si le paramètre de destination est `new`, Microsoft Flow s’ouvre lorsque les utilisateurs cliquent sur un modèle et ceux-ci peuvent créer un flux dans le concepteur. Consultez la section suivante pour voir le fonctionnement complet de l’expérience directement depuis l’application.

### <a name="passing-additional-parameters-to-the-flow"></a>Transmission de paramètres supplémentaires au flux
Si l’utilisateur est dans un contexte particulier dans votre site web ou application, vous souhaitez transmettre ce contexte au flux. Par exemple, un utilisateur peut ouvrir un modèle *M’avertir lorsqu’un élément est ajouté à une liste* quand il consulte une liste donnée dans Wunderlist. En suivant ces étapes, vous pouvez transmettre l’ID de liste sous forme de *paramètre* au flux :

1. Définissez le paramètre dans le modèle de flux avant de le publier. Voici à quoi ressemble un paramètre : `@{parameters('parameter_name')}`.
2. Transmettez le paramètre dans iframe src. Par exemple, ajoutez `&parameters.listName={the name of the list}` si vous avez un paramètre appelé **listName**.

### <a name="full-sample"></a>Exemple complet
Pour afficher les quatre principaux modèles relatifs à Wunderlist en allemand et pour que l’utilisateur commence avec **myCoolList** :

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Incorporer la gestion de flux
Utilisez le Kit de développement logiciel (SDK) Flow authentifié pour permettre aux utilisateurs de créer et de gérer des flux directement à partir de votre site web ou application (au lieu d’y accéder par le portail Microsoft Flow). Vous devez connecter l’utilisateur à un compte Microsoft ou Azure Active Directory pour utiliser le Kit de développement logiciel (SDK) authentifié.

> [!NOTE]
> Tous les utilisateurs qui utilisent Microsoft Flow dans votre application sont indiqués comme des utilisateurs Microsoft Flow. Il n’existe aucun moyen de masquer la marque Microsoft Flow.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>Inclure le code JavaScript pour le Kit de développement logiciel (SDK) authentifié
Incluez le Kit de développement logiciel (SDK) dans votre code HTML en suivant cet exemple. Vous pouvez également télécharger, compresser et mettre en package le Kit de développement logiciel (SDK) avec votre produit.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Créer un conteneur pour contenir la vue
Ajoutez une balise div HTML :

```html
<div id="flowDiv" class="flowContainer"></div>
```

Nous vous recommandons de mettre en forme ce conteneur afin qu’il apparaisse avec les dimensions appropriées dans votre expérience :

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

Notez que l’iframe n’est pas rendu correctement en dessous de 320 pixels en largeur et ne remplit pas le contenu dépassant 1 200 pixels en largeur. N’importe quelle hauteur doit fonctionner.

### <a name="authentication-against-the-sdk"></a>Authentification auprès du Kit de développement logiciel (SDK)
Pour répertorier les flux que l’utilisateur a déjà créés et également pour créer des flux à partir de modèles, fournissez un jeton d’authentification à partir d’AAD.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

Vous pouvez trouver `environmentId` en effectuant l’appel d’API suivant, qui retourne la liste des environnements auxquels l’utilisateur a accès :

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

Cette opération retourne une réponse JSON avec la liste des environnements, dans laquelle vous pouvez choisir n’importe quel environnement. Vous pouvez rechercher l’environnement utilisateur par défaut en vérifiant la propriété `properties.isDefault=true`.

Dans cet exemple, `requestParam` est défini comme :

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Ensuite, `widgetDoneCallback` est une fonction de rappel qui doit être appelée une fois que l’hôte a le jeton. Cela s’effectue ainsi, car l’acquisition de jeton est probablement un processus asynchrone. Les paramètres qui doivent être transmis lors de l’appel de cette fonction sont `(errorResult: any, successResult: any)`. Le résultat successResult varie en fonction du type de rappel. Pour `GetAccessToken`, le type est :

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
