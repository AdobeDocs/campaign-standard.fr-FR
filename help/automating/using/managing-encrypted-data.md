---
title: Gérer des données cryptées
description: Découvrez comment gérer les données chiffrées.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 80%

---


# Gérer des données cryptées {#managing-encrypted-data}

Dans certains cas, les données que vous souhaitez importer peuvent être cryptées, par exemple si elles contiennent des données d’identification personnelle.

Pour pouvoir importer ou exporter des fichiers cryptés, vous devez d’abord contacter l’Assistance clientèle d’Adobe pour obtenir votre instance avec les commandes de cryptage/décryptage nécessaires.

Pour ce faire, envoyez une requête indiquant :

* Le **libellé** qui s’affichera dans l’interface de Campaign pour utiliser la commande. Par exemple, « Crypter le fichier ».
* La **commande** à installer sur votre instance.
Par exemple, pour décrypter un fichier à l’aide de PGP, la commande sera :

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Once the request is processed, the encryption / decryption commands will be available in the **[!UICONTROL Pre-processing stage]** field from the **[!UICONTROL Load file]** and **[!UICONTROL Extract file]** activities. Vous pouvez les utiliser pour décrypter ou crypter les fichiers à importer ou exporter.

![](assets/preprocessing-encryption.png)

**Rubriques connexes :**

* [Chargement de fichier](../../automating/using/load-file.md)
* [Extraction de fichier](../../automating/using/extract-file.md)
