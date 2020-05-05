---
title: Ciblage des audiences Adobe Experience Platform
description: Découvrez comment cibler les audiences Adobe Experience Platform dans les workflows.
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


# Ciblage des audiences Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Le service Audience Destinations est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Une fois l’[audience Adobe Experience Platform](../../audiences/using/aep-about-audience-destinations-service.md) créée à l’aide du créateur de segment Profil unifié, vous pouvez l’utiliser de la même manière qu’une audience Campaign dans les workflows pour personnaliser et envoyer des messages.

Pour activer une audience Adobe Experience Platform dans vos workflows, procédez comme suit :

1. Add a **[!UICONTROL Read audience]** activity into the workflow, then open it.

1. Sélectionnez l’ **[!UICONTROL Adobe Experience Platform]** option sous **[!UICONTROL Type of audience]**, puis ajoutez l’audience de votre choix.

   ![](assets/aep_wkf_readaudience.png)

1. (Facultatif) Une fois l’audience sélectionnée, vous pouvez cliquer sur le bouton en forme d’œil pour vérifier et/ou éditer la définition du segment (veillez à enregistrer à nouveau les modifications).

   En cliquant sur le bouton en forme d’œil, vous accédez simplement au créateur de segment unifié (dans un autre onglet) associé à l’audience sélectionnée dans Campaign.

1. Select a **[!UICONTROL Platform data mapping]** element to specify the desired targeting dimension for the selected Adobe Experience Platform audience.

   Par défaut, la clé primaire (par exemple, iRecipientID pour la table Profil, iAppSubscriptionID pour la table AppSubscription) utilisée pour la réconciliation sera automatiquement disponible dans la liste déroulante. Pour effectuer un ciblage en dehors de la clé primaire, vous devez créer un **espace de nommage** personnalisé.

   >[!NOTE]
   >
   >Pour les cibles en dehors de la clé primaire, vous devez également créer un mapping de ciblage personnalisé correspondant à l’espace de nommage personnalisé. Pour plus d’informations sur le mapping de ciblage, consultez [cette section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Cette liste contient tous les mappings XDM (Experience Data Model) configurés sur votre instance. Pour plus d’informations sur Adobe Experience Platform Data Connector, reportez-vous à [ce document dédié](../../developing/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Once the audience and targeting dimensions are configured properly, click the **[!UICONTROL Confirm]** button to save your changes.

Vous pouvez maintenant configurer le workflow avec d’autres activités. You can, for example, link an **[!UICONTROL Email delivery]** activity to send an email to the audience that has been selected.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard permet de cibler les audiences Adobe Experience Platform dans tous les canaux de diffusion : emails, SMS, courrier, notifications push et messages In-app.
>
>*Remarque : pour tous les messages push et In-app, Campaign Standard ne prend en charge les diffusions que pour les profils connus.

Pour plus d’informations sur l’utilisation des workflows et des diffusions, reportez-vous aux sections suivantes :

* [Présentation des workflows](../../automating/using/get-started-workflows.md)
* [Construire un workflow](../../automating/using/building-a-workflow.md)
* [Découvrir les canaux de communication](../../channels/using/get-started-communication-channels.md)
* [A propos des activités des canaux](../../automating/using/about-channel-activities.md)
