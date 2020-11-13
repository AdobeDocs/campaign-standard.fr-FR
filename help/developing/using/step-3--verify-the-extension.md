---
title: '"Etape 3 : Vérifier l''extension"'
description: Apprenez à accéder au champ étendu avec l'API REST.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '59'
ht-degree: 100%

---


# Etape 3 : Vérifier l&#39;extension{#step-verify-the-extension}

1. Effectuez une opération GET sur les métadonnées de l&#39;API Profiles &amp; Services Extension afin de vérifier la disponibilité du champ ajouté à la ressource personnalisée Profiles.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Elle renvoie :

   ![](assets/extendpandsapiview.png)

   Le champ est désormais disponible pour d&#39;autres développements et intégrations éventuels.

