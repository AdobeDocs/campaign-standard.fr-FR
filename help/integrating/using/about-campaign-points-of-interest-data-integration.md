---
title: À propos de l'intégration Campaign-Données de points ciblés
description: Grâce à la collecte des données de points ciblés auprès des abonnés de votre application mobile, envoyez-leur des messages marketing en fonction de leur localisation par le biais de l'intégration dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 100%
---
# À propos de l&#39;intégration Campaign-Données de points ciblés{#about-campaign-points-of-interest-data-integration}

Outre l&#39;activité en ligne des clients, il est également possible de détecter et d&#39;utiliser leur emplacement physique. Grâce à l&#39;intégration avec Adobe Analytics pour Mobile, vous pouvez utiliser Adobe Campaign pour envoyer des messages marketing aux abonnés de votre application mobile en fonction de leur localisation.

Les points ciblés sont constitués d&#39;une latitude, d&#39;une longitude et d&#39;un rayon associés à un libellé. Ils sont définis dans l&#39;interface [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=fr).

Lorsqu&#39;un abonné ouvre votre application mobile, Adobe Campaign capture les données via le SDK Experience Cloud Mobile si la localisation correspond à un point ciblé. Vous pouvez utiliser ces informations pour envoyer des messages personnalisés en fonction de la localisation de l&#39;utilisateur (tels que des emails, des notifications push ou des SMS).

Par exemple, vous pouvez envoyer une réduction de 10 % aux clients qui utilisent l&#39;application et qui se sont rendus dans l&#39;une de vos boutiques de Lyon au cours des 15 derniers jours.

Un cas pratique est présenté dans la section [Personnaliser des messages Campaign avec les données de points ciblés](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
