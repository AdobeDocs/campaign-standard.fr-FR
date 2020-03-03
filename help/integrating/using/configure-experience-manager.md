---
title: Configuration de l’intégration Campaign-Experience Manager
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
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Configuration de l’intégration Campaign-Experience Manager {#configuration-aem}

Cette intégration entre Adobe Campaign Standard et Experience Manager vous permet d&#39;utiliser du contenu créé dans Adobe Experience Manager dans vos emails Adobe Campaign.

Avec ce cas d’utilisation, vous apprendrez à créer et à gérer le contenu des courriers électroniques dans Adobe Experience Manager, puis à les utiliser pour vos campagnes marketing en les important dans vos courriers électroniques dans Adobe Campaign Standard.

## Prérequis {#prerequisites}

Vous devez au préalable posséder les éléments suivants :

* Une instance Adobe Experience Manager de création (également appelée **authoring**).
* Une instance Adobe Experience Manager de publication (également appelée **publishing**).
* Une instance Adobe Campaign

## Configuration dans Adobe Campaign Standard {#config-acs}

Afin de pouvoir utiliser conjointement ces deux solutions, vous devez les paramétrer pour les connecter l&#39;une à l&#39;autre.
Les étapes de configuration d&#39;Adobe Campaign sont les suivants :

1. Vous devez d’abord configurer le compte **[!UICONTROL Adobe Experience Manager instance]** externe sous **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configurez le compte externe de type Adobe Experience Manager avec votre **[!UICONTROL Server]** URL **[!UICONTROL Account]** et **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Vérifiez que l’ **[!UICONTROL AEMResourceTypeFilter]** option a été correctement configurée. Accédez au **[!UICONTROL Options]** menu sous **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

1. Dans le **[!UICONTROL Value (text)]** champ, vérifiez que la syntaxe suivante est correcte :

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Ensuite, dans le menu avancé sous **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, dupliquez l’un des modèles existants pour créer un modèle de courrier électronique spécifique à Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Cliquez sur l’ **[!UICONTROL Edit properties]** icône .

   ![](assets/aem_4.png)

1. Dans la **[!UICONTROL Content]** liste déroulante, sélectionnez **[!UICONTROL Adobe Experience Manager]** dans le **[!UICONTROL Content source]** champ, puis votre compte externe créé précédemment dans le **[!UICONTROL Adobe Experience Manager account]**.

Vous devez maintenant configurer l’intégration dans Adobe Experience Manager.

## Configuration dans Adobe Experience Manager {#config-aem}

Pour configurer Adobe Experience Manager avec Adobe Campaign Standard, procédez comme suit :

1. Vous devez d’abord configurer la réplication entre les instances de création et de publication d’Adobe Experience Manager. Consultez cette [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Then, connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**. Consultez cette [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Vous devez maintenant configurer l’externaliseur dans Adobe Experience Manager sur votre instance d’auteur. Consultez cette [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

