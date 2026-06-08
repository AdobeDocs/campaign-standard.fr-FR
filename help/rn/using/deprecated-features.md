---
title: Fonctionnalités obsolètes et supprimées de Campaign Standard
description: Cette page répertorie les fonctionnalités obsolètes et supprimées d’Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
TQID: https://experienceleague.adobe.com/S430SyqHAam2JE4LQppJUy3xuEdS6lw1qGQE9viVCS8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b631758a-142d-425f-b9aa-f756d85cb979
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 998
ht-degree: 100%

---

# Fonctionnalités obsolètes et supprimées {#deprecated-and-removed-features}

Adobe évalue constamment les fonctionnalités des produits pour identifier celles qui devraient être remplacées par des solutions plus modernes afin d&#39;offrir une plus grande valeur ajoutée, et ce en prenant toujours en compte la rétrocompatibilité

Lors de l&#39;annonce de la suppression ou du remplacement imminent de fonctionnalités Campaign Standard, les règles suivantes s&#39;appliquent :

* L’annonce de l’obsolescence vient en premier. Les fonctionnalités obsolètes sont encore disponibles pour les utilisateurs existants, elles ne seront plus améliorées ni documentées.
* La suppression de fonctionnalités obsolètes aura lieu au plus tôt dans la version suivante. La date de suppression cible est annoncée sur cette page.

Cette procédure laisse aux clients au moins un cycle de publication pour s’adapter à une nouvelle version ou au successeur d’une fonctionnalité supprimée avant la suppression définitive.

>[!NOTE]
>Les versions et nouvelles fonctionnalités d’Adobe Campaign Standard sont répertoriées dans les [Notes de mise à jour](../../rn/using/release-notes.md).


## Fonctionnalités obsolètes {#deprecated-features}

Cette section répertorie les fonctions et fonctionnalités qui ont été désignées comme étant obsolètes dans les dernières versions de Campaign Standard.

En règle générale, les fonctionnalités qui doivent être supprimées dans une version ultérieure sont définies comme étant obsolètes dans un premier temps et une solution de remplacement est fournie. Ces fonctions et fonctionnalités ne sont plus disponibles pour les nouveaux clients de Campaign Standard ou ne doivent pas être utilisées dans le cadre d&#39;une nouvelle implémentation. Elles sont également supprimées de la documentation du produit.

Il est conseillé aux clients d&#39;évaluer dans quelle mesure ils utilisent la fonctionnalité dans leur déploiement actuel et d&#39;envisager de modifier leur implémentation pour utiliser la solution de remplacement proposée. Référez-vous à la version de suppression cible pour planifier les mises à jour de votre environnement et de vos projets en conséquence.



<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK V4 pour les applications mobiles</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La prise en charge des SDK Adobe Experience Platform Mobile version 4 a pris fin le 31 août 2021. Si vous utilisez toujours cette version héritée du SDK dans Adobe Campaign Standard, vous devez mettre à jour votre implémentation avec le SDK Adobe Experience Platform <strong>avant fin juin 2024</strong>. </p></br>
   <p>Lisez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=fr">cet article</a> pour savoir comment adapter votre implémentation et passer au dernier SDK Experience Platform.</p></br>
   <p><strong>Attention</strong> : le SDK V4 ne sera plus pris en charge dans Campaign Standard à compter de la fin du mois de juin 2024.</p>
  </td> 
  </tr> 
 </tbody> 
</table>




<table> 
 <thead> 
  <tr> 
   <th> <strong>Conception d'email - Ancien éditeur d'email</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À compter de la version 19.0 de Campaign, l'ancien éditeur d'email est obsolète. Utilisez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html?lang=fr">le concepteur d’e-mails de Campaign</a> pour créer et personnaliser le contenu de votre email. </p></br>
   <p>Lisez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html?lang=fr">cette section</a> pour apprendre à adapter vos modèles d'email pour le nouvel éditeur.</p></br>
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
   <td> <p>À compter de la version 18.7 de Campaign, les entités géographiques sont obsolètes. Les entités organisationnelles et géographiques sont des constructions identiques dans Campaign. Les utilisateurs devront uniquement utiliser les entités organisationnelles pour définir une hiérarchie d'autorisations/d'accès aux données de l'utilisateur. <a href="https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html">En savoir plus</a>. Notez que, à partir de la version 18.7, cette fonctionnalité ne peut pas être implémentée sur les nouvelles instances Campaign Standard, ni sur les instances existantes sans entités géographiques créées.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Fonctionnalités supprimées {#removed-features}

Cette section répertorie les fonctionnalités supprimées de Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Intégration au service Audience Destinations</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> À compter de la version 21.3 de Campaign Standard, l’intégration au service Audience Destinations est obsolète.  Elle a été supprimée.</p>
   <p>Pour une nouvelle mise en œuvre, vous ne pouvez plus intégrer Audience Destinations à Adobe Campaign Standard. Vous avez toutefois la possibilité d’intégrer Campaign et Adobe Experience Platform par l’intermédiaire des sources et des destinations. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=fr">En savoir plus</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Intégration au connecteur d’Adobe Experience Platform</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> À compter de la version 21.3 de Campaign Standard, l’intégration au connecteur d’Adobe Experience Platform est obsolète.  Elle a été supprimée.</p>
   <p>Pour une nouvelle mise en œuvre, vous ne pouvez plus intégrer le connecteur d’Adobe Experience Platform à Adobe Campaign Standard. Vous avez toutefois la possibilité d’intégrer Campaign et Adobe Experience Platform par l’intermédiaire des sources et des destinations. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=fr">En savoir plus</a>.</p>
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
   <td> <p> À compter de la version 20.1 de Campaign, le SDK v4 est obsolète. Il a été supprimé. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.htmlhtml?lang=fr">En savoir plus</a>.</p><br/>
   <p>Le <a href="https://developer.adobe.com/client-sdks/documentation/">SDK Mobile Adobe Experience Platform</a> (auparavant appelé v5) prend maintenant exclusivement en charge les fonctionnalités Adobe Experience Cloud à venir.</p>
   <p>Après le 31 août 2021, les clients peuvent continuer à télécharger et à utiliser les SDK version 4, mais il n’y a plus d’assistance clientèle ni d’accès aux forums.</p>
   <p>Découvrez comment migrer du SDK v4 vers le SDK mobile Adobe Experience Platform <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=fr">dans cette page</a>.</p></br>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Demandes d’accès à des informations personnelles - API et interface Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>À compter de la version 21.2 de Campaign, l’utilisation de l’API et de l’interface de Campaign pour les demandes d’accès à des informations personnelles et de suppression est obsolète. La suppression de profil en 2 étapes n’est plus disponible. Utilisez <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy Core Service</a>.</p></br>
   <p>Voir aussi <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=fr">Gestion des demandes d'accès à des informations personnelles</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Optimisation prédictive de l'objet</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> À compter d'avril 2021, la fonctionnalité Optimisation prédictive de l'objet est désactivée.</p><br/>
   <p>Nous vous suggérons d'exploiter les fonctionnalités de messagerie optimisée par IA pour analyser et estimer les taux d'ouverture, les délais d'envoi optimaux et le taux probable d'exécution en fonction des mesures d'engagement historiques. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html?lang=fr">En savoir plus</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Score de propension avec Triggers Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le <b>score de propension</b> a été désactivé dans les déclencheurs Adobe Experience Cloud Triggers. Par conséquent, cette option a été supprimée d’Adobe Campaign Standard. Pour éviter toute valeur obsolète de score de propension dans les schémas d’enrichissement, nous vous recommandons de mettre à jour les schémas afin de récupérer les dernières modifications et de republier les déclencheurs existants. Pour plus d’informations, consultez <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html?lang=fr">Publication d’un déclencheur dans Campaign</a>.</p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] a été désactivé. De ce fait, à compter de la version Campaign 20.2, l’édition d’images optimisée par [!DNL Creative SDK] dans les e-mails de Campaign Standard n’est plus disponible.</p></br>
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
   <td> <p>À partir de la version du printemps 2019 et de la version de Campaign 19.2, Microsoft Internet Explorer 11 n'est plus supporté avec Adobe Campaign et Adobe Experience Cloud. Passez à Microsoft Edge ou tout autre navigateur pris en charge. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html?lang=fr">En savoir plus</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
