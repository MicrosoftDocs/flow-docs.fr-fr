---
title: Inscription de Flow Q & A dans votre organisation | Microsoft Docs
description: Questions fréquentes et réponses sur les licences, l’administration et les utilisateurs qui s’inscrivent à Flow dans votre client Office 365
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
ms.openlocfilehash: 750386a4a90a0b8dfb0f1e1f4320de3afee8db6f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548897"
---
# <a name="flow-in-your-organization-qa"></a>Flow dans votre organisation Q & A
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cette rubrique décrit comment les utilisateurs de votre organisation peuvent utiliser Flow, et comment vous pouvez contrôler le service Flow.

## <a name="signing-up-for-flow"></a>Inscription à Flow
### <a name="what-is-microsoft-flow"></a>Qu’est-ce que Microsoft Flow ?
Microsoft Flow est un service cloud public qui permet aux individus et aux équipes de configurer des flux de travail automatisés entre leurs applications et services favoris pour synchroniser, obtenir des notifications, collecter des données et bien plus encore. 

### <a name="how-do-people-sign-up-for-flow"></a>Comment les gens s’inscrivent-ils à Flow ?
Les utilisateurs peuvent s’inscrire à Flow via le portail Web de deux manières :

#### <a name="option-1"></a>Option 1
Tout le monde peut s’inscrire en accédant à [Flow.Microsoft.com](https://flow.microsoft.com), en sélectionnant **Inscrivez-vous gratuitement**, puis en terminant le processus d’inscription pour flow via [admin.Microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) ou [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Option 2
Tout le monde peut s’inscrire en accédant à [Flow.Microsoft.com](https://flow.microsoft.com), en sélectionnant **se connecter**, en se connectant avec leur adresse de messagerie professionnelle, scolaire ou personnelle, et en acceptant les conditions d’utilisation.    

Lorsqu’un utilisateur de votre organisation s’inscrit à Flow avec l’option 2, un Microsoft Flow licence gratuite est automatiquement attribuée à cet utilisateur.

S' [inscrire à Flow](sign-up-sign-in.md) contient plus de détails.

### <a name="what-is-the-microsoft-flow-free-plan"></a>Qu’est-ce que le Microsoft Flow plan gratuit ?

Le Microsoft Flow plan gratuit est utilisé uniquement à des fins de suivi. L’activation ou la désactivation de cette option n’a aucun effet sur la capacité d’un utilisateur à créer des flux. Si vous désactivez l’Microsoft Flow plan gratuit, il redevient réactivé lorsqu’un utilisateur se connecte. Il s’agit du comportement attendu.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Puis-je empêcher une autre personne de s’inscrire à Flow ?
Microsoft Flow est un service Cloud entièrement public, et tout le monde peut s’inscrire et l’utiliser pour automatiser les tâches quotidiennes. Pour utiliser Microsoft Flow il n’existe aucune exigence concernant les utilisateurs ou l’utilisation d’un compte Office 365. Pour cette raison, il n’existe aucun mécanisme à ce stade pour empêcher une autre personne d’utiliser Flow (puisque tout le monde peut, quelle que soit son adresse e-mail).

Toutefois, si une personne s’inscrit à Microsoft Flow et que vous choisissez de ne pas la prendre en charge au sein de votre organisation, elle ne peut en aucun cas supporter des coûts pour votre entreprise. Lorsqu’une personne s’inscrit pour Microsoft Flow, la relation est établie entre cette personne et Microsoft, qui est semblable à de nombreux autres services Cloud de Microsoft, tels que Bing, Wunderlist, OneDrive ou Outlook.com. L’utilisation d’Microsoft Flow par un individu n’implique en aucune façon que le service est fourni par votre organisation.

Enfin, si votre entreprise souhaite limiter l’utilisation de données de l’organisation uniquement à l’intérieur de Microsoft Flow, il est possible d’utiliser des stratégies de protection contre la perte de données (DLP).

### <a name="how-can-people-gain-access-to-the-paid-features-of-microsoft-flow"></a>Comment les utilisateurs peuvent-ils accéder aux fonctionnalités payantes de Microsoft Flow ?
Les utilisateurs peuvent accéder aux fonctionnalités payantes de Microsoft Flow de trois façons différentes :

1. Ils peuvent s’inscrire individuellement à une version d’essai de l’offre Flow plan 1 ou Flow plan 2, 90 jours gratuits
2. Vous pouvez leur attribuer une licence de Flow dans le portail d’administration Office 365.
3. Des plans Office 365 et Dynamics 365 ont été attribués à l’utilisateur, qui inclut l’accès au service de Flow. Pour obtenir la liste des plans Office 365 et Dynamics 365 qui incluent des fonctionnalités de Flow, consultez la [page de tarification Flow](https://flow.microsoft.com/pricing/) .

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Puis-je empêcher une autre personne d’utiliser les fonctionnalités payantes de Flow ?
Toute personne peut tester les fonctionnalités payantes de Microsoft Flow pendant 90 jours et ne pas supporter de frais. Toutefois, vous pouvez gérer entièrement l’attribution des licences perpétuelles payantes à l’intérieur de votre organisation par le biais du portail d’administration Office 365.

Comme avec les offres gratuites, si un individu choisit de s’inscrire à l’essai qui est une relation directe entre la personne et Microsoft, qui n’est pas nécessairement approuvée par votre entreprise.

## <a name="administration-of-flow"></a>Administration de Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Pourquoi l’icône de Flow apparaît-elle dans le lanceur d’applications Office 365 ?
Comme annoncé en août, Microsoft Flow est désormais un élément fondamental de la suite Office 365. Trois mois après cette annonce Microsoft Flow a été activé en tant que service dans le cadre de toutes les références SKU Office 365 existantes. À mesure que les utilisateurs dans le monde entier peuvent désormais utiliser Microsoft Flow, ils sont apparus dans le lanceur d’applications.

Consultez la section suivante si vous souhaitez supprimer la vignette Flow du lanceur d’applications par défaut.

### <a name="how-do-i-remove-microsoft-flow-from-the-app-launcher-for-my-organization"></a>Comment faire supprimer Microsoft Flow du lanceur d’applications pour mon organisation ?
Si un utilisateur a reçu une licence Flow plan 1 ou Flow plan 2, vous pouvez effectuer les étapes suivantes pour supprimer la licence Flow pour cet utilisateur, ce qui supprime l’icône Flow du lanceur d’applications :

1. Accédez au [portail d’administration Office 365](https://portal.microsoftonline.com/).
2. Dans la barre de navigation de gauche, sélectionnez **utilisateurs**, puis **utilisateurs actifs**.
3. Recherchez l’utilisateur pour lequel vous souhaitez supprimer la licence, puis sélectionnez son nom.
4. Dans le volet Détails de l’utilisateur, dans la section **licences du produit** , sélectionnez **modifier**.
5. Recherchez la licence appelée **Microsoft Flow plan 1** ou **Microsoft Flow plan 2**, définissez le bouton bascule sur **désactivé** , puis sélectionnez **Enregistrer**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Si un utilisateur a accès à Flow via sa licence Office 365 et Dynamics 365 plan, vous pouvez désactiver son accès aux fonctionnalités supplémentaires incluses dans ce plan en procédant comme suit :

1. Accédez au [portail d’administration Office 365](https://portal.microsoftonline.com/).
2. Dans la barre de navigation de gauche, sélectionnez **utilisateurs**, puis **utilisateurs actifs**.
3. Recherchez l’utilisateur pour lequel vous souhaitez supprimer l’accès, puis sélectionnez son nom.
4. Dans le volet Détails de l’utilisateur, dans la section **licences du produit** , sélectionnez **modifier**.
5. Développez la licence Office 365 ou Dynamics 365 de l’utilisateur, désactivez l’accès au service appelé **Flow pour office 365** ou **flow pour Dynamics 365** , puis sélectionnez **Enregistrer**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

La suppression en bloc de licences est également possible via PowerShell. Pour obtenir un exemple détaillé, consultez [supprimer des licences de comptes d’utilisateur avec Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx) .   Enfin, vous trouverez plus d’informations sur la suppression en bloc de services au sein d’une licence dans la [désactivation de l’accès aux services avec Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

La suppression de la licence ou du service Flow pour un utilisateur de votre organisation entraînera la suppression de l’icône de flow des emplacements suivants pour cet utilisateur :

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Lanceur d’applications Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Notez que cette opération supprime uniquement la vignette Flow par défaut. Un utilisateur peut toujours choisir d’utiliser Microsoft Flow en tant qu’individu.

### <a name="why-did-10000-licenses-for-microsoft-flow-show-up-in-my-office-365-tenant"></a>Pourquoi les licences 10 000 pour Microsoft Flow s’affichent-elles dans mon locataire Office 365 ?
Toute personne peut essayer Microsoft Flow plan 1 ou 2 pendant 90 jours, et ces licences d’essai représentent la capacité disponible pour les nouveaux utilisateurs de Flow dans votre locataire. Ces licences ne sont pas facturées. Plus précisément, il existe deux raisons possibles pour lesquelles vous pouvez voir une licence de capacité 10 000 (version d’évaluation) pour le workflow qui s’affiche dans le portail d’administration Office 365 :

1. Si au moins un utilisateur de votre locataire a participé à la préversion publique de Flow comprise entre le 2016 avril et le 2016 octobre, vous verrez 10 000 licences intitulées « Microsoft PowerApps et flux logiques ».
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Si au moins un utilisateur de votre locataire s’est inscrit à une version d’évaluation de Flow plan 2 en passant par l' **option 1** décrite dans la section [Comment les utilisateurs peuvent-ils s’inscrire à powerapps](#how-do-people-sign-up-for-flow) , vous verrez 10 000 licences intitulées « Microsoft Power Apps & Flow ».
   
    ![](./media/organization-q-and-a/licenses1.png)

Vous pouvez choisir d’attribuer des licences supplémentaires aux utilisateurs via le portail d’administration Office 365, mais notez qu’il s’agit de licences d’essai pour Microsoft Flow plan 2 et qu’elles expirent au bout de 90 jours après leur affectation à un utilisateur.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Est-ce gratuit ? Mes licences seront-elles facturées ?
Aucun utilisateur ne peut supporter aucuns frais pour votre organisation sans votre consentement expresse, donc aucune licence gratuite ou d’essai ne peut occasionner des frais pour votre organisation. En outre, ils n’utilisent pas non plus de quotas, tels que des quotas d’exécution.

### <a name="i-removed-the-microsoft-flow-free-license-and-users-can-still-access-flow"></a>J’ai supprimé le Microsoft Flow licence gratuite et les utilisateurs peuvent toujours accéder au Flow ?
La licence gratuite Microsoft Flow est incluse uniquement à des fins de suivi. Comme décrit dans la première section, il n’est pas possible d’empêcher une autre personne d’utiliser des Microsoft Flow à des fins individuelles. Ainsi, la présence d’un Microsoft Flow licence gratuite n’accorde pas ou ne supprime aucune fonctionnalité.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Pourquoi ne puis-je pas voir toutes les licences de Flow dans le portail d’administration Office 365 ?
Les utilisateurs peuvent utiliser Microsoft Flow en tant qu’individus ou dans le cadre de leur organisation. Les licences au niveau de l’organisation sont toujours visibles dans le portail Office 365. Toutefois, si un utilisateur s’inscrit à une version d’évaluation en tant qu’individu, cela signifie qu’il n’est pas géré par son administrateur Office 365 et qu’il n’apparaît pas dans le portail.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Comment une personne détermine-t-elle le plan sur lequel elle se trouve ?
Tout le monde peut voir le plan dont il dispose en visitant la page de tarification sur [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). Le plan ou l’essai sur lequel il se trouve est affiché ici.

### <a name="will-microsoft-flow-sign-up-impact-the-identities-in-my-organization"></a>L’inscription Microsoft Flow-t-elle un impact sur les identités de mon organisation ?
Si votre organisation dispose déjà d’un environnement Office 365 et que tous les utilisateurs de votre organisation disposent de comptes Office 365, la gestion des identités n’est pas affectée.

Si votre organisation dispose déjà d’un environnement Office 365, mais que tous les utilisateurs de votre organisation n’ont pas de comptes Office 365, nous créons un utilisateur dans le locataire et attribuons des licences en fonction de l’adresse de messagerie professionnelle ou scolaire de l’utilisateur. Cela signifie que le nombre d’utilisateurs que vous gérez à un moment donné augmente à mesure que les utilisateurs de votre organisation s’inscrivent au service.

Si votre organisation ne dispose pas d’un environnement Office 365 connecté à votre domaine de messagerie, il n’y a aucun changement dans la façon dont vous gérez l’identité. Les utilisateurs seront ajoutés à un nouveau répertoire utilisateur Cloud, et vous aurez la possibilité de prendre le contrôle de l’administrateur du locataire et de les gérer.

### <a name="a-new-tenant-was-created-by-microsoft-flow-how-do-i-manage-this"></a>Un nouveau locataire a été créé par Microsoft Flow, comment puis-je le gérer ?
Si un nouveau locataire a été créé par Microsoft Flow, vous pouvez revendiquer et gérer ce locataire en procédant comme suit :

1. Rejoignez le locataire en vous inscrivant à Flow à l’aide d’un domaine d’adresse de messagerie qui correspond au domaine de locataire que vous souhaitez gérer. Par exemple, si Microsoft a créé le locataire contoso.com, joignez le locataire avec une adresse de messagerie se terminant par @contoso.com.
2. Demandez le contrôle d’administration en vérifiant la propriété du domaine : une fois que vous êtes dans le locataire, vous pouvez vous promouvoir au rôle d’administrateur en vérifiant la propriété du domaine. Pour ce faire, procédez comme suit :    
   
   1. Accédez à [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Sélectionnez l’icône du lanceur d’applications en haut à gauche, puis choisissez admin.
   3. Lisez les instructions de la page **devenir l’administrateur** , puis choisissez **Oui, je souhaite être l’administrateur**.  
      
       **Remarque**: si cette option n’apparaît pas, cela signifie qu’un administrateur Office 365 est déjà en place.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Si je possède plusieurs domaines, puis-je contrôler le locataire Office 365 auquel les utilisateurs sont ajoutés ?
Si vous ne faites rien, un locataire est créé pour chaque domaine et sous-domaine de messagerie de l’utilisateur.

Si vous souhaitez que tous les utilisateurs soient dans le même locataire, quelle que soit leur extension d’adresse de messagerie :  

* Créez un locataire cible à l’avance ou utilisez un locataire existant. Ajoutez tous les domaines et sous-domaines existants que vous souhaitez consolider au sein de ce locataire. Ensuite, tous les utilisateurs avec des adresses de messagerie se terminant par ces domaines et sous-domaines rejoignent automatiquement le locataire cible lorsqu’ils s’inscrivent.

**Important**: il n’existe aucun mécanisme automatisé pris en charge pour déplacer des utilisateurs entre les locataires une fois qu’ils ont été créés. Pour en savoir plus sur l’ajout de domaines à un seul locataire Office 365, consultez [ajouter vos utilisateurs et votre domaine à office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Comment puis-je limiter la capacité des utilisateurs à accéder aux données d’entreprise de mon organisation ?
Microsoft Flow vous permet de créer des zones de données pour des données professionnelles et non professionnelles, comme indiqué ci-dessous. Une fois que ces stratégies de protection contre la perte de données sont implémentées, les utilisateurs ne peuvent pas concevoir ou exécuter de Flow qui combinent des données professionnelles et non professionnelles. Pour plus d’informations, consultez [stratégies de protection contre la perte de données (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

