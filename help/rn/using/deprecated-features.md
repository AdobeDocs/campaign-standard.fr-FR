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
source-git-commit: 490908e5fe0810c0a07c73fef5040ddb42983019

---


# Fonctionnalités obsolètes et supprimées {#deprecated-and-removed-features}

Adobe évalue constamment les capacités du produit afin d’identifier les anciennes fonctionnalités qui doivent être remplacées par des alternatives plus modernes afin d’améliorer la valeur globale du client, toujours en tenant compte de la compatibilité ascendante.

Pour communiquer la suppression ou le remplacement imminent des fonctionnalités de Campaign Standard, les règles suivantes s’appliquent :

* L&#39;annonce de la dépréciation vient en premier. Bien que des fonctionnalités obsolètes puissent toujours être disponibles pour les utilisateurs existants, elles ne seront pas améliorées, ni documentées.
* La suppression des fonctionnalités obsolètes aura lieu dans la version suivante au plus tôt. La date cible réelle de suppression est annoncée dans cette page.

Ce processus permet aux clients d’adapter au moins un cycle de publication à une nouvelle version ou à un successeur d’une fonctionnalité obsolète, avant une suppression réelle.

>[!NOTE]
>Les versions et nouvelles fonctionnalités d’Adobe Campaign Standard sont répertoriées dans les Notes [de](../../rn/using/release-notes.md)mise à jour.


## Fonctions obsolètes {#deprecated-features}

Cette section répertorie les fonctionnalités qui ont été marquées comme obsolètes avec les dernières versions de Campaign Standard.

En règle générale, les fonctionnalités qui doivent être supprimées dans une version ultérieure sont définies comme obsolètes en premier, avec une alternative fournie. Ces fonctionnalités ne sont plus disponibles pour les nouveaux clients de Campaign Standard ou ne doivent pas être utilisées pour une nouvelle implémentation. Ils sont également supprimés de la documentation du produit.

Il est conseillé aux clients de vérifier s’ils utilisent la fonctionnalité ou la fonctionnalité dans leur déploiement actuel et de planifier de modifier leur mise en oeuvre pour utiliser l’alternative fournie. Veuillez vous reporter à la date de suppression cible pour planifier votre environnement et les mises à jour du projet en conséquence.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifications Push avec SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Depuis la version 20.1, le SDK v4 est obsolète. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">En savoir plus</a>.</p><br/>
   <p>Le SDK <a href="https://aep-sdks.gitbook.io/docs/">mobile</a> Adobe Experience Platform (précédemment appelé v5) prendra exclusivement en charge les fonctionnalités et fonctionnalités Adobe Experience Cloud à venir.</p></br>
     <p>Date de suppression cible :30 septembre 2020</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK pour Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK a été mis hors service. En conséquence, l’édition d’images optimisée par Creative SDK dans les courriers électroniques de Campaign Standard est obsolète à partir de la version 20.1.</p></br>
  <p> Date de suppression cible :Mars 2020 - Version 20.2 de Campaign</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Demandes de confidentialité - API et interface de Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Depuis la version 19.4 de Campaign, l’utilisation de l’API et de l’interface Campaign pour les demandes d’accès et de suppression est obsolète. Utilisez <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Voir aussi Gestion <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">de la confidentialité dans Campaign Standard</a>.</p>
  <p> Date de suppression cible : Juillet 2020 - Version 20.5 de Campaign</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Conception de courrier électronique - Éditeur de courrier électronique hérité</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Depuis la version 19.0 de Campaign, l’éditeur de courrier électronique hérité est obsolète. Utilisez <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">le nouveau concepteur</a> de messagerie pour créer et personnaliser votre contenu de messagerie. </p></br>
   <p>Lisez <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">cette section</a> pour savoir comment adapter vos modèles de courrier électronique au nouvel éditeur.</p></br>
  <p> Date de suppression cible :Octobre 2020 - Version de Campaign 20.6</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Utilisateurs et sécurité - Unités géographiques</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A compter de la version 18.7, les unités géographiques sont obsolètes. Les unités organisationnelles et géographiques sont des éléments identiques dans Campaign. Les utilisateurs doivent utiliser les unités d’organisation seules pour créer leur hiérarchie d’accès aux données/autorisations utilisateur. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">En savoir plus</a>. Notez que les nouvelles instances de Campaign Standard, ainsi que les instances existantes sans unités géographiques créées, ne peuvent pas avoir cette fonctionnalité mise en oeuvre à partir de la version 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## Fin de compatibilité {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign et Adobe Experience Cloud ont abandonné la prise en charge de Microsoft Internet Explorer 11 à compter du printemps 2019 et de la version 19.2 de Campaign. Passez à Microsoft Edge ou tout autre navigateur pris en charge. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">En savoir plus</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
