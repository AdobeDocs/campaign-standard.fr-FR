---
title: Ingérer des audiences Adobe Experience Platform dans Campaign
description: Découvrez comment intégrer des audiences Adobe Experience Platform dans Campaign Standard.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: b70f632b-2cfd-43d0-9266-284281100d70id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 100%

---

# Ingérer des audiences Adobe Experience Platform dans Campaign {#destinations}

Pour ingérer des audiences Adobe Experience Platform dans Campaign et les utiliser dans vos workflows, vous devez d’abord connecter Adobe Campaign en tant que **destination** Adobe Experience Platform et le configurer avec le segment à exporter.

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
