---
title: À propos de l'import et de l'export de données
description: Découvrez les différentes manières d'importer et d'exporter des données avec Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
TQID: 'https://experienceleague.adobe.com/WP1mlY9lQQu5qWqIx5L89VE6MxnOhxoYewTWAYwfFTI'
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
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 100%
---
# À propos de l&#39;import et de l&#39;export de données{#about-data-import-and-export}

En fonction des besoins de votre entreprise, plusieurs méthodes permettent d&#39;importer et d&#39;exporter des données dans Adobe Campaign :

* **Packages** : les packages sont des fichiers XML qui vous permettent d&#39;exporter et d&#39;importer des configurations et des jeux de données d&#39;une instance Adobe Campaign vers une autre. Les mises à jour système sont également effectuées par le biais d&#39;imports de package.
* **Listes** : tous les écrans de type Liste peuvent être configurés et les données affichées peuvent être exportées dans un fichier distinct.
* **Workflows** : importez des données depuis des fichiers et utilisez-les pour mettre à jour la base de données ou envoyer des emails. Vous pouvez également sélectionner les données à exporter dans des fichiers. Les workflows offrent le meilleur moyen d&#39;automatiser des mises à jour régulières comme des imports de profils.

  * L’activité **[!UICONTROL Chargement de fichier]** permet d’importer les données d’un fichier sous une forme structurée afin de les utiliser dans Adobe Campaign. Les données importées le sont temporairement et nécessitent l&#39;utilisation d&#39;une autre activité pour les intégrer définitivement dans la base de données Adobe Campaign. Pour plus d’informations sur l’utilisation de cette activité, consultez [cette section](../../automating/using/load-file.md).
  * L’activité **[!UICONTROL Transfert de fichier]** permet de recevoir ou d’envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign. Vous pouvez utiliser cette activité avant un **[!UICONTROL Chargement de fichier]** si vous devez récupérer le fichier à partir d’une source externe. Pour plus d’informations sur l’utilisation de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

Lors de la conception des imports, il est recommandé d&#39;utiliser des modèles de workflow que vous pouvez adapter à vos besoins. Pour plus d&#39;informations sur la configuration d&#39;un modèle de workflow pour l&#39;import de données, reportez-vous à [ce cas pratique](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign propose également un moyen simplifié d&#39;effectuer des imports réguliers qui consiste à concevoir des **modèles d&#39;import**. Les modèles d&#39;import sont des modèles de workflow spécialisés qui sont accessibles dans un écran dédié. Une fois l&#39;import conçu, l&#39;utilisateur qui l&#39;effectue doit uniquement charger le fichier à importer dans une vue simplifiée.

**Rubriques connexes** :

* [Importer des données avec des modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md)
* [Définir un modèle d&#39;import](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gestion des packages](../../automating/using/managing-packages.md)
