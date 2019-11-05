---
title: Notes de publication | Microsoft Docs
description: Problèmes courants et nouveautés pour les versions de Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548871"
---
# <a name="release-notes"></a>Notes de publication
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Principales questions
1. Mon Flow a échoué. Comment faire le résoudre ?
   
   1. Identifiez l’échec. Commencez par accéder à l’icône notifications en haut du portail Web, ou en sélectionnant l’onglet **activité** dans l’application mobile. Vous devez voir votre fluide ici et vous pouvez le sélectionner.
   2. Vous voyez maintenant les détails du fluide. Recherchez l’étape à l’aide de l’icône d’exclamation rouge et vous devriez voir le message d’erreur de votre Flow.
   3. En fonction du message d’erreur, vous devez être en mesure de **modifier** le Flow et de le corriger. [En savoir plus sur la résolution des échecs courants de workflow](fix-flow-failures.md).
2. Comment faire utiliser une condition avancée ou une expression ?
   
   * En savoir plus sur l' [Ajout de conditions](add-condition.md).
   * Si vous souhaitez plusieurs cas dans un fluide, sélectionnez **Ajouter une condition** à l’intérieur d’une condition existante.
   * Créez une expression avancée en référençant [une fonction dans Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Comment les licences fonctionnent-elles avec Office 365 ?
   
   * Si vous êtes un utilisateur Office 365, vous bénéficiez d’un accès complet par le biais du plan Microsoft Flow pour Office 365. Pour plus d’informations, consultez les [plans de tarification pour Microsoft Flow](https://flow.microsoft.com/pricing/) .
   * Si vous êtes administrateur, consultez les informations sur [les licences pour Microsoft Flow](organization-q-and-a.md), notamment avec Office 365.

## <a name="known-issues"></a>Problèmes connus
1. Les listes SharePoint sur mes sites et qui ne sont pas de type *liste personnalisée* ne sont pas prises en charge. Pour contourner ce problème, créez une liste personnalisée sur un site SharePoint standard.
2. Les déclencheurs de fichier ne sont pas activés pour les fichiers ajoutés dans des dossiers imbriqués à l’intérieur du dossier que vous sélectionnez.

## <a name="whats-new"></a>Nouveautés

> [!IMPORTANT]
>
> **Annonce des notes de publication**
>
> Vous vous demandez les fonctionnalités à venir et récemment publiées dans Microsoft Flow ?
>[Consultez les notes de publication d’octobre 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Nous avons capturé tous les détails, de bout en bout, de haut en bas, que vous pouvez utiliser pour la planification. Pour plus d’informations, passez en revue [chaque version hebdomadaire](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) avec les fonctionnalités et les améliorations qu’elle contient.
>
> Les notes de publication antérieures à la version 2018 d’octobre seront conservées ici pour référence ultérieure, mais toutes les nouvelles versions ne seront incluses que dans les emplacements ci-dessus et non dans cette page.

### <a name="release-2018-09-24"></a>Version 2018-09-24

- **Accès administrateur à aide et support** : Ouvrez les tickets de support pour Microsoft Flow dans le centre d’administration plateforme Power et fournissez des détails supplémentaires sur l’échec de votre flux de travail.
- **Nouvelle conception de la communauté de fluides** : trouver ce dont vous avez besoin plus facile dans la communauté de distribution.
- **Améliorations apportées au connecteur Microsoft teams** : nouveaux déclencheurs pour Microsoft Teams, qui vous permettent d’exécuter un Flow quand de nouveaux messages sont contenus dans un canal.
- **Autres actions SharePoint** : il existe de nouvelles actions pour déplacer des fichiers et plus encore dans le connecteur SharePoint.
- **Nouveaux rapports d’analyse d’administration** -l’environnement et l’analyse à l’ensemble du locataire ont été ajoutés au centre d’administration de la plateforme d’applications d’entreprise.
- **Intégration de Power Query** : une expérience de Power Query est générée, qui permet aux décideurs de mettre en forme des hybrides de données à partir de SQL Server.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) sur cette version.

### <a name="release-2018-08-31"></a>Version 2018-08-31

- **Testez votre Flow en utilisant des exemples** de données d’utilisation de données à partir de connecteurs pour tester votre Flow au fur et à mesure que vous le générez dans le concepteur de Microsoft Flow. Lorsque vous testez votre Flow avec des exemples de données, vous confirmez que le flow s’exécutera comme prévu lors de son déploiement en production.
- **Cinq nouveaux connecteurs** : nous avons ajouté quatre nouveaux connecteurs de gestion : powerapps pour les décideurs d’applications, les plateforme Power pour les administrateurs, les powerapps pour les administrateurs, les Microsoft Flow pour les administrateurs et Microsoft School Data Sync.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/test-data-management-connectors/) sur cette version.

### <a name="release-2018-08-24"></a>Version 2018-08-24

- **Nouveaux modèles de synchronisation de calendrier** -nouveaux modèles de calendrier qui copient des événements entre Google Calendar et Office 365 ou Outlook.com.
- **Prise en charge de plusieurs valeurs pour SharePoint** : en lecture et en écriture pour les champs à valeurs multiples dans SharePoint qui sont des types choix, personne ou recherche.
- **Envoyer des approbations pour le compte d’autres utilisateurs de votre organisation** -envoyer des approbations pour le compte d’autres utilisateurs de votre organisation, par exemple, la personne qui a chargé le fichier dans la liste SharePoint, au lieu de la personne qui a créé le Flow.
- **Autres types d’entrée de bouton** : les boutons ont deux nouveaux types d’entrée : nombre et oui/non.
- **Mises à jour de connecteur** : un nouveau connecteur NetDocuments, des améliorations apportées aux connecteurs Azure, et bien plus encore.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/button-types-more/) sur cette version.

### <a name="release-2018-08-02"></a>Version 2018-08-02

Le programme Microsoft Flow Preview est la façon d’accéder en avant-première aux fonctionnalités et mises à jour à venir pour Microsoft Flow. Pour obtenir un accès en avant-première aux fonctionnalités les plus récentes, il vous suffit de créer, puis d’utiliser, un environnement dans la zone d’aperçu.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/flow-preview-program/) sur cette version.

### <a name="release-2018-07-23"></a>Version 2018-07-23

- **Générer et exécuter des flux à partir d’Excel** : avec le bouton nouveau **flux** (accessible à partir de l’onglet **données** du ruban), vous pouvez créer et déclencher des automations à partir de Microsoft Flow sur les données de votre table dans Excel. Automatisez le traitement des données ou la copie/importation de données.
- **Créer un** workflow de processus d’entreprise : un workflow de processus d’entreprise est un nouveau type de fluide interactif et interactif basé sur le Common Data Service. Utilisez ces nouveaux flux pour définir un ensemble d’étapes et de procédures à suivre pour les personnes. Ils peuvent avancer ou reculer en fonction des besoins.
- **Créer un Flow pour Microsoft to-do dans Outlook Web App** : si une personne n’est \@mentionnée dans Outlook Web App, elle voit un raccourci pour créer un fluide. Ce Flow crée automatiquement des tâches pour la \@personne mentionnée dans Microsoft, en fonction du contenu de l’e-mail.
- **Prise en charge de l’affichage SharePoint** : le connecteur SharePoint prend désormais en charge la sélection d’une vue SharePoint spécifique sur les déclencheurs et les actions. Cela permet de filtrer les colonnes uniquement sur les champs de la vue sélectionnée.
- **Quatre nouveaux connecteurs** : ajout d’Azure IOT central : solution SaaS (Software-as-a-service) IOT hautement évolutive-enquête 123, LMS365 et ProjectWise Design Integration.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) sur cette version.

### <a name="release-2018-06-29"></a>Version 2018-06-29

- **Demande de workflow de déconnexion intégré à SharePoint** : lorsque vous sélectionnez un fichier ou un élément dans SharePoint, vous voyez une nouvelle **demande de workflow de déconnexion** . Ce fluide ne nécessite aucune configuration ou configuration et envoie une demande d’approbation en un seul clic.
- **Deux nouveaux connecteurs** : ajout de Cloud Connect Studio et PoliteMail.
- **Améliorations de l’historique et des pages de création** : nous actualisons la liste de l’historique des exécutions en incluant les durées d’exécution exactes et la page créer en y ajoutant une nouvelle vidéo de procédure pas à pas.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) sur cette version.

### <a name="release-2018-06-08"></a>Version 2018-06-08

- Les **applets** de commande PowerShell, à la fois les réformateurs et les administrateurs de locataires, peuvent désormais utiliser PowerShell pour gérer leurs flux par programme.
- **Améliorations apportées au bot de flux teams** : le robot Flow de Microsoft teams peut exécuter des boutons de flux et décrire vos flux.
- **Trois nouveaux connecteurs** -ajout de la prise en charge de Marketo, ElasticOCR et DynamicSignal. 
- Informations de **partage supplémentaires** : ajout d’informations supplémentaires lorsque vous partagez, ou exécutez des flux partagés, afin de connaître exactement les autorisations que les autres personnes recevront.
- **Ajustement automatique des URL SharePoint** : lorsque vous copiez et collez une URL SharePoint dans le navigateur, elle peut contenir du texte supplémentaire au-delà du site, ce texte est automatiquement supprimé afin que vous puissiez vous connecter au site uniquement.
- **Documentation sur les demandes RGPD** : nous avons créé un guide complet et un ensemble d’outils permettant aux organisations d’entreprise de gérer les demandes de droits de l’objet de données.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) sur cette version.

### <a name="release-2018-05-21"></a>Version 2018-05-21

- **Flux « appartenant à » les listes et les bibliothèques SharePoint** : les flux qui fonctionnent avec les listes et les bibliothèques SharePoint peuvent être partagés avec ces listes ou bibliothèques. Ainsi, au lieu d’être partagé avec des individus ou des groupes, ils sont partagés avec tous ceux qui ont accès à la liste. À mesure que des utilisateurs sont ajoutés ou supprimés de la liste ou de la bibliothèque, leur appartenance change automatiquement en conséquence.
- **Analyse des détails** de l’erreur : nouveau rapport incorporé qui fournit des informations sur toutes les erreurs qui se produisent à l’intérieur d’un Workflow.
- **Partager des flux avec les groupes office 365** : vous pouvez faire d’un groupe Office 365 moderne le propriétaire d’un flux, et partager des flux de bouton avec les groupes Office 365 pour que toute personne du groupe puisse exécuter le flux.
- **Améliorations du connecteur SharePoint** : il existe deux nouvelles fonctionnalités de connecteur SharePoint : déclencher des flux lorsque des éléments ou des fichiers sont supprimés et appeler un point de terminaison http pris en charge par l’API REST SharePoint.
- **Deux nouveaux connecteurs** -ajout de la prise en charge de Azure Data Factory et MailParser

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) sur cette version.

### <a name="release-2018-05-01"></a>Version 2018-05-01

- **Texte enrichi dans les messages d’approbation** : utilisez la démarque pour mettre en forme les détails d’approbation que vous envoyez.
- **Boutons avec plusieurs entrées de sélection** -créer des boutons de déroulement qui utilisent une liste de sélection multiple pour collecter plusieurs valeurs à la fois.
- **Travaillez avec des flux plus larges** : l’application mobile Microsoft Flow prend désormais en charge la vue paysage et le concepteur Web a une barre de défilement horizontale.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) sur cette version.

### <a name="release-2018-04-12"></a>Version 2018-04-12

- **Renvoyer des données à powerapps à partir d’un** flux : générer des flux qui peuvent être appelés à partir d’une application générée avec powerapps, et renvoyer des données à l’application. Utilisez le concepteur de Flow glisser-déplacer visuel pour créer la logique dont vous avez besoin pour vos applications. 
- **Ajouter plusieurs enregistrements aux entrées de tableau** -ajout d’un générateur de listes dans Microsoft Flow qui peut être utilisé pour ajouter plusieurs pièces jointes à un message électronique, par exemple.
- **Flux de test avec les données d’exécution précédentes** -ajout d’un nouveau bouton de flux de test au concepteur qui vous permet de tester votre flux avec des données de déclencheur provenant d’exécutions de flux précédentes.
- **Nouveaux champs de flux de travail ()** : vous pouvez maintenant accéder au nom d’environnement et au nom d’affichage de flux avec l’expression de flux de travail ().

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/return-data-to-powerapps/) sur cette version.

### <a name="release-2018-04-04"></a>Version 2018-04-04

- Les **approbations sur le Common Data Service** -les approbations modernes reposent sur la version la plus récente du Common Data Service. Cela signifie que vous pouvez générer des flux qui lisent l’état des approbations que vous envoyez ou recevez avec le connecteur Common Data Service.
- **Rechercher les erreurs dans appliquer à chaque** -accède directement aux erreurs dans les boucles de la vue d’exécution du workflow, même si la boucle contient des centaines d’éléments.
- **Réassigner des approbations** : vous pouvez affecter une approbation que vous recevez à une autre personne de votre organisation pour lui déléguer l’approbation. 
- **Listes de salles** -le connecteur Office 365 Outlook a ajouté des actions pour accéder aux données de l’espace dans votre organisation.
- **Afficher les détails des boutons de Flow** -quand vous exécutez un Flow qui a été partagé avec vous, vous pouvez maintenant voir toutes les actions utilisées par le Flow.
- **Région du Royaume-Uni** -les environnements peuvent maintenant être créés pour stocker leurs données au Royaume-Uni.
- **Deux nouveaux connecteurs** -ajout de la prise en charge de l’administrateur AtBot et du Hub de contenu marketing.
- **Nouvelle page d’accueil** de la documentation : mise à jour de la page d’accueil de la documentation pour que le contenu soit regroupé par qui vous êtes : débutant, utilisateur intermédiaire ou expert. 

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) sur cette version.

### <a name="release-2018-03-13"></a>Version 2018-03-13

- **Historique des approbations** : consultez toutes les demandes d’approbation que vous avez envoyées, y compris les réponses, les commentaires qui ont été envoyés et l’heure exacte à laquelle ils se sont produits.
- **Quatre nouveaux connecteurs** : ajout d’Excel Online (Business), Excel Online (OneDrive), Azure SQL Data Warehouse et Pitney Bowes Tax Calculator.
- **Info-bulles de contenu dynamique** -pointez sur le contenu dynamique pour voir où il provient de l’intérieur des actions, et prévisualisez les expressions sans ouvrir l’éditeur d’expressions complet.
- **Contrôle d’accès concurrentiel** -activer le contrôle d’accès concurrentiel pour qu’un fluide donné n’ait qu’une seule exécution à la fois.
- Nouvelle **tentative exponentielle** -nouveau type de stratégie de nouvelle tentative qui espace les nouvelles tentatives de manière exponentielle au fil du temps.
- Mise en conformité de l' **accessibilité** : publication de nouveaux documents de conformité qui décrivent comment Microsoft Flow répondre aux normes d’accessibilité.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/approval-history-accessibility/) sur cette version.

### <a name="release-2018-02-09"></a>Version 2018-02-09

- **Haute disponibilité** de la passerelle : créez des clusters hautement disponibles de passerelles de données locales pour maintenir les connexions en cas de défaillance d’un seul ordinateur.
- Amélioration de la méthode **apply to each** -avec Flow plan 1 ou Flow plan 2, jusqu’à 100 000 éléments en une seule exécution et 50 actions en parallèle dans les boucles apply to each. 

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sur cette version.

### <a name="release-2018-01-29"></a>Version 2018-01-29

- **Flux au sein des équipes Microsoft** -à partir d’équipes, vous pouvez créer et gérer des flux, passer en revue vos approbations reçues et envoyées, et lancer des flux directement dans l’application de bureau équipes ou sur Teams.Microsoft.com- [en savoir plus ici](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notifications de modification partagées** : chaque fois qu’un workflow que vous possédez est modifié par un collègue, vous recevez une notification par courrier électronique vous informant de la personne qui a modifié le Flow.
- **Nouvelles expressions** -ajout de deux nouveaux jeux d’expressions : un pour analyser les URL et un autre pour travailler avec des objets JSON.
- **Trois nouveaux connecteurs** : cette semaine, il existe deux nouveaux connecteurs Plumsail : Plumsail SP et Plumsail Forms, ainsi qu’un nouveau connecteur à kintone.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sur cette version.

### <a name="release-2018-01-17"></a>Version 2018-01-17

- **Informations sur le profil office 365** -nous avons ajouté de nouvelles actions au connecteur Office 365 Users qui fonctionnent avec les profils utilisateur et les photos.
- Ajouter **aux variables de chaîne** : vous pouvez ajouter à des chaînes à l’intérieur de boucles pour créer des tables ou d’autres listes.
- **Connecteur Infobip** -Infobip est un service qui permet la communication de qualité professionnelle, y compris les appels vocaux et le déclenchement sur les SMS entrants.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/o365-profile-infobip/) sur cette version.

### <a name="release-2017-12-20"></a>Version 2017-12-20

Microsoft Flow Analytics est désormais disponible dans toutes les régions de Microsoft Flow, ce qui signifie que vous pouvez obtenir plus d’informations sur l’intégrité des flux exécutés dans votre environnement.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sur cette version.


### <a name="release-2017-12-14"></a>Version 2017-12-14

- **Améliorations du connecteur Outlook** : vous pouvez enregistrer un e-mail en tant que fichier « . eml », répondre automatiquement aux invitations du calendrier et déclencher des flux lorsque vous êtes mentionné dans un thread de courrier électronique.
- **Améliorations des connexions** : Microsoft Flow mémorise vos connexions récemment utilisées et vous montre tous les connecteurs nouvellement ajoutés.
- **Cinq nouveaux connecteurs** : ajout de Azure Container instances, Azure Kusto, des tâches, des documents Microsoft et Plumsail.
- **Améliorations http** : l’action http prend désormais en charge l’encodage mémorisé en bloc.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/outlook-connector-more/) sur cette version.

### <a name="release-2017-12-05"></a>Version 2017-12-05

Le panneau de lancement Microsoft Flow est désormais disponible dans toutes les régions. Ce panneau vous permet d’ajouter des valeurs à un Flow lorsque vous l’exécutez à l’intérieur de votre liste ou bibliothèque de documents SharePoint.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sur cette version.


### <a name="release-2017-11-28"></a>Version 2017-11-28

- **Métadonnées managées** : lit et écrit des données dans des colonnes SharePoint qui utilisent les métadonnées managées (également appelé. Type de taxonomie).
- Ajouter **aux tableaux** -ajoutez des éléments à la fin des tableaux à l’aide d’une nouvelle action de variable ajouter à un tableau.
- **Tago** : nouveau connecteur à Tago, qui fournit une connexion facile des appareils électroniques avec des données externes pour prendre des décisions plus intelligentes à l’aide de l’analyse contextuelle.
- **iPhone x** : nouvelle version de l’application Microsoft Flow qui utilise le plein écran sur l’iPhone X et qui a une amélioration de la vitesse pour les chargements d’images.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/managed-metadata-tago/) sur cette version.

### <a name="release-2017-11-09"></a>Version 2017-11-09

- **Intégration de Onedrive entreprise** : il existe [maintenant un bouton flux à l’intérieur de onedrive entreprise](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) qui peut créer ou déclencher des flux sur des fichiers ou dossiers sélectionnés.
- **Déclencheurs du planificateur** -démarrer les flux lors de la création d’une tâche, quand une tâche vous est assignée ou lorsque l’une d’elles est terminée.
- **Pièces jointes SharePoint** -travailler avec des pièces jointes sur des éléments de liste SharePoint : liste, téléchargement, ajout ou suppression de pièces jointes.
- **Connecteur de gestion de flux** : créez des flux qui automatisent la gestion d’autres flux dans votre environnement (par exemple, ajout automatique d’autorisations aux flux).
- **Quatre nouveaux connecteurs** : ajout d’Azure Service vision personnalisée, D &, Optimizer, Enadoc et derdak SIGNL4. 
- **Autres actions de connecteur** : exécuter des requêtes SQL, obtenir des déclencheurs de messagerie plus rapides, utiliser n’importe quelle méthode avec HTTP avec Azure ad, et bien plus encore.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sur cette version.

### <a name="release-2017-11-02"></a>Version 2017-11-02

- **Journalisation des audits** -les événements d’audit Microsoft Flow sont désormais disponibles dans Office 365 Centre de sécurité et de conformité pour tous les locataires.
- **Correctifs du widget de Flow** : résolution d’un problème dans l’application mobile Flow qui empêchait le chargement de boutons dans le widget.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/security-and-compliance-center/) sur cette version.

### <a name="release-2017-10-19"></a>Version 2017-10-19

- **Imbriquée appliquer à chaque** : vous pouvez ajouter appliquer à chaque action, filtrer et sélectionner dans autre appliquer à chaque action de conteneur.
- **Actions de date** et d’heure : nouvelles actions pour l’obtention des heures locales, l’ajout, la soustraction ou la mise en forme des heures.
- **Quatre nouveaux connecteurs** : ajout de Content moderator, docparser, Microsoft Kaizala et Pitney Bowes Data validation.
- Amélioration de l' **expérience de connexion** : notifications dans le portail Microsoft Flow lorsqu’une connexion est interrompue et que les détails de connexion sont plus riches.
- **Collection on-the-Go** : nouvelle collection de modèles pour [les travailleurs en déplacement](https://flow.microsoft.com/collections/onthego/).
- **Entrées du bouton adresse de messagerie** : collecter les adresses de messagerie des utilisateurs lorsqu’ils exécutent des boutons.
- **Entrées de bouton fichier** : accédez aux fichiers téléchargés, tels que les photos, à partir des utilisateurs lorsqu’ils exécutent des boutons.
- **Première exécution et connexion automatique** -amélioration des expériences de la première exécution sur l’application mobile, y compris la connexion automatique.
- **Déclencheurs Microsoft Forms plus rapides** : les formulaires déclenchent des flux beaucoup plus rapidement qu’auparavant (précédemment une fois par heure).
- **Entrées de bouton entre les sessions** : les boutons déclenchés sur votre téléphone mobile mémorisent les entrées précédentes.
- **Flux d’activité mobile** : flux d’activité amélioré pour inclure des résumés d’exécution plus détaillés et des détails de résolution des problèmes.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/nested-apply-to-each/) sur cette version.

### <a name="release-2017-10-03"></a>Version 2017-10-03

- **Tous doivent approuver** : exiger une demande d’approbation envoyée à plusieurs personnes pour que tout le monde ait reçu la demande d’approbation.
- **Nouvelles actions Onedrive entreprise** : générez des fichiers PDF pour les fichiers stockés sur OneDrive entreprise et quatre autres nouvelles actions.
- **Connecteur Apache Impala** : Apache Impala (incubation) est la base de données analytique Native Open source pour Apache Hadoop.
- **Ajouter des descriptions de flux** -donnez vos descriptions de flux. ainsi, lorsque vous les partagez, vos collègues peuvent voir un résumé du flux.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sur cette version.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Version 2017-09-25-mise à jour Q3 pour Microsoft Flow

- **Intégration de SharePoint plus profonde dans la première version** : il existe une nouvelle version « intégrée » pour les flux de révision et un volet de flux pour la collecte des entrées lorsque vous exécutez un flux pour les locataires de la première version.
- **Dynamics 365 Apps** : Flow est désormais intégré à l’interface utilisateur pour les applications Dynamics 365, telles que Dynamics 365 sales et Dynamics 365 Customer service.
- Centre de gestion de la **confidentialité Microsoft** -Microsoft Flow est listé dans le centre de gestion de la confidentialité Microsoft, qui présente des certifications telles que HIPAA, ISO et SOC.
- **Analyse de l’utilisation** : chaque Flow dispose d’un tableau de bord Power bi incorporé avec l’analyse d’utilisation de base.
- **Journalisation d’audit dans la première version** : tous les événements de gestion de flow sont consignés dans le centre de sécurité et conformité Office 365 pour les locataires de première version.
- **Six nouveaux connecteurs** -ajout de LinkedIn, Office 365 groupes, Skype entreprise, Adobe Sign, Bizzy et Azure log Analytics de la collecte de données.
- **Déclencheurs SQL** : exécute des flux lorsqu’une nouvelle ligne est ajoutée ou lorsqu’une ligne est mise à jour dans une table SQL.
- **Connecteurs personnalisés local** : les connecteurs personnalisés peuvent désormais utiliser la passerelle de données locale pour se connecter à des points de terminaison internes sur votre réseau.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/q3-2017-update/) sur cette version.

### <a name="release-2017-09-21"></a>Version 2017-09-21

- **Télécharger l’historique de Flow** -Téléchargez l’historique des exécutions d’un workflow en tant que fichier CSV pour l’ouvrir dans Excel.
- **Récurrence avancée** : créez des planifications récurrentes pour déclencher vos flux, par exemple, uniquement pour les jours de la semaine.
- **IntelliSense** : lorsque vous tapez des expressions, IntelliSense fournit des suggestions pour les paramètres.
- **Quatre nouveaux connecteurs** : connecteurs ajoutés pour Azure ad les services http, Amazon Redshift, Azure Event Grid Publish et FlowForma.
- **Liens de partage** -nouvelle action pour générer des liens partageables pour les fichiers OneDrive ou les objets BLOB de stockage Azure.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/download-history-recurrence/) sur cette version.


### <a name="release-2017-08-25"></a>Version 2017-08-25
* Les **Propriétés de document et plus encore pour SharePoint** - [lire et définir les propriétés d’une bibliothèque de documents SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/), et utiliser des champs supplémentaires tels que des liens vers l’élément SharePoint.
* **Collections de flows** : les collections de flows sont un ensemble de collections de modèles organisées par rôle ou par vertical.
* Repartage de **bouton** : lorsque vous partagez des boutons avec vos collègues, ils peuvent les repartager avec d’autres personnes.
* **Collecter des listes à partir de boutons** : définissez les listes déroulantes des options que les utilisateurs peuvent sélectionner lorsqu’ils appuient sur le bouton.
* **Sept nouveaux connecteurs** : AWeber, Azure log Analytics, Azure tables, DocFusion365, Azure Event Grid, Azure Event hubs et StaffHub. 
* Les **améliorations apportées à la marge et à MySQL** créent ou joignent des canaux en marge, et vous pouvez écrire dans des bases de données MySQL.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sur cette version.

### <a name="release-2017-08-02"></a>Version 2017-08-02
* **Écrire dans les champs personne, choix et recherche** : SharePoint créer un élément et mettre à jour [l’élément prend désormais en charge la possibilité de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) définir des champs personne, choix et recherche.
* **Autres paramètres d’action** -désormais, il y a plus de contrôle sur l’exécution des déclencheurs et des actions, notamment la configuration des stratégies de nouvelle tentative et la pagination.
* **Quatre nouveaux connecteurs** : vous pouvez désormais utiliser le stockage fichier Azure, les formes élastiques, Plivo et Video indexer.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/four-connector-action-settings/) sur cette version.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Version 2017-07-27-mise à jour du 2e trimestre pour Microsoft Flow
* Importez **et** exportez des solutions de Flow et importez-les dans des environnements ou de test à la production. 
* **Utiliser des expressions dans des actions** : entrez des expressions dans n’importe quelle action et bénéficiez d’une aide en ligne sur la façon de les utiliser.
* **Augmentation jusqu’à Azure Logic Apps** : enregistrez vos flux en tant que ressource d’application logique Azure qui peut être déployée par le biais de Visual Studio ou de l’portail Azure.
* **Visibilité** de l’administrateur : Téléchargez Microsoft Flow utilisation dans votre locataire pour comprendre exactement où et comment les flux sont utilisés.
* **Flux dans dynamics 365** -utilisez des flux dans Dynamics 365 pour operations & Financials, Business Edition.
* **Rechercher des scénarios plus facilement** -parcourir tout ce que le connecteur peut faire, puis utiliser n’importe quel déclencheur comme point de départ pour la création de flux.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/q2-2017-update/) sur cette version.

### <a name="release-2017-07-13"></a>Version 2017-07-13
* **Amélioration** de la publication de modèles : Publiez tous les flows que vous créez, ainsi que ses catégories, dans la galerie publique.
* **Obtenir des événements dans votre calendrier Outlook** -nouvelle action pour retourner tous les événements entre deux fois dans votre calendrier.
* **Nouvelles fonctionnalités mobiles** : exécuter des flux à la demande et soumettre à nouveau les exécutions ayant échoué dans l’application mobile.
* **Menus déroulants dynamiques dans les connecteurs personnalisés** : créez des menus déroulants dynamiques, des déclencheurs d’interrogation et testez vos connecteurs personnalisés.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sur cette version.

### <a name="release-2017-06-28"></a>Version 2017-06-28
* **Mettre à jour vos paramètres de langue** : vous pouvez personnaliser la langue et la région que Microsoft Flow utilise dans le menu paramètres.
* **Cinq nouveaux connecteurs** -ajout de la prise en charge de Adobe Creative Cloud, Bing maps, recherche Bing, JotForm et Freshservice.
* **Configurer des délais d’attente** -modifiez les actions de longue durée, telles que les approbations, exécutez avant qu’elles « expirent » et que le workflow continue.
* **Inclure des commentaires dans Outlook pour les approbations** : lorsque vous recevez une demande d’approbation, vous pouvez fournir des commentaires sans jamais quitter Outlook.
* **Couleurs** de la personnalisation des connecteurs personnalisés : vous pouvez maintenant entrer une couleur pour vos connecteurs personnalisés qui seront utilisés pour les arrière-plans.
* **Enregistrer en tant que pour les flux d’équipe** : effectuer des copies de tous les flux, y compris les flux d’équipe
* **Supprimer les informations de Flow** : lorsque vous supprimez un Flow, vous voyez s’afficher la liste de toutes les exécutions en attente pour ce Flow.
* **Filtrage sur la page connecteurs** : recherchez les connecteurs souhaités dans la page connecteurs, puis filtrez par type de connecteur.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/language-settings-3-connectors/) sur cette version.

### <a name="release-2017-06-19"></a>Version 2017-06-19
Vous pouvez désormais afficher l’état de toutes les demandes d’approbation en attente que vous avez envoyées. En outre, vous pouvez parcourir et agir sur toutes vos approbations en attente directement à partir de votre appareil mobile.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sur cette version.

### <a name="release-2017-06-15"></a>Version 2017-06-15
* **Conversion du contenu** : nouveau connecteur qui peut convertir le contenu HTML en texte brut, ce qui est utile pour gérer les messages électroniques au format html.
* **Trois nouveaux connecteurs de base de données** : ajout de la prise en charge en lecture seule pour MySQL, PostgreSQL et Teradata. Ces connecteurs se connectent via la passerelle de données locale.
* **Trois autres connecteurs** : Connectez-vous à Azure application Insights, à des projets d’équipe et d’équipe.
* **Meilleure visualisation pour la gestion des erreurs** : les étapes qui s’exécutent après des erreurs sont maintenant affichées avec des flèches en pointillés rouges pour vous permettre de les identifier facilement.
* **Volet Détails** de l’exécution-en cas d’échec d’un workflow, il existe désormais un nouveau volet de droite qui contient des étapes utiles pour la correction de votre fluide.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/seven-connectors-and-html/) sur cette version.

### <a name="release-2017-06-04"></a>Version 2017-06-04
* **GA pour Windows Phone** - [l’application mobile Microsoft Flow a été mise à la disposition générale pour Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **E-mails sur les échecs de transmission** : Soyez averti par courrier électronique lorsque vous avez un workflow qui échoue. Ces messages d’échec ne seront envoyés qu’une fois par semaine et peuvent être activés ou désactivés par l’utilisateur.
* **Sélectionner une action pour les tables** : utilisez la nouvelle action sélectionner pour modifier l’ensemble des colonnes qui seront incluses dans les tables.
* **Connecteur Microsoft Forms** : Microsoft Forms est un nouveau composant d’Office 365 Education qui permet aux enseignants et aux étudiants de créer rapidement et facilement des questionnaires personnalisés, des enquêtes, des questionnaires, des inscriptions, etc.
* **Office 365 Enterprise K1 plan** -powerapps et Microsoft Flow sont désormais inclus dans le plan Office 365 Enterprise K1 avec certains quotas.
* Les **en-têtes HTTP sont plus faciles** : tout comme l’action Select, vous pouvez fournir un nom d’en-tête et une valeur d’en-tête en remplissant simplement les zones de texte de l’action.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sur cette version.

### <a name="release-2017-05-23"></a>Version 2017-05-23
* Le **Connecteur Microsoft teams** - [Microsoft teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) est un espace de travail de conversation dans Office 365 qui regroupe des personnes, des conversations et du contenu, ainsi que les outils dont les équipes ont besoin pour collaborer facilement pour atteindre davantage.
* Les **widgets sur les widgets iOS et Android** Microsoft Flow sont des raccourcis de bouton qui vous offrent un moyen plus simple et plus rapide de déclencher des boutons directement à partir de votre écran d’accueil.
* **Créer des étapes de gestion des erreurs** : définissez une ou plusieurs étapes à exécuter après l’échec d’une action. Par exemple, recevez immédiatement une notification si votre workflow ne parvient pas à créer un enregistrement dans Dynamics 365.
* **Variables de type Integer et float** : initialisent et incrémentent ou décrémentent des compteurs à l’intérieur d’une exécution de workflow pour compter le nombre de fois qu’un certain ensemble de logique s’exécute.
* **Page Détails du flux** -quand vous sélectionnez un flux dans votre liste **mes flux** , une page contenant des détails sur ce flux s’affiche, par exemple, qui a accès et l’historique des exécutions.
* **Quotas d’exécution des flows pour** les administrateurs : les administrateurs peuvent désormais surveiller l’utilisation de l’exécution du workflow au sein d’une organisation par rapport au quota d’exécution commun de l’entreprise et obtenir une répartition des quotas pour comprendre quelles licences contribuent à leur quota.
* **Améliorations du déclencheur de requête http** : utilisez différentes méthodes http et ajoutez des segments de chemin d’accès pour le déclencheur de requête.
* **Deux connecteurs partenaires** : Microsoft Flow pouvez maintenant vous connecter à Parserr, à un service d’analyse de courrier électronique et à cognito Forms, un service de formulaires en ligne.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/error-handling/) sur cette version.

### <a name="release-2017-05-12"></a>Version 2017-05-12
* **Intégration de bibliothèques de documents SharePoint** : vous pouvez sélectionner n’importe quel fichier dans une bibliothèque de documents et lancer un Flow, par exemple pour l’envoyer à votre responsable pour approbation, [et bien plus encore](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Connecteur Microsoft Planner** : Microsoft Planner vous permet de réunir facilement des équipes, des tâches, des documents et des conversations pour obtenir de meilleurs résultats.
* **Vue d’administration des licences** : les administrateurs peuvent voir toutes les licences Microsoft Flow et PowerApp (à la fois version d’évaluation et payante) dans le centre d’administration Microsoft Flow.
* **Programme de la communauté PowerApp** -le plan de la communauté PowerApp est un plan gratuit permettant aux utilisateurs d’explorer, de découvrir et de développer des compétences pour les powerapps, les Microsoft Flow et les Common Data Service.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/planner-community-and-licenses/) sur cette version.

### <a name="release-2017-05-09"></a>Version 2017-05-09
* **Connecteur Azure ad** : il existe un nouveau connecteur pour effectuer des actions d’administration à partir de Microsoft Flow, notamment créer des utilisateurs ou les ajouter à des groupes.
* **Améliorations d’Office 365 Outlook** -les flux peuvent maintenant être déclenchés par des boîtes aux lettres partagées et envoyer des messages à une boîte aux lettres partagée. Ils peuvent également définir ou lire des réponses automatiques.
* **Disponible au Canada** : vous pouvez maintenant créer vos flux au Canada.
* **Créer des webhooks d’API personnalisée** -les développeurs de connecteurs personnalisés peuvent désormais ajouter des déclencheurs à leurs API personnalisées avec des webhooks.
* **Gérer les propriétaires de Flow dans le centre d’administration** : les administrateurs d’environnement peuvent gérer les propriétaires de Flow dans le centre d’administration Microsoft Flow.
* **Référence de la documentation** sur le connecteur : nous disposons désormais d’une [référence complète sur docs.Microsoft.com](https://docs.microsoft.com/Connectors/).
* **Deux services partenaires** : deux nouveaux services partenaires ont été publiés : Nexmo et Paylocity.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/canada-mailboxes-aad) sur cette version.

### <a name="release-2017-04-27"></a>Version 2017-04-27
* **Générer des flux avec des étapes parallèles** : créer des flux avec une exécution parallèle : cela signifie que vous pouvez avoir deux ou plusieurs étapes qui s’exécutent exactement au même moment.
* **Cinq nouveaux services pris en charge** : cinq nouveaux services : approbations, E-mail de benchmark, capsule CRM, LiveChat et gestionnaire de clients Outlook.
* **Surveiller les nouvelles tentatives pour les actions** -Microsoft Flow réessayera en cas d’échec avec les services. Voyons maintenant combien de nouvelles tentatives automatiques ont eu lieu et les détails de ce qui s’est passé.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/parallel-actions/) sur cette version.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Version 2017-04-17-mise à jour Q1 pour Microsoft Flow
* **Expériences d’approbation modernes** : créez des flux de travail dans lesquels les approbateurs peuvent approuver en toute sécurité à l’intérieur de l’application mobile Microsoft Flow ou du centre d’approbations unifiées sur le site Web Microsoft Flow.
* **Disponibilité générale des flux d’équipe** : plusieurs personnes peuvent posséder et gérer un flux avec les flux d’équipe, qui sont désormais mis à la disposition générale.
* **Connecteurs de build pour Microsoft Flow** -tout le monde peut envoyer son propre Connecteur Microsoft Flow gratuitement pour le reste du monde.
* **Concepteur « diététique »** -pour certains modèles, une nouvelle version du concepteur présente uniquement les champs requis pour créer un fluide, ce qui simplifie l’expérience.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/q1-2017-update/) sur cette version.

### <a name="release-2017-04-11"></a>Version 2017-04-11
* **Nouvelles actions pour générer des tables et des listes** -nouveau créer une table HTML, créer une table CSV et joindre des actions qui peuvent traiter des listes d’éléments (au lieu de l’application précédente apply-to-each uniquement).
* **Insérer des étapes partout** : vous pouvez maintenant insérer une nouvelle étape n’importe où dans le Workflow sans avoir à effectuer une opération glisser-déplacer.
* **Quatre nouveaux services** : Flow prend désormais en charge la planification de 10 à 8, Act !, Inoreader et le API vision par ordinateur. Avec la API Vision par ordinateur vous pouvez traiter les images pour récupérer le contenu de texte (également appelé OCR) ou baliser automatiquement les images en fonction de leur contenu.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sur cette version.

### <a name="release-2017-04-03"></a>Version 2017-04-03
* **Windows Phone version bêta** : le programme Windows Phone App Beta est disponible pour obtenir un aperçu de l’application sur votre Windows Phone. [En savoir plus](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **PDF Muhimbi** : vous pouvez désormais convertir des fichiers Microsoft Word au format PDF, ajouter des filigranes, fusionner des documents et bien plus encore avec Muhimbi PDF. [En savoir plus](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Déclenchez des flux à partir des boutons physiques** -annonce de partenariats avec deux des principaux produits dans l’espace physique du bouton : flic par les laboratoires de raccourcis et bouton BTTN par le bouton Corporation. [En savoir plus](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Version 2017-03-22
* **Effectuer une copie de votre Flow** : vous pouvez maintenant effectuer une copie de votre workflow pour travailler sur des versions préliminaires ou dupliquer un fluide que vous avez créé dans le passé.
* **Deux nouveaux services** : ajout de la prise en charge de Toodledo-Gérez votre liste des tâches en créant et mettant à jour des tâches, et Zendesk, qui fournit un service client et une plateforme de création de tickets de support.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/make-a-copy/) sur cette version.

### <a name="release-2017-03-15"></a>Version 2017-03-15
* **Partager des boutons avec des collègues** : vous pouvez désormais partager des boutons de Flow avec d’autres personnes, ce qui permet à n’importe quel utilisateur professionnel d’effectuer des tâches rapides.
* **Boutons de déclenchement à partir de l’écran d’accueil** : les raccourcis vers les boutons de déroulement à partir des écrans d’accueil et de verrouillage des appareils mobiles permettent de déclencher plus rapidement un fluide.
* **Flux d’équipe dans l’application Microsoft Flow** : vous pouvez maintenant voir les flux qui ont d’autres propriétaires dans l’application Microsoft Flow pour iOS ou Android.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/button-sharing/) sur cette version.

### <a name="release-2017-03-10"></a>Version 2017-03-10
* **Amélioration de l’expérience des connecteurs personnalisés** : vous pouvez désormais utiliser une collection de publications pour créer un connecteur personnalisé et modifier, ajouter et tester des actions.
* **Deux nouveaux services** : ajout de notifications PowerApp et de support PivotalTracker.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/new-updates-custom-api/) sur cette version.

### <a name="release-2017-02-27"></a>Version 2017-02-27
* **Déclencher vos boutons de Flow** : vous pouvez désormais déclencher des boutons de Flow directement à partir de Microsoft Flow. Quand vous examinez votre liste de flux, il vous suffit de sélectionner le « ... » et choisissez la commande Exécuter maintenant.
* **Cinq nouveaux services** : ajout de la prise en charge de Oracle Database, Intercom, FreshBooks, LeanKit et webmerge.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sur cette version.

### <a name="release-2017-02-21"></a>Version 2017-02-21
* **Afficher les flux d’environnement** : les administrateurs d’environnement peuvent désormais afficher la liste complète de tous les flux au sein d’un environnement donné, ainsi que activer, désactiver ou supprimer des flux.
* **Deux nouveaux services** : ajout de la prise en charge de Azure Automation et Basecamp 2.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sur cette version.

### <a name="release-2017-02-16"></a>Version 2017-02-16
* **Cinq nouveaux services** : ajout de la prise en charge de Azure Data Lake, bitbucket (un service d’hébergement Web pour les projets qui utilisent le contrôle de révision git), Eventbrite, Infusionsoft et Pipedrive.
* **Authentification http personnalisée** : dans le concepteur de Flow, il est désormais possible d’utiliser l’authentification avec des points de terminaison HTTP personnalisés.
* **Analyser les messages JSON** : vous pouvez analyser les données JSON à partir du déclencheur de requête HTTP ou retournée à partir de l’action http.
* **Filtrage d’exécution de flux** : filtrage amélioré pour les exécutions de flux, avec des options plus spécifiques, notamment la consultation des flux en cours d’exécution ou l’annulation des exécutions.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sur cette version.

### <a name="release-2017-02-06"></a>Version 2017-02-06
* **Flux d’équipe** : les flux d’équipe permettent à plusieurs personnes de posséder et de gérer un flux ensemble, et, si une personne quitte une organisation, les flux qu’elle a créés peuvent continuer à s’exécuter.
* **Partage de connecteurs personnalisés** : les connecteurs personnalisés, comme les flux d’équipe, peuvent être partagés et gérés collectivement au sein d’une organisation.
* **Prise en charge de Gmail et de Luis** : Connectez-vous à Gmail et à Azure cognitive services Language Understanding intelligent service.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/team-flows/) sur cette version.

### <a name="release-2017-01-30"></a>Version 2017-01-30
* **Entrées de bouton de Flow** : les boutons de déroulement peuvent désormais recevoir des entrées utilisateur au moment de l’exécution. ainsi, les auteurs de Flow peuvent définir des informations qui sont transmises lorsque le bouton est frappé.
* **Tâches Outlook et HelloSign** -le service tâches Outlook vous permet de gérer des tâches et HelloSign active des signatures électroniques sécurisées.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/button-user-inputs/) sur cette version.

### <a name="release-2017-01-23"></a>Version 2017-01-23
* **Rechercher par service** : Parcourir par service lorsque vous ajoutez un déclencheur ou une action pour afficher toutes les actions pour chaque service.
* **Switch case** -ajoutez des blocs de commutateur pour avoir plusieurs branches de logique parallèle.
* **Autres actions de messagerie** : nouvelles fonctionnalités dans les services Office 365 Outlook et Outlook.com pour travailler avec des messages avec indicateur.
* **Cinq nouveaux services** : Connectez-vous à des systèmes de fichiers locaux ou réseau, à l’entrelacement de service de paiement, à IBM Informix, à IBM DB2 et à uservoice.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/search-by-service/) sur cette version.

### <a name="release-2017-01-14"></a>Version 2017-01-14
* Soumettre à nouveau les **exécutions** : si un workflow a échoué et que vous souhaitez essayer de le corriger et de l’exécuter à nouveau, vous pouvez renvoyer l’échec de l’exécution.
* **Annuler les exécutions** : lorsqu’un Flow est bloqué, vous pouvez maintenant annuler explicitement l’exécution.
* **Deux nouveaux services** : ajout de la prise en charge de GoToTraining et GoToWebinar.
* **Liens mobiles** : vous pouvez partager des modèles directement à partir de l’application mobile. nous avons ajouté un lien de téléchargement rapide pour les applications en haut du site Web.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/managing-runs/) sur cette version.

### <a name="release-2016-12-29"></a>Version 2016-12-29
Microsoft Flow prend désormais en charge DocuSign pour gérer les qui permet et la gestion des transactions numériques. SurveyMonkey, pour les enquêtes sur le Web ; et l’application de création de notes OneNote (comptes professionnels uniquement).

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/final-2016-services/) sur cette version.

### <a name="release-2016-12-20"></a>Version 2016-12-20
* **Exécuter maintenant** : vous pouvez maintenant activer un déclencheur périodique à la demande, par exemple, si vous avez un rapport planifié tous les jours, mais que vous avez besoin d’exécuter le rapport **maintenant** .
* **Six nouveaux services** : créez des flux qui se connectent à MSN Météo, Medium, Google contacts, buffer, récolte et TypeForm.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sur cette version.

### <a name="release-2016-12-14"></a>Version 2016-12-14
Vous pouvez maintenant tirer parti d’informations précieuses lors du déclenchement d’un workflow, par exemple à partir de l’endroit où le bouton a été déclenché, par qui, à quel moment, et bien plus encore.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/button-trigger-tokens/) sur cette version.

### <a name="release-2016-12-06"></a>Version 2016-12-06
* **Présentation de la formation guidée** : commencez avec une collection séquencée de cours qui associent des vidéos à la documentation pour vous aider à comprendre les fonctionnalités étendues et puissantes de Microsoft Flow.
* **Deux nouveaux services** : les flux peuvent désormais utiliser Freshdesk, une solution de support client et GoToMeeting, un outil de réunion en ligne.
* **Prise en charge du webhook http** : un Flow peut maintenant être un point de terminaison pour les webhooks qui s’inscrivent et se désinscrivent automatiquement.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sur cette version.

### <a name="release-2016-11-23"></a>Version 2016-11-23
* **Power bi la prise en charge des alertes dans Flow** -transformez les Insights en actions en déclenchant des flux à partir d’alertes de données Power bi.
* **Améliorations des applications mobiles** : ajout de la possibilité de créer des flux à partir d’un espace, en plus de l’expérience déjà existante de la création à partir de modèles. Nous avons également amélioré les performances lors de l’affichage des exécutions de fluides.
* **Huit nouveaux services** : vous pouvez maintenant vous connecter à Azure Resource Manager, files d’attente Azure, chatter, Disqus, Azure Cosmos DB, cognitive services API visage, HipChat et WordPress.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sur cette version.

### <a name="release-2016-11-15"></a>Version 2016-11-15
* **Microsoft Flow programme partenaire** : Microsoft Flow dispose désormais d’un programme partenaire certifié pour établir des connexions et tirer parti des compétences et de l’expérience d’une autre société avec Microsoft Flow dans le monde entier.
* **Six nouveaux services** : nous avons également publié six services cette semaine : asana, Campfire, EASYREDMINE, JIRA, redmine et Vimeo.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/partner-program-six-new-services/) sur cette version.

### <a name="release-2016-10-31---general-availability"></a>Version 2016-10-31-disponibilité générale
* **Tarifs et licences** : désormais disponible dans les plans gratuit et payant, ainsi qu’inclus dans Office 365 et Dynamics 365.
* **Microsoft Flow Centre d’administration** -entreprise-prêt avec le nouveau centre d’administration. Dans le centre d’administration, vous pouvez gérer les environnements au sein de l’organisation.
* **Stratégies de protection contre la perte de données** -les administrateurs peuvent créer des stratégies de protection contre la perte de données pour contrôler le workflow des données entre les services.
* **Disponibilité Android** : l’application Microsoft Flow Phone est désormais disponible pour iOS et Android. L’application vous permet d’obtenir des notifications, d’analyser l’activité et de démarrer des flux en appuyant sur un bouton.
* **Nouvelles expériences de conception** : vous pouvez désormais effectuer une recherche dans le contenu dynamique passé d’une étape à l’autre, ce qui permet de référencer plus rapidement les données de votre choix.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/announcing-ga/) sur cette version.

### <a name="release-2016-10-26"></a>Version 2016-10-26
* **Flux de bouton** : il existe des opérations innombrables que nous souhaitons déclencher à tout moment et en tout lieu. Maintenant, avec les flux de bouton, vous pouvez les faire simplement en cliquant sur un bouton à partir de votre appareil mobile.
* **Annonce des environnements** : les environnements sont des espaces distincts pour stocker et gérer les flux de votre organisation. Les environnements sont géolocalisés, ce qui signifie que les flux, les applications et les données d’entreprise qui résident dans un environnement seront dans la région où se trouve l’environnement.
* **Six nouveaux services** : ajout de la prise en charge de Bit.ly, cognitive services analyse de texte, Dynamics NAV, Dynamics 365 pour Financials, Instapaper et Pinterest.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/environments-for-makers/) sur cette version.

### <a name="release-2016-10-16"></a>Version 2016-10-16
* Les **connecteurs personnalisés prennent en charge davantage de types d’authentification** : les connecteurs personnalisés prennent désormais en charge l’authentification par clé API et peuvent s’authentifier auprès d’un service qui prend en charge la spécification OAuth 2,0 complète.
* **Trois nouveaux services pris en charge** : nous avons ajouté la prise en charge de Basecamp 3, Blogger et PagerDuty.
* **Améliorations du concepteur** -amélioration des performances, vous pouvez maintenant mettre à jour et réparer vos connexions directement à partir du... menu pour chaque action, et nous avons ajouté une nouvelle étape appelée Terminate, que vous pouvez utiliser pour mettre fin à l’exécution d’un Workflow.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/early-october-updates/) sur cette version.

### <a name="release-2016-09-25"></a>Version 2016-09-25
La création de Flow est désormais disponible à partir de vos téléphones mobiles. Parcourez notre galerie de modèles enrichis, parcourez notre liste de services ou sélectionnez une catégorie de modèle à explorer. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/mobile-creation/) sur cette version.

### <a name="release-2016-09-22"></a>Version 2016-09-22
* **Sélecteur de personnes Microsoft Graph** : un nouveau sélecteur de personnes Microsoft Graph est intégré directement dans l’interface utilisateur de Microsoft Flow pour vous aider à choisir le contact ou l’adresse de messagerie approprié.
* **Prise en charge de Microsoft Dynamics AX** : à partir de vos flux, vous pouvez désormais prendre des mesures sur vos données d’opérations Dynamics AX Online, de la création de nouveaux enregistrements à l’interrogation des données.
* **Deux nouveaux services de partenaires** : utilisez à présent appFigures ou Insights à partir de vos flux.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/more-september-updates/) sur cette version.

### <a name="release-2016-09-14"></a>Version 2016-09-14
* **Incorporation dans votre site Web ou votre application** : les développeurs peuvent désormais incorporer des Microsoft Flow directement dans leurs applications ou sites Web pour offrir à leurs utilisateurs un moyen simple d’automatiser leurs tâches personnelles ou professionnelles.
* **Utiliser un workflow en tant que point de terminaison http** : vous pouvez maintenant utiliser un Flow lui-même en tant qu’API http. Il existe un déclencheur appelé request à l’intérieur du Flow. vous pouvez choisir de répondre à la demande entrante en ajoutant une carte de réponse.
* **Support todo** -todo vous offre une perspective sur tous vos projets, au travail et chez vous.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/extend-web-site-application/) sur cette version.

### <a name="release-2016-09-01"></a>Version 2016-09-01
Microsoft Flow maintenant disponible pour tout le monde : nous avons initialement ouvert la version préliminaire uniquement pour les adresses de messagerie fournies par votre entreprise ou votre école, comme celles utilisées avec Office 365 Business ou Office 365 Enterprise. Aujourd’hui, nous annoncerons que la version préliminaire est officiellement disponible, gratuite à utiliser, pour tous les utilisateurs, quel que soit le courrier électronique que vous avez. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/available-for-everyone/) sur cette version.

### <a name="release-2016-08-31"></a>Version 2016-08-31
* **Conditionnels imbriqués** : vous pouvez maintenant ajouter une deuxième condition (ou troisième, etc...) à l’intérieur d’une autre.
* **Apply to each** -une boucle apply to each permet de contrôler la liste que vous répétez.
* **Do-** until : une boucle Do-Until vous permet de répéter une étape jusqu’à ce qu’une certaine condition soit remplie.
* **Filtrer les tableaux** : il existe une seule étape de filtre natif qui peut s’assurer que chaque élément de la liste correspond à une expression que vous définissez.
* **Composer des variables de chaîne** : vous pouvez maintenant composer une variable de chaîne.
* **Étendues** : les étendues sont un moyen simple de regrouper deux ou plusieurs actions.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/build-advanced-flows/) sur cette version.

### <a name="release-2016-08-27"></a>Version 2016-08-27
* **Commentaires sur les étapes** -les commentaires facilitent l’annotation de chaque action avec des notes afin que vous puissiez facilement vous souvenir de ce que le Flow a besoin
* **Prise en charge de Smartsheet** : cette semaine, nous avons ajouté la prise en charge de la connexion à Smartsheet. Smartsheet est un service qui facilite la collaboration sur des feuilles dans le Cloud.
* **Améliorations de l’interface utilisateur lors** de la création de flux : nous avons créé le nom de flux avant et centre et déplacé le bouton enregistrer en haut de la page pour y accéder facilement.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/add-comments-smartsheet/) sur cette version.

### <a name="release-2016-08-18"></a>Version 2016-08-18
Vous pouvez maintenant afficher un aperçu de la nouvelle expérience des listes modernes SharePoint Online qui comprend l’intégration de Microsoft Flow. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sur cette version.

### <a name="release-2016-08-13"></a>Version 2016-08-13
* **Visual Studio Team Services** avec Flow, vous pouvez désormais connecter VSTS à un large éventail de services, tels que l’e-mail O365, la marge, Trello et Wunderlist.
* Les **améliorations apportées à SharePoint** -les listes SharePoint prennent en charge une plage de types de données à partir d’objets simples comme des lignes de texte uniques et de la date et de l’heure pour des objets complexes tels que Person ou Group, Lookup et Choice.
* **Tester les connexions Outlook o365** -chaque fois que vous créez une nouvelle connexion Office 365 Outlook, nous allons la tester pour vous assurer que vous êtes prêt à l’utiliser.
* **Contrôle booléen** : nous avons également ajouté un contrôle booléen pour clarifier les valeurs que vous devez entrer pour les champs d’entrée booléens, tels que contient les pièces jointes dans le déclencheur à l’arrivée d’un nouveau message électronique.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sur cette version.

### <a name="release-2016-08-08"></a>Version 2016-08-08
Version préliminaire publique du Common Data Service Microsoft intégré à Microsoft Flow. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/flow-and-common-data-model/) sur cette version.

### <a name="release-2016-08-05"></a>Version 2016-08-05
* **SharePoint sur site** : tout comme avec SharePoint Online, vous pouvez créer des flux autour de vos listes locales et bibliothèques de documents SharePoint à l’aide de modèles prédéfinis ou en les générant à partir de zéro.
* **Info-bulles dans le concepteur** : pour développer les fonctionnalités de chaque déclencheur et action, nous avons ajouté des bulles d’informations au-dessus de chaque étape de votre Flow.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sur cette version.

### <a name="release-2016-07-15"></a>Version 2016-07-15
* **Quatre nouveaux services ajoutés** : Connectez-vous à Google Calendar, Google Tasks, YouTube et SparkPost.
* **Renommez vos actions** : maintenant, vous pouvez distinguer ces différentes actions en les renommant.
* **Délai pour différentes périodes** : vous pouvez désormais sélectionner un nombre de secondes, de minutes, d’heures ou de jours.
* Simplification de l’utilisation de l' **Explorateur de dossiers** : nous avons simplifié l’Explorateur de dossiers. à présent, si vous sélectionnez sur la gauche, ce dossier est sélectionné, et si vous sélectionnez à droite, ce dossier s’ouvre afin que vous puissiez choisir les sous-dossiers à l’intérieur de.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/new-google-services-rename-more/) sur cette version.

### <a name="release-2016-07-08"></a>Version 2016-07-08
Connectivité locale pour Microsoft Flow à l’aide de la passerelle de données locale. Cela vous permet d’établir des connexions sécurisées à SQL Server et de les intégrer à vos flux. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/on-premises-data-gateway/) sur cette version.

### <a name="release-2016-07-02"></a>Version 2016-07-02
* **Prise en charge de Google Sheets** : dans le passé, nous avons la possibilité d’utiliser Excel, ainsi que Google Drive, mais cette semaine, nous ajoutons une prise en charge de Google Sheets native.
* Commencez **plus rapidement à partir de modèles** : nous avons également apporté des optimisations à la façon dont vous pouvez démarrer à partir de modèles. À présent, vous pouvez sélectionner les comptes que vous souhaitez utiliser pour un modèle directement en ligne sur la page du modèle.
* **Aucune autorisation n’arrivant à expiration pour SharePoint et Office 365** -maintenant, Microsoft Flow renouvellera automatiquement votre accès aux services basés sur Azure Active Directory, de sorte que tous vos flux continuent de fonctionner à travers les modifications de mot de passe.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/more-june-updates/) sur cette version.

### <a name="release-2016-06-20"></a>Version 2016-06-20
* **Présentation de la nouvelle application mobile pour Microsoft Flow** -aujourd’hui, nous avons le plaisir d’introduire une autre partie importante de notre offre : une application mobile désormais disponible en téléchargement sur iOS (bientôt sur Android) qui vous donne la possibilité de gérer, suivre et explorer votre workflows automatisés à tout moment et en tout lieu.  
* **Authentification unique** : nous avons implémenté l’authentification unique qui vous permet de vous authentifier auprès de Microsoft Flow avec d’autres services Microsoft comme Office 365.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sur cette version.

### <a name="release-2016-06-18"></a>Version 2016-06-18
* **Nouveau service de messagerie** : vous pouvez désormais envoyer des e-mails directement à partir de Microsoft Flow, sans avoir à vous connecter à vos comptes de messagerie personnels ou professionnels à l’intérieur de Microsoft Flow.
* **Notifications dans le portail** : à présent, vous verrez des notifications en haut du portail chaque fois que des éléments sont brisés avec vos flux.
* **Toutes les activités dans le portail** : vous pouvez désormais Voir l’activité dans tous vos flux en cliquant sur l’onglet nouvelle activité dans le site Web Flow.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/mail-and-all-activity/) sur cette version.

### <a name="release-2016-05-27"></a>Version 2016-05-27
* **Parcourir les modèles par service** : il existe un moyen de voir tous les services que nous prenons en charge (sans avoir à vous connecter). À partir de cette page, vous pouvez voir une description de chacun des services et consulter les modèles dont nous disposons pour ce service.
* **Créez et utilisez vos connecteurs personnalisés** . comme vous pouvez créer des connecteurs personnalisés dans powerapps, vous pouvez également vous connecter à vos propres API à l’adresse Flow.Microsoft.com :
* **Testez vos flux avant de terminer** -chaque fois que vous enregistrez un flux, vous pouvez maintenant voir les résultats de l’exécution du flux en temps réel dans la page, si vous exécutez l’action de démarrage.

[En savoir plus et poser des questions](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sur cette version.

### <a name="release-2016-05-07"></a>Version 2016-05-07
Ajout de deux nouveaux services : Microsoft Project Online et Mandrill by MailChimp. [En savoir plus et poser des questions](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sur cette version.

### <a name="release-2016-04-27---public-preview"></a>Version 2016-04-27-version préliminaire publique
Si vous avez utilisé des flux logiques dans le cadre de [Microsoft PowerApps](https://powerapps.microsoft.com), la version préliminaire de Microsoft Flow offre plusieurs nouvelles fonctionnalités :

* Vous pouvez maintenant parcourir une galerie de dizaines de modèles et trier par popularité, nom ou date de publication.
* Vous pouvez [publier vos propres modèles](publish-a-template.md) dans la Galerie après avoir personnalisé un fluide.
* Vous pouvez voir l’historique de chaque vérification et exécution de votre workflow.
* Lorsque vous enregistrez un fluide, vous pouvez le [regarder en action immédiatement](see-a-flow-run.md) en effectuant simplement l’action du déclencheur.
* Nous avons une [nouvelle communauté](https://go.microsoft.com/fwlink/?LinkID=787467) qui vous permet de discuter du Flow ou de [soumettre vos idées](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Étapes suivantes
Si vous avez des problèmes qui n’ont pas encore été traités dans ces notes de publication ou dans le [Forum aux questions](frequently-asked-questions.md), [Rejoignez notre communauté](https://go.microsoft.com/fwlink/?LinkID=787467) pour poser des questions ou [Contactez le support technique](https://go.microsoft.com/fwlink/?LinkID=787479).

