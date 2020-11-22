---
solution: Campaign Standard
product: campaign
title: Définir le contenu du courrier
description: Découvrez comment définir le contenu de votre diffusion courrier.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---


# Définir le contenu du courrier{#defining-the-direct-mail-content}

Vous pouvez définir le contenu dans le dernier écran de l&#39;assistant de création ou en cliquant sur la section **Contenu** du tableau de bord de la diffusion.

![](assets/direct_mail_6.png)

L&#39;écran de définition du **[!UICONTROL Contenu]** est spécifique au canal courrier. Il comporte quatre onglets : **[!UICONTROL Extraction]**, **[!UICONTROL Structure du fichier]**, **[!UICONTROL En-tête]** et **[!UICONTROL Pied de page]**.

![](assets/direct_mail_11.png)

## Définir l&#39;extraction {#defining-the-extraction}

1. Définissez tout d&#39;abord le nom du fichier d&#39;extraction. Cliquez sur le bouton situé à droite du champ **[!UICONTROL Fichier de sortie]** et saisissez le libellé souhaité. Vous pouvez utiliser des champs de personnalisation, des blocs de contenu et du texte dynamique (voir [Définir le contenu](../../designing/using/personalization.md#example-email-personalization)). Vous pouvez, par exemple, renseigner le libellé avec l&#39;identifiant de la diffusion ou la date d&#39;extraction.

   ![](assets/direct_mail_12.png)

1. Cliquez sur le bouton **[!UICONTROL +]** ou **[!UICONTROL Ajouter un élément]** pour ajouter une colonne de sortie. Les **[!UICONTROL Colonnes de sortie]** permettent de définir les informations de profil (colonnes) à exporter dans le fichier de sortie.

   >[!CAUTION]
   >
   >Vérifiez que les profils contiennent une adresse postale car cette information est indispensable pour le prestataire de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils. Voir [Recommandations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Créez autant de colonnes que nécessaire. Vous pouvez éditer les colonnes en cliquant sur leur expression et leur libellé.

>[!NOTE]
>
>Pour plus d&#39;informations sur la définition des colonnes de sortie, reportez-vous à la section de l&#39;activité de workflow [Extraction de fichier](../../automating/using/extract-file.md).

## Définir la structure de fichier   {#defining-the-file-structure}

L&#39;onglet **Structure de fichier** permet de paramétrer les formats de sortie, des dates et des nombres du fichier qui sera exporté.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Les options disponibles sont présentées dans les sections de l&#39;activité de workflow [Extraction de fichier](../../automating/using/extract-file.md).

## Définir l&#39;en-tête et le pied de page   {#defining-the-header-and-footer}

Vous pouvez parfois avoir besoin d&#39;ajouter des informations au début ou à la fin du fichier d&#39;extraction. Pour cela, vous pouvez utiliser les onglets **[!UICONTROL En-tête]** et **[!UICONTROL Pied de page]** de l&#39;écran de configuration **[!UICONTROL Contenu]**.

![](assets/direct_mail_7.png)

Par exemple, vous souhaiterez peut-être inclure dans l&#39;en-tête du fichier des informations sur l&#39;expéditeur pour l&#39;opérateur de services postaux. Il est possible de personnaliser le pied de page et l&#39;en-tête avec des informations qui sont disponibles dans le cadre de la diffusion. Voir [Définir le contenu](../../designing/using/personalization.md#example-email-personalization).

L&#39;adresse de l&#39;expéditeur est définie dans la section **[!UICONTROL Envoi]** des propriétés du courrier ou au niveau du modèle.

![](assets/direct_mail_24.png)
