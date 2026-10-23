---
title: Création d'un formulaire Campaign dans Experience Manager
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez concevoir des formulaires directement dans AEM afin de créer et mettre à jour des profils ou gérer des abonnements.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: 'https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '191'
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
