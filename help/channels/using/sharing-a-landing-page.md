---
title: Partager une landing page
seo-title: Partager une landing page
description: Partager une landing page
seo-description: Découvrez comment tester et publier une landing page dans Adobe Campaign.
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Partager une landing page{#sharing-a-landing-page}

## A propos de la publication d'une landing page {#about-landing-page-publication}

Avant de publier une landing page, vous devez effectuer des tests : valider l'exécution, configurer l'accès et définir la fin de vie de la landing page. Ces étapes sont des pré-requis et doivent être exécutées avec précaution.

## Tester la landing page  {#testing-the-landing-page-}

Comme la landing page aura un impact sur votre plate-forme et les données, vous devez tester soigneusement son exécution. Pour cela :

1. Cliquez sur le bouton **[!UICONTROL Tester]** présent dans la barre d'actions de la landing page.
1. Dans l'écran de test, sélectionnez un profil de test et un service de test si la landing page a pour but de gérer les inscriptions.

   ![](assets/lp_test_2.png)

1. Renseignez les champs et sélectionnez des options.
1. Validez la landing page et vérifiez les mises à jour dans la base de données.

   >[!CAUTION]
   >
   >Lorsque le formulaire est validé, le service et le profil utilisés sont mis à jour.

1. Répétez cette opération avec des profils et des données différents.

   Vous pouvez également générer la miniature de la landing page depuis cet écran.

## Configurer les paramètres de validité  {#setting-up-validity-parameters}

Avant de procéder à la publication, il est vivement recommandé, pour des raisons de sécurité et de performances de la plate-forme, de définir une date d'expiration dans les propriétés de la landing page. A la date choisie, la landing page est automatiquement dépubliée. Pour cela :

1. Editez les propriétés de la landing page accessibles via le bouton ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page.

   ![](assets/lp_edit_properties_button.png)

1. Configurez la date et l'heure d'expiration dans la section **[!UICONTROL Publication]** : la landing page est automatiquement dépubliée à la date spécifiée et n'est donc plus disponible.

   Vous pouvez sélectionner le fuseau horaire à prendre en compte pour cette date et cette heure.

1. Définissez une URL de redirection pour rediriger les visiteurs lorsqu'ils tentent d'accéder à une landing page inactive.

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>Vous pouvez également définir une date et une heure de déploiement : la landing page sera alors automatiquement publiée à la date spécifiée.

## Publier une landing page  {#publishing-a-landing-page}

Lorsque vous publiez une landing page, elle est mise en ligne et devient accessible aux visiteurs.

Vous pouvez à tout moment dépublier ou mettre à jour et republier votre landing page via le bouton **[!UICONTROL Publier]**. Cependant, si la republication échoue et que vous n'avez pas dépublié votre landing page auparavant, la première version reste en ligne.
