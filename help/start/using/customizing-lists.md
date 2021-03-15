---
solution: Campaign Standard
product: campaign
title: Personnalisation des listes
description: '"Découvrez comment personnaliser l''affichage et exécuter des actions sur les écrans de type Liste dans Adobe Campaign Standard : tri, filtrage, suppression ou duplication d''éléments. Les écrans de type Liste affichent les éléments d''une ou plusieurs ressources données."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Opérations
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 99%

---


# Personnalisation des listes{#customizing-lists}

Les écrans de type **Liste** permettent d&#39;afficher les éléments d&#39;une ou de plusieurs ressources données.

Adobe Campaign propose deux types de listes :

* Une liste **homogène** qui contient un seul type de ressource. Par exemple, la liste des profils contient uniquement des profils.
* Une liste **hétérogène** qui contient plusieurs types de ressources. Par exemple : la liste des activités marketing contient des landing pages, des workflows, des emails, des SMS, etc.

Les listes sont affichées en colonnes. Chaque colonne peut être triée dans un ordre croissant ou décroissant, une à la fois.

Les éléments d&#39;une liste disposent d&#39;une case à cocher permettant de les sélectionner. En sélectionnant un ou plusieurs éléments, vous pouvez effectuer plusieurs actions, notamment éditer, dupliquer et supprimer ces éléments.

Au survol d&#39;un élément de liste, des **actions contextuelles** apparaissent. Ces actions permettent différentes interactions avec l&#39;élément survolé comme l&#39;édition, la sélection, la suppression ou l&#39;affichage des détails.

![](assets/overview_list_quickactions.png)

Vous pouvez également configurer les colonnes affichées pour une liste. Pour ajouter ou retirer des colonnes :

1. Le cas échéant, assurez-vous que l&#39;écran se trouve bien en mode **Liste**.

   ![](assets/export_list_mode_switch.png)

1. Accédez à la fenêtre de configuration de la liste à l&#39;aide du bouton ![](assets/columnsettings.png) de la barre d&#39;actions.

   ![](assets/list_configuration1.png)

1. Ajoutez les colonnes que vous souhaitez inclure dans votre liste. Pour cela, sélectionnez une colonne depuis la partie gauche de la fenêtre puis utilisez le bouton ![](assets/arrowright.png) de la barre d&#39;actions pour ajouter une colonne.

   Les colonnes sélectionnables correspondent à la ressource de la liste.

   Pour chaque colonne ajoutée, indiquez si vous souhaitez appliquer un tri par défaut :

   * **[!UICONTROL NON]** : aucun tri sur la colonne
   * **[!UICONTROL ASC]** : applique un tri ascendant (croissant) sur la colonne
   * **[!UICONTROL DESC]** : applique un tri descendant (décroissant) sur la colonne.

1. Supprimez les colonnes que vous ne souhaitez pas afficher. Pour cela, cochez les cases correspondant aux colonnes à supprimer. Utilisez ensuite le bouton ![](assets/delete.png) de la barre d&#39;actions pour valider la suppression.
1. Une fois que votre liste contient les bonnes colonnes, vous pouvez modifier l&#39;ordre dans lequel elles seront affichées dans la liste. Pour cela, cochez les cases des colonnes à déplacer. Utilisez ensuite les flèches ![](assets/arrowdown.png) et ![](assets/arrowup.png).
1. Validez la configuration de votre liste en sélectionnant **[!UICONTROL OK]**.

Votre liste est désormais affichée telle que vous l&#39;avez configurée.
