---
title: Personnalisation des listes
description: '"Découvrez comment personnaliser l''affichage et exécuter des actions sur les écrans de type Liste dans Adobe Campaign Standard : tri, filtrage, suppression ou duplication d''éléments. Les écrans de type Liste affichent les éléments d''une ou plusieurs ressources données."'
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Personnalisation des listes{#customizing-lists}

Les écrans de type **Liste** permettent d'afficher les éléments d'une ou de plusieurs ressources données.

Adobe Campaign propose deux types de listes :

* Une liste **homogène** qui contient un seul type de ressource. Par exemple, la liste des profils contient uniquement des profils.
* Une liste **hétérogène** qui contient plusieurs types de ressources. Par exemple : la liste des activités marketing contient des landing pages, des workflows, des emails, des SMS, etc.

Les listes sont affichées en colonnes. Chaque colonne peut être triée dans un ordre croissant ou décroissant, une à la fois.

Les éléments d'une liste disposent d'une case à cocher permettant de les sélectionner. En sélectionnant un ou plusieurs éléments, vous pouvez effectuer plusieurs actions, notamment éditer, dupliquer et supprimer ces éléments.

Au survol d'un élément de liste, des **actions contextuelles** apparaissent. Ces actions permettent différentes interactions avec l'élément survolé comme l'édition, la sélection, la suppression ou l'affichage des détails.

![](assets/overview_list_quickactions.png)

Vous pouvez également configurer les colonnes affichées pour une liste. Pour ajouter ou retirer des colonnes :

1. Le cas échéant, assurez-vous que l'écran se trouve bien en mode **Liste**.

   ![](assets/export_list_mode_switch.png)

1. Accédez à la fenêtre de configuration de la liste à l'aide du bouton ![](assets/columnsettings.png) de la barre d'actions.

   ![](assets/list_configuration1.png)

1. Ajoutez les colonnes que vous souhaitez inclure dans votre liste. Pour cela, sélectionnez une colonne depuis la partie gauche de la fenêtre puis utilisez le bouton ![](assets/arrowright.png) de la barre d'actions pour ajouter une colonne.

   Les colonnes sélectionnables correspondent à la ressource de la liste.

   Pour chaque colonne ajoutée, indiquez si vous souhaitez appliquer un tri par défaut :

   * **[!UICONTROL NON]** : aucun tri sur la colonne
   * **[!UICONTROL ASC]** : applique un tri ascendant (croissant) sur la colonne
   * **[!UICONTROL DESC]** : applique un tri descendant (décroissant) sur la colonne.

1. Supprimez les colonnes que vous ne souhaitez pas afficher. Pour cela, cochez les cases correspondant aux colonnes à supprimer. Utilisez ensuite le bouton ![](assets/delete.png) de la barre d'actions pour valider la suppression.
1. Une fois que votre liste contient les bonnes colonnes, vous pouvez modifier l'ordre dans lequel elles seront affichées dans la liste. Pour cela, cochez les cases des colonnes à déplacer. Utilisez ensuite les flèches ![](assets/arrowdown.png) et ![](assets/arrowup.png).
1. Validez la configuration de votre liste en sélectionnant **[!UICONTROL OK]**.

Votre liste est désormais affichée telle que vous l'avez configurée.
