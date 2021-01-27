---
solution: Campaign Standard
product: campaign
title: A propos de l'import et de l'export de données
description: Découvrez les différentes manières d'importer et d'exporter des données avec Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 100%

---


# A propos de l&#39;import et de l&#39;export de données{#about-data-import-and-export}

En fonction des besoins de votre entreprise, plusieurs méthodes permettent d&#39;importer et d&#39;exporter des données dans Adobe Campaign :

* **Packages** : les packages sont des fichiers XML qui vous permettent d&#39;exporter et d&#39;importer des configurations et des jeux de données d&#39;une instance Adobe Campaign vers une autre. Les mises à jour système sont également effectuées par le biais d&#39;imports de package.
* **Listes** : tous les écrans de type Liste peuvent être configurés et les données affichées peuvent être exportées dans un fichier distinct.
* **Workflows** : importez des données depuis des fichiers et utilisez-les pour mettre à jour la base de données ou envoyer des emails. Vous pouvez également sélectionner les données à exporter dans des fichiers. Les workflows offrent le meilleur moyen d&#39;automatiser des mises à jour régulières comme des imports de profils.

   * L’activité **[!UICONTROL Chargement de fichier]** permet d’importer les données d’un fichier sous une forme structurée afin de les utiliser dans Adobe Campaign. Les données importées le sont temporairement et nécessitent l’utilisation d’une autre activité pour les intégrer définitivement dans la base de données Adobe Campaign. Pour plus d’informations sur l’utilisation de cette activité, consultez [cette section](../../automating/using/load-file.md).
   * L’activité **[!UICONTROL Transfert de fichier]** permet de recevoir ou d’envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign. Vous pouvez utiliser cette activité avant un **[!UICONTROL Chargement de fichier]** si vous devez récupérer le fichier à partir d’une source externe. Pour plus d’informations sur l’utilisation de cette activité, consultez [cette section](../../automating/using/transfer-file.md).

Lors de la conception des imports, il est recommandé d&#39;utiliser des modèles de workflow que vous pouvez adapter à vos besoins. Pour plus d&#39;informations sur la configuration d&#39;un modèle de workflow pour l&#39;import de données, reportez-vous à [ce cas pratique](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign propose également un moyen simplifié d&#39;effectuer des imports réguliers qui consiste à concevoir des **modèles d&#39;import**. Les modèles d&#39;import sont des modèles de workflow spécialisés qui sont accessibles dans un écran dédié. Une fois l&#39;import conçu, l&#39;utilisateur qui l&#39;effectue doit uniquement charger le fichier à importer dans une vue simplifiée.

**Rubriques connexes** :

* [Importer des données avec des modèles d’import](../../automating/using/importing-data-with-import-templates.md)
* [Définir un modèle d’import](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gestion des packages](../../automating/using/managing-packages.md)
