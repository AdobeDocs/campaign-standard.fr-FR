---
title: Personnalisation des campagnes à l’aide des attributs d’Adobe Experience Platform
description: Découvrez comment personnaliser vos campagnes à l’aide des attributs d’Adobe Experience Platform.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Personnalisation des campagnes à l’aide des attributs d’Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.
>
>Les canaux **push** et **In-app** ne sont pas encore disponibles pour la personnalisation à l’aide de données contextuelles issues d’Adobe Experience Platform.

Une fois votre workflow configuré avec une [audience Adobe Experience Platform](../../audiences/using/aep-about-audience-destinations-service.md), vous pouvez personnaliser les messages à l’aide des attributs de profil présents exclusivement dans Experience Data Model (XDM).

To do this, you must add these attributes into the **[!UICONTROL Read audience]** activity:

1. Open the **[!UICONTROL Read audience]** activity. Dans l’ **[!UICONTROL Additional data]** onglet, cliquez sur le **[!UICONTROL Create element]** bouton.

   Note that the **[!UICONTROL Additional data]** tab is only available after an Adobe Experience Platform audience has been selected.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Les types de données tableau et carte ne sont pas pris en charge dans cette fonctionnalité. En outre, seules les données du schéma d’union s’affichent dans le sélecteur.

1. Select the desired XDM field from the list, then click **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Click the **[!UICONTROL Add]** button to add it to the list of additional data.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Répétez ces étapes pour chaque champ XDM que vous souhaitez ajouter à votre workflow.

   >[!NOTE]
   >
   >You can add a maximum of 20 XDM fields in a **[!UICONTROL Read audience]** activity.

1. Once all the fields have been added, click the **[!UICONTROL Confirm]** button to save your changes. Les champs sont désormais à votre disposition pour personnaliser les diffusions.

Pour plus d’informations sur la création et la personnalisation de diffusions, voir la documentation de Campaign Standard :

* [Découvrir les canaux de communication](../../channels/using/get-started-communication-channels.md)
* [A propos des activités des canaux](../../automating/using/about-channel-activities.md)
* [Personnaliser les diffusions](../../designing/using/personalization.md)
