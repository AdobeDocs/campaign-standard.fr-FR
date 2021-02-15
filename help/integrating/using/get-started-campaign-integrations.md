---
solution: Campaign Standard
product: campaign
title: Prise en main des intégrations de Campaign
description: Utilisez d'autres solutions d'Adobe et combinez leurs différentes fonctionnalités avec Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
translation-type: ht
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: ht
source-wordcount: '632'
ht-degree: 100%

---


# A propos des intégrations de Campaign{#get-started-campaign-integrations}

Cette section présente les intégrations fonctionnelles disponibles entre la version actuelle d&#39;Adobe Campaign et d&#39;autres solutions et services.

Les différentes intégrations présentées ci-après vous permettent de combiner les fonctionnalités de diffusion et de gestion de campagnes avancées d&#39;Adobe Campaign avec un ensemble de solutions conçues pour vous aider à personnaliser l&#39;expérience de vos utilisateurs.

>[!NOTE]
>
> Par défaut, Adobe Campaign est déjà lié à un compte Adobe Experience Cloud.

En fonction de votre environnement, d&#39;autres solutions peuvent également être liées à Adobe Experience Cloud. Elles sont liées sous la forme d&#39;organisations (aussi appelés tenants).

Une organisation est l&#39;entité qui permet à un administrateur de configurer des groupes et des utilisateurs et de contrôler l&#39;authentification unique dans Experience Cloud. L&#39;organisation fonctionne comme une société de connexion qui couvre tous les produits et solutions Experience Cloud. L’organisation correspond le plus souvent au nom de votre société. Toutefois, une société peut détenir plusieurs organisations. La gestion des utilisateurs et des organisations est présentée sur le [portail d&#39;aide Adobe Experience Cloud](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/organizations.html).

Si vous souhaitez intégrer des flux de données d&#39;autres systèmes avec Adobe Campaign, consultez la [documentation des API](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard peut également se connecter à Microsoft Dynamics 365 : cette intégration permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant ainsi toutes celles appropriées disponibles pour les activités de campagne. Pour plus d&#39;informations sur cette intégration, consultez [Utilisation de Campaign et Dynamics 365](../../integrating/using/d365-acs-get-started.md).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Cas pratique<br /> </th> 
   <th> Reportez-vous à<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> Permet de créer des contenus d'email ou des formulaires mappés à la base Adobe Campaign directement dans Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Utiliser Campaign et Experience Manager</a>, <a href="https://helpx.adobe.com/fr/experience-manager/6-4/sites/administering/using/campaignstandard.html">Intégrer Experience Manager et Campaign Standard</a>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_AEM.html">Créer un email avec Experience Manager et Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Permet d'insérer des images calculées dynamiquement par Adobe Target au moment de l'ouverture d'un email créé et envoyé via Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Utiliser Campaign et Target</a>, <a href="https://docs.adobe.com/content/help/fr-FR/target/using/integrate/campaign-and-target.html">Intégrer Campaign et Target</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Personnaliser les images d'email en temps réel</a> (étape 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Permet de tracker les performances de vos diffusions email directement dans Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Partager les données de Campaign avec Analytics</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Partager les KPI pour le reporting intégré de Campaign</a> (étape 1))
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager et People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Permet d'échanger des audiences avec les différentes applications d'Adobe Experience Cloud que vous utilisez.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People core service (Profiles &amp; Audiences)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service et Assets On Demand<br /> </td> 
   <td> Permet d'insérer des ressources de votre bibliothèque Adobe Experience Cloud dans les emails et les landing pages créés dans Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets core service</a> ou Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Points ciblés (Analytics pour Mobile)<br /> </td> 
   <td> Permet de collecter les données de points ciblés auprès des abonnés de votre application mobile pour envoyer des messages marketing personnalisés avec Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Envoyer des messages marketing en fonction de la localisation avec Campaign et les données de points ciblés</a> (Analytics pour Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Triggers Experience Cloud<br /> </td> 
   <td> Permet d'envoyer des emails personnalisés à vos clients dans Adobe Campaign en réaction à des comportements spécifiques trackés sur votre site web par Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utiliser les triggers Experience Cloud dans Campaign Standard</a> <a href="../../integrating/using/abandonment-triggers-use-cases.md">Cas pratiques Triggers-Campaign d'abandon</a>, vidéo <a href="https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html">Déclencher des messages de remarketing selon l'activité du site</a> (étape 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Permet d'éditer le contenu d'un email dans Dreamweaver et de le synchroniser avec Adobe Campaign.<br /> </td> 
   <td> 
    Vidéo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">Créer des emails personnalisés avec Dreamweaver</a> <a href="https://helpx.adobe.com/fr/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Utilisation de l'extension de Campaign pour Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK Experience Platform<br /> </td> 
   <td> Permettent d'automatiser l'activation des propriétés de l'application mobile dans Adobe Campaign à l'aide des SDK Adobe Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html">Configuration d'une application mobile à l'aide des SDK Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

