---
title: Utiliser des flux de processus d’entreprise à l’aide de code | MicrosoftDocs
description: Découvrez comment travailler par programmation avec les flux de processus d’entreprise pour créer des processus d’entreprise plus efficaces et rationalisés.
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
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547725"
---
# <a name="work-with-business-process-flows-using-code"></a>Travailler avec des flux de processus d’entreprise à l’aide de code
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Un *processus d’entreprise* vous permet de créer des processus d’entreprise plus efficaces et rationalisés. Il crée une visualisation de votre processus d’entreprise en plaçant des contrôles spéciaux en haut des formulaires d’entité. Les utilisateurs sont guidés par le biais de différentes étapes des processus de vente, de marketing ou de service jusqu’à leur achèvement. Chaque processus prend en charge plusieurs étapes et étapes. Vous pouvez ajouter ou supprimer des étapes, modifier l’ordre des étapes ou ajouter de nouvelles entités au processus d’entreprise.  
  
Différentes instances de workflow de processus d’entreprise peuvent s’exécuter simultanément sur le même enregistrement d’entité. Les utilisateurs peuvent basculer entre les instances de processus d’entreprise simultanées et reprendre leur travail à une étape actuelle du processus. 

Cette rubrique fournit des informations sur la façon dont vous pouvez travailler par programmation avec les flux de processus d’entreprise.

> [!NOTE]
> Vous n’avez pas besoin d’écrire du code pour travailler avec des flux de processus d’entreprise. Pour plus d’informations sur l’utilisation de l’interface utilisateur pour créer et gérer des flux de processus d’entreprise, consultez [vue d’ensemble des flux de processus d’entreprise](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Conditions préalables pour le workflow de processus d’entreprise 

Les entités personnalisées et les entités qui ont mis à jour des formulaires d’interface utilisateur peuvent participer au processus d’entreprise. Les entités d’interface utilisateur mises à jour ont la propriété <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> définie sur `true`. 

Pour activer une entité pour le workflow du processus d’entreprise, affectez à la propriété <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> la valeur `true`.

> [!IMPORTANT]
>  L’activation d’une entité pour le processus d’entreprise est un processus unidirectionnel. Vous ne pouvez pas l’inverser.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Définir le déroulement du processus d’entreprise
  
Utilisez le concepteur Visual Business Process Flow pour définir un processus d’entreprise. Pour en savoir plus : [créer un workflow de processus d’entreprise](../create-business-process-flow.md)

Par défaut, un enregistrement de workflow de processus d’entreprise est créé dans l’État `Draft`.  

Une définition de workflow de processus d’entreprise est stockée dans l’entité <xref:Microsoft.Dynamics.CRM.workflow>, et les informations d’étape pour le workflow de processus d’entreprise sont stockées dans l’entité <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Activer le workflow de processus d’entreprise  
 Avant de pouvoir utiliser le processus, vous devez l’activer. Pour l’activer, vous devez disposer du privilège `prvActivateBusinessProcessFlow` pour l’entité `Workflow`. Utilisez le message <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> pour définir l’état de l’enregistrement d’entité `Workflow` sur `Activated`. Pour plus d’informations : [effectuer des opérations spécialisées à l’aide de la mise à jour](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > Vous pouvez également utiliser le concepteur de workflow de processus d’entreprise pour activer un workflow de processus d’entreprise. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entité Business Process Flow 
 Une fois que vous avez activé une définition de workflow de processus d’entreprise en modifiant l’état de l’enregistrement d’entité `Workflow` correspondant ou à l’aide du concepteur de workflow de processus d’entreprise, une entité personnalisée portant le nom suivant est automatiquement créée pour stocker l’entreprise activée instances de workflow de processus : « *\<activesolutionprefix >* _ *\<UniqueName >* », où le UniqueName est dérivé du nom que vous spécifiez.  
  
 Par exemple, si vous avez spécifié « mon BPF personnalisé » comme nom de la définition de workflow de processus d’entreprise et que vous utilisez le serveur de publication par défaut (nouveau) pour votre solution active, le nom de l’entité personnalisée créée pour le stockage des instances de processus sera « new_mycustombpf ».  
  
 Si la valeur de `uniquename` n’est pas disponible pour une définition de workflow de processus d’entreprise, par exemple si le workflow de processus d’entreprise a été importé dans le cadre de la solution à partir d’une version antérieure, le nom par défaut de l’entité personnalisée sera «`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  L’exemple d’enregistrement de workflow de processus d’entreprise utilise des entités système pour stocker les enregistrements d’instance de workflow de processus d’entreprise correspondants.  
>   
>  Toutefois, les nouvelles définitions de workflow de processus d’entreprise que vous créez utilisent des entités personnalisées pour stocker leurs enregistrements d’instance, comme expliqué précédemment. 

Vous pouvez récupérer le nom de votre entité de workflow de processus d’entreprise à l’aide de l’une des méthodes suivantes :

- **À l’aide de l’interface utilisateur**: utilisez l’interface utilisateur de personnalisation pour accéder à votre entité de workflow de processus d’entreprise :

    ![](media/bpf-entity-name.png)
- **À l’aide de l’API Web**: utilisez la requête suivante :

    **Demande**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Lutte**
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
    ```
- **À l’aide du service d’organisation**: utilisez l’exemple de code suivant :

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
    ```
> [!NOTE]
> La propriété <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> est `true` pour les entités de workflow de processus d’entreprise. Vous pouvez récupérer toutes les entités de workflow de processus d’entreprise dans votre instance en exécutant la requête d’API Web suivante :
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gérer la sécurité des flux de processus d’entreprise

L’entité personnalisée qui est automatiquement créée lors de l’activation d’un workflow de processus d’entreprise pour stocker des instances de workflow de processus d’entreprise adhère au modèle de sécurité standard comme pour toute autre entité personnalisée dans Common Data Service. Cela implique que les privilèges accordés sur ces entités définissent les autorisations d’exécution pour les utilisateurs pour les flux de processus d’entreprise.

L’entité de workflow de processus d’entreprise personnalisée a une étendue d’organisation. Les privilèges de création, de récupération, de mise à jour et de suppression standard sur cette entité définissent l’autorisation dont les utilisateurs ont besoin en fonction des rôles qui leur sont attribués. Par défaut, lorsque l’entité personnalisée de workflow de processus d’entreprise est créée, seuls les rôles de sécurité **administrateur système** et **Personnalisateur de système** y ont accès, et vous devez accorder explicitement des autorisations à la nouvelle entité de workflow de processus d’entreprise (pour exemple, **mon BPF personnalisé**) pour les autres rôles de sécurité requis.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Créer, récupérer, mettre à jour et supprimer des enregistrements d’entité de workflow de processus d’entreprise (instances de processus)  
 L’entité personnalisée qui est automatiquement créée lors de l’activation d’une définition de workflow de processus d’entreprise stocke toutes les instances de processus pour la définition de workflow de processus d’entreprise. L’entité personnalisée prend en charge la création et la gestion de programmes standard des enregistrements (instances de processus) à l’aide de l’API Web et du point de terminaison CRM 2011.

> [!IMPORTANT]
> Le basculement vers une autre instance de processus pour un enregistrement d’entité est pris en charge uniquement par le biais de l’interface utilisateur (client) ou par programme à l’aide des informations disponibles dans cette section. Vous ne pouvez plus utiliser le message d' `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> ou <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) pour basculer les processus par programme (définissez un autre workflow de processus d’entreprise en tant qu’instance de processus active) pour l’enregistrement d’entité cible. 

 Prenons l’exemple suivant, dans lequel nous avons un workflow de processus d’entreprise entre entités, « mon BPF personnalisé », avec 3 étapes : S1 : compte, S2 : compte et S3 : contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Récupérer tous les enregistrements (instances) d’une entité de workflow de processus d’entreprise
 Si le nom de votre entité de workflow de processus d’entreprise est « new_mycustombpf », utilisez la requête suivante pour récupérer tous les enregistrements (instances de processus) de votre entité de workflow de processus d’entreprise :  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

À ce stade, vous risquez de ne pas recevoir d’instances dans votre réponse, car il n’en existe aucune. Exécutez cette demande après avoir créé une instance de votre définition de workflow de processus d’entreprise plus loin dans cette rubrique.

> [!NOTE]
> Pour savoir comment récupérer le nom de votre entité de workflow de processus d’entreprise, consultez la section précédente, [entité Business Process Flow](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Créer un enregistrement d’entité de fluide de processus d’entreprise (instance de processus) 

Créez un enregistrement d’entité de workflow de processus d’entreprise (instance de processus) par programmation si vous souhaitez basculer vers un autre processus d’entreprise pour un enregistrement d’entité sans utiliser l’interface utilisateur. 

Pour créer un enregistrement d’entité de workflow de processus d’entreprise, vous devez spécifier les valeurs suivantes : 
- Associez l’enregistrement d’entité de traitement des processus d’entreprise à un enregistrement d’entité primaire en définissant la propriété de navigation à valeur unique à l’aide de l’annotation `@odata.bind`. Pour déterminer le nom de la propriété de navigation qui pointe vers l’enregistrement d’entité primaire pour votre définition de workflow de processus d’entreprise, utilisez le [document $Metadata CSDL](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associez l’enregistrement d’entité de traitement des processus d’entreprise à une étape valide spécifiée dans la définition du workflow de processus d’entreprise en définissant la propriété de navigation à valeur unique à l’aide de l’annotation `@odata.bind`. Pour connaître le nom de la propriété de navigation (généralement `activestageid`) qui pointe vers l’enregistrement d’étape pour votre définition de workflow de processus d’entreprise, utilisez le [document CSDL $Metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    En outre, vous pouvez récupérer des informations sur toutes les étapes d’une définition de workflow de processus d’entreprise à l’aide de la demande d’API Web suivante en supposant que l’ID de votre définition de workflow de processus d’entreprise est 2669927e-8ad6-4f95-8a9a-f1008af6956f :

    **Demande**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Lutte**

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

Ensuite, utilisez la requête suivante pour créer une instance de votre définition de workflow de processus d’entreprise pour un enregistrement de compte (ID = a176be9e-9a68-E711-80e7-00155d41e206) et l’étape active définie comme première étape de l’instance de processus, S1 (ID = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Demande**

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

**Lutte**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Notez que, si vous souhaitez créer une instance de votre définition de workflow de processus d’entreprise avec l’étape active définie comme ***une étape différente de la*** première étape, vous devez également fournir `traversedpath` dans votre demande. Le chemin parcouru est la chaîne délimitée par des virgules des ID d’étape de processus qui représentent les étapes visitées de l’instance de workflow de processus d’entreprise. La demande suivante crée une instance pour un enregistrement de compte (ID = 679b2464-71b5-E711-80f5-00155d513100) et un ensemble d’étapes actives comme deuxième étape, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Mettre à jour un enregistrement d’entité de fluide de processus d’entreprise (instance de processus)

Vous pouvez mettre à jour une instance de processus pour passer à l’étape suivante ou précédente, abandonner une instance de processus, réactiver une instance de processus ou terminer une instance de processus. 

#### <a name="stage-navigation"></a>Navigation dans les étapes

Pour accéder à une autre étape, vous devez mettre à jour un enregistrement d’instance de processus pour modifier son ID d’étape active et mettre à jour le chemin parcouru. Notez que vous devez passer à l’étape suivante ou précédente lors de la mise à jour d’une instance de workflow de processus d’entreprise.

Pour effectuer la navigation entre les étapes, vous avez besoin de l’ID de l’instance de workflow de processus d’entreprise que vous souhaitez mettre à jour. Pour récupérer toutes les instances de votre processus d’entreprise, consultez [récupérer les enregistrements (instances) d’une entité de workflow de processus d’entreprise](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) précédemment.

En supposant que l’ID de l’instance de processus que vous souhaitez mettre à jour est dc2ab599-306d-e811-80ff-00155d513100, utilisez la requête suivante pour mettre à jour l’étape active de S1 à S2 :

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Modifier l’état d’une instance de processus : abandonner, réactiver ou terminer 

Une instance de processus peut avoir l’un des États suivants : **actif**, **terminé**ou **abandonné**. L’État est déterminé par les attributs suivants sur l’enregistrement d’instance de processus :

- **statecode**: affiche l’état de l’instance de processus.

    |ajoutée|Noms|
    |-----|-----|
    |entre    |Proactive|
    |1,0    |Inactive|

- **statusCode**: affiche des informations sur l’état de l’instance de processus.

    |ajoutée|Noms|
    |-----|-----|
    |1,0    |Proactive|
    |2    |Démarré|
    |1,3    |Abandonnée|

Par conséquent, pour **abandonner** une instance de processus, utilisez la demande suivante, définissez les valeurs `statecode` et `statuscode` de manière appropriée :

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
> Vous pouvez abandonner une instance de processus à tout moment.

De même, pour réactiver une instance de processus, remplacez les valeurs `statecode` et `statuscode` dans le code ci-dessus respectivement par **0** et **1** .

Enfin, pour définir l’état d’une instance de processus comme **terminé**, ce qui n’est possible qu’à la dernière étape d’une instance de processus, remplacez les valeurs `statecode` et `statuscode` dans le code ci-dessus par **0** et **2** , respectivement.

#### <a name="cross-entity-navigation"></a>Navigation entre les entités

Pour la navigation entre les entités dans cet exemple, vous devez définir l’étape active de l’instance de processus à la dernière étape, S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), mettre à jour le chemin parcouru en conséquence et définir un enregistrement de contact en tant qu’enregistrement d’entité primaire en fonction de définition du workflow de processus d’entreprise.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Supprimer un enregistrement d’entité de fluide de processus d’entreprise (instance de processus)

Utilisez la demande d’API Web suivante :

**Demande**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Lutte**

Si l’enregistrement existe, vous obtenez une réponse normale avec l’État 204 pour indiquer que la suppression a réussi. Si l’entité est introuvable, vous obtenez une réponse avec l’État 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Utiliser des messages RetrieveProcessInstances et RetrieveActivePath

Utilisez le message d' `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) pour récupérer toutes les instances de workflow de processus d’entreprise pour un enregistrement d’entité dans toutes les définitions de processus d’entreprise. Les instances de workflow de processus d’entreprise retournées pour une entité sont triées en fonction de l’attribut `modifiedon` de l’instance. Par exemple, l’instance de workflow de processus d’entreprise modifié le plus récemment sera le *premier* enregistrement dans la collection retournée. L’instance de workflow de processus d’entreprise récemment modifiée est celle qui est active sur l’interface utilisateur pour un enregistrement d’entité.  
  
Chaque enregistrement d’instance de workflow de processus d’entreprise renvoyé pour un enregistrement d’entité à la suite de l’utilisation de la `RetrieveProcessInstances` message stocke l’ID de l’étape active dans l’attribut `processstageid` qui peut être utilisé pour Rechercher l’étape active, puis passer à l’étape précédente ou suivante. Pour ce faire, vous devez d’abord Rechercher le chemin d’accès actif d’une instance de workflow de processus d’entreprise et les étapes disponibles dans l’instance de workflow à l’aide du message de `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Une fois que vous avez l’étape active et les informations de chemin d’accès actives pour une instance de workflow de processus d’entreprise, vous pouvez utiliser ces informations pour passer à l’étape précédente ou suivante dans le chemin d’accès actif. La navigation vers l’avant des étapes doit être effectuée dans l’ordre, autrement dit, vous ne devez passer à l’étape suivante que dans le chemin d’accès actif.   
  
 Pour obtenir un exemple complet du code illustrant l’utilisation de ces deux méthodes et de la navigation au niveau des étapes à l’aide du [service d’organisation](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), consultez [exemple : travailler avec des flux de processus d’entreprise](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Appliquer le workflow de processus d’entreprise lors de la création d’un enregistrement d’entité

Cette section fournit des informations sur le comportement par défaut pour appliquer automatiquement des flux de processus d’entreprise aux nouveaux enregistrements d’entité créés dans Common Data Service, et comment vous pouvez le remplacer pour appliquer un flux de processus d’entreprise de votre choix pour de nouveaux enregistrements d’entité.

Par défaut, pour une entité qui a plusieurs flux de processus d’entreprise définis pour celle-ci, le système applique un flux de processus d’entreprise au nouvel enregistrement d’entité à l’aide de la logique en plusieurs étapes suivante :
1. Identifiez tous les flux de processus d’entreprise applicables au nouvel enregistrement d’entité en fonction de l’attribut **Workflow. PrimaryEntity** des enregistrements de définition de flux de processus d’entreprise.
2. Identifiez les définitions de workflow de processus d’entreprise auxquelles l’utilisateur actuel a accès. Pour plus d’informations sur la façon dont l’accès à un flux de processus d’entreprise est déterminé et géré, consultez [gérer la sécurité des flux de processus d’entreprise](#BPFSecurity) plus haut dans cette rubrique.<br/>  
3. Toutes les définitions de workflow de processus d’entreprise dans le système sont soumises à une commande globale par entité. L’ordre du flux de processus d’entreprise est stocké dans l’attribut **Workflow. ProcessOrder** . Les définitions de workflow de processus d’entreprise pour une entité sont triées en fonction de cette commande, et celle avec la valeur de commande la moins faible est choisie.
4. Enfin, si l’enregistrement d’entité est créé à partir d’une application d’entreprise (module d’application), un niveau supplémentaire de filtrage est appliqué pour choisir le processus d’entreprise à appliquer automatiquement au nouvel enregistrement d’entité. Lorsque vous travaillez dans une application, les utilisateurs peuvent accéder uniquement aux entités pertinentes, aux flux de processus d’entreprise, aux affichages et aux formulaires auxquels ils ont accès en vertu des rôles de sécurité attribués à l’application d’entreprise. 
    - Si l’application d’entreprise ne contient pas de workflow de processus d’entreprise, le workflow de processus d’entreprise est appliqué comme expliqué jusqu’à l’étape 3.
    - Si l’application d’entreprise possède un ou plusieurs flux de processus d’entreprise, seuls les flux de processus d’entreprise présents dans l’application sont applicables. Dans ce cas, lorsque l’utilisateur travaille dans un contexte d’application métier, la liste des flux de processus d’entreprise de l’étape 3 est filtrée plus loin que celle qui fait partie de l’application métier présente dans le module d’application et est triée en fonction de l’ordre des processus. 
    - Si aucun workflow de processus d’entreprise n’est disponible dans une application d’entreprise pour l’entité ou une application à laquelle l’utilisateur a accès, aucun workflow de processus d’entreprise n’est appliqué pour le nouvel enregistrement d’entité.

Vous pouvez remplacer la logique par défaut des flux de processus d’entreprise qui est appliquée automatiquement aux nouveaux enregistrements d’entité. Pour ce faire, définissez l’attribut **ProcessID** de l’entité sur l’une des valeurs suivantes lors de la création d’un nouvel enregistrement d’entité :
- Affectez la valeur **GUID. Empty** pour ignorer la définition d’un workflow de processus d’entreprise pour les nouveaux enregistrements d’entité. Vous souhaiterez peut-être le faire si vous créez en bloc des enregistrements d’entité, mais que vous ne voulez pas que le workflow de processus d’entreprise leur soit appliqué.
- Affectez-lui une entité de workflow de processus d’entreprise spécifique (comme référence d’entité). Dans ce cas, le système applique le workflow de processus d’entreprise spécifié au lieu de la logique par défaut.

Si vous ne définissez pas de valeur pour l’attribut **ProcessID** lors de la création d’un nouvel enregistrement d’entité, le système applique la logique par défaut comme expliqué précédemment.

> [!NOTE]
> La substitution de la logique par défaut des flux de processus d’entreprise s’appliquant automatiquement aux nouveaux enregistrements d’entité est prise en charge par programme uniquement. Vous ne pouvez pas le faire à l’aide de l’interface utilisateur.

## <a name="legacy-process-related-attributes-in-entities"></a>Attributs de processus hérités dans les entités

Les attributs de processus hérités (tels que **ProcessID**, **StageId**et **TraversedPath**) sur les entités activées pour les flux de processus d’entreprise sont déjà dépréciés. La manipulation de ces attributs de processus hérités pour les enregistrements d’entité cible ne garantit pas la cohérence de l’état du processus d’entreprise et n’est ***pas*** un scénario pris en charge. La méthode recommandée consiste à utiliser les attributs de l’entité de workflow de processus d’entreprise, comme expliqué précédemment dans la section [créer, récupérer, mettre à jour et supprimer des enregistrements d’entité de workflow de processus d’entreprise (instances de processus)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances) .

La seule exception est la modification par programmation de l’attribut **ProcessID** lors de la création d’un enregistrement d’entité pour remplacer l’application par défaut du workflow du processus d’entreprise par le nouvel enregistrement, comme expliqué dans la section précédente : [application d’entreprise processus de création d’un enregistrement d’entité](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Prise en charge de la programmabilité côté client pour les flux de processus d’entreprise  
 Il existe un objet côté client que vous pouvez utiliser pour interagir avec les flux de processus d’entreprise dans vos scripts de formulaire. Les flux de processus d’entreprise déclenchent des événements côté client chaque fois qu’un processus est appliqué à un enregistrement, que l’étape est modifiée ou que son état est modifié en `Active`, `Finished`ou `Aborted`. Informations supplémentaires : [formContext. Data. Process (informations de référence sur l’API Client)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Nombre maximal de processus, étapes et étapes  
 Par entité, la valeur par défaut du nombre maximal de flux de processus d’entreprise activés est 10. Vous pouvez spécifier une autre valeur à l’aide de l’attribut `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. Toutefois, si la valeur est supérieure à 10, vous pouvez constater une diminution des performances de votre système lorsque vous basculez des processus ou ouvrez un enregistrement qui a un workflow de processus d’entreprise attribué. Cela peut être particulièrement perceptible si les processus s’étendent sur plusieurs entités.  
  
 Les paramètres suivants ne sont pas personnalisables :  
  
-   Le nombre maximal d’étapes par entité dans le processus est de 30.  
  
-   Le nombre maximal d’étapes dans chaque phase est de 30.  
  
-   Le nombre maximal d’entités pouvant participer au processus est de 5.  

