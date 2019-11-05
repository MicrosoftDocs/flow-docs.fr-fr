---
title: Prise en main | Microsoft Docs
description: Méthodes rapides pour commencer à automatiser votre travail et votre vie avec Power automate
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 54d1478f34743b6059692b927da8baf2c49a35a7
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589852"
---
# <a name="get-started-with-power-automate"></a>Prise en main de Power automate

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Invité! Power automate est un service qui vous permet de créer des flux de travail automatisés entre vos applications et services favoris pour synchroniser des fichiers, obtenir des notifications, collecter des données et bien plus encore.

Les principaux types de flux sont les flux [automatisé](get-started-logic-flow.md), de [bouton](introduction-to-button-flows.md), [planifié](run-scheduled-tasks.md)et de [processus d’entreprise](business-process-flows-overview.md) .

## <a name="types-of-flows"></a>Types de flux

Power automate est l’un des trois piliers de Power Platform. Il fournit une plateforme de code faible pour le workflow et l’automatisation des processus. Voici une liste des différents types de flux :

| **Type de workflow**                                                                       | **Cas d’usage**                                                                                  | **Indicatif**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Flux automatisés](get-started-logic-flow.md)                 | Créer un Flow qui effectue automatiquement une ou plusieurs tâches après qu’il a été déclenché par un événement. | [Connecteurs](https://docs.microsoft.com/connectors/) pour les services Cloud ou locaux. |
| [Flux de bouton](introduction-to-button-flows.md)              | Exécuter des tâches répétitives à tout moment, à tout moment, via votre appareil mobile.                        |                                                                                        |
| [Flux planifiés](run-scheduled-tasks.md)                    | Créer un Flow qui effectue une ou plusieurs tâches selon une planification.             |                                                                                        |
| [Flux de processus d’entreprise](business-process-flows-overview.md) | Définissez un ensemble d’étapes que les utilisateurs doivent suivre pour les faire passer à un résultat souhaité.                 | Processus humains                                                                        |
| [Flux de l’interface utilisateur (version préliminaire)](ui-flows/overview.md)                                                | Enregistrez et automatisez la lecture des étapes manuelles sur les logiciels hérités.                    | Applications de bureau et Web qui n’ont pas d’API disponibles pour l’automatisation.    |

Vous pouvez créer et gérer tous les flux à partir de l’onglet **mes flux** dans Power automate.

Si vous êtes un utilisateur Dynamics 365, vous pouvez également vous familiariser avec les processus de Common Data Service classiques qui incluent, les [flux de travail](configure-workflow-steps.md), les [actions](create-actions.md), les [flux de tâches mobiles](create-mobile-task-flow.md)et les [boîtes de dialogue](use-cds-for-apps-dialogs.md).

La première étape consiste à s' [inscrire](sign-up-sign-in.md), ou, si vous disposez déjà d’un compte avec Power automate, à vous [connecter](https://flow.microsoft.com/signin) sur votre tablette, votre ordinateur de bureau ou même votre téléphone.

## <a name="check-out-the-start-page"></a>Consultez la page de démarrage ##

[Sur la page de démarrage](https://flow.microsoft.com) de Power automate, vous pouvez [explorer un ensemble varié de modèles](https://flow.microsoft.com/templates) et en savoir plus sur les principales fonctionnalités de Power automate. Vous pouvez obtenir un aperçu rapide de ce qui est possible et de la manière dont Power automate peut aider votre entreprise et votre vie.

Avec Power automate, vous pouvez :

- Recherchez facilement des modèles et des services.

    ![Page de démarrage du Flow 1](./media/getting-started/flowhome1.png)

- Choisissez parmi les services les plus populaires.

    ![Page de démarrage du Flow 2](./media/getting-started/flowhome2.png)

- Consultez une vue d’ensemble de chaque Flow.

    ![Page de démarrage du Flow 3](./media/getting-started/flowhome3.png)

Chaque modèle est conçu à des fins spécifiques. Par exemple, il existe des modèles pour vous envoyer un message texte lorsque votre patron vous envoie un courrier électronique, en ajoutant des clients Twitter à Dynamics 365 ou en sauvegardant vos fichiers. Ces modèles sont juste le bout de l’iceberg. Ils sont destinés à vous inspirer à créer des flux personnalisés pour les processus exacts dont vous avez besoin.

## <a name="create-your-first-flow"></a>Créer votre premier Flow ##

1. Sélectionnez un modèle qui vous convient. Un modèle simple est [**obtenir des rappels quotidiens par courrier électronique**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![modèle de rappel quotidien](./media/getting-started/template-details.png)

1. Sélectionnez **Continuer**.

    ![Créer une connexion](./media/getting-started/create-connection.png)

1. Entrez les adresses de messagerie auxquelles le rappel quotidien sera envoyé. Ensuite, entrez le message de rappel. Enfin, sélectionnez **créer un Flow**, puis vérifiez que votre flow s’exécute comme prévu.

    ![Fournir les informations d’identification pour la connexion](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Vous pouvez explorer les conditions qui déclenchent le Flow et l’action résultant de cet événement. Jouez avec les paramètres pour que le fluide soit le vôtre. Vous pouvez même ajouter ou supprimer des actions.

1. Sélectionnez **terminé**.

[Suivez ce didacticiel](get-started-logic-template.md) pour en savoir plus sur la création de flux à partir de modèles.

## <a name="get-creative"></a>Soyez créatif ##

Maintenant que vous avez créé votre premier flux à partir d’un modèle, utilisez l’une des plus de [150 sources de données](https://flow.microsoft.com/connectors/) que Power automate prend en charge pour [créer vos propres flux à partir de zéro](get-started-logic-flow.md).

![Création d’un fluide](./media/getting-started/build-a-flow.png)

Lorsque vous créez un flux à partir de zéro, vous contrôlez l’ensemble du flux de travail. Voici quelques idées pour vous aider à démarrer :

- [Flux avec de nombreuses étapes](multi-step-logic-flow.md).
- [Exécuter des tâches selon une planification](run-scheduled-tasks.md).
- [Créez un workflow d’approbation](wait-for-approvals.md).
- [Regardez un Flow en action](see-a-flow-run.md).
- [Publiez un modèle](publish-a-template.md).
- [Créer des flux à partir d’un modèle Microsoft teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Lire le code

Vous n’avez pas besoin d’être développeur pour créer des flux. Toutefois, Power automate fournit une fonctionnalité d' **Aperçu du code** qui permet à quiconque d’examiner de plus près le code généré pour l’ensemble des actions et des déclencheurs dans un flux. L’aperçu du code peut vous permettre de mieux comprendre les données utilisées par les déclencheurs et les actions. Suivez ces étapes pour lire le code généré pour vos flux à partir du concepteur Power automate : 

1. Sélectionnez l’élément de menu **...** dans le coin supérieur droit d’une **action** ou d’un **déclencheur**. 
1. Sélectionnez **lire le code**.

    ![Lire le code](media/getting-started/peek-code.png)

1. Notez la représentation JSON complète des actions et des déclencheurs. Cela comprend toutes les entrées, telles que le texte que vous entrez directement, et les expressions utilisées. Vous pouvez sélectionner des expressions ici, puis les coller dans l’éditeur d’expressions de **contenu dynamique** . Cela peut également vous donner un moyen de vérifier que les données attendues sont présentes dans le Workflow.

    ![Lire le code](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Trouvez facilement vos flux

Lorsque vos jus créatifs commencent à *circuler*, vous pouvez créer de nombreux flux. Ne vous inquiétez pas, la recherche de vos flux est simple. Utilisez la zone de recherche de l’écran **mes flux**, **flux d’équipe**, **connexions**ou **solutions** pour afficher uniquement les flux qui correspondent aux termes de recherche que vous entrez.

![Filtrer ou Rechercher des flux](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Le filtre de recherche recherche uniquement les flux qui ont été chargés dans la page. Si vous ne trouvez pas votre Flow, essayez de sélectionner **charger plus** en bas de la page.

## <a name="get-notifications-when-somethings-wrong"></a>Recevoir des notifications en cas de problème

Utilisez Power automate notification Center (situé en haut à droite du concepteur) pour voir rapidement la liste des flux ayant échoué récemment. Le centre de notifications affiche un nombre qui indique le nombre de flux ayant échoué récemment.

Dans le centre de notifications, vous pouvez accéder à la page **activité** de Power automate pour voir tous vos flux récemment exécutés, les notifications envoyées ou les échecs.

![Centre de notifications](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Utiliser l’application mobile ##

Téléchargez l’application Mobile Power automate pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows). Avec cette application, vous pouvez [surveiller l’activité de flux](mobile-monitor-activity.md), [gérer vos flux](mobile-manage-flows.md) et [créer des flux à partir de modèles](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Nous sommes là pour vous aider ##

Nous sommes ravis de voir ce que vous faites avec Power automate et nous souhaitons vous assurer d’avoir une expérience de qualité. Veillez à consulter nos didacticiels de [formation guidée](https://flow.microsoft.com/guided-learning/) et [Rejoignez notre communauté](https://go.microsoft.com/fwlink/?LinkID=787467) pour poser des questions et partager vos idées. Si vous rencontrez des problèmes, [Contactez le support technique](https://go.microsoft.com/fwlink/?LinkID=787479) .
