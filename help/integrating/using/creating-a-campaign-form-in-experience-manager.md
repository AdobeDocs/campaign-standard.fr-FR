---
title: Création d'un formulaire Campaign dans Experience Manager
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez concevoir des formulaires directement dans AEM afin de créer et mettre à jour des profils ou gérer des abonnements.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 100%

---

# Création d&#39;un formulaire Campaign dans Experience Manager {#creating-a-campaign-form-in-experience-manager}

Vous pouvez créer des pages de type « formulaire » sur vos sites AEM et mapper les champs de ces formulaires aux champs de la base de données Adobe Campaign, afin de créer et mettre à jour des profils ou de gérer les abonnements d&#39;un service.

Pour créer un formulaire Adobe Campaign sur votre site AEM :

1. Dans votre site AEM, créez une page basée sur le modèle **Profil Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. Dans les propriétés de la page, sélectionnez le **[!UICONTROL Cloud Service]** correspondant à votre instance Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Sélectionnez le type de formulaire à partir du composant **[!UICONTROL Début du formulaire]** :

   * **Adobe Campaign : enregistrer le profil**
   * **Adobe Campaign : s&#39;abonner aux services**
   * **Adobe Campaign : se désabonner des services**

1. Editez le contenu du formulaire en ajoutant différents champs et composants que vous pouvez mapper aux champs de la base Adobe Campaign.
1. Testez et publier le formulaire afin de le rendre accessible sur votre site AEM.

Pour plus d&#39;informations, consultez la [documentation détaillée](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=fr).
