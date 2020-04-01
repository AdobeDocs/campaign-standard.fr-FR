---
title: Créer un profil
description: Découvrez comment créer des profils et collecter des données sur vos contacts à l'aide des API, des fonctionnalités d'import, de l'acquisition en ligne et des mises à jour automatiques ou manuelles.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Créer un profil{#creating-profiles}

Dans Adobe Campaign, les profils sont utilisés par défaut pour définir la cible principale des messages.

Pour créer ou mettre à jour un profil dans Campaign, vous pouvez :

* importer une liste de profils depuis un fichier, par l&#39;intermédiaire d&#39;un [workflow](../../automating/using/importing-data.md#example--import-workflow-template) ;
* collecter des données en ligne via des [landing pages](../../channels/using/getting-started-with-landing-pages.md) ;
* créer des profils en masse via l&#39;[API REST](../../api/using/about-campaign-standard-apis.md) ;
* synchroniser les profils depuis [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) ;
* saisir des données dans les écrans de l&#39;interface graphique, comme expliqué ci-dessous.

Par exemple, pour créer un profil directement dans l&#39;interface utilisateur, procédez comme suit :

1. Depuis la page d&#39;accueil d&#39;Adobe Campaign, cliquez sur la vignette **Profils clients** ou l&#39;onglet **Profils** pour accéder à la liste des profils.

   ![](assets/profile_creation_1.png)

1. Cliquez ensuite sur **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Renseignez les données de ce profil.

   ![](assets/profile_creation1.png)

   * Les informations de contact, telles que nom, prénom, genre, date de naissance, photo, préférence linguistique (pour les [emails multilingues](../../channels/using/creating-a-multilingual-email.md)) permettent de personnaliser davantage les diffusions.
   * The profile&#39;s **[!UICONTROL Time zone]** is used to send deliveries at the profile&#39;s time zone. Voir à ce propos cette [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * The **[!UICONTROL Channels]** category, which contains the email address, mobile phone number, opt-out information, lets you know on which channel the profile is reachable.
   * The **[!UICONTROL No longer contact]** category is updated as soon as the profile unsubscribe to a channel.
   * The **[!UICONTROL Address]** category contains the postal address that needs to be filled along with the **[!UICONTROL Address specified]** option to send [direct mail](../../channels/using/about-direct-mail.md) to this profile. If the **[!UICONTROL Address specified]** option is not checked, this profile will be excluded from every direct mail delivery.
   * The **[!UICONTROL Access authorization]** category indicates the profile&#39;s organizational units (to [manage permissions](../../administration/using/about-access-management.md)). Voir également [Partitionnement des profils](../../administration/using/organizational-units.md#partitioning-profiles).
   * The **[!UICONTROL Traceability]** category automatically updates with information concerning the user who created or modified the profile.

1. Click **[!UICONTROL Create]** to save the profile.

Le profil est ajouté à la liste.

>[!NOTE]
>
>La création des profils est également possible à l&#39;aide de l&#39;API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](../../api/using/creating-profiles.md).

Les profils peuvent être également partitionnés en fonction de leurs entités organisationnelles. Pour ajouter les champs des entités organisationnelles à vos profils, reportez-vous à la section [Partitionnement des profils](../../administration/using/organizational-units.md#partitioning-profiles).

>[!NOTE]
>
>Le champ des préférences linguistiques est utilisé pour sélectionner la langue lors de l&#39;envoi de messages multilingues. Pour plus d&#39;informations sur les messages multilingues, consultez [cette page](../../channels/using/creating-a-multilingual-email.md).

**Rubriques connexes :**

* Guide détaillé [A propos des landing pages](../../channels/using/getting-started-with-landing-pages.md)
* [Importer des profils](https://video.tv.adobe.com/v/24993?captions=fre_fr) video
