---
title: Gestion des données de formulaire de landing page
description: Découvrez comment gérer les données de formulaire de landing page.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# Gestion des données de formulaire de landing page{#managing-landing-page-form-data}

## Modifier les propriétés des données d&#39;un formulaire pour une landing page{#changing-a-landing-page-form-data-properties}

Vous pouvez associer des champs de la base à des blocs de type zone de saisie, bouton radio ou case à cocher. To do this, select the block and enter the **[!UICONTROL Form data]** in the palette.

![](assets/delivery_content_9.png)

* La zone de sélection **Champ** permet de sélectionner un champ de la base de données à associer avec le champ du formulaire.
* L&#39;option **Obligatoire** permet de n&#39;autoriser la validation de la page que si l&#39;utilisateur a renseigné le champ. Si un champ obligatoire n&#39;est pas renseigné, un message d&#39;erreur sera affiché.

## Association des champs de formulaire  {#mapping-form-fields}

Les champs de saisie sont utilisés pour stocker ou mettre à jour les données dans la base de données Campaign. Pour cela, vous devez associer des champs de la base de données à des blocs de type zone de saisie, bouton radio ou case à cocher. Pour cela :

1. Sélectionnez un bloc dans la landing page.
1. Remplissez la **[!UICONTROL Form data]** partie dans la palette.

   ![](assets/editing_lp_content_4.png)

1. Choose a database field to link with the form field in the **[!UICONTROL Field]** selection zone. Les landing pages peuvent seulement être mappées avec des **profils**.

1. Cochez l’ **[!UICONTROL Mandatory]** option si nécessaire. La page ne peut être envoyée que si l’utilisateur a rempli ce champ. Si un champ obligatoire n&#39;est pas renseigné, un message d&#39;erreur s&#39;affiche lorsque l&#39;utilisateur valide la page.

1. Définissez le type de champ en choisissant, par exemple **[!UICONTROL Text]**, **[!UICONTROL Number]** ou **[!UICONTROL Date]** dans la zone de **[!UICONTROL HTML type of the field]** sélection.
Si vous choisissez une valeur obligatoire **[!UICONTROL Checkbox]**, assurez-vous qu’elle est de **[!UICONTROL Field]** type.

>[!NOTE]
>
>Les champs par défaut des landing pages intégrées sont préconfigurés. Vous pouvez les modifier si nécessaire.

## Réconciliation et stockage des données{#data-storage-and-reconciliation}

Les paramètres de réconciliation permettent de définir le mode de gestion des données entrées dans la landing page lors de sa validation par un visiteur.

Pour cela :

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_parameters_4.png)

1. Select the **[!UICONTROL Reconciliation key]**: these database fields (for example: email, first name, last name) are used to determine whether the visitor has a profile that is already known in the Adobe Campaign database. Cela permet de mettre à jour ou de créer un profil, en fonction des paramètres de stratégie de mise à jour définis.
1. Define the **[!UICONTROL Form parameter mapping]**: this section allows you to map the landing page field parameters and those used in the reconciliation key.
1. Select the **[!UICONTROL Update strategy]**: if the reconciliation key recovers an existing database profile, you can choose for this profile to be updated with the data entered in the form or instead prevent this update.
