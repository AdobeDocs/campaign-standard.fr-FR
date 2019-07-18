---
title: Création ou extension de la ressource
seo-title: Création ou extension de la ressource
description: Création ou extension de la ressource
seo-description: Découvrez comment définir entièrement une ressource.
page-status-flag: jamais activé
uuid: 7 c 26 b 63 d -9587-472 b -804 f-cde 5 c 45 dfb 3 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: développement
content-type: référence
topic-tags: ajout-extension-a-resource
discoiquuid: 8 dc 45 c 37-6908-407 e -8 e 41-4 a 4188 cba 2 b 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Création ou extension de la ressource{#creating-or-extending-the-resource}

Les administrateurs peuvent créer une ressource ou une extension d'une ressource existante si vous avez besoin d'utiliser des données qui ne font pas partie du modèle de données d'usine.

Seules les ressources d'usine suivantes peuvent être étendues :

* **[!UICONTROL Campagne (campaign)]**
* **[!UICONTROL Diffusions (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profils (profile)]**
* **[!UICONTROL Programme (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Abonnements à une application (appSubscriptionRcp)]**
* **[!UICONTROL Profils de test (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Pour créer ou étendre une ressource :

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click the **[!UICONTROL Create]** button.
1. Sélectionnez l'action que vous souhaitez réaliser :

   * **[!UICONTROL Créer une nouvelle ressource]** : renseignez les champs **[!UICONTROL Libellé]** et **Identifiant[!UICONTROL .]** Le champ **[!UICONTROL Identifiant]est obligatoire.** Si vous laissez le champ Libellé vide, il sera automatiquement renseigné à partir de l'identifiant.

      ![](assets/schema_extension_2.png)

   * **[!UICONTROL Etendre une ressource existante]** : sélectionnez la ressource que vous souhaitez étendre.

      ![](assets/schema_extension_10.png)

1. Cliquez sur **[!UICONTROL Créer]** pour créer la ressource. Celle-ci prend alors le statut **[!UICONTROL En création]s'il s'agit d'une nouvelle ressource ou** En édition] s'il s'agit d'une extension.**[!UICONTROL **

La nouvelle ressource est créée et peut être maintenant configurée. Pour plus d'informations sur la configuration d'une ressource, consultez la section [Configuration de la structure de données de la ressource](../../developing/using/configuring-the-resource-s-data-structure.md).
