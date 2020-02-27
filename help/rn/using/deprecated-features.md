---
title: Fonctions obsolètes et supprimées de Campaign Standard
description: Cette page répertorie les fonctionnalités obsolètes et supprimées d’Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# Fonctions obsolètes et supprimées de Campaign Standard {#deprecated-and-removed-features}

Adobe évalue constamment les capacités du produit afin d’identifier les anciennes fonctionnalités qui doivent être remplacées par des alternatives plus modernes afin d’améliorer la valeur globale du client, toujours en tenant compte de la compatibilité ascendante.

Pour communiquer la suppression ou le remplacement imminent des fonctionnalités de Campaign Standard, les règles suivantes s’appliquent :

* L&#39;annonce de la dépréciation vient en premier. Bien que des fonctionnalités obsolètes puissent toujours être disponibles pour les utilisateurs existants, elles ne seront pas améliorées, ni documentées.
* La suppression des fonctionnalités obsolètes aura lieu dans la version suivante au plus tôt. La date cible réelle de suppression est annoncée dans cette page.

Ce processus permet aux clients d’adapter au moins un cycle de publication à une nouvelle version ou à un successeur d’une fonctionnalité obsolète, avant une suppression réelle.

>[!NOTE]
>Les versions et nouvelles fonctionnalités d’Adobe Campaign Standard sont répertoriées dans les Notes [de](../../rn/using/release-notes.md)mise à jour.


## Fonctions obsolètes {#deprecated-features}

Cette section répertorie les fonctionnalités qui ont été marquées comme obsolètes avec les dernières versions de Campaign Standard. En règle générale, les fonctionnalités qui doivent être supprimées dans une version ultérieure sont définies comme obsolètes en premier, avec une alternative fournie. Ces fonctionnalités ne sont plus disponibles pour les nouveaux clients de Campaign Standard ou ne doivent pas être utilisées pour une nouvelle implémentation. Ils sont également supprimés de la documentation du produit.

Il est conseillé aux clients de vérifier s’ils utilisent la fonctionnalité ou la fonctionnalité dans leur déploiement actuel et de planifier de modifier leur mise en oeuvre pour utiliser l’alternative fournie. Veuillez vous reporter à la date de suppression cible pour planifier votre environnement et les mises à jour du projet en conséquence.

<table> 
 <thead> 
  <tr> 
   <th> Release<br /> </th> 
   <th> Caractéristiques<br /> </th> 
   <th> Replacement<br /> </th> 
    <th> Date de suppression cible<br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Notifications Push<br /> </td> 
    <td> Le SDK <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">mobile</a> Adobe Experience Platform (précédemment appelé v5) prendra exclusivement en charge les fonctionnalités et fonctionnalités Adobe Experience Cloud à venir. <br /> </td> 
    <td> September 30, 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Creative SDK pour Campaign Standard<br /> </td> 
  <td> Adobe Creative SDK a été mis hors service. Par conséquent, l’édition d’images optimisée par Creative SDK dans les courriers électroniques de Campaign Standard est désormais obsolète.<br /> </td>
  <td> Mars 2020 - Version 20.2 de Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> 19.4<br /> </td> 
   <td> Demandes de confidentialité - API et interface de Campaign<br /> </td>
    <td> L'utilisation de l'API et de l'interface de Campaign pour les demandes d'accès et de suppression est obsolète. Utilisez le service Privacy Core. <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">En savoir plus</a>. Voir aussi Gestion <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">de la confidentialité dans Campaign Standard</a>.<br /> </td>
    <td>  Juillet 2020 - Version 20.5 de Campaign<br /> </td> 
  </tr>
  <tr> 
   <td> 19.0<br /> </td> 
   <td> Conception de courrier électronique - Éditeur de courrier électronique hérité<br /> </td>
    <td> L’éditeur de courrier électronique hérité est désormais obsolète. Utilisez le nouveau concepteur de courrier électronique pour créer et personnaliser votre contenu de courrier électronique. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">En savoir plus</a>. Lisez <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">cette section</a> pour savoir comment adapter vos modèles de courrier électronique au nouvel éditeur.<br /> </td>
    <td> Octobre 2020 - Version de Campaign 20.6<br /> </td> 
  </tr>
  <tr> 
   <td> 18.7<br /> </td> 
   <td> Utilisateurs et sécurité - Unités géographiques<br /> </td>
    <td> Les unités organisationnelles et géographiques sont des éléments identiques dans Campaign. Les utilisateurs doivent utiliser les unités d’organisation seules pour créer leur hiérarchie d’accès aux données/autorisations utilisateur. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">En savoir plus</a>. Please note that new Campaign Standard instances, as well as existing instances with no geographical units created, cannot have this capability implemented starting 18.7 release.<br /> </td>
    <td> N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Fin de compatibilité {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> Release<br /> </th> 
   <th> Caractéristiques<br /> </th> 
   <th> Replacement<br /> </th> 
 </tr> 
 </thead> 
 <tbody>
<tr> 
   <td> 19.2<br /> </td> 
   <td> Demandes de confidentialité - API et interface de Campaign<br /> </td>
    <td> Adobe Campaign et Adobe Experience Cloud ont abandonné la prise en charge de Microsoft Internet Explorer 11 à compter du printemps 2019 et de la version 19.2 de Campaign. Passez à Microsoft Edge ou tout autre navigateur pris en charge.  <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">En savoir plus</a>.<br /> </td>
    <td><br /> </td> 
  </tr>
  </tbody> 
</table>
