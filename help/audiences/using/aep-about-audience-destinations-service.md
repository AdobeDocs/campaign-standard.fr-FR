---
title: À propos du service Audience Destinations
description: En savoir plus sur le service   Destinations.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# À propos du service Audience Destinations {#about-audiences}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Donnez à vos clients les moyens d’acquérir des expériences en exploitant la plate-forme [d’](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) Adobe Experience Platform pour créer des  très ciblés en fonction de jeux de données complexes et volumineux. La plate-forme Adobe Experience Platform regroupe les données de , de comportement et de plusieurs entités sur des sources en ligne et hors ligne, y compris Adobe Analytics, afin de vous aider à créer un à 360 degrés de votre client, ce qui vous permet de gérer efficacement vos expériences client.

 Adobe Campaign Standard utilisera alors le service Destinations **de** pour récupérer une collection d’ **, connue sous le nom de** de, à partir d’Adobe Experience Platform pour le codage de campagne à plusieurs étapes et/ou à plusieursniveaux.

**** sont créés en créant d’abord **des segments**, qui sont essentiellement un ensemble de règles basées sur pratiquement n’importe quelle variable (par exemple, les données de, de, de multi-entité) au sein d’un client à partir d’Adobe Experience Platform pour créer un multidimensionnel. Les concepts généraux relatifs aux services de  et de segmentation unifiés sont référencés dans ces  dédiées :

* [Présentation du de clients en temps réel](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Présentation du service de segmentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Une fois qu’un segment a été créé, vous pouvez l’activer en tant que   pour un dans le [](../../automating/using/aep-targeting-audiences.md)de. De plus, vous pouvez utiliser les données contextuelles de la plateforme Adobe Experience Platform pour [personnaliser](../../automating/using/aep-personalizing-campaigns.md) et ajouter du contenu dynamique à vos campagnes.

How-to videos are also available in [this section](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termes utilisés dans ces sections :

* ****: est un modèle de données standard de la plateforme d’expérience utilisé pour définir les attributs des consommateurs. Un  de peut également être un  de données et d’attributs dela part d’une personne ou d’un dispositif.

   Exemple : &quot;John Doe est un homme de 55 ans.&quot;

* **Segment**: Ensemble de règles qui définit un sous-ensemble de  de votre base de données, à l’aide d’attributs et de données .

   Exemple : &quot;Hommes > 50 ans.&quot;

* ****: Collection de  qui respectent les règles de segmentation.

   Exemple :  de  correspondant à tous les hommes de plus de 50 ans dans votre base de données.
