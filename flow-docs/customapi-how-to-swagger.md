---
title: "Extensions OpenAPI pour les connecteurs personnalisés dans Microsoft Flow | Microsoft Docs"
description: "Afficher les extensions de schéma requises par OpenAPI pour fonctionner avec Microsoft Flow"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: sunaysv
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: sunayv
ms.openlocfilehash: b8fdc04c16701c876d84e9761a48093fa5fb195c
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="openapi-extensions-for-custom-connectors-in-microsoft-flow"></a>Extensions OpenAPI pour les connecteurs personnalisés dans Microsoft Flow
## <a name="introduction"></a>Introduction
Pour créer des connecteurs personnalisés pour Microsoft Flow, Azure Logic Apps ou Microsoft PowerApps, vous devez fournir un fichier de définition OpenAPI, c’est-à-dire un document lisible par tout ordinateur, indépendamment du langage, qui décrit les opérations et paramètres de votre API. En plus des fonctionnalités prêtes à l’emploi d’OpenAPI, lorsque vous créez des connecteurs personnalisés pour Logic Apps et Flow, vous pouvez inclure les extensions OpenAPI suivantes :

* `summary`
* `x-ms-summary`
* `description`
* `x-ms-visibility`
* `x-ms-dynamic-values`
* `x-ms-dynamic-schema`

Voici plus de détails sur ces extensions :

<a name="summary"></a>

## <a name="summary"></a>summary
Spécifie le titre de l’action (opération). </br>
S’applique à : Opérations </br>
Recommandé : utiliser une *majuscule en début de phrase* pour `summary`. </br>
Exemple : « Lors d l’ajout d’un événement au calendrier » ou « Envoyer un courrier »

![« summary » pour chaque opération](./media/custom-connector-openapi-extensions/summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "summary": "Send an email",
    /// Other action properties here...
  }
},
```

## <a name="x-ms-summary"></a>x-ms-summary
Spécifie le titre d’une entité. </br>
S’applique à : Paramètres, Schéma de réponse </br>
Recommandé : utiliser des *initiales majuscules* pour `x-ms-summary`. </br>
Exemple : « ID De Calendrier », « Objet », « Description D’Événement », etc.

![« x-ms-summary » pour chaque entité](./media/custom-connector-openapi-extensions/x-ms-summary.png)

``` json
"actions" {
  "Send_an_email": {
    /// Other action properties here...
    "parameters": [ 
      {
        /// Other parameters here...
        "x-ms-summary": "Subject",
        /// Other parameters here...
      }
    ]
  }
},
```
<a name="description"></a>

## <a name="description"></a>description
Explication détaillée de la fonctionnalité de l’opération ou du format et de la fonction d’une entité. </br>
S’applique à : Opérations, Paramètres, Schéma de réponse </br>
Recommandé : utiliser une *majuscule en début de phrase* pour `description`. </br>
Exemple : « Cette opération est déclenchée lors de l’ajout d’un événement au calendrier », « Spécifiez l’objet du message », etc.

![« description » pour chaque opération ou entité](./media/custom-connector-openapi-extensions/description.png)

``` json
"actions" {
  "Send_an_email": {
     "description": "Specify the subject of the mail",
     /// Other action properties here...
  }
},
```

<a name="visibility"></a>

## <a name="x-ms-visibility"></a>x-ms-visibility
Spécifie la visibilité d’une entité pour l’utilisateur. </br>
Valeurs possibles : `important`, `advanced` et`internal` </br>
S’applique à : Opérations, Paramètres, Schémas

* Les opérations et paramètres `important` sont toujours affichés en premier à l’utilisateur.
* Les opérations et paramètres `advanced` sont masqués sous un menu supplémentaire.
* Les opérations et paramètres `internal` sont masqués à l’utilisateur.

> [!NOTE]
> Pour les paramètres `internal` et `required`, vous **devez** fournir des valeurs par défaut.
> 
> 

Exemple : les menus **Afficher plus** et **Afficher les options avancées** masquent les opérations et paramètres `advanced`.

![« x-ms-visibility » pour afficher ou masquer des opérations et paramètres](./media/custom-connector-openapi-extensions/x-ms-visibility.png)

``` json
"actions" {
  "Send_an_email": {
     /// Other action properties here...
     "parameters:": [
         {
           "name": "Subject",
           "type": "string",
           "description": "Specify the subject of the mail",
           "x-ms-summary": "Subject",
           "x-ms-visibility": "important",
           /// Other parameter properties here
         }
     ]
     /// Other action properties here...
  }
},
```

## <a name="x-ms-dynamic-values"></a>x-ms-dynamic-values
Affiche à l’utilisateur une liste dans laquelle il peut sélectionner les paramètres d’entrée d’une opération. </br>
S’applique à : Paramètres </br>
Mode d’utilisation : ajouter l’objet `x-ms-dynamic-values` à la définition du paramètre. Voir cet [exemple OpenAPI](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json).

![« x-ms-dynamic-values » pour afficher des listes](./media/custom-connector-openapi-extensions/x-ms-dynamic-values.png)

### <a name="properties-for-x-ms-dynamic-values"></a>Propriétés pour x-ms-dynamic-values
| Nom | Obligatoire ou facultatif | Description |
| --- | --- | --- |
| **operationID** |Obligatoire |Opération à appeler pour le remplissage de la liste. |
| **value-path** |Obligatoire |Chaîne de chemin d’accès dans l’objet à l’intérieur de `value-collection`, qui fait référence à la valeur du paramètre. Si la valeur de `value-collection` n’est pas spécifiée, la réponse est évaluée en tant que tableau. |
| **value-title** |Facultatif |Chaîne de chemin d’accès dans l’objet à l’intérieur de `value-collection`, qui fait référence à la description de la valeur. Si la valeur de `value-collection` n’est pas spécifiée, la réponse est évaluée en tant que tableau. |
| **value-collection** |Facultatif |Chaîne de chemin d’accès qui donne un tableau d’objets dans la charge utile de réponse |
| **parameters** |Facultatif |Objet dont les propriétés spécifient les paramètres d’entrée requis pour appeler une opération dynamic-values |

Voici un exemple montrant les propriétés dans `x-ms-dynamic-values` :

``` json
"x-ms-dynamic-values": {
  "operationId": "PopulateDropdown",
  "value-path": "name",
  "value-title": "properties/displayName",
  "value-collection": "value",
  "parameters": {
     "staticParameter": "{value}",
     "dynamicParameter": {
        "parameter": "{value-to-pass-to-dynamicParameter}"
     }
  }
}
```

## <a name="example-all-the-openapi-extensions-up-to-this-point"></a>Exemple : Toutes les extensions OpenAPI jusqu’à ce point
``` json
"/api/lists/{listID-dynamic}": {
    "get": {
        "description": "Get items from a single list - uses dynamic values and outputs dynamic schema",
        "summary": "Gets items from the selected list",
        "operationID": "GetListItems",
        "parameters": [
           {
             "name": "listID-dynamic",
             "type": "string",
             "in": "path",
             "description": "Select the list from where you want outputs",
             "required": true,
             "x-ms-summary": "Select List",
             "x-ms-dynamic-values": {
                "operationID": "GetLists",
                "value-path": "id",
                "value-title": "name"
             }
           }
        ]
    }
}
```

## <a name="x-ms-dynamic-schema"></a>x-ms-dynamic-schema
Indique que le schéma pour la réponse ou le paramètre actuels est dynamique. Cet objet peut appeler une opération définie par la valeur de ce champ, découvrir le schéma de façon dynamique et afficher l’interface utilisateur appropriée pour la collecte des entrées d’utilisateur ou les champs disponibles. 

S’applique à : Paramètres, Réponse

Mode d’utilisation : ajouter l’objet `x-ms-dynamic-schema` à une définition de paramètre de requête ou de corps de réponse. Voir cet [exemple OpenAPI](https://procsi.blob.core.windows.net/blog-images/sampleDynamicSwagger.json).

Cet exemple montre comment le formulaire d’entrée change en fonction de l’élément que l’utilisateur sélectionne dans la liste déroulante :

![« x-ms-dynamic-schema » pour les paramètres dynamiques](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema.png)

Et cet exemple montre comment les sorties changent en fonction de l’élément que l’utilisateur sélectionne dans la liste déroulante : Dans cette version, l’utilisateur sélectionne « Cars » (Voitures) :

![« x-ms-dynamic-schema-response » pour l’élément sélectionné « Cars »](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output1.png)

Dans cette version, l’utilisateur sélectionne « Food » (Aliments) :

![« x-ms-dynamic-schema-response » pour l’élément sélectionné « Food »](./media/custom-connector-openapi-extensions/x-ms-dynamic-schema-output2.png)

### <a name="properties-for-x-ms-dynamic-schema"></a>Propriétés pour x-ms-dynamic-schema
| Nom | Obligatoire ou facultatif | Description |
| --- | --- | --- |
| **operationID** |Obligatoire |Opération à appeler pour l’extraction du schéma |
| **parameters** |Obligatoire |objet dont les propriétés spécifient les paramètres d’entrée obligatoires pour appeler une opération dynamic-schema |
| **value-path** |Facultatif |Chaîne de chemin d’accès faisant référence à la propriété possédant le schéma. </br>À défaut de spécification, la réponse est supposée contenir le schéma dans les propriétés de l’objet racine. |
|  | | |

Voici un exemple pour un paramètre dynamique :

``` json
{
  "name": "dynamicListSchema",
  "in": "body",
  "description": "Dynamic schema for items in the selected list",
  "schema": {
    "type": "object",
    "x-ms-dynamic-schema": {
        "operationID": "GetListSchema",
        "parameters": {
          "listID": {
            "parameter": "listID-dynamic"
          }
        },
        "value-path": "items"
    }
  }
}
```

Voici un exemple pour une réponse dynamique :

``` json
"DynamicResponseGetListSchema": {
   "type": "object",
   "x-ms-dynamic-schema": {
      "operationID": "GetListSchema",
      "parameters": {
         "listID": {
            "parameter": "listID-dynamic"
         }
      },
      "value-path": "items"
    }
}
```

## <a name="next-steps"></a>Étapes suivantes
[Inscrivez un connecteur personnalisé](register-custom-api.md).

[Utiliser une API web ASP.NET](customapi-web-api-tutorial.md).

[Inscrire une API Azure Resource Manager](customapi-azure-resource-manager-tutorial.md).

