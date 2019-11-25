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
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Créer un profil{#creating-profiles}

Dans Adobe Campaign, les profils sont utilisés par défaut pour définir la cible principale des messages.

Pour créer ou mettre à jour un profil dans Campaign, vous pouvez :

* importer une liste de profils depuis un fichier, par l'intermédiaire d'un [workflow](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html) ;
* collecter des données en ligne via des [landing pages](../../channels/using/about-landing-pages.md) ;
* créer des profils en masse via l'[API REST](../../api/using/about-campaign-standard-apis.md) ;
* synchroniser les profils depuis [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html) ;
* saisir des données dans les écrans de l'interface graphique, comme expliqué ci-dessous.

Par exemple, pour créer un profil directement dans l'interface utilisateur, procédez comme suit :

1. Depuis la page d'accueil d'Adobe Campaign, cliquez sur la vignette **Profils clients** ou l'onglet **Profils** pour accéder à la liste des profils.

   ![](assets/profile_creation_1.png)

1. Cliquez ensuite sur **[!UICONTROL Créer]**.

   ![](assets/profile_creation.png)

1. Renseignez les données de ce profil.

   ![](assets/profile_creation1.png)

   * Les informations de contact, telles que nom, prénom, genre, date de naissance, photo, préférence linguistique (pour les [emails multilingues](../../channels/using/creating-a-multilingual-email.md)) permettent de personnaliser davantage les diffusions.
   * Le **[!UICONTROL Fuseau horaire]** du profil est utilisé pour envoyer des diffusions en fonction du fuseau horaire du profil. Voir à ce propos cette [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La catégorie **[!UICONTROL Canaux]**, qui contient les adresses email, les numéros de téléphone portable et les informations d'opt-out, indique sur quel canal le profil est accessible.
   * La catégorie **[!UICONTROL Ne plus contacter]** est mise à jour dès qu'un profil se désabonne d'un canal.
   * La catégorie **[!UICONTROL Adresse]** contient l'adresse postale qui doit être complétée ainsi que l'option **[!UICONTROL Adresse renseignée]** à activer pour envoyer des [courriers](../../channels/using/about-direct-mail.md) à ce profil. Si la case **[!UICONTROL Adresse renseignée]** n'est pas cochée, le profil se retrouve exclu de toutes les diffusions courriers.
   * La catégorie **[!UICONTROL Autorisation d'accès]** indique les entités organisationnelles du profil (pour [gérer les permissions](../../administration/using/about-access-management.md)). Voir également [Partitionnement des profils](../../administration/using/organizational-units.md#partitioning-profiles).
   * La catégorie **[!UICONTROL Traçabilité]** est automatiquement mise à jour avec les informations concernant l'utilisateur qui a créé ou modifié le profil.

1. Cliquez sur **[!UICONTROL Créer]** pour enregistrer le profil.

Le profil est ajouté à la liste.

>[!NOTE]
>
>La création des profils est également possible à l'aide de l'API Adobe Campaign Standard. Consultez à ce sujet la [documentation dédiée](../../api/using/managing-profiles.md).

Les profils peuvent être également partitionnés en fonction de leurs entités organisationnelles. Pour ajouter les champs des entités organisationnelles à vos profils, reportez-vous à la section [Partitionnement des profils](../../administration/using/organizational-units.md#partitioning-profiles).

>[!NOTE]
>
>Le champ des préférences linguistiques est utilisé pour sélectionner la langue lors de l'envoi de messages multilingues. Pour plus d'informations sur les messages multilingues, consultez [cette page](../../channels/using/creating-a-multilingual-email.md).

**Rubriques connexes :**

* Guide détaillé [A propos des landing pages](../../channels/using/about-landing-pages.md)
* [Importer des profils](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

