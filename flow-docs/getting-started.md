---
title: Prise en main| Microsoft Docs
description: Méthodes rapides pour démarrer l’automatisation de votre travail et de vos activités personnelles avec Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f667401774e49505009cd416f6975ff38683a5c7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035248"
---
# <a name="get-started-with-microsoft-flow"></a>Prise en main de Microsoft Flow #

<iframe width="560" height="315" src="https://www.youtube.com/embed/iMteXfAvDSE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Bienvenue ! Microsoft Flow est un service qui vous aide à créer des workflows automatisés entre vos applications et services favoris pour synchroniser des fichiers, obtenir des notifications, collecter des données, etc.

Les principaux types de flux sont les flux [automatisés](get-started-logic-flow.md), de [bouton](introduction-to-button-flows.md), [planifiés](run-scheduled-tasks.md) et de [processus métier](business-process-flows-overview.md).

Si vous êtes personnalisateur Dynamics 365 Customer Engagement, vous êtes peut-être aussi familiarisé avec les processus Common Data Service classiques qui incluent les [workflows](configure-workflow-steps.md), les [actions](create-actions.md), les [flux de tâches mobiles](create-mobile-task-flow.md) et les [dialogues](use-cds-for-apps-dialogs.md).

La première étape consiste à vous [inscrire](sign-up-sign-in.md), ou, si vous avez déjà un compte Microsoft Flow, [connectez-vous](https://flow.microsoft.com/signin) sur votre tablette, votre ordinateur de bureau ou même votre téléphone.

## <a name="check-out-the-start-page"></a>Consulter la page de démarrage ##

[Sur la page de démarrage](https://flow.microsoft.com) de Microsoft Flow, vous pouvez [explorer un ensemble varié de modèles](https://flow.microsoft.com/templates) et en apprendre plus sur les principales fonctionnalités de Microsoft Flow. Vous pouvez avoir une idée de ce qui est possible et de la manière dont Microsoft Flow peut vous aider dans votre entreprise et votre vie de tous les jours.

Avec Microsoft Flow, vous pouvez :

- Rechercher facilement des modèles et des services.

    ![Page de démarrage 1 Flow](./media/getting-started/flowhome1.png)

- Choisir parmi les services les plus populaires.

    ![Page de démarrage 2 Flow](./media/getting-started/flowhome2.png)

- Consulter une vue d’ensemble de chaque flux.

    ![Page de démarrage 3 Flow](./media/getting-started/flowhome3.png)

Chaque modèle est conçu dans un but spécifique. Par exemple, il existe des modèles pour envoyer un message texte lorsque votre patron vous envoie un courrier électronique, ajouter des prospects Twitter à Dynamics 365 ou sauvegarder vos fichiers. Ces modèles ne constituent qu’une infime partie des possibilités. Ils sont destinés à vous encourager à créer des flux qui sont personnalisés en fonction des processus exacts dont vous avez besoin.

## <a name="create-your-first-flow"></a>Créer votre premier flux ##

1. Sélectionnez un modèle utile pour vous. Un modèle simple est [**Recevoir des rappels quotidiens par e-mail**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/) :

    ![modèle de rappel quotidien](./media/getting-started/template-details.png)

1. Sélectionnez **Continuer**.

    ![Créer la connexion](./media/getting-started/create-connection.png)

1. Entrez les adresses de messagerie qui recevront le rappel quotidien. Saisissez ensuite le message de rappel. Enfin, sélectionnez **Créer un flux**, puis vérifiez que votre flux fonctionne comme prévu.

    ![Fournir les informations d’identification pour la connexion](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Vous pouvez maintenant parcourir les conditions qui déclenchent le flux et l’action résultant de cet événement. Testez les paramètres pour personnaliser le flux. Vous pouvez même ajouter ou supprimer des actions.

1. Sélectionnez **Terminé**.

[Suivez ce didacticiel](get-started-logic-template.md) pour en savoir plus sur la création de flux à partir de modèles.

## <a name="get-creative"></a>Soyez créatif ##

Maintenant que vous avez créé votre premier flux à partir d’un modèle, utilisez l’une des [150 sources de données](https://flow.microsoft.com/connectors/) et plus prises en charge par Microsoft Flow pour [créer vos propres flux à partir de zéro](get-started-logic-flow.md).

![Création d’un flux](./media/getting-started/build-a-flow.png)

Lorsque vous créez un flux à partir de zéro, vous contrôlez l’intégralité du flux de travail. Voici quelques idées pour vous aider à vous lancer :

- [Flux avec de nombreuses étapes](multi-step-logic-flow.md).
- [Exécution de tâches selon une planification](run-scheduled-tasks.md).
- [Créer un flux d’approbation](wait-for-approvals.md).
- [Voir un flux en action](see-a-flow-run.md).
- [Publier un modèle](publish-a-template.md).
- [Créer des flux à partir d’un modèle Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Lire le code

Vous n’avez pas besoin d’être développeur pour créer des flux, toutefois, Microsoft Flow fournit-il un **lire le code** fonctionnalité qui permet à quiconque entrent en examiner plus en détail le code est généré pour toutes les actions et déclencheurs dans un flux. Lire le code pourrait vous donner une compréhension plus claire des données qui sont utilisées par les déclencheurs et actions. Suivez ces étapes pour lire le code est généré pour vos flux à partir du concepteur Microsoft Flow : 

1. Sélectionnez le **...**  élément de menu situé en haut à droite de n’importe quel **action** ou **déclencheur**. 
1. Sélectionnez **lire le code**.

    ![Lire le code](media/getting-started/peek-code.png)

1. Notez que la représentation JSON complet des actions et déclencheurs. Cela inclut toutes les entrées, telles que le texte que vous entrez directement et les expressions utilisées. Vous pouvez sélectionner ici des expressions et les coller ensuite dans le **Dynamic Content** Éditeur d’expression. Cela peut également vous donner une façon de vérifier les données que vous attendez sont présentes dans le flux.

    ![Lire le code](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Trouver vos flux facilement

Lorsque votre creative jus de démarrage *circulant*, vous pouvez créer plusieurs flux. Ne vous inquiétez pas, la recherche de vos flux est facile : simplement utiliser la zone de recherche sur le **mes flux**, **flux d’équipes**, **connexions**, ou **Solutions** écran pour afficher circule uniquement qui correspondent aux termes de recherche que vous entrez.

![Filtrer ou rechercher des flux](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Le filtre de recherche recherche uniquement des flux qui ont été chargés dans la page. Si vous ne trouvez pas votre flux, essayez de sélectionner **charger plus** en bas de la page.

## <a name="get-notifications-when-somethings-wrong"></a>Obtenir des notifications lorsque quelque chose ne va pas

Utiliser le centre de notification Microsoft Flow (situé en haut à droite du concepteur) pour rapidement voir une liste de flux ont échoué récemment. Le centre de notification s’affiche un nombre qui indique le nombre de flux ayant échoué récemment.

À partir du centre de notification, vous pouvez accéder à la **activité** page de Microsoft Flow pour voir tous vos flux ayant récemment exécuté, des notifications ou a échoué.

![Centre de notification](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Utiliser l’application mobile ##

Téléchargez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows). Avec cette application, vous pouvez [surveiller l’activité du flux](mobile-monitor-activity.md), [gérer votre flux](mobile-manage-flows.md) et [créer des flux à partir de modèles](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Nous sommes là pour vous aider ##

Nous avons hâte de voir ce que vous ferez avec Microsoft Flow et nous voulons nous assurer que vous bénéficiez d’une formidable expérience. N’oubliez pas de consulter nos didacticiels de [formation interactive](https://flow.microsoft.com/guided-learning/) et [rejoignez notre communauté](http://go.microsoft.com/fwlink/?LinkID=787467) pour poser des questions et partager vos idées. [Contactez le support technique](http://go.microsoft.com/fwlink/?LinkID=787479) si vous rencontrez des problèmes.
