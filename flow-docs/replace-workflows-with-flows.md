---
title: Remplacer les flux de travail de Common Data Service classiques par des Microsoft Flow | Microsoft Docs
description: Décrit les fonctionnalités de Microsoft Flow et les modèles recommandés pour utiliser Flow au lieu d’un flux de travail classique.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548528"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Remplacer les flux de travail de Common Data Service classiques par des flux
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cette rubrique compare les fonctionnalités de Microsoft Flow avec le flux de travail classique.

Microsoft Flow présente des avantages significatifs par rapport au modèle de flux de travail classique. vous devez envisager d’utiliser Microsoft Flow pour automatiser vos processus au lieu du flux de travail classique. 

Créez des flux au lieu de flux de travail de Common Data Service classiques pour générer de nouveaux processus d’automatisation. En outre, vous devez passer en revue vos processus de flux de travail classiques existants et envisager de les remplacer par des flux.

## <a name="feature-capability-comparison"></a>Comparaison des fonctionnalités des fonctionnalités

Ce tableau résume une comparaison entre les fonctionnalités de flux de travail Microsoft Flow et Classic. 

*Nous ajoutons en permanence de nouvelles fonctionnalités à Microsoft Flow de façon à ce qu’elles soient au pair et même mieux que les fonctionnalités de flux de travail classiques. Nous allons mettre à jour les informations contenues dans ce tableau en tant que Microsoft Flow gagne des fonctionnalités ; Vérifiez régulièrement ! Pour plus d’informations sur les fonctionnalités de flux futures qui vous aideront à remplacer le flux de travail classique avec Flow, consultez [nouveautés et prévisions pour Microsoft Flow](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) dans les notes de publication d’avril 2019.*

<table>
<tr>
<th colspan="2">Faculté</th>
<th>Microsoft Flow</th>
<th>Flux de travail classique</th>
</tr>
<tr>
<td rowspan="5">Pièces</td>
<td>Branchement conditionnel</td>
<td>Oui</td>
<td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Bouclage
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Conditions d’attente sur les champs
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Branche parallèle
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Connecteurs prêts à l’emploi vers des systèmes externes (déclencher et effectuer des actions dans des services externes)
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Composition
                    
                </td>
                <td>
                    
   Contenu dynamique
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Accès à la pré-image des données d’événement
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter des workflows enfants
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter des actions Common Data Service (y compris personnalisé)
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter des activités de flux de travail personnalisées
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Grouper les étapes à exécuter dans une transaction
                    
                </td>
                <td>
                    
   Oui (ensembles de modifications)
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Flux de travail d’approbation
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Production
                    
                </td>
                <td>
                    
   Déclencher des modifications de champ
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Déclencher de manière conditionnelle sur des valeurs de champ (par exemple, à une certaine date dans un champ de date)
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Déclencher sur plusieurs événements d’entité Common Data Service
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter à la demande
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Étendues exécuter en tant que    <br/>
   (par exemple, organisation, Division, utilisateur)
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter selon une planification
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter de façon synchrone (en temps réel)
                    
                </td>
                <td>
                    
   º
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Historique
                    
                </td>
                <td>
                    
   Audit
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Exécuter Analytics
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Création et portabilité
                    
                </td>
                <td>
                    
   Prise en charge des solutions
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Concepteur moderne
                    
                </td>
                <td>
                    
   Oui
                    
                </td>
                <td>
                    
   º
                    
                </td>
            </tr>
            <tr>
<td>Création assistée de l’intelligence artificielle</td>
<td>Oui</td>
<td>º</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Exemple de scénario : remplacer un flux de travail par un flux

Imaginez un scénario de vente dans lequel vous avez rassemblé un devis pour un client et que vous devez maintenant demander l’approbation de votre équipe de gestion avant de l’envoyer au client. Avec les flux de travail classiques, cela n’aurait pas été facile, et la plupart des solutions à cette fin nécessitent que le développeur écrive des activités de flux de travail personnalisées pour récupérer les éléments de ligne de devis.

Avec les flux, il est plus facile de générer, comme illustré dans la procédure pas à pas, une partie des Microsoft Flow fonctionnalités de prise en charge du scénario. Cela comprend les éléments suivants :

-   Création d’un Flow qui s’exécute à la demande

-   Obtention d’une liste d’enregistrements liés à une entité Common Data Service

-   Bouclage sur une liste d’enregistrements

-   Envoi de demandes d’approbation

Pour permettre au commercial de déclencher la demande d’approbation à la demande :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/) et créez un fluide dans une solution. Informations supplémentaires : [créer un fluide dans une solution](create-flow-solution.md). 

1. Dans la liste des déclencheurs, sélectionnez **Common Data Service (environnement actuel) : lorsqu’un enregistrement est sélectionné** et sélectionnez des **guillemets** comme entité. Ce déclencheur permet à un workflow d’être exécuté à la demande sur un enregistrement ou une liste d’enregistrements.

1. Une fois le déclencheur configuré, ajoutez des actions à exécuter dans notre Flow. Cela fournira à l’approbateur les détails du résumé dont il a besoin pour identifier les éléments et les valeurs entre guillemets. Commencez par ajouter l’action **Common Data Service (environnement actuel) – liste des enregistrements** . Étant donné que nous souhaitons obtenir des éléments de ligne individuels à partir d’un devis, définissez l’entité sur des **lignes de devis**. Pour vous assurer que nous n’indiquons que les éléments de ligne de devis qui appartiennent au devis pour lequel le Flow a été déclenché, nous allons spécifier un critère de filtre de style OData. Dans le champ **requête de filtre** , tapez *\_EQ quoteid_value* , puis sélectionnez *quot* dans la liste des valeurs dynamiques qui s’affichent.

    ![Définir votre Flow](media/define-flow-1.png "Définir votre Flow")

1. Au fur et à mesure que nous souhaitons synthétiser les éléments de ligne de devis pour l’approbation, ajoutez l’action **initialiser la variable** . Définissez le champ **nom** sur *quoted Line Summary* et le **type** sur String (dans la liste déroulante), et laissez le champ de **valeur** vide.

1. Ajoutez l’action ajouter **à la variable de chaîne** , puis sélectionnez la variable de résumé de la *ligne de citation* que nous avons créée précédemment. Dans le champ **valeur** , sélectionnez *quantité, nom, prix unitaire, montant étendu et montant manuel* dans la liste des valeurs dynamiques. Le concepteur de Microsoft Flow indique que ces valeurs proviennent d’une liste d’éléments de ligne de devis et ajoute cette action dans une boucle **apply to each** pour s’assurer que les informations de chaque élément de ligne sont ajoutées à ce résumé.

    ![Définir votre Flow](media/define-flow-2.png "Définir votre Flow")

1. Pour demander l’approbation sur le résumé de devis que nous avons créé, ajoutez l’action **approbation – démarrer et attendre une approbation** . Sélectionnez un type d’approbation (par exemple, approuver/rejeter – tout d’abord pour répondre), donnez un **titre** à la demande d’approbation (par exemple, le nom du devis pour lequel l’approbation est demandée, choisi dans la liste des valeurs dynamiques), entrez l’adresse de messagerie du personne qui doit examiner et approuver le devis dans le champ **affecté à** . Dans le champ détails, ajoutez la variable de résumé de la *ligne de guillemets* , ainsi que toutes les autres informations qui peuvent être pertinentes à l’aide du sélecteur de valeurs dynamiques (par exemple, montant total).

1. Pour déterminer ce qui se produit une fois qu’une approbation est acceptée ou rejetée, ajoutez l’action **condition** . Sélectionnez *résultat* dans la liste des valeurs dynamiques du premier champ de la condition, *contient* dans la liste déroulante du deuxième champ, puis entrez *Accept* dans le troisième champ de la condition. Enfin, ajoutez des actions en fonction du résultat de l’approbation (par exemple, envoyez un e-mail de notification).

    ![Définir votre Flow](media/define-flow-3.png "Définir votre Flow")

Nous avons maintenant la structure d’approbation créée afin que l’approbateur dispose de toutes les informations nécessaires pour prendre une décision sur les étapes suivantes. Voici l’exemple complet de workflow à la demande pour demander une approbation :

![Structure du fluide d’approbation](media/approval-flow-structure.png "Structure du fluide d’approbation")

Lorsque vous exécutez ce processus en fonction de votre devis, il résume les Articles de la citation pour ce devis et envoie une demande d’approbation que l’approbateur peut traiter à partir de Microsoft Flow ou l’e-mail actionnable qu’il reçoit. Voici un exemple d’affichage :

![Flow en action](media/flow-in-action.png "Flow en action")

## <a name="recommended-patterns"></a>Modèles recommandés


-   **Flux de travail avec une logique conditionnelle else-if complexe**  
    
    Au lieu d’utiliser des conditions, nous vous recommandons d’utiliser l' [action Switch](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) à la place.

-   **Flux de travail qui s’exécutent à partir du plug-in/code**  
    
    Nous vous recommandons de redéfinir le Flow pour démarrer avec les déclencheurs.

    -   Utilisez Common Data Service déclencheurs pour exécuter des flux en fonction des événements qu’il contient.

    -   Pour exécuter des flux basés sur des événements dans un service externe, tirez parti de plus de 260 connecteurs prêts à l’emploi.

    -   Pour les scénarios où un connecteur dont vous avez besoin n’est pas prêt à l’emploi, créez facilement votre propre connecteur personnalisé [apprendre à créer des connecteurs personnalisés](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Enfin, s’il existe des scénarios dans lesquels vous ne pouvez pas déclencher votre Flow à l’aide d’Common Data Service Connector, l’un des connecteurs prêts à l’emploi ou créer un connecteur personnalisé, tirez parti du [déclencheur lors de la réception d’une requête http](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) pour appeler le Flow

-   **Flux de travail qui s’exécutent de manière récursive**  
    
    Utilisez plutôt l' [opération Do-Until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) ou [appliquer à chaque](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) boucle dans les flux

-   **Workflows qui ont besoin d’une liste d’enregistrements**  
    
    Utilisez l’action **répertorier les enregistrements** . Lorsque vous utilisez cette action, définissez les critères de filtrage des enregistrements à l’aide de la syntaxe OData pour optimiser l’action en réduisant le nombre d’enregistrements que vous souhaitez récupérer.

-   **Flux de travail qui s’exécutent selon une planification**  
    
    Utilisez le déclencheur de **récurrence** pour exécuter la logique métier à intervalles réguliers.

-   **Les workflows pour lesquels des exécutions ont été gérées pour s’assurer que les activités ont été exécutées dans une transaction unique**  
    
    [Utilisez l' [action d’ensemble de modifications](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) pour vous assurer que toutes les actions qu’il contient sont effectuées sous la forme d’une seule unité atomique dans laquelle toutes les opérations réussissent ou échouent en tant que groupe. Si l’une des actions d’un ensemble de modifications échoue, les modifications apportées par les opérations terminées sont annulées.

-   **Surveiller les exécutions de workflow pour les défaillances**  
    
    Dans Microsoft Flow, utilisez le **paramètre exécuter après** sur une action pour la configurer de façon à ce qu’elle s’exécute lorsque l’action précédente échoue. Par exemple, envoyez une notification Microsoft Flow mobile lorsque l’action **mettre à jour un enregistrement** échoue ou expire.

## <a name="faqs"></a>FAQ


-   **J’ai une licence Dynamics 365. Puis-je utiliser Microsoft Flow ?**

    Chaque utilisateur Dynamics 365 est autorisé à utiliser Microsoft Flow. Passez en revue les informations de licence : <https://flow.microsoft.com/pricing/>

-   **Quelle est la fréquence de déclenchement de mes flux ?**

    -   Les flux Dynamics 365 (ou Common Data Service) s’exécutent presque en temps réel après le déclencheur, car ils utilisent des webhooks (aucune interrogation requise)

    -   Comme avec l’accès direct à l’API, il existe des limitations/limites dans le système, entièrement documentées ici : <https://docs.microsoft.com/flow/limits-and-config>

    -   Plus précisément, il existe une limite de 100 000 actions par 5 minutes, par Flow, et une boucle unique dans un Flow ne peut pas traiter plus de 100 000 éléments à la fois

    -   Maximum de 6 Go de débit par 5 minutes

-   **Pendant combien de temps un seul Workflow peut-il s’exécuter ?**  
    
    Une exécution de workflow unique expire après 30 jours.

-   **Comment faire déplacer mes flux entre les environnements ?**  
    
    Tout comme les flux de travail classiques, vous pouvez créer des flux dans des solutions pour prendre en charge le cycle de vie complet des applications pour les processus.

-   **Les dépendances de Microsoft Flow sont-elles suivies dans Common Data Service ?**  
    
    Comme pour les autres composants d’une solution, toutes les dépendances des flux dans les solutions sont suivies dans Common Data Service.

-   **Qu’en est-il des flux de travail synchrones ?** 
 
    Vous devez réévaluer la nécessité de flux de travail synchrones pour déterminer si l’objectif ou des parties du flux de travail peuvent être générés à l’aide d’un flux. Nous voyons, en particulier, à partir de nos données de télémétrie que les flux de travail synchrones sont un contributeur significatif à l’expérience des performances médiocres de l’utilisateur final. Pour de nombreuses utilisations, bien qu’il soit préférable de fractionner ces actions comme asynchrones afin que l’utilisateur puisse poursuivre son activité pendant que Microsoft Flow continue à garantir l’achèvement de l’action.

-   **À l’aide de Microsoft Flow, mes données seront-elles conservées dans la région (c’est-à-dire la même région que mon environnement Dynamics 365 ou Common Data Service) ?**  
    
    Oui, Microsoft Flow utilise toujours la même région que Common Data Service.

-   **Dois-je apporter des modifications au proxy/pare-feu ?**  
    
    Reportez-vous à la [référence de configuration d’adresse IP](limits-and-config.md#ip-address-configuration) pour déterminer si vous devez apporter des modifications au proxy ou au pare-feu.
