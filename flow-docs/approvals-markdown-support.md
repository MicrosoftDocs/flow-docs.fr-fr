---
title: Utiliser la démarque pour mettre en forme les approbations de Microsoft Flow | Microsoft Docs
description: Apprenez à utiliser la démarque pour mettre en forme Microsoft Flow demandes d’approbation.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545312"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Utiliser la démarque dans Microsoft Flow les demandes d’approbation
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cet article explique comment utiliser la syntaxe de [démarque](https://en.wikipedia.org/wiki/Markdown) pour ajouter des tables et une mise en forme enrichies à vos demandes d’approbation.

## <a name="headers"></a>En-têtes

Structurez vos commentaires à l’aide d’en-têtes. Les en-têtes segmentent les commentaires plus longs, ce qui les rend plus faciles à lire.

Commencez une ligne par un caractère de hachage `#` pour définir un titre. Organisez vos notes avec des sous-titres en démarrant une ligne avec des caractères de hachage supplémentaires, par exemple `####`. Jusqu’à six niveaux d’en-tête sont pris en charge.

**Tels**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Venir**

![Exporter le workflow](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragraphes et sauts de ligne

Facilitez la lecture de votre texte en le divisant par des paragraphes ou des sauts de ligne. Entrez deux espaces avant le saut de ligne pour commencer un nouveau paragraphe, ou entrez deux sauts de ligne consécutivement pour commencer un nouveau paragraphe.   
   
**Tels**

Ajoutez des lignes entre votre texte à l’aide de la touche entrée.
Cela permet d’améliorer la lisibilité de votre texte.

**Résultat :**    
Ajoutez des lignes entre votre texte à l’aide de la touche entrée.      
Cela permet d’améliorer la lisibilité de votre texte.


**Exemple 2**

Ajoutez deux espaces avant la fin de la ligne. (espace, espace)     
Cela ajoute de l’espace entre les paragraphes.

**Venir**  
Ajoutez deux espaces avant la fin de la ligne.   

Cela ajoute de l’espace entre les paragraphes.
  

## <a name="lists"></a>Suivant

Organiser les éléments associés avec des listes. Vous pouvez ajouter des listes triées avec des nombres ou des listes non triées avec des puces simples.

Les listes triées commencent par un nombre suivi d’un point pour chaque élément de liste. Les listes non triées commencent par un `*`. Commencez chaque élément de liste sur une nouvelle ligne. Dans un fichier ou un widget de démarque, entrez deux espaces avant le saut de ligne pour commencer un nouveau paragraphe, ou entrez deux sauts de ligne consécutivement pour commencer un nouveau paragraphe.   

### <a name="ordered-or-numbered-lists"></a>Listes triées ou numérotées

**Tels**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Venir**

1. Premier élément.
2. Deuxième élément.
3. Troisième élément.

### <a name="bullet-lists"></a>Listes à puces

**Tels**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Venir**

- Élément 1
- Élément 2
- Élément 3

### <a name="nested-lists"></a>Listes imbriquées

**Tels**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Venir**  

1. Premier élément.

    - Élément 1
    - Élément 2
    - Élément 3
2. Deuxième élément.
    - Élément imbriqué 1
    - Élément imbriqué 2
    - Élément imbriqué 3


## <a name="links"></a>Liées

Les URL HTTP et HTTPs sont automatiquement mises en forme en tant que liens. 

Vous pouvez définir des liens hypertexte de texte pour votre URL en utilisant la syntaxe de lien de démarque standard :

```Markdown
[Link Text](Link URL)
```

**Tels**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Venir**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Liens d’ancrage

Les ID d’ancrage sont assignés à tous les en-têtes lorsqu’ils sont rendus au format HTML. L’ID est le texte du titre, les espaces étant remplacés par des tirets (-) et tous les minuscules.

**Tels**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Venir**

Syntaxe d’un lien d’ancrage vers une section...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
L’ID est en minuscules, et le lien respecte la casse. Veillez donc à utiliser des minuscules, même si l’en-tête lui-même utilise majuscules.


## <a name="tables"></a>Elles

Organisez les données structurées avec des tables. 

- Placer chaque ligne de table sur sa propre ligne 
- Séparer les cellules d’un tableau à l’aide du caractère de barre verticale `|` 
- Les deux premières lignes d’une table définissent les en-têtes de colonnes et l’alignement des éléments dans le tableau.
- Utiliser les signes deux-points (`:`) lors de la Division de l’en-tête et du corps des tableaux pour spécifier l’alignement des colonnes (gauche, Centre, droite) 
- Pour commencer une nouvelle ligne, utilisez la balise break HTML (`<br/>`) (fonctionne dans un wiki mais pas ailleurs)  
- Veillez à terminer chaque ligne par une CR ou un LF. 

**Tels**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Venir**  

| Titre 1 | Titre 2 | Titre 3 |  
|-----------|:---------:|-----------:|  
| Cellule a1 | Cellule a2 | Cellule a3 |  
| Cellule B1 | Cellule B2 | Cellule B3<br/>deuxième ligne de texte |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Accentuation (gras, italique, barré)  

Vous pouvez mettre en évidence le texte en appliquant le gras, l’italique ou le barré aux caractères : 
- Pour appliquer l’italique : entourez le texte d’un astérisque `*` ou un trait de soulignement `_`   
- Pour appliquer l’attribut gras : Placez le texte entre deux astérisques `**`.    
- Pour appliquer le style barré : Placez le texte entre deux caractères tilde `~~`.   

Combinez ces éléments pour appliquer plusieurs caractères d’accentuation au texte.    

**Tels**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Venir**

Utilisez l' _accent_ sur les commentaires pour exprimer des opinions **solides** et faire état des <s>corrections</s>   
**_Texte en gras et en italique_**    
**~~Texte en gras et barré~~**  


## <a name="special-characters"></a>Caractères spéciaux

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Stockéesyntaxe</th>
<th width="350px">Exemples/remarques</th>
</tr>



<tr>
<td>
<p>Pour insérer l’un des caractères suivants, préfixe avec une barre oblique inverse :</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Exemples d’insertion de caractères spéciaux
<p>Entrez ```\\``` pour accéder à \\ </p>
<p>Entrez ```\_``` pour accéder à _ </p>
<p>Entrez ```\#``` pour accéder à \# </p>
<p>Entrez ```\(``` pour accéder à \( </p>
<p>Entrez ```\.``` pour accéder à \. </p>
<p>Entrez ```\!``` pour accéder à \! </p>
</td>
</tr>

</tbody>
</table>
