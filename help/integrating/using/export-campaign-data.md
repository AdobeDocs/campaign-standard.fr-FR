---
solution: Campaign Standard
product: campaign
title: Exporter des données de Campaign vers Adobe Experience Platform
description: Découvrez comment exporter des données de Campaign Standard vers Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Sources et destinations
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
translation-type: ht
source-git-commit: 27cbb2f8a202b3361122fdadfcfe8d0820aa3cb3
workflow-type: ht
source-wordcount: '528'
ht-degree: 100%

---

# Exporter des données de Campaign vers Adobe Experience Platform {#sources}

Pour exporter des données de Campaign Standard vers Adobe Real-time Customer Data Platform (RTCDP), vous devez d&#39;abord créer un workflow dans Campaign Standard pour exporter vers votre emplacement d&#39;enregistrement S3 ou Azure Blob les données que vous souhaitez partager.

Une fois le workflow configuré et les données envoyées à votre emplacement d&#39;enregistrement, vous devez connecter votre emplacement d&#39;enregistrement S3 ou Azure Blob en tant que **Source** dans la Adobe Experience Platform.

>[!NOTE]

Veuillez noter que nous vous recommandons d&#39;exporter uniquement les données générées par Campaign (par exemple, envois, ouvertures, clics, etc.) vers Adobe Experience Platform. Les données ingérées à partir d’une source tierce (tel que votre CRM) doivent être importées directement dans Adobe Experience Platform.

## Création d’un workflow d’exportation dans Campaign Standard

Pour exporter des données de Campaign Standard vers votre emplacement d&#39;enregistrement S3 ou Azure Blob, vous devez créer un workflow pour cibler les données à exporter et les envoyer vers votre emplacement d&#39;enregistrement.

Pour ce faire, ajoutez et configurez les éléments suivants :

* Activité **[!UICONTROL Extraction de fichier]** pour extraire les données ciblées dans un fichier CSV. Pour plus d’informations sur la configuration de cette activité, consultez [cette section](../../automating/using/extract-file.md).

   ![](assets/rtcdp-extract-file.png)

* Activité **[!UICONTROL Transfert de fichier]** pour transférer le fichier CSV vers votre emplacement d’enregistrement. Pour plus d’informations sur la configuration de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

   ![](assets/rtcdp-transfer-file.png)

Par exemple, le workflow ci-dessous extrait régulièrement les logs dans un fichier CSV, puis transfère le fichier vers un emplacement d’enregistrement.

![](assets/aep-export.png)

Des exemples de workflows de gestion des données sont disponibles dans la section [cas d&#39;utilisation des workflows](../../automating/using/about-workflow-use-cases.md#management).

Rubriques connexes :

* [Activités de Data Management](../../automating/using/about-data-management-activities.md)
* [A propos de l’import et de l’export de données](../../automating/using/about-data-import-and-export.md)


## Connecter votre emplacement d&#39;enregistrement en tant que source

Les étapes principales pour connecter votre emplacement d&#39;enregistrement S3 ou Azure Blob en tant que **Source** dans la Adobe Experience Platform sont énumérées ci-dessous. Des informations détaillées sur chacune de ces étapes sont disponibles dans la [documentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html).

1. Dans le menu **[!UICONTROL Sources]** de Adobe Experience Platform, créez une connexion vers votre emplacement d&#39;enregistrement :

   * [Création d’une connexion source Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Connecteur de Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >L&#39;emplacement de l&#39;enregistrement peut être Amazon S3, SFTP avec mot de passe, SFTP avec clé SSH ou des connexions Azure Blob. La méthode préférée pour envoyer des données vers Adobe Campaign est via Amazon S3 ou Azure Blob :

   ![](assets/rtcdp-connector.png)

1. Configurez un flux de données pour une connexion par lots à espace de stockage. Un flux de données est une tâche planifiée qui récupère et ingère des données de l’emplacement d’enregistrement vers un jeu de données Adobe Experience Platform. Cette procédure vous permet de configurer l’assimilation des données depuis votre emplacement d&#39;enregistrement, y compris la sélection des données et le mappage des champs CSV vers un schéma XDM.

   Des informations détaillées sont disponibles dans [cette page](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html).

   ![](assets/rtcdp-map-xdm.png)

1. Une fois la source configurée, Adobe Experience Platform importe le fichier à partir de l&#39;emplacement d&#39;enregistrement que vous avez fourni.

   Cette opération peut être planifiée en fonction de vos besoins. Il est recommandé d’effectuer l’exportation jusqu’à 6 fois par jour, selon la charge déjà présente sur l’instance.
