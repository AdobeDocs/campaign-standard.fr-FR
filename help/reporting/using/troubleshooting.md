---
title: Résolution des problèmes
seo-title: Résolution des problèmes
description: Résolution des problèmes
seo-description: Trouvez ici des questions courantes liées à la création de rapports dynamiques.
page-status-flag: jamais activé
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: beneat
products: SG_ CAMPAIGN/STANDARD
audience: création de rapports
content-type: référence
topic-tags: dépannage
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Résolution des problèmes{#troubleshooting}

Cette section contient des questions courantes relatives aux rapports dynamiques.

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

Il s'agit d'un comportement attendu.
Nous pouvons utiliser l'exemple suivant pour expliquer ce comportement.

Un courrier électronique est envoyé aux profils P 1 et P 2.

P 1 ouvre le courriel deux fois le premier jour, puis les heures de l'arborescence le second jour.

Par contre, P 2 ouvre le courriel une fois le premier jour et ne l'ouvre pas dans les jours suivants.
Voici une représentation visuelle de l'interaction des profils avec le courriel envoyé :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Ouvertures (Opens)</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. Cependant, puisque le courrier électronique n'était ciblé que sur 2 profils, le taux d'ouverture devrait afficher 150 %.

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. Dans ce cas, même si P 1 a ouvert le courriel le jour 1 et le Jour 2, ses ouvertures uniques sont toujours 1.

Ceci entraînera le tableau suivant :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Ouvertures (Opens)</strong><br /> </th> 
   <th align="center"> <strong>Ouvertures uniques</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Les valeurs uniques sont basées sur une esquisse basée sur HLL, ce qui peut entraîner de légères imprécisions à un nombre élevé.

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>Comme les valeurs uniques sont basées sur une esquisse basée sur HLL, les incohérences mineures entre les décomptes peuvent être expérimentées.

## Comment le nombre de distributions périodiques/transactionnelles est-il calculé ?

Lors de l'utilisation de remises périodiques et transactionnelles, les décomptes sont attribués aux distributions parents et enfants.

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

Supposons que seule une personne ait ouvert toutes les livraisons enfants à plusieurs reprises. In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

Avant la version 19.2.1 d'Adobe Campaign Standard, les rapports ressemblait à ce qui suit :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Diffusion</strong> <br /> </th> 
   <th align="center"> <strong>Sent</strong> <br /> </th> 
   <th align="center"> <strong>Delivrés</strong> <br /> </th>
   <th align="center"> <strong>Ouvertures (Opens)</strong><br /> </th> 
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

Après la version Adobe Campaign Standard 19.2.1, les rapports ressemblent à ce qui suit :

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Diffusion</strong> <br /> </th> 
   <th align="center"> <strong>Sent</strong> <br /> </th> 
   <th align="center"> <strong>Delivrés</strong> <br /> </th>
   <th align="center"> <strong>Ouvertures (Opens)</strong><br /> </th> 
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

## What is the colors' signification in my reports' table? {#reports-color-signification}

Les couleurs affichées dans vos rapports sont aléatoires et ne peuvent pas être personnalisées. Elles représentent une barre de progression et s'affichent pour vous aider à mieux mettre en évidence la valeur maximale atteinte dans vos rapports.

Dans l'exemple ci-dessous, la cellule est de la même couleur car sa valeur est 100 %.

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. En revanche, si elle atteint la limite inférieure, elle devient bidirectionnelle.

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)