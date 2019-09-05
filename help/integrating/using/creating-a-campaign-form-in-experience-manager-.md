---
title: 'Création d''un formulaire Campaign dans Experience Manager '
seo-title: 'Création d''un formulaire Campaign dans Experience Manager '
description: 'Création d''un formulaire Campaign dans Experience Manager '
seo-description: Avec l'intégration d'Adobe Experience Manager, vous pouvez concevoir des formulaires directement dans AEM afin de créer et mettre à jour des profils ou gérer des abonnements.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: ht
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Création d'un formulaire Campaign dans Experience Manager {#creating-a-campaign-form-in-experience-manager}

Vous pouvez créer des pages de type « formulaire » sur vos sites AEM et mapper les champs de ces formulaires aux champs de la base de données Adobe Campaign, afin de créer et mettre à jour des profils ou de gérer les abonnements d'un service.

Pour créer un formulaire Adobe Campaign sur votre site AEM :

1. Dans votre site AEM, créez une page basée sur le modèle **Profil Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. Dans les propriétés de la page, sélectionnez le **[!UICONTROL Cloud Service]** correspondant à votre instance Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Sélectionnez le type de formulaire à partir du composant **[!UICONTROL Début du formulaire]** :

   * **Adobe Campaign : enregistrer le profil**
   * **Adobe Campaign : s'abonner aux services**
   * **Adobe Campaign : se désabonner des services**

1. Editez le contenu du formulaire en ajoutant différents champs et composants que vous pouvez mapper aux champs de la base Adobe Campaign.
1. Testez et publier le formulaire afin de le rendre accessible sur votre site AEM.

Pour plus d'informations, consultez la [documentation détaillée](https://helpx.adobe.com/fr/experience-manager/6-2/sites/authoring/using/adobe-campaign-forms.html).
