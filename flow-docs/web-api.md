---
title: Les flux sont maintenant stockés dans Common Data Service et utilisent l’API web avancée
description: Les flux sont maintenant stockés dans Common Data Service et utilisent l’API web avancée.
author: stepsic-microsoft-com
ms.reviewer: deonhe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: business-applications
ms.technology: ''
ms.author: stepsic
audience: Power user
ms.openlocfilehash: 210965e443f42935529219705cd7b08fe60c92ca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548653"
---
# <a name="microsoft-flow-web-api"></a>API web Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

À l’avenir, tous les flux seront stockés dans Common Data Service et tireront parti de l’[API Web avancée](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/perform-operations-web-api).

Ce contenu traite de la gestion des flux inclus sur l’onglet **Solutions** dans Microsoft Flow. Actuellement, les flux sous **Mes flux** ne sont pas pris en charge par ces API.

## <a name="compose-http-requests"></a>Composer des requêtes HTTP

Pour commencer à créer des requêtes, vous devrez d’abord construire l’URL. Le format pour l’URL de base de l’API Web Microsoft Flow est : `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. Les deux paramètres sont :

- L’**ID d’organisation** est un nom unique pour l’environnement qui stocke vos flux. Vous pouvez voir l’ID d’organisation dans le sélecteur d’environnement dans le coin supérieur droit de Microsoft Flow. Remarque : l’**ID d’organisation** est différent de l’**ID d’environnement** (qui correspond à l’interface graphique utilisateur qui apparaît dans l’URL du flux).

     ![Sélecteur d’environnement](media/web-api/get-organization-id.png "Sélecteur d’environnement")

- Le **sous-domaine régional** dépend de l’emplacement de votre environnement. Lorsque vous vous connectez à Microsoft Flow, vous pouvez voir la région de votre environnement dans l’URL de la page web. Utilisez ce nom de région pour trouver le sous-domaine associé dans le tableau suivant :

     ![URL de flux](media/web-api/get-region-name.png "URL de flux")

     | Région         | Sous-domaine   |
     | -------------- | ----------- |
     | États-Unis  | crm         |
     | Amérique du Sud  | crm2        |
     | Canada         | crm3        |
     | Europe         | crm4        |
     | Asie-Pacifique   | crm5        |
     | Australie      | crm6        |
     | Japon          | crm7        |
     | Inde          | crm8        |
     | US Gov  | crm9        |
     | Royaume-Uni | crm11       |

Vous pouvez aussi obtenir par programmation la liste des instances disponibles via la méthode [Get Instances](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) dans l’API Online Management.

Les en-têtes `Accept` et `Content-type` de chaque requête faite à l’API Web doivent être définis sur `application/json`.

Enfin, remplissez l’en-tête `Authorization` avec un jeton du porteur Azure AD. Vous pouvez [apprendre](https://docs.microsoft.com/powerapps/developer/common-data-service/authenticate-oauth) à acquérir un jeton du porteur Azure AD pour Common Data Service. Par exemple, cette requête :

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

La réponse contient la liste des flux provenant de cet environnement :

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in Common Data Service.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Liste des flux

Comme indiqué ci-dessus, vous pouvez obtenir la liste des flux de travail en appelant `GET` et `workflows`. Chaque flux de travail dispose de plusieurs propriétés, mais les plus importantes sont :

| Nom de la propriété     | Description                                              |
| ----------------- | -------------------------------------------------------- |
| Catégorie          | Catégorie du flux. Les différents types sont : 0 - workflows Common Data Service classiques, 1 - dialogues Common Data Service classiques, 2 - règles métier, 3 - actions Common Data Service classiques, 4 - flux de processus métier et 5 - flux automatisés, instantanés ou planifiés. |
| statecode         | L’état du flux. L’état peut être **0** - désactivé ou **1** - activé.|
| workflowuniqueid  | Identificateur unique de cette installation du flux. |
| workflowid        | Identificateur unique d’un flux pour toutes les importations. |
| createdon         | Date de création du flux. |
| _ownerid_value    | Identificateur unique de l’utilisateur ou de l’équipe propriétaire du flux. Il s’agit d’un ID de l’entité systemusers dans Common Data Service. |
| modifiedon        | Dernière mise à jour du flux. |
| ismanaged         | Indique si le flux a été installé via une solution managée. |
| name              | Nom complet que vous avez donné au flux. |
| _modifiedby_value | Dernier utilisateur ayant mis à jour le flux. Il s’agit d’un ID de l’entité systemusers dans Common Data Service. |
| _createdby_value  | Utilisateur ayant créé le flux. Il s’agit d’un ID de l’entité systemusers dans Common Data Service. |
| type              | Indique si le flux est en cours d’exécution, ou s’il s’agit d’un modèle pouvant être utilisé pour créer des flux supplémentaires. 1 - flux, 2 - activation ou 3 - modèle. |
| description       | Description du flux donnée par l’utilisateur. |
| clientdata        | Une chaîne encodée JSON d’un objet qui contient l’élément connectionReferences et la définition du flux. |

Vous pouvez aussi interroger des propriétés spécifiques, filtrer la liste des flux et bien plus encore, comme décrit dans la [documentation sur l’API Common Data Service pour interroger des données](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/query-data-web-api). Par exemple, cette requête retourne uniquement les flux automatisés, instantanés ou planifiés qui sont actuellement activés :

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Créer un flux

Appelez `POST` sur la collection `workflows` pour créer un flux. Les propriétés nécessaires pour les flux automatisés, instantanés et planifiés sont : category, name, type, primaryentity et clientdata. Utilisez `none` pour la propriété primaryentity pour ces types de flux.

Vous pouvez également fournir une description et un code d’état (statecode).

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from Common Data Service.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

La section la plus importante est `clientdata`, qui contient la propriété connectionReferences que le flux utilise, ainsi que la [définition](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) du flux. La propriété connectionReferences correspond aux mappages de chaque connexion dont se sert le flux.

Il existe trois propriétés :

| Nom de la propriété  | Description                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identifie la connexion. Vous pouvez voir la propriété connectionName en vous rendant sur la page **Connexions** puis en la copiant à partir de l’URL de la connexion. |
| source         | Soit `Embedded`, soit `Invoker`. `Invoker` n’est valide que pour les flux instantanés (ceux où un utilisateur sélectionne un bouton pour exécuter le flux), et indique que l’utilisateur final fournit la connexion. Dans ce cas, la propriété connectionName n’est utilisée qu’au moment du design. Si la connexion est `Embedded`, cela signifie que la propriété connectionName spécifiée est toujours utilisée. |
| id             | Identificateur du connecteur. L’ID commence toujours par `/providers/Microsoft.PowerApps/apis/` suivi du nom du connecteur, que vous pouvez copier à partir de l’URL de la connexion ou en sélectionnant le connecteur depuis la page **Connecteurs**. |

Une fois que vous avez exécuté la requête `POST`, vous recevez l’en-tête `OData-EntityId`, qui contient la propriété `workflowid` pour votre nouveau flux.

## <a name="update-a-flow"></a>Mettre à jour un flux

Vous pouvez appeler `PATCH` sur le flux de travail pour mettre à jour, activer ou désactiver un flux. Utilisez la propriété `workflowid` pour effectuer ces appels. Par exemple, vous pouvez mettre à jour la description et le propriétaire du flux avec l’appel suivant :

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> La syntaxe pour changer d’utilisateur utilise le format `odata.bind`. Cela signifie qu’au lieu d’appliquer une mise à jour corrective au champ \_ownerid_value directement, vous ajoutez `@odata.bind` au nom de la propriété et entourez l’ID avec `systemusers()`.

Dans un autre exemple, vous pouvez activer un flux avec cet appel :

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Supprimer un flux

Supprimer un flux avec un simple appel `DELETE` :

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Vous ne pouvez pas supprimer un flux qui est activé. Vous devez d’abord désactiver le flux (voir **Mise à jour d’un flux**), sinon vous rencontrerez l’erreur : `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Obtenir tous les utilisateurs avec qui un flux est partagé

Pour lister les utilisateurs avec un accès, utilisez une *fonction* dans Common Data Service. Cette fonction prend un paramètre unique de `Target` :

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

Le paramètre `Target` est une chaîne similaire à JSON avec une propriété unique appelée `@odata.id`. Remplacez l’ID du flux de travail dans l’exemple ci-dessus. Cela renvoie :

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Partager ou annuler le partage d’un flux

Vous pouvez partager un flux à l’aide de l’action `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

Le paramètre `AccessMask` est un champ avec les valeurs suivantes pour différents niveaux d’autorisation :

| Nom         | Description                                          |
| ------------ | ---------------------------------------------------- |
| Aucune         | Aucun accès.                                           |
| ReadAccess   | Droit de lire le flux.                          |
| WriteAccess  | Droit de mettre à jour le flux.                        |
| DeleteAccess | Droit de supprimer le flux.                        |
| ShareAccess  | Droit de partager le flux.                         |
| AssignAccess | Droit de modifier le propriétaire du flux.           |

Vous pouvez combiner les autorisations avec une virgule. Par exemple, pour fournir la capacité à lire et à mettre à jour un flux, envoyez `ReadAccess,WriteAccess`.

Vous pouvez *annuler le partage* d’un flux avec l’action `RevokeAccess`. Voici un exemple :

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess` permet de supprimer toutes les autorisations accordées dans `AccessMask`.

## <a name="export-flows"></a>Exporter les flux

Utilisez l’action `ExportSolution` pour exporter des flux dans un fichier .zip. Ajoutez d’abord les flux de votre choix à une [solution](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Une fois vos flux dans une solution, appelez l’action suivante :

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` retourne une chaîne encodée 64 dans la propriété `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Vous pouvez alors sauvegarder ce fichier dans le contrôle de code source et/ou utiliser un système de distribution ou de gestion de la version que vous voulez.

## <a name="import-flows"></a>Importer des flux

Appelez l’action `ImportSolution` pour importer une solution.

| Nom de la propriété                    | Description                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | S’il y a des instances de ces flux dans Common Data Service, cet indicateur doit être défini sur `true` pour les importer. Sinon, elles ne seront pas remplacées. |
| PublishWorkflows                 | Indique si des flux de travail Common Data Service classiques seront activés lors de l’importation. Ce paramètre ne s’applique pas à d’autres types de flux. |
| ImportJobId                      | Fournit une nouvelle et unique interface graphique utilisateur pour suivre la tâche d’importation. |
| CustomizationFile                | Un fichier zip de base encodé 64 contenant la solution. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

L’importation est une opération à long terme. La réponse à l’action ImportSolution est donc `204 No content`. Pour suivre la progression, appelez une action `GET` sur l’objet `importjobs`, en fournissant le `ImportJobId` que vous avez inclus dans l’action d’origine `ImportSolution`.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Cet appel retourne le statut de l’opération d’importation, avec `progress` (le pourcentage de progression), `startedon` et `completedon` (si l’importation est terminée).

Une fois l’importation terminée, vous devez configurer les connexions pour le flux, car la propriété `connectionNames` sera sûrement différente dans l’environnement de destination (si les connexions existent). Si vous configurez de nouvelles connexions dans l’environnement de destination, le propriétaire des flux doit alors les créer dans le concepteur Microsoft Flow. Si les connexions sont déjà configurées dans le nouvel environnement, vous pouvez `PATCH` sur la propriété `clientData` du flux avec les noms des connexions.
