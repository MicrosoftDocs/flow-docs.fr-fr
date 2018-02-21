---
title: "Créer une chaîne d’approbation avec Common Data Service | Microsoft Docs"
description: "Créez une entité, un flux et une application qui fonctionnent ensemble afin que les réviseurs puissent approuver ou rejeter des fichiers ajoutés à Dropbox."
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
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: f56b109cc0263c8464d6d7475421ab32af8888d5
ms.sourcegitcommit: f3261717768177e03e825c0dd2e3ba736dc9b94d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2018
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Créer une chaîne d’approbation avec Microsoft Flow et le service Common Data Service de Microsoft
Le service Common Data Service vous permet de générer des flux qui comportent des informations stockées dans une base de données indépendante d’un flux. Les approbations en sont le meilleur exemple. Si vous stockez l’état de l’approbation dans une entité, votre flux peut fonctionner par-dessus.

Dans cet exemple, vous allez créer un processus d’approbation qui démarre lorsqu’un utilisateur ajoute un fichier à Dropbox. Lorsque le fichier est ajouté, les informations associées s’affichent dans une application, dans laquelle un réviseur peut approuver ou rejeter la modification. Lorsque le réviseur approuve ou rejette la modification, un message de notification est envoyé et les fichiers refusés sont supprimés de Dropbox.

En suivant les étapes décrites dans cette section, vous allez créer :

* Une **entité personnalisée** qui contient des informations sur chaque fichier ajouté à Dropbox et qui indique si l’état du fichier est approuvé, rejeté ou en attente.
* Un **flux** qui ajoute des informations à l’entité personnalisée lorsqu’un fichier est ajouté à Dropbox, envoie un message lorsque le fichier est approuvé ou rejeté et supprime les fichiers rejetés. Ces étapes montrent comment générer un flux de ce type à partir de zéro, mais vous pouvez créer un flux similaire à partir d’un modèle.
* Une **application** dans laquelle un réviseur peut approuver ou rejeter les fichiers ajoutés à Dropbox. Vous allez utiliser PowerApps pour générer cette application automatiquement selon les champs de l’entité personnalisée.

**Conditions préalables**

* Inscrivez-vous à [Microsoft Flow](sign-up-sign-in.md) et [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Créez des connexions à Dropbox et Office 365 Outlook en suivant les instructions de la page [Gérer vos connexions](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>Créer l’entité
1. Connectez-vous à [powerapps.com](https://web.powerapps.com).
2. Si la barre de navigation gauche n’apparaît pas par défaut, cliquez ou appuyez sur l’icône représentant trois lignes horizontales dans le coin supérieur gauche.
   
    ![Barre de navigation gauche ouverte](./media/common-data-model-approve/hamburger-icon.png)
3. Dans la barre de navigation gauche, cliquez ou appuyez sur **Gérer**, puis sur **Entités**.
   
    ![Gérer les entités](./media/common-data-model-approve/manage-entities.png)
4. Si vous y êtes invité, cliquez ou appuyez sur **Créer ma base de données**.
   
    ![Créer la base de données](./media/common-data-model-approve/create-database.png)
5. Près de l’angle supérieur droit, cliquez ou appuyez sur **Nouvelle entité**.
   
    ![Créer une entité](./media/common-data-model-approve/new-entity.png)
   
    Si votre fenêtre de navigateur est réduite, ce bouton peut apparaître dans un autre emplacement.
6. Sous **Nom de l’entité**, spécifiez un nom sans espace et qui n’est pas déjà utilisé par d’autres entités de votre base de données.
   
    Pour suivre cet exemple exactement, spécifiez **RéviserFichiersDropbox**.
   
    ![Spécifier le nom de l’entité](./media/common-data-model-approve/entity-name.png)
7. Sous **Nom d’affichage**, spécifiez un nom convivial.
   
    ![Spécifier le nom d’affichage](./media/common-data-model-approve/display-name.png)
8. Cliquez ou appuyez sur **Suivant**.
   
    ![Bouton Suivant](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Ajouter des champs à l’entité
1. Près de l’angle supérieur droit, cliquez ou appuyez sur **Ajouter un champ**.
   
    ![Ajouter un champ](./media/common-data-model-approve/add-field.png)
2. Dans la ligne vide qui apparaît en bas de la liste des champs, définissez les propriétés d’un champ **Approbateur**. (Lorsque vous définissez ces propriétés, vous pouvez basculer vers la colonne suivante en appuyant sur la touche Tabulation.)
   
   * Dans la colonne **Nom d’affichage**, entrez **Approbateur**.
   * Dans la colonne **Nom**, entrez **Email_Approbateur**.
   * Dans la colonne **Type**, cliquez ou appuyez sur l’option **Email**.
   * Dans la colonne **Obligatoire**, activez la case à cocher.
     
     ![Champ Approbateur](./media/common-data-model-approve/approver-field.png)
3. Dans la ligne suivante, définissez les propriétés d’un champ **État** :
   
   * Dans la colonne **Nom d’affichage**, entrez **État**.
   * Dans la colonne **Nom**, entrez **État**.
   * Dans la colonne **Type**, cliquez ou appuyez sur l’option **Text**.
   * Dans la colonne **Propriétés**, laissez la valeur par défaut.
   * Dans la colonne **Obligatoire**, activez la case à cocher.
     
     ![Champ État](./media/common-data-model-approve/status-field.png)
4. Dans la ligne suivante, définissez les propriétés d’un champ **ID fichier** :
   
   * Dans la colonne **Nom d’affichage**, entrez **Identificateur de fichier**.
   * Dans la colonne **Nom**, entrez **ID fichier**.
   * Dans la colonne **Type**, cliquez ou appuyez sur l’option **Text**.
   * Dans la colonne **Propriétés**, laissez la valeur par défaut.
   * Dans la colonne **Unique**, activez la case à cocher.
   * Dans la colonne **Obligatoire**, activez la case à cocher.
     
     ![Champ ID fichier](./media/common-data-model-approve/fileid-field.png)
5. Près du bord droit, cliquez ou appuyez sur le bouton de sélection (...) du champ **ID fichier**, puis cliquez ou appuyez sur **Définir comme champ de titre**.
   
    ![Définir comme champ de titre](./media/common-data-model-approve/set-title-field.png)
6. Près de l’angle inférieur gauche, cliquez ou appuyez sur **Créer**.
   
    ![Créer une entité](./media/common-data-model-approve/create-button.png)
7. (facultatif) Lorsque la liste des entités réapparaît, agrandissez la fenêtre du navigateur si elle est réduite, puis cliquez ou appuyez sur l’en-tête de colonne **Type**. La liste est triée et les entités personnalisées, comme celle que vous venez de créer, apparaissent en haut.

## <a name="sign-in-and-create-a-flow"></a>Se connecter et créer un flux
1. Ouvrez le [portail Microsoft Flow](https://flow.microsoft.com).
2. Agrandissez la fenêtre du navigateur si elle est réduite, puis cliquez ou appuyez sur **Se connecter** près du coin supérieur droit.
   
    ![Bouton Se connecter pour Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. Dans le menu en haut à droite, vous sélectionnez l’environnement dans lequel vous avez créé la base de données dans powerapps.com.
   
    **Remarque** : si vous ne sélectionnez pas le même environnement, vous ne verrez pas votre entité.
4. Près de l’angle supérieur gauche, cliquez ou appuyez sur **Mes flux**.
   
    ![Bouton Mes flux](./media/common-data-model-approve/myflows-button.png)
5. Près de l’angle supérieur droit, cliquez ou appuyez sur **Créer entièrement**.
   
    ![Bouton Créer un flux](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Démarrer lorsqu’un fichier est ajouté
1. Dans la zone qui contient **Rechercher d’autres déclencheurs**, tapez ou collez **Dropbox**, puis cliquez ou appuyez sur **Dropbox - Lorsqu’un fichier est créé**.
   
    ![Créer le déclencheur](./media/common-data-model-approve/create-trigger.png)
2. Sous **Dossier**, cliquez ou appuyez sur l’icône en forme de dossier, puis accédez au dossier où les fichiers seront ajoutés.
   
    ![Choisir le dossier](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Ajouter des données à l’entité
1. Cliquez ou appuyez sur **Nouvelle étape**, puis sur **Ajouter une action**.
   
    ![Ajouter une action](./media/common-data-model-approve/add-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Common Data Service**, puis cliquez ou appuyez sur **Common Data Service - Create object** (Common Data Service - Créer un objet).
   
    ![Créer un objet dans le service Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Sous **Entité**, tapez ou collez **Révision**, puis cliquez ou appuyez sur **Réviser les fichiers Dropbox**.
   
    ![Choisir l’entité](./media/common-data-model-approve/choose-entity-flow.png)
4. Sous **Titre**, cliquez ou appuyez dans la zone, puis sur **Nom de fichier** dans la liste de jetons de paramètre pour ajouter ce jeton au champ.
   
    ![Ajouter le jeton de nom de fichier](./media/common-data-model-approve/add-filename-token.png)
5. Sous **Approbateur**, tapez ou collez l’adresse de messagerie de la personne qui révisera les fichiers.
   
    **Remarque** : pour faciliter le test du flux, spécifiez votre propre adresse. Vous pourrez la modifier ultérieurement lorsque le flux sera prêt pour une utilisation réelle.
   
    ![Ajouter un approbateur](./media/common-data-model-approve/add-approver.png)
6. Sous **État**, tapez ou collez **En attente**.
   
    ![Ajouter l’état par défaut](./media/common-data-model-approve/add-default-status.png)
7. Sous **Identificateur de fichier**, cliquez ou appuyez dans la zone, puis sur **Identificateur de fichier** dans la liste de jetons de paramètre pour ajouter ce jeton au champ.
   
    ![Ajouter le jeton d’identificateur de fichier](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Vérifier si le fichier a été révisé
1. Sous l’action **Créer un objet**, cliquez ou appuyez sur **Nouvelle étape**, sur **Plus**, puis sur **Ajouter un do until**.
   
    ![Ajouter un do until](./media/common-data-model-approve/add-do-until.png)
2. Dans le coin supérieur gauche de l’action **Do until**, cliquez ou appuyez dans la zone contenant **Choisir une valeur**.
   
    ![Choisir une valeur](./media/common-data-model-approve/choose-value.png)
   
    **Remarque** : si votre navigateur n’est pas agrandi au maximum, cliquez ou appuyez dans la zone supérieure contenant **Choisir une valeur**.
3. Sous **Sorties de Créer un objet**, cliquez ou appuyez sur **État** pour ajouter le jeton de paramètre au champ.
   
    ![Ajouter le jeton d’état](./media/common-data-model-approve/add-status.png)
4. Ouvrez la liste près du centre de l’action **Do until**, puis cliquez ou appuyez sur **N’est pas égal à**.
   
    ![Spécifiez n’est pas égal à](./media/common-data-model-approve/is-not-equal.png)
5. Dans le coin supérieur droit de l’action **Do until**, tapez ou collez **En attente** dans la zone contenant **Choisir une valeur**.
   
    ![Spécifier l’état à surveiller](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Remarque** : si votre navigateur n’est pas agrandi au maximum, cliquez ou appuyez dans la zone inférieure contenant **Choisir une valeur**.
6. Près du bas de l’action **Do until**, cliquez ou appuyez sur **Ajouter une action**.
   
    ![Ajouter une action dans un Do until](./media/common-data-model-approve/add-action-in-dountil.png)
7. Dans la zone qui contient **Rechercher d’autres actions**, tapez **Common**, puis cliquez ou appuyez sur **Common Data Service - Get object** (Common Data Service - Obtenir un objet).
   
    ![Obtenir un objet](./media/common-data-model-approve/get-object.png)
8. Sous **Espace de noms**, cliquez ou appuyez sur votre base de données.
9. Sous **Entité**, tapez ou collez **Révision**, puis cliquez ou appuyez sur **Réviser les fichiers Dropbox**.
   
    ![Choisir une entité](./media/common-data-model-approve/choose-entity-flow.png)
10. Sous **ID d’objet**, cliquez ou appuyez dans la zone, puis sur le jeton de paramètre **Identificateur de fichier** pour l’ajouter au champ.
    
     ![Ajouter l’identificateur d’objet](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Vérifier si l’élément a été approuvé
1. Sous l’action **Do until**, cliquez ou appuyez sur **Nouvelle étape**, puis sur **Ajouter une condition**.
   
    ![Ajouter une condition](./media/common-data-model-approve/add-condition.png)
2. Dans le coin supérieur gauche de la condition, cliquez ou appuyez dans la zone contenant **Choisir une valeur**.
   
    ![Angle supérieur gauche de la condition](./media/common-data-model-approve/condition-upper-left.png)
   
    **Remarque** : si votre navigateur n’est pas agrandi au maximum, cliquez ou appuyez dans la zone supérieure contenant **Choisir une valeur**.
3. Sous **Sorties de Obtenir un objet**, cliquez ou appuyez sur le jeton de paramètre **État** pour l’ajouter au champ.
   
    ![Ajouter un état à la condition](./media/common-data-model-approve/add-status-to-condition.png)
4. Dans le coin supérieur droit de la condition, tapez ou collez **Approuvé** dans la zone contenant **Choisir une valeur**.
   
    ![Vérifier si l’état est défini sur Approuvé](./media/common-data-model-approve/status-equals-approved.png)
   
    **Remarque** : si votre navigateur n’est pas agrandi au maximum, tapez ou collez **Approuvé** dans la zone inférieure contenant **Choisir une valeur**

## <a name="send-notification-mail"></a>Envoyer un courrier électronique de notification
1. Sous **Si oui, ne rien faire**, cliquez ou appuyez sur **Ajouter une action**.
   
    ![Si oui, ajouter une action](./media/common-data-model-approve/if-yes-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Envoyer un message électronique**, puis cliquez ou appuyez sur **Office 365 Outlook - Envoyer un message électronique**.
   
    ![Si oui, envoyer un message](./media/common-data-model-approve/if-yes-send-mail.png)
3. Sous **À**, tapez ou collez l’adresse de la personne que vous souhaitez notifier lorsqu’un élément est accepté.
   
    **Remarque** : pour faciliter le test du flux, spécifiez votre propre adresse. Vous pouvez la modifier lorsque le flux est prêt pour une utilisation réelle.
   
    ![Destinataire de l’approbation](./media/common-data-model-approve/approval-recipient.png)
4. Sous **Objet**, cliquez ou appuyez dans la zone, puis sur le jeton de paramètre **Nom de fichier** pour l’ajouter au champ.
   
    ![Spécifier le nom de fichier en tant qu’objet du message électronique](./media/common-data-model-approve/subject-is-file-name.png)
5. Sous **Corps**, tapez ou collez **L’élément a été approuvé**.
   
    ![Corps du courrier d’approbation](./media/common-data-model-approve/approval-body.png)
6. Sous **Si non, ne rien faire**, répétez les étapes 1 à 5 de cette procédure, mais définissez le corps du message électronique sur **L’élément a été rejeté**.
   
    ![Corps du message de rejet](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Supprimer les fichiers rejetés
1. Sous les champs du message de refus, cliquez ou appuyez sur **Ajouter une action**.
   
    ![Ajouter une action de suppression](./media/common-data-model-approve/add-delete-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Dropbox**, puis cliquez ou appuyez sur **Dropbox - Supprimer le fichier**.
   
    ![Supprimer le fichier de Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Sous **Fichier**, cliquez ou appuyez dans la zone, puis sur le paramètre de jeton **Identificateur de fichier** pour l’ajouter au champ.
   
    ![Identifier le fichier à supprimer](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Enregistrer le flux
1. En haut de l’écran, tapez ou collez un nom pour le flux que vous créez, puis cliquez ou appuyez sur **Créer un flux**.
   
    ![Enregistrer le flux](./media/common-data-model-approve/save-flow.png)
2. Cliquez ou appuyez sur **Fermer**, puis sur **Terminé**.
3. Dans Dropbox, ajoutez au moins deux fichiers au dossier que vous avez spécifié : un pour tester l’approbation et l’autre pour tester le rejet.

## <a name="build-the-app"></a>Créer l’application
1. Connectez-vous à [powerapps.com](https://web.powerapps.com), puis cliquez ou appuyez sur **Nouvelle application** vers le bas de la barre de navigation gauche.
   
    ![Créer une application dans un navigateur](./media/common-data-model-approve/new-app-button.png)
2. Dans la boîte de dialogue qui s’affiche, cliquez ou appuyez sur l’option pour ouvrir PowerApps Studio pour Windows ou PowerApps Studio pour le web.
3. Si vous avez ouvert PowerApps Studio pour Windows, cliquez ou appuyez sur **Nouveau** dans la barre de navigation gauche.
4. Sous **Créer une application à partir de vos données**, cliquez ou appuyez sur **Mode téléphone** dans la vignette **Common Data Service**.
   
    ![Créer une application](./media/common-data-model-approve/afd-cdm.png)
5. Dans la zone **Recherche**, tapez ou collez **Révision**.
   
    ![Rechercher une entité](./media/common-data-model-approve/search-entities.png)
6. Sous **Choisir une entité**, cliquez ou appuyez sur **Réviser les fichiers Dropbox**.
   
    ![Choisir une entité](./media/common-data-model-approve/choose-entity.png)
7. Près de l’angle inférieur droit, cliquez ou appuyez sur **Se connecter**.
   
    ![Bouton de connexion](./media/common-data-model-approve/connect-button.png)
8. Si l’écran d’ouverture de la visite guidée d’introduction apparaît, suivez la visite guidée afin de vous familiariser avec PowerApps (ou cliquez ou appuyez sur **Ignorer**).
   
    ![Visite guidée d’introduction](./media/common-data-model-approve/quick-tour.png)
   
    Vous pourrez toujours suivre la visite guidée ultérieurement en cliquant ou en appuyant sur l’icône en forme de point d’interrogation dans l’angle supérieur gauche, puis sur **Suivre la visite guidée d’introduction**.
9. (facultatif) Au bas de l’écran, faites glisser le curseur pour augmenter le zoom pour mieux voir l’application.
   
    ![Contrôle de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personnaliser l’application
1. Dans la barre de navigation de droite, cliquez ou appuyez sur la mise en page qui comporte un en-tête et une description.
   
    ![Bouton de connexion](./media/common-data-model-approve/choose-layout.png)
2. Sur l’**écran Parcourir**, cliquez ou appuyez juste en dessous de la barre de recherche pour sélectionner le contrôle de zone de texte le plus grand.
   
    ![Sélectionner un en-tête](./media/common-data-model-approve/select-header.png)
3. Dans le volet de droite, ouvrez la liste inférieure en cliquant ou en appuyant sur la flèche vers le bas.
   
    ![Ouvrir le menu déroulant](./media/common-data-model-approve/open-dropdown.png)
4. Dans la liste inférieure, cliquez ou appuyez sur **Titre** de façon à afficher le nom des fichiers ajoutés.
   
    ![Définir les données d’en-tête](./media/common-data-model-approve/set-heading.png)
5. Dans le volet de droite, ouvrez la liste supérieure, puis cliquez ou appuyez sur **État** pour afficher l’état de chaque fichier.
   
    ![Définir les données du corps](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Tester la solution globale
1. Dans PowerApps, ouvrez le mode Aperçu en cliquant ou en appuyant sur le bouton de lecture dans le coin supérieur gauche.
   
    ![Ouvrir le mode Aperçu](./media/common-data-model-approve/open-preview.png)
2. Pour le premier fichier de la liste, cliquez ou appuyez sur la flèche pour afficher les détails associés.
   
    ![Ouvrir l’écran Détails](./media/common-data-model-approve/open-details.png)
3. Dans le coin supérieur droit, cliquez ou appuyez sur l’icône en forme de crayon pour modifier les informations du fichier.
   
    ![Ouvrir l’écran Modifier](./media/common-data-model-approve/edit-record.png)
4. Dans la zone **État**, tapez ou collez **Approuvé**.
   
    ![Approuver un fichier](./media/common-data-model-approve/change-status.png)
5. Dans le coin supérieur droit, cliquez ou appuyez sur l’icône en forme de coche pour enregistrer vos modifications et revenir à l’écran Détails.
   
    ![Enregistrer les modifications](./media/common-data-model-approve/save-record.png)
   
    Dans quelques minutes, vous allez recevoir un courrier électronique indiquant que le fichier a été approuvé.
6. Dans le coin supérieur droit, cliquez ou appuyez sur le bouton Précédent pour revenir à l’écran de navigation.
   
    ![Revenir à l’écran de navigation](./media/common-data-model-approve/back-arrow.png)
7. Pour les autres fichiers de la liste, cliquez ou appuyez sur la flèche pour afficher les détails associés.
   
    ![Ouvrir l’écran Détails](./media/common-data-model-approve/open-details.png)
8. Dans le coin supérieur droit, cliquez ou appuyez sur l’icône en forme de crayon pour modifier les informations du fichier.
   
    ![Ouvrir l’écran Modifier](./media/common-data-model-approve/edit-record.png)
9. Dans la zone **État**, tapez ou collez **Rejeté** (ou un autre texte, sauf **Approuvé** ou des déclinaisons telles que **Aprouvé** ou **Approuuvé**).
   
    ![Rejeter le fichier](./media/common-data-model-approve/reject-file.png)
10. Dans le coin supérieur droit, cliquez ou appuyez sur l’icône en forme de coche pour enregistrer vos modifications et revenir à l’écran Détails.
    
     ![Enregistrer les modifications](./media/common-data-model-approve/save-record.png)
    
     Dans quelques minutes, vous allez recevoir un courrier électronique indiquant que le fichier a été rejeté. Le fichier va être supprimé de Dropbox.

