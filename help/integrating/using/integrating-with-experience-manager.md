---
title: A propos de l’intégration de Campaign-Experience Manager
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# A propos de l’intégration de Campaign-Experience Manager{#integrating-with-experience-manager}

Cette intégration entre Adobe Campaign Standard et Experience Manager vous permet d&#39;utiliser du contenu créé dans Adobe Experience Manager dans vos emails Adobe Campaign.

Vous avez ainsi la possibilité de profiter à la fois des fonctionnalités d&#39;édition de contenu d&#39;Adobe Experience Manager, et des capacités de diffusion et de gestion de données d&#39;Adobe Campaign. Notez que vous ne pouvez pas effectuer de tests A/B pour le contenu importé à partir d’Adobe Experience Manager.

Adobe Campaign Standard est compatible avec Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 et 6.5. Les sections suivantes présentent un aperçu des actions que vous pouvez exécuter. Pour plus de détails, consultez les sections dédiées au [paramétrage](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) et à l&#39;[utilisation](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) de l&#39;intégration.

>[!NOTE]
>
> Les modèles Adobe Campaign Standard ne sont plus disponibles avec Adobe Experience Manager 6.5.

## Conseils sur l’utilisation de l’intégration Campaign-Experience Manager {#tips-aem}

* **Identifier le modèle à utiliser avec l’intégration**

   Les modèles de courrier électronique pouvant être modifiés dans Adobe Experience Manager, il peut s’avérer plus facile de modifier n’importe quel modèle dans Adobe Experience Manager. Mais certains modèles ne sont pas facilement adaptés. Les modèles personnalisés spécifiques à un client ne sont pas recommandés pour cette intégration et doivent être modifiés directement dans Adobe Campaign Standard.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Assurez-vous que l’Externalizer a été configuré pendant l’implémentation.**

   La configuration de l’Externalizer lors de l’implémentation d’Experience Manager pour Adobe Campaign Standard permet de transformer un chemin de ressource en une URL. Cela vous permet de rendre vos images visibles sur la page. Si l’Externalizer n’est pas configuré correctement, vos courriels contiennent des images endommagées.

   To learn how to configure the Externalizer, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html)

* **Organisez vos modèles de courrier électronique pour éviter toute utilisation abusive.**

   Le fait de conserver les modèles organisés garantit que les modèles appropriés se trouvent dans les dossiers appropriés et de ne pas choisir les modèles incorrects par erreur. Lors de l’implémentation, vous devez créer des chemins d’accès pour enregistrer les modèles aux emplacements appropriés.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability)

* **Commencez rapidement avec les composants prêts à l&#39;emploi.**

   Les composants prêts à l’emploi d’Adobe Experience Manager pour Adobe Campaign Standard peuvent vous aider à démarrer rapidement si vos modèles ne sont pas complexes.
Il existe sept composants prêts à l’emploi dans Experience Manager que vous pouvez commencer à utiliser :
   1. Titre
   1. Image
   1. Lien
   1. Modèle d’image Scene7
   1. Référence ciblée
   1. Texte et image
   1. Texte et personnalisation

* **Le code HTML pour les courriers électroniques est différent du code HTML pour le Web**

   Il est important de comprendre que vous ne pouvez pas utiliser les mêmes composants utilisés dans votre contenu Web pour les modèles de courrier électronique. L’utilisation de composants prêts à l’emploi garantit la compatibilité de vos composants avec les courriers électroniques.

* **Dissociez le contenu des modèles et réutilisez-les encore et encore.**

   Lors de la configuration de vos courriers électroniques dans Campaign Standard et de la sélection d’un modèle Experience Manager, vous pouvez uniquement en choisir un qui n’a pas encore été lié à une autre campagne. Dans le cas contraire, si vous modifiez le contenu d’Adobe Experience Manager pour une campagne et l’actualisez, vous pouvez involontairement affecter le contenu de l’autre campagne.
Pour éviter cela, une fois que vous avez fini d’utiliser votre modèle, vous pouvez le dissocier pour l’utiliser à nouveau. Il vous suffit de sélectionner le modèle et de cliquer sur **[!UICONTROL Supprimer le lien avec le contenu]**d’Adobe Experience Manager.

* **Utilisez Adobe Experience Manager pour créer des variantes de courriers électroniques pour Adobe Campaign Standard.**

   Cette intégration vous permet de transformer facilement un courrier électronique en plusieurs versions avec la segmentation.
Pour savoir comment configurer la segmentation dans Adobe Experience Manager et comment créer des courriers électroniques avec du contenu ciblé, consultez cette [page](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Pour une synchronisation réussie, le nom du segment dans Experience Manager doit correspondre exactement au nom du segment dans Campaign.**