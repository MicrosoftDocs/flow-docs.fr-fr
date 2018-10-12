---
title: 'Exemple : Utiliser des flux de processus métier (Guide du développeur pour Dynamics 365 Customer Engagement) | Microsoft Docs'
description: L’exemple montre comment utiliser par programmation des flux de processus métier tels que la récupération d’instances de flux de processus métier pour un enregistrement d’entité, la récupération du chemin d’accès actif d’une instance de flux de processus métier et de ses phases de processus et le changement de phase active.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6fe2b6d600d86dfd807dbb1ef794a1f428f26fbf
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690051"
---
# <a name="sample-work-with-business-process-flows"></a>Exemple : Utiliser des flux de processus métier

Cet exemple montre comment utiliser par programmation des flux de processus métier tels que la récupération d’instances de flux de processus métier pour un enregistrement d’entité, la récupération du chemin d’accès actif d’une instance de flux de processus métier et de ses phases de processus et le changement de phase active. Pour plus d’informations sur ces concepts, consultez [Utiliser des flux de processus métier à l’aide de code](business-process-flows-code.md).  

 Vous pouvez télécharger cet exemple à partir de la page [Exemple : Utiliser des flux de processus métier](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Prérequis  
 Avant d’exécuter l’exemple :  

1. Vous devez avoir accès à un environnement Common Data Service for Apps.  

2. Vous devez disposer des privilèges appropriés sur les entités Prospect, Opportunité et Workflow et sur les enregistrements d’entité de définition de flux de processus métier utilisés dans cet exemple.  

3. Vous devez disposer de Visual Studio version 2015 ou ultérieure pour exécuter l’exemple.  

4. Vous devez avoir une connexion Internet pour télécharger l’exemple de projet et restaurer les packages NuGet utilisés dans celui-ci.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Ce que fait cet exemple  

1.  Il crée un exemple d’enregistrement Prospect. Cette opération crée automatiquement une instance du flux de processus métier « Processus de vente prospect-opportunité » pour l’enregistrement Prospect.  

2.  Il convertit l’enregistrement Prospect en enregistrement Opportunité.  


4.  Il récupère les instances de flux de processus métier associées à l’enregistrement « Opportunité » à l’aide du message `RetrieveProcessInstances`. Le premier enregistrement dans la collection retournée est l’instance de flux de processus métier active pour l’enregistrement d’opportunité, en l’occurrence « Processus de vente prospect-opportunité ».  

5.  Il récupère le chemin d’accès actif et les phases de processus pour l’instance « Processus de vente prospect-opportunité » à l’aide du message `RetrieveActivePath`.  

6.  Il récupère la phase active pour l’instance « Processus de vente prospect-opportunité » et invite l’utilisateur à indiquer s’il faut passer à la phase suivante. Une fois la confirmation recueillie, il définit la phase suivante dans le chemin d’accès actif en tant que phase active pour l’instance « Processus de vente prospect-opportunité ».  

7.  Enfin, il invite l’utilisateur à indiquer s’il faut supprimer les enregistrements créés au cours de l’exécution de l’exemple.  

     Voici la sortie de l’exemple :  

    ![Exemple de sortie](media/work-with-bpf-sample-output.png "Exemple de sortie")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Exécuter l’exemple  

1. [Téléchargez](https://go.microsoft.com/fwlink/p/?LinkId=846108) l’exemple de projet Visual Studio WorkWithBPF, puis extrayez-le dans un dossier sur votre ordinateur.  

2. Recherchez le fichier `WorkWithBPF.sln` dans votre dossier d’extraction, puis ouvrez-le dans Visual Studio.  

3. L’exemple de projet utilise des packages NuGet qui doivent être restaurés avant que l’exemple ne soit exécuté. Vérifiez que la restauration automatique de packages NuGet est activée dans Visual Studio. Pour plus d’informations, consultez [Activation et désactivation de la restauration des packages NuGet](https://go.microsoft.com/fwlink/?linkid=846106).  

    Vous pouvez également sélectionner **Projet** > **Gérer les Packages NuGet**, puis sélectionner **Restaurer** pour restaurer manuellement les packages utilisés dans l’exemple.  

4. Appuyez sur F5 ou sélectionnez **Déboguer** > **Démarrer le débogage**.  

5. Si vous n’avez pas encore exécuté un des exemples, vous devez entrer des informations pour exécuter le code, sinon, entrez le numéro d’une des instances que vous avez configurées.  


   |                                 Invite                                  |                                                                                             Description                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Entrer un nom de serveur et un port Dynamics 365 [crm.dynamics.com]       | Tapez le nom de votre serveur Dynamics 365. La valeur par défaut est Dynamics 365 (en ligne) (crm.dynamics.com) en Amérique du Nord.<br /><br /> Exemple : <br />crm5.dynamics.com |
   | Cette organisation est-elle provisionnée dans Microsoft Online Services ? (o/n) [n] |                                                 Tapez **o** s’il s’agit d’une organisation provisionnée dans Microsoft Online Services. Sinon, tapez **n**.                                                  |
   |                          Entrer le domaine\nom d’utilisateur                          |                                                                                    Tapez votre compte Microsoft.                                                                                     |
   |                             Entrer le mot de passe                              |                      Tapez votre mot de passe. Les caractères s’affichent sous la forme « \* » dans la fenêtre. Votre mot de passe est enregistré de manière sécurisée dans le Gestionnaire d’informations d’identification Microsoft en vue de sa réutilisation.                       |
   |                Spécifier un numéro d’organisation (1-n) [1]                 |                      À partir de la liste affichée des organisations auxquelles vous appartenez, tapez le numéro correspondant. La valeur par défaut est 1, soit la première organisation dans la liste.                       |


6. L’exemple effectue les opérations décrites dans [Ce que fait cet exemple](#what-this-sample-does) et peut vous inviter à définir des options supplémentaires.  

7. Une fois l’exemple terminé, appuyez sur Entrée pour fermer la fenêtre de console.  

