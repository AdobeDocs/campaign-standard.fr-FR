---
title: Dimensions et mesures de Campaign dans Analytics
description: Découvrez les différentes dimensions proposées dans Adobe Analytics afin de commencer le tracking de vos diffusions email depuis Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '322'
ht-degree: 100%

---

# Dimensions et mesures de Campaign dans Analytics{#campaign-dimensions-and-metrics-in-analytics}

L&#39;intégration d&#39;Adobe Campaign et d&#39;Adobe Analytics permet le tracking des performances des diffusions email directement dans Adobe Analytics.

Les **[!UICONTROL dimensions]** de Campaign qui figurent dans Analytics sont répertoriées ci-dessous :

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Identifiant de la campagne<br /> </td> 
   <td> Nom interne de la campagne affiché dans Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Libellé de la campagne<br /> </td> 
   <td> Libellé de la campagne affiché dans Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Identifiant de la diffusion<br /> </td> 
   <td> Nom interne de la diffusion affiché dans Campaign.<br /> Par exemple, DM1 est une diffusion récurrente planifiée pour envoyer des diffusions enfants toutes les semaines. Les diffusions DM2, DM3 et DM4 sont envoyées les trois premières semaines. La dimension Identifiant de la diffusion affiche ensuite les résultats de chaque diffusion, à savoir DM1 à DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Libellé de la diffusion<br /> </td> 
   <td> Libellé de la diffusion affiché dans Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Identifiant de la diffusion exécutée<br /> </td> 
   <td> Nom interne de la diffusion affiché dans Campaign. Cette dimension concerne uniquement la diffusion en cours d'exécution dans Campaign.<br /> Par exemple, DM1 est une diffusion récurrente planifiée pour envoyer des diffusions enfants toutes les semaines. Les diffusions DM2, DM3 et DM4 sont envoyées les trois premières semaines. La dimension Identifiant de la diffusion exécutée affiche ensuite les résultats des diffusions exécutées, à savoir les diffusions enfants DM2, DM3 et DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Libellé de la diffusion exécutée<br /> </td> 
   <td> Libellé de la diffusion affiché dans Campaign. Cette dimension concerne uniquement la diffusion en cours d'exécution dans Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Les **[!UICONTROL mesures]** de Campaign qui figurent dans Analytics sont répertoriées ci-dessous :

<table> 
 <thead> 
  <tr> 
   <th> Mesure<br /> </th> 
   <th> Définition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Ont cliqué<br /> </td> 
   <td> Nombre de clics sur un contenu dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> Nombre de messages envoyés avec succès, par rapport au nombre total de messages envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ayant ouvert<br /> </td> 
   <td> Nombre d'ouvertures d'un message dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Envoyés<br /> </td> 
   <td> Nombre total d’envois pour la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total de bounces<br /> </td> 
   <td> Nombre total d'erreurs cumulées lors des diffusions et du traitement automatique des retours par rapport au nombre total de messages envoyés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures uniques<br /> </td> 
   <td> Nombre de destinataires ayant ouvert la diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics uniques<br /> </td> 
   <td> Nombre de destinataires ayant cliqué sur un contenu dans une diffusion.<br /> </td> 
  </tr> 
  <tr> 
   <td> Désabonnement<br /> </td> 
   <td> Nombre de clics sur le lien de désabonnement.<br /> </td> 
  </tr> 
 </tbody> 
</table>
