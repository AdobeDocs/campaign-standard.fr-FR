---
solution: Campaign Standard
product: campaign
title: Incorporer des audiences Adobe Experience Platform dans Campaign
description: Découvrez comment intégrer des audiences Adobe Experience Platform dans le Campaign Standard.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---


# Incorporer les audiences Adobe Experience Platform dans Campaign {#destinations}

Pour importer des audiences Adobe Experience Platform dans Campaign et les utiliser dans vos workflows, vous devez d&#39;abord connecter Adobe Campaign en tant qu&#39;Adobe Experience Platform **Destination** et le configurer avec le segment à exporter.

Une fois la destination configurée, les données sont exportées vers votre emplacement d’enregistrement et vous devez créer un processus dédié dans le Campaign Standard pour les assimiler.

## Connecter Adobe Campaign en tant que destination

Dans la plate-forme Adobe Experience, configurez une connexion avec Adobe Campaign en sélectionnant un emplacement d’enregistrement pour les segments exportés. Cette procédure vous permet également de sélectionner les segments à exporter et de spécifier des champs XDM supplémentaires à inclure.

Pour plus d&#39;informations à ce sujet, consultez la [documentation sur les destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

Une fois la destination configurée, Adobe Experience Platform crée un fichier .txt ou .csv délimité par des tabulations à l’emplacement de l’enregistrement que vous avez fourni. Cette opération est planifiée et exécutée une fois par 24h.

Vous pouvez désormais configurer un processus Campaign Standard pour assimiler le segment dans Campaign.

## Création d’un processus d’importation dans le Campaign Standard

Une fois que le Campaign Standard a été configuré en tant que destination, vous devez créer un processus dédié pour importer le fichier qui a été exporté par Adobe Experience Platform.

Pour ce faire, vous devez ajouter et configurer une activité **[!UICONTROL Transférer le fichier]**. Pour plus d&#39;informations sur la configuration de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Vous pouvez ensuite créer votre processus en fonction de vos besoins (mettre à jour la base de données à l’aide des données de segment, envoyer des diffusions entre canaux au segment, etc.)

Par exemple, le flux de travail ci-dessous télécharge quotidiennement le fichier depuis l’emplacement de votre enregistrement, puis met à jour la base de données Campaign avec les données de segment.

![](assets/rtcdp-workflow.png)

Des exemples de workflows de data Management sont disponibles dans la section [cas d&#39;utilisation des workflows](../../automating/using/about-workflow-use-cases.md#management).

Rubriques connexes :

* [Activités de Data Management](../../automating/using/about-data-management-activities.md)
* [A propos de l’import et de l’export de données](../../automating/using/about-data-import-and-export.md)
