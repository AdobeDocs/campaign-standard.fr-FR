---
title: Export de profils dans un fichier externe
description: Ce cas pratique montre comment exporter une liste de profils sous la forme d’un fichier externe pour en utiliser les données en dehors d’Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
TQID: https://experienceleague.adobe.com/wVo-oDNJNFmaNcb7p6fACNIfrPG-2Y-VbXxXG0P8XTQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 100%

---

# Export de profils dans un fichier externe {#exporting-profiles-external-file}

L&#39;exemple suivant illustre le paramétrage d&#39;une activité de type **[!UICONTROL Extraction de fichier]** suivant une activité de type **[!UICONTROL Requête]**.

Le but de ce workflow est d&#39;exporter une liste de profils sous la forme d&#39;un fichier externe afin d&#39;en utiliser les données hors d&#39;Adobe Campaign.

1. Placez une activité de type [Extraction de fichier](../../automating/using/extract-file.md) à la suite d&#39;une activité de type [Requête](../../automating/using/query.md).

   Dans cet exemple, la requête porte sur tous les profils dont l&#39;âge se situe entre 18 et 30 ans inclus.

1. Ouvrez l’activité **[!UICONTROL Extraction de fichier]** pour l’éditer.
1. Nommez le fichier de sortie.
1. Ajoutez les colonnes de sortie.

   Dans cet exemple, l&#39;email, l&#39;âge, la date de naissance, le nom et le prénom des profils ciblés sont ajoutés comme colonnes de sortie.

   ![](assets/wkf_data_export6.png)

1. Cliquez sur l&#39;onglet **[!UICONTROL Structure du fichier]** pour définir :

   * Format de sortie CSV

     ![](assets/wkf_data_export7.png)

   * Format de date

     ![](assets/wkf_data_export9.png)

1. Validez votre activité.
1. Placez une activité de type [Transfert de fichier](../../automating/using/transfer-file.md) à la suite de l&#39;activité **[!UICONTROL Extraction de fichier]** pour récupérer le fichier extrait sur un compte externe.
1. Ouvrez l’activité et choisissez l’action **[!UICONTROL Chargement de fichier]**.

   ![](assets/wkf_data_export11.png)

1. Sélectionnez le compte externe et spécifiez le chemin du dossier sur le serveur.

   ![](assets/wkf_data_export12.png)

1. Validez votre activité et sauvegardez votre workflow.
1. Démarrez le workflow.

   Lorsque le workflow s&#39;est correctement exécuté, le fichier extrait est disponible sur le compte externe.
