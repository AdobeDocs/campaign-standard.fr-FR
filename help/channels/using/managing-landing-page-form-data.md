---
title: Gestion des données de formulaire de page d’entrée
seo-title: Gestion des données de formulaire de page d’entrée
description: Gestion des données de formulaire de page d’entrée
seo-description: Découvrez comment gérer les données de formulaire de page d’entrée.
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
source-git-commit: 9cdfafad7a2ac2db59b037962a84aa03568a55e6

---


# Gestion des données de formulaire de page d’entrée{#managing-landing-page-form-data}

## Modifier les propriétés des données d'un formulaire pour une landing page{#changing-a-landing-page-form-data-properties}

Vous pouvez associer des champs de la base à des blocs de type zone de saisie, bouton radio ou case à cocher. Pour cela, sélectionnez le bloc et renseignez la partie **[!UICONTROL Données du formulaire]** dans la palette.

![](assets/delivery_content_9.png)

* La zone de sélection **Champ** permet de sélectionner un champ de la base de données à associer avec le champ du formulaire.
* L'option **Obligatoire** permet de n'autoriser la validation de la page que si l'utilisateur a renseigné le champ. Si un champ obligatoire n'est pas renseigné, un message d'erreur sera affiché.

## Association des champs de formulaire   {#mapping-form-fields}

Les champs de saisie sont utilisés pour stocker ou mettre à jour les données dans la base de données Campaign. Pour cela, vous devez associer des champs de la base de données à des blocs de type zone de saisie, bouton radio ou case à cocher. Pour cela :

1. Sélectionnez un bloc dans la landing page.
1. Renseignez la partie **[!UICONTROL Données de formulaire]** de la palette.

   ![](assets/editing_lp_content_4.png)

1. Sélectionnez un champ de base de données à associer au champ de formulaire dans la zone de sélection **[!UICONTROL Champ]**.

   Quand l'option **[!UICONTROL Obligatoire]** est cochée, la validation de la page est autorisée uniquement si l'utilisateur a renseigné le champ correspondant. Si un champ obligatoire n'est pas renseigné, un message d'erreur s'affiche lorsque l'utilisateur valide la page.

   >[!NOTE]
   >
   >Les landing pages peuvent seulement être mappées avec des **profils**.

1. Il est enfin possible de définir le type du champ en choisissant par exemple **[!UICONTROL Texte]**, **[!UICONTROL Nombre]** ou **[!UICONTROL Date]** dans la zone de sélection **[!UICONTROL Type HTML du champ]**.

>[!NOTE]
>
>Les champs par défaut des landing pages intégrées sont préconfigurés. Vous pouvez les modifier si nécessaire.

## Associer un formulaire à un service   {#linking-a-form-to-a-service}

Vous pouvez associer un formulaire à un service afin que les profils puissent s'inscrire à un service spécifique lors de la validation des landing pages.

Les paramètres d'association permettent de définir le type de l'action réalisée et si la landing page est liée spécifiquement à un seul service ou si elle est générique.

Pour sélectionner le service à associer, procédez comme suit :

1. Editez les propriétés de la landing page accessibles via l'icône ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page, puis affichez les paramètres **[!UICONTROL Traitement]**.

   ![](assets/lp_edit_properties_button.png)

1. Sélectionnez **[!UICONTROL Inscription]** dans la liste déroulante **[!UICONTROL Actions spécifiques]**.

   ![](assets/lp_parameters_5.png)

1. Sélectionnez **[!UICONTROL Service spécifique]** pour associer la landing page à un seul service. Ne sélectionnez pas cette option si vous souhaitez utiliser plusieurs services avec la landing page.

   Utilisez l'option **[!UICONTROL Service provenant de l'URL]** pour que la landing page puisse être utilisée pour plusieurs services. Vous devez alors référencer la landing page lors du paramétrage du service.

## Réconciliation et stockage des données{#data-storage-and-reconciliation}

Les paramètres de réconciliation permettent de définir le mode de gestion des données entrées dans la landing page lors de sa validation par un visiteur.

Pour cela :

1. Editez les propriétés de la landing page accessibles via l'icône ![](assets/edit_darkgrey-24px.png) dans le tableau de bord de la landing page, puis affichez les paramètres **[!UICONTROL Traitement]**.

   ![](assets/lp_parameters_4.png)

1. Sélectionnez la **[!UICONTROL Clé de réconciliation]** : ces champs de la base (par exemple : email, nom, prénom, etc.) sont utilisés pour déterminer si le visiteur a déjà un profil connu dans la base Adobe Campaign. Cela permet de mettre à jour ou de créer un profil, en fonction des paramètres de stratégie de mise à jour définis.
1. Définissez la **[!UICONTROL Correspondance des paramètres du formulaire]** : cette section permet de mettre en correspondance les paramètres des champs de la landing page et ceux utilisés dans la clé de réconciliation.
1. Sélectionnez la **[!UICONTROL Stratégie de mise à jour]** : si la clé de réconciliation permet de retrouver un profil existant en base, vous pouvez mettre à jour ce profil avec les données entrées dans le formulaire ou bien empêcher cette mise à jour.
