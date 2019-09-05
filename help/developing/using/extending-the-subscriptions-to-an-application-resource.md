---
title: Extension des abonnements à une ressource d'application
seo-title: Extension des abonnements à une ressource d'application
description: Extension des abonnements à une ressource d'application
seo-description: null
page-status-flag: never-activated
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: ht
source-git-commit: 20b4d5dfb297cac4cd69fe6f945b4399abd7f06a

---


# Extension des abonnements à une ressource d'application{#extending-the-subscriptions-to-an-application-resource}

Dans Adobe Campaign, les données d'attributs de profil mobile envoyées depuis un appareil mobile sont stockées dans la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** qui permet de définir les données que vous souhaitez collecter auprès des abonnés de vos applications. Pour plus d'informations sur les ressources personnalisées, consultez cette [page](../../developing/using/key-steps-to-add-a-resource.md).

Cette ressource peut être étendue pour collecter les données que vous avez l'intention d'envoyer depuis d'appareil mobile vers Adobe Campaign.

1. Dans le menu de navigation avancé (via le logo Adobe Campaign), sélectionnez **[!UICONTROL Administration]** &gt; **[!UICONTROL Développement]**, puis **[!UICONTROL Ressources personnalisées]**.
1. Cliquez sur **[!UICONTROL Créer]** et sélectionnez l'option **[!UICONTROL Etendre une ressource existante]**.
1. Sélectionnez la ressource **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]** et cliquez sur **[!UICONTROL Créer]**.

   ![](assets/in_app_personal_data_4.png)

1. Dans la catégorie **[!UICONTROL Champs]** de l'onglet **[!UICONTROL Structure de données]**, définissez les données du client à récupérer de l'application mobile en cliquant sur le bouton **[!UICONTROL Ajouter un champ]**.

   >[!NOTE]
   >
   >Si vous gérez plusieurs applications mobiles, tous les champs utilisés par l'ensemble de vos applications doivent être répertoriés. C'est l'appel de collecte des PII Android ou iOS qui définit les champs capturés par chaque application.

   ![](assets/in_app_personal_data.png)

1. Ajoutez un **[!UICONTROL Libellé]** et un **[!UICONTROL Identifiant]** pour le nouveau champ. Sélectionnez le **[!UICONTROL Type]** du champ.

   ![](assets/schema_extension_uc9.png)

1. Dans la catégorie **[!UICONTROL Lien vers les profils]**, configurez la clé de réconciliation utilisée pour lier les profils de la base de données Adobe Campaign aux abonnés de vos applications (l'email, par exemple).

   Pour les messages In-App, vous ne pouvez définir qu'une seule clé de réconciliation pour l'ensemble de vos applications mobiles.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Enregistrez]** et publiez votre ressource personnalisée. Pour plus d'informations sur la publication des ressources personnalisées, consultez cette [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

