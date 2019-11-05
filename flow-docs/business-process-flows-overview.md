---
title: Vue d’ensemble des flux de processus d’entreprise | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545519"
---
# <a name="business-process-flows-overview"></a>Vue d’ensemble des flux de processus d’entreprise
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Vous pouvez vous assurer que les utilisateurs entrent les données de manière cohérente et suivent les mêmes étapes chaque fois qu’ils travaillent avec un client en créant un workflow de processus d’entreprise. Par exemple, vous souhaiterez peut-être créer un processus d’entreprise pour que tout le monde gère les demandes de service client de la même manière, ou pour demander à ce que les personnes reçoivent une approbation pour une facture avant de soumettre une commande. Les flux de processus d’entreprise utilisent la même technologie sous-jacente que les autres processus, mais les fonctionnalités qu’ils fournissent sont très différentes des autres fonctionnalités qui utilisent des processus. Pour savoir comment créer ou modifier un workflow de processus d’entreprise, consultez [créer un workflow de processus d’entreprise](create-business-process-flow.md).  
  
 [Regardez une brève vidéo (4:49) sur les flux de processus d’entreprise.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Pourquoi utiliser des flux de processus d’entreprise ?  
Les flux de processus d’entreprise fournissent un guide permettant aux utilisateurs d’effectuer leur travail. Ils fournissent une expérience utilisateur rationalisée qui amène les gens à parcourir les processus définis pour les interactions qui doivent être avancées jusqu’à une conclusion d’une sorte. Cette expérience utilisateur peut être personnalisée afin que les personnes avec des rôles de sécurité différents puissent avoir une expérience qui correspond au mieux au travail qu’ils font.  
  
 Utilisez les flux de processus d’entreprise pour définir un ensemble d’étapes que les utilisateurs doivent suivre pour les faire passer à un résultat souhaité. Ces étapes fournissent un indicateur visuel qui indique aux personnes où elles se trouvent dans le processus d’entreprise. Les flux de processus d’entreprise réduisent le besoin de formation, car les nouveaux utilisateurs n’ont pas à se concentrer sur l’entité qu’ils doivent utiliser. Ils peuvent laisser le processus les guider. Vous pouvez configurer des flux de processus d’entreprise pour prendre en charge des méthodologies de vente courantes qui peuvent aider vos groupes de ventes à obtenir de meilleurs résultats. Pour les groupes de services, les flux de processus d’entreprise peuvent aider le nouveau personnel à être plus rapide et à éviter des erreurs susceptibles d’entraîner des clients insatisfaisants.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>Quel est le rôle des flux de processus d’entreprise ?  
 Avec les flux de processus d’entreprise, vous définissez un *ensemble d'* étapes et d' *étapes* qui sont ensuite affichées dans un contrôle en haut du formulaire.  
  
 ![Processus d’entreprise avec étapes](media/business-process-stages.png "Processus d’entreprise avec étapes")  
  
 Chaque étape contient un groupe d’étapes. Chaque étape représente un champ dans lequel les données peuvent être entrées. Les utilisateurs avancent jusqu’à l’étape suivante en utilisant le bouton **Next stage** . Vous pouvez effectuer une étape requise pour que les utilisateurs puissent entrer des données pour le champ correspondant avant de passer à l’étape suivante. C’est communément appelé « étape-déclenchement ».  
  
 Les flux de processus d’entreprise s’affichent relativement simplement par rapport à d’autres types de processus, car ils ne fournissent pas de logique métier ou d’automatisation conditionnelle au-delà de la fourniture d’une expérience rationalisée pour l’entrée de données et le contrôle de l’entrée en étapes. Toutefois, lorsque vous les combinez avec d’autres processus et personnalisations, ils peuvent jouer un rôle important dans l’économie du temps, la réduction des coûts de formation et l’adoption de l’utilisateur.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Flux de processus d’entreprise intégré à d’autres personnalisations  
 Lorsque vous ou votre utilisateur entre des données à l’aide de flux de processus d’entreprise, les modifications de données sont également appliquées aux champs de formulaire afin que toute automatisation fournie par les règles d’entreprise ou les scripts de formulaire puisse être appliquée immédiatement. Vous pouvez ajouter des étapes qui définissent des valeurs pour les champs qui ne sont pas présents dans le formulaire. ces champs seront ajoutés au modèle d’objet `Xrm.Page` utilisé pour les scripts de formulaire. Tous les flux de travail initiés par des modifications apportées à des champs inclus dans un flux de processus d’entreprise sont appliqués lorsque les données du formulaire sont enregistrées. Si l’automatisation est appliquée par un workflow en temps réel, les modifications sont immédiatement visibles à l’utilisateur lorsque les données du formulaire sont actualisées après l’enregistrement de l’enregistrement.  
  
 Bien que le contrôle de workflow de processus d’entreprise dans le formulaire ne fournisse pas de programmabilité directe côté client, les modifications appliquées par les règles d’entreprise ou les scripts de formulaire sont automatiquement appliquées aux contrôles de workflow de processus d’entreprise. Si vous masquez un champ dans un formulaire, ce champ est également masqué dans le contrôle de workflow de processus d’entreprise. Si vous définissez une valeur à l’aide de règles d’entreprise ou de scripts de formulaire, cette valeur sera définie dans le processus d’entreprise.  
  
### <a name="concurrent-process-flows"></a>Flux de processus simultanés  
 Les flux de processus d’entreprise simultanés permettent aux personnalisations de configurer plusieurs processus d’entreprise et de les associer au même enregistrement de départ. Les utilisateurs peuvent basculer entre plusieurs processus d’entreprise exécutés simultanément et reprendre leur travail à l’étape où ils se trouvaient.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Flux de processus d’entreprise système  
 Les flux de processus d’entreprise suivants sont inclus. Pour comprendre le fonctionnement du flux de processus d’entreprise, passez en revue les flux de processus d’entreprise suivants :  
  
-   Prospect au processus de vente d’opportunités  
  
-   Processus de vente des opportunités  
  
-   Téléphone au processus de cas  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Plusieurs entités dans les flux de processus d’entreprise  
 Vous pouvez utiliser un workflow de processus d’entreprise pour une seule entité ou plusieurs entités. Par exemple, vous pouvez avoir un processus qui commence par une opportunité, puis continue jusqu’à un devis, une commande, puis une facture, avant de revenir à la fin de l’opportunité.  
  
 Vous pouvez concevoir des flux de processus d’entreprise qui associent les enregistrements pour cinq entités différentes dans un même processus afin que les utilisateurs de l’application puissent se concentrer sur le flux de leur processus plutôt que sur l’entité dans laquelle ils travaillent. Ils peuvent naviguer plus facilement entre les enregistrements d’entité associés.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Plusieurs flux de processus d’entreprise sont disponibles par entité  
 Tous les utilisateurs d’une organisation ne peuvent pas suivre le même processus et des conditions différentes peuvent nécessiter l’application d’un processus différent. Vous pouvez avoir jusqu’à 10 flux de processus d’entreprise actifs par entité pour fournir les processus appropriés pour différentes situations.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Contrôler le workflow de processus d’entreprise qui sera appliqué  
 Vous pouvez associer des flux de processus d’entreprise à des rôles de sécurité afin que seules les personnes disposant de ces rôles de sécurité puissent les voir ou les utiliser. Vous pouvez également définir l’ordre des flux de processus d’entreprise afin de pouvoir contrôler le flux de processus d’entreprise qui sera défini par défaut. Cela fonctionne de la même façon que plusieurs formulaires pour une entité sont définis.  
  
 Quand quelqu’un crée un nouvel enregistrement d’entité, la liste des définitions de processus d’entreprise actives est filtrée par le rôle de sécurité de l’utilisateur. La première définition de processus d’entreprise activée pour le rôle de sécurité de l’utilisateur, selon la liste des commandes de processus, est celle appliquée par défaut. Si plusieurs définitions de processus d’entreprise actives sont disponibles, les utilisateurs peuvent en charger un autre à partir de la boîte de dialogue changer de processus. Chaque fois que les processus sont basculés, le affiché passe en arrière-plan et est remplacé par celui qui est sélectionné, mais il conserve son état et peut être rétabli. Chaque enregistrement peut être associé à plusieurs instances de processus (chacune pour une définition de workflow de processus métier différente, jusqu’à 10). Lors du chargement du formulaire, un seul fluide de processus d’entreprise est restitué. Lorsqu’un utilisateur applique un processus différent, ce processus peut uniquement être chargé par défaut pour cet utilisateur particulier.  
  
 Pour s’assurer qu’un processus d’entreprise est chargé par défaut pour tous les utilisateurs (comportement équivalant à l’épinglage du processus), un script d’API client personnalisé (ressource Web) peut être ajouté sur le chargement de formulaire qui charge spécifiquement une instance de processus d’entreprise existante en fonction de l’entreprise ID de définition de processus. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considérations sur le déroulement des processus d’entreprise  
 Vous pouvez définir des flux de processus d’entreprise uniquement pour les entités qui les prennent en charge. Vous devez également connaître les limites du nombre de processus, d’étapes et d’étapes qui peuvent être ajoutés.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Flux de processus d’entreprise appelant un flux de travail  
 Vous pouvez appeler des workflows à la demande à partir d’un flux de processus d’entreprise. Vous pouvez configurer ce mode à partir du nouveau concepteur de flux de processus d’entreprise en faisant glisser un composant de workflow vers une étape de processus ou vers la section flux de travail globaux. Pour plus d’informations sur l’utilisation de workflows dans les flux de processus d’entreprise, consultez [blog : automatisation des flux de processus d’entreprise dans Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Lorsque vous incluez un flux de travail que vous souhaitez déclencher à la sortie de la phase d’une étape dans votre flux de processus d’entreprise, et que cette étape est la dernière étape du flux, le concepteur donne l’impression que le flux de travail sera déclenché une fois cette étape terminée. Toutefois, le flux de travail n’est pas déclenché, car une transition d’étape n’a pas lieu. Vous ne recevrez pas d’avertissement ou d’erreur vous empêchant d’inclure le flux de travail à l’étape. Lorsqu’un utilisateur interagit avec le flux de processus d’entreprise, la fin ou l’abandon du processus n’entraîne pas de transition d’étape, et par conséquent, le flux de travail n’est pas déclenché. Prenons les exemples suivants :  
  
-   Vous créez un flux de processus d’entreprise en deux étapes : S1 se connecte à S2, avec un flux de travail à l’étape S2 et définit le déclencheur sur **phase de sortie**.  
  
-   Vous créez un workflow de processus d’entreprise avec trois étapes, S1 se connecte à S2, puis S2 à S3. Vous incluez un flux de travail sur S2 et définissez le déclencheur sur **étape quitter**.  
  
 Le flux de travail n’est pas déclenché dans les deux cas. Pour contourner ce problème, vous pouvez ajouter un flux de travail global et ajouter le flux de travail que vous souhaitez déclencher à celui-ci afin que le flux de travail soit déclenché pour le processus d’entreprise plutôt qu’une étape du processus. Vous pouvez définir le déclencheur pour un flux de travail global pour traiter l’abandon ou le processus terminé pour que le flux de travail se déclenche lorsqu’un utilisateur abandonne ou termine le processus d’entreprise.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entités pouvant utiliser des flux de processus d’entreprise  
 Toutes les entités personnalisées peuvent utiliser des flux de processus d’entreprise. Les entités standard suivantes peuvent également utiliser des flux de processus d’entreprise :  
  
-   Compte  
-   RDV  
-   Campagnes  
-   Activité de la campagne  
-   Réponse de la campagne  
-   Ses  
-   Communiquer  
-   Messagerie  
-   Droit  
-   Télécopie  
-   Études  
-   Facture  
-   duisent  
-   Identificateur  
-   Liste marketing  
-   Occasion  
-   Appel téléphonique  
-   Production  
-   Élément de liste de prix  
-   Cours  
-   Rendez-vous périodique  
-   Documentation commerciale  
-   Activité sociale  
-   Ordre  
-   Utilisateur  
-   Tâche  
-   Travail  
  
 Pour activer une entité personnalisée pour les flux de processus d’entreprise, activez la case à cocher **flux de processus d’entreprise (champs créés)** dans la définition de l’entité. Notez que vous ne pouvez pas annuler cette action.  
  
> [!NOTE]
>  Si vous accédez à l’étape de déroulement du processus d’entreprise qui contient l’entité `Social Activity` et que vous choisissez le bouton **étape suivante** , l’option **créer** s’affiche. Lorsque vous choisissez **créer**, le formulaire **activité sociale** se charge. Toutefois, étant donné que `Social Activity` n’est pas valide pour `Create` à partir de l’interface utilisateur de l’application, vous ne pouvez pas enregistrer le formulaire et le message d’erreur suivant s’affiche : « erreur inattendue ».  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Nombre maximal de processus, étapes et étapes  
 Pour garantir des performances acceptables et la facilité d’utilisation de l’interface utilisateur, vous devez tenir compte de certaines limitations lorsque vous envisagez d’utiliser des flux de processus d’entreprise :  
  
-   Il ne peut pas y avoir plus de 10 processus de workflow de processus d’entreprise activés par entité.  
  
-   Chaque processus ne peut pas contenir plus de 30 étapes.  
  
-   Les processus à plusieurs entités ne peuvent pas contenir plus de cinq entités.
  
## <a name="business-process-flow-entity-customization-support"></a>Prise en charge de la personnalisation de l’entité de workflow de processus d’entreprise 

Introduite dans la mise à jour de Dynamics 365 (Online), version 9,0, les entités de workflow de processus d’entreprise peuvent apparaître dans le système afin que les données d’enregistrement d’entité puissent être mises à disposition dans des grilles, des affichages, des graphiques et des tableaux de bord. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Utiliser des enregistrements d’entité de workflow de processus d’entreprise avec des grilles, des affichages, des graphiques et des tableaux de bord

Avec les flux de processus d’entreprise disponibles en tant qu’entité, vous pouvez désormais utiliser des recherches avancées, des affichages, des graphiques et des tableaux de bord provenant de données de flux de processus d’entreprise pour une entité donnée, par exemple un prospect ou une opportunité. Les administrateurs système et les personnalisateurs peuvent créer des grilles, des affichages, des graphiques et des tableaux de bord de processus métier personnalisés similaires à ceux créés avec n’importe quelle autre entité.

Les flux de processus d’entreprise, tels que **prospect-processus de vente d’opportunités**, s’affichent sous la forme d’une entité personnalisable dans l’Explorateur de solutions.

![Explorateur de solutions avec une entité de processus de prospect-à-opportunité](media/bpf-lead-solution-explorer.png)

Pour accéder à une vue de workflow de processus d’entreprise par défaut, ouvrez l’Explorateur de solutions, développez **entités** > développez le processus de votre choix, par exemple **prospect au processus de vente d’opportunités**, sélectionnez **vues**, puis sélectionnez la vue de votre choix.

Plusieurs affichages par défaut sont disponibles et peuvent être consultés sous forme de graphique, tels que la vue **active des ventes d’opportunités** . 

![Vue des processus de vente des opportunités actives](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir avec l’entité de flux de processus d’entreprise à partir d’un Workflow
Vous pouvez également interagir avec les entités de flux de processus d’entreprise à partir d’un flux de travail. Par exemple, vous pouvez créer un flux de travail pour l’enregistrement d’entité de flux de processus d’entreprise afin de modifier l’étape active quand un champ de l’enregistrement d’entité opportunité est mis à jour. Pour plus d’informations sur la procédure à suivre, consultez [automatiser les étapes de flux de processus d’entreprise à l’aide de workflows](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitations relatives à l’utilisation d’entités de workflow de processus d’entreprise

- Actuellement, vous ne pouvez pas créer de formulaires personnalisés pour des entités basées sur un workflow de processus d’entreprise.
- Si une solution comprend une entité de workflow de processus d’entreprise, l’entité de workflow de processus d’entreprise doit être ajoutée manuellement à la solution avant son exportation. Dans le cas contraire, l’entité de workflow de processus d’entreprise ne sera pas incluse dans le package de solution. Plus d’informations : [Ajouter des composants de solution](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Étapes suivantes  
 [Regardez une brève vidéo (4:49) sur les flux de processus d’entreprise](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Créer un  de workflow de processus d’entreprise](create-business-process-flow.md)  
 [Améliorer les flux de processus d’entreprise avec branchement](enhance-business-process-flows-branching.md) <br/>
 [Livre blanc : processus d’activation avec Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
