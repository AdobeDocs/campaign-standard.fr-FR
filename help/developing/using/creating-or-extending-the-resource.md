---
title: Création ou extension de la ressource
description: Découvrez comment définir entièrement une ressource.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
TQID: 'https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA'
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
source-wordcount: '198'
ht-degree: 100%
---
# Création ou extension de la ressource{#creating-or-extending-the-resource}

Les administrateurs peuvent créer une ressource ou une extension d&#39;une ressource existante si vous avez besoin d&#39;utiliser des données qui ne font pas partie du modèle de données natif.

Seules les ressources natives suivantes peuvent être étendues :

* **[!UICONTROL Campagne (campaign)]**
* **[!UICONTROL Diffusions (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profils (profile)]**
* **[!UICONTROL Programme (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]**
* **[!UICONTROL Profils de test (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Pour créer ou étendre une ressource :

1. Depuis **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Ressources personnalisées]**, cliquez sur le bouton **[!UICONTROL Créer]**.
1. Sélectionnez l&#39;action que vous souhaitez réaliser :

   * **[!UICONTROL Créer une nouvelle ressource]** : renseignez les champs **[!UICONTROL Libellé]** et **[!UICONTROL Identifiant]**. Le champ **[!UICONTROL Identifiant]** est obligatoire. Si vous laissez le champ Libellé vide, il sera automatiquement renseigné à partir de l&#39;identifiant.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Utilisez 30 caractères au maximum.

   * **[!UICONTROL Etendre une ressource existante]** : sélectionnez la ressource que vous souhaitez étendre.

     ![](assets/schema_extension_10.png)

1. Cliquez sur **[!UICONTROL Créer]** pour créer la ressource. Celle-ci prend alors le statut **[!UICONTROL En création]** s&#39;il s&#39;agit d&#39;une nouvelle ressource ou **[!UICONTROL En édition]** s&#39;il s&#39;agit d&#39;une extension.

La nouvelle ressource est créée et peut être maintenant configurée. Pour plus d&#39;informations sur la configuration d&#39;une ressource, consultez la section [Configuration de la structure de données de la ressource](../../developing/using/configuring-the-resource-s-data-structure.md).
