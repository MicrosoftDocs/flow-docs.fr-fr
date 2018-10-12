---
title: Créer une logique métier personnalisée par le biais de processus avec PowerApps | Microsoft Docs
description: Découvrez les différents types de logique métier que vous pouvez utiliser dans votre application
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b6cf8c2bc5e7499e7eaf5feb367c07a3aa94b3f7
ms.sourcegitcommit: f7985b96afe68b079b7fd4a6d04cd0a042d893e0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2018
ms.locfileid: "47188590"
---
# <a name="create-custom-business-logic-through-processes"></a>Créer une logique métier personnalisée par le biais de processus

La définition et l’application de processus métier cohérents constituent une des principales raisons de l’utilisation d’applications basées sur des modèles. Avec des processus cohérents, les utilisateurs du système peuvent se concentrer sur leur travail sans avoir à l’esprit une liste d’étapes manuelles à effectuer. Les processus peuvent être simples ou complexes et peuvent changer au fil du temps.  
  
PowerApps inclut plusieurs types de processus, chacun conçu pour un objectif différent :  
  
-   Flux de processus métier  
  
-   Flux de tâches mobiles  
  
-   Workflows  
  
-   Actions  
  
 Comme pour les processus, vous pouvez créer des recommandations et des règles métier. Pour plus d’informations, consultez [Créer des recommandations et des règles métier pour appliquer une logique dans un formulaire](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form).  

> [!NOTE]
>  L’utilisation de processus peut impacter les exigences en licence pour PowerApps et Flow. Pour plus d’informations, consultez [Conditions de licence pour les entités](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quand utiliser des flux de processus métier  
 Utilisez un flux de processus métier quand vous souhaitez que vos équipes parcourent les mêmes phases et suivent les mêmes étapes pour interagir avec un client. Par exemple, utilisez un flux de processus métier si vous souhaitez que tous les utilisateurs gèrent les demandes de service client de la même manière ou pour que les équipes obtiennent l’approbation d’une facture avant d’envoyer une commande.  
  
 Votre environnement inclut plusieurs flux de processus métier prêts à l’emploi, que vous pouvez utiliser tels quels ou en les modifiant à peine, pour les tâches courantes de ventes, de service et de marketing. Ou bien, vous pouvez créer les vôtres. Pour plus d’informations sur les flux de processus métier, consultez la rubrique suivante :  
  
-   [Créer un flux de processus métier](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quand utiliser des workflows  
 Utilisez des workflows pour automatiser des processus métier en arrière-plan. Les workflows étant généralement lancés par des événements système, l’utilisateur n’a pas besoin d’avoir conscience qu’ils sont en cours d’exécution. Les workflows qui fonctionnent en arrière-plan sont « asynchrones ». Vous pouvez également configurer des workflows afin qu’ils soient lancés manuellement si vous souhaitez automatiser des tâches courantes, telles que l’envoi automatique d’un e-mail de confirmation à un client quand une commande est expédiée. Les workflows qui opèrent en temps réel sont « synchrones ». Pour plus d’informations sur les workflows, consultez [Processus de workflow](workflow-processes.md).  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quand utiliser des actions  
 Utilisez des actions quand vous souhaitez automatiser une série de commandes dans le système. Les actions développent le vocabulaire dont disposent les développeurs pour exprimer les processus métier. À partir de verbes principaux tels que Créer, Mettre à jour, Supprimer et Attribuer fournis par le système, une action crée des verbes plus expressifs tels qu’Approuver, Réaffecter, Acheminer ou Planifier. Si la définition d’un processus métier change, une personne qui n’est pas développeur peut modifier l’action, si bien que le code n’a pas besoin d’être changé.  Pour plus d’informations sur les actions, consultez [Actions](create-actions.md).  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quand utiliser Microsoft Flow  
 Utilisez Microsoft Flow quand vous avez besoin de créer des workflows automatisés qui effectuent des actions entre votre environnement et votre application ou service favori, tel que Dynamics 365, Twitter, Dropbox, les services Google, Office 365 et SharePoint. Vous pouvez déclencher un flux en fonction d’une action spécifique ou l’appeler à partir de votre application. Plus d’informations : [Utiliser Microsoft Flow pour automatiser des processus entre services](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Comment puis-je créer des processus ?  
 Il existe deux chemins pour accéder au processus :  
  
- Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) et accédez à **Composants > Processus.** Ce chemin est pratique quand vous effectuez un autre travail de personnalisation dans les outils de personnalisation.  

- **[Paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processus.** Ce chemin vous permet d’utiliser les vues définies pour l’entité Processus, y compris toutes les vues personnalisées.  
  
 En outre, vous pouvez modifier un flux de processus métier spécifique à l’aide du bouton **Modifier le processus** dans la barre de commandes liée au formulaire où le flux du processus est actif.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Qui peut créer des processus ?  
 Seules les personnes ayant le rôle de sécurité Administrateur système, Personnalisateur de système ou Directeur général - Dirigeant d’entreprise peuvent créer des processus qui s’appliquent à l’ensemble de l’environnement. Les personnes ayant d’autres rôles peuvent créer des processus avec un niveau d’accès limité. Par exemple, les personnes bénéficiant du niveau d’accès Utilisateur peuvent créer des workflows pour leur propre utilisation avec des enregistrements qu’elles possèdent.  
  
 Le tableau suivant montre le niveau d’accès des processus en fonction des rôles de sécurité par défaut.  
  
|||  
|-|-|  
|**Rôle de sécurité**|**Niveau d’accès**|  
|Directeur général - Dirigeant d’entreprise|Organisation|  
|Administrateur système|Organisation|  
|Personnalisateur de système|Organisation|  
|Vice-président du marketing|Division mère : sous-divisions|  
|Directeur de division|Division mère : sous-divisions|  
|Responsable de service|Division|  
|Directeur du marketing|Division|  
|Directeur commercial|Division|  
|Gestionnaire de planification|Division|  
|Conseiller du service clientèle|Utilisateur|  
|Professionnel du marketing|Utilisateur|  
|Vendeur|Utilisateur|  
|Planificateur|Utilisateur|  
  
> [!NOTE]
>  Bien que les personnes puissent créer des processus de flux de processus métier, de workflow en temps réel ou d’action, elles doivent avoir les privilèges **Activer les flux des processus métier** ou **Activer les processus en temps réel** pour les activer.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Complément d’information sur les workflows et les actions  
 Les processus peuvent vérifier des conditions, appliquer une logique de branchement et effectuer des actions. Ils effectuent ces actions dans une série d’étapes. Le tableau suivant décrit les étapes disponibles dans les processus de workflow et d’action. Pour plus d’informations, consultez les rubriques associées à chaque type de processus.  
  
|Étape|Type de processus|Description|  
|----------|------------------|-----------------|  
|**Phase**|Workflow, Action|Les phases facilitent la lecture de la logique des workflows et expliquent cette logique. Toutefois, les phases n’affectent pas la logique ou le comportement des workflows. Si un processus comprend des phases, toutes les étapes du processus doivent être accompagnées d’une phase.|  
|**Condition de vérification**|Workflow, Action|Instruction « si-\<condition>-alors » logique.<br /><br /> Vous pouvez vérifier les valeurs de l’enregistrement sur lequel le workflow s’exécute, de tous les enregistrements liés à cet enregistrement par une relation N à 1 ou de tous les enregistrements créés par des étapes précédentes. En fonction de ces valeurs, vous pouvez définir des étapes supplémentaires quand la condition est `true`.|  
|**Branche conditionnelle**|Workflow, Action|Instruction « sinon-si-alors » logique. L’éditeur utilise le texte « Sinon, si \<condition>, alors : ».<br /><br /> Sélectionnez une condition de vérification que vous avez définie ; vous pouvez alors ajouter une branche conditionnelle pour définir des étapes supplémentaires qui sont exécutées si la condition retourne `false`.|  
|**Action par défaut**|Workflow, Action|Instruction « sinon » logique. L’éditeur utilise le texte « Sinon : ».<br /><br /> Sélectionnez une condition de vérification, une branche conditionnelle, une condition d’attente ou une branche d’attente parallèle que vous avez définie ; vous pouvez alors utiliser une action par défaut afin de définir des étapes pour tous les cas qui ne satisfont pas aux critères définis dans les éléments de condition ou de branche.|  
|**Condition d’attente**|Workflow en arrière-plan uniquement|Permet à un workflow d’arrière-plan de s’interrompre jusqu’à ce que les critères définis par la condition soient remplis. Le workflow redémarre automatiquement une fois que les critères de la condition d’attente sont remplis.|  
|**Branche d’attente parallèle**|Workflow en arrière-plan uniquement|Définit une condition d’attente alternative pour un workflow d’arrière-plan avec un ensemble correspondant d’étapes supplémentaires qui ne sont effectuées que si le critère initial est rempli. Vous pouvez utiliser des branches d’attente parallèles pour créer des limites de temps dans votre logique de workflow. Elles permettent d’éviter que le workflow attende indéfiniment que les critères définis dans une condition d’attente soient remplis.|  
|**Attribuer une valeur**|Action|Définit une valeur sur une variable ou un paramètre de sortie dans le processus.|  
|**Créer l’enregistrement**|Workflow, Action|Crée un enregistrement pour une entité et assigne des valeurs aux attributs.|  
|**Mettre à jour l’enregistrement**|Workflow, Action|Vous pouvez mettre à jour l’enregistrement sur lequel le workflow s’exécute, tous les enregistrements liés à cet enregistrement par une relation N à 1 ou tous les enregistrements créés par des étapes précédentes.|  
|**Attribuer l’enregistrement**|Workflow, Action|Vous attribuer l’enregistrement sur lequel le workflow s’exécute, tous les enregistrements liés à cet enregistrement par une relation N à 1 ou tous les enregistrements créés par des étapes précédentes.|  
|**Envoyer un courrier électronique**|Workflow, Action|Envoie un e-mail. Vous pouvez choisir de créer un e-mail ou d’utiliser un modèle d’e-mail configuré pour l’entité de l’enregistrement sur lequel le workflow est en cours d’exécution, pour toutes les entités qui ont une relation N à 1 avec l’entité ou pour l’entité de tous les enregistrements créés par des étapes précédentes.|  
|**Lancer un workflow enfant**|Workflow, Action|Démarre un processus de workflow qui a été configuré en tant que workflow enfant.|  
|**Modifier le statut**|Workflow, Action|Change le statut de l’enregistrement sur lequel le processus s’exécute, de tous les enregistrements liés à cet enregistrement par une relation N à 1 ou de tous les enregistrements créés par des étapes précédentes.|  
|**Arrêter le workflow**|Workflow, Action|Arrête l’action ou le workflow actuel. Vous pouvez définir un statut **Terminé** ou **Annulé** et spécifier un message de statut.|  
|**Étape personnalisée**|Workflow, Action|Fournit des extensions aux éléments logiques disponibles par défaut. Les étapes peuvent inclure des conditions, des actions, d’autres étapes ou une combinaison de ces éléments. Les développeurs peuvent créer des étapes de workflow personnalisées. Par défaut, aucune étape personnalisée n’est disponible.|

Pour plus d’informations destinées aux développeurs, consultez la rubrique du Guide du développeur [Automatiser vos processus métier dans Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/automate-business-processes-customer-engagement
).
  

