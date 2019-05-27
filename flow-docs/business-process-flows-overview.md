---
title: Vue d’ensemble des flux de processus métier | Microsoft Docs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1e23a3ddfd4302c4a5429029ea4fb47f0ab9808
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464986"
---
# <a name="business-process-flows-overview"></a>Vue d’ensemble des flux de processus métier

Pour que les utilisateurs entrent des données de manière cohérente et suivent les mêmes étapes chaque fois qu’ils collaborent avec un client, vous pouvez créer un flux de processus métier. Par exemple, vous pouvez créer un flux de processus métier pour que tous les utilisateurs gèrent les demandes de service client de la même manière ou pour qu’ils obtiennent l’approbation d’une facture avant d’envoyer une commande. Les flux de processus métier utilisent la même technologie sous-jacente que les autres processus, mais les fonctionnalités qu’ils fournissent sont très différentes de celles qui utilisent des processus. Pour savoir comment créer ou modifier un flux de processus métier, consultez [Créer un flux de processus métier](create-business-process-flow.md).  
  
 [Regardez une courte vidéo (4:49) sur les flux de processus métier.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Pourquoi utiliser des flux de processus métier ?  
Les flux de processus métier guident les utilisateurs dans la réalisation de leur travail. Ils fournissent une expérience utilisateur rationalisée qui guide les utilisateurs à travers les processus que leur organisation a définis pour des interactions devant aboutir à une conclusion donnée. Cette expérience utilisateur peut être adaptée en fonction du rôle de sécurité associé à l’utilisateur et du travail qu’il effectue.  
  
 Utilisez des flux de processus métier pour définir un ensemble d’étapes que les utilisateurs doivent suivre pour aboutir à un résultat souhaité. Ces étapes indiquent visuellement aux utilisateurs où ils en sont dans le processus métier. Les flux de processus métier réduisent les besoins en formation, car les nouveaux utilisateurs n’ont pas besoin de se concentrer sur l’entité qu’ils doivent utiliser. Ils peuvent laisser le processus les guider. Vous pouvez configurer des flux de processus métier pour prendre en charge des méthodologies de ventes courantes qui peuvent aider vos groupes de ventes à obtenir de meilleurs résultats. Pour les groupes de service, les flux de processus métier peuvent aider les nouvelles équipes à être opérationnelles plus rapidement et à éviter les erreurs qui pourraient engendrer des insatisfactions chez les clients.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>À quoi les flux de processus métier peuvent-ils servir ?  
 Avec des flux de processus métier, vous définissez un ensemble de *phases* et *d’étapes* qui sont ensuite affichées dans un contrôle en haut du formulaire.  
  
 ![Phases d’un processus métier](media/business-process-stages.png "Phases d’un processus métier")  
  
 Chaque phase contient un groupe d’étapes. Chaque étape représente un champ dans lequel des données peuvent être entrées. Les utilisateurs passent à la phase suivante à l’aide du bouton **Phase suivante**. Vous pouvez rendre une étape obligatoire afin que les utilisateurs doivent entrer des données pour le champ correspondant avant de passer à la phase suivante. Cette technique est communément appelée « processus de phases (stage-gating) ».  
  
 Les flux de processus métier sont relativement simples par rapport aux autres types de processus, car ils ne fournissent pas de logique métier conditionnelle ou d’automatisation au-delà de l’expérience simplifiée de la saisie de données et du contrôle de l’entrée dans les phases. Toutefois, quand vous les combinez avec d’autres processus et personnalisations, ils peuvent jouer un rôle important pour faire économiser du temps aux utilisateurs, ce qui réduit les coûts de formation et accroît l’adoption par ces derniers.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flux de processus métier intégrés à d’autres personnalisations  
 Quand votre utilisateur ou vous-même entrez des données à l’aide de flux de processus métier, les modifications de données sont également appliquées aux champs de formulaire afin que toute automatisation fournie par des règles métier ou des scripts de formulaire soit applicable immédiatement. Vous pouvez ajouter des étapes qui définissent des valeurs pour des champs qui sont absents dans le formulaire ; ces champs sont alors ajoutés au modèle objet `Xrm.Page` utilisé pour les scripts de formulaire. Tous les workflows qui sont lancés par des modifications apportées à des champs inclus dans un flux de processus métier sont appliqués quand les données du formulaire sont enregistrées. Si l’automatisation est appliquée par un workflow en temps réel, l’utilisateur voit immédiatement les modifications quand il actualise les données du formulaire après avoir enregistré l’enregistrement.  
  
 Bien que le contrôle du flux de processus métier dans le formulaire ne fournisse pas de programmabilité côté client directe, les modifications appliquées par les règles métier ou les scripts de formulaire sont automatiquement appliquées aux contrôles de flux de processus métier. Si vous masquez un champ dans un formulaire, ce champ est également masqué dans le contrôle du flux de processus métier. Si vous définissez une valeur à l’aide de règles métier ou de scripts de formulaire, cette valeur est définie dans le flux de processus métier.  
  
### <a name="concurrent-process-flows"></a>Flux de processus simultanés  
 Les flux de processus métier simultanés permettent aux personnalisateurs de configurer plusieurs processus métier et de les associer au même enregistrement de départ. Les utilisateurs peuvent basculer entre plusieurs processus métier qui s’exécutent simultanément et reprendre leur travail à la phase du processus à laquelle ils se trouvaient.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flux de processus métier système  
 Les flux de processus métier ci-après sont inclus. Pour comprendre comment fonctionnent les flux de processus métier, passez en revue ces flux de processus métier système :  
  
-   Processus de vente prospect-opportunité  
  
-   Processus de vente Opportunité  
  
-   Processus téléphone-incident  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Entités multiples dans les flux de processus métier  
 Vous pouvez utiliser un flux de processus métier pour une seule entité ou englober plusieurs entités. Par exemple, vous pouvez avoir un processus qui commence par une opportunité, puis passe à un devis, à une commande, à une facture, puis, pour finir, à la fermeture de l’opportunité.  
  
 Vous pouvez concevoir des flux de processus métier qui lient les enregistrements relatifs à au maximum cinq différentes entités dans un même processus afin que les utilisateurs de l’application puissent se concentrer sur le flux de leur processus plutôt que sur l’entité dans laquelle ils travaillent. Ils peuvent évoluer plus facilement entre les enregistrements de l’entité associée.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Plusieurs flux de processus métier sont disponibles par entité  
 Tous les utilisateurs dans une organisation ne suivent pas forcément le même processus, et différentes conditions peuvent nécessiter l’application d’un autre processus. Vous pouvez avoir jusqu’à 10 flux de processus métier actifs par entité pour fournir des processus appropriés en fonction de la situation.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Contrôler le flux de processus métier à appliquer  
 Vous pouvez associer des flux de processus métier à des rôles de sécurité afin que seuls les utilisateurs dotés de ces rôles de sécurité puissent les voir ou s’en servir. Vous pouvez également définir l’ordre des flux de processus métier afin de contrôler le flux de processus métier à définir par défaut. Cette approche fonctionne de la même façon que la définition de plusieurs formulaires pour une entité.  
  
 Quand un utilisateur crée un enregistrement d’entité, la liste des définitions de processus métier actif disponibles est filtrée par le rôle de sécurité de l’utilisateur. La première définition de processus métier actif disponible pour le rôle de sécurité de l’utilisateur en fonction de la liste de l’ordre des processus est celle qui est appliquée par défaut. Si plusieurs définitions de processus métier actif sont disponibles, les utilisateurs peuvent en charger une autre à partir de la boîte de dialogue Changer de processus. À chaque changement de processus, celui affiché passe à l’arrière-plan et est remplacé par celui sélectionné, mais il conserve son état et peut être rétabli. Chaque enregistrement peut se voir associer plusieurs instances de processus (chacune pour une définition de flux de processus métier différente, dans la limite de 10). Au chargement du formulaire, un seul flux de processus métier est affiché. Quand un utilisateur applique un processus différent, ce processus ne peut se charger par défaut que pour cet utilisateur.  
  
 Pour qu’un processus métier soit chargé par défaut pour tous les utilisateurs (ce qui revient à « épingler » le processus), vous pouvez ajouter, au chargement du formulaire, un script d’API cliente personnalisé (ressource web) qui charge une instance de processus métier existante en fonction de l’ID de la définition de processus métier. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considérations relatives aux flux de processus métier  
 Vous pouvez définir des flux de processus métier uniquement pour les entités qui les prennent en charge. Notez également que vous ne pouvez pas ajouter un nombre illimité de processus, de phases et d’étapes.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flux de processus métier qui appellent un workflow  
 Vous pouvez appeler des workflows à la demande depuis un flux de processus métier. Pour ce faire, à partir du nouveau concepteur de flux de processus métier, vous pouvez faire glisser un composant de workflow vers une phase du processus ou vers la section Workflow global. Pour plus d’informations sur l’utilisation de workflows dans les flux de processus métier, consultez le [billet de blog relatif à l’automatisation des flux de processus métier dans Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Quand vous incluez un workflow que vous souhaitez déclencher à la sortie d’une phase de votre flux de processus métier et que cette phase est la dernière phase du flux, le concepteur donne l’impression que le workflow sera déclenché quand cette phase sera terminée. Toutefois, le workflow ne sera pas déclenché, car aucune transition de phase n’a lieu. Vous ne recevez pas d’avertissement ou d’erreur vous empêchant d’inclure le workflow sur la phase. Quand un utilisateur interagit avec le flux de processus métier, le fait de terminer ou d’abandonner le processus n’entraîne pas une transition de phase et le workflow n’est donc pas déclenché. Prenons les exemples suivants :  
  
-   Vous créez un flux de processus métier avec deux phases, S1 se connecte à S2, avec un workflow sur la phase S2, et vous définissez le déclencheur sur **Sortie de phase**.  
  
-   Vous créez un flux de processus métier avec trois phases, S1 se connecte à S2, puis S2 se branche sur S3. Vous incluez un workflow sur S2 et définissez le déclencheur sur **Sortie de phase**.  
  
 Le workflow ne se déclenche dans aucun des deux cas. Pour contourner ce problème, vous pouvez ajouter un workflow global et ajouter à ce dernier le workflow que vous souhaitez déclencher afin que celui-ci soit déclenché pour le processus métier, plutôt que pour une phase du processus. Vous pouvez définir le déclencheur pour un workflow global sur Processus abandonné ou Processus terminé afin que le workflow soit déclenché quand un utilisateur abandonne ou termine le processus métier.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entités pouvant utiliser des flux de processus métier  
 Toutes les entités personnalisées peuvent utiliser des flux de processus métier. Les entités standard suivantes peuvent également utiliser des flux de processus métier :  
  
-   Compte  
-   Rendez-vous  
-   Campagne  
-   Activité de campagne  
-   Réponse de campagne  
-   Concurrent  
-   Contact  
-   E-mail  
-   Droit  
-   Télécopie  
-   Incident  
-   Facture  
-   Prospect  
-   Lettre  
-   Liste marketing  
-   Opportunité  
-   Appel téléphonique  
-   Produit  
-   Élément tarifaire  
-   Devis  
-   Rendez-vous périodique  
-   Documentation commerciale  
-   Activité sociale  
-   Commande  
-   Utilisateur  
-   Tâche  
-   Équipe  
  
 Pour activer une entité personnalisée pour les flux de processus métier, cochez la case **Flux des processus d’entreprise (des champs vont être créés)** dans la définition de l’entité. Notez que vous ne pouvez pas annuler cette action.  
  
> [!NOTE]
>  Si vous accédez à la phase du flux de processus métier dans laquelle se trouve l’entité `Social Activity` et que vous choisissez le bouton **Phase suivante**, vous voyez l’option **Créer**. Quand vous choisissez **Créer**, le formulaire **Activité sociale** est chargé. Toutefois, `Social Activity` n’étant pas valide pour `Create` à partir de l’interface utilisateur de l’application, vous ne pouvez pas enregistrer le formulaire, et le message d’erreur suivant s’affiche : « Erreur inattendue ».  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Nombre maximal de processus, de phases et d’étapes  
 Pour garantir des performances acceptables et la convivialité de l’interface utilisateur, certaines limitations s’appliquent, dont vous devez être conscient quand vous envisagez d’utiliser des flux de processus métier :  
  
-   Il ne peut pas y avoir plus de 10 processus de flux de processus métier activés par entité.  
  
-   Chaque processus peut contenir 30 phases au maximum.  
  
-   Les processus à plusieurs entités peuvent contenir au maximum cinq entités.
  
## <a name="business-process-flow-entity-customization-support"></a>Prise en charge de la personnalisation des entités de flux de processus métier 

À compter de la mise à jour version 9.0 de Dynamics 365 (en ligne), les entités de flux de processus métier peuvent apparaître dans le système ; ainsi, les données d’enregistrement des entités peuvent être rendues disponibles dans les grilles, vues, graphiques et tableaux de bord. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Utiliser des enregistrements d’entité de flux de processus métier avec des grilles, vues, graphiques et tableaux de bord

Les flux de processus métier étant disponibles en tant qu’entité, vous pouvez maintenant utiliser des vues, des graphiques, des tableaux de bord et des recherches avancés à partir des données de flux de processus métier pour une entité spécifique, telle qu’un prospect ou une opportunité. Les personnalisateurs et les administrateurs système peuvent créer des tableaux de bord, des vues, des graphiques et des grilles de flux de processus métier personnalisés similaires à ceux créés avec toute autre entité.

Les flux de processus métier, tels que **Processus de vente prospect-opportunité**, apparaissent sous la forme d’une entité personnalisable dans l’Explorateur de solutions.

![Explorateur de solutions avec l’entité Processus de vente prospect-opportunité](media/bpf-lead-solution-explorer.png)

Pour accéder à une vue de flux de processus métier par défaut, ouvrez l’Explorateur de solutions, développez **Entités**, développez le processus de votre choix, tel que **Processus de vente prospect-opportunité**, sélectionnez **Vues**, puis sélectionnez la vue souhaitée.

Vous pouvez afficher sous forme de graphique plusieurs vues par défaut, telles que la vue **Processus de vente : Opportunités actives**. 

![Vue Processus de vente : Opportunités actives](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir avec l’entité de flux de processus métier à partir d’un workflow
Vous pouvez également interagir avec les entités de flux de processus métier à partir d’un workflow. Par exemple, vous pouvez créer un workflow pour l’enregistrement de l’entité Flux des processus d’entreprise pour changer la phase active quand un champ de l’enregistrement de l’entité Opportunité est mis à jour. Pour plus d’informations sur la procédure à suivre, consultez le [billet de blog consacré à l’automatisation des phases des flux de processus métier à l’aide de workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitations de l’utilisation des entités de flux de processus métier

- Vous ne pouvez pas créer de formulaires personnalisés pour les entités basées sur un flux de processus métier.
- Si une solution inclut une entité de flux de processus métier, vous devez ajouter celle-ci manuellement à la solution avant de l’exporter. Sinon, l’entité de flux de processus métier n’est pas incluse dans le package de solution. Plus d’informations : [Ajouter des composants de solution](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Étapes suivantes  
 [Regarder une courte vidéo (4:49) sur les flux de processus métier](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Créer un flux de processus métier](create-business-process-flow.md)   
 [Améliorer les flux de processus métier avec le branchement](enhance-business-process-flows-branching.md) <br/>
 [Livre blanc : Optimisation des processus avec Dynamics 365](http://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
