---
solution: Campaign Standard
product: campaign
title: À propos du service Audience Destinations
description: En savoir plus sur le service Audience Destinations.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 100%

---


# À propos du service Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Donnez à vos clients les moyens d’acquérir des expériences en exploitant [Adobe Experience Platform](https://docs.adobe.com/content/help/fr-FR/experience-platform/landing/home.html) pour créer des audiences très ciblées basées sur des jeux de données complexes et volumineux. Adobe Experience Platform regroupe les données de profil, de comportement et multi-entités sur des sources en ligne et hors ligne, y compris Adobe Analytics, afin de vous aider à créer une vue à 360 degrés de votre client, ce qui vous permet de gérer efficacement vos expériences client.

 Adobe Campaign Standard utilisera alors le service **Audience Destinations** pour récupérer une collection de profils, connue sous le nom d’**Audiences**, depuis Adobe Experience Platform pour les programmes de campagne à plusieurs étapes et/ou cross-canal.

Les **audiences** sont créées d’abord à travers la création de **segments**, qui sont essentiellement un jeu de règles basées sur pratiquement n’importe quelle variable (par exemple, les données de profil, d’événement, ou multi-entités) au sein d’un profil client à partir d’Adobe Experience Platform pour créer une cible multidimensionnelle. Les concepts généraux relatifs aux services de profil client en temps réel et de segmentation sont référencés dans ces documents dédiés :

* [Aperçu du profil client en temps réel](https://docs.adobe.com/content/help/fr-FR/experience-platform/profile/home.html)
* [Présentation du service de segmentation](https://docs.adobe.com/content/help/fr-FR/experience-platform/segmentation/home.html)

Une fois qu’un segment a été créé, vous pouvez l’activer en tant qu’audience pour une diffusion dans des [workflows Campaign Standard](../../automating/using/aep-targeting-audiences.md). De plus, vous pouvez utiliser les données contextuelles issues d’Adobe Experience Platform pour [personnaliser](../../automating/using/aep-personalizing-campaigns.md) et ajouter du contenu dynamique à vos campagnes.

![](assets/do-not-localize/how-to-video.png) Des vidéos pratiques sont également disponibles dans [cette section](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termes utilisés dans ces sections :

* **Profil**: Un profil est un modèle de données standard d’Experience Platform utilisé pour définir les attributs des consommateurs. Un profil peut également être un agrégat de données et d’attributs liés à une personne ou un appareil.

   Exemple : « John Doe est un homme de 55 ans. »

* **Segment** : Ensemble de règles qui définit un sous-ensemble de profils de votre base de données, à l’aide d’attributs et de données d’événement.

   Exemple : « Hommes > 50 ans. »

* **Audience** : Collection de profils qui respectent les règles de segmentation.

   Exemple :  Liste de profils correspondant à tous les hommes de plus de 50 ans dans votre base de données.
