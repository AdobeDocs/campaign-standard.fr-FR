---
title: Configuration de la définition d'écran
description: Découvrez comment définir de nouveaux écrans Adobe Campaign à partir de la structure des données des ressources.
page-status-flag: never-activated
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Configuration de la définition d&#39;écran{#configuring-the-screen-definition}

Lors de la création d&#39;une ressource ou de l&#39;ajout de nouveaux champs à une ressource existante, vous pouvez définir la façon dont ils doivent apparaître dans l&#39;interface.

Cette étape n&#39;est pas obligatoire, car vous pourrez toujours renseigner votre ressource et accéder à ses données via les workflows, les audiences et l&#39;API REST.

Dans l’ **[!UICONTROL Screen definition]** onglet, vous pouvez effectuer les opérations suivantes :

* Ajouter l&#39;accès à la ressource personnalisée dans le volet de navigation
* Personnaliser la manière dont sera présentée la liste des éléments constituant la ressource
* Définir l&#39;affichage du détail de chaque élément de la ressource

## Permettre l&#39;accès depuis le menu de navigation {#enabling-access-from-the-navigation-menu}

Si vous souhaitez que votre ressource dispose d&#39;un écran dédié, vous pouvez la rendre accessible depuis le menu de navigation.

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. Cochez la **[!UICONTROL Add an entry in the 'Client data' section]** case pour autoriser l&#39;accès à cette ressource à partir du volet de navigation.

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Définir la configuration de liste par défaut {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. Le champ ajouté s&#39;affiche dans la liste. Vous pouvez modifier son libellé et sa largeur.

   ![](assets/schema_extension_20.png)

1. Dans la **[!UICONTROL Simple search]** section, cochez la **[!UICONTROL Specify the fields to be taken into account in the search]** pour définir les champs qui seront inclus dans la recherche.

   >[!IMPORTANT]
   >
   >Cette configuration remplace les champs utilisés dans la recherche par défaut.

1. Dans la **[!UICONTROL Advanced filtering]** section, cochez la **[!UICONTROL Add search fields]** case pour ajouter d’autres champs au-delà du champ de recherche simple. Par exemple, si vous sélectionnez le champ &quot;date&quot; parmi les champs que vous avez créés, l&#39;utilisateur pourra effectuer une recherche ne portant que sur la date.
1. Vous pouvez modifier l&#39;ordre des champs pour les deux types de recherche.
1. Dans le cas d&#39;une recherche avancée, il est possible d&#39;ajouter des champs de type liens vers une ressource liée. These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

L&#39;écran de présentation de la ressource est maintenant défini.

## Définir la configuration de l&#39;écran de détail {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. Dépliez la **[!UICONTROL Detail screen configuration]** section et vérifiez **[!UICONTROL Define a detail screen]** pour configurer l’écran correspondant à chaque élément de la ressource. Si vous ne cochez pas cette case, le détail des éléments de cette ressource ne sera pas accessible.
1. Vous pouvez ajouter en un seul clic tous les champs de votre ressource personnalisée. To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. Sélectionnez un élément parmi ceux créés pour cette ressource et indiquez un type de champ :

   * **[!UICONTROL Input field]**: est un champ modifiable.
   * **[!UICONTROL Value]**: est un champ en lecture seule.
   * **[!UICONTROL List]**: est une table.
   * **[!UICONTROL Separator]**: sépare vos éléments en .
   ![](assets/schema_extension_23.png)

1. L&#39;élément ajouté s&#39;affiche dans la liste. Vous pouvez modifier son libellé.

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   Vous pouvez ainsi afficher un séparateur pour que votre fenêtre soit mieux organisée.

   ![](assets/schema_extension_25.png)

L&#39;écran de détail de la ressource est maintenant défini.

## Section Actions sur les données {#actions-on-data-section}

Ces paramètres permettent d&#39;afficher une barre de contrôle dans l&#39;écran de la ressource personnalisée. Trois options sont disponibles :

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: cette option vous permet d’activer la création d’éléments de la ressource. L&#39;utilisateur peut donc ajouter des enregistrements supplémentaires.

   >[!NOTE]
   >
   >Vous devez activer l&#39;écran de détail associé à la ressource pour rendre cette option accessible.

* **[!UICONTROL Authorize duplicating]**: cette option vous permet d’activer la duplication des enregistrements liés à la ressource personnalisée.
* **[!UICONTROL Authorize deleting]**: cette option vous permet d’activer la suppression d’enregistrements liés à la ressource personnalisée.
