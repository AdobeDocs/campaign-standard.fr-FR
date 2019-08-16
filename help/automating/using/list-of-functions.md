---
title: Liste des fonctions
seo-title: Liste des fonctions
description: Liste des fonctions
seo-description: L'outil d'édition de requêtes permet d'utiliser des fonctions avancées afin de réaliser des filtrages complexes.
page-status-flag: never-activated
uuid: fd50fc99-1e7a-479b-beb7-1f246b419d46
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 3cdbe962-1c59-4cd8-b29e-36aa2562fac6
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Liste des fonctions{#list-of-functions}

## A propos des fonctions {#about-functions}

L'outil d'édition de requêtes permet d'utiliser des fonctions avancées afin de réaliser des filtrages complexes. Pour cela, la palette de l'outil contient l'élément **[!UICONTROL Expression]** que vous pouvez utiliser dans l'espace de travail. L'utilisation de cet élément est détaillée dans une [section spécifique](../../automating/using/advanced-expression-editing.md).

Cet élément vous permet de saisir manuellement vos conditions. Vous pouvez y utiliser les fonctions définies dans les sections ci-après.

Plusieurs types de fonctions sont disponibles, en fonction des résultats souhaités et du types des données manipulées :

* Dates
* Géomarketing
* numériques
* autres fonctions
* des agrégats.
* manipulation de chaînes
* tri

## Dates  {#dates}

Les fonctions de date sont utilisées pour manipuler des valeurs de date ou d'heure.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> Ajoute un nombre de jours à une date<br /> </td> 
   <td> AddDays(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Ajoute un nombre d'heures à une date<br /> </td> 
   <td> AddHours(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Ajoute un nombre de minutes à une date<br /> </td> 
   <td> AddMinutes(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Ajoute un nombre de mois à une date<br /> </td> 
   <td> AddMonths(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Ajoute un nombre de secondes à une date<br /> </td> 
   <td> AddSeconds(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> Ajoute un nombre d'années à une date<br /> </td> 
   <td> AddYears(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Renvoie la date uniquement (avec heure à zéro)<br /> </td> 
   <td> DateOnly(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Renvoie le nombre représentant le jour de la date<br /> </td> 
   <td> Day(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Renvoie le numéro du jour dans l'année de la date<br /> </td> 
   <td> DayOfYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Renvoie la date correspondant à la date courante moins n jours<br /> </td> 
   <td> DaysAgo(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Renvoie la date (entier aaaammjj) correspondant à la date courante moins n jours<br /> </td> 
   <td> DaysAgoInt(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Nombre de jours entre deux dates<br /> </td> 
   <td> DaysDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Renvoie l'ancienneté en jours d'une date<br /> </td> 
   <td> DaysOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Renvoie la date système courante du serveur<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> Renvoie l'heure de la date<br /> </td> 
   <td> Hour(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Renvoie le nombre d'heures entre deux dates<br /> </td> 
   <td> HoursDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Convertit des date et heure locales en format UTC.<br /> </td> 
   <td> LocalToUTC(&lt;date&gt;, &lt;Fuseau horaire&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> Renvoie les minutes de la date<br /> </td> 
   <td> Minute(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Renvoie le nombre de minutes entre deux dates<br /> </td> 
   <td> MinutesDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> Renvoie le nombre représentant le mois de la date<br /> </td> 
   <td> Month(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Renvoie la date correspondant à la date courante moins n mois<br /> </td> 
   <td> MonthsAgo(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Renvoie le nombre de mois entre deux dates<br /> </td> 
   <td> MonthsDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Renvoie l'ancienneté en mois d'une date<br /> </td> 
   <td> MonthsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> Renvoie les secondes de la date<br /> </td> 
   <td> Second(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> Retourne la date la plus ancienne. </td> 
   <td> Oldest(&lt;Date&gt;, &lt;Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Renvoie le nombre de secondes entre deux dates<br /> </td> 
   <td> SecondsDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Enlève un nombre de jours à une date<br /> </td> 
   <td> SubDays(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Enlève un nombre d'heures à une date<br /> </td> 
   <td> SubHours(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Enlève un nombre de minutes à une date<br /> </td> 
   <td> SubMinutes(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Enlève un nombre de mois à une date<br /> </td> 
   <td> SubMonths(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Enlève un nombre de secondes à une date<br /> </td> 
   <td> SubSeconds(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Enlève un nombre d'années à une date<br /> </td> 
   <td> SubYears(&lt;date&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Convertit une date + heure en date seule<br /> </td> 
   <td> ToDate(&lt;date + heure&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Convertit une chaîne en date + heure<br /> </td> 
   <td> ToDateTime(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Convertit une chaîne en date + fuseau horaire.<br /> Exemple : ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Tehran")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Arrondit une date + heure à la seconde<br /> </td> 
   <td> TruncDate(@lastModified, &lt;nombre de secondes&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Arrondit une date + heure à la seconde près<br /> </td> 
   <td> TruncDateTZ(&lt;date&gt;, &lt;nombre de secondes&gt;, &lt;fuseau horaire&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Arrondit une date au trimestre<br /> </td> 
   <td> TruncQuarter(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Arrondit la partie heure à la seconde<br /> </td> 
   <td> TruncTime(&lt;date&gt;, &lt;nombre de secondes&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Arrondit une date à la semaine<br /> </td> 
   <td> TruncWeek(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Arrondit une date + heure au premier janvier de l'année<br /> </td> 
   <td> TruncYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Renvoie le numéro du jour dans la semaine de la date<br /> </td> 
   <td> WeekDay(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> Renvoie le nombre représentant l'année de la date<br /> </td> 
   <td> Year(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> Renvoie le nombre représentant l'année et le mois de la date<br /> </td> 
   <td> YearAndMonth(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> Renvoie le nombre d'années entre deux dates<br /> </td> 
   <td> YearsDiff(&lt;date de fin&gt;, &lt;date de début&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Renvoie l'ancienneté en années d'une date<br /> </td> 
   <td> YearsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Géomarketing  {#geomarketing}

Les fonctions de géomarketing sont utilisées pour manipuler des valeurs géographiques.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distance</strong><br /> </td> 
   <td> Renvoie la distance en kilomètres entre deux points définis par leur longitude et latitude (exprimées en degrés)<br /> </td> 
   <td> Distance(&lt;Longitude A&gt;, &lt;Latitude A&gt;, &lt;Longitude B&gt;, &lt;Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numériques  {#numerical}

Les fonctions numériques sont utilisées pour convertir du texte en nombres.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Renvoie la valeur absolue d'un nombre<br /> </td> 
   <td> Abs(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Renvoie le plus petit entier supérieur ou égal à un nombre<br /> </td> 
   <td> Ceil(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Renvoie le plus grand entier supérieur ou égal à un nombre<br /> </td> 
   <td> Floor(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> Renvoie le plus grand de deux nombres<br /> </td> 
   <td> Greatest(&lt;nombre 1&gt;, &lt;nombre 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Renvoie le plus petit de deux nombres<br /> </td> 
   <td> Least(&lt;nombre 1&gt;, &lt;nombre 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Renvoie le reste de la division entiers de n1 par n2<br /> </td> 
   <td> Mod(&lt;nombre 1&gt;, &lt;nombre 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percent</strong><br /> </td> 
   <td> Renvoie la proportion en pourcentage entre deux nombres<br /> </td> 
   <td> Percent(&lt;nombre 1&gt;, &lt;nombre 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Random</strong><br /> </td> 
   <td> Renvoie une valeur aléatoire<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Arrondit un nombre à n décimales près<br /> </td> 
   <td> Round(&lt;nombre&gt;, &lt;nombre de décimales&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Renvoie le signe du nombre<br /> </td> 
   <td> Sign(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Convertit un entier en réel<br /> </td> 
   <td> ToDouble(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Convertit un réel en entier 64 bits<br /> </td> 
   <td> ToInt64(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Convertit un réel en entier<br /> </td> 
   <td> ToInteger(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Tronque n1 à n2 décimales<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Autres  {#others}

Ce tableau contient les autres fonctions disponibles.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Renvoie la valeur 1 si la condition est vérifiée. Sinon, renvoie la valeur 2<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;valeur 1&gt;), Else(&lt;valeur 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Efface le Flag dans la valeur<br /> </td> 
   <td> ClearBit(&lt;identifiant&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Renvoie la valeur 2 si la valeur 1 est nulle ou vide (null), sinon renvoie la valeur 1<br /> </td> 
   <td> Coalesce(&lt;valeur 1&gt;, &lt;valeur 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Renvoie la valeur 3 si valeur 1 = valeur 2, sinon renvoie la valeur 4<br /> </td> 
   <td> Decode(&lt;valeur 1&gt;, &lt;valeur 2&gt;, &lt;valeur 3&gt;, &lt;valeur 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Renvoie la valeur 1 (ne peut être utilisée qu'en paramètre de la fonction Case)<br /> </td> 
   <td> Else(&lt;valeur 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extrait le domaine d'une adresse email<br /> </td> 
   <td> GetEmailDomain(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Récupère l'URL du serveur de page miroir<br /> </td> 
   <td> GetMirrorURL(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Renvoie la valeur 1 si l'expression est vraie, sinon renvoie la valeur 2<br /> </td> 
   <td> Iif(&lt;condition&gt;, &lt;valeur 1&gt;, &lt;valeur 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Indique si le Flag est présent dans la valeur<br /> </td> 
   <td> IsBitSet(&lt;identifiant&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Renvoie la valeur 2 si la chaîne est vide, sinon renvoie la valeur 3<br /> </td> 
   <td> IsEmptyString(&lt;chaîne&gt;, &lt;valeur 2&gt;, &lt;valeur 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Renvoie la chaîne vide si l'argument n'a pas de valeur (null)<br /> </td> 
   <td> NoNull(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Renvoie le numéro de la ligne<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Force le Flag dans la valeur<br /> </td> 
   <td> SetBit(&lt;identifiant&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetVar</strong><br /> </td> 
   <td> Définit une variable.<br /> </td> 
   <td> SetVar(&lt;variable&gt;, &lt;expression&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Convertit un nombre en booléen<br /> </td> 
   <td> ToBoolean(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> Renvoie la valeur 1 si l'expression est vérifiée. Sinon, renvoie la valeur 2 (ne peut être utilisée qu'en paramètre de la fonction Case)<br /> </td> 
   <td> When(&lt;condition&gt;, &lt;valeur 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Retourne un nouvel UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Chaîne  {#string}

Les fonctions de chaîne sont utilisées pour manipuler un ensemble de chaînes.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Indique si tous les paramètres sont non nuls et non vides<br /> </td> 
   <td> AllNonNull2(&lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indique si tous les paramètres sont non nuls et non vides<br /> </td> 
   <td> AllNonNull3(&lt;chaîne&gt;, &lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ascii</strong><br /> </td> 
   <td> Renvoie la valeur ascii du premier caractère de la chaîne<br /> </td> 
   <td> Ascii(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Renvoie le caractère de code ascii n<br /> </td> 
   <td> Char(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Retourne la position de la chaîne 2 dans la chaîne 1<br /> </td> 
   <td> Charindex(&lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Retourne le nombre de caractères dans une chaîne.<br /> </td> 
   <td> DataLength(&lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Renvoie la nième (de 1 à n) ligne de la chaîne<br /> </td> 
   <td> GetLine(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Renvoie le troisième paramètre si les deux premiers paramètres sont égaux sinon renvoie le dernier paramètre<br /> </td> 
   <td> IfEquals(&lt;chaîne&gt;, &lt;chaîne&gt;, &lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Indique si le memo passé en paramètre est nul<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Concatène les deux chaînes passées en paramètres. Un espace est ajouté entre chaque chaîne dans la valeur renvoyée.<br /> </td> 
   <td> JuxtWords(&lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concatène les trois chaînes passées en paramètres. Un espace est ajouté entre chaque chaîne dans la valeur renvoyée.<br /> </td> 
   <td> JuxtWords3(&lt;chaîne&gt;, &lt;chaîne&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Renvoie la chaîne complétée à gauche<br /> </td> 
   <td> LPad(&lt;chaîne&gt;, &lt;nombre&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Renvoie les n premiers caractères de la chaîne<br /> </td> 
   <td> Left(&lt;chaîne&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> Renvoie la longueur de la chaîne<br /> </td> 
   <td> Length(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Renvoie la chaîne en minuscules<br /> </td> 
   <td> Lower(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Ote les espaces à gauche de la chaîne<br /> </td> 
   <td> Ltrim(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Renvoie une représentation hexadécimale de la clé MD5 d'une chaîne<br /> </td> 
   <td> Md5Digest(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Indique si le mémo contient la chaîne passée en paramètre<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Renvoie la chaîne complétée à droite<br /> </td> 
   <td> RPad(&lt;chaîne&gt;, &lt;nombre&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Remplace toutes les occurrences d'une valeur de chaîne spécifiée (2e paramètre) par une autre valeur de chaîne (3e paramètre) dans une chaîne (1er paramètre).<br /> </td> 
   <td> Replace(&lt;Chaîne&gt;, &lt;Chaîne&gt;, &lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Renvoie les n derniers caractères de la chaîne<br /> </td> 
   <td> Right(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Ote les espaces à droite de la chaîne<br /> </td> 
   <td> Rtrim(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcule le hachage standard <strong>SHA256</strong> pour une chaîne UTF8 donnée.<br /> </td> 
   <td> Sha256Digest(&lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcule le hachage standard <strong>SHA384</strong> pour une chaîne UTF8 donnée.<br /> </td> 
   <td> Sha384Digest(&lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcule le hachage standard <strong>SHA512</strong> pour une chaîne UTF8 donnée.<br /> </td> 
   <td> Sha512Digest(&lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Renvoie la chaîne avec la première lettre de chaque mot en majuscule<br /> </td> 
   <td> Smart(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> Extrait la sous-chaîne débutant au caractère n1 de la chaîne et de longueur n2<br /> </td> 
   <td> Substring(&lt;chaîne&gt;, &lt;départ&gt;, &lt;longueur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Convertit le nombre en chaîne<br /> </td> 
   <td> ToIntlString(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Convertit le nombre en chaîne<br /> </td> 
   <td> ToString(&lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Renvoie la chaîne en majuscules<br /> </td> 
   <td> Upper(&lt;chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Renvoie la clé étrangère d'un lien passée en premier paramètre, si les deux autres paramètres sont égaux<br /> </td> 
   <td> VirtualLink(&lt;nombre&gt;, &lt;nombre&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Renvoie la clé étrangère (texte) d'un lien passée en premier paramètre, si les deux autres paramètres sont égaux<br /> </td> 
   <td> VirtualLinkStr(&lt;chaîne&gt;, &lt;nombre&gt;, &lt;nombre&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Décrypte une valeur cryptée au format HEX avec le préfixe "<strong>x</strong>" (1er paramètre) à l'aide d'une clé au format HEX (2ème paramètre) et d'un vecteur d'initialisation au format HEX (3ème paramètre)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;Chaîne&gt;, &lt;Chaîne&gt;, &lt;Chaîne&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Cryptage au moyen d'un algorithme AES (mode bloc CBC), une chaîne de caractères (1er paramètre) avec une clé (2e paramètre) et un vecteur d'initialisation (3e paramètre). La clé et le vecteur d'initialisation doivent être indiqués sous une représentation hexadécimale (commençant par <strong>\x</strong>). Le résultat sera sous forme hexadécimale sans <strong>\x</strong>.<br /> Notez que la taille de la clé peut être de 128, 192 ou 256 bits (16, 24 ou 32 caractères hexadécimaux), mais nous vous conseillons d'utiliser 256 bits et un ID randomisé de la même longueur que la clé.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;chaîne&gt;, &lt;chaîne&gt;, &lt;chaîne&gt;)<br /> Par exemple : encryption_aescbcEncrypt(johndoe@exemple.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## des agrégats.{#aggregates}

Les fonctions d'agrégation sont disponibles uniquement lors de l'[ajout de données additionnelles](../../automating/using/query.md#enriching-data) depuis une activité de **[!UICONTROL Requête]** d'un workflow.

Elles sont utilisées pour effectuer des calculs sur un ensemble de valeurs.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Moyenne<br /> </td> 
   <td> Renvoie la moyenne d'une colonne de type numérique.<br /> </td> 
   <td> Avg(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Comptage (sauf NULL)<br /> </td> 
   <td> Compte les valeurs non nulles d'une colonne.<br /> </td> 
   <td> Count(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Comptage intégral<br /> </td> 
   <td> Compte toutes les valeurs (valeurs nulles et doublons inclus).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Comptage distinct<br /> </td> 
   <td> Compte les valeurs distinctes non nulles d'une colonne.<br /> </td> 
   <td> Countdistinct(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Maximum<br /> </td> 
   <td> Renvoie la valeur maximum d'une colonne de type numérique, chaîne ou date.<br /> </td> 
   <td> Max(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Minimum<br /> </td> 
   <td> Renvoie la valeur minimum d'une colonne de type numérique, chaîne ou date.<br /> </td> 
   <td> Min(&lt;valeur&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Somme<br /> </td> 
   <td> Renvoie la somme des valeurs d'une colonne de type numérique.<br /> </td> 
   <td> Sum(&lt;valeur&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Représentation  {#representation}

Les fonctions de représentation sont utilisées pour classer des valeurs.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nom</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
   <td> <strong>Syntaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Applique un tri descendant<br /> </td> 
   <td> Desc(&lt;valeur 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Trie le résultat au sein de la partition<br /> </td> 
   <td> OrderBy(&lt;valeur 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Partitionne le résultat d'une requête sur une table<br /> </td> 
   <td> PartitionBy(&lt;valeur 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Génère un numéro de ligne en fonction de la partition de la table et d'un ordre de tri. Fonction non supportée pour MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;valeur 1&gt;), OrderBy(&lt;valeur 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

