---
title: Ingérer des audiences Adobe Experience Platform dans Campaign
description: Découvrez comment intégrer des audiences Adobe Experience Platform dans Campaign Standard.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# Ingérer des audiences Adobe Experience Platform dans Campaign {#destinations}

Pour importer des audiences Adobe Experience Platform dans Campaign et les utiliser dans vos workflows, vous devez d&#39;abord connecter Adobe Campaign en tant que **destination** Adobe Experience Platform et le configurer avec le segment à exporter.

Une fois la destination configurée, les données sont exportées vers votre emplacement d’enregistrement et vous devez créer un workflow dédié dans Campaign Standard pour les ingérer.

## Connecter Adobe Campaign en tant que destination

Dans Adobe Experience Platform, configurez une connexion avec Adobe Campaign en sélectionnant un emplacement d’enregistrement pour les segments exportés. Cette procédure permet également de sélectionner les segments à exporter et de spécifier des champs XDM additionnels à inclure.

Consultez à ce sujet la [documentation sur les destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=fr).

Une fois la destination configurée, Adobe Experience Platform crée un fichier .txt ou .csv délimité par des tabulations à l’emplacement de stockage indiqué. Cette opération est planifiée et exécutée une fois toutes les 24 heures.

Vous pouvez désormais configurer un workflow Campaign Standard pour ingérer le segment dans Campaign.

## Création d’un workflow d&#39;import dans Campaign Standard

Une fois que Campaign Standard a été configuré en tant que destination, vous devez créer un workflow dédié pour importer le fichier qui a été exporté par Adobe Experience Platform.

Pour ce faire, vous devez ajouter et configurer une activité **[!UICONTROL Transfert de fichier]**. Pour plus d’informations sur la configuration de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Vous pouvez ensuite créer votre workflow en fonction de vos besoins (mettre à jour la base de données à l’aide des données de segment, envoyer des diffusions cross-canal au segment, etc.)

Par exemple, le workflow ci-dessous télécharge quotidiennement le fichier depuis votre emplacement de stockage, puis met à jour la base de données Campaign à l’aide des données de segment.

![](assets/rtcdp-workflow.png)

Des exemples de workflows de gestion des données sont disponibles dans la section [cas d&#39;utilisation des workflows](../../automating/using/about-workflow-use-cases.md#management).

Rubriques connexes :

* [Activités de Data Management](../../automating/using/about-data-management-activities.md)
* [À propos de l&#39;import et de l&#39;export de données](../../automating/using/about-data-import-and-export.md)
