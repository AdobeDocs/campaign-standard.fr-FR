---
title: Création ou extension de la ressource
description: Découvrez comment définir entièrement une ressource.
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Création ou extension de la ressource{#creating-or-extending-the-resource}

Les administrateurs peuvent créer une nouvelle ressource à partir de zéro ou créer une extension d’une ressource existante si vous avez besoin de travailler sur des données qui ne font pas partie du modèle de données intégré.

Seules les ressources intégrées suivantes peuvent être étendues :

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Pour créer ou étendre une ressource :

1. Dans **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, cliquez sur le **[!UICONTROL Create]** bouton.
1. Sélectionnez l&#39;action que vous souhaitez réaliser :

   * **[!UICONTROL Create a new resource]**: Entrez les champs **[!UICONTROL Label]** et **[!UICONTROL ID]** . The **[!UICONTROL ID]** field is mandatory. Si vous laissez le champ Libellé vide, il sera automatiquement renseigné à partir de l&#39;identifiant.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Utilisez 30 caractères au maximum.

   * **[!UICONTROL Extend an existing resource]**: Sélectionnez la ressource que vous souhaitez étendre.

      ![](assets/schema_extension_10.png)

1. Click **[!UICONTROL Create]** to create the resource, which will then take on the **[!UICONTROL Draft]** status in case of new resource or the **[!UICONTROL Editing]** status in case of extension.

La nouvelle ressource est créée et peut être maintenant configurée. Pour plus d&#39;informations sur la configuration d&#39;une ressource, consultez la section [Configuration de la structure de données de la ressource](../../developing/using/configuring-the-resource-s-data-structure.md).
