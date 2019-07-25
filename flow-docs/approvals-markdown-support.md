---
title: Utiliser Markdown pour formater les approbations Microsoft Flow | Microsoft Docs
description: Apprenez à utiliser Markdown pour formater les demandes d’approbation Microsoft Flow.
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
ms.openlocfilehash: 7611ccb8bba9f2647402df46753de284016d7cd4
ms.sourcegitcommit: 014f64bcc4aed27794d5c7efc2eca241d271518e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58656128"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Utiliser Markdown dans des demandes d’approbation Microsoft Flow

Cet article explique comment utiliser la syntaxe [Markdown](https://en.wikipedia.org/wiki/Markdown) pour ajouter une mise en forme enrichie et des tables à vos demandes d’approbation.

## <a name="headers"></a>En-têtes

Structurez vos commentaires à l’aide d’en-têtes. Les en-têtes permettent de segmenter les commentaires et les rendent ainsi plus lisibles.

Commencez une ligne par un caractère de hachage `#` pour définir un titre. Organisez vos remarques à l’aide de sous-titres en commençant une ligne par des caractères de hachage supplémentaires, par exemple `####`. Jusqu'à six niveaux d’en-têtes sont pris en charge.

**Exemple :**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Résultat :**

![Exporter le flux](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Paragraphes et sauts de ligne

Facilitez la lecture de votre texte en l’espaçant à l’aide de paragraphes ou de sauts de ligne. Insérez deux espaces avant le saut de ligne pour commencer un nouveau paragraphe, ou deux sauts de ligne consécutivement pour commencer un nouveau paragraphe.   
   
**Exemple**

Ajoutez les lignes entre votre texte avec la touche Entrée.
Cela permet de mieux espacer votre texte et de le rendre plus lisible.

**Résultat :**    
Ajoutez les lignes entre votre texte avec la touche Entrée.      
Cela permet de mieux espacer votre texte et de le rendre plus lisible.


**Exemple 2**

Ajoutez deux espaces avant la fin de la ligne.(espace, espace)     
Ceci permet d’ajouter de l’espace entre des paragraphes.

**Résultat :**  
Ajoutez deux espaces avant la fin de la ligne.   

Ceci permet d’ajouter de l’espace entre des paragraphes.
  

## <a name="lists"></a>Listes

Organisez les éléments connexes à l’aide de listes. Vous pouvez ajouter des listes triées contenant des numéros ou des listes non triées avec des puces uniquement.

Les listes triées commencent par un numéro, suivi d’un point pour chaque élément de la liste. Les listes non triées commencent par un `*`. Commencez chaque élément de la liste sur une nouvelle ligne. Dans un fichier ou un widget Markdown, insérez deux espaces avant le saut de ligne pour commencer un nouveau paragraphe, ou deux sauts de ligne consécutivement pour commencer un nouveau paragraphe.   

### <a name="ordered-or-numbered-lists"></a>Listes triées ou numérotées

**Exemple :**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Résultat :**

1. First item.
2. Second item.
3. Third item.

### <a name="bullet-lists"></a>Listes à puces

**Exemple :**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Résultat :**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listes imbriquées

**Exemple :**
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

**Résultat :**  

1. First item.

    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
    - Nested item 2
    - Nested item 3


## <a name="links"></a>Liens

Les URL HTTP et HTTPS sont automatiquement mises en forme sous forme de liens. 

Vous pouvez définir des liens au format texte pour votre URL à l’aide de la syntaxe Markdown standard :

```Markdown
[Link Text](Link URL)
```

**Exemple :**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Résultat :**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Liens d’ancrage

Des ID d’ancrage sont attribués à tous les en-têtes lors du rendu au format HTML. L’ID représente le texte du titre, les espaces étant remplacés par des tirets (-) et toutes les lettres sont des minuscules.

**Exemple :**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Résultat :**

Syntaxe d’un lien d’ancrage pour une section.

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
L’ID est entièrement composé de minuscules, et le lien respecte la casse. Veillez par conséquent à utiliser des minuscules même si l’en-tête lui-même est constitué de majuscules.


## <a name="tables"></a>Tableaux

Organisez les données structurées à l’aide de tableaux. 

- Placez chaque ligne du tableau sur sa propre ligne 
- Séparez les cellules du tableau à l’aide de la barre verticale `|` 
- Les deux premières lignes d’un tableau définissent les en-têtes de colonne et l’alignement des éléments dans le tableau
- Utilisez les deux-points (`:`) pour séparer l’en-tête et le corps des tableaux afin de spécifier l’alignement de la colonne (gauche, centre, droite) 
- Pour insérer une nouvelle ligne, utilisez la balise de saut de ligne HTML (`<br/>`) (fonctionne uniquement dans un document Wiki)  
- Veillez à terminer chaque ligne avec un retour chariot (CR) ou un saut de ligne (LF). 

**Exemple :**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Résultat :**  

| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Accentuation (gras, italique, barré)  

Vous pouvez mettre en évidence un texte en appliquant aux caractères un style gras, italique ou barré : 
- Pour mettre en italique : entourez le texte d’un astérisque `*` ou d’un trait de soulignement `_`.   
- Pour mettre en gras : entourez le texte d’astérisques doubles `**`.    
- Pour barrer un texte : entourez le texte de deux caractères tilde `~~`.   

Combinez ces éléments pour appliquer plusieurs styles au texte.    

**Exemple :**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Résultat :**

Use _emphasis_ in comments to express **strong** opinions and point out <s>corrections</s>   
**_Bold, italicized text_**    
**~~Bold, strike-through text~~**  


## <a name="special-characters"></a>Caractères spéciaux

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Syntaxe</th>
<th width="350px">Exemple/notes</th>
</tr>



<tr>
<td>
<p>Pour insérer un des caractères suivants, ajoutez en préfixe une barre oblique inverse :</p>

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
<td>Quelques exemples d’insertion de caractères spéciaux
<p>Entrez ```\\``` pour obtenir \\ </p>
<p>Entrez ```\_``` pour obtenir _ </p>
<p>Entrez ```\#``` pour obtenir \# </p>
<p>Entrez ```\(``` pour obtenir \( </p>
<p>Entrez ```\.``` pour obtenir \. </p>
<p>Entrez ```\!``` pour obtenir \! </p>
</td>
</tr>

</tbody>
</table>
