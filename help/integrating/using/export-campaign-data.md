---
solution: Campaign Standard
product: campaign
title: Exporter des données de Campaign vers Adobe Experience Platform
description: Découvrez comment exporter des données du Campaign Standard vers Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: bf442b12506ef71cc76aa7fffb0e4c8bb2ce70da
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 1%

---


# Exporter des données de Campaign vers Adobe Experience Platform {#sources}

Pour exporter des données de Campaign Standard vers la plateforme de données client en temps réel Adobe (RTCDP), vous devez d&#39;abord créer un processus en Campaign Standard pour exporter vers votre enregistrement de données blob S3 ou Azure les données que vous souhaitez partager.

Une fois le flux de travail configuré et les données envoyées à votre emplacement d&#39;enregistrement, vous devez connecter votre emplacement d&#39;enregistrement blob S3 ou Azure en tant que **Source** dans la plate-forme d&#39;expérience d&#39;Adobe.

>[!NOTE]

Veuillez noter que nous vous recommandons d&#39;exporter uniquement les données générées par Campaign (par exemple, envoie, ouvre, clics, etc.) à Adobe Experience Platform. Les données ingérées à partir d’une source tierce (telle que votre gestion de la relation client) doivent être importées directement dans Adobe Experience Platform.

## Création d’un processus d’exportation dans le Campaign Standard

Pour exporter des données du Campaign Standard vers votre emplacement d&#39;enregistrement Blob S3 ou Azure, vous devez créer un processus pour cible les données à exporter et les envoyer à votre emplacement enregistrement.

Pour ce faire, ajoutez et configurez les éléments suivants :

* Activité **[!UICONTROL Extraire le fichier]** pour extraire les données ciblées dans un fichier CSV. Pour plus d&#39;informations sur la configuration de cette activité, consultez [cette section](../../automating/using/extract-file.md).

   ![](assets/rtcdp-extract-file.png)

* Activité **[!UICONTROL Transférer le fichier]** pour transférer le fichier CSV vers votre emplacement d’enregistrement. Pour plus d&#39;informations sur la configuration de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

   ![](assets/rtcdp-transfer-file.png)

Par exemple, le processus ci-dessous extrait régulièrement les journaux dans un fichier CSV, puis les transfère vers un emplacement d’enregistrement.

![](assets/aep-export.png)

Des exemples de workflows de data Management sont disponibles dans la section [cas d&#39;utilisation des workflows](../../automating/using/about-workflow-use-cases.md#management).

Rubriques connexes :

* [Activités de Data Management](../../automating/using/about-data-management-activities.md)
* [A propos de l’import et de l’export de données](../../automating/using/about-data-import-and-export.md)


## Connecter votre emplacement d&#39;enregistrement en tant que source

Les étapes principales pour connecter votre emplacement d&#39;enregistrement blob S3 ou Azure en tant que **Source** dans la plate-forme d&#39;expérience d&#39;Adobe sont énumérées ci-dessous. Des informations détaillées sur chacune de ces étapes sont disponibles dans la [documentation des connecteurs source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html).

1. Dans le menu de la plate-forme Adobe Experience **[!UICONTROL Sources]**, créez une connexion à l’emplacement de votre enregistrement :

   * [Création d’une connexion source Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Connecteur de blocage Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >L&#39;emplacement de l&#39;enregistrement peut être Amazon S3, SFTP avec mot de passe, SFTP avec clé SSH ou les connexions Azure Blob. La méthode préférée pour envoyer des données à Adobe Campaign est via Amazon S3 ou Azure Blob :

   ![](assets/rtcdp-connector.png)

1. Configurez un flux de données pour une connexion par lots à un enregistrement cloud. Un flux de données est une tâche planifiée qui récupère et ingère des données de l’emplacement de l’enregistrement vers un jeu de données Adobe Experience Platform. Cette procédure vous permet de configurer l’assimilation des données depuis l’emplacement de votre enregistrement, y compris la sélection des données et le mappage des champs CSV à un schéma XDM.

   Des informations détaillées sont disponibles dans [cette page](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html).

   ![](assets/rtcdp-map-xdm.png)

1. Une fois la source configurée, Adobe Experience Platform importe le fichier à partir de l&#39;emplacement de l&#39;enregistrement que vous avez fourni.

   Cette opération peut être planifiée en fonction de vos besoins. Il est recommandé d’effectuer l’exportation jusqu’à 6 fois par jour, selon la charge déjà présente sur l’instance.
