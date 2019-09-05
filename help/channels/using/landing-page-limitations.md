---
title: Limites des landing pages
seo-title: Limites des landing pages
description: Limites des landing pages
seo-description: Découvrez les landing pages Campaign et leur cycle de vie.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 5dbb89eca363f252d0c69126878d4f79320e0f19

---


# Limites des landing pages{#landing-page-limitations}

**Ecriture et mise à jour des données**

* Les landing pages sont limitées uniquement aux ressources **[!UICONTROL Profil]** et **[!UICONTROL Abonnement]**. Un enregistrement peut être sauvegardé et mis à jour depuis le **[!UICONTROL Profil]** et un abonnement/désabonnement à un **[!UICONTROL Service]**.
Pour en savoir plus sur la configuration des ressources, voir [Configuration de la structure de données de la ressource](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>Une page d'entrée ne peut pas afficher ni mettre à jour les données d'une autre ressource que **[!UICONTROL Profil]** et **[!UICONTROL Abonnement]**.

**Préchargement**

* Une landing page ne peut pas afficher automatiquement une liste d'enregistrements. Elle ne peut pas répertorier les services auxquels les profils sont déjà abonnés. Pour plus d'informations sur les services, consultez cette [page](../../audiences/using/creating-a-service.md).

* Une landing page avec un formulaire prérenseigné (les données sont préchargées avec la page) n'est accessible qu'à partir d'un email Adobe Campaign. Il est impossible d'accéder à ce type de formulaire depuis une page d'un site web.

**Réconciliation**

* Le comportement de réconciliation est le suivant : dès qu'une correspondance est trouvée, la réconciliation s'arrête. La réconciliation ne peut donc être effectuée que sur un enregistrement de profil et non sur plusieurs enregistrements lorsqu'il existe des doublons.

Vous souhaitez par exemple envoyer la landing page d'acquisition suivante à vos profils afin de mettre à jour votre base de données Campaign avec les numéros des téléphones mobiles de vos profils.

![](assets/landing_page_limitation_1.png)

Si l'un de vos profils renseigne votre landing page avec de nouvelles informations mais possède déjà un profil dupliqué, le profil correspondant avec la date de création la plus ancienne est mis à jour, car les profils sont classés par ordre de priorité en fonction de la date de création uniquement.

Dans le cas présent, seul le premier profil a été mis à jour, car il s'agit de l'entrée la plus ancienne.

![](assets/landing_page_limitation_2.png)

**Test de la landing page**

* Les landing pages ne fonctionnent que sur les profils et non sur les profils de test. Elles ne peuvent donc pas être testées dans le cadre d'un BAT d'email.
