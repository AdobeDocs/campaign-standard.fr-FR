---
solution: Campaign Standard
product: campaign
title: Mettre à jour la structure de la base de données
description: Découvrez comment mettre à jour la base de données Adobe Campaign.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: deploy,main;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 100%

---


# Mettre à jour la structure de la base de données{#updating-the-database-structure}

Pour prendre en compte les modifications apportées au modèle de données et pour pouvoir les utiliser, la structure de la base de données doit être mise à jour.

>[!NOTE]
>
>Les ressources personnalisées sont automatiquement actualisées lors des mises à jour automatiques effectuées par Adobe.

## Publier une ressource personnalisée  {#publishing-a-custom-resource}

Pour appliquer les modifications apportées aux ressources, vous devez effectuer une mise à jour de la base de données.

>[!NOTE]
>
>Si le champ d&#39;une ressource personnalisée utilisée lors d&#39;un événement est modifié ou supprimé, l&#39;événement correspondant sera automatiquement dépublié. Consultez [Configuration des messages transactionnels](../../administration/using/configuring-transactional-messaging.md).

1. Sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Développement]**, puis **[!UICONTROL Publication]** dans le menu avancé (via le logo Adobe Campaign).
1. Par défaut, l&#39;option **[!UICONTROL Déterminer les modifications depuis la dernière publication]** est cochée, ce qui signifie que seuls les changements apportés depuis la dernière mise à jour seront appliqués.

   >[!NOTE]
   >
   >L&#39;option **[!UICONTROL Réparer la structure de la base de données]** permet de rétablir une configuration correcte si la publication a échoué avant d&#39;avoir pris fin. Toute modification directement apportée à la base de données et non par le biais des ressources personnalisées sera supprimée.

   ![](assets/schema_extension_12.png)

1. Cliquez sur le bouton **[!UICONTROL Préparer la publication]** pour lancer l&#39;analyse. Veuillez noter que les mises à jour importantes des tables devraient être réalisées lorsque l&#39;instance ne fait pas l&#39;objet d&#39;une utilisation intense par les workflows.

   Pour plus d&#39;informations sur l&#39;action à réaliser sur l&#39;API Profiles &amp; Services, consultez [Publier une ressource avec l&#39;extension de l&#39;API](#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Une fois l&#39;analyse effectuée, cliquez sur le bouton **[!UICONTROL Publier]** pour appliquer vos nouvelles configurations.
1. Une fois la publication effectuée, le volet **[!UICONTROL Résumé]** de chaque ressource indique que le statut est désormais **[!UICONTROL Publié]** et précise la date de la dernière publication.

   >[!NOTE]
   >
   >Si vous apportez de nouvelles modifications à une ressource, vous devrez répéter cette opération afin de les appliquer.

   Si des ressources ont le statut **[!UICONTROL En attente d&#39;initialisation]** avant la publication, alors un message informatif supplémentaire apparaît, vous invitant à vérifier vos actions car la publication va entraîner des modifications définitives (suppression de colonnes, de tables...). Pour vous aider à faire cette dernière modification, un onglet **[!UICONTROL Script SQL]** est disponible. Il fournit la commande SQL qui va être exécutée lors de la publication.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >Vous pouvez arrêter le processus de réinitialisation en cliquant sur le bouton **[!UICONTROL Annuler la réinitialisation]**. Cette action rétablit le statut d&#39;origine de la ressource.

1. En cas d&#39;échec de votre publication, vous pouvez toujours rétablir la publication précédente en cliquant sur **[!UICONTROL Retour vers la dernière publication réussie]**.

   Notez que si vous laissez votre publication dans un état d&#39;échec, une fenêtre contextuelle s&#39;ouvrira dès que vous vous connecterez à votre instance pour vous rappeler de corriger cette publication. Votre instance ne sera pas mise à niveau avec les nouvelles versions de produit tant que votre publication n&#39;aura pas été corrigée.

   ![](assets/schema_extension_31.png)

## Publier une ressource avec l&#39;extension de l&#39;API  {#publishing-a-resource-with-api-extension}

Vous pouvez créer l&#39;API Profile and Services dans les cas suivants :

* Lors de l&#39;extension des ressources personnalisées **[!UICONTROL Profils]** ou **[!UICONTROL Services]**, vous pouvez effectuer une mise à jour de l&#39;API Profiles et Services afin d&#39;intégrer les champs déclarés dans l&#39;extension des ressources personnalisées.
* Lorsque vous définissez une ressource personnalisée et créez un lien entre les ressources **[!UICONTROL Profils]** ou **[!UICONTROL Services]** et la ressource personnalisée, vous pouvez réaliser une mise à jour afin d&#39;inclure la nouvelle ressource dans l&#39;API.

Vous pouvez sélectionner cette option dans l&#39;écran de publication.

* Si l&#39;API n&#39;a pas encore été publiée (en d&#39;autres termes, si vous n&#39;avez jamais étendu la ressource ou si vous n&#39;avez jamais coché cette option pour cette ressource ou une autre), vous avez le choix de la créer ou non.

   ![](assets/create-profile-and-services-api.png)

* Si l&#39;API a déjà été publiée (c&#39;est-à-dire si vous avez étendu la ressource et coché cette option), la mise à jour de l&#39;API est forcée.

   En effet, une fois créée, l&#39;API est mise à jour automatiquement chaque fois que vous la publiez à nouveau. Cela permet d&#39;éviter de rompre la ressource de profil ou de service de cette API et d&#39;endommager votre instance.

La ressource personnalisée est intégrée par défaut, mais si, pour un comportement précis, vous ne souhaitez pas publier cette ressource, sélectionnez l&#39;option **[!UICONTROL Masquer cette ressource dans les API]** disponible dans les **[!UICONTROL Propriétés de la ressource]**.

![](assets/removefromextoption.png)

Après l&#39;étape **[!UICONTROL Préparer la publication]**, Adobe Campaign affiche les différences entre la version actuelle et la future version de l&#39;API après publication dans l&#39;onglet **[!UICONTROL Aperçu de l&#39;API Profiles &amp; Services]**. Si vous étendez l&#39;API pour la première fois, la définition d&#39;usine de la ressource personnalisée est comparée à votre extension.

Les informations contenues dans l&#39;onglet sont divisées en trois sections : éléments ajoutés, supprimés et modifiés.

![](assets/extendpandsapi_diff.png)

L&#39;analyse des différences est une étape obligatoire, car la publication modifiera le comportement de l&#39;API et aura probablement un effet en cascade sur le développement environnant.

>[!NOTE]
>
>Cette publication met à jour l&#39;API **[!UICONTROL profilesAndServicesExt]**. L&#39;API **[!UICONTROL profilesAndServices]** n&#39;est pas mise à jour.

Pour plus d&#39;informations sur l&#39;API Adobe Campaign, reportez-vous à la documentation Adobe Campaign dédiée sur [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
