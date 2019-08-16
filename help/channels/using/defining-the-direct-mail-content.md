---
title: Définir le contenu du courrier
seo-title: Définir le contenu du courrier
description: Définir le contenu du courrier
seo-description: Découvrez comment définir le contenu de votre diffusion courrier.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Définir le contenu du courrier{#defining-the-direct-mail-content}

Vous pouvez définir le contenu dans le dernier écran de l'assistant de création ou en cliquant sur la section **Contenu** du tableau de bord de la diffusion.

![](assets/direct_mail_6.png)

L'écran de définition du **[!UICONTROL Contenu]** est spécifique au canal courrier. Il comporte quatre onglets : **[!UICONTROL Extraction]**, **[!UICONTROL Structure du fichier]**, **[!UICONTROL En-tête]** et **[!UICONTROL Pied de page]**.

![](assets/direct_mail_11.png)

## Définir l'extraction {#defining-the-extraction}

1. Définissez tout d'abord le nom du fichier d'extraction. Cliquez sur le bouton situé à droite du champ **[!UICONTROL Fichier de sortie]** et saisissez le libellé souhaité. Vous pouvez utiliser des champs de personnalisation, des blocs de contenu et du texte dynamique (voir [Définir le contenu](../../designing/using/example--email-personalization.md)). Vous pouvez, par exemple, renseigner le libellé avec l'identifiant de la diffusion ou la date d'extraction.

   ![](assets/direct_mail_12.png)

1. Cliquez sur le bouton **[!UICONTROL +]** ou **[!UICONTROL Ajouter un élément]** pour ajouter une colonne de sortie. Les **[!UICONTROL Colonnes de sortie]** permettent de définir les informations de profil (colonnes) à exporter dans le fichier de sortie.

   >[!CAUTION]
   >
   >Vérifiez que les profils contiennent une adresse postale car cette information est indispensable pour le prestataire de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils. Voir [Recommandations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Créez autant de colonnes que nécessaire. Vous pouvez éditer les colonnes en cliquant sur leur expression et leur libellé.

>[!NOTE]
>
>Pour plus d'informations sur la définition des colonnes de sortie, reportez-vous à la section de l'activité de workflow [Extraction de fichier](../../automating/using/extract-file.md).

## Définir la structure de fichier  {#defining-the-file-structure}

L'onglet **Structure de fichier** permet de paramétrer les formats de sortie, des dates et des nombres du fichier qui sera exporté.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Les options disponibles sont présentées dans les sections de l'activité de workflow [Extraction de fichier](../../automating/using/extract-file.md).

## Définir l'en-tête et le pied de page  {#defining-the-header-and-footer}

Vous pouvez parfois avoir besoin d'ajouter des informations au début ou à la fin du fichier d'extraction. Pour cela, vous pouvez utiliser les onglets **[!UICONTROL En-tête]** et **[!UICONTROL Pied de page]** de l'écran de configuration **[!UICONTROL Contenu]**.

![](assets/direct_mail_7.png)

Par exemple, vous souhaiterez peut-être inclure dans l'en-tête du fichier des informations sur l'expéditeur pour l'opérateur de services postaux. Il est possible de personnaliser le pied de page et l'en-tête avec des informations qui sont disponibles dans le cadre de la diffusion. Voir [Définir le contenu](../../designing/using/example--email-personalization.md).

L'adresse de l'expéditeur est définie dans la section **[!UICONTROL Envoi]** des propriétés du courrier ou au niveau du modèle.

![](assets/direct_mail_24.png)

