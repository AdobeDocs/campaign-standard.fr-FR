---
title: Définir un texte dynamique
description: Découvrez comment afficher différents textes de manière dynamique à l’utilisateur selon les conditions définies dans Adobe Campaign.
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%

---


# Définir un texte dynamique{#defining-dynamic-text}

Le texte dynamique est défini de la même façon que le contenu dynamique. Voir [Définir le contenu dynamique](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Pour les SMS et les notifications push, vous pouvez uniquement définir le texte dynamique. Vous pouvez définir du contenu et du texte dynamiques dans une landing page. Si vous souhaitez définir du texte dynamique à l’aide du [Concepteur d’email](../../designing/using/designing-content-in-adobe-campaign.md), reportez-vous à la section [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Notez que les paires de substitution, les caractères non inclus dans le plan multilingue de base du jeu de caractères Unicode, ne peuvent pas être stockés sur 2 octets (16 bits) et doivent être codés sur 2 caractères UTF-16. Ces caractères incluent certaines idéogrammes CJK, la plupart des émoticônes et certaines langues.
<br>Ces caractères peuvent provoquer des problèmes d’incompatibilité dans le texte dynamique. Vous devez effectuer des tests stricts avant d&#39;envoyer vos messages.


L’exemple ci-dessous montre comment définir du texte dynamique dans un SMS.

1. Sélectionnez du texte dans le corps de votre message ou landing page.
1. Cliquez sur **[!UICONTROL Activer le texte dynamique]**.

   ![](assets/dynamic_text_sms_1.png)

   L’option **[!UICONTROL Texte dynamique]** apparaît dans la palette. Son paramétrage est identique au contenu dynamique.

1. Sélectionnez une variante.

   ![](assets/dynamic_text_sms_2.png)

1. Définissez une condition pour cette variante.

   ![](assets/dynamic_text_sms_4.png)

Une fois qu’une condition est définie pour au moins une variante, un cadre violet s’affiche autour du texte dynamique.

![](assets/dynamic_text_sms_3.png)
