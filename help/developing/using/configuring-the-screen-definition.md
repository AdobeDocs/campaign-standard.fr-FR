---
solution: Campaign Standard
product: campaign
title: Configuration de la définition d'écran
description: Découvrez comment définir de nouveaux écrans Adobe Campaign à partir de la structure des données des ressources.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '681'
ht-degree: 100%

---


# Configuration de la définition d&#39;écran{#configuring-the-screen-definition}

Lors de la création d&#39;une ressource ou de l&#39;ajout de nouveaux champs à une ressource existante, vous pouvez définir la façon dont ils doivent apparaître dans l&#39;interface.

Cette étape n&#39;est pas obligatoire, car vous pourrez toujours renseigner votre ressource et accéder à ses données via les workflows, les audiences et l&#39;API REST.

Dans l&#39;onglet **[!UICONTROL Définition des écrans]**, vous pouvez :

* Ajouter l&#39;accès à la ressource personnalisée dans le volet de navigation
* Personnaliser la manière dont sera présentée la liste des éléments constituant la ressource
* Définir l&#39;affichage du détail de chaque élément de la ressource

## Permettre l&#39;accès depuis le menu de navigation   {#enabling-access-from-the-navigation-menu}

Si vous souhaitez que votre ressource dispose d&#39;un écran dédié, vous pouvez la rendre accessible depuis le menu de navigation.

1. Depuis l&#39;onglet **[!UICONTROL Définition des écrans]** de la ressource, développez la section **[!UICONTROL Navigation]**.
1. Cochez la case **[!UICONTROL Ajouter une entrée dans la section &#39;Données client&#39;]** si vous souhaitez permettre l&#39;accès à cette ressource depuis le volet de navigation.

   ![](assets/schema_extension_19.png)

La ressource apparaîtra en tant que sous-entrée de la section **[!UICONTROL Données client]**.

## Définir la configuration de liste par défaut {#defining-the-default-list-configuration}

La section **[!UICONTROL Configuration de liste]** de la définition des écrans vous permet de définir les colonnes et informations qui s&#39;afficheront par défaut dans l&#39;aperçu d&#39;une ressource.

1. Cochez la case **[!UICONTROL Personnaliser la configuration de la liste]** pour définir l&#39;affichage des colonnes de la ressource.
1. Utilisez le bouton **[!UICONTROL Créer un élément]** pour sélectionner un champ parmi ceux que vous avez créés.
1. Le champ ajouté s&#39;affiche dans la liste. Vous pouvez modifier son libellé et sa largeur.

   ![](assets/schema_extension_20.png)

1. Dans la section **[!UICONTROL Recherche simple]**, cochez la case **[!UICONTROL Définir les champs pris en compte dans la recherche]** pour spécifier les champs qui seront inclus dans la recherche.

   >[!IMPORTANT]
   >
   >Cette configuration remplace les champs utilisés dans la recherche par défaut.

1. Dans la section **[!UICONTROL Filtrage avancé]**, cochez la case **[!UICONTROL Ajouter des champs de recherche]** pour ajouter des champs supplémentaires en plus du champ de recherche simple. Par exemple, si vous sélectionnez le champ &quot;date&quot; parmi les champs que vous avez créés, l&#39;utilisateur pourra effectuer une recherche ne portant que sur la date.
1. Vous pouvez modifier l&#39;ordre des champs pour les deux types de recherche.
1. Dans le cas d&#39;une recherche avancée, il est possible d&#39;ajouter des champs de type liens vers une ressource liée. Ces filtres apparaissent dans le menu **[!UICONTROL Recherche]** de l&#39;écran généré.

L&#39;écran de présentation de la ressource est maintenant défini.

## Définir la configuration de l&#39;écran de détail   {#defining-the-detail-screen-configuration}

La section **[!UICONTROL Configuration de l&#39;écran de détail]** de la définition des écrans vous permet de définir les colonnes et les informations qui seront affichées dans l&#39;écran de détail de chaque élément de la ressource.

1. Développez la section **[!UICONTROL Configuration de l&#39;écran de détail]** et cochez la case **[!UICONTROL Définir un écran de détail]** pour configurer l&#39;écran correspondant à chaque élément de la ressource. Si vous ne cochez pas cette case, le détail des éléments de cette ressource ne sera pas accessible.
1. Vous pouvez ajouter en un seul clic tous les champs de votre ressource personnalisée. Pour cela, cliquez sur l&#39;icône ![](assets/addallfieldsicon.png) ou utilisez le bouton **[!UICONTROL Ajouter un élément]**.
1. Sélectionnez un élément parmi ceux créés pour cette ressource et indiquez un type de champ :

   * **[!UICONTROL Champ de saisie]** : il s&#39;agira d&#39;un champ éditable.
   * **[!UICONTROL Valeur]** : il s&#39;agira d&#39;un champ non modifiable.
   * **[!UICONTROL Liste]** : il s&#39;agira d&#39;un tableau.
   * **[!UICONTROL Séparateur]** : classe vos éléments dans des catégories.

   ![](assets/schema_extension_23.png)

1. L&#39;élément ajouté s&#39;affiche dans la liste. Vous pouvez modifier son libellé.

   ![](assets/schema_extension_22.png)

1. Ajoutez autant de **[!UICONTROL Séparateurs]** que nécessaire pour classer vos éléments dans différentes catégories.

   Vous pouvez ainsi afficher un séparateur pour que votre fenêtre soit mieux organisée.

   ![](assets/schema_extension_25.png)

L&#39;écran de détail de la ressource est maintenant défini.

## Section Actions sur les données   {#actions-on-data-section}

Ces paramètres permettent d&#39;afficher une barre de contrôle dans l&#39;écran de la ressource personnalisée. Trois options sont disponibles :

![](assets/schema_extension_actions.png)

* **[!UICONTROL Autoriser la création]** : cette option permet d&#39;activer la création d&#39;éléments de la ressource. L&#39;utilisateur peut donc ajouter des enregistrements supplémentaires.

   >[!NOTE]
   >
   >Vous devez activer l&#39;écran de détail associé à la ressource pour rendre cette option accessible.

* **[!UICONTROL Autoriser la duplication]** : cette option permet d&#39;activer la duplication d&#39;enregistrements liés à la ressource personnalisée.
* **[!UICONTROL Autoriser la suppression]** : cette option permet d&#39;activer la suppression d&#39;enregistrements liés à la ressource personnalisée.
