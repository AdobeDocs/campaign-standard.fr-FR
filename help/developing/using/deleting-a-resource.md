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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6cf00f9b9bafdd54d8424a353b33dc689c0f59aa

---


# Supprimer une ressource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* Elle vient d&#39;être créée et n&#39;est pas encore publiée.
* Si elle est déjà publiée, la ressource doit être réinitialisée.

>[!IMPORTANT]
>
>La réinitialisation et la suppression d&#39;une ressource personnalisée sont des opérations sensibles pouvant avoir un impact sur d&#39;autres ressources. Ces actions doivent être effectuées par un utilisateur expert uniquement.

Pour réinitialiser et supprimer une ressource publiée :

1. Sélectionnez la ressource que vous souhaitez réinitialiser.
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Clics **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Cette action est permanente : les colonnes ou la table de la base de données de la ressource et leurs données seront supprimés définitivement lors de la publication de la modification, ce qui peut entraîner la rupture des liens à partir d&#39;autres ressources personnalisées. Seule la définition de la ressource restera disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vous réinitialisez une extension de la ressource d&#39;usine **Profils (profile)**, vous devez également réinitialiser toute extension **Profil de test (seedMember)** que vous avez pu définir. Pour plus d&#39;informations sur l&#39;extension de la ressource de profil, voir [cette section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publiez la ressource. Pour obtenir des étapes plus détaillées, consultez la section [Publier une ressource personnalisée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** mode, check the resource to delete then click the ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** icon.

   ![](assets/schema_extension_uc28.png)

Votre ressource est supprimée du modèle de données.

>[!NOTE]
>
>Si le champ d&#39;une ressource personnalisée utilisée lors d&#39;un événement est modifié ou supprimé, l&#39;événement correspondant sera automatiquement dépublié. Voir [Configurer les messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

