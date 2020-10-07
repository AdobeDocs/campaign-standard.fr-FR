---
title: Supprimer une ressource
description: 'Découvrez comment supprimer une ressource. '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Supprimer une ressource{#deleting-a-resource}

Pour supprimer une ressource, celle-ci doit être **[!UICONTROL En création]**. La ressource est **[!UICONTROL En création]** si :

* Elle vient d&#39;être créée et n&#39;est pas encore publiée.
* Si elle est déjà publiée, la ressource doit être réinitialisée.

>[!IMPORTANT]
>
>La réinitialisation et la suppression d&#39;une ressource personnalisée sont des opérations sensibles pouvant avoir un impact sur d&#39;autres ressources. Ces actions doivent être effectuées par un utilisateur expert uniquement.

Pour réinitialiser et supprimer une ressource publiée :

1. Sélectionnez la ressource que vous souhaitez réinitialiser.
1. Cliquez sur le bouton **[!UICONTROL Réinitialiser]** disponible dans la barre d&#39;actions.

   ![](assets/schema_extension_uc26.png)

1. Cliquez sur **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Cette action est permanente : les colonnes ou la table de la base de données de la ressource et leurs données seront supprimés définitivement lors de la publication de la modification, ce qui peut entraîner la rupture des liens à partir d&#39;autres ressources personnalisées. Seule la définition de la ressource restera disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vous réinitialisez une extension de la ressource d&#39;usine **Profils (profile)**, vous devez également réinitialiser toute extension **Profil de test (seedMember)** que vous avez pu définir. Pour plus d&#39;informations sur l&#39;extension de la ressource de profil, voir [cette section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publiez la ressource. Pour obtenir des étapes plus détaillées, consultez la section [Publier une ressource personnalisée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   La ressource passe en mode **En création** et son statut d&#39;activation est **[!UICONTROL Désactivé]**.

1. En mode **[!UICONTROL Liste]**, cochez la ressource à supprimer puis cliquez sur l&#39;icône ![](assets/delete_darkgrey-24px.png)**[!UICONTROL Supprimer l&#39;élément]**.

   ![](assets/schema_extension_uc28.png)

Votre ressource est supprimée du modèle de données.

>[!NOTE]
>
>Si le champ d&#39;une ressource personnalisée utilisée lors d&#39;un événement est modifié ou supprimé, l&#39;événement correspondant sera automatiquement dépublié. Voir [Configurer les messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

