---
title: 'Étape 2 : publier l''extension'
description: Découvrez comment publier l'extension dans Campaign Standard. Partie 2 d'une série.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: e3bebded-764c-4d2e-9580-c413f1576a2c
TQID: 'https://experienceleague.adobe.com/BPvEkhFMAe2Xiwllo4RwTzGeXo-IPxYiEp-1sGUzK-A'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%
---
# Étape 2 : publier l&#39;extension{#step-publish-the-extension}

1. Sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Développement]**, puis **[!UICONTROL Publication]** dans le menu avancé (via le logo Adobe Campaign).
1. Cliquez sur le bouton **[!UICONTROL Préparer la publication]**.
1. Sélectionnez l&#39;option **[!UICONTROL Créer l&#39;API Profiles &amp; Services Ext]**.

   ![](assets/create-profile-and-services-api.png)

   >[!NOTE]
   >
   >Si l&#39;API a déjà été publiée (c&#39;est-à-dire si vous avez déjà coché cette option pour cette ressource ou une autre), la mise à jour de l&#39;API est forcée.

1. Cliquez sur l&#39;onglet **[!UICONTROL Aperçu de l&#39;API Profiles &amp; Services]**.

   Vous verrez ainsi les changements qui seront appliqués par la publication de l&#39;API à la version actuelle de l&#39;API profilesAndServicesExt.

   Ici, le champ Code Promotion (ID : cusBrand) sera inséré dans l&#39;API.

   ![](assets/extendpandsapi_diff.png)

1. Cliquez sur le bouton **[!UICONTROL Publier]**.
