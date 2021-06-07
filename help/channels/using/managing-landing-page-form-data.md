---
solution: Campaign Standard
product: campaign
title: Gestion des données de formulaire de landing page
description: Découvrez comment gérer les données de formulaire de landing page.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing pages
role: Business Practitioner
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: d84a11d4064938792a2e2c365b6085c263f55648
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 62%

---

# Gestion des données de formulaire de landing page{#managing-landing-page-form-data}

## Modifier les propriétés des données d&#39;un formulaire pour une landing page{#changing-a-landing-page-form-data-properties}

Vous pouvez associer des champs de la base à des blocs de type zone de saisie, bouton radio ou case à cocher. Pour cela, sélectionnez le bloc et accédez aux **[!UICONTROL Données du formulaire]** dans la palette.

![](assets/delivery_content_9.png)

* La zone de sélection **Champ** permet de sélectionner un champ de la base de données à associer avec le champ du formulaire.
* L&#39;option **Obligatoire** permet de n&#39;autoriser la validation de la page que si l&#39;utilisateur a renseigné le champ. Si un champ obligatoire n&#39;est pas renseigné, un message d&#39;erreur sera affiché.

## Association des champs de formulaire      {#mapping-form-fields}

Les champs de saisie sont utilisés pour stocker ou mettre à jour les données dans la base de données Campaign. Pour cela, vous devez associer des champs de la base de données à des blocs de type zone de saisie, bouton radio ou case à cocher. Pour cela :

1. Sélectionnez un bloc dans la landing page.
1. Renseignez la partie **[!UICONTROL Données de formulaire]** de la palette.

   ![](assets/editing_lp_content_4.png)

1. Sélectionnez un champ de base de données à associer au champ de formulaire dans la zone de sélection **[!UICONTROL Champ.]** Les landing pages peuvent seulement être mappées avec des **profils**.

1. Si nécessaire, cochez l’option **[!UICONTROL Obligatoire]**. La page ne peut être envoyée que si l’utilisateur a renseigné ce champ. Si un champ obligatoire n&#39;est pas renseigné, un message d&#39;erreur s&#39;affiche lorsque l&#39;utilisateur valide la page.

1. Il est enfin possible de définir le type du champ en choisissant par exemple **[!UICONTROL Texte]**, **[!UICONTROL Nombre]** ou **[!UICONTROL Date]** dans la zone de sélection **[!UICONTROL Type HTML du champ.]**
Si vous sélectionnez une **[!UICONTROL case à cocher]** obligatoire, assurez-vous qu’elle est de type **[!UICONTROL Champ]**.

>[!NOTE]
>
>Les champs par défaut des landing pages intégrées sont préconfigurés. Vous pouvez les modifier si nécessaire.

## Réconciliation et stockage des données{#data-storage-and-reconciliation}

Les paramètres de réconciliation permettent de définir le mode de gestion des données entrées dans la landing page lors de sa validation par un visiteur.

Pour cela :

1. Editez les propriétés de la landing page accessibles via l&#39;icône ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page, puis affichez les paramètres **[!UICONTROL Traitement]**.

   ![](assets/lp_parameters_4.png)

1. Sélectionnez la **[!UICONTROL Clé de réconciliation]** : ces champs de la base (par exemple : email, nom, prénom, etc.) sont utilisés pour déterminer si le visiteur a déjà un profil connu dans la base Adobe Campaign. Cela permet de mettre à jour ou de créer un profil, en fonction des paramètres de stratégie de mise à jour définis.
1. Définissez la **[!UICONTROL Correspondance des paramètres du formulaire]** : cette section permet de mettre en correspondance les paramètres des champs de la landing page et ceux utilisés dans la clé de réconciliation.
1. Sélectionnez la **[!UICONTROL Stratégie de mise à jour]** : si la clé de réconciliation permet de retrouver un profil existant en base, vous pouvez mettre à jour ce profil avec les données entrées dans le formulaire ou bien empêcher cette mise à jour.

## Case à cocher Contrat {#agreement-checkbox}

Vous pouvez ajouter une case à cocher que le profil doit vérifier avant d’envoyer la landing page.

Cela vous permet, par exemple, de demander le consentement des utilisateurs pour la politique de confidentialité ou de les obliger à accepter vos conditions générales avant d’envoyer le formulaire.

<!--This is particularly useful in the following case:

When a profile opens the landing page from an Outlook.com mailbox, Outlook checks whether the links on the landing page are suspicious. However, this Outlook security feature (called safelinks) has an unwanted effect: it automatically activates the buttons included on the landing page. Consequently, profiles are automatically subscribed or unsubscribed without confirmation when the landing page is displayed after clicking the email link, even if they do not submit the form.

![](assets/lp_submit_button.png)

To avoid this, Adobe recommends you always add to your landing page a checkbox which enables the profile to agree before proceeding with subscription or unsubscription.-->

>[!IMPORTANT]
>
>La sélection de cette case à cocher est obligatoire pour vos utilisateurs. S&#39;il n&#39;est pas sélectionné, il ne pourra pas envoyer la landing page.

Pour insérer et configurer cette case à cocher, procédez comme suit :

1. Lors de la conception de la landing page, cliquez sur **[!UICONTROL Afficher la source]**.

   ![](assets/lp_show_source.png)

1. Insérez manuellement une case à cocher, comme dans l’exemple ci-dessous :

   ![](assets/lp_checkbox_code.png)

   <!--
   <div id="HtmlPage_htmlPage.line3" data-nl-format="datetime"><input type="checkbox" class="nl-dce-todo" data-nl-bindto="agreement" data-nl-agreementmsg="You must agree with the terms and conditions before proceeding" />I agree with the terms and conditions</div>
   -->

1. Cliquez sur **[!UICONTROL Masquer la source]**.

1. La nouvelle case à cocher s’affiche. Sélectionnez-le.

   ![](assets/lp_select_checkbox.png)

1. La liste déroulante correspondante est affichée dans la section **[!UICONTROL Données du formulaire]** de la palette. Sélectionnez **[!UICONTROL Accord]** dans la liste.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >L’élément **[!UICONTROL Agreement]** n’est pas mappé à un champ de la base de données Campaign.

1. Cliquez sur l’icône ![](assets/lp-properties-icon.png) en regard de **[!UICONTROL Données du formulaire]** pour accéder aux propriétés avancées de la case à cocher.

1. Si nécessaire, vous pouvez modifier le message.

   ![](assets/lp_agreement_message.png)

   Ce texte s’affiche sous forme d’avertissement si l’utilisateur ne coche pas la case avant d’envoyer le formulaire.

   >[!NOTE]
   >
   >Cette action est obligatoire par défaut et ne peut pas être modifiée.

1. Cliquez sur **[!UICONTROL Confirmer]**.

Désormais, chaque fois que la landing page s’affiche, l’utilisateur doit cocher cette case avant d’envoyer le formulaire. Si ce n’est pas le cas, l’avertissement s’affiche et l’utilisateur ne peut pas envoyer le formulaire tant que la case à cocher n’est pas activée.