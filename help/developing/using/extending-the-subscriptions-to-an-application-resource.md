---
title: Extension des abonnements à une ressource d’application
description: Découvrez comment étendre l’abonnement à une ressource d’application
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
TQID: 'https://experienceleague.adobe.com/LtTykn3J6LjivrUr-xkhsZMgaVg-uQ2PHqA6wcJipo8'
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
source-wordcount: '265'
ht-degree: 100%
---
# Extension des abonnements à une ressource d&#39;application{#extending-the-subscriptions-to-an-application-resource}

Dans Adobe Campaign, les données d’attributs de profil mobile envoyées depuis un appareil mobile sont stockées dans la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** qui permet de définir les données que vous souhaitez collecter auprès des abonnés de vos applications. Pour plus d’informations sur les ressources personnalisées, consultez [cette page](../../developing/using/key-steps-to-add-a-resource.md).

Cette ressource peut être étendue pour collecter les données que vous avez l&#39;intention d&#39;envoyer depuis d&#39;appareil mobile vers Adobe Campaign.

1. Dans le menu de navigation avancé (via le bouton Adobe Campaign), sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Développement]**, puis **[!UICONTROL Ressources personnalisées]**.
1. Cliquez sur **[!UICONTROL Créer]** et sélectionnez l&#39;option **[!UICONTROL Etendre une ressource existante]**.
1. Sélectionnez la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** et cliquez sur **[!UICONTROL Créer]**.

   ![](assets/in_app_personal_data_4.png)

1. Dans la catégorie **[!UICONTROL Champs]** de l&#39;onglet **[!UICONTROL Structure de données]**, définissez les données du client à récupérer de l&#39;application mobile en cliquant sur le bouton **[!UICONTROL Ajouter un champ]**.

   >[!NOTE]
   >
   >Si vous gérez plusieurs applications mobiles, tous les champs utilisés par l&#39;ensemble de vos applications doivent être répertoriés. C&#39;est l&#39;appel de collecte des PII Android ou iOS qui définit les champs capturés par chaque application.

   ![](assets/in_app_personal_data.png)

1. Ajoutez un **[!UICONTROL Libellé]** et un **[!UICONTROL Identifiant]** pour le nouveau champ. Sélectionnez le **[!UICONTROL Type]** du champ.

   ![](assets/schema_extension_uc9.png)

1. Dans la catégorie **[!UICONTROL Lien vers les profils]**, configurez la clé de réconciliation utilisée pour lier les profils de la base de données Adobe Campaign aux abonnés de vos applications (l&#39;email, par exemple).

   Pour les messages In-App, vous ne pouvez définir qu&#39;une seule clé de réconciliation pour l&#39;ensemble de vos applications mobiles.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Enregistrez]** et publiez votre ressource personnalisée. Pour plus d&#39;informations sur la publication des ressources personnalisées, consultez cette [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
