---
title: Mise à jour des données à l’aide d’un téléchargement automatique de fichier
description: L'exemple suivant montre le résultat d'une activité de chargement d'un fichier automatiquement téléchargé via une activité de transfert, suivie d'une mise à jour de données.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
TQID: 'https://experienceleague.adobe.com/q-u5dH48a4wea1yStaF-QekcD9VaS2NjDhWnSQc6QGU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 100%
---
# Mise à jour des données à l&#39;aide d&#39;un téléchargement automatique de fichier {#updating-data-automatic-file-download}

L&#39;activité de chargement de fichier sert essentiellement à structurer des données issues d&#39;une activité de transfert de fichier en vue de les intégrer à des données existantes.

L&#39;exemple suivant montre le résultat d&#39;une activité de chargement d&#39;un fichier automatiquement téléchargé via une activité de transfert, suivie d&#39;une mise à jour de données. Le but de ce workflow est d&#39;enrichir la base Adobe Campaign avec de nouveaux profils ou de mettre à jour les profils existants à partir des données récupérées dans le fichier importé.

![](assets/load_file_workflow_ex1.png)

Pour créer le workflow, procédez comme suit :

1. Placez une activité [Transfert de fichier](../../automating/using/transfer-file.md) dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Configurez l’activité de manière à ce qu’elle récupère le fichier de votre choix. Dans l’onglet **[!UICONTROL Protocole]**, choisissez le protocole **SFTP**.
1. Sélectionnez l’option **Utiliser des paramètres de connexion définis dans un compte externe**.
1. Renseignez le nom du compte externe.
1. Renseignez le **chemin des fichiers sur le serveur distant**.

   ![](assets/wkf_file_transfer_07.png)

1. Validez votre activité.
1. Placez une activité [Chargement de fichier](../../automating/using/load-file.md) et connectez-la à la suite de l&#39;activité **[!UICONTROL Transfert de fichier]**.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Dans la section **[!UICONTROL Fichier à charger]** de l&#39;onglet **[!UICONTROL Exécution]**, cochez la case **[!UICONTROL Utiliser le fichier provenant de la transition entrante]**.

   ![](assets/wkf_file_loading8.png)

1. Paramétrez l&#39;activité comme indiqué ci-dessus.
1. Placez une activité [Mise à jour de données](../../automating/using/update-data.md), connectez-la à la suite de l&#39;activité **[!UICONTROL Chargement de fichier]** et paramétrez-la.

Une fois le workflow lancé, le fichier voulu est téléchargé, les données sont extraites, puis elles sont utilisées pour enrichir la base Adobe Campaign.
