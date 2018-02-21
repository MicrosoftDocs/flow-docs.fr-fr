---
title: Notes de publication | Microsoft Docs
description: "Problèmes courants et nouveautés des versions Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/12/2018
ms.author: stepsic
ms.openlocfilehash: 3687266e84c06c37ac6ae0ee3d89aae0814158f3
ms.sourcegitcommit: 28b6b09c9f3dd98a64492668d9a3b8c7bfbd6ce3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2018
---
# <a name="release-notes"></a>Notes de publication
## <a name="top-questions"></a>Principales questions
1. Mon flux a échoué. Comment le corriger ?
   
   1. Identifiez l’erreur. Commencez par accéder à l’icône de notifications en haut du portail web ou par sélectionner l’onglet **Activité** dans l’application mobile. Votre flux doit s’afficher et vous pouvez le sélectionner.
   2. Vous voyez maintenant les détails du flux. Trouvez l’étape avec un point d’exclamation rouge pour voir le message d’erreur relatif à votre flux.
   3. Selon le message d’erreur, vous devez pouvoir **modifier** le flux et le corriger. [En savoir plus sur la façon de corriger les problèmes courants rencontrés avec les flux](fix-flow-failures.md).
2. Comment utiliser une condition ou une expression avancée ?
   
   * En savoir plus sur l’[ajout de conditions](add-condition.md).
   * Si vous souhaitez avoir plusieurs étapes à l’intérieur d’un flux, cliquez ou appuyez sur **Ajouter une condition** dans une condition existante.
   * Créez une expression avancée en faisant référence à [une fonction dans Logic Apps](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Comment fonctionnent les licences avec Office 365 ?
   
   * Si vous êtes un utilisateur Office 365, vous bénéficiez d’un accès complet à Microsoft Flow dans le cadre de l’abonnement Office 365. Pour plus d’informations, consultez la [tarification des offres Microsoft Flow](https://flow.microsoft.com/pricing/).
   * Si vous êtes un administrateur, consultez les informations sur [les licences Microsoft Flow](organization-q-and-a.md), y compris avec Office 365.

## <a name="known-issues-and-resolutions"></a>Problèmes connus et solutions
1. Les listes SharePoint sur Mes Sites et qui ne sont pas de type *Liste personnalisée* ne sont pas prises en charge. Pour contourner ce problème, créez une liste personnalisée sur un site SharePoint standard.
2. Les flux ne peuvent pas être écrits dans les champs Taxonomie dans les listes SharePoint. Jusqu’à ce que le problème soit corrigé, nous vous recommandons d’utiliser un champ de chaîne simple.
3. Les déclencheurs de fichier ne sont pas activés pour les fichiers ajoutés dans les dossiers imbriqués au sein du dossier sélectionné.

## <a name="whats-new"></a>Nouveautés

### <a name="release-2018-02-09"></a>Version 09-02-2018

- **Haute disponibilité de la passerelle**  - créez des clusters à haute disponibilité de passerelles de données locales pour maintenir les connexions lorsque des machines uniques s’arrêtent.
- **Amélioration de l’option Appliquer à chacun** - avec Flow - Plan 1 ou Flow - Plan 2, traitez jusqu'à 100 000 éléments en une seule fois et 50 actions en parallèle dans des boucles Appliquer à chacun. 

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sur cette version.

### <a name="release-2018-01-29"></a>Version 29-01-2018

- **Flux dans Microsoft Teams** - à partir de Teams, vous pouvez créer et gérer des flux, examiner vos approbations envoyées et reçues, et lancer des flux directement au sein de l’application de bureau Teams ou sur teams.microsoft.com - [En savoir plus ici](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notifications de modification partagées** - lorsqu’un flux dont vous êtes propriétaire est modifié par un collègue, vous recevez une notification par courrier électronique vous indiquant qui a modifié ce flux.
- **Nouvelles expressions** - deux nouveaux jeux d’expressions ont été ajoutés : un pour analyser les URL et un autre pour utiliser des objets JSON.
- **Trois nouveaux connecteurs** : cette semaine, deux nouveaux connecteurs Plumsail sont disponibles : Plumsail SP et Plumsail Forms, ainsi qu’un nouveau connecteur pour kintone.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sur cette version.

### <a name="release-2018-01-17"></a>Version 17-01-2018

- **Informations de profil Office 365** - nous avons ajouté de nouvelles actions au connecteur Utilisateurs d'Office 365, qui fonctionnent avec les profils utilisateur et les photos.
- **Ajout à des variables de chaînes** - vous pouvez ajouter des chaînes à l’intérieur de boucles pour générer des tables ou d’autres listes.
- **Connecteur Infobip** - Infobip est un service permettant d’établir des communications de niveau entreprise, y compris des appels vocaux, et qui se déclenche en cas de SMS entrants.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/o365-profile-infobip/) sur cette version.

### <a name="release-2017-12-20"></a>Version 20-12-2017

Microsoft Flow Analytics est à présent disponible dans toutes les régions Microsoft Flow. Cela signifie que vous pouvez obtenir plus d’informations sur l’état de vos flux exécutés dans votre environnement.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sur cette version.


### <a name="release-2017-12-14"></a>Version 14-12-2017

- **Améliorations du connecteur Outlook** : vous pouvez enregistrer un message électronique sous forme de fichier « .eml », répondre à des invitations de calendrier automatiquement et déclencher des flux lorsque vous êtes mentionné dans un fil de discussion.
- **Améliorations des connexions** : Microsoft Flow mémorise vos connexions les plus récentes et vous montre tous les connecteurs qui viennent d’être ajoutés.
- **Cinq nouveaux connecteurs** : ajout de Azure Container Instances, Azure Kusto, Metatask, Microsoft To-Do et Plumsail Documents.
- **Améliorations HTTP** : l’action HTTP prend maintenant en charge le codage segmenté.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/outlook-connector-more/) sur cette version.

### <a name="release-2017-12-05"></a>Version 05-12-2017

Le panneau de lancement de Microsoft Flow est maintenant disponible dans toutes les régions. Ce panneau vous permet d’ajouter des valeurs à un flux lorsque vous l’exécutez à l’intérieur de votre liste ou bibliothèque de documents SharePoint.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sur cette version.


### <a name="release-2017-11-28"></a>Version 28-11-2017

- **Métadonnées gérées** : lisez et écrivez des données dans des colonnes SharePoint qui utilisent le type Métadonnées gérées (également appelées Classification).
- **Ajout aux tableaux** : ajoutez des éléments à la fin de tableaux à l’aide d’une nouvelle action de variable Ajouter au tableau.
- **Tago** : nouveau connecteur à Tago, qui fournit une connexion simple d’appareils électroniques avec des données externes permettant de prendre de meilleures décisions à l’aide d’une analyse contextuelle.
- **iPhone X** : nouvelle version de l’application Microsoft Flow qui utilise le mode plein écran sur l’iPhone X, et qui comporte une amélioration de la vitesse de chargement des images.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/managed-metadata-tago/) sur cette version.

### <a name="release-2017-11-09"></a>Version 09-11-2017

- **Intégration de OneDrive Entreprise** : il existe [maintenant un bouton de flux dans OneDrive Entreprise](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) qui permet de créer ou de déclencher des flux sur les fichiers ou dossiers sélectionnés.
- **Déclencheurs de planification** : lancez des flux lorsqu’une tâche est créée, vous est assignée ou est terminée.
- **Pièces jointes SharePoint** : utilisez des pièces jointes sur des éléments de liste SharePoint : répertorier, télécharger, ajouter ou supprimer des pièces jointes.
- **Connecteur de gestion de flux** : créez des flux qui automatisent la gestion des autres flux de votre environnement (par exemple, ajoutez des autorisations aux flux automatiquement).
- **Quatre nouveaux connecteurs** : ajout de Azure Custom Vision Service, D&B Optimizer, Enadoc et Derdak SIGNL4. 
- **Autres actions de connecteur** : exécutez des requêtes SQL, obtenez des déclencheurs de messagerie plus rapides, utilisez n’importe quelle méthode HTTP avec Azure AD et bien plus encore.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sur cette version.

### <a name="release-2017-11-02"></a>Version 02-11-2017

- **Enregistrement d’audit** : les événements d’audit Microsoft Flow sont maintenant disponibles dans le centre de sécurité et conformité Office 365 pour tous les locataires.
- **Correctifs apportés aux widgets des flux** : résolution d’un problème dans l’application mobile Flow qui empêchait le chargement des boutons dans le widget.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/security-and-compliance-center/) sur cette version.

### <a name="release-2017-10-19"></a>Version 19-10-2017

- **Action « Appliquer à chacun » imbriquée** : vous pouvez ajouter des actions « Appliquer à chacun », filtrer et sélectionner dans d’autres conteneurs « Appliquer à chacun ».
- **Actions DateTime** : nouvelles actions pour l’obtention des heures locales, l’ajout, la soustraction ou la mise en forme des heures.
- **Quatre nouveaux connecteurs** : ajout de Content Moderator, Docparser, Microsoft Kaizala et Pitney Bowes Data Validation.
- **Amélioration de l’expérience de connexion** : réception de notifications dans le portail Flow lorsqu’une connexion est interrompue et détails de connexion enrichis.
- **Collection mobile** : nouvelle collection de modèles pour les [travailleurs mobiles](https://flow.microsoft.com/collections/onthego/).
- **Collecte d’adresses e-mail via des boutons** : collectez les adresses e-mail des utilisateurs lorsque ces derniers exécutent des boutons.
- **Obtention de fichiers via des boutons** : obtenez des fichiers chargés, tels que des photos, provenant des utilisateurs lorsqu’ils exécutent des boutons.
- **Première exécution et connexion automatique** : amélioration des expériences de première exécution sur l’application mobile, notamment la connexion automatique.
- **Déclencheurs Microsoft Forms plus rapides** : les formulaires déclenchent des flux beaucoup plus rapidement qu’avant (une fois par heure).
- **Entrées de bouton dans les différentes sessions** : les boutons déclenchés sur votre téléphone mobile mémorisent les entrées précédentes.
- **Flux d’activités mobile** : amélioration du flux d’activité pour inclure des résumés d’exécution plus détaillés et des informations de dépannage.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/nested-apply-to-each/) sur cette version.

### <a name="release-2017-10-03"></a>Version 03-10-2017

- **Tous doivent approuver** : demandez l’envoi d’une demande d’approbation à plusieurs personnes pour que tous les utilisateurs qui ont reçu la demande l’approuvent.
- **Nouvelles actions OneDrive Entreprise** : générez des PDF pour les fichiers stockés sur OneDrive Entreprise et quatre nouvelles actions.
- **Connecteur Apache Impala** : Apache Impala (incubating) est la base de données d’analytique native open source pour Apache Hadoop.
- **Ajouter des descriptions de flux** : décrivez vos flux afin que vos collègues puissent en afficher un résumé lorsque vous les partagez avec eux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sur cette version.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Version 25-09-2017 - Mise à jour du 3e trimestre pour Microsoft Flow

- **Intégration SharePoint approfondie dans la version First Release** : il existe de nouveaux flux prêts à l’emploi d’envoi pour révision et un volet Flow pour la collecte d’entrées lorsque vous exécutez un flux pour les locataires First Release.
- **Dynamics 365 Customer Engagement** : Flow est maintenant intégré dans l’interface utilisateur de Dynamics 365 Customer Engagement.
- **Centre de gestion de la confidentialité Microsoft** : Flow est répertorié dans le Centre de gestion de la confidentialité Microsoft, et affiche des certifications telles que HIPAA, ISO et SOC.
- **Analyse de l’utilisation** : chaque flux possède un tableau de bord Power BI incorporé avec une analyse de l’utilisation de base.
- **Enregistrement d’audit dans la version First Release** : tous les événements de gestion de flux sont enregistrés dans le Centre de conformité et sécurité Office 365 pour les locataires de la version First Release.
- **Six nouveaux connecteurs** : ajout de LinkedIn, Groupes Office 365, Skype Entreprise, Adobe Sign, Bizzy et Azure Log Analytics Data Collection.
- **Déclencheurs SQL** : exécutez des flux lorsqu’une ligne est ajoutée ou mise à jour dans une table SQL.
- **Connecteurs personnalisés locaux** : les connecteurs personnalisés peuvent maintenant utiliser la passerelle de données locale pour se connecter aux points de terminaison internes sur votre réseau.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/q3-2017-update/) sur cette version.

### <a name="release-2017-09-21"></a>Version 21-09-2017

- **Télécharger l’historique des flux** : téléchargez l’historique d’exécution d’un flux dans un fichier CSV à ouvrir dans Excel.
- **Périodicité avancée** : créez des planifications périodiques pour déclencher vos flux (par exemple, déclencher uniquement les jours de semaine).
- **IntelliSense** : lorsque vous tapez des expressions, IntelliSense fournit des suggestions de paramètres.
- **Quatre nouveaux connecteurs** : ajout de connecteurs pour les services Azure AD HTTP, Amazon Redshift, Azure Event Grid Publish et FlowForma.
- **Partage de liens** : nouvelle action permettant de générer des liens partageables pour les fichiers OneDrive ou les blob Stockage Azure.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/download-history-recurrence/) sur cette version.


### <a name="release-2017-08-25"></a>Version 25-08-2017
* **Propriétés du document et plus encore pour SharePoint** - [Lecture et configuration des propriétés de la bibliothèque de documents SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)et utilisation de champs supplémentaires, tels que des liens vers un élément SharePoint.
* **Collections de flux** -Les collections de flux sont un ensemble de collections de modèles organisés par rôle ou verticalement.
* **Repartage de bouton** - Lorsque vous partagez des boutons avec vos collègues, ils peuvent également les partager à nouveau avec d’autres personnes.
* **Collecter des listes à partir des boutons** -Définissez des listes déroulantes d’options à choisir pour les utilisateurs lorsqu’ils appuient sur le bouton.
* **Sept nouveaux connecteurs** -Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs, et StaffHub. 
* **Améliorations de Slack et MySQL** - Créez ou rejoignez des canaux dans Slack et écrivez également dans les bases de données MySQL.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sur cette version.

### <a name="release-2017-08-02"></a>Version 02-08-2017
* **Écrire dans les champs Personne, Choix et Recherche** - Les éléments Créer un élément et Mettre à jour un élément de SharePoint [prennent maintenant en charge la possibilité de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) définir des champs Personne, Choix et Recherche.
* **Nouveaux paramètres d’action** - Vous pouvez maintenant contrôler davantage la façon dont les déclencheurs et les actions s’exécutent, y compris configurer des stratégies de nouvelle tentative et une pagination.
* **Quatre nouveaux connecteurs** - Vous pouvez maintenant utiliser Stockage Fichier Azure, Elastic Forms, Plivo et Video Indexer.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/four-connector-action-settings/) sur cette version.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Version 27-07-2017 - Mise à jour du 2e trimestre pour Microsoft Flow
* **Importer et exporter** - Exportez et importez des solutions de flux dans des environnements ou d’un environnement de test à un environnement de production. 
* **Utiliser des expressions dans les actions** - Entrez des expressions dans les actions et obtenez de l’aide en ligne sur leur utilisation.
* **Prise en charge d’Azure Logic Apps** - Enregistrez vos flux en tant que ressources Azure Logic App pouvant être déployées par le biais de Visual Studio ou du portail Azure.
* **Visibilité de l’administrateur** -Téléchargez l’utilisation de Microsoft Flow dans votre locataire pour comprendre exactement où et comment les flux sont utilisés.
* **Flux dans Dynamics 365** - Utilisez des flux dans Dynamics 365 for Operations/Financials, édition Business.
* **Rechercher plus facilement des scénarios** - Parcourez toutes les actions que le connecteur peut effectuer, puis utilisez un déclencheur comme point de départ pour la création de flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/q2-2017-update/) sur cette version.

### <a name="release-2017-07-13"></a>Version 13-07-2017
* **Amélioration de la publication du modèles** - Publiez un flux que vous créez, ainsi que ses catégories, dans la galerie publique.
* **Recevoir des événements sur le calendrier Outlook** - Nouvelle action permettant de retourner tous les événements situés dans une période donnée dans le calendrier.
* **Nouvelles fonctionnalités mobiles** - Exécutez les flux à la demande et resoumettez les exécutions ayant échoué dans l’application mobile.
* **Menus déroulants dynamiques dans les connecteurs personnalisés** - Générez des menus déroulants dynamiques, des déclencheurs d’interrogation et testez vos connecteurs personnalisés.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sur cette version.

### <a name="release-2017-06-28"></a>Version 28-06-2017
* **Mettre à jour vos paramètres de langue** - Vous pouvez personnaliser la langue et la région que Microsoft Flow utilise par le biais du menu Paramètres.
* **Cinq nouveaux connecteurs** - Ajout de la prise en charge de Adobe Creative Cloud, Bing Maps, Recherche Bing, JotForm et Freshservice.
* **Configurer des délais d’attente** - Modifiez la durée pendant laquelle les actions de longue durée (telles que des approbations) s’exécutent avant qu’elles arrivent à expiration et que le flux se poursuive.
* **Inclure des commentaires dans Outlook pour les approbations** - Lorsque vous recevez une demande d’approbation, vous pouvez fournir des commentaires sans jamais quitter Outlook.
* **Couleurs des connecteurs personnalisés** - Vous pouvez maintenant entrer une couleur pour vos connecteurs personnalisés qui sera utilisée en arrière-plan.
* **Option Enregistrer sous pour les flux d’équipe** - Effectuez des copies de n’importe quel flux, y compris les flux d’équipe
* **Supprimer les informations du flux** - Lorsque vous supprimez un flux, vous voyez la liste de toutes les exécutions en attente pour ce flux.
* **Filtrage sur la page Connecteurs** -Recherchez les connecteurs souhaités dans la page Connecteurs et filtrez-les par type.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/language-settings-3-connectors/) sur cette version.

### <a name="release-2017-06-19"></a>Version 19-06-2017
Vous pouvez à présent afficher l’état de toutes les demandes d’approbation en attente que vous avez envoyées. En outre, vous pouvez parcourir toutes vos approbations en attente et prendre les mesures adéquates directement à partir de votre appareil mobile.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sur cette version.

### <a name="release-2017-06-15"></a>Version 15-06-2017
* **Conversion du contenu** - Un nouveau connecteur peut convertir le contenu HTML en texte brut, ce qui est utile pour la gestion des courriers au format HTML.
* **Trois nouveaux connecteurs de base de données** - Ajout de la prise en charge de l’accès en lecture seule pour MySQL, PostgreSQL et Teradata. Ces connecteurs se connectent au moyen de la passerelle de données locale.
* **Trois autres connecteurs** - Connectez-vous à Azure Application Insights, Calendly et Teamwork Projects.
* **Meilleure visualisation pour la gestion des erreurs** - Les étapes qui s’exécutent après les erreurs sont maintenant affichées avec des flèches en pointillés rouges afin de pouvoir les identifier facilement.
* **Volet Détails de l’exécution** - En cas d’échec d’un flux, il existe à présent un nouveau volet, situé à droite, qui contient quelques étapes utiles pour savoir comment corriger votre flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/seven-connectors-and-html/) sur cette version.

### <a name="release-2017-06-04"></a>Version 04-06-2017
* **Disponibilité générale pour Windows Phone** - [L’application mobile Microsoft Flow a été lancée en disponibilité générale pour Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Courriers électroniques en cas d’échec des flux** - Soyez informé par courrier électronique lorsqu’un de vos flux échoue. Ces messages d’erreur sont envoyés uniquement une fois par semaine et peuvent être activés ou désactivés par l’utilisateur.
* **Action de sélection pour les tables** - Utilisez la nouvelle action de sélection pour modifier le jeu de colonnes inclus dans les tables.
* **Connecteur Microsoft Forms** - Microsoft Forms est un nouveau composant d’Office 365 Éducation qui permet aux enseignants et aux étudiants de créer rapidement et facilement des questionnaires personnalisés, des enquêtes, des questionnaires, des inscriptions et bien plus encore.
* **Offre Office 365 Enterprise K1** - PowerApps et Microsoft Flow sont maintenant inclus dans l’offre Office 365 Enterprise K1 avec certains quotas.
* **En-têtes HTTP simplifiés** - Comme pour l’action de sélection, vous pouvez fournir un nom et une valeur d’en-tête en renseignant simplement les zones de texte sur l’action.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sur cette version.

### <a name="release-2017-05-23"></a>Version 23-05-2017
* **Connecteur Microsoft Teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) est un espace de travail basé sur les conversations dans Office 365. Celui-ci rassemble les individus, les conversations et les contenus, ainsi que les outils dont les équipes ont besoin pour collaborer aisément et être plus productives.
* **Widgets sur iOS et Android** : les widgets Microsoft Flow sont des raccourcis de bouton qui fournissent un moyen plus simple et rapide de déclencher un bouton directement depuis votre écran d’accueil.
* **Créer des étapes de « gestion des erreurs »** : définissez une ou plusieurs étapes à exécuter après l’échec d’une action. Par exemple, recevez immédiatement une notification si votre flux ne parvient pas à créer un enregistrement dans Dynamics 365.
* **Variables de type Integer et Float** : initialisez et incrémentez ou décrémentez les compteurs dans une exécution de flux pour compter le nombre d’exécutions d’un ensemble de logique donné.
* **Page Détails flux** : lorsque vous sélectionnez un flux dans la liste **Mes flux**, une page affiche des détails sur ce flux, comme l’utilisateur qui y a accès et l’historique d’exécution.
* **Quotas d’exécutions de flux pour les administrateurs** : ces derniers peuvent maintenant surveiller l’utilisation des exécutions de flux au sein d’une organisation, la comparer au quota d’exécutions communes de l’entreprise et obtenir une répartition du quota pour comprendre les licences qui y contribuent.
* **Améliorations du déclencheur de demande HTTP** : utilisez différentes méthodes HTTP et ajoutez des segments de chemin d’accès pour le déclencheur de la demande.
* **Deux connecteurs partenaires** : Microsoft Flow peut maintenant se connecter à Parserr, un service d’analyse de courrier et à Cognito Forms, un service de formulaires en ligne.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/error-handling/) sur cette version.

### <a name="release-2017-05-12"></a>Version 12-05-2017
* **Intégration de bibliothèques de documents SharePoint** - Vous pouvez sélectionner n’importe quel fichier dans une bibliothèque de documents et lancer un flux, par exemple pour l’envoyer à votre responsable pour approbation, [et bien plus encore](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Connecteur du Planificateur Microsoft** - Le Planificateur Microsoft vous permet de réunir aisément les équipes, les tâches, les documents et les conversations pour de meilleurs résultats.
* **Affichage des licences par l’Administrateur** - Les administrateurs peuvent afficher toutes les licences Microsoft Flow et PowerApps (d’évaluation et payantes) dans le Centre d’administration Microsoft Flow.
* **Offre de la communauté PowerApps** - L’offre de la communauté PowerApps est un plan gratuit permettant aux utilisateurs d’explorer, de découvrir et d’apprendre à maîtriser PowerApps, Microsoft Flow et Common Data Service.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/planner-community-and-licenses/) sur cette version.

### <a name="release-2017-05-09"></a>Version 09-05-2017
* **Connecteur Azure AD** : un nouveau connecteur permet d’effectuer des actions d’administrateur à partir de Microsoft Flow, y compris la création d’utilisateurs ou l’ajout d’utilisateurs à des groupes.
* **Améliorations apportées à Outlook Office 365** : les flux peuvent maintenant être déclenchés par des boîtes aux lettres partagées et envoyer des messages à une boîte aux lettres partagée. Ils peuvent également définir ou lire les réponses automatiques.
* **Disponibilité au Canada** : vous pouvez maintenant créer vos flux au Canada.
* **Créer des webhooks d’API personnalisée** : les développeurs de connecteurs personnalisés peuvent maintenant ajouter des déclencheurs à leurs API personnalisées avec des webhooks.
* **Gérer les propriétaires de flux dans le centre d’administration** : les administrateurs d’environnement peuvent gérer les propriétaires de flux dans le centre d’administration Microsoft Flow.
* **Documentation de référence sur les connecteurs** : nous disposons à présent d’une [documentation de référence complète sur les connecteurs sur docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Deux services partenaires** : deux nouveaux services partenaires ont été publiés : Nexmo et Paylocity.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/canada-mailboxes-aad) sur cette version.

### <a name="release-2017-04-27"></a>Version 27-04-2017
* **Créer des flux avec des étapes parallèles** : créez des flux avec une exécution parallèle : cela signifie que vous avez au moins deux étapes qui s’exécutent en même temps.
* **Cinq nouveaux services pris en charge** : Approbations, Benchmark Email, Capsule CRM, LiveChat et Outlook Customer Manager.
* **Surveiller les nouvelles tentatives pour les actions** : Microsoft Flow effectue de nouvelles tentatives lorsque l’exécution de services échoue. Vous pouvez maintenant voir le nombre de nouvelles tentatives automatiques qui se sont produites et les détails associés.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/parallel-actions/) sur cette version.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Version 17-04-2017 - Mise à jour du 1er trimestre pour Microsoft Flow
* **Expériences d’approbation modernes** : créez des flux de travail où les approbateurs peuvent approuver en toute sécurité à partir de l’application mobile Microsoft Flow ou du centre d’approbations unifié sur le site web Microsoft Flow.
* **Disponibilité générale des flux d’équipes** : plusieurs personnes peuvent posséder et gérer un flux avec les flux d’équipes, maintenant mis à la disposition générale.
* **Créer des connecteurs pour Microsoft Flow** : tout le monde peut soumettre son propre connecteur Microsoft Flow gratuit qui pourra ensuite être utilisé par les utilisateurs du monde entier.
* **Concepteur « allégé »** : pour certains modèles, une nouvelle version du concepteur affiche uniquement les champs qui sont nécessaires pour créer un flux, ce qui simplifie l’expérience.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/q1-2017-update/) sur cette version.

### <a name="release-2017-04-11"></a>Version 11-04-2017
* **Nouvelles actions pour créer des tableaux et des listes** : actions Créer un tableau HTML, Créer un tableau CSV et Joindre qui peuvent traiter des listes d’éléments (au lieu de l’action Apply-to-each précédente).
* **Insertion d’étapes n’importe où** : vous pouvez désormais insérer une nouvelle étape n’importe où dans le flux de travail sans avoir recours au glisser-déposer.
* **Quatre nouveaux services** : Flow prend désormais en charge les API 10 to 8 Scheduling, Act!, Inoreader et Computer Vision. Avec l’API Computer Vision, vous pouvez traiter des images pour obtenir le contenu de texte (procédé appelé OCR) ou appliquer automatiquement une balise aux images en fonction de leur contenu.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sur cette version.

### <a name="release-2017-04-03"></a>Version 03-04-2017
* **Version bêta de Windows Phone** - Le programme bêta de l’application Windows Phone est disponible en aperçu de l’application sur votre Windows Phone. [En savoir plus](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** - Vous pouvez à présent convertir des fichiers Microsoft Word en PDF, ajouter des filigranes, fusionner des documents et bien plus choses encore avec Muhimbi PDF. [En savoir plus](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Déclenchement de flux à partir de boutons physiques** - Annonce de partenariats avec les deux produits principaux dans l’espace physique de boutons : Flic de Shortcut Labs et Bttn de The Button Corporation. [En savoir plus](https://flow.microsoft.com/blog/physical-buttons/).

### <a name="release-2017-03-22"></a>Version 22-03-2017
* **Faites une copie de votre flux** - Vous pouvez dorénavant faire une copie de votre flux dans les versions en mode brouillon ou dupliquer un flux que vous avez créé dans le passé.
* **Deux nouveaux services** - Ajout de la prise en charge de Toodledo pour gérer votre liste des tâches en créant et en mettant à jour des tâches, ainsi que de Zendesk, qui fournit une plateforme de service client et de prise en charge de la gestion des tickets.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/make-a-copy/) sur cette version.

### <a name="release-2017-03-15"></a>Version 15-03-2017
* **Partager des boutons avec des collègues** : vous pouvez à présent partager des boutons de flux avec d’autres personnes, ce qui permet aux utilisateurs de l’entreprise d’effectuer des tâches rapides en toute simplicité.
* **Déclencher des boutons dans l’écran d’accueil** : les raccourcis de boutons de flux situés dans l’écran d’accueil et l’écran de verrouillage des appareils mobiles permettent de déclencher les flux avec une rapidité inédite.
* **Flux d’équipe dans l’application Microsoft Flow** : vous pouvez à présent afficher les flux d’autres propriétaires dans l’application Microsoft Flow pour iOS ou Android.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/button-sharing/) sur cette version.

### <a name="release-2017-03-10"></a>Version 10-03-2017
* **Expérience de connecteur personnalisé améliorée** : vous pouvez à présent utiliser un fichier Postman Collection pour créer un connecteur personnalisé, mais aussi pour modifier, ajouter et tester des actions.
* **Deux nouveaux services** : ajout des notifications PowerApps et de la prise en charge de PivotalTracker.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/new-updates-custom-api/) sur cette version.

### <a name="release-2017-02-27"></a>Version 27-02-2017
* **Déclencher les boutons de flux** : vous pouvez à présent déclencher des boutons de flux directement à partir du site web Microsoft Flow. Dans la fenêtre où figure votre liste de flux, sélectionnez simplement le menu « ... », puis choisissez la commande Exécuter maintenant.
* **Cinq nouveaux services** : ajout de la prise en charge d’Oracle Database, Intercom, FreshBooks, LeanKit et WebMerge.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sur cette version.

### <a name="release-2017-02-21"></a>Version 21-02-2017
* **Afficher les flux d’environnement** : les administrateurs d’environnement peuvent maintenant afficher la liste complète de tous les flux situés à l’intérieur d’un environnement donné, mais aussi activer, désactiver ou supprimer des flux.
* **Deux nouveaux services** : ajout de la prise en charge d’Azure Automation et de Basecamp 2.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sur cette version.

### <a name="release-2017-02-16"></a>Version 16-02-2017
* **Cinq nouveaux services** : ajout de la prise en charge d’Azure Data Lake, Bitbucket (service d’hébergement web pour les projets qui utilisent le contrôle de révision GIT), Eventbrite, Infusionsoft et Pipedrive.
* **Authentification HTTP personnalisée** : dans le concepteur de flux, il est maintenant possible d’utiliser l’authentification avec des points de terminaison HTTP personnalisés.
* **Analyser les messages JSON** : vous pouvez analyser les données JSON du déclencheur de requête HTTP ou celles retournées par l’action HTTP.
* **Filtrage des exécutions de flux** : filtrage amélioré pour les exécutions de flux, avec des options plus spécifiques, notamment l’affichage des flux en cours d’exécution ou des exécutions annulées.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sur cette version.

### <a name="release-2017-02-06"></a>Version 06-02-2017
* **Flux d’équipes** : les flux d’équipes permettent à plusieurs personnes en même temps de posséder et de gérer un flux. Par ailleurs, si une personne quitte une organisation, les flux qu’elle a créés peuvent continuer à fonctionner.
* **Partage des connecteurs personnalisés** : les connecteurs personnalisés, tels que les flux d’équipes, peuvent être partagés et gérés collectivement à l’intérieur d’une organisation.
* **Prise en charge de Gmail et LUIS** : connectez-vous à Gmail et au service LUIS (Language Understanding Intelligent Service) d’Azure Cognitive Services.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/team-flows/) sur cette version.

### <a name="release-2017-01-30"></a>Version 30-01-2017
* **Entrées des boutons de flux** : les boutons de flux peuvent maintenant recevoir des entrées utilisateur au moment de l’exécution. Ainsi, les auteurs du flux peuvent définir les informations qui sont transmises quand l’utilisateur appuie sur le bouton.
* **Tâches Outlook et HelloSign** : le service Tâches Outlook vous permet de gérer des tâches et HelloSign autorise les signatures électroniques sécurisées.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/button-user-inputs/) sur cette version.

### <a name="release-2017-01-23"></a>Version 23-01-2017
* **Recherche par service** : filtrez par service lorsque vous ajoutez un déclencheur ou une action pour afficher toutes les actions pour chaque service.
* **Casse de commutateur** : ajoutez des blocs de commutateur pour avoir plusieurs branches d’une logique parallèle.
* **Nouvelles actions de messagerie** : nouvelles fonctionnalités des services Office 365 Outlook et Outlook.com permettant d’utiliser des e-mails marqués.
* **Cinq nouveaux services** : connectez-vous aux systèmes de gestion de fichiers en réseau ou locaux, au service de paiement Stripe, à IBM Informix, à IBM DB2 et à UserVoice.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/search-by-service/) sur cette version.

### <a name="release-2017-01-14"></a>Version 14-01-2017
* **Soumettre à nouveau les exécutions** : si un flux échoue et que vous souhaitez tenter de résoudre le problème et relancer l’exécution, vous pouvez soumettre à nouveau l’exécution ayant échoué.
* **Annuler les exécutions** : quand un flux reste bloqué, vous pouvez maintenant explicitement annuler son exécution.
* **Deux nouveaux services** : ajout de la prise en charge de GoToTraining et GoToWebinar.
* **Liens mobiles** : vous pouvez partager des modèles directement à partir de l’application mobile. Nous avons par ailleurs ajouté un lien de téléchargement rapide pour les applications en haut du site web.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/managing-runs/) sur cette version.

### <a name="release-2016-12-29"></a>Version 29-12-2016
Microsoft Flow prend maintenant en charge DocuSign, qui permet de gérer les signatures électroniques et les transactions numériques, SurveyMonkey (pour les enquêtes sur le web) et l’application de prise de notes OneNote (comptes d’entreprise uniquement).

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/final-2016-services/) sur cette version.

### <a name="release-2016-12-20"></a>Version 20-12-2016
* **Exécuter maintenant** : vous pouvez maintenant déclencher un déclencheur récurrent à la demande. Par exemple, si vous avez un rapport planifié chaque jour, mais que vous devez exécuter le rapport **maintenant**.
* **Six nouveaux services** : générez des flux qui se connectent à MSN Météo, Medium, Google Contacts, Buffer, Harvest et TypeForm.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sur cette version.

### <a name="release-2016-12-14"></a>Version 14-12-2016
Vous pouvez maintenant tirer parti d’informations précieuses lors du déclenchement d’un flux de bouton, par exemple à partir d’où le bouton est déclenché, par qui, à quel moment, etc.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/button-trigger-tokens/) sur cette version.

### <a name="release-2016-12-06"></a>Version 06-12-2016
* **Présentation de la formation guidée** : commencez avec une collection ordonnée de cours associés à des vidéos et de la documentation pour vous aider à comprendre les fonctionnalités complètes et puissantes de Microsoft Flow.
* **Deux nouveaux services** : les flux peuvent maintenant utiliser Freshdesk, une solution de support client et GoToMeeting, un outil de réunion en ligne.
* **Prise en charge des webhook HTTP** : un flux peut être un point de terminaison pour webhook qui s’inscrit ou se désinscrit automatiquement.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sur cette version.

### <a name="release-2016-11-23"></a>Version 23-11-2016
* **Prise en charge des alertes Power BI dans Flow** : transformez les insights en action en déclenchant des flux à partir d’alertes de données Power BI.
* **Améliorations apportées à l’application mobile** : il est à présent possible de créer entièrement des flux en plus d’en créer à partir de modèles. Nous avons également amélioré les performances lors de l’affichage des exécutions de flux.
* **Huit nouveaux services** : vous pouvez à présent vous connecter à Azure Resource Manager, Files d’attente Azure, Chatter, Disqus, Azure DocumentDB, l’API Visage Cognitive Services, HipChat et Wordpress.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sur cette version.

### <a name="release-2016-11-15"></a>Version 15-11-2016
* **Programme pour partenaires Microsoft Flow** : Microsoft Flow a maintenant un programme de partenaires certifié pour établir des connexions et tirer parti des différentes compétences et expériences d’entreprise avec Microsoft Flow dans le monde entier.
* **Six nouveaux services** : nous avons également publié six services cette semaine : Asana, Campfire, EasyRedmine, JIRA, Redmine et Vimeo.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/partner-program-six-new-services/) sur cette version.

### <a name="release-2016-10-31---general-availability"></a>Version 31-10-2016 - Disponibilité générale
* **Tarifs et licences** : maintenant disponible dans les offres gratuites et payantes et inclus dans Office 365 et Dynamics 365.
* **Centre d’administration Microsoft Flow** : prêt pour les entreprises grâce au nouveau centre d’administration. Le centre d’administration permet de gérer les environnements au sein de l’organisation.
* **Stratégies de protection contre la perte de données** : les administrateurs peuvent créer des stratégies de protection contre la perte de données pour contrôler le flux de données entre services.
* **Disponibilité Android** : l’application de téléphone Microsoft Flow est désormais disponible pour iOS et Android. Elle permet d’obtenir des notifications, de surveiller l’activité et de démarrer des flux en appuyant simplement sur un bouton.
* **Nouvelles expériences au sein du concepteur** : vous pouvez maintenant réaliser des recherches dans le contenu dynamique transmis d’étape en étape, ce qui simplifie le référencement des données souhaitées.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/announcing-ga/) sur cette version.

### <a name="release-2016-10-26"></a>Version 26-10-2016
* **Flux de bouton** : il existe un nombre incalculable d’opérations que nous souhaiterions pouvoir déclencher à tout moment et en tout lieu. Grâce aux flux de bouton, cela est désormais possible en appuyant simplement sur un bouton sur votre appareil mobile.
* **Annonce des environnements** : les environnements sont des espaces distincts de stockage et de gestion des flux de votre organisation. Les environnements sont géolocalisés, ce qui signifie que les flux, les applications et les données d’entreprise qui se trouvent dans un environnement sont stockés dans la région où se trouve l’environnement.
* **6 nouveaux services** : ajout de la prise en charge de Bit.ly, de l’analyse de texte Cognitive Services, de Dynamics NAV, de Dynamics 365 for Financials, d’Instapaper et de Pinterest.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/environments-for-makers/) sur cette version.

### <a name="release-2016-10-16"></a>Version 16-10-2016
* **Les connecteurs personnalisés prennent en charge davantage de types d’authentification** : ils prennent maintenant en charge l’authentification par clé d’API et peuvent s’authentifier via un service qui prend en charge la spécification complète OAuth 2.0.
* **Trois nouveaux services pris en charge** - Nous avons ajouté la prise en charge pour Basecamp 3, Blogger et PagerDuty.
* **Améliorations du concepteur** - Bénéficiez de performances optimisées. Vous pouvez désormais mettre à jour et réparer vos connexions directement à partir du menu « ... », et nous avons par ailleurs ajouté une nouvelle étape, Terminer, à utiliser pour mettre un terme à un flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/early-october-updates/) sur cette version.

### <a name="release-2016-09-25"></a>Version 25-09-2016
Vous pouvez désormais créer des flux à partir de vos téléphones mobiles. Parcourez notre riche galerie de modèles, consultez notre liste de services ou sélectionnez une catégorie de modèles à analyser. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/mobile-creation/) sur cette version.

### <a name="release-2016-09-22"></a>Version 22-09-2016
* **Sélectionneur de contacts Microsoft Graph** - Un nouveau sélectionneur de contacts Microsoft Graph est directement intégré dans l’interface utilisateur Microsoft Flow afin de vous aider à sélectionner le contact ou l’adresse de messagerie appropriés.
* **Prise en charge Microsoft Dynamics AX** - Depuis vos flux, vous pouvez désormais agir sur vos données opérationnelles Dynamics AX Online, par exemple en créant de nouveaux enregistrements ou en recherchant des données.
* **Deux nouveaux services des partenaires** - Utilisez désormais appFigures ou Insightly à partir de vos flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/more-september-updates/) sur cette version.

### <a name="release-2016-09-14"></a>Version 14-09-2016
* **Intégration dans votre site web ou votre application** - Les développeurs peuvent désormais intégrer Microsoft Flow dans leurs applications ou leurs sites web afin d’octroyer aux utilisateurs un moyen simple d’automatiser leurs tâches personnelles ou professionnelles.
* **Utilisez un flux comme point de terminaison HTTP** - Vous pouvez désormais utiliser un flux en tant qu’API HTTP. Un déclencheur appelé Request est intégré dans le flux, et vous pouvez décider de répondre à la requête entrante en ajoutant une carte de réponse.
* **Prise en charge Todoist** - Todoist vous procure une perspective sur l’ensemble de vos projets, à domicile comme au travail.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/extend-web-site-application/) sur cette version.

### <a name="release-2016-09-01"></a>Version 01-09-2016
Microsoft Flow est désormais accessible par l’ensemble des utilisateurs. Initialement, nous avions ouvert la version d’évaluation uniquement aux adresses électroniques fournies par votre entreprise ou votre établissement, comme celles utilisées avec Office 365 Business ou Office 365 Enterprise. Aujourd’hui, nous annonçons que la version d’évaluation est officiellement disponible gratuitement pour l’ensemble des utilisateurs, quelle que soit l’adresse électronique utilisée. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/available-for-everyone/) sur cette version.

### <a name="release-2016-08-31"></a>Version 31-08-2016
* **Conditions imbriquées** - Vous pouvez désormais ajouter une deuxième (ou une troisième) condition à l’intérieur d’une autre instance.
* **Apply to each** -  Une boucle apply-to-each permet de contrôler la liste répétée.
* **Do-until** - Une boucle do-until vous permet de répéter une étape jusqu’à ce qu’une condition spécifique soit satisfaite.
* **Réseaux de filtres** - Une phase unique de filtrage natif vous permet de garantir que l’ensemble des éléments de la liste correspondent à l’expression définie.
* **Composition de variables de chaîne** - Vous pouvez désormais composer une variable de chaîne.
* **Étendues** - Les étendues sont un moyen simple de regrouper deux ou plusieurs actions.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/build-advanced-flows/) sur cette version.

### <a name="release-2016-08-27"></a>Version 27-08-2016
* **Commentaires sur les étapes** - Les commentaires permettent d’annoter simplement chaque action, de manière à retenir facilement les besoins de votre flux.
* **Prise en charge Smartsheet** - Cette semaine, nous avons ajouté la prise en charge de la connexion à Smartsheet. Smartsheet est un service qui facilite la collaboration sur des feuilles dans le cloud.
* **Améliorations de l’interface utilisateur lors de la création des flux** - Pour un accès simplifié, nous avons également déplacé le nom du flux au premier plan et le bouton d’enregistrement sur la partie supérieure de la page.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/add-comments-smartsheet/) sur cette version.

### <a name="release-2016-08-18"></a>Version 18-08-2016
Vous pouvez désormais afficher un aperçu de la nouvelle expérience de listes modernes SharePoint Online, qui inclut l’intégration Microsoft Flow. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sur cette version.

### <a name="release-2016-08-13"></a>Version 13-08-2016
* **Visual Studio Team Services** - Avec Microsoft Flow, vous pouvez désormais connecter VSTS à un large éventail de services comme O365 Email, Slack, Trello, et Wunderlist.
* **Améliorations apportées à SharePoint** - Les listes SharePoint prennent en charge une gamme élargie de types de données, des objets simples comme les lignes de texte et les informations de date et d’heures aux objets complexes, comme les individus ou les groupes, la recherche et la sélection.
* **Testez les connexions O365 Outlook** - Quand vous créez une nouvelle connexion O365 Outlook, nous vérifions que vous pouvez l’utiliser.
* **Contrôle booléen** - Nous avons également ajouté un contrôle booléen afin d’apporter une clarification sur les valeurs à saisir dans les champs de saisie booléens, comme dans celui indiquant les pièces jointes du déclencheur d’arrivée des nouveaux e-mails.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sur cette version.

### <a name="release-2016-08-08"></a>Version 08-08-2016
Version d’évaluation publique du service Microsoft Common Data Service intégré à Microsoft Flow. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/flow-and-common-data-model/) sur cette version.

### <a name="release-2016-08-05"></a>Version 05-08-2016
* **SharePoint On-Premises** - Tout comme avec SharePoint Online, vous pouvez créer des flux autour de vos listes SharePoint locales et de vos bibliothèques documentaires à l’aide de modèles pré-définis ; vous pouvez également les créer entièrement.
* **Info-bulles dans le concepteur** - Afin de développer les capacités de chaque déclencheur et action, nous avons ajouté des info-bulles au-dessus de chacune des étapes de votre flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sur cette version.

### <a name="release-2016-07-15"></a>Version 15-07-2016
* **Quatre nouveaux services ajoutés** - Connectez-vous à Google Agenda, à Google Tasks, à YouTube et à SparkPost.
* **Renommez vos actions** - Désormais, vous pouvez distinguer ces différentes actions en les renommant.
* **Définissez différents délais** - Vous pouvez dès maintenant définir des délais en secondes, en minutes ou en jours.
* **Simplicité d’utilisation du navigateur de dossiers** - Nous avons simplifié le navigateur de dossiers. Effectuez une sélection sur la gauche pour choisir ce dossier, et sur la droite pour l’ouvrir et spécifier des sous-dossiers.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/new-google-services-rename-more/) sur cette version.

### <a name="release-2016-07-08"></a>Version 08-07-2016
Connectivité locale pour Microsoft Flow à l’aide de la passerelle locale de données. Cette fonctionnalité vous permet d’établir des connexions sécurisées à SQL Server et de les intégrer à vos flux. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/on-premises-data-gateway/) sur cette version.

### <a name="release-2016-07-02"></a>Version 02-07-2016
* **Prise en charge de Google Sheets** - Par le passé, il était possible d’utiliser Excel, tout comme Google Drive, mais nous ajoutons cette semaine la prise en charge native de Google Sheets.
* **Démarrez plus rapidement à partir des modèles** - Nous avons également apporté des améliorations au mode de démarrage à partir des modèles. Désormais, vous pouvez sélectionner les comptes que vous souhaitez utiliser pour un modèle en ligne, sur la page du modèle.
* **Aucune autorisation arrivant à expiration pour SharePoint et Office 365** - Désormais, Microsoft Flow renouvelle automatiquement votre accès aux services basés sur Microsoft Azure Active Directory, de manière à ce que l’ensemble de vos flux demeurent utilisables après les modifications de mot de passe.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/more-june-updates/) sur cette version.

### <a name="release-2016-06-20"></a>Version 20-06-2016
* **Présentation de la nouvelle application mobile pour Microsoft Flow** - Aujourd’hui, nous sommes heureux de lancer une nouvelle composante majeure de notre offre : une application mobile disponible au téléchargement sur iOS (bientôt également sur Android) qui vous donne les moyens de gérer, d’effectuer le suivi de vos workflows et de les explorer à tout moment, en tout lieu.  
* **Authentification unique** - Nous avons implémenté l’authentification unique, grâce à laquelle vous vous connectez à Microsoft Flow avec d’autres services Microsoft, comme Office 365.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sur cette version.

### <a name="release-2016-06-18"></a>Version 18-06-2016
* **Nouveau service de messagerie** - Vous pouvez désormais envoyer directement des e-mails depuis Microsoft Flow, sans avoir à vous connecter à vos comptes de messagerie personnels ou professionnels dans Microsoft Flow.
* **Notifications dans le portail** - Désormais, les notifications s’affichent dans la partie supérieure du portail si des dysfonctionnements sont identifiés dans vos flux.
* **Toute l’activité dans le portail** - Vous pouvez désormais avoir des informations sur l’activité de l’ensemble de vos flux. Pour ce faire, cliquez sur le nouvel onglet Activité du site web consacré aux flux.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/mail-and-all-activity/) sur cette version.

### <a name="release-2016-05-27"></a>Version 27-05-2016
* **Parcourez les modèles par service** - Vous avez maintenant la possibilité de consulter l’ensemble des services pris en charge (sans avoir à vous connecter). À partir de cette page, vous avez accès à une description de l’ensemble des services et pouvez consulter les modèles associés à ce service.
* **Créer et utiliser vos connecteurs personnalisés** : tout comme il est possible de créer des connecteurs personnalisés dans PowerApps, vous pouvez également vous connecter à vos propres API depuis flow.microsoft.com :
* **Testez vos flux avant de terminer** - Quand vous enregistrez un flux, vous pouvez afficher les résultats en temps réel de l’exécution associée, si vous exécutez l’action de démarrage.

[Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sur cette version.

### <a name="release-2016-05-07"></a>Version 07-05-2016
Ajout de deux nouveaux services : Microsoft Project Online et Mandrill par Mailchimp. [Découvrez davantage de ressources et posez des questions](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sur cette version.

### <a name="release-2016-04-27---public-preview"></a>Version 27-04-2016 - Version préliminaire publique
Si vous avez utilisé des flux logiques dans le cadre de [Microsoft PowerApps](https://powerapps.microsoft.com), la version préliminaire de Microsoft Flow propose plusieurs nouvelles fonctionnalités :

* Vous pouvez maintenant parcourir une galerie composée de dizaines de modèles et effectuer un tri par popularité, nom ou date de publication.
* Vous pouvez [publier vos propres modèles](publish-a-template.md) dans la galerie une fois que vous avez personnalisé un flux.
* Vous pouvez consulter l’historique de chacune des vérifications et exécutions de votre flux.
* Lorsque vous enregistrez un flux, vous pouvez [le voir en action immédiatement](see-a-flow-run.md) en effectuant simplement l’action de déclencheur.
* Nous avons une [nouvelle communauté](https://go.microsoft.com/fwlink/?LinkID=787467) dans laquelle vous pouvez discuter de Microsoft Flow ou [soumettre vos idées](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Étapes suivantes
Si vous rencontrez des problèmes qui ne sont pas encore traités dans ces notes de publication ou dans le [Forum Aux Questions](frequently-asked-questions.md), [rejoignez notre communauté](https://go.microsoft.com/fwlink/?LinkID=787467) pour poser des questions ou [contactez le support technique](http://go.microsoft.com/fwlink/?LinkID=787479).

