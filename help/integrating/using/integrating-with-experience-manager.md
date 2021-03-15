---
solution: Campaign Standard
product: campaign
title: A propos de l’intégration Campaign-Experience Manager
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 99%

---


# A propos de l’intégration Campaign-Experience Manager{#integrating-with-experience-manager}

Cette intégration entre Adobe Campaign Standard et Experience Manager vous permet d&#39;utiliser du contenu créé dans Adobe Experience Manager dans vos emails Adobe Campaign.

Vous avez ainsi la possibilité de profiter à la fois des fonctionnalités d&#39;édition de contenu d&#39;Adobe Experience Manager, et des capacités de diffusion et de gestion de données d&#39;Adobe Campaign. Notez que vous ne pouvez pas effectuer de test A/B sur des contenus importés depuis Adobe Experience Manager.

Adobe Campaign Standard est compatible avec Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 et 6.5. Les sections suivantes présentent une vue d’ensemble des actions que vous pouvez exécuter. Pour plus de détails, consultez les sections dédiées au [paramétrage](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/administering/integration/campaignstandard.html) et à l&#39;[utilisation](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) de l&#39;intégration.

>[!NOTE]
>
> Les modèles Adobe Campaign Standard ne sont plus disponibles avec Adobe Experience Manager 6.5.

## Conseils sur l’utilisation de l’intégration Campaign-Experience Manager {#tips-aem}

* **Identifier le modèle à utiliser avec l’intégration**

   Les modèles d’email pouvant être édités dans Adobe Experience Manager, il peut sembler plus facile d’éditer n’importe quel modèle dans cette solution. Mais certains modèles ne sont pas adaptés. Les modèles personnalisés spécifiques à un client ne sont pas recommandés pour cette intégration et doivent être édités directement dans Adobe Campaign Standard.

   Pour plus d’informations sur les modèles, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/developing/platform/templates/templates.html).

* **Vérifiez que l’externaliseur a été configuré pendant l’implémentation.**

   La configuration de l’externaliseur lors de l’implémentation d’Experience Manager pour Adobe Campaign Standard permet de transformer un chemin de ressource en URL. Vous pouvez ainsi rendre vos images visibles sur la page. Si l’externaliseur n’est pas configuré correctement, vos emails contiendront des images endommagées.

   Pour découvrir comment configurer l’externaliseur, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/developing/platform/externalizer.html)..

* **Organisez vos modèles d’email pour éviter toute mauvaise utilisation.**

   Le fait de conserver les modèles organisés permet de s’assurer que les modèles adéquats se trouvent dans les dossiers adéquats. Vous êtes ainsi certain de ne pas choisir des modèles incorrects par erreur. Lors de l’implémentation, il est nécessaire de créer des chemins d’accès pour enregistrer les modèles aux bons emplacements.

   Pour plus d’informations sur les modèles, consultez cette [page](https://docs.adobe.com/content/help/fr-FR/experience-manager-65/developing/platform/templates/templates.html#template-availability)..

* **Commencez rapidement avec les composants d’usine.**

   Les composants d’usine d’Adobe Experience Manager pour Adobe Campaign Standard vous permettent de commencer rapidement si vos modèles ne sont pas complexes.
Experience Manager contient sept composants d’usine que vous pouvez commencer à utiliser :

   * Titre
   * Image
   * Lien
   * Modèle d’image Scene7
   * Référence ciblée
   * Texte et image
   * Texte et personnalisation

* **Le code HTML pour les emails est différent du code HTML pour le web**

   Il est important de comprendre que vous ne pouvez pas utiliser les mêmes composants utilisés dans votre contenu web pour les modèles d’email. L’utilisation des composants d’usine garantit la compatibilité de vos composants avec les emails.

* **Dissociez le contenu des modèles et réutilisez-les sans fin.**

   Lors de la configuration de vos emails dans Campaign Standard et de la sélection d’un modèle Experience Manager, vous pouvez uniquement choisir un modèle qui n’a pas encore été lié à une autre campagne. Sinon, si vous modifiez le contenu dans Adobe Experience Manager pour une campagne et l’actualisez, vous pouvez involontairement affecter le contenu de l’autre campagne.
Pour éviter cela, une fois que vous avez fini d’utiliser votre modèle, vous pouvez le dissocier pour l’utiliser à nouveau. Il vous suffit de sélectionner le modèle et de cliquer sur **[!UICONTROL Supprimer le lien avec le contenu Adobe Experience Manager]**.

* **Utilisez Adobe Experience Manager pour créer des variantes d’emails pour Adobe Campaign Standard.**

   Cette intégration vous permet de transformer facilement un email en plusieurs versions avec la segmentation.
Pour savoir comment configurer la segmentation dans Adobe Experience Manager et comment créer des emails avec du contenu ciblé, consultez cette [page](https://docs.adobe.com/help/fr-FR/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Pour une synchronisation réussie, le nom du segment dans Experience Manager doit correspondre exactement au nom du segment dans Campaign.**