---
title: Créer une boucle d’approbation avec le Common Data Service | Microsoft Docs
description: Créer une entité, un Flow et une application qui fonctionnent ensemble afin que les réviseurs puissent approuver ou rejeter des fichiers ajoutés à Dropbox.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4f58e5b3095769349e71e9ba8b203ea678981391
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546843"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Créer une boucle d’approbation à l’aide de Microsoft Flow et de Microsoft Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Le Common Data Service peut vous offrir un moyen de créer des flux qui contiennent des informations stockées dans une base de données indépendamment d’un flux. Le meilleur exemple est avec les approbations. Si vous stockez l’état de l’approbation dans une entité, votre Flow peut travailler dessus.

Dans cet exemple, vous allez créer un processus d’approbation qui démarre lorsqu’un utilisateur ajoute un fichier à Dropbox. Une fois le fichier ajouté, des informations s’affichent dans une application, dans laquelle un réviseur peut approuver ou rejeter la modification. Lorsque le réviseur approuve ou rejette la modification, le courrier de notification est envoyé et les fichiers rejetés sont supprimés de Dropbox.

En suivant les étapes de cette section, vous allez créer :

* **entité personnalisée** qui contient des informations sur chaque fichier ajouté à Dropbox et indique si l’état du fichier est approuvé, rejeté ou en attente.
* un **Flow** qui ajoute des informations à l’entité personnalisée lorsqu’un fichier est ajouté à Dropbox, envoie un message lorsque le fichier est approuvé ou rejeté et supprime les fichiers rejetés. Ces étapes montrent comment créer un tel flot à partir de zéro, mais vous pouvez créer un flot similaire à partir d’un modèle.
* **application** dans laquelle un réviseur peut approuver ou rejeter des fichiers ajoutés à Dropbox. Vous allez utiliser PowerApps pour générer automatiquement cette application en fonction des champs de l’entité personnalisée.

**Conditions préalables**

* Inscrivez-vous à [Microsoft Flow](sign-up-sign-in.md) et [powerapps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Créez des connexions à Dropbox et Office 365 Outlook, comme décrit dans [gérer vos connexions](https://powerapps.microsoft.com/tutorials/add-manage-connections/) .

## <a name="build-the-entity"></a>Créer l’entité
1. Connectez-vous à [powerapps.com](https://web.powerapps.com).
2. Si la barre de navigation de gauche n’apparaît pas par défaut, cliquez ou appuyez sur l’icône avec trois lignes horizontales dans le coin supérieur gauche.
   
    ![Ouvrir la barre de navigation gauche](./media/common-data-model-approve/hamburger-icon.png)
3. Dans la barre de navigation de gauche, cliquez ou appuyez sur **gérer**, puis cliquez ou appuyez sur **entités**.
   
    ![Gérer les entités](./media/common-data-model-approve/manage-entities.png)
4. Si vous y êtes invité, cliquez ou appuyez sur **créer ma base de données**.
   
    ![Créer une base de données](./media/common-data-model-approve/create-database.png)
5. Près de l’angle supérieur droit, cliquez ou appuyez sur **nouvelle entité**.
   
    ![Créer une entité](./media/common-data-model-approve/new-entity.png)
   
    Si la fenêtre de votre navigateur n’est pas agrandie, ce bouton peut apparaître à un autre emplacement.
6. Sous **nom**de l’entité, spécifiez un nom qui ne contient pas d’espaces et n’a pas d’autre entité dans votre base de données.
   
    Pour suivre exactement cet exemple, spécifiez **réviserfichiersdropbox**.
   
    ![Spécifier le nom de l’entité](./media/common-data-model-approve/entity-name.png)
7. Sous **nom complet**, spécifiez un nom convivial.
   
    ![Spécifier le nom d’affichage](./media/common-data-model-approve/display-name.png)
8. Cliquez ou appuyez sur **suivant**.
   
    ![Bouton suivant](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Ajouter des champs à l’entité
1. Près de l’angle supérieur droit, cliquez ou appuyez sur **Ajouter un champ**.
   
    ![Ajouter un champ](./media/common-data-model-approve/add-field.png)
2. Dans la ligne vide qui apparaît en bas de la liste des champs, définissez les propriétés d’un champ **approbateur** . (Lorsque vous définissez ces propriétés, vous pouvez basculer vers la colonne suivante en appuyant sur la touche Tab.)
   
   * Dans la colonne **nom complet** , tapez **approbateur**.
   * Dans la colonne **nom** , tapez **ApproverEmail**.
   * Dans la colonne **type** , cliquez ou appuyez sur l’option **e-mail** .
   * Dans la colonne **obligatoire** , activez la case à cocher.
     
     ![Champ approbateur](./media/common-data-model-approve/approver-field.png)
3. Dans la ligne suivante, définissez les propriétés d’un champ d' **État** :
   
   * Dans la colonne **nom complet** , tapez **Status**.
   * Dans la colonne **nom** , tapez **Status**.
   * Dans la colonne **type** , cliquez ou appuyez sur l’option **Text (texte** ).
   * Dans la colonne **Propriétés** , laissez la valeur par défaut.
   * Dans la colonne **obligatoire** , activez la case à cocher.
     
     ![Champ d’État](./media/common-data-model-approve/status-field.png)
4. Dans la ligne suivante, définissez les propriétés d’un champ **fileid** :
   
   * Dans la colonne **nom complet** , tapez **identificateur de fichier**.
   * Dans la colonne **nom** , tapez **fileid**.
   * Dans la colonne **type** , cliquez ou appuyez sur l’option **Text (texte** ).
   * Dans la colonne **Propriétés** , laissez la valeur par défaut.
   * Dans la colonne **unique** , activez la case à cocher.
   * Dans la colonne **obligatoire** , activez la case à cocher.
     
     ![Champ FileID](./media/common-data-model-approve/fileid-field.png)
5. Près du bord droit, cliquez ou appuyez sur les points de suspension (...) du champ **fileid** , puis cliquez ou appuyez sur **définir comme champ de titre**.
   
    ![Définir le champ de titre](./media/common-data-model-approve/set-title-field.png)
6. Près de l’angle inférieur gauche, cliquez ou appuyez sur **créer**.
   
    ![Créer une entité](./media/common-data-model-approve/create-button.png)
7. facultatif Lorsque la liste des entités réapparaît, agrandissez la fenêtre de votre navigateur si elle n’est pas déjà agrandie, puis cliquez ou appuyez sur l’en-tête de colonne **type** . La liste est triée avec les entités personnalisées, telles que celle que vous venez de créer, qui apparaît en haut.

## <a name="sign-in-and-create-a-flow"></a>Se connecter et créer un Flow
1. Ouvrez le [portail Microsoft Flow](https://flow.microsoft.com).
2. Agrandissez la fenêtre de votre navigateur si elle n’est pas déjà agrandie, puis cliquez ou appuyez sur **se connecter dans** l’angle supérieur droit.
   
    ![Bouton de connexion pour Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. Dans le menu en haut à droite, sélectionnez l’environnement dans lequel vous avez créé la base de données dans powerapps.com.
   
    **Remarque**: Si vous ne sélectionnez pas le même environnement, vous ne verrez pas votre entité.
4. Près de l’angle supérieur gauche, cliquez ou appuyez sur **mes flux**.
   
    ![Bouton mes flux](./media/common-data-model-approve/myflows-button.png)
5. Près de l’angle supérieur droit, cliquez ou appuyez sur **créer un nouveau fluide**.
   
    ![Bouton créer un nouveau Flow](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Démarrer quand un fichier est ajouté
1. Dans la zone qui contient **Rechercher d’autres déclencheurs**, tapez ou collez **Dropbox**, puis cliquez ou appuyez sur **Dropbox-quand un fichier est créé**.
   
    ![Créer un déclencheur](./media/common-data-model-approve/create-trigger.png)
2. Sous **dossier**, cliquez ou appuyez sur l’icône de dossier, puis accédez au dossier dans lequel les fichiers seront ajoutés.
   
    ![Choisir un dossier](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Ajouter des données à l’entité
1. Cliquez ou appuyez sur **nouvelle étape**, puis cliquez ou appuyez sur **Ajouter une action**.
   
    ![Ajouter une action](./media/common-data-model-approve/add-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Common Data Service**, puis cliquez ou appuyez sur **Common Data Service-créer un objet**.
   
    ![Créer un objet dans le Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Sous **l’entité**, tapez ou collez la **révision**, puis cliquez ou appuyez sur **vérifier les fichiers Dropbox**.
   
    ![Choisir l’entité](./media/common-data-model-approve/choose-entity-flow.png)
4. Sous **titre**, cliquez ou appuyez dans la zone, puis cliquez ou appuyez sur **nom de fichier** dans la liste des jetons de paramètre pour ajouter ce jeton au champ.
   
    ![Ajouter un jeton de nom de fichier](./media/common-data-model-approve/add-filename-token.png)
5. Sous **approbateur**, tapez ou collez l’adresse de messagerie de la personne qui examinera les fichiers.
   
    **Remarque**: pour faciliter le test du fluide, spécifiez votre propre adresse. Vous pouvez le modifier ultérieurement, lorsque le workflow est prêt pour une utilisation réelle.
   
    ![Ajouter un approbateur](./media/common-data-model-approve/add-approver.png)
6. Sous **État**, tapez ou collez **en attente**.
   
    ![Ajouter l’État par défaut](./media/common-data-model-approve/add-default-status.png)
7. Sous **identificateur de fichier**, cliquez ou appuyez dans la zone, puis cliquez ou appuyez sur **identificateur de fichier** dans la liste des jetons de paramètre pour ajouter ce jeton au champ.
   
    ![Ajouter un jeton d’identificateur de fichier](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Vérifier si le fichier a été révisé
1. Sous l' **action créer un objet** , cliquez ou appuyez sur **nouvelle étape**, cliquez ou appuyez sur **plus**, puis cliquez ou appuyez sur **Ajouter un Do Until**.
   
    ![Ajouter jusqu’à](./media/common-data-model-approve/add-do-until.png)
2. Dans l’angle supérieur gauche de l’action **Do Until** , cliquez ou appuyez dans la zone contenant **choisir une valeur**.
   
    ![Choisir une valeur](./media/common-data-model-approve/choose-value.png)
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, cliquez ou appuyez dans la zone supérieure contenant **choisir une valeur**.
3. Sous **sorties de Create Object**, cliquez ou appuyez sur **Status** pour ajouter ce jeton de paramètre au champ.
   
    ![Ajouter un jeton d’État](./media/common-data-model-approve/add-status.png)
4. Ouvrez la liste à proximité du centre de l’action **Do Until** , puis cliquez ou appuyez sur **n’est pas égal à**.
   
    ![Spécifier n’est pas égal à](./media/common-data-model-approve/is-not-equal.png)
5. Dans l’angle supérieur droit de l’action **Do Until** , tapez ou collez en **attente** dans la zone contenant **choisir une valeur**.
   
    ![Spécifier l’État à surveiller](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, cliquez ou appuyez dans la zone inférieure contenant **choisir une valeur**.
6. Vers le bas de l’action **Do Until** , cliquez ou appuyez sur **Ajouter une action**.
   
    ![Ajouter une action à l’intérieur d’un Do Until](./media/common-data-model-approve/add-action-in-dountil.png)
7. Dans la zone qui contient **Rechercher d’autres actions**, tapez **Common**, puis cliquez ou appuyez sur **Common Data Service-obtenir un objet**.
   
    ![Obtient un objet](./media/common-data-model-approve/get-object.png)
8. Sous **l’espace de noms**, cliquez ou appuyez sur votre base de données.
9. Sous **l’entité**, tapez ou collez la **révision**, puis cliquez ou appuyez sur **vérifier les fichiers Dropbox**.
   
    ![Choisir une entité](./media/common-data-model-approve/choose-entity-flow.png)
10. Sous **ID d’objet**, cliquez ou appuyez dans la zone, puis cliquez ou appuyez sur le jeton de paramètre d' **identificateur de fichier** pour l’ajouter au champ.
    
     ![Ajouter un identificateur d’objet](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Vérifier si l’élément a été approuvé
1. Sous l’action **Do-Until** , cliquez ou appuyez sur **nouvelle étape**, puis cliquez ou appuyez sur **Ajouter une condition**.
   
    ![Ajouter une condition](./media/common-data-model-approve/add-condition.png)
2. Dans l’angle supérieur gauche de la condition, cliquez ou appuyez dans la zone contenant **choisir une valeur**.
   
    ![Coin supérieur gauche de la condition](./media/common-data-model-approve/condition-upper-left.png)
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, cliquez ou appuyez dans la zone supérieure contenant **choisir une valeur**.
3. Sous **sorties de l’objet d’extraction**, cliquez ou appuyez sur le jeton de paramètre d' **État** pour l’ajouter au champ.
   
    ![Ajouter l’État à la condition](./media/common-data-model-approve/add-status-to-condition.png)
4. Dans le coin supérieur droit de la condition, tapez ou collez **approuvé** dans la zone contenant **choisir une valeur**.
   
    ![Vérifier si l’État est défini sur approuvé](./media/common-data-model-approve/status-equals-approved.png)
   
    **Remarque**: Si votre fenêtre de navigateur n’est pas agrandie, tapez ou collez **approuvé** dans la zone inférieure contenant **choisir une valeur**.

## <a name="send-notification-mail"></a>Envoyer un message de notification
1. Sous **si oui, ne rien faire**, cliquez ou appuyez sur **Ajouter une action**.
   
    ![Si oui, ajouter une action](./media/common-data-model-approve/if-yes-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Envoyer un message**électronique, puis cliquez ou appuyez sur **Office 365 Outlook-envoyer un e-mail**.
   
    ![Si oui, envoyer un message](./media/common-data-model-approve/if-yes-send-mail.png)
3. Sous **à**, tapez ou collez l’adresse de la personne que vous souhaitez notifier lorsqu’un élément est accepté.
   
    **Remarque**: pour faciliter le test du fluide, spécifiez votre propre adresse. Vous pouvez le modifier lorsque le workflow est prêt pour une utilisation réelle.
   
    ![Destinataire de l’approbation](./media/common-data-model-approve/approval-recipient.png)
4. Sous **objet**, cliquez ou appuyez sur dans la zone, puis cliquez ou appuyez sur le jeton de paramètre de **nom de fichier** pour l’ajouter au champ.
   
    ![Spécifier le nom de fichier en tant qu’objet de l’e-mail](./media/common-data-model-approve/subject-is-file-name.png)
5. Sous **corps**, tapez ou collez **l’élément a été approuvé.**
   
    ![Corps du message d’approbation](./media/common-data-model-approve/approval-body.png)
6. Sous **si non, ne rien faire**, répétez les étapes 1-5 de cette procédure, sauf si vous spécifiez le corps du message électronique lorsque **l’élément a été rejeté.**
   
    ![Corps du courrier de rejet](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Supprimer les fichiers rejetés
1. Sous les champs du courrier de rejet, cliquez ou appuyez sur **Ajouter une action**.
   
    ![Ajouter une action de suppression](./media/common-data-model-approve/add-delete-action.png)
2. Dans la zone qui contient **Rechercher d’autres actions**, tapez ou collez **Dropbox**, puis cliquez ou appuyez sur **Dropbox-supprimer le fichier**.
   
    ![Supprimer le fichier de Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Sous **fichier**, cliquez ou appuyez dans la zone, puis cliquez ou appuyez sur le paramètre jeton de l' **identificateur de fichier** pour l’ajouter au champ.
   
    ![Identifier le fichier à supprimer](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Enregistrer le Flow
1. En haut de l’écran, tapez ou collez un nom pour le Flow que vous êtes en train de créer, puis cliquez ou appuyez sur **créer un Flow**.
   
    ![enregistrer le Flow](./media/common-data-model-approve/save-flow.png)
2. Cliquez ou appuyez sur **Fermer** , puis cliquez ou appuyez sur **terminé**.
3. Dans Dropbox, ajoutez au moins deux fichiers au dossier que vous avez spécifié : un pour tester l’approbation et un pour tester le rejet.

## <a name="build-the-app"></a>générer l’application
1. Connectez-vous à [powerapps.com](https://web.powerapps.com), puis cliquez ou appuyez sur **New App (nouvelle application** ) dans la partie inférieure de la barre de navigation de gauche.
   
    ![Créer une application dans un navigateur](./media/common-data-model-approve/new-app-button.png)
2. Dans la boîte de dialogue qui s’affiche, cliquez ou appuyez sur l’option pour ouvrir l’PowerApps Studio pour Windows ou PowerApps Studio pour le Web.
3. Si vous avez ouvert PowerApps Studio pour Windows, cliquez ou appuyez sur **nouveau** dans la barre de navigation de gauche.
4. Sous **créer une application à partir de vos données**, cliquez ou appuyez sur **mode téléphone** dans la vignette **Common Data Service** .
   
    ![Créer une application](./media/common-data-model-approve/afd-cdm.png)
5. Dans la zone de **recherche** , tapez ou collez la **révision**.
   
    ![Rechercher une entité](./media/common-data-model-approve/search-entities.png)
6. Sous **choisir une entité**, cliquez ou appuyez sur **vérifier les fichiers Dropbox**.
   
    ![Choisir une entité](./media/common-data-model-approve/choose-entity.png)
7. Près de l’angle inférieur droit, cliquez ou appuyez sur **Connect (connecter**).
   
    ![Bouton de connexion](./media/common-data-model-approve/connect-button.png)
8. Si l’écran d’accueil de la visite guidée de Intro s’affiche, suivez la visite guidée pour vous familiariser avec les PowerApps (ou cliquez ou appuyez sur **Skip**).
   
    ![Présentation de l’introduction](./media/common-data-model-approve/quick-tour.png)
   
    Vous pouvez toujours suivre la visite guidée ultérieurement en cliquant ou appuyant sur l’icône de point d’interrogation près de l’angle supérieur gauche, puis en cliquant ou appuyant sur **Take the Intro tour**.
9. facultatif Vers le bas de l’écran, faites glisser le curseur pour augmenter le zoom afin que l’application soit plus facile à voir.
   
    ![Contrôle de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personnaliser l’application
1. Dans la barre de navigation de droite, cliquez ou appuyez sur la disposition qui comprend un en-tête et une description.
   
    ![Bouton de connexion](./media/common-data-model-approve/choose-layout.png)
2. Sur la **BrowseScreen**, cliquez ou appuyez sur juste sous la barre de recherche pour sélectionner le contrôle de zone de texte de plus grande taille.
   
    ![Sélectionner un en-tête](./media/common-data-model-approve/select-header.png)
3. Dans le volet de droite, ouvrez la liste inférieure en cliquant ou en appuyant sur la flèche vers le bas.
   
    ![Ouvrir la liste déroulante](./media/common-data-model-approve/open-dropdown.png)
4. Dans la liste inférieure, cliquez ou appuyez sur **title** pour afficher le nom de fichier des fichiers ajoutés.
   
    ![Définir les données d’en-tête](./media/common-data-model-approve/set-heading.png)
5. Dans le volet de droite, ouvrez la liste supérieure, puis cliquez ou appuyez sur **Status** pour afficher l’état de chaque fichier.
   
    ![Définir des données de corps](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Tester la solution globale
1. Dans PowerApps, ouvrez le mode aperçu en cliquant ou en appuyant sur le bouton de lecture près de l’angle supérieur gauche.
   
    ![Ouvrir le mode aperçu](./media/common-data-model-approve/open-preview.png)
2. Pour le premier fichier de la liste, cliquez ou appuyez sur la flèche pour afficher les détails de ce fichier.
   
    ![Ouvrir l’écran de détails](./media/common-data-model-approve/open-details.png)
3. Dans l’angle supérieur droit, cliquez ou appuyez sur l’icône en forme de crayon pour modifier les détails du fichier.
   
    ![Ouvrir l’écran de modification](./media/common-data-model-approve/edit-record.png)
4. Dans la zone **État** , tapez ou collez **approuvé**.
   
    ![Approuver un fichier](./media/common-data-model-approve/change-status.png)
5. Dans l’angle supérieur droit, cliquez ou appuyez sur l’icône de coche pour enregistrer vos modifications et revenir à l’écran de détails.
   
    ![Enregistrer les modifications](./media/common-data-model-approve/save-record.png)
   
    Dans quelques minutes, vous recevrez un courrier électronique indiquant que le fichier a été approuvé.
6. Dans l’angle supérieur droit, cliquez ou appuyez sur le bouton précédent pour revenir à l’écran de navigation.
   
    ![Revenir à l’écran de navigation](./media/common-data-model-approve/back-arrow.png)
7. Pour l’autre fichier de la liste, cliquez ou appuyez sur la flèche pour afficher les détails de ce fichier.
   
    ![Ouvrir l’écran de détails](./media/common-data-model-approve/open-details.png)
8. Dans l’angle supérieur droit, cliquez ou appuyez sur l’icône en forme de crayon pour modifier les détails du fichier.
   
    ![Ouvrir l’écran de modification](./media/common-data-model-approve/edit-record.png)
9. Dans la zone **État** , tapez ou collez **rejeté** (ou tout sauf **approuvé**, y compris **aproved** ou **approuuvé**).
   
    ![Rejeter le fichier](./media/common-data-model-approve/reject-file.png)
10. Dans l’angle supérieur droit, cliquez ou appuyez sur l’icône de coche pour enregistrer vos modifications et revenir à l’écran de détails.
    
     ![Enregistrer les modifications](./media/common-data-model-approve/save-record.png)
    
     Dans quelques minutes, vous recevrez un courrier électronique indiquant que le fichier a été rejeté et le fichier sera supprimé de Dropbox.

