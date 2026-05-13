---
title: Exporter des données de Campaign vers Adobe Experience Platform
description: Découvrez comment exporter des données de Campaign Standard vers Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
TQID: https://experienceleague.adobe.com/wevJB72xRacTndQ1-VOyKHOtRak0UKJT2V-pzUd6d-Q
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: b70f632b-2cfd-43d0-9266-284281100d70id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 542
ht-degree: 100%

---

# Exporter des données de Campaign vers Adobe Experience Platform {#sources}

Pour exporter des données de Campaign Standard vers Adobe Real-time Customer Data Platform (RTCDP), vous devez d’abord créer un workflow dans Campaign Standard pour exporter vers votre service de stockage Amazon (S3) ou votre emplacement de stockage Azure Blob les données que vous souhaitez partager.

Une fois le workflow configuré et les données envoyées à votre emplacement de stockage, vous devez connecter votre emplacement de stockage S3 ou Azure Blob en tant que **Source** dans Adobe Experience Platform.

>[!NOTE]
>
>Veuillez noter que nous vous recommandons d’exporter uniquement les données générées par Campaign (par exemple, envois, ouvertures, clics, etc.) vers Adobe Experience Platform. Les données ingérées à partir d’une source tierce (telle que votre CRM) doivent être importées directement dans Adobe Experience Platform.

## Création d’un workflow d’exportation dans Campaign Standard

Pour exporter des données de Campaign Standard vers votre emplacement d&#39;enregistrement S3 ou Azure Blob, vous devez créer un workflow pour cibler les données à exporter et les envoyer vers votre emplacement d&#39;enregistrement.

Pour ce faire, ajoutez et configurez les éléments suivants :

* Activité **[!UICONTROL Extraction de fichier]** pour extraire les données ciblées dans un fichier CSV. Pour plus d’informations sur la configuration de cette activité, consultez [cette section](../../automating/using/extract-file.md).

  ![](assets/rtcdp-extract-file.png)

* Activité **[!UICONTROL Transfert de fichier]** pour transférer le fichier CSV vers votre emplacement de stockage. Pour plus d’informations sur la configuration de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

  ![](assets/rtcdp-transfer-file.png)

Par exemple, le workflow ci-dessous extrait régulièrement les logs dans un fichier CSV, puis transfère ce fichier vers un emplacement de stockage.

![](assets/aep-export.png)

Des exemples de workflows de gestion des données sont disponibles dans la section [cas d&#39;utilisation des workflows](../../automating/using/about-workflow-use-cases.md#management).

Rubriques connexes :

* [Activités de Data Management](../../automating/using/about-data-management-activities.md)
* [À propos de l&#39;import et de l&#39;export de données](../../automating/using/about-data-import-and-export.md)


## Connecter votre emplacement de stockage en tant que source

Les étapes principales pour connecter votre service de stockage Amazon (S3) ou Azure Blob en tant que **Source** dans Adobe Experience Platform sont énumérées ci-dessous. Des informations détaillées sur chacune de ces étapes sont disponibles dans la [documentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=fr).

1. Dans le menu **[!UICONTROL Sources]** d’Adobe Experience Platform, créez une connexion vers votre emplacement de stockage :

   * [Créer une connexion source Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=fr)
   * [Connecteur Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=fr)

   >[!NOTE]
   >
   >L&#39;emplacement de l&#39;enregistrement peut être Amazon S3, SFTP avec mot de passe, SFTP avec clé SSH ou des connexions Azure Blob. La méthode préférée pour envoyer des données vers Adobe Campaign est via Amazon S3 ou Azure Blob :

   ![](assets/rtcdp-connector.png)

1. Configurez un flux de données pour une connexion par lots vers l’espace de stockage. Un flux de données est une tâche planifiée qui récupère et ingère des données issues de l’emplacement de stockage pour obtenir un jeu de données Adobe Experience Platform. Cette procédure permet de configurer l’ingestion des données depuis votre emplacement de stockage, y compris la sélection des données et le mapping des champs CSV avec un schéma XDM.

   Des informations détaillées sont disponibles dans [cette page](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=fr).

   ![](assets/rtcdp-map-xdm.png)

1. Une fois la source configurée, Adobe Experience Platform importe le fichier à partir de l’emplacement de stockage que vous avez indiqué.

   Cette opération peut être planifiée en fonction de vos besoins. Il est recommandé d’effectuer l’exportation jusqu’à 6 fois par jour, selon la charge déjà présente sur l’instance.
