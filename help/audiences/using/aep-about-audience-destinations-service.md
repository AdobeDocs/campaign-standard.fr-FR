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
source-git-commit: 77ceb5e5ca05fc3ee350d8e50fe0c957dec6ea26

---


# À propos du service Destinations d’audience {#about-audiences}

>[!IMPORTANT]
>
>Le service Destinations d’audience est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

Optimisez vos expériences client en exploitant la plate-forme [d’](https://www.adobe.io/apis/experienceplatform/home.html) Adobe Experience Platform pour créer des audiences hautement ciblées basées sur des jeux de données complexes et volumineux. La plate-forme Adobe Experience Platform consolide les données de profil, de comportement et de plusieurs entités sur des sources en ligne et hors ligne, y compris Adobe Analytics, afin de vous aider à créer une vue à 360 degrés de votre client, ce qui vous permet de gérer efficacement vos expériences client.

Adobe Campaign Standard utilise ensuite le service Destinations **d’** audience pour récupérer une collection de profils, appelés **Audiences**, depuis Adobe Experience Platform pour les programmes de campagne multicanaux et/ou multicanaux.

**Les audiences** sont créées en créant d’abord **des segments**, qui sont essentiellement un ensemble de règles basées sur pratiquement n’importe quelle variable (par exemple, profil, événement, données multientités) dans un profil client d’Adobe Experience Platform pour créer une cible multidimensionnelle. Les concepts généraux sur les services de profil et de segmentation unifiés sont référencés dans [ces documents](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)dédiés.

Une fois qu’un segment a été créé, vous pouvez l’activer en tant qu’audience pour une diffusion dans les processus [standard de](../../automating/using/aep-targeting-audiences.md)campagne. De plus, vous pouvez utiliser les données contextuelles de la plateforme Adobe Experience Platform pour [personnaliser](../../automating/using/aep-personalizing-campaigns.md) et ajouter du contenu dynamique à vos campagnes.

Des vidéos pratiques sont également disponibles dans [cette section](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termes utilisés dans ces sections :

* **Profil**: Le profil est un modèle de données standard de la plateforme d’expérience utilisé pour définir les attributs des consommateurs. Un profil peut également être un agrégat de données d’événement et d’attributs liés à une personne et/ou à un appareil.

   Exemple : &quot;John Doe est un homme de 55 ans.&quot;

* **Segment**: Ensemble de règles qui définit un sous-ensemble de profils de votre base de données, à l’aide d’attributs et de données d’événement.

   Exemple : &quot;Hommes > 50 ans.&quot;

* **Public**: Collection de profils qui respectent les règles de segmentation.

   Exemple : Liste des profils correspondant à tous les hommes de plus de 50 ans dans votre base de données.
