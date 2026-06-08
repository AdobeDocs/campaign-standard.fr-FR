---
title: À propos de l’intégration Campaign-Experience Manager
description: Avec l'intégration d'Adobe Experience Manager, vous pouvez créer du contenu directement dans AEM et l'utiliser ultérieurement dans Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
TQID: https://experienceleague.adobe.com/OuQgaZgJVeL04fw3rvn5nydbp2fOSdQOVpiFhrUcEl4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: a658c786-869b-4194-a780-2594d663addaid: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: df0d6518-6f49-46e2-b46e-3bcc513f553f
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 586
ht-degree: 100%

---

# À propos de l’intégration Campaign-Experience Manager{#integrating-with-experience-manager}

Cette intégration entre Adobe Campaign Standard et Experience Manager vous permet d&#39;utiliser du contenu créé dans Adobe Experience Manager dans vos emails Adobe Campaign.

Vous avez ainsi la possibilité de profiter à la fois des fonctionnalités d&#39;édition de contenu d&#39;Adobe Experience Manager, et des capacités de diffusion et de gestion de données d&#39;Adobe Campaign. Notez que vous ne pouvez pas effectuer de test A/B sur des contenus importés depuis Adobe Experience Manager.

Adobe Campaign Standard est compatible avec Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 et 6.5. Les sections suivantes présentent une vue d’ensemble des actions que vous pouvez exécuter. Pour plus de détails, consultez les sections dédiées au [paramétrage](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=fr) et à l’[utilisation](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html?lang=fr) de l’intégration.

>[!NOTE]
>
> Les modèles Adobe Campaign Standard ne sont plus disponibles avec Adobe Experience Manager 6.5.

## Conseils sur l’utilisation de l’intégration Campaign-Experience Manager {#tips-aem}

* **Identifier le modèle à utiliser avec l’intégration**

  Les modèles d’email pouvant être édités dans Adobe Experience Manager, il peut sembler plus facile d’éditer n’importe quel modèle dans cette solution. Mais certains modèles ne sont pas adaptés. Les modèles personnalisés spécifiques à un client ne sont pas recommandés pour cette intégration et doivent être édités directement dans Adobe Campaign Standard.

  Pour plus d’informations sur les modèles, consultez cette [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=fr).

* **Vérifiez que l’externaliseur a été configuré pendant l’implémentation.**

  La configuration de l’externaliseur lors de l’implémentation d’Experience Manager pour Adobe Campaign Standard permet de transformer un chemin de ressource en URL. Vous pouvez ainsi rendre vos images visibles sur la page. Si l’externaliseur n’est pas configuré correctement, vos emails contiendront des images endommagées.

  Pour découvrir comment configurer l’externaliseur, consultez cette [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html?lang=fr).

* **Organisez vos modèles d’email pour éviter toute mauvaise utilisation.**

  Le fait de conserver les modèles organisés permet de s’assurer que les modèles adéquats se trouvent dans les dossiers adéquats. Vous êtes ainsi certain de ne pas choisir des modèles incorrects par erreur. Lors de l’implémentation, il est nécessaire de créer des chemins d’accès pour enregistrer les modèles aux bons emplacements.

  Pour plus d’informations sur les modèles, consultez cette [page](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html?lang=fr#template-availability).

* **Commencez rapidement avec les composants d’usine.**

  Les composants d’usine d’Adobe Experience Manager pour Adobe Campaign Standard vous permettent de commencer rapidement si vos modèles ne sont pas complexes.
Il y a sept composants d’usine dans Experience Manager que vous pouvez commencer à utiliser :

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

  Lors de la configuration de vos e-mails dans Campaign Standard et de la sélection d’un modèle Experience Manager, vous ne pouvez en choisir qu’un qui n’a pas déjà été lié à une autre campagne. Dans le cas contraire, si vous modifiez le contenu dans Adobe Experience Manager pour une campagne et que vous l’actualisez, vous pouvez affecter involontairement le contenu de l’autre campagne.
Pour éviter cela, une fois que vous avez fini d’utiliser votre modèle, vous pouvez le dissocier pour le réutiliser. Il vous suffit de sélectionner le modèle et de cliquer sur **[!UICONTROL Supprimer le lien avec le contenu Adobe Experience Manager]**.

* **Utilisez Adobe Experience Manager pour créer des variantes d’e-mails pour Adobe Campaign Standard.**

  Cette intégration vous permet de créer facilement plusieurs versions d’un e-mail avec la segmentation.
Pour savoir comment configurer la segmentation dans Adobe Experience Manager et comment créer des e-mails avec du contenu ciblé, consultez cette [page](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html?lang=fr#setting-up-segmentation-in-aem).

* **Pour une synchronisation réussie, le nom du segment dans Experience Manager doit correspondre exactement au nom du segment dans Campaign.**
