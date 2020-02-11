---
title: Définir l'audience du courrier
description: Découvrez comment définir la cible de votre diffusion courrier.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Définir l&#39;audience du courrier{#defining-the-direct-mail-audience}

Vous pouvez définir l&#39;audience dans l&#39;assistant de création ou en cliquant sur la section **Audience** du tableau de bord de la diffusion.

![](assets/direct_mail_15.png)

## Définir la cible principale  {#defining-the-main-target}

Pour les courriers, les profils ciblés sont ceux qui seront inclus dans le fichier d&#39;extraction qui sera envoyé à l&#39;opérateur de services postaux.

Pour chaque profil ciblé, une nouvelle ligne est ajoutée dans le fichier d&#39;extraction. La quantité d&#39;informations de profil qui sera incluse pour chaque destinataire est définie dans l&#39;écran [Définir l&#39;extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!CAUTION]
>
>Vérifiez que les profils contiennent une adresse postale car cette information est indispensable pour le prestataire de services postaux. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles&#39; information. Voir [Recommandations](../../channels/using/about-direct-mail.md#recommendations).

## Ajouter des profils de test et de type piège  {#adding-test-and-trap-profiles}

Ajoutez des profils de test afin de tester votre fichier avec un petit nombre de profils. Vous pouvez ainsi créer un fichier d&#39;exemple pour tester et valider la structure avant de préparer le fichier réel. Voir [Gérer les profils de test](../../audiences/using/managing-test-profiles.md).

L&#39;utilisation de pièges est essentielle pour les diffusions courrier. Ils permettent de vérifier que votre opérateur de services postaux envoie bien la communication et qu&#39;il ne partage pas votre liste de clients avec un autre opérateur. Voir [Utilisation de pièges](../../sending/using/using-traps.md).

Dans le cadre des diffusions courrier, les pièges sont ajoutés pendant l&#39;extraction et mélangés dans le document de sortie. Par défaut, ils sont insérés dans l&#39;ordre de tri du fichier de sortie, mais vous pouvez choisir de les insérer au début ou à la fin du fichier. When defining the audience, select the desired option from the **[!UICONTROL Trap insertion mode]** tab.

![](assets/direct_mail_trap_insertion_mode.png)
