---
title: Utilisez des expressions avec des conditions. | Microsoft Docs
description: Utilisez des expressions avancées telles que « et », « ou », « Empty », « Less » et « plus » avec des conditions de Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/15/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 940ab40b9bac7d76734773805820911a20cd46aa
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548373"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Utiliser des expressions dans des conditions pour vérifier plusieurs valeurs
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dans cette procédure pas à pas, vous allez apprendre à utiliser des expressions et des **conditions** pour comparer plusieurs valeurs en **mode avancé**.

Lorsque vous créez un fluide, vous pouvez utiliser la carte [**condition**](add-condition.md#add-a-condition) en mode de base pour comparer rapidement une valeur unique à une autre valeur. Toutefois, il est parfois nécessaire de comparer plusieurs valeurs. Par exemple, vous pouvez vérifier la valeur de quelques colonnes dans une feuille de calcul ou une table de base de données.

Vous pouvez utiliser n’importe quelle combinaison d’expressions logiques suivantes dans vos conditions.

formule|Descriptive|Tels
--------|-----------|-------
|[les](#use-the-and-expression)|Accepte deux arguments et retourne true si les deux valeurs sont vraies.<br><b>Remarque</b>: les deux arguments doivent être des valeurs booléennes.|Cette expression retourne la valeur false : <br>et (supérieur à (1, 10), égal à (0, 0))
|[ni](#use-the-or-expression)|Accepte deux arguments et retourne true si l’un des arguments a la valeur true. <br><b>Remarque</b>: les deux arguments doivent être des valeurs booléennes.|Cette expression retourne true :<br>ou (supérieur (1, 10), égal à (0, 0))
|Equals|Retourne la valeur true si deux valeurs sont égales.|Par exemple, si paramètre1 est someValue, cette expression retourne true :<br>est égal à (Parameters ('paramètre1 '), 'someValue')
|[inferieur](#use-the-less-expression)|Accepte deux arguments et retourne la valeur true si le premier argument est inférieur au deuxième argument. <br><b>Remarque</b>: les types pris en charge sont Integer, float et String.|Cette expression retourne true :<br>moins (10100)
|lessOrEquals|Accepte deux arguments et retourne la valeur true si le premier argument est inférieur ou égal au deuxième argument. <br><b>Remarque</b>: les types pris en charge sont Integer, float et String.|Cette expression retourne true :<br>lessOrEquals (10, 10)
|[supérieur](#use-the-greater-expression)|Accepte deux arguments et retourne la valeur true si le premier argument est supérieur au deuxième argument. <br><b>Remarque</b>: les types pris en charge sont Integer, float et String.|Cette expression retourne la valeur false :<br>supérieur (10, 10)
|greaterOrEquals|Accepte deux arguments et retourne la valeur true si le premier argument est supérieur ou égal au deuxième argument. <br><b>Remarque</b>: les types pris en charge sont Integer, float et String.|Cette expression retourne la valeur false :<br>greaterOrEquals (10100)
|[vidé](#use-the-empty-expression)|Retourne la valeur true si l’objet, le tableau ou la chaîne est vide.|Cette expression retourne true :<br>Empty (' ')
|pas|Retourne l’inverse d’une valeur booléenne. |Cette expression retourne true :<br>Not (contient (« 200 Success », « Fail »))
|Que|Retourne une valeur spécifique si l’expression donne True ou false.|Cette expression renvoie « Oui » :<br>Si (est égal à (1, 1), « oui », « non »)

## <a name="prerequisites"></a>Conditions préalables
* Accès aux Microsoft Flow.
* Une feuille de calcul avec les tables décrites plus loin dans cette procédure pas à pas. Veillez à enregistrer votre feuille de calcul dans un emplacement tel que Dropbox ou Microsoft OneDrive afin que les Microsoft Flow puissent y accéder.
* Microsoft Office Outlook 365 (pendant que nous utilisons Office 365 Outlook, vous pouvez utiliser n’importe quel service de messagerie pris en charge dans vos flux.)

## <a name="use-the-or-expression"></a>Utiliser l’expression ou
Parfois, votre flux de travail doit effectuer une action si la valeur d’un élément est valueA **ou** valueB. Par exemple, vous pouvez effectuer le suivi de l’état des tâches dans un tableau de feuille de calcul. Supposons que la table possède une colonne nommée *Status* et que les valeurs possibles dans la colonne *Status* soient :

* **procédé**
* **obstrué**
* **évite**
* **non démarré**

Voici un exemple de ce à quoi peut ressembler la feuille de calcul :

![exemple de feuille de calcul](./media/use-expressions-in-conditions/spreadsheet-table.png)

À partir de la feuille de calcul précédente, vous souhaitez utiliser Microsoft Flow pour supprimer toutes les lignes dont la colonne *Status* est définie sur *Completed* ou *inutile*.

Créons le Flow.

### <a name="start-with-a-blank-flow"></a>Démarrer avec un flot vide
1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com).

    ![Connexion](includes/media/modern-approvals/sign-in.png)
2. Sélectionnez l’onglet **mes flux** .

    ![sélectionner mes flux](includes/media/modern-approvals/select-my-flows.png)
3. Sélectionnez **créer à partir d’un espace vide**.

    ![créer à partir d’un espace](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Ajouter un déclencheur à votre Flow
1. Recherchez **planification**, puis sélectionnez le déclencheur **planification-récurrence**

    ![déclencheur de planification](includes/media/schedule-trigger/schedule-trigger.png)
2. Définissez la planification pour qu’elle s’exécute une fois par jour.

    ![définir la planification](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Sélectionner la feuille de calcul et récupérer toutes les lignes
1. Sélectionnez **nouvelle étape** > **Ajouter une action**.

    ![Nouvelle étape](includes/media/new-step/action.png)
2. Recherchez des **lignes**, puis sélectionnez **Excel-obtenir des lignes**.

    Remarque : sélectionnez l’action « extraire les lignes » qui correspond à la feuille de calcul que vous utilisez. Par exemple, si vous utilisez Google Sheets, sélectionnez **Google Sheets-obtenir des lignes**.

    ![récupérer les lignes](includes/media/new-step/get-excel-rows.png)
3. Sélectionnez l’icône de dossier dans la zone **nom de fichier** , accédez à, puis sélectionnez la feuille de calcul qui contient vos données.

    ![sélectionner une feuille de calcul](includes/media/new-step/select-spreadsheet.png)
4. Sélectionnez la table qui contient vos données dans la liste nom de la **table** .

    ![sélectionner une table](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Vérifiez la colonne État de chaque ligne
1. Sélectionnez **nouvelle étape** > **plus** > **Ajouter un appliquer à chaque**.

    ![sélectionner une table](includes/media/new-step/apply-to-each.png)
2. Ajoutez le jeton de **valeur** à la zone **Sélectionnez une sortie à partir des étapes précédentes** .

    ![sélectionner une table](includes/media/apply-to-each/add-value-token.png)
3. Sélectionnez **Ajouter une condition** > **modifier en mode avancé**.
4. Ajoutez l’expression **ou** suivante. Cette expression **ou** vérifie la valeur de chaque ligne de la table (une ligne est appelée « élément » lorsque vous y accédez dans une expression). Si la valeur de la colonne **Status** est *terminée* **ou** *inutile*, l’expression **ou** prend la valeur « true ».

    L’expression **ou** s’affiche comme illustré ici :

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    La carte de **condition** ressemble à l’image suivante :

    ![image de l’expression or](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Supprimer les lignes correspondantes de la feuille de calcul
1. Sélectionnez **Ajouter une action** dans la branche **si oui, ne rien faire** de la condition.
2. Recherchez **Supprimer la ligne**, puis sélectionnez **Excel-supprimer la ligne**.

    ![supprimer l’image de ligne](includes/media/new-step/select-delete-excel-row.png)
3. Dans la zone **nom de fichier** , recherchez et sélectionnez le fichier de feuille de calcul qui contient les données que vous souhaitez supprimer.
4. Dans la liste nom de la **table** , sélectionnez la table qui contient vos données.
5. Placez le jeton d' **ID de ligne** dans la zone **ID de ligne** .

    ![fichier de feuille de calcul](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Nommer le Flow et l’enregistrer
1. Donnez un nom à votre Flow, puis sélectionnez le bouton **créer un Flow** .

    ![enregistrer votre Flow](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Exécuter le Flow avec l’expression ou
Le workflow s’exécute une fois que vous l’avez enregistré. Si vous avez créé la feuille de calcul indiquée plus haut dans cette procédure pas à pas, voici à quoi elle ressemble une fois l’exécution terminée :

![ou l’expression se termine](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Notez que toutes les données des lignes dont l’État est « Completed » ou « inutile » dans la colonne Status ont été supprimées.

## <a name="use-the-and-expression"></a>Utiliser l’expression and
Supposons que vous disposez d’un tableau de feuille de calcul avec deux colonnes. Les noms des colonnes sont Status et Assigned. Supposons également que vous souhaitez supprimer toutes les lignes si la valeur de la colonne d’État est « bloqué » et que la valeur de la colonne affectée est « John Wonder ».  Pour accomplir cette tâche, suivez toutes les étapes décrites plus haut dans cette procédure pas à pas. Toutefois, lorsque vous modifiez la carte **condition** en mode avancé, utilisez l’expression **and** présentée ici :

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

La carte de **condition** ressemble à l’image suivante :

![image de l’expression and](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Exécuter le Flow avec l’expression and
Si vous avez suivi le, votre feuille de calcul ressemble à cette image :

![avant et s’exécute](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Une fois votre workflow exécuté, votre feuille de calcul ressemble à cette image :

![après et s’exécute](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Utiliser l’expression Empty
Notez qu’il y a maintenant plusieurs lignes vides dans la feuille de calcul. Pour les supprimer, utilisez l’expression **Empty** pour identifier toutes les lignes qui n’ont pas de texte dans les colonnes Assigned et Status.

Pour accomplir cette tâche, suivez toutes les étapes répertoriées dans la section **utiliser l’expression and** plus haut dans cette procédure pas à pas. Toutefois, lorsque vous modifiez la carte **condition** en mode avancé, utilisez l’expression Empty comme suit :

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

La carte de **condition** ressemble à l’image suivante :

![image d’expression vide](./media/use-expressions-in-conditions/empty-expression.png)

Après l’exécution de votre workflow, la feuille de calcul ressemble à l’image suivante :

![après des exécutions vides](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Notez que des lignes supplémentaires sont supprimées de la table.

## <a name="use-the-greater-expression"></a>Utiliser l’expression supérieure
Imaginez que vous avez acheté des tickets de baseball pour vos collègues et que vous utilisez une feuille de calcul pour vous assurer qu’ils sont remboursés par chaque personne. Vous pouvez rapidement créer un workflow qui envoie un e-mail quotidien à chaque personne qui n’a pas payé le montant total.

Utilisez l’expression **supérieure** pour identifier les employés qui n’ont pas payé le montant total. Vous pouvez ensuite envoyer automatiquement un courrier électronique de rappel à ceux qui n’ont pas été entièrement payés.

Voici une vue de la feuille de calcul :

![vue de la feuille de calcul](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Voici l’implémentation de l’expression **supérieure** qui identifie toutes les personnes qui ont payé moins que le montant dû :

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Utiliser l’expression less
Imaginez que vous avez acheté des tickets de baseball pour vos collègues et que vous utilisez une feuille de calcul pour vous assurer que chaque personne est remboursée par la date à laquelle tout le monde a convenu. Vous pouvez créer un Flow qui envoie un message de rappel à chaque personne qui n’a pas payé le montant total si la date actuelle est antérieure à un jour avant la date d’échéance.

Utilisez l’expression and avec l’expression **less** **,** car deux conditions sont validées :


|          Condition à valider          | expression à utiliser |                    Tels                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   Le montant total a-t-il été payé ?    |      supérieur      |   @greater(Item () ? [' Due'], élément () ? [« Payé »])    |
| La date d’échéance est-elle inférieure à un jour ? |       inferieur        | @less(Item () ? [' DueDate'], addDays (utcNow (), 1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Combiner les expressions supérieure et inférieure dans une expression and
Utilisez l’expression **supérieure** pour identifier les employés qui ont payé moins que le montant total dû et utilisez l’expression **moins** pour déterminer si la date d’échéance du paiement est antérieure d’un jour à la date actuelle. Vous pouvez ensuite **Envoyer une action envoyer un courrier électronique** pour envoyer des rappels conviviaux à ceux qui n’ont pas été entièrement payés et la date d’échéance est antérieure à un jour.

Voici une vue du tableau de la feuille de calcul :

![vue de la feuille de calcul](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Voici l’implémentation de l’expression **and** qui identifie toutes les personnes qui ont payé moins que le montant dû, et la date d’échéance est antérieure d’un jour à la date actuelle :

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="use-functions-in-expressions"></a>Utiliser des fonctions dans les expressions

Certaines expressions obtiennent leurs valeurs à partir d’actions d’exécution qui peuvent ne pas encore exister lorsqu’un workflow commence à s’exécuter. Pour référencer ou utiliser ces valeurs dans les expressions, vous pouvez utiliser des fonctions fournies par le langage de définition de flux de travail. Informations supplémentaires : [référence aux fonctions pour le langage de définition de flux de travail dans Microsoft Flow](https://docs.microsoft.com/azure/logic-apps/workflow-definition-language-functions-reference)
