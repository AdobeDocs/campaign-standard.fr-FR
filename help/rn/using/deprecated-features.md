---
solution: Campaign Standard
product: campaign
title: Fonctionnalités obsolètes et supprimées de Campaign Standard
description: Cette page répertorie les fonctionnalités obsolètes et supprimées d’Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: becaf20fefb6fce05db0824baa69670f810966dc
workflow-type: tm+mt
source-wordcount: '734'
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

Il est conseillé aux clients d’évaluer dans quelle mesure ils utilisent la fonctionnalité dans leur déploiement actuel et d’envisager de modifier leur implémentation pour utiliser la solution de remplacement proposée. Référez-vous à la version de suppression prévue pour planifier les mises à jour de votre environnement et de vos projets en conséquence.

<table> 
 <thead> 
 <tr> 
   <th> <strong>Optimisation prédictive de l’objet</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> À compter du 15 décembre 2020, la fonctionnalité prédictive de l’objet est abandonnée.</p><br/>
   <p>Nous vous suggérons d’exploiter les fonctionnalités de messagerie optimisée par IA pour analyser et estimer les taux d’ouverture, les délais d’envoi optimaux et le taux probable d’exécution en fonction des mesures d’engagement historiques. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">En savoir plus</a></p></br>
     <p>
     <em>Date de suppression prévue : avril 2021</em></p>
     </td> 
  </tr> 
  </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifications push avec le SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A compter de la version Campaign 20.1, le SDK v4 est obsolète. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">En savoir plus</a>.</p><br/>
   <p>Le <a href="https://aep-sdks.gitbook.io/docs/">SDK Mobile Adobe Experience Platform</a> (précédemment appelé v5) prendra exclusivement en charge les fonctionnalités Adobe Experience Cloud à venir.</p>
   <p>Découvrez comment migrer du SDK v4 vers le SDK Adobe Experience Platform Mobile <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">dans cette page</a>.</p></br>
     <p>
     <em>Date de suppression prévue : 31 août 2021</em></p>
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
   <p>Voir aussi <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=fr">Gestion des demandes d’accès à des informations personnelles</a>.</p>
  <p> 
  <em>Date de suppression prévue : avril 2021</em></p>
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
   <td> <p>À compter de la version 19.0 de Campaign, l’ancien éditeur d’email est obsolète. Utilisez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html?lang=fr">le Concepteur d’email de Campaign</a> pour créer et personnaliser le contenu de votre email. </p></br>
   <p>Lisez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">cette section</a> pour apprendre à adapter vos modèles d’email pour le nouvel éditeur.</p></br>
  <p> 
  <em>Date de suppression prévue : fin 2021</em></p>
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
   <td> <p>A compter de la version Campaign 18.7, les unités géographiques sont obsolètes. Les entités organisationnelles et géographiques sont des constructions identiques dans Campaign. Les utilisateurs devront uniquement utiliser les entités organisationnelles pour définir une hiérarchie de permissions/d’accès aux données de l’utilisateur. <a href="https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html">En savoir plus</a>. Notez que, à partir de la version 18.7, cette fonctionnalité ne peut pas être implémentée sur les nouvelles instances Campaign Standard, ni sur les instances existantes sans entités géographiques créées.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Catégories supprimées {#removed-features}

Cette section répertorie les catégories et fonctionnalités qui ont été supprimées de Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Score de propension avec Triggers Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le <b>score de propension</b> a été retiré d’Adobe Experience Cloud Triggers. Cette option a donc été supprimée d’Adobe Campaign Standard. Pour éviter toute valeur obsolète de score de propension dans les schémas d’enrichissement, nous vous recommandons de les mettre à jour afin de récupérer les dernières modifications et de republier les déclencheurs existants. Pour plus d’informations, voir la section <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html?lang=fr">Publication d’un déclencheur dans Campaign</a>.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK Creative pour Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] a été retiré. De ce fait, à compter de la version Campaign 20.2, l’édition d’images avec [!DNL Creative SDK] dans les emails de Campaign Standard n’est plus disponible.</p></br>
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
   <td> <p>À partir de la version du printemps 2019 et de la version de Campaign 19.2, Microsoft Internet Explorer 11 n’est plus supporté avec Adobe Campaign et Adobe Experience Cloud. Passez à Microsoft Edge ou tout autre navigateur pris en charge. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html?lang=fr">En savoir plus</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
