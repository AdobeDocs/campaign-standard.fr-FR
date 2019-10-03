---
title: 'Création et utilisation d''un contenu réutilisable '
seo-title: Création et utilisation d'un contenu réutilisable
description: Création et utilisation d'un contenu réutilisable
seo-description: Commencez à créer du contenu d'email réutilisable avec le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: ht
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---

# Création et utilisation d'un contenu réutilisable {#using-reusable-content}

Découvrez comment maîtriser l'édition de contenu d'email. Avec le Concepteur d'email, vous pouvez créer des modèles et des fragments avec votre contenu prédéfini et les réutiliser pour les prochaines diffusions.

## Conception à l'aide de modèles {#designing-templates}

>[!NOTE]
>
> Dans Adobe Campaign Standard, vous pouvez créer différents types de modèles accessibles à partir du menu **Ressources** &gt; **Modèles**. Les modèles utilisés dans le Concepteur d'email sont des modèles de contenu. Pour plus d'informations, voir [A propos des modèles](../../start/using/about-templates.md).

### Modèles de contenu  {#content-templates}

Vous pouvez gérer les contenus HTML qui seront proposés dans l'onglet **[!UICONTROL Modèles]** de la page d'accueil du [Concepteur d'email. ](../../designing/using/overview.md) Les différents modèles présentent de multiples combinaisons de plusieurs types d'éléments. Par exemple, les modèles 'Contour progressif' possèdent des marges, tandis que les modèles 'Astro' en sont dépourvus. Voir à ce propos la section [Modèles de contenu](../../designing/using/using-reusable-content.md#content-templates).

![](assets/template_content.png)

Pour savoir comment créer un email à partir d'un modèle d'usine, reportez-vous à [Concepteur d'email](../../designing/using/quick-start.md#building-content-from-an-out-of-the-box-template).

### Créer un modèle de contenu {#creating-a-content-template}

Vous pouvez créer vos propres modèles de contenu pour les utiliser autant de fois que nécessaire.

L'exemple ci-dessous montre comment créer un modèle de contenu d'email.

1. Accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**, puis cliquez sur **[!UICONTROL Créer]**.
1. Cliquez sur le libellé d'email de façon à accéder à l'onglet **[!UICONTROL Propriétés]** du Concepteur d'email.
1. Spécifiez un libellé reconnaissable et sélectionnez les paramètres suivants afin d'utiliser ce modèle dans les emails :

   * Sélectionnez **[!UICONTROL Partagé]** ou **[!UICONTROL Diffusion]** dans la liste déroulante **[!UICONTROL Type de contenu]**.
   * Sélectionnez **[!UICONTROL Modèle]** dans la liste déroulante **[!UICONTROL Type HTML]**.
   ![](assets/email_designer_create-template.png)

1. Si nécessaire, vous pouvez définir une image qui sera utilisée comme miniature du modèle. Sélectionnez-la dans l'onglet **[!UICONTROL Miniature]** des propriétés de modèle.

   ![](assets/email_designer_create-template_thumbnail.png)

   Cette miniature sera affichée dans l'onglet **[!UICONTROL Modèles]** de la page d'accueil du [Concepteur d'email](../../designing/using/overview.md#about-the-email-designer).

1. Fermez l'onglet **[!UICONTROL Propriétés]** pour retourner à l'espace de travail principal.
1. Ajoutez des composants de structure et de contenu que vous pouvez personnaliser au besoin.
   >[!NOTE]
   >
   > Vous ne pouvez pas insérer des champs de personnalisation ni du contenu conditionnel dans un modèle de contenu.
1. Une fois le modèle édité, enregistrez-le.

Ce modèle peut à présent être utilisé dans n'importe quel email créé avec le Concepteur d'email. Sélectionnez-le dans l'onglet **[!UICONTROL Modèles]** de la page d'accueil du [Concepteur d'email](../../designing/using/overview.md#about-the-email-designer).

![](assets/content_template_new.png)

### Enregistrer du contenu en tant que modèle {#saving-content-as-template}

Lorsque vous éditez un email avec le Concepteur d'email, vous ne pouvez pas enregistrer directement le contenu de cet email en tant que modèle.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Sélectionnez **[!UICONTROL Enregistrer en tant que modèle]** dans la barre d'outils principale du Concepteur d'email.

   ![](assets/email_designer_save-as-template.png)

1. Ajoutez un libellé et une description en cas de besoin, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Pour retrouver le modèle que vous venez de créer, accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**.

1. Pour utiliser votre nouveau modèle, sélectionnez-le dans l'onglet **[!UICONTROL Modèles]** de la page d'accueil du [Concepteur d'email](../../designing/using/overview.md#about-the-email-designer).

   ![](assets/content_template_new.png)

### Création d'un modèle avec des fragments et des composants {#template-fragments-components}

Vous pouvez maintenant créer un modèle d'email à l'aide du Concepteur d'email. Utilisez des composants de contenu pour représenter les différentes sections de votre email et ajustez les paramètres pour qu'ils ressemblent autant que possible à votre newsletter d'origine. Insérez enfin les fragments que vous venez de créer.

1. A l'aide du Concepteur d'email, créez un modèle. Voir à ce propos la section [Modèles de contenu](../../designing/using/using-reusable-content.md#content-templates).
1. Insérez plusieurs composants de structure dans votre modèle, correspondant à l'en-tête, au pied de page et au corps de votre email. Pour plus d'informations sur l'ajout de composants de structure, voir [Editer la structure d'un email à l'aide du Concepteur d'email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Insérez autant de composants de contenu que nécessaire pour créer le corps de votre newsletter. Il s'agit du contenu éditable de l'email que vous mettrez à jour tous les mois.

   ![](assets/des_loading_compatible_fragment_5.png)

   Si vous maîtrisez le code HTML, Adobe recommande d'utiliser les composants **[!UICONTROL Html]** dans lesquels vous pouvez copier-coller les éléments les plus complexes de l'email d'origine. Utilisez d'autres composants comme **[!UICONTROL Button]**, **[!UICONTROL Image]** ou **[!UICONTROL Text]** pour le contenu restant. Voir à ce propos la section [A propos des composants de contenu](../../designing/using/designing-from-scratch.md#about-content-components).

   >[!NOTE]
   >
   >L'utilisation du composant **[!UICONTROL Html]** entraîne la création de composants éditables avec des options limitées. Vous devez savoir gérer le code HTML pour sélectionner ce composant.

1. Ajustez les composants du contenu pour qu'ils correspondent autant que possible à l'email d'origine.

   ![](assets/des_loading_compatible_fragment_6.png)

   Pour plus d'informations sur la gestion des paramètres de style et les attributs intégrés, voir [Editer les styles d'un email](../../designing/using/styles.md).

1. Insérez les deux fragments (en-tête et pied de page) que vous avez précédemment créés dans les composants de structure de votre choix.

   ![](assets/des_loading_compatible_fragment_10.png)

1. Enregistrez votre modèle.

Vous pouvez maintenant gérer entièrement ce modèle dans le Concepteur d'email afin de créer et mettre à jour la newsletter que vous enverrez tous les mois à vos destinataires.

Pour l'utiliser, créez un email et sélectionnez le modèle de contenu que vous venez de créer.

**Rubrique connexe** :

* [Créer un email](../../channels/using/creating-an-email.md)
* [Vidéo d'introduction au Concepteur d'email](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=fre_fr)
* [Concevoir entièrement un contenu d'email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## A propos des fragments  {#about-fragments}

Un fragment est un composant réutilisable pouvant être référencé dans un ou plusieurs emails.
Il se trouve dans l'interface sous **Ressources** &gt; **Contenu, fragments et modèles**.

Pour optimiser les fragments dans le Concepteur d'email :

* Créez vos propres fragments. Voir [Créer un fragment de contenu](../../designing/using/using-reusable-content.md#creating-a-content-fragment) et [Enregistrer du contenu en tant que fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).
* Utilisez-les autant de fois que nécessaire dans vos emails. Voir [Insérer des éléments dans un email](../../designing/using/using-reusable-content.md#inserting-elements-into-an-email).
* Lorsque vous éditez un fragment, les modifications sont synchronisées : elles sont automatiquement propagées à tous les emails (à condition qu'ils n'aient pas encore été préparés ou envoyés) contenant ce fragment.

Lorsqu'ils sont ajoutés à un email, les fragments sont verrouillés par défaut. Si vous souhaitez modifier un fragment pour un email spécifique, vous pouvez arrêter la synchronisation avec le fragment d'origine en le déverrouillant dans l'email dans lequel il est utilisé. Les modifications ne seront plus synchronisées.

Pour déverrouiller un fragment dans un email, sélectionnez-le et cliquez sur l'icône représentant un verrou dans la barre d'outils contextuelle.

![](assets/des_unlocking_fragment.png)

Ce fragment devient alors un composant autonome qui n'est plus lié au fragment d'origine. Il peut ensuite être édité comme n'importe quel autre composant de contenu. Voir [A propos des composants de contenu](../../designing/using/designing-from-scratch.md#about-content-components).

### Insertion de fragments dans un email {#inserting-elements-into-an-email}

Pour définir le contenu de votre email, vous pouvez ajouter des éléments de contenu aux composants de structure que vous avez préalablement placés. Voir [Editer la structure de l'email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Accédez aux éléments de contenu en sélectionnant l'icône **+** sur la gauche. Sélectionnez [Fragments](../../designing/using/using-reusable-content.md#about-fragments) ou [Composants du contenu](../../designing/using/designing-from-scratch.md#about-content-components).
1. Si vous connaissez déjà tout ou partie du libellé du fragment que vous souhaitez ajouter, vous pouvez le rechercher.

   ![](assets/email_designer_fragmentsearch.png)

1. Déposez un composant de contenu ou un fragment depuis la palette dans un composant de structure de l'email.

   ![](assets/email_designer_addfragment.png)

   Une fois un élément ajouté à l'email, il peut être déplacé à l'intérieur du composant de structure ou vers un autre composant de structure de l'email.

   ![](assets/email_designer_movefragment.png)

1. Editez l'élément pour répondre aux besoins de cet email. Vous pouvez ajouter du texte, des liens, des images, etc.

   >[!NOTE]
   >
   >Les fragments sont verrouillés par défaut lorsqu'ils sont ajoutés à un email. Vous pouvez arrêter la synchronisation avec le fragment d'origine si vous souhaitez modifier le fragment d'un email spécifique. Vous pouvez aussi directement apporter votre modification dans le fragment. Voir [A propos des fragments](../../designing/using/using-reusable-content.md#about-fragments).

1. Répétez cette procédure pour tous les éléments que vous devez ajouter à votre email.
1. Enregistrez votre email.

Maintenant que la structure de l'email est remplie, vous pouvez modifier le style de chaque élément de contenu. Voir [Editer un élément](../../designing/using/styles.md#editing-an-element).

>[!NOTE]
>
>Si un fragment est modifié, les changements sont automatiquement propagés dans les emails dans lequel il est utilisé. Voir à ce propos la section [A propos des fragments](../../designing/using/using-reusable-content.md#about-fragments).

### Créer un fragment de contenu  {#creating-a-content-fragment}

Vous pouvez créer vos propres fragments de contenu pour les utiliser selon vos besoins dans un ou plusieurs emails.

1. Accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**, puis cliquez sur **[!UICONTROL Créer]**.
1. Cliquez sur le libellé d'email de façon à accéder à l'onglet **[!UICONTROL Propriétés]** du Concepteur d'email.
1. Spécifiez un libellé reconnaissable et sélectionnez les paramètres suivants afin de retrouver le fragment lors de l'édition d'un contenu d'email :

   * Les fragments étant uniquement compatibles avec les emails, sélectionnez **[!UICONTROL Diffusion]** dans la liste déroulante **[!UICONTROL Type de contenu]**.
   * Sélectionnez **[!UICONTROL Fragment]** dans la liste déroulante **[!UICONTROL Type HTML]** afin de pouvoir utiliser ce contenu en tant que fragment.
   ![](assets/email_designer_createfragment.png)

1. Si nécessaire, vous pouvez définir une image qui sera utilisée comme miniature du fragment. Sélectionnez-la dans l'onglet **[!UICONTROL Miniature]** des propriétés de modèle.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Cette miniature apparaîtra en regard du libellé du fragment lorsque vous éditez un email.

1. Fermez l'onglet **[!UICONTROL Propriétés]** pour retourner à l'espace de travail principal.
1. Ajoutez des composants de structure et de contenu que vous pouvez personnaliser au besoin.

   >[!NOTE]
   >
   >Les fragments ne peuvent pas inclure des champs de personnalisation, un contenu dynamique ni un autre fragment.
   >La [vue mobile](../../designing/using/styles.md#switching-to-mobile-view) n'est pas disponible dans les fragments.

1. Une fois le fragment édité, enregistrez-le.

Ce fragment peut à présent être utilisé dans n'importe quel email créé avec le Concepteur d'email. Il apparaît sous la section **[!UICONTROL Fragments]** de la palette.

>[!NOTE]
>
>Vous ne pouvez pas insérer de champs de personnalisation dans un fragment sauf s'il est utilisé dans un email et qu'il est déverrouillé. Voir [A propos des fragments](../../designing/using/using-reusable-content.md#about-fragments).

### Enregistrer du contenu en tant que fragment  {#saving-content-as-a-fragment}

Lorsque vous éditez un email avec le Concepteur d'email, vous pouvez enregistrer directement une partie de cet email en tant que fragment.

* Vous ne pouvez pas enregistrer en tant que fragment une structure contenant des champs de personnalisation, du contenu dynamique ou un autre fragment.
* Vous pouvez uniquement sélectionner des structures adjacentes.
<!-- - You cannot select an empty structure.-->

1. Lors de l'édition d'un email dans le Concepteur d'email, sélectionnez **[!UICONTROL Enregistrer en tant que fragment]** dans la barre d'outils principale.

   ![](assets/email_designer_save-as-fragment.png)

1. Dans l'espace de travail, sélectionnez les structures qui composeront le fragment.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Veillez à sélectionner des structures qui sont adjacentes et qui ne comprennent pas de champs de personnalisation, de contenu dynamique ni un autre fragment.
   <!--You cannot select an empty structure.-->

1. Cliquez sur **[!UICONTROL Créer]**.

1. Ajoutez un libellé et une description en cas de besoin, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. Pour retrouver le fragment que vous venez de créer, accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles de contenu et fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Pour utiliser le nouveau fragment, ouvrez n'importe quel contenu d'email et sélectionnez-le dans la liste des fragments.

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>La [vue mobile](../../designing/using/styles.md#switching-to-mobile-view) n'est pas disponible dans les fragments. Si vous souhaitez éditer la vue mobile d'un email, faites-le avant d'enregistrer votre contenu en tant que fragment.

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

## Création d'en-têtes et de pieds de page réutilisables à l'aide de fragments {#header-footer-fragments}

A l'aide du Concepteur d'email, créez un fragment pour chaque section réutilisable. Dans cet exemple, vous allez créer deux fragments : un pour l'en-tête et un autre pour le pied de page. Vous pouvez ensuite copier les parties pertinentes de votre contenu existant dans ces fragments.

Pour ce faire, procédez comme suit :

1. Dans Adobe Campaign, accédez à **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles et fragments de contenu]**, puis créez un fragment pour votre en-tête. Voir à ce propos la section [Créer un fragment de contenu](../../designing/using/using-reusable-content.md#creating-a-content-fragment).
1. Ajoutez autant de composants de structure que vous le souhaitez à votre fragment.

![](assets/des_loading_compatible_fragment_1.png)

1. Ajoutez des composants d'image et de texte à votre structure.

![](assets/des_loading_compatible_fragment_2.png)

1. Téléchargez l'image correspondante, saisissez votre texte et ajustez les paramètres.

![](assets/des_loading_compatible_fragment_3.png)

1. Enregistrez votre fragment.
1. Procédez de la même manière pour créer votre pied de page et enregistrez-le.

![](assets/des_loading_compatible_fragment_4.png)

Vos fragments peuvent maintenant être utilisés dans un modèle.
