---
title: À propos du service Destinations d’audience
description: En savoir plus sur le service Destinations d’audience.
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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# À propos du service Destinations d’audience {#about-audiences}

>[!IMPORTANT]
>
>Le service Destinations d’audience est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

Le service **Destinations** d’audience vous permet de créer des audiences hautement ciblées en fonction de jeux de données volumineux et complexes et de partager ces segments en temps quasi réel avec d’autres solutions Adobe Experience Cloud.

La plate-forme [](https://www.adobe.io/apis/experienceplatform/home.html) Adobe Experience Platform regroupe les données de profil, de comportement et de plusieurs entités afin de vous aider à créer une vue 360 de votre client, ce qui vous permet de gérer efficacement vos expériences client.

Campaign Standard vous permet de travailler avec Adobe Experience Platform afin d’identifier des collections de profils, appelés **audiences**. Ils sont créés en créant **des segments**, c’est-à-dire des règles comprenant des attributs de profil et des données d’événement provenant d’Adobe Experience Platform. Les concepts généraux sur les services de profil et de segmentation unifiés peuvent être référencés dans [ces documents](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)dédiés.

Une fois qu’une audience a été créée, vous pouvez l’activer pour une diffusion dans les processus [](../../automating/using/aep-targeting-audiences.md)Campaign Standard. De plus, vous pouvez utiliser des données contextuelles de la plateforme Adobe Experience Platform pour [personnaliser](../../automating/using/aep-personalizing-campaigns.md) et ajouter du contenu dynamique à vos campagnes, le cas échéant.

Des vidéos de démonstration sont également disponibles dans [cette page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/leveraging-aep-audiences-overview.html)

Termes utilisés dans ces sections :

* **Profil**: Le profil est un modèle de données standard de la plateforme d’expérience utilisé pour définir les attributs des consommateurs. Un profil peut également être un agrégat de données d’événement et d’attributs liés à une personne et/ou à un appareil.

   Exemple : &quot;John Doe est un homme de 55 ans.&quot;

* **Segment**: Ensemble de règles qui définit un sous-ensemble de profils de votre base de données, à l’aide d’attributs et de données d’événement.

   Exemple : &quot;Hommes > 50 ans.&quot;

* **Public**: Collection de profils qui respectent les règles de segmentation.

   Exemple : Liste des profils correspondant à tous les hommes de plus de 50 ans dans votre base de données.
