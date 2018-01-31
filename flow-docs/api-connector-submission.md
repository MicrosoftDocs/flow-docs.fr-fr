---
title: Soumettre pour certification en tant que connecteur API | Microsoft Docs
description: "Lorsqu’un connecteur est certifié, il devient disponible pour tous les utilisateurs de Microsoft Flow, PowerApps et Logic Apps."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 33283e1f682190f6aea02cb61a31cb43b42d5289
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="submit-your-connectors-for-microsoft-certification"></a>Soumettre vos connecteurs pour certification par Microsoft
Pour rendre des connecteurs personnalisés publiquement disponibles pour tous les utilisateurs dans Microsoft Flow, Azure Logic Apps et Microsoft PowerApps, vous devez les soumettre à Microsoft à des fins de révision, de validation et d’approbation avant publication. 

## <a name="certification-criteria"></a>Critères de certification
| Capacité | Détails | Obligatoire ou recommandé |
| --- | --- | --- |
| Application SaaS |Correspond à un scénario utilisateur parfaitement adapté à Logic Apps, Microsoft Flow et PowerApps. |Obligatoire |
| Type d’authentification |Votre API doit prendre en charge l’authentification OAuth2, par clé API ou De base. |Obligatoire |
| Support |Vous devez fournir un contact de support permettant aux clients d’obtenir de l’aide. |Obligatoire |
| Disponibilité et temps d’activité |Le temps d’activité de votre application est au moins de 99,9 %. |Recommandé |
|  | | |

Si, n’étant pas un partenaire Microsoft ou un éditeur de logiciels indépendant (ISV), vous souhaitez certifier et publier un connecteur, vous devez soit être propriétaire du service sous-jacent, soit présenter des droits explicites d’utiliser l’API.

Pour être certifié, votre connecteur fait l’objet d’une révision en deux phases : 

1. Validation de fonctionnalité
   
    Le connecteur personnalisé doit être évalué sur les points suivants :
   
   * Swagger non valide ou erreurs JSON dans la section Définition de l’Assistant Connecteur personnalisé
   * Erreurs de validation de runtime ou de schéma dans la section Test de l’Assistant
     
     Par conséquent, chaque opération est soigneusement testée dans Microsoft Flow, Logic Apps et PowerApps pour toutes les erreurs côté client.
2. Validation du contenu
   
    Un connecteur bien écrit utilise des noms conviviaux et des descriptions pour chaque entité. Nous évaluons votre Swagger pour nous assurer que chaque opération, chaque paramètre d’entrée et chaque attribut de réponse contient ce qui suit :
   
   * [Résumé](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#summary)
   * [Description](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#description)
   * [Informations de visibilité](https://docs.microsoft.com/azure/logic-apps/custom-connector-openapi-extensions#visibility)

## <a name="nominate-and-submit-your-connector-to-microsoft-for-certification"></a>Nominer et soumettre votre connecteur à Microsoft pour certification
Pour demander une certification, procédez comme suit :

1. **Nomination**
   
   1. [Soumettez votre nomination](https://go.microsoft.com/fwlink/?linkid=848754).
   2. Signez à l’accord de confidentialité et l’accord de partenariat que vous recevez. 
      Microsoft exige ces accords signés avant de continuer. 
      Nous pouvons ensuite vérifier si votre connecteur répond aux critères de certification. 
   3. Si votre connecteur est approuvé, Microsoft vous en informe et vous fournit des instructions pour l’intégration.
2. **Révision**
   
   1. Envoyez à votre contact de nomination les informations suivantes pour révision :
      
      * Fichier OpenAPI décrivant votre API.
      * Fichier d’icône (.png ou .jpg) représentant votre connecteur (l’icône doit présenter un logo d’environ 160 pixels à l’intérieur d’un carré de 230 pixels. Un logo blanc sur fond coloré est préférable).
      * Couleur de votre icône au format hexadécimal, qui doit correspondre à l’arrière-plan coloré du fichier d’icône.
      * Un compte de test pour la validation
      * Un contact de support
   2. Si nous avons besoin d’informations supplémentaires, nous vous contacterons.
3. **Publication**
   
    Après validation de la fonctionnalité et du contenu du connecteur, nous proposons celui-ci pour déploiement dans l’ensemble des produits et régions. En règle générale, le processus de certification et de déploiement prend jusqu’à 3 semaines.
   
    Par défaut, tous les connecteurs sont publiés en tant que « Premium ». 
    Si vous avez créé votre application avec Azure, vous pouvez demander que votre connecteur soit répertorié en tant que connecteur « Standard » disponible pour tous les utilisateurs ayant acquis une offre Office 365 Entreprise. 
    Pour plus d’informations, renseignez-vous auprès de votre contact de nomination.

