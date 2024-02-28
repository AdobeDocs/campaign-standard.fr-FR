---
title: Configurer l'intégration Campaign-Target
description: Découvrez comment configurer l'intégration d'Adobe Target pour commencer à utiliser du contenu dynamique dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: ht
source-wordcount: '190'
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
