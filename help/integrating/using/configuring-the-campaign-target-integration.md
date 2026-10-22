---
title: Configurer l'intégration Campaign-Target
description: Découvrez comment configurer l'intégration d'Adobe Target pour commencer à utiliser du contenu dynamique dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: 'https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ'
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
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 100%
---
# Configurer l&#39;intégration Campaign-Target{#configuring-the-campaign-target-integration}

L&#39;intégration entre Adobe Campaign et Adobe Target vous permet d&#39;insérer du contenu dynamique dans votre diffusion.

Dans Adobe Campaign, une configuration est d&#39;abord nécessaire pour utiliser les fonctionnalités d&#39;intégration avec Adobe Target. Celle-ci doit être gérée par l&#39;administrateur fonctionnel.

Les éléments suivants sont nécessaires pour cette procédure :

* un Tenant Adobe Experience Cloud
* un tenant Adobe Target
* un &quot;rawbox&quot; Adobe Target défini afin d&#39;établir la connexion avec Adobe Campaign

1. Depuis le menu avancé, via le logo Adobe Campaign en haut à gauche, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Paramètres de l’application]** > **[!UICONTROL Options]**.
1. Pour configurer les options de tenant et de serveur pour Adobe Target, renseignez les champs suivants :

   * **[!UICONTROL TNT_TenantName]** : nom du tenant Adobe Target. Cette valeur correspond au nom du **[!UICONTROL Client Adobe Target]**.
   * **[!UICONTROL TNT_EdgeServer]** : serveur Adobe Target utilisé pour l&#39;intégration. Cette option est déjà renseignée par défaut. Cette valeur correspond au **[!UICONTROL Server Domain]** Adobe Target, suivie de la valeur **/m2**. Par exemple : **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Vos utilisateurs peuvent désormais ajouter des images dynamiques dans une diffusion avec Adobe Target.
