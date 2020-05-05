---
title: Importer des données avec des modèles d'import
description: Découvrez comment collecter des données afin d'alimenter la base de données de Campaign.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importer des données avec des modèles d&#39;import{#importing-data-with-import-templates}

L&#39;import de données vous permet de collecter des données afin d&#39;alimenter la base de données de Campaign.

Alternativement aux [workflows](../../automating/using/get-started-workflows.md), Adobe Campaign propose une fonction d&#39;import simplifiée permettant de gérer certains types d&#39;import, préalablement définis par un administrateur.

Le principe de fonctionnement est le suivant : un **administrateur** définit et gère des modèles d&#39;import (voir [Définir des modèles d&#39;import](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** menu.

Ces utilisateurs n&#39;ont alors qu&#39;à sélectionner le type d&#39;import qu&#39;ils souhaitent réaliser et à charger le fichier contenant les données à importer. Le workflow définit par l&#39;administrateur est exécuté de manière transparente pour l&#39;utilisateur, qui peut accéder au détail du résultat de son import une fois ce dernier terminé.

>[!NOTE]
>
>La fonction d’importation de données peut être gérée par des utilisateurs avec **[!UICONTROL GENERIC IMPORT (import)]** et **[!UICONTROL WORKFLOW (workflow)]** des rôles. Pour plus d&#39;informations sur les rôles, consultez [cette section](../../administration/using/list-of-roles.md).

Les imports peuvent être filtrés en fonction du modèle à partir duquel ils ont été exécutés, de leur date d&#39;exécution ainsi que de leur statut d&#39;exécution.

1. From the imports overview, click the **[!UICONTROL Create]** button. L&#39;assistant d&#39;import s&#39;ouvre.
1. Sélectionnez le type d&#39;import que vous souhaitez réaliser. Les types d&#39;import correspondent aux modèles d&#39;import disponibles.
1. Si besoin, téléchargez le fichier d&#39;exemple associé au modèle sur votre poste afin de visualiser les types de données attendus dans le fichier à importer.
1. Téléchargez le fichier contenant les données à importer dans l&#39;assistant.
1. Lancez l&#39;import. L&#39;assistant se ferme et vous renvoie à la liste des imports réalisés avec le modèle utilisé.
1. Rafraîchissez votre page et sélectionnez l&#39;import que vous venez de réaliser afin de visualiser le détail de son exécution.

   ![](assets/simplified_import1.png)

Les détails de l&#39;exécution de l&#39;import sont à présent disponibles. Vous pouvez également télécharger sur votre poste le fichier qui a été importé ainsi que le fichier contenant le détail des rejets (données non importées).
