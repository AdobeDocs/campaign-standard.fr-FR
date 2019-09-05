---
title: Modèles
seo-title: Modèles
description: Modèles
seo-description: '"Les modèles d''Adobe Campaign permettent de pré-configurer des paramètres selon vos besoins : les modèles peuvent contenir un paramétrage complet ou partiel de l''activité marketing, afin de simplifier l''utilisation d''Adobe Campaign pour les utilisateurs finaux non techniques."'
page-status-flag: never-activated
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816c580d952848ac760c9a98c06f54bf260f3554

---


# Modèles{#about-templates}

## Modèles d'activité marketing {#marketing-activity-templates}

Lorsque vous créez une activité marketing, le premier écran de l'assistant vous invite à sélectionner un type – ou modèle. Les modèles vous permettent de préconfigurer certains paramètres selon vos besoins. Le modèle peut contenir un paramétrage complet ou partiel de l'activité marketing. La gestion des modèles est effectuée par l’administrateur fonctionnel.

L'utilisateur final bénéficie d'une interface simplifiée. Lors de la création d'une activité marketing, il lui suffit de sélectionner le modèle souhaité. Il n'a pas à se soucier du paramétrage technique. Celui-ci a en effet été pré-configuré par l'administrateur fonctionnel dans le modèle.

Par exemple, dans le cas d'un modèle d'email, vous pouvez pré-renseigner le contenu HTML, l'audience et tout autre paramètre de votre diffusion : planning, profils de test, propriétés générales de la diffusion, paramètres avancés, etc. Vous gagnez ainsi du temps lors de la création d'une activité.

![](assets/template_1.png)

Pour chaque type d'activité marketing, un ou plusieurs modèles hors-la-boîte sont disponibles avec une configuration minimale. Ces modèles d'usine ne peuvent être ni modifiés, ni supprimés.

Des modèles sont disponibles pour les activités marketing suivantes :

* Programmes
* Campagnes
* Diffusions Email
* Diffusions SMS
* Notifications push 
* Landing pages 
* Workflows 
* Services
* Import
* Messages transactionnels

La gestion de ces modèles s'effectue sur l'écran **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles]**.

>[!NOTE]
>
>Le paramétrage des marques peut être pré-configuré dans un modèle d'email ou de landing page. Voir à ce sujet la section [Marques](../../administration/using/branding.md).

## Modèles de contenu  {#content-templates}

The HTML content templates are accessible from the **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates &amp; fragments]** screen of the [Advanced menu](../../start/using/interface-description.md#advanced-menu). A partir de là, vous pouvez gérer des modèles de contenu de page d'atterrissage, des modèles de contenu e-mail et aussi des fragments.

![](assets/content_templates_list.png)

Les modèles de contenu hors-la-boîte sont uniquement lisibles. Pour en modifier l'un, vous devez d'abord reproduire le modèle souhaité.

Vous pouvez créer de nouveaux modèles ou fragments et définir votre propre contenu. Pour plus d'informations, voir [Créer un modèle de contenu](../../start/using/about-templates.md#creating-a-content-template) et [Créer un fragment de contenu](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Lors de l'édition du contenu avec le concepteur de courriels, vous pouvez aussi créer des modèles de contenu en sauvegardant votre contenu comme un fragment ou comme un modèle. Pour plus d'informations, voir [Sauvegarder le contenu comme modèle](../../start/using/about-templates.md#saving-content-as-template) et [Sauvegarder le contenu comme fragmentment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

### gabarits de contenu électronique {#email-content-templates}

You can manage the HTML contents that are offered in the **[!UICONTROL Templates]** tab of the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) home page.

Les modèles de contenu e-mail de l'email comprennent dix-huit mises en page optimisées par mobile et quatre modèles adaptés à la classe conçus par les artistes Behance. Ils correspondent aux utilisations les plus courantes : messages de bienvenue, newsletters, emails de réengagement, etc. Ils peuvent être facilement personnalisés avec le contenu de vos marques afin de faciliter la création des emails.

![](assets/content_templates.png)

**Rubriques connexes :**

* Découvrez comment personnaliser les modèles de contenu [dans cette vidéo](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Pour plus d'informations sur l'édition de contenu, voir [A propos de la conception du contenu d'un email](../../designing/using/about-email-content-design.md).

### Creating a content template {#creating-a-content-template}

Vous pouvez créer vos propres modèles de contenu pour les utiliser autant de fois que nécessaire.

L'exemple suivant montre comment créer un modèle de contenu email.

1. Accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**, puis cliquez sur **[!UICONTROL Créer]**.
1. Cliquez sur le libellé d'email de façon à accéder à l'onglet **[!UICONTROL Propriétés]** du Concepteur d'email.
1. Spécifiez une étiquette reconnaissable et sélectionnez les paramètres suivants pour pouvoir utiliser ce modèle dans les courriels :

   * Sélectionnez **[!UICONTROL Shared]** ou **[!UICONTROL Livraison]** à partir de **[!UICONTROL la liste]** déroulante Type de contenu.
   * Sélectionnez **[!UICONTROL Template]** dans **[!UICONTROL la liste]** déroulante Type HTML.
   ![](assets/email_designer_create-template.png)

1. Si nécessaire, vous pouvez définir une image qui sera utilisée comme vignette pour le modèle. Sélectionnez-la dans l'onglet **[!UICONTROL Miniature]** des propriétés de modèle.

   ![](assets/email_designer_create-template_thumbnail.png)

   Cette vignette sera affichée dans l'onglet **[!UICONTROL Modèles]** de la [page d'accueil du concepteur](../../designing/using/about-email-content-design.md#about-the-email-designer) de courriels.

1. Fermez l'onglet **[!UICONTROL Propriétés]** pour retourner à l'espace de travail principal.
1. Ajoutez des composants de structure et des composants de contenu que vous pouvez personnaliser au besoin.
   >[!NOTE]
   >
   > Vous ne pouvez pas insérer de champs de personnalisation ou de contenu conditionnel dans un modèle de contenu.
1. Une fois édité, enregistrez votre modèle.

Ce modèle peut maintenant être utilisé dans n'importe quel email construit avec le concepteur email. Sélectionnez-le dans l'onglet **[!UICONTROL Modèles]** de la [page d'accueil du concepteur](../../designing/using/about-email-content-design.md#about-the-email-designer) de courriels.

![](assets/content_template_new.png)

### Sauvegarder le contenu comme modèle {#saving-content-as-template}

Lors de l'édition d'un email avec le concepteur email, vous pouvez sauvegarder directement le contenu de ce courriel comme modèle.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Sélectionnez **[!UICONTROL Enregistrer sous la]** barre d'outils principale de la barre d'outils.

   ![](assets/email_designer_save-as-template.png)

1. Ajoutez une étiquette et une description si nécessaire, puis cliquez **[!UICONTROL sur Enregistrer]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Pour trouver le modèle que vous venez de créer, allez aux **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**.

1. Pour utiliser votre nouveau modèle, sélectionnez-le dans l'onglet **[!UICONTROL Modèles]** de la [page d'accueil du concepteur](../../designing/using/about-email-content-design.md#about-the-email-designer) de courriels.

   ![](assets/content_template_new.png)

