---
title: Gestion des données de formulaire de landing page
description: Découvrez comment gérer les données de formulaire de landing page.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 100%

---

# Gestion des données de formulaire de landing page{#managing-landing-page-form-data}

Dans le contenu de la landing page, les champs de saisie sont utilisés pour stocker ou mettre à jour les données de la base de données Campaign.

Pour cela, ces champs doivent être mappés aux champs de la base de données.

Vous pouvez définir et gérer leur mappage à l&#39;aide de la section **[!UICONTROL Données de formulaire]** de la palette de gauche.

![](assets/lp_form-data.png)

## Mappage des champs de formulaire  {#mapping-form-fields}

Pour mettre à jour la base de données Campaign selon vos besoins, associez les champs pertinents de la base de données aux blocs de type zone de saisie, bouton radio ou case à cocher de votre landing page.

Pour ce faire, procédez comme suit :

1. Sélectionnez un bloc dans le contenu de la landing page.

   >[!NOTE]
   >
   >Les champs par défaut des landing pages intégrées sont préconfigurés. Vous pouvez les modifier si nécessaire.

1. Accédez à la section **[!UICONTROL Données de formulaire]** de la palette de gauche.

1. Pour modifier le type de champ, sélectionnez une valeur dans la liste déroulante **[!UICONTROL Type HTML du champ]**.

   ![](assets/lp_html-field-type.png)

   >[!NOTE]
   >
   >Pour plus d&#39;informations sur l&#39;utilisation du type case à cocher dans une landing page, reportez-vous aux sections [Mise à jour de plusieurs abonnements aux services](#multiple-subscriptions) et [Case à cocher Accord](#agreement-checkbox).

1. Si vous sélectionnez un type de champ non compatible avec le champ de base de données actuellement sélectionné dans la zone **[!UICONTROL Champ]**, un message d&#39;avertissement s&#39;affiche. Pour un mappage optimal, sélectionnez une valeur appropriée.

   ![](assets/lp_field-type-warning.png)

1. Utilisez la zone **[!UICONTROL Champ]** pour sélectionner un champ de la base de données qui sera associé au champ du formulaire.

   ![](assets/lp_select-database-field.png)

   >[!NOTE]
   >
   >Les landing pages peuvent uniquement être mappées aux ressources **[!UICONTROL Profils]** ou **[!UICONTROL Service]**.

   Dans cet exemple, mappez le champ **Nom** de votre landing page au champ **[!UICONTROL Nom]** de la ressource **[!UICONTROL Profils]**.

   ![](assets/lp_database-field-example.png)

1. Si nécessaire, cochez l&#39;option **[!UICONTROL Obligatoire]**. Dans ce cas, la landing page ne peut être envoyée que si l&#39;utilisateur a renseigné ce champ.

   ![](assets/lp_mandatory-option.png)

   Si un champ obligatoire n&#39;est pas renseigné, un message d&#39;erreur s&#39;affiche lorsque l&#39;utilisateur envoie la page.

1. Cliquez sur **[!UICONTROL Confirmer]** pour sauvegarder vos changements.

<!--If you choose a mandatory **[!UICONTROL Checkbox]**, make sure that it is of **[!UICONTROL Field]** type.-->

## Réconciliation et stockage des données{#data-storage-and-reconciliation}

Les paramètres de réconciliation permettent de définir le mode de gestion des données entrées dans la landing page lors de sa validation par un visiteur.

Pour cela :

1. Editez les propriétés de la landing page accessibles via l&#39;icône ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page, puis affichez les paramètres **[!UICONTROL Traitement]**.

   ![](assets/lp_parameters_job.png)

1. Sélectionnez la **[!UICONTROL clé de réconciliation]** : ce champ de base de données permet de déterminer si le visiteur possède un profil déjà connu dans la base de données Adobe Campaign. Il peut s&#39;agir par exemple d&#39;une adresse email, d&#39;un prénom ou d&#39;un nom. La clé de réconciliation permet de mettre à jour ou de créer un profil, en fonction du paramètre **[!UICONTROL Stratégie de mise à jour]** défini ci-dessous.

1. Définissez la **[!UICONTROL Correspondance des paramètres du formulaire]** : cette section permet de mettre en correspondance les paramètres des champs de la landing page et ceux utilisés dans la clé de réconciliation.

1. Sélectionnez la **[!UICONTROL Stratégie de mise à jour]** : si la clé de réconciliation permet de retrouver un profil existant en base, vous pouvez mettre à jour ce profil avec les données entrées dans le formulaire ou bien empêcher cette mise à jour.

   ![](assets/lp_parameters_update-strategy.png)

## Abonnements multiples à des services {#multiple-subscriptions}

Vous pouvez utiliser plusieurs cases à cocher sur une seule landing page pour permettre aux utilisateurs de s&#39;abonner ou de se désabonner de plusieurs services.

Pour ce faire, procédez comme suit :

1. Lors de la conception de la landing page :

   * Sélectionnez un bloc et, dans la section **[!UICONTROL Données de formulaire]**, sélectionnez **[!UICONTROL Case à cocher]** comme type de champ.

     ![](assets/lp_field-type-checkbox.png)

   * Si vous maîtrisez le langage HTML, vous pouvez également insérer manuellement une case à cocher à l&#39;aide du bouton **[!UICONTROL Afficher la source]**.

     ![](assets/lp_show_source.png)

     Vous pouvez ainsi insérer la case à cocher là où cela vous convient dans la page.

     ![](assets/lp_manual-checkbox.png)

1. Assurez-vous que la case est cochée dans votre contenu. La liste déroulante **[!UICONTROL Type]** correspondante est affichée dans la section **[!UICONTROL Données de formulaire]** de la palette de gauche. Sélectionnez **[!UICONTROL Service et abonnement]** dans la liste.

   ![](assets/lp_service-and-subscription.png)

1. Choisissez une option dans la liste déroulante **[!UICONTROL Comportement]**.

   ![](assets/lp_checkbox-behavior.png)

1. Sélectionnez un [service](../../audiences/using/creating-a-service.md) dans la liste correspondante.

   ![](assets/lp_checkbox-service.png)

1. Assurez-vous que l&#39;option **[!UICONTROL Obligatoire]** n&#39;est pas cochée. Sinon, vos utilisateurs n&#39;auront pas le choix.

   ![](assets/lp_uncheck-mandatory.png)

1. Pour ajouter d&#39;autres cases à cocher permettant de s&#39;abonner à d&#39;autres services, répétez les étapes ci-dessus autant de fois que nécessaire.

   ![](assets/lp_multiple-checkboxes.png)

Une fois la landing page publiée, les utilisateurs peuvent cocher plusieurs cases pour s&#39;inscrire à plusieurs newsletters de la même page.

## Case à cocher Accord {#agreement-checkbox}

Vous pouvez ajouter une case à cocher que le profil doit vérifier avant d&#39;envoyer la landing page.

Cela vous permet, par exemple, de demander le consentement des utilisateurs pour la politique de confidentialité ou de les obliger à accepter vos conditions générales avant d&#39;envoyer le formulaire.

>[!IMPORTANT]
>
>La sélection de cette case à cocher est obligatoire pour vos utilisateurs. Si elle n&#39;est pas sélectionnée, ils ne pourront pas envoyer la landing page.

Pour insérer et configurer cette case à cocher, procédez comme suit :

1. Lors de la conception de la landing page :

   * Sélectionnez un bloc et, dans la section **[!UICONTROL Données de formulaire]**, sélectionnez **[!UICONTROL Case à cocher]** comme type de champ.

     ![](assets/lp_field-type-checkbox.png)

   * Si vous maîtrisez le langage HTML, vous pouvez également insérer manuellement une case à cocher à l&#39;aide du bouton **[!UICONTROL Afficher la source]**.

     ![](assets/lp_show_source.png)

     <!--Manually insert a checkbox, such as in the example below:

      <!--Click **[!UICONTROL Hide source]**.-->

1. Assurez-vous que la case est cochée.

   ![](assets/lp_select_checkbox.png)

1. La liste déroulante **[!UICONTROL Type]** correspondante est affichée dans la section **[!UICONTROL Données de formulaire]** de la palette de gauche. Sélectionnez **[!UICONTROL Accord]** dans la liste.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >L&#39;élément **[!UICONTROL Accord]** n&#39;est pas mappé à un champ de la base de données Campaign.

1. Cliquez sur l&#39;icône ![](assets/lp-properties-icon.png) en regard de **[!UICONTROL Données de formulaire]** pour accéder aux propriétés avancées de la case à cocher.

1. Si besoin, vous pouvez modifier le message.

   ![](assets/lp_agreement_message.png)

   Ce texte s&#39;affiche sous forme d&#39;avertissement si l&#39;utilisateur ne coche pas la case avant d&#39;envoyer le formulaire.

   >[!NOTE]
   >
   >Cette action est obligatoire par défaut et ne peut pas être modifiée.

1. Cliquez sur **[!UICONTROL Confirmer]**.

Désormais, chaque fois que la landing page s&#39;affiche, l&#39;utilisateur doit cocher cette case avant d&#39;envoyer le formulaire. Si ce n&#39;est pas le cas, l&#39;avertissement s&#39;affiche et l&#39;utilisateur ne peut pas envoyer le formulaire tant que la case à cocher n&#39;est pas activée.