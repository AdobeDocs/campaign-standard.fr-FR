---
solution: Campaign Standard
product: campaign
title: Conception de contenu dans Adobe Campaign
description: Créez du contenu d’email à partir de zéro, en important du code HTML ou en utilisant des modèles existants.
audience: designing
content-type: reference
topic-tags: about-content-design
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 100%

---


# Concepteur d&#39;email de Campaign{#designing-content-in-adobe-campaign}

Une fois que vous avez créé un email dans Adobe Campaign, vous devez en définir le contenu.

Le Concepteur d’email vous permet de créer des emails captivants et personnalisés au moyen d’une interface par glisser-déposer. Que vous commenciez à partir de zéro ou que vous utilisiez des fragments ou des modèles de contenu existants, vous pouvez concevoir et affiner le contenu de chaque email pour un usage promotionnel ou transactionnel.

Conçu pour générer du code HTML optimisé favorisant une conception réactive, le Concepteur d&#39;emails permet de définir et d&#39;appliquer facilement des conditions de visibilité et des contenus dynamiques à un email, un modèle ou un fragment, directement via l&#39;interface utilisateur. Vous pouvez basculer facilement entre l&#39;interface glisser-déposer et le code HTML d&#39;un simple clic sur un bouton.

Le Concepteur d&#39;email permet de créer du contenu d&#39;email et des modèles de contenu d&#39;email. Il est compatible avec les emails simples, les emails transactionnels, les emails de test A/B, les emails multilingues et les emails récurrents.

Pour commencer à utiliser le Concepteur d&#39;email, regardez cet [ensemble de vidéos](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) qui expliquent la fonctionnalité générale de l&#39;outil et qui décrivent comment créer entièrement un email ou le concevoir à l&#39;aide de modèles.

<!--The Email Designer has more features than the Legacy Editor and is backward compatible.-->

* Pour découvrir comment créer un contenu d’email, voir la section [Prise en main du Concepteur d’email](../../designing/using/quick-start.md).
* Pour une présentation du Concepteur d&#39;email, voir [Utilisation du Concepteur d&#39;email](../../designing/using/designing-content-in-adobe-campaign.md).
* Pour en savoir plus sur la création de contenu :
   * En partant de zéro, voir [Conception d&#39;emails à partir de zéro](../../designing/using/designing-from-scratch.md).
   * A l&#39;aide d&#39;un contenu existant, voir [Conception à l&#39;aide d&#39;un contenu existant](../../designing/using/using-existing-content.md).
   * À l’aide des intégrations Creative Cloud, voir [Conception d’emails multisolution](../../designing/using/using-integrations.md).
* Pour plus d&#39;informations sur la personnalisation, voir [Personnalisation](../../designing/using/personalization.md).

Lorsque vous créez un email, vous pouvez choisir d&#39;utiliser un modèle prédéfini ou de charger un contenu existant à partir d&#39;une autre source. Voir [Sélectionner un contenu existant](../../designing/using/using-existing-content.md#selecting-an-existing-content).

Pour augmenter l&#39;efficacité de vos campagnes marketing, personnalisez votre contenu. Voir [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field) et [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block).

Vous pouvez également définir un contenu dynamique qui varie en fonction de chaque profil. Voir [Définir le contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) et [Définir le contenu dynamique dans une landing page](../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page).

Améliorez vos messages et landing pages avec des liens et des images. Voir [Insérer un lien](../../designing/using/links.md#inserting-a-link) et [Insérer des images](../../designing/using/images.md#inserting-images).

## Interface du Concepteur d&#39;email {#email-designer-interface}

Le Concepteur d&#39;email propose de nombreuses options qui permettent de créer, éditer et personnaliser tous les aspects de votre contenu.

L&#39;interface est composée de plusieurs zones offrant des fonctionnalités différentes :

![](assets/email_designer_overview.png)

A partir des éléments disponibles dans la **palette** (1), déposez des composants de structure et des fragments de contenu dans l&#39;**espace de travail** principal (2). Sélectionnez un composant ou un élément dans l&#39;**espace de travail** (2) et personnalisez ses principales caractéristiques de style et d&#39;affichage dans le volet **Paramètres** (3).

Accédez à des options et des paramètres plus généraux à partir de la **barre d&#39;outils** principale (4).

>[!NOTE]
>
>Le volet **Paramètres** peut être déplacé vers la gauche selon la résolution et l&#39;affichage de votre écran.

![](assets/email_designer_toolbar.png)

La **barre d&#39;outils contextuelle** de l&#39;interface de l&#39;éditeur présente des fonctionnalités différentes selon la zone sélectionnée. Elle regroupe des boutons d&#39;action et des boutons permettant de modifier le style du texte. Les modifications effectuées s&#39;appliquent toujours sur la zone sélectionnée.

### Page d&#39;accueil du Concepteur d&#39;email {#email-designer-home-page}

Lors de la [création d&#39;un email](../../channels/using/creating-an-email.md), la page d&#39;accueil du **[!UICONTROL Concepteur d&#39;email]** s&#39;affiche automatiquement lors de la sélection du contenu de l&#39;email.

![](assets/email_designer_home_page.png)

L&#39;onglet **[!UICONTROL Propriétés]** permet de modifier les détails d&#39;un email, tels que le libellé, l&#39;adresse et le nom de l&#39;expéditeur ou l&#39;objet. Vous pouvez également accéder à cet onglet en cliquant sur le libellé de l&#39;email en haut de l&#39;écran.

![](assets/email_designer_home_properties.png)

L&#39;onglet **[!UICONTROL Modèles]** permet d&#39;effectuer une sélection parmi les contenus HTML d&#39;usine ou les modèles que vous avez déjà créés pour commencer rapidement à concevoir votre email. Voir [Modèles de contenu](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

L&#39;onglet **[!UICONTROL Formation et support]** permet d&#39;accéder facilement à la documentation et aux tutoriels connexes.

![](assets/email_designer_home_support.png)

Si vous ne sélectionnez pas de modèle, la page d&#39;accueil du Concepteur d&#39;email vous permet également de choisir le mode de conception de votre contenu :

* Cliquez sur le bouton **[!UICONTROL Créer]** pour commencer à créer entièrement un contenu. Voir [Concevoir entièrement un contenu d&#39;email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Cliquez sur le bouton **[!UICONTROL Télécharger]** pour télécharger un fichier à partir de votre ordinateur. Voir [Importer du contenu depuis un fichier](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Cliquez sur le bouton **[!UICONTROL Importer depuis l&#39;URL]** pour récupérer du contenu existant à partir d&#39;une URL. Voir [Importer du contenu depuis une URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

## Terminologie {#terminology}

**Modèles** : les modèles sont des structures d&#39;email que vous pouvez créer et réutiliser pour plusieurs diffusions.

**Fragments** : un fragment est un composant réutilisable pouvant être référencé dans un ou plusieurs emails.

**Composants de structure** : éléments structurels définissant la disposition de l&#39;email..

**Composants de contenu** : les composants de contenu sont des composants bruts et vides que vous pouvez éditer une fois qu&#39;ils ont été placés dans un email.

## Bonnes pratiques relatives à la conception de contenu {#content-design-best-practices}

Pour utiliser correctement le Concepteur d&#39;email et créer des emails optimaux aussi simplement que possible, il est recommandé d&#39;appliquer les principes suivants :

* Utilisez les styles intégrés plutôt qu&#39;une feuille CSS distincte et une feuille CSS dans la section &lt;head> du code HTML. En utilisant les styles intégrés, vous pourrez optimiser l&#39;enregistrement et la réutilisation des fragments de contenu.

   Voir [Ajouter des attributs de style intégrés](../../designing/using/styles.md#adding-inline-styling-attributes).

* Si vous importez des fichiers ZIP comportant le contenu HTML, utilisez une feuille CSS standard. Les feuilles de style SCSS ne sont pas prises en charge.

* Etablissez facilement votre marque en créant et en réutilisant des fragments de contenu pour assurer la cohérence de vos campagnes marketing.

   Voir [Créer un fragment de contenu](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Lors de l&#39;édition du **contenu d&#39;un email** :

   Prévisualisez vos messages avant de les envoyer. Adobe Campaign permet de tester le rendu des emails à l&#39;aide de Litmus. Voir à ce propos la section [Rendu des emails](../../sending/using/email-rendering.md).

La section suivante présente davantage de concepts et de bonnes pratiques générales concernant les messages : [Bonnes pratiques de diffusion](../../sending/using/delivery-best-practices.md).

### Mise à jour des fragments {#email-designer-updates}

Le Concepteur d&#39;email est sans cesse amélioré. Si vous avez créé un contenu d&#39;email entièrement ou à partir d&#39;un modèle d&#39;usine ou si vous avez créé des fragments, le message de mise à jour suivant peut s&#39;afficher lors de la prochaine ouverture du contenu :

![](assets/email_designer_fragment_patch_message.png)

Adobe recommande de mettre à jour votre contenu vers la dernière version pour éviter les problèmes comme ceux des collisions CSS. Cliquez sur **[!UICONTROL Mettre à jour maintenant]**.

Si une erreur se produit lors de la mise à jour du contenu, vérifiez votre code HTML et corrigez-le avant d&#39;effectuer à nouveau cette mise à jour.

En ce qui concerne les fragments, tenez compte des points suivants :

* Si vous souhaitez ajouter un fragment à un nouvel email ou à un modèle et que ce message s&#39;affiche, vous devez d&#39;abord mettre à jour ce fragment.

* Si vous disposez de plusieurs fragments, vous devez mettre à jour ceux que vous souhaitez utiliser dans le contenu d&#39;un email.

* Pour éviter tout impact sur les emails en cours qui ne sont pas encore préparés, vous pouvez choisir de ne pas mettre à jour certains fragments.

* Vous pouvez toujours envoyer des emails dans lequel un fragment n&#39;étant pas à jour est déjà utilisé, mais celui-ci n&#39;est pas modifiable.

* La mise à jour des fragments utilisés dans des emails déjà préparés n&#39;a aucun impact sur ces derniers.

## Limitations du Concepteur d&#39;email       {#email-designer-limitations}

* Vous ne pouvez pas utiliser de champs de personnalisation dans un fragment. Pour plus d&#39;informations sur les fragments, voir [cette section](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->

* Lors de l&#39;édition de styles, seules les polices web officiellement prises en charge par la plupart des clients d&#39;email sont disponibles.
* Les styles ne peuvent pas être enregistrés en tant que thème pour une réutilisation ultérieure. Le style CSS peut toutefois être enregistré dans un modèle de contenu ou dans un email. Pour plus d&#39;informations sur les styles, voir [cette section](../../designing/using/styles.md).
* La balise meta de référent n’est pas prise en charge dans le Concepteur d’email.
* Les paires de substitution, les caractères non inclus dans le plan multilingue de base du jeu de caractères Unicode, ne peuvent pas être stockés sur 2 octets (16 bits) et doivent être codés sur 2 caractères UTF-16. Ces caractères incluent certains idéographes CJK, la plupart des émoticônes et certaines langues.<br>Ces caractères peuvent provoquer des problèmes d’incompatibilité dans le texte dynamique. Vous devez effectuer des tests stricts avant d&#39;envoyer vos messages.

**Rubriques connexes :**

* Vidéo [Créer un email](../../channels/using/creating-an-email.md)
* [Concevoir une landing page](../../channels/using/designing-a-landing-page.md)
* [Créer un SMS](../../channels/using/creating-an-sms-message.md)
* [Créer et envoyer une notification push](../../channels/using/preparing-and-sending-a-push-notification.md)
