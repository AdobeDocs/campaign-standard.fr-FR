---
title: Personnalisation des campagnes à l’aide des attributs d’Adobe Experience Platform
description: Découvrez comment personnaliser vos campagnes à l’aide des attributs de la plateforme Adobe Experience Platform.
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
source-git-commit: 2086bbb6fa87106692b3f3744c40ecf40e66caf3

---


# Personnalisation des campagnes à l’aide des attributs d’Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Le service Destinations d’audience est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.
>
>**Les canaux Push** et **in-app** ne sont pas encore disponibles pour la personnalisation à l’aide de données contextuelles d’Adobe Experience Platform.

Une fois votre flux de travail configuré avec une audience [](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience Platform, vous pouvez personnaliser les messages avec des attributs de profil qui existent exclusivement dans le modèle de données d’expérience (XDM).

Pour ce faire, vous devez ajouter ces attributs à l’activité d’audience ****Lecture :

1. Ouvrez l’activité **[!UICONTROL Lire l’audience]**. Dans l’onglet Données**** supplémentaires, cliquez sur le bouton **[!UICONTROL Créer un élément]**.

   >[!NOTE]
   >
   >L’onglet Données ****supplémentaires n’est disponible qu’après la sélection d’une audience Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

1. Sélectionnez un champ XDM dans la liste, puis cliquez sur **[!UICONTROL Confirmer]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter]**pour l’ajouter à la liste des données supplémentaires.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Répétez ces étapes pour chaque champ XDM que vous souhaitez ajouter à votre processus.

   >[!NOTE]
   >
   >Vous pouvez ajouter un maximum de 20 champs XDM dans une activité d’audience **[!UICONTROL en]**lecture.

1. Une fois tous les champs ajoutés, cliquez sur le bouton **[!UICONTROL Confirmer]**pour enregistrer vos modifications. Ils seront désormais disponibles pour personnaliser vos livraisons.

Pour plus d’informations sur la création et la personnalisation des livraisons, voir la documentation de Campaign Standard :

* [Découvrir les canaux de communication](../../channels/using/discovering-communication-channels.md)
* [A propos des activités des canaux](../../automating/using/about-channel-activities.md)
* [Personnaliser les diffusions](../../designing/using/personalization.md)
