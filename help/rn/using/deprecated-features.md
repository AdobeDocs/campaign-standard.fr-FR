---
title: Fonctionnalités obsolètes et supprimées de Campaign Standard
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
source-git-commit: 7622018bff9c8b8573dae139372bea697815849f
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 94%

---


# Fonctionnalités obsolètes et supprimées {#deprecated-and-removed-features}

Adobe évalue constamment les fonctionnalités des produits pour identifier celles qui devraient être remplacées par des solutions plus modernes afin d’offrir une plus grande valeur ajoutée, et ce en prenant toujours en compte la rétrocompatibilité

Lors de l’annonce de la suppression ou du remplacement imminent de fonctionnalités Campaign Standard, les règles suivantes s’appliquent :

* L’annonce de l’obsolescence vient en premier. Les fonctionnalités obsolètes sont encore disponibles pour les utilisateurs existants, elles ne seront plus améliorées ni documentées.
* La suppression de fonctionnalités obsolètes aura lieu au plus tôt dans la version suivante. La date de suppression prévue est annoncée sur cette page.

Cette procédure laisse aux clients au moins un cycle de publication pour s’adapter à une nouvelle version ou au successeur d’une fonctionnalité supprimée avant la suppression définitive.

>[!NOTE]
>Les versions et nouvelles fonctionnalités d’Adobe Campaign Standard sont répertoriées dans les [Notes de mise à jour](../../rn/using/release-notes.md).


## Fonctionnalités obsolètes {#deprecated-features}

Cette section répertorie les fonctions et fonctionnalités qui ont été désignées comme étant obsolètes dans les dernières versions de Campaign Standard.

En règle générale, les fonctionnalités qui doivent être supprimées dans une version ultérieure sont définies comme étant obsolètes dans un premier temps et une solution de remplacement est fournie. Ces fonctions et fonctionnalités ne sont plus disponibles pour les nouveaux clients de Campaign Standard ou ne doivent pas être utilisées dans le cadre d’une nouvelle implémentation. Elles sont également supprimées de la documentation du produit.

Il est conseillé aux clients d’évaluer dans quelle mesure ils utilisent la fonctionnalité dans leur déploiement actuel et d’envisager de modifier leur implémentation pour utiliser la solution de remplacement proposée. Consultez la version de suppression de la cible pour planifier votre environnement et les mises à jour de votre projet en conséquence.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifications push avec le SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> À compter de la version 20.1, le SDK v4 est obsolète. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">En savoir plus</a>.</p><br/>
   <p>Le <a href="https://aep-sdks.gitbook.io/docs/">SDK Mobile Adobe Experience Platform</a> (précédemment appelé v5) prendra exclusivement en charge les fonctionnalités Adobe Experience Cloud à venir.</p></br>
     <p>
     <em>Date de suppression prévue : le 30 septembre 2020</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Demandes d’accès à des informations personnelles - API et interface de Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À compter de la version 19.4 de Campaign, l’utilisation de l’API et de l’interface de Campaign pour les demandes d’accès à des informations personnelles et de suppression est obsolète. La suppression en deux étapes ne sera pas disponible. Utilisez <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Voir aussi <a href="https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html">Gestion de la confidentialité dans Campaign Standard</a>.</p>
  <p> 
  <em>Version de suppression de Cible : Version Campaign 20.4</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Conception d’email - Ancien éditeur d’email</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À compter de la version 19.0 de Campaign, l’ancien éditeur d’email est obsolète. Utilisez <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">le nouveau Concepteur d’email</a> pour créer et personnaliser le contenu de votre email. </p></br>
   <p>Lisez <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">cette section</a> pour apprendre à adapter vos modèles d’email pour le nouvel éditeur.</p></br>
  <p> 
  <em>Version de suppression de Cible : 2021</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Utilisateurs et sécurité - Entités géographiques</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À compter de la version 18.7, les entités géographiques sont obsolètes. Les entités organisationnelles et géographiques sont des constructions identiques dans Campaign. Les utilisateurs devront uniquement utiliser les entités organisationnelles pour définir une hiérarchie de permissions/d’accès aux données de l’utilisateur. <a href="https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html">En savoir plus</a>. Notez que, à partir de la version 18.7, cette fonctionnalité ne peut pas être implémentée sur les nouvelles instances Campaign Standard, ni sur les instances existantes sans entités géographiques créées.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Catégories supprimées {#removed-features}

Cette section répertorie les catégories et fonctionnalités qui ont été supprimées de Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK Creative pour Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le SDK Adobe Creative a été retiré. En conséquence, à compter de la version Camppaign 20.2, l’édition d’images avec le SDK Creative dans les emails de Campaign Standard n’est plus disponible.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Fin de compatibilité {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À partir de la version du printemps 2019 et de la version de Campaign 19.2, Microsoft Internet Explorer 11 n’est plus supporté avec Adobe Campaign et Adobe Experience Cloud. Passez à Microsoft Edge ou tout autre navigateur pris en charge. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">En savoir plus</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
