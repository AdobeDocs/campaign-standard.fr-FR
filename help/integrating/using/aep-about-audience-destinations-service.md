---
title: À propos du service Audience Destinations
description: En savoir plus sur le service Audience Destinations.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: ht
source-wordcount: '376'
ht-degree: 100%

---

# À propos du service Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’assistance clientèle d’Adobe si vous souhaitez y accéder.

Donnez à vos clients les moyens d’acquérir des expériences en exploitant [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=fr) pour créer des audiences très ciblées basées sur des jeux de données complexes et volumineux. Adobe Experience Platform regroupe les données de profil, de comportement et multi-entités sur des sources en ligne et hors ligne, y compris Adobe Analytics, afin de vous aider à créer une vue à 360 degrés de votre client, ce qui vous permet de gérer efficacement vos expériences client.

 Adobe Campaign Standard utilisera alors le service **Audience Destinations** pour récupérer une collection de profils, connue sous le nom d’**Audiences**, depuis Adobe Experience Platform pour les programmes de campagne à plusieurs étapes et/ou cross-canal.

Les **audiences** sont créées d’abord à travers la création de **segments**, qui sont essentiellement un jeu de règles basées sur pratiquement n’importe quelle variable (par exemple, les données de profil, d’événement, ou multi-entités) au sein d’un profil client à partir d’Adobe Experience Platform pour créer une cible multidimensionnelle. Les concepts généraux relatifs aux services de profil client en temps réel et de segmentation sont référencés dans ces documents dédiés :

* [Aperçu du profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr)
* [Présentation du service de segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=fr)

Une fois qu’un segment a été créé, vous pouvez l’activer en tant qu’audience pour une diffusion dans des [workflows Campaign Standard](../../integrating/using/aep-targeting-audiences.md). De plus, vous pouvez utiliser les données contextuelles issues d’Adobe Experience Platform pour [personnaliser](../../integrating/using/aep-personalizing-campaigns.md) et ajouter du contenu dynamique à vos campagnes.

![](assets/do-not-localize/how-to-video.png) Des vidéos pratiques sont également disponibles dans [cette section](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=fr).

Termes utilisés dans ces sections :

* **Profil**: Un profil est un modèle de données standard d’Experience Platform utilisé pour définir les attributs des consommateurs. Un profil peut également être un agrégat de données et d’attributs liés à une personne ou un appareil.

   Exemple : « John Doe est un homme de 55 ans. »

* **Segment** : Ensemble de règles qui définit un sous-ensemble de profils de votre base de données, à l’aide d’attributs et de données d’événement.

   Exemple : « Hommes > 50 ans. »

* **Audience** : Collection de profils qui respectent les règles de segmentation.

   Exemple : Liste de profils correspondant à tous les hommes de plus de 50 ans dans votre base de données.
