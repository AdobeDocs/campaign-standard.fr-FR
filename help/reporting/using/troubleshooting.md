---
title: Résolution des problèmes
seo-title: Résolution des problèmes
description: Résolution des problèmes
seo-description: Vous trouverez ici des questions courantes relatives aux rapports dynamiques.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: ht
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Résolution des problèmes{#troubleshooting}

Cette section contient des questions courantes relatives aux rapports dynamiques.

## Pour les ouvertures uniques et les clics uniques, le décompte de la ligne agrégée ne correspond pas à ceux de chaque ligne. {#unique-open-clicks-no-match}

Il s'agit d'un comportement attendu.
Prenons l'exemple suivant pour expliquer ce comportement.

Un email est envoyé aux profils P1 et P2.

P1 ouvre l'email deux fois le premier jour, puis trois fois le jour suivant.

P2, quant à lui, ouvre l'email une fois le premier jour et ne le rouvre pas les jours suivants.
Voici une représentation visuelle de l'interaction des profils avec l'email envoyé :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Jour</strong> <br /> </th> 
   <th align="center"> <strong>Ouvertures</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Jour 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Jour 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Pour comprendre le nombre total des ouvertures uniques, nous devons additionner les chiffres des lignes des **[!UICONTROL Ouvertures uniques]**, ce qui nous donne la valeur 3. Toutefois, comme l'email n'était ciblé que sur 2 profils, le taux d'ouverture devrait être de 150 %.

Pour ne pas obtenir de pourcentage supérieur à 100, la définition des **[!UICONTROL ouvertures uniques]** est le nombre de broadlogs uniques ouverts. Dans ce cas, même si P1 a ouvert l'email le jour 1 et le jour 2, les ouvertures uniques sont toujours égales à 1.

Cela donne le tableau suivant :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Jour</strong> <br /> </th> 
   <th align="center"> <strong>Ouvertures</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Jour 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Jour 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Les décomptes uniques reposent sur un sketch HLL, ce qui peut entraîner de légères imprécisions dans le cas de nombres élevés.

## Les décomptes des ouvertures ne correspondent pas à ceux de la base de données. {#open-counts-no-match-database}

Cela peut être dû au fait que la méthode heuristique est utilisée dans les rapports dynamiques pour tracker les ouvertures, même lorsque nous ne pouvons pas tracker l'action **[!UICONTROL Ouvrir]**.

Par exemple, si un utilisateur a désactivé les images sur son client et qu'il clique sur un lien dans l'email, l'**[!UICONTROL Ouverture]** peut ne pas être trackée par la base de données mais le **[!UICONTROL clic]** oui.

Par conséquent, les logs de tracking des **[!UICONTROL ouvertures]** peuvent ne pas avoir le même décompte que dans la base de données.

Ces occurrences sont ajoutées car **"un clic sur un email implique l'ouverture de l'email"**.

>[!NOTE]
>
>Comme les décomptes uniques reposent sur le sketch HLL, des incohérences mineures entre les décomptes sont possibles.

## Comment les décomptes des diffusions récurrentes/transactionnelles sont-ils calculés ?

Lors de l'utilisation de diffusions récurrentes et transactionnelles, les décomptes sont attribués aux diffusions parents et enfants.

Prenons comme exemple une diffusion récurrente appelée **R1** définie pour s'exécuter tous les jours le jour 1 (RC1), le jour 2 (RC2) et le jour 3 (RC3).

Supposons que seule une personne a ouvert toutes les diffusions enfants à plusieurs reprises. Dans ce cas, chaque diffusion enfant récurrente affichera le nombre 1 d'**[!UICONTROL Ouverture]**.

Toutefois, comme la même personne a cliqué sur toutes les diffusions, la diffusion récurrente parent aura également un décompte de 1 pour les **[!UICONTROL ouvertures uniques]**.

Après la version 19.2.1 d'Adobe Campaign Standard, la définition des **décomptes uniques** est changée du **nombre de personnes uniques interagissant avec la diffusion** au **nombre de messages uniques ayant fait l'objet d'une interaction**.

Avant la version 19.2.1 d'Adobe Campaign Standard, les rapports ressemblaient à ce qui suit :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Diffusion</strong> <br /> </th> 
   <th align="center"> <strong>Envoyés</strong> <br /> </th> 
   <th align="center"> <strong>Delivrés</strong> <br /> </th>
   <th align="center"> <strong>Ouvertures</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Après la version 19.2.1 d'Adobe Campaign Standard, les rapports ressemblent à ce qui suit :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Diffusion</strong> <br /> </th> 
   <th align="center"> <strong>Envoyés</strong> <br /> </th> 
   <th align="center"> <strong>Delivrés</strong> <br /> </th>
   <th align="center"> <strong>Ouvertures</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Quelle est la signification des couleurs dans le tableau des rapports ? {#reports-color-signification}

Les couleurs affichées dans vos rapports sont aléatoires et ne peuvent pas être personnalisées. Elles représentent une barre de progression et s'affichent pour mettre en évidence la valeur maximale atteinte dans vos rapports.

Dans l'exemple ci-dessous, la cellule est de la même couleur car sa valeur est 100 %.

![](assets/troubleshooting_1.png)

Si vous définissez la **mise en forme conditionnelle** sur personnalisée, lorsque la valeur atteint la limite supérieure, la cellule devient verte. En revanche, si elle atteint la limite inférieure, elle devient rouge.

Par exemple, ici, nous définissons la **limite supérieure** sur 500 et la **limite inférieure** sur 0.

![](assets/troubleshooting_2.png)