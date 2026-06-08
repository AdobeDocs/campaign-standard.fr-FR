---
title: Commencer avec les intégrations de Campaign
description: Utilisez d'autres solutions d'Adobe et combinez leurs différentes fonctionnalités avec Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
TQID: https://experienceleague.adobe.com/ertIWjv9n88c9As-BDvGXtzsod8Bce4yTYEVpmeZeEo
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bb6c4d97-79f4-412c-a764-b541e9f9facdid: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: df0d6518-6f49-46e2-b46e-3bcc513f553f
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 675
ht-degree: 100%

---

# À propos des intégrations de Campaign{#get-started-campaign-integrations}

Cette section présente les intégrations fonctionnelles disponibles entre la version actuelle d&#39;Adobe Campaign et d&#39;autres solutions et services.

Les différentes intégrations présentées ci-après vous permettent de combiner les fonctionnalités de diffusion et de gestion de campagnes avancées d&#39;Adobe Campaign avec un ensemble de solutions conçues pour vous aider à personnaliser l&#39;expérience de vos utilisateurs.

>[!NOTE]
>
> Par défaut, Adobe Campaign est déjà lié à un compte Adobe Experience Cloud.

En fonction de votre environnement, d&#39;autres solutions peuvent également être liées à Adobe Experience Cloud. Elles sont liées sous la forme d&#39;organisations (aussi appelés tenants).

Une organisation est l&#39;entité qui permet à un administrateur de configurer des groupes et des utilisateurs et de contrôler l&#39;authentification unique dans Experience Cloud. L&#39;organisation fonctionne comme une société de connexion qui couvre tous les produits et solutions Experience Cloud. L&#39;organisation correspond le plus souvent au nom de votre société. Toutefois, une société peut détenir plusieurs organisations. La gestion des utilisateurs et des organisations est présentée sur le [portail d&#39;aide Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=fr).

Si vous souhaitez intégrer des flux de données d&#39;autres systèmes avec Adobe Campaign, consultez la [documentation des API](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard peut également se connecter à Microsoft Dynamics 365 : cette intégration permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant ainsi toutes celles appropriées disponibles pour les activités de campagne. Pour plus d&#39;informations sur cette intégration, consultez [Utilisation de Campaign et Dynamics 365](../../integrating/using/d365-acs-get-started.md).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Cas d’utilisation<br /> </th> 
   <th> Reportez-vous à<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> Permet de créer des contenus d'e-mail ou des formulaires mappés à la base Adobe Campaign directement dans Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Utiliser Campaign et Experience Manager</a>, <a href="https://helpx.adobe.com/fr/experience-manager/6-4/sites/administering/using/campaignstandard.html">Intégrer Experience Manager et Campaign Standard</a>, <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=fr">Créer un e-mail avec Experience Manager et Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Permet d'insérer des images calculées dynamiquement par Adobe Target au moment de l'ouverture d'un e-mail créé et envoyé via Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Utiliser Campaign et Target</a>, <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=fr">Intégrer Campaign et Target</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Personnaliser les images d’e-mail en temps réel</a> (étape 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Permet de tracker les performances de vos diffusions e-mail directement dans Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Partager des données Campaign avec Analytics</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Partager les KPI pour le reporting intégré de Campaign</a> (étape 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager et People Core Service (Profiles et audiences)<br /> </td> 
   <td> Permet d’échanger des audiences avec les différentes applications d’Adobe Experience Cloud que vous utilisez.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People Core Service (Profiles et audiences)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Plateforme de données clientèle Adobe en temps réel (RTCDP)<br /> </td> 
   <td> L’intégration entre Adobe Campaign et la plateforme de données clientes en temps réel d’Adobe (RTCDP) vous permet de partager des données de segments et d’importer des audiences dans Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Commencer avec les sources et les destinations</a></td>
  </tr> 
  <tr> 
   <td> Adobe Asset core service et Assets On Demand<br /> </td> 
   <td> Permet d’insérer des ressources de votre bibliothèque Adobe Experience Cloud dans les e-mails et les pages de destination créés dans Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets Core Service</a> ou Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points ciblés (Analytics pour Mobile)<br /> </td> 
   <td> Permet de collecter les données de points ciblés auprès des personnes abonnées de votre application mobile pour envoyer des messages marketing personnalisés avec Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Envoyer des messages marketing en fonction de la localisation avec Campaign et les données de points ciblés</a> (Analytics pour Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Triggers Adobe Experience Cloud<br /> </td> 
   <td> Permet d'envoyer des e-mails personnalisés à vos clients dans Adobe Campaign en réaction à des comportements spécifiques trackés sur votre site web par Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utiliser les triggers Experience Cloud dans Campaign Standard</a> <a href="../../integrating/using/abandonment-triggers-use-cases.md">Cas pratiques Triggers-Campaign d'abandon</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Déclencher des messages de remarketing selon l'activité du site</a> (étape 2)
    </td> 
  </tr> 
    <tr> 
   <td> Adobe Journey Orchestration<br /> </td> 
   <td> Permet d'envoyer des e-mails, des notifications push et des SMS à l'aide des fonctionnalités de messagerie transactionnelle d'Adobe Campaign Standard dans le contexte d'Adobe Journey Orchestration, par le biais d'une action d'usine.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=fr">Utilisation d'Adobe Journey Orchestration et d'Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Permet d'éditer le contenu d'un e-mail dans Dreamweaver et de le synchroniser avec Adobe Campaign.<br /> </td> 
   <td> 
    Vidéo <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=fr">Créer des e-mails personnalisés avec Dreamweaver</a> <a href="https://helpx.adobe.com/fr/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Utilisation de l'extension de Campaign pour Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK Adobe Experience Platform<br /> </td> 
   <td> Permettent d'automatiser l'activation des propriétés de l'application mobile dans Adobe Campaign à l'aide des SDK Adobe Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configuration d'une application mobile à l'aide des SDK Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
