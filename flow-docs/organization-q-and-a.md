---
title: Questions et réponses sur la connexion à Microsoft Flow dans votre organisation | Microsoft Docs
description: Questions et réponses courantes sur les licences, l’administration et la connexion des utilisateurs à Microsoft Flow dans votre client Office 365
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f62bbf9e508c269c17284382b674a07221a2d568
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690557"
---
# <a name="flow-in-your-organization-qa"></a>Questions et réponses sur Microsoft Flow dans votre organisation
Cette rubrique décrit comment les utilisateurs de votre organisation peuvent utiliser Flow, et comment vous pouvez contrôler le service Microsoft Flow.

## <a name="signing-up-for-flow"></a>S’inscrire à Flow
### <a name="what-is-microsoft-flow"></a>Qu’est-ce que Microsoft Flow ?
Microsoft Flow est un service cloud public conçu pour aider les utilisateurs et les équipes à définir des flux de travail automatisés entre leurs applications et services favoris pour synchroniser des fichiers, obtenir des notifications, collecter des données, etc. 

### <a name="how-do-people-sign-up-for-flow"></a>Comment les utilisateurs s’inscrivent-ils à Microsoft Flow ?
Les utilisateurs disposent de deux méthodes pour s’inscrire à Microsoft Flow par le biais du portail web :

#### <a name="option-1"></a>Option 1
Les utilisateurs peuvent s’inscrire en accédant à [flow.microsoft.com](https://flow.microsoft.com), en sélectionnant **Inscrivez-vous gratuitement**, puis en terminant le processus d’inscription à Microsoft Flow sur [portal.office.com](https://portal.office.com/Start?sku=flow_free) ou [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Option 2
Les utilisateurs peuvent s’inscrire en accédant à [flow.microsoft.com](https://flow.microsoft.com), en sélectionnant **Se connecter**, en se connectant à l’aide de leur compte professionnel, scolaire ou personnel et en acceptant les conditions d’utilisation de Microsoft Flow.    

Lorsqu’un utilisateur de votre organisation s’inscrit à Microsoft Flow avec la deuxième option, une licence Microsoft Flow lui est attribuée automatiquement.

De plus amples détails sont disponibles sous [S’inscrire à Microsoft Flow](sign-up-sign-in.md).

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Puis-je empêcher une autre personne de s’inscrire à Flow ?
Microsoft Flow est un service cloud public auquel tout le monde peut s’inscrire et que tout le monde peut utiliser pour automatiser les tâches quotidiennes. Pour utiliser Microsoft Flow, les utilisateurs n’ont pas besoin de posséder ou d’utiliser un compte Office 365. Pour cette raison, il n’existe actuellement aucun mécanisme pour empêcher une autre personne d’utiliser Flow (puisque n’importe qui dans le monde peut le faire, quelle que soit son adresse de messagerie).

Toutefois, si une personne s’inscrit à Microsoft Flow et que vous choisissez de ne pas la prendre en charge à l’intérieur de votre organisation, elle ne peut en aucun cas faire encourir des frais à votre entreprise. Lorsqu’une personne s’inscrit à Microsoft Flow, la relation est établie entre cette personne et Microsoft directement, comme avec les nombreux autres services cloud de Microsoft, tels que Bing, Wunderlist, OneDrive ou Outlook.com. Lorsqu’une personne utilise Microsoft Flow, cela n’implique en aucune façon que le service est fourni par votre organisation.

Enfin, si votre entreprise souhaite limiter l’utilisation de données propres à l’organisation à l’intérieur de Microsoft Flow, c’est possible grâce à des stratégies de protection contre la perte de données (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-microsoft-flow"></a>Comment les utilisateurs peuvent-ils accéder aux fonctionnalités payantes de Microsoft Flow ?
Les personnes peuvent accéder aux fonctionnalités payantes de Microsoft Flow de trois façons différentes :

1. Elles peuvent s’inscrire individuellement à l’offre d’essai gratuit Flow Plan 1 ou Flow Plan 2 valable 90 jours.
2. Vous pouvez leur attribuer une licence Flow dans le portail d’administration d’Office 365.
3. L’utilisateur s’est vu attribuer un plan Office 365 et Dynamics 365 qui comprend l’accès au service Flow. Consultez la [page de tarification sur Flow](https://flow.microsoft.com/pricing/) pour obtenir la liste des plans Office 365 et Dynamics 365 qui incluent des fonctionnalités Flow.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Puis-je empêcher une autre personne d’utiliser les fonctionnalités payantes de Flow ?
Toute personne peut essayer les fonctionnalités payantes de Microsoft Flow pendant 90 jours et ce gratuitement. Toutefois, vous pouvez gérer entièrement l’attribution des licences perpétuelles payantes à l’intérieur de votre organisation via le portail d’administration Office 365.

Comme avec les offres gratuites, si une personne choisit de s’abonner à la version d’essai, une relation directe est établie entre la personne et Microsoft, et n’est pas nécessairement approuvée par votre entreprise.

## <a name="administration-of-flow"></a>Administration de Microsoft Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Pourquoi l’icône Flow s’affiche-t-elle dans le Lanceur d’applications Office 365 ?
Comme annoncé en août, Microsoft Flow est maintenant un élément fondamental de la suite Office 365. Trois mois après cette annonce, Microsoft Flow a été activé en tant que service dans le cadre de toutes les offres Office 365 existantes. Comme les utilisateurs du monde entier peuvent à présent utiliser Microsoft Flow, l’application s’affiche dans le Lanceur d’applications.

Consultez la section suivante si vous souhaitez supprimer la vignette Flow du Lanceur d’applications par défaut.

### <a name="how-do-i-remove-microsoft-flow-from-the-app-launcher-for-my-organization"></a>Comment supprimer Microsoft Flow du Lanceur d’applications pour mon organisation ?
Si un utilisateur s’est vu attribuer une licence Flow Plan 1 ou Flow Plan 2, vous pouvez effectuer les étapes suivantes pour supprimer la licence Flow pour cet utilisateur, ce qui supprime l’icône Flow du Lanceur d’applications :

1. Accédez au [portail d’administration d’Office 365](https://portal.microsoftonline.com/).
2. Dans la barre de navigation de gauche, sélectionnez **Utilisateurs**, puis **Utilisateurs actifs**.
3. Trouvez l’utilisateur dont vous souhaitez supprimer la licence, puis sélectionnez son nom.
4. Dans le volet de détails de l’utilisateur, dans la section **Licences du produit**, sélectionnez **Modifier**.
5. Recherchez la licence appelée **Microsoft Flow Plan 1** ou **Microsoft Flow Plan 2**, définissez le bouton bascule sur la valeur **Désactivé**, puis sélectionnez **Enregistrer**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Si un utilisateur a accès à Flow par le biais de la licence associée à son offre Office 365 et Dynamics 365, vous pouvez désactiver son accès aux fonctionnalités supplémentaires incluses dans ce plan en procédant comme suit :

1. Accédez au [portail d’administration d’Office 365](https://portal.microsoftonline.com/).
2. Dans la barre de navigation de gauche, sélectionnez **Utilisateurs**, puis **Utilisateurs actifs**.
3. Recherchez l’utilisateur dont vous souhaitez supprimer l’accès, puis sélectionnez son nom.
4. Dans le volet de détails de l’utilisateur, dans la section **Licences du produit**, sélectionnez **Modifier**.
5. Développez la licence Office 365 ou Dynamics 365 de l’utilisateur, désactivez l’accès au service appelé **Flow pour Office 365** ou **Flow pour Dynamics 365**, puis sélectionnez **Enregistrer**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

La suppression en bloc de licences est également possible via PowerShell. Pour accéder à un exemple détaillé, voir [Licence Office 365 et Windows PowerShell : Suppression d’une licence](https://technet.microsoft.com/library/dn771774.aspx).   Enfin, pour des conseils supplémentaires sur la suppression en bloc des services au sein d’une licence, consultez [Désactiver l’accès aux services Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

La suppression de la licence ou du service Flow d’un utilisateur de votre organisation entraîne la suppression de l’icône Flow des emplacements suivants pour cet utilisateur :

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Lanceur d’applications Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Notez que cela supprime uniquement la vignette Flow par défaut. Un utilisateur peut toujours choisir d’utiliser Microsoft Flow pour lui-même.

### <a name="why-did-10000-licenses-for-microsoft-flow-show-up-in-my-office-365-tenant"></a>Pourquoi 10 000 licences pour Microsoft Flow apparaissent dans mon locataire Office 365 ?
Tout le monde peut essayer Microsoft Flow Plan 1 ou 2 pendant 90 jours et ces licences d’essai représentent la capacité disponible pour les nouveaux utilisateurs de Flow dans votre locataire. Ces licences ne sont pas facturées. Plus précisément, il existe deux raisons pour lesquelles vous pouvez voir une capacité de 10 000 licences d’essai pour Flow dans le portail d’administration d’Office 365 :

1. Si au moins un utilisateur de votre locataire a participé à la version préliminaire publique de Flow qui s’étendait d’avril 2016 à octobre 2016, vous voyez 10 000 licences portant la mention « Microsoft PowerApps et flux logiques ».
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Si au moins un utilisateur de votre locataire s’est inscrit à une version d’essai Flow Plan 2 par l’intermédiaire de l’**Option 1** décrite dans la section qui décrit [comment les utilisateurs s’inscrivent à PowerApps](#how-do-people-sign-up-for-flow), vous voyez 10 000 licences intitulées « Microsoft Power Apps et Flow ».
   
    ![](./media/organization-q-and-a/licenses1.png)

Vous pouvez choisir d’attribuer des licences supplémentaires pour les utilisateurs vous-même via le portail d’administration Office 365, mais notez que ce sont des licences d’essai de Microsoft Flow Plan 2 qui expirent 90 jours après leur attribution à un utilisateur.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Est-ce gratuit ? Ces licences vont-elles m’être facturées ?
Aucun utilisateur ne peut entraîner la facturation de coûts pour votre organisation sans votre consentement explicite. Par conséquent, ni les licences d’essai ni les licences gratuites ne peuvent générer de frais pour votre organisation. En outre, elles n’utilisent pas de quotas (d’exécution par exemple).

### <a name="i-removed-the-microsoft-flow-free-license-and-users-can-still-access-flow"></a>J’ai supprimé la licence gratuite Microsoft Flow et les utilisateurs peuvent toujours accéder à Flow.
La licence gratuite Microsoft Flow est incluse uniquement à des fins de suivi. Comme indiqué dans la première section, il n’est pas possible d’empêcher une autre personne d’utiliser Microsoft Flow à des fins personnelles. Par conséquent, la présence d’une licence gratuite Microsoft Flow n’accorde ni ne supprime réellement de fonctionnalités.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Pourquoi ne puis-je pas voir toutes les licences Flow dans le portail d’administration d’Office 365 ?
Les utilisateurs peuvent utiliser Microsoft Flow individuellement ou dans le cadre de leur organisation. Les licences au niveau de l’organisation sont toujours visibles dans le portail Office 365. Toutefois, si un utilisateur s’inscrit à un essai en tant qu’individu, ceci n’est pas géré par leur administrateur Office 365 et n’apparaît pas dans le portail.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Comment une personne sait-elle quel plan elle utilise ?
Tout le monde peut voir son plan en visitant la page des prix de Flow sur [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Le plan ou l’essai en cours est présenté ici.

### <a name="will-microsoft-flow-sign-up-impact-the-identities-in-my-organization"></a>L’inscription à Microsoft Flow a-t-elle un impact sur les identités de mon organisation ?
Si votre organisation possède déjà un environnement Office 365 et que tous les utilisateurs de votre organisation ont un compte Office 365, la gestion des identités n’est pas affectée.

Si votre organisation possède déjà un environnement Office 365, mais que certains utilisateurs de votre organisation n’ont pas de compte Office 365, nous créons un utilisateur dans le locataire et attribuons des licences en fonction de l’adresse électronique professionnelle ou scolaire de cet utilisateur. Cela signifie que le nombre d’utilisateurs que vous gérez à un moment donné augmente à mesure que les utilisateurs de votre organisation s’inscrivent au service.

Si votre organisation n’a pas d’environnement Office 365 connecté à son domaine de messagerie, vous continuez de gérer les identités comme auparavant. Les utilisateurs sont ajoutés à un nouveau répertoire d’utilisateurs cloud et vous avez la possibilité de devenir l’administrateur du locataire et de les gérer.

### <a name="a-new-tenant-was-created-by-microsoft-flow-how-do-i-manage-this"></a>Un locataire a été créé par Microsoft Flow. Comme gérer cela ?
Si un locataire a été créé par Microsoft Flow, vous pouvez revendiquer et gérer ce locataire en procédant comme suit :

1. Rejoignez le locataire en vous inscrivant à Microsoft Flow à l’aide d’un domaine d’adresse électronique identique au domaine du locataire que vous souhaitez gérer. Par exemple, si Microsoft a créé le locataire contoso.com, vous devez rejoindre le locataire en utilisant une adresse électronique se terminant par @contoso.com.
2. Revendiquez le contrôle d’administration en vérifiant la propriété du domaine : une fois dans le locataire, vous pouvez prendre le rôle d’administrateur en vérifiant la propriété du domaine. Pour cela, procédez comme suit :    
   
   1. Accédez à [https://portal.office.com](https://portal.office.com/Start?sku=flow_free).
   2. Sélectionnez l’icône de lancement d’application dans le coin supérieur gauche et cliquez sur Administrateur.
   3. Lisez les instructions de la page **Become the admin** (Devenir l’administrateur), puis choisissez **Yes, I want to be the admin** (Oui, je souhaite être l’administrateur).  
      
       **REMARQUE** : si cette option n’est pas affichée, cela signifie qu’il existe déjà un administrateur Office 365.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Si je possède plusieurs domaines, puis-je contrôler le locataire Office 365 auquel les utilisateurs sont ajoutés ?
Si vous ne faites rien, un locataire est créé pour chaque domaine et sous-domaine de messagerie des utilisateurs.

Pour que tous les utilisateurs soient dans le même locataire indépendamment de leur extension d’adresse électronique :  

* Créez un locataire cible à l’avance ou utilisez un locataire existant. Ajoutez tous les domaines et sous-domaines que vous souhaitez consolider au sein de ce locataire. Tous les utilisateurs dont l’adresse électronique se termine par ces domaines et sous-domaines rejoignent alors automatiquement le locataire cible lors de leur inscription.

**Important** : il n’existe aucun mécanisme automatique pris en charge permettant de déplacer des utilisateurs entre les locataires une fois qu’ils ont été créés. Pour en savoir plus sur l’ajout de domaines à un locataire Office 365, voir [Ajouter des utilisateurs et un domaine à Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Comment puis-je limiter la capacité de mes utilisateurs à accéder aux données d’entreprise de mon organisation ?
Microsoft Flow vous permet de créer des zones pour les données d’entreprise et les données non commerciales, comme indiqué ci-dessous. Une fois que ces stratégies de protection contre la perte de données sont implémentées, les utilisateurs ne peuvent pas concevoir ou exécuter de flux qui combinent des données d’entreprise et non commerciales. Pour plus d’informations, consultez [Stratégies de protection contre la perte de données](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

