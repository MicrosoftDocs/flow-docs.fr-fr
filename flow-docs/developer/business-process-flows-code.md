---
title: Utiliser des flux de processus métier à l’aide de code | Microsoft Docs
description: Découvrez comment utiliser des flux de processus métier par programmation pour créer des processus métier simplifiés et plus efficaces.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: ae3633047bda556058c8e2ec94e6411e7f277e76
ms.sourcegitcommit: 50ea1cdd763863a2cbc88f9f965bdf9351f1059c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2018
ms.locfileid: "44691063"
---
# <a name="work-with-business-process-flows-using-code"></a>Utiliser des flux de processus métier à l’aide de code

Un *flux de processus métier* vous permet de créer des processus métier de ventes, de service et autres plus efficaces et simplifiés. Il crée une visualisation de votre processus métier en plaçant des contrôles spéciaux en haut des formulaires d’entité. Les utilisateurs sont guidés tout au long des différentes phases des processus de ventes, de marketing ou de service. Chaque processus prend en charge plusieurs phases et étapes. Vous pouvez ajouter ou supprimer des étapes, changer l’ordre des phases ou ajouter de nouvelles entités au flux de processus.  
  
Différentes instances de flux de processus métier peuvent s’exécuter simultanément sur le même enregistrement d’entité. Les utilisateurs peuvent basculer entre des instances de processus métier simultanées et reprendre leur travail au niveau d’une phase actuelle dans le processus. 

Cette rubrique fournit des informations sur la façon dont vous pouvez utiliser des flux de processus métier par programmation.

> [!NOTE]
> Vous n’avez pas besoin d’écrire de code pour utiliser des flux de processus métier. Pour plus d’informations sur l’utilisation de l’interface utilisateur pour créer et gérer des flux de processus métier, consultez [Vue d’ensemble des flux de processus métier](../business-process-flows-overview.md).  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Prérequis pour le flux de processus métier 

Les entités personnalisées et les entités qui ont des formulaires d’interface utilisateur mis à jour peuvent participer au flux du processus. Les entités d’interface utilisateur mises à jour ont la propriété <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> définie sur `true`. 

Pour activer une entité pour le flux de processus métier, définissez la propriété <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> sur `true`.

> [!IMPORTANT]
>  L’activation d’une entité pour le flux de processus métier est un processus unidirectionnel. Vous ne pouvez pas l’annuler.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Définir un flux de processus métier
  
Utilisez le concepteur de flux de processus métier visuel pour définir un flux de processus métier. Pour plus d’informations, consultez [Créer un flux de processus métier](../create-business-process-flow.md).

Par défaut, un enregistrement de flux de processus métier est créé dans l’état `Draft`.  

La définition d’un flux de processus métier est stockée dans l’entité <xref:Microsoft.Dynamics.CRM.workflow>, tandis que les informations sur les phases du flux de processus métier sont stockées dans l’entité <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Activer le flux de processus métier  
 Pour pouvoir utiliser le flux de processus, vous devez l’activer. Pour ce faire, vous devez avoir le privilège `prvActivateBusinessProcessFlow` pour l’entité `Workflow`. Utilisez le message <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> pour définir l’état de l’enregistrement d’entité `Workflow` sur `Activated`. Pour plus d’informations, consultez [Effectuer des opérations spécialisées à l’aide d’une mise à jour](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update). 

 > [!NOTE]
 > Vous pouvez également utiliser le concepteur de flux de processus métier pour activer un flux de processus métier. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entité de flux de processus métier 
 Une fois que vous avez activé la définition d’un flux de processus métier en changeant l’état de l’enregistrement d’entité `Workflow` correspondant ou en utilisant le concepteur de flux de processus métier, une entité personnalisée portant le nom suivant est automatiquement créée pour stocker les instances du flux de processus métier activé : « *\<préfixe_solution_active>*_*\<nom_unique>*  », où nom_unique est dérivé du nom que vous spécifiez.  
  
 Par exemple, si vous avez spécifié « My Custom BPF » (Mon FPM personnalisé) comme nom de définition de flux de processus métier et que vous utilisez l’éditeur par défaut (nouveau) pour votre solution active, le nom de l’entité personnalisée créée pour stocker les instances de processus est « new_mycustombpf ».  
  
 Si la valeur `uniquename` n’est pas disponible pour la définition d’un flux de processus métier, par exemple, si le flux de processus a été importé dans le cadre de la solution à partir d’une version antérieure, le nom par défaut de l’entité personnalisée est « *\<préfixe_solution_active>*\_bpf\_*<GUID_définition_FPM>*  » :  
  
> [!IMPORTANT]
>  Les exemples d’enregistrements de flux de processus métier utilisent des entités système pour stocker les enregistrements d’instance de flux de processus métier correspondants.  
>   
>  Toutefois, toute définition de flux de processus métier que vous créez utilise des entités personnalisées pour stocker ses enregistrements d’instance comme expliqué précédemment. 

Vous pouvez récupérer le nom de votre entité de flux de processus métier de l’une des manières suivantes :

- **Utilisation de l’interface utilisateur** : utilisez l’interface utilisateur de personnalisation pour accéder à votre entité de flux de processus métier :

    ![](media/bpf-entity-name.png)
- **Utilisation de l’API web** : utilisez la requête suivante :

    **Requête**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Réponse**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }

- **Using the Organization service**: Use the following code sample:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 

> [!NOTE]
> The <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> property is `true` for business process flow entities. You can retrieve all the business process flow entities in your instance by running the following Web API request:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## Manage security for business process flows

The custom entity that is automatically created on activating a business process flow to store business process flow instances adheres to the standard security model as for any other custom entity in Customer Engagement. This implies that privileges granted on these entities define the runtime permissions for users for business process flows.

The custom business process flow entity has organization scope. The regular create, retrieve, update and delete privileges on this entity define the permission the user would have based on his/her assigned roles. By default, when the business process flow custom entity is created, only **System Administrator** and **System Customizer** security roles are granted access to it, and you must explicitly grant permissions to the new business process flow entity (for example, **My Custom BPF**) for other security roles as required.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## Create, retrieve, update, and delete business process flow entity records (process instances)  
 The custom entity that is automatically created on activating a business process flow definition stores all the process instances for the business process flow definition. The custom entity supports the standard programmatic creation and management of records (process instances) using Web API and CRM 2011 endpoint.

> [!IMPORTANT]
> Switching to another process instance for an entity record is only supported through UI (client) or programmatically using information available in this section. You can no longer use the `SetProcess` message (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> or <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) to programmatically switch processes (set another business process flow as the active process instance) for the target entity record. 

 Lets consider the following example where we have a cross-entity business process flow, "My Custom BPF," with 3 stages: S1:Account, S2:Account, and S3:Contact. 

 ![](media/sample-bpf.png)
 
### Retrieve all the records (instances) for a business process flow entity
 If the name of your business process flow entity is "new_mycustombpf", use the following query to retrieve all the records (process instances) for your business process flow entity:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

À ce stade, vous ne pouvez pas obtenir d’instances dans votre réponse, car il n’en existe aucune. Exécutez cette requête après avoir créé une instance de la définition du flux de processus métier plus loin dans cette rubrique.

> [!NOTE]
> Pour savoir comment récupérer le nom de votre entité de flux de processus métier, consultez la section précédente, [Entité de flux de processus métier](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Créer un enregistrement d’entité de flux de processus métier (instance de processus) 

Créez un enregistrement d’entité de flux de processus métier (instance de processus) par programmation si vous souhaitez basculer vers un autre flux de processus métier pour un enregistrement d’entité sans utiliser l’interface utilisateur. 

Pour créer un enregistrement d’entité de flux de processus métier, vous devez spécifier les valeurs suivantes : 
- Associez l’enregistrement d’entité de flux de processus métier à un enregistrement d’entité principale en définissant la propriété de navigation à valeur unique à l’aide de l’annotation `@odata.bind`. Pour trouver le nom de la propriété de navigation qui pointe vers l’enregistrement d’entité principale pour la définition du flux de processus métier, utilisez le [document CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associez l’enregistrement d’entité de flux de processus métier à une phase valide spécifiée dans la définition du flux de processus métier en définissant la propriété de navigation à valeur unique à l’aide de l’annotation `@odata.bind`. Pour trouver le nom de la propriété de navigation (généralement `activestageid`) qui pointe vers l’enregistrement de phase pour la définition du flux de processus métier, utilisez le [document CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    En outre, vous pouvez récupérer des informations sur toutes les phases pour la définition d’un flux de processus métier à l’aide de la requête d’API web suivante, où l’ID de la définition du flux de processus métier est 2669927e-8ad6-4f95-8a9a-f1008af6956f :

    **Requête**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Réponse**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Ensuite, utilisez la requête suivante afin de créer une instance de la définition du flux de processus métier pour un enregistrement de compte (ID=a176be9e-9a68-e711-80e7-00155d41e206) avec la phase active définie en tant que première phase de l’instance de processus, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b) :

**Requête**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Réponse**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Notez que si vous souhaitez créer une instance de la définition du flux de processus métier avec la phase active définie en tant que phase ***autre*** que la première phase, vous devez également fournir `traversedpath` dans votre requête. Le chemin parcouru est la chaîne délimitée par des virgules des ID de phase de processus qui représentent les phases visitées de l’instance du flux de processus métier. La requête suivante crée une instance d’un enregistrement de compte (ID=679b2464-71b5-e711-80f5-00155d513100) avec la phase active définie en tant que deuxième phase, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Mettre à jour un enregistrement d’entité de flux de processus métier (instance de processus)

Vous pouvez mettre à jour une instance de processus pour passer à la phase suivante ou précédente, abandonner une instance de processus, réactiver une instance de processus ou terminer une instance de processus. 

#### <a name="stage-navigation"></a>Accès à une phase

Pour accéder à une autre phase, vous devez mettre à jour un enregistrement d’instance de processus afin de changer son ID de phase active et de mettre à jour le chemin parcouru en conséquence. Notez que vous devez uniquement passer à la phase suivante ou précédente quand vous mettez à jour une instance de flux de processus métier.

Pour accéder à une phase, vous avez besoin de l’ID de l’instance de flux de processus métier que vous souhaitez mettre à jour. Pour récupérer toutes les instances de flux de processus métier, consultez [Récupérer tous les enregistrements (instances) pour une entité de flux de processus métier](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) plus haut.

En supposant que l’ID de l’instance de processus que vous souhaitez mettre à jour est dc2ab599-306d-e811-80ff-00155d513100, utilisez la requête suivante pour mettre à jour la phase active de S1 à S2 :

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Changer l’état d’une instance de processus : Abandonner, Réactiver ou Terminer 

Une instance de processus peut avoir un des états suivants : **Actif**, **Terminé** ou **Abandonné**. L’état est déterminé par les attributs suivants sur l’enregistrement d’instance de processus :

- **statecode** : affiche l’état de l’instance de processus.

    |Valeur|Étiquette|
    |-----|-----|
    |0    |Actif|
    |1    |Inactif|

- **statuscode** : affiche des informations sur le statut de l’instance de processus.

    |Valeur|Étiquette|
    |-----|-----|
    |1    |Actif|
    |2    |Terminé|
    |3    |Abandonné|

Ainsi, pour **Abandonner** une instance de processus, utilisez la requête suivante en définissant les valeurs `statecode` et `statuscode` de manière appropriée :

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Vous pouvez abandonner une instance de processus dans n’importe quelle phase.

De même, pour réactiver une instance de processus, remplacez les valeurs `statecode` et `statuscode` dans le code ci-dessus par **0** et **1** respectivement.

Enfin, pour définir un statut d’instance de processus comme étant **Terminé**, ce qui n’est possible qu’à la dernière phase d’une instance de processus, remplacez les valeurs `statecode` et `statuscode` dans le code ci-dessus par **0** et **2** respectivement.

#### <a name="cross-entity-navigation"></a>Navigation entre les entités

Pour naviguer entre les entités dans cet exemple, vous devez définir la phase active de l’instance de processus sur la dernière phase, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), mettre à jour le chemin parcouru en conséquence et définir un enregistrement de contact en tant qu’enregistrement d’entité principale selon la définition du flux de processus métier.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Supprimer un enregistrement d’entité de flux de processus métier (instance de processus)

Utilisez la requête d’API web suivante :

**Requête**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Réponse**

Si l’enregistrement existe, vous obtenez une réponse normale avec le statut 204 indiquant que la suppression a réussi. Si l’entité est introuvable, vous obtenez une réponse avec le statut 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Utiliser des messages RetrieveProcessInstances et RetrieveActivePath

Utilisez le message `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) pour récupérer toutes les instances de flux de processus métier pour un enregistrement d’entité dans toutes les définitions de processus métier. Les instances de flux de processus métier retournées pour une entité sont classées en fonction de l’attribut `modifiedon` qui leur est associé. Par exemple, l’instance de flux de processus métier la plus récemment modifiée est le *premier* enregistrement dans la collection retournée. L’instance de flux de processus métier la plus récemment modifiée est celle qui est active sur l’interface utilisateur pour un enregistrement d’entité.  
  
Chaque enregistrement d’instance de flux de processus métier retourné pour un enregistrement d’entité suite à l’utilisation du message `RetrieveProcessInstances` stocke l’ID de la phase active dans l’attribut `processstageid` qui peut être utilisé pour rechercher la phase active, puis pour passer à la phase précédente ou suivante. Pour ce faire, vous devez tout d’abord rechercher le chemin d’accès actif d’une instance de flux de processus métier et les phases disponibles dans l’instance de flux de processus à l’aide du message `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Une fois que vous disposez des informations sur la phase active et le chemin d’accès actif pour une instance de flux de processus métier, vous pouvez utiliser ces informations pour passer à une phase précédente ou suivante dans le chemin d’accès actif. La navigation vers l’avant parmi les phases doit être effectuée dans l’ordre ; autrement dit, vous devez uniquement passer à la phase suivante dans le chemin d’accès actif.   
  
 Pour obtenir l’exemple de code complet qui illustre l’utilisation de ces deux méthodes et l’accès aux phases à l’aide du [service d’organisation](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), consultez [Exemple : Utiliser des flux de processus métier](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Appliquer des flux de processus métier pendant la création d’un enregistrement d’entité

Cette section fournit des informations sur le comportement par défaut de l’application automatique de flux de processus métier aux enregistrements d’entité créés dans Customer Engagement, ainsi que sur la façon de contourner ce comportement afin d’appliquer un flux de processus métier de votre choix pour les nouveaux enregistrements d’entité.

Par défaut, pour une entité pour laquelle plusieurs flux de processus métier sont définis, le système applique un flux de processus métier au nouvel enregistrement d’entité à l’aide de la logique à plusieurs étapes suivante :
1. Identifier tous les flux de processus métier applicables au nouvel enregistrement d’entité selon l’attribut **Workflow.PrimaryEntity** des enregistrements de définition de flux de processus métier.
2. Identifier les définitions de flux de processus métier auxquelles l’utilisateur actuel a accès. Pour plus d’informations sur la détermination et la gestion de l’accès à un flux de processus métier, consultez [Gérer la sécurité des flux de processus métier](#BPFSecurity) plus haut dans cette rubrique.<br/>  
3. Toutes les définitions de flux de processus métier dans le système sont soumises à un ordre global par entité. L’ordre du flux de processus métier est stocké dans l’attribut **Workflow.ProcessOrder**. Les définitions de flux de processus métier pour une entité sont triées en fonction de cet ordre ; celle ayant la plus petite valeur d’ordre est choisie.
4. Enfin, si l’enregistrement d’entité est créé à partir d’une application métier (module d’application), un niveau de filtrage supplémentaire est appliqué pour récupérer le flux de processus métier à appliquer automatiquement au nouvel enregistrement d’entité. Quand vous travaillez dans une application métier, les entités, flux de processus métier, vues et formulaires accessibles aux utilisateurs sont déterminés par les rôles de sécurité attribués à l’application. 
    - Si l’application métier ne contient pas de flux de processus métier, le flux de processus métier est appliqué comme expliqué jusqu’à l’étape 3.
    - Si l’application métier a un ou plusieurs flux de processus métier, seuls les flux de processus métier présents dans l’application sont applicables. Dans ce cas, quand l’utilisateur travaille dans le contexte d’une application métier, la liste des flux de processus métier issue de l’étape 3 est filtrée de manière à ne contenir que ceux qui font partie de l’application métier et qui sont présents dans le module d’application, puis est triée en fonction de l’ordre des processus. 
    - Si aucun flux de processus métier n’est disponible dans une application métier pour l’entité ou pour une entité à laquelle l’utilisateur a accès, aucun flux de processus métier n’est appliqué pour le nouvel enregistrement d’entité.

Vous pouvez remplacer la logique par défaut qui prévoit l’application automatique des flux de processus métier aux nouveaux enregistrements d’entité. Pour ce faire, définissez l’attribut **ProcessId** de l’entité sur une des valeurs suivantes au moment de la création d’un enregistrement d’entité :
- Définissez-le sur **Guid.Empty** afin d’ignorer la définition d’un flux de processus métier pour les nouveaux enregistrements d’entité. Cette approche peut vous intéresser si vous créez des enregistrements d’entité en bloc, mais que vous ne souhaitez pas que le flux de processus métier leur soit appliqué.
- Définissez-le sur une entité de flux de processus métier spécifique (telle qu’une référence d’entité). Dans ce cas, le système applique le flux de processus métier spécifié au lieu de la logique par défaut.

Si vous ne définissez pas de valeur pour l’attribut **ProcessId** au moment de la création d’un enregistrement d’entité, le système applique la logique par défaut comme expliqué précédemment.

> [!NOTE]
> Le remplacement de la logique par défaut qui prévoit l’application automatique des flux de processus métier aux nouveaux enregistrements d’entité n’est pris en charge que par programmation. Vous ne pouvez pas effectuer cette opération à l’aide de l’interface utilisateur.

## <a name="legacy-process-related-attributes-in-entities"></a>Attributs liés aux processus hérités dans les entités

Les attributs liés aux processus hérités (comme **ProcessId**, **StageId** et **TraversedPath**) sur les entités activées pour les flux de processus métier sont déjà dépréciés. La manipulation de ces attributs liés aux processus hérités pour les enregistrements d’entité cible ne garantissant pas la cohérence de l’état des flux de processus métier, elle ***n’est pas*** un scénario pris en charge. La méthode recommandée consiste à utiliser les attributs de l’entité de flux de processus métier comme expliqué précédemment dans la section [Créer, récupérer, mettre à jour et supprimer des enregistrements d’entité de flux de processus métier (instances de processus)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances).

La seule exception à cette approche est la modification par programmation de l’attribut **ProcessId** pendant la création d’un enregistrement d’entité pour remplacer l’application par défaut du flux de processus métier au nouvel enregistrement, comme expliqué dans la section précédente [Appliquer des flux de processus métier pendant la création d’un enregistrement d’entité](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Prise en charge par programmation côté client des flux de processus métier  
 Il existe un objet côté client que vous pouvez utiliser pour interagir avec les flux de processus métier dans vos scripts de formulaire. Les flux de processus métier déclenchent des événements côté client chaque fois qu’un processus est appliqué à un enregistrement, que la phase est changée ou que son statut passe à `Active`, `Finished` ou `Aborted`. Pour plus d’informations, consultez [formContext.data.process (informations de référence sur l’API cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md).  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Nombre maximal de processus, de phases et d’étapes  
 Par entité, la valeur par défaut pour le nombre maximal de flux de processus métier activés est 10. Vous pouvez spécifier une valeur différente à l’aide de l’attribut `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Toutefois, si la valeur est supérieure à 10, vous pouvez constater une diminution des performances du système quand vous changez de processus ou que vous ouvrez un enregistrement auquel est attribué un flux de processus métier. Cela peut être particulièrement le cas si les processus englobent plusieurs entités.  
  
 Les paramètres suivants ne sont pas personnalisables :  
  
-   Le nombre maximal de phases par entité dans le processus est 30.  
  
-   Le nombre maximal d’étapes par phase est 30.  
  
-   Le nombre maximal d’entités pouvant participer au flux de processus est 5.  

