---
title: Gestion des packages
description: Les administrateurs peuvent définir des packages pour échanger des ressources entre différentes instances Adobe Campaign par le biais de fichiers structurés au format XML.
page-status-flag: never-activated
uuid: d041f549-bfc5-4e6b-87bf-a63c7c224bca
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: c3015cdc-8432-4e57-8ac0-43ae7827e3b0
context-tags: packageDef,overview;packageInstall,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 100%

---


# Gestion des packages{#managing-packages}

Les administrateurs peuvent définir des packages pour échanger des ressources entre différentes instances Adobe Campaign par le biais de fichiers structurés au format XML. Il peut s&#39;agir de paramètres de configuration ou de données.

C&#39;est utile par exemple quand on souhaite transférer des données d&#39;un serveur à un autre ou répliquer les paramétrages d&#39;une instance.

Les packages sont disponibles dans les menus **[!UICONTROL Administration]** > **[!UICONTROL Déploiement]** > **[!UICONTROL Exports de package]** ou **[!UICONTROL Imports de package.]** Les deux menus ont un comportement similaire.

Les éléments de chaque liste s&#39;affichent par défaut selon leur date de modification ou d&#39;installation, de la plus récente à la plus ancienne.

![](assets/packages_1.png)

Pour afficher le contenu d&#39;un élément et le modifier, cliquez sur son libellé. Reportez-vous aux sections [Export d&#39;un package](#exporting-a-package) et [Import d&#39;un package](#importing-a-package).

## Exports de package {#package-exports}

### Packages par défaut {#standard-packages}

**[!UICONTROL Il existe deux packages natifs, Plate-forme]** et **[!UICONTROL Administration]**, qui contiennent chacun une liste prédéfinie de ressources à exporter. Ils s&#39;ouvrent en lecture seule et peuvent uniquement être exportés.

![](assets/packages_14.png)

>[!IMPORTANT]
>
>L&#39;export de package n&#39;est pas autorisé si les ressources exportées ont des identifiants par défaut. Il est donc obligatoire de modifier les identifiants des ressources exportables en s&#39;éloignant des modèles livrés par Adobe Campaign Standard. Par exemple, pour exporter des profils de test, il ne faut pas utiliser un identifiant contenant la valeur &quot;SDM&quot; ou &quot;sdm&quot;.
>
>Lors de l&#39;export de packages contenant des identifiants par défaut, les erreurs du type suivant peuvent s&#39;afficher : &quot;L&#39;entité de type &#39;Marques (branding)&#39; utilise un identifiant par défaut (&#39;BRD1&#39;) susceptible de provoquer un conflit lors de l&#39;import du package. Modifiez ce nom et renouvelez l&#39;opération.&quot;

Les étapes d&#39;export d&#39;un package sont présentées dans la section [Export d&#39;un package](#exporting-a-package).

* Le package **[!UICONTROL Plate-forme]** regroupe toutes les ressources ajoutées pendant la configuration technique : ressources personnalisées, ensembles de ressources personnalisées, Triggers et options d&#39;application de type **[!UICONTROL Système]**.
* Le package **[!UICONTROL Administration]** regroupe tous les objets ajoutés pendant la configuration métier : modèles d&#39;opération, modèles de contenu, modèles de diffusion, modèles de landing page, modèles de programme et modèles de workflow.

   Il comprend également les objets suivants : blocs de contenu, mappings de ciblage, comptes externes, entités organisationnelles, options d&#39;application de type **[!UICONTROL Utilisateur]**, rôles, typologies, règles de typologie et utilisateurs.

>[!NOTE]
>
>Il n&#39;est pas possible de modifier la définition de ces deux packages. En revanche, ces derniers contiennent toujours les données disponibles les plus à jour. Vous pouvez [créer vos propres packages](#creating-a-package) pour exporter des éléments spécifiques.

### Création de package {#creating-a-package}

Pour exporter des jeux de données spécifiques, vous devez créer un package.

Pour créer un package, vous devez disposer des droits d&#39;administration.

1. Depuis **[!UICONTROL Administration]** > **[!UICONTROL Déploiement]** > **[!UICONTROL Exports de package]**, cliquez sur le bouton **[!UICONTROL Créer]** dans la liste des contenus de package.

   L&#39;élément est immédiatement créé. Pour annuler sa création, il faut revenir à la liste et cocher la case correspondante pour le supprimer.

1. Dans l&#39;écran de définition du package, indiquez un nom et un identifiant.
1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]** si vous souhaitez ajouter une description et restreindre l&#39;accès à certains utilisateurs.

   ![](assets/packages_18.png)

1. Dans l&#39;onglet **[!UICONTROL Définition de l&#39;export]**, utilisez le bouton **[!UICONTROL Créer un élément]** pour sélectionner les ressources que vous souhaitez exporter.

   ![](assets/packages_2.png)

1. Les ressources s&#39;affichent par ordre alphabétique et peuvent être filtrées par nom. Leur nom technique est indiqué entre parenthèses. Choisissez un élément de la liste et validez votre choix.

   ![](assets/packages_3.png)

1. Le nom de la ressource s&#39;affiche dans l&#39;onglet **[!UICONTROL Définition de l&#39;export]**. Pour modifier une ressource, cochez la case correspondante et utilisez le bouton **[!UICONTROL Afficher le détail de l&#39;élément sélectionné]**.

   ![](assets/packages_4.png)

1. Utilisez l&#39;éditeur de requêtes pour filtrer les éléments à exporter. Voir à ce propos la section [Edition de requêtes](../../automating/using/editing-queries.md#creating-queries).

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >Vous pouvez exporter jusqu&#39;à 5 000 objets par ressource.

1. Une fois que vous avez défini toutes les ressources à exporter, enregistrez votre sélection.

Votre package est maintenant créé et prêt à être exporté.

### Export d&#39;un package {#exporting-a-package}

L&#39;export d&#39;un package vous permet d&#39;enregistrer un état spécifique d&#39;une ressource que vous pourrez réimporter ultérieurement sur une même instance ou sur une autre instance.

>[!CAUTION]
>
>L&#39;export de packages n&#39;est pas autorisé si les ressources exportées ont des identifiants d&#39;usine. Il est donc obligatoire de modifier les identifiants des ressources exportables en s&#39;éloignant des modèles livrés par Adobe Campaign Standard. Par exemple, pour exporter des profils de test, il ne faut pas utiliser un identifiant contenant la valeur &quot;SDM&quot; ou &quot;sdm&quot;.

1. Depuis **[!UICONTROL Administration]** > **[!UICONTROL Déploiement]** > **[!UICONTROL Exports de package]**, sélectionnez un package pour accéder à ses détails.
1. Vérifiez que le package contient les données dont vous avez besoin.
1. Cliquez sur le bouton **[!UICONTROL Démarrer l&#39;export]**.

Le fichier exporté est stocké dans le répertoire de téléchargement du navigateur utilisé. Il est automatiquement nommé &quot;package_xxx.xml&quot;, &quot;xxx&quot; correspondant à l&#39;identifiant du package.

Lorsque l&#39;opération est terminée, plusieurs sections s&#39;affichent :

* **[!UICONTROL La section Statut de l&#39;export]** indique si l&#39;opération s&#39;est correctement déroulée.

   ![](assets/packages_6.png)

* L&#39;onglet **[!UICONTROL Journal]** permet de consulter les différentes étapes de l&#39;export. Il contient les états de tous les exports précédents.

   ![](assets/packages_7.png)

>[!NOTE]
>
>Lorsque vous sélectionnez, à partir de la liste des définitions de package, un élément qui a déjà été exporté, les onglets **[!UICONTROL Journal]** et **[!UICONTROL Dernier export]** sont toujours disponibles.

## Imports de package {#package-imports}

### Mises à jour système {#system-updates}

La liste des imports de package contient notamment les imports automatiques liés à des mises à jour effectuées par Adobe.

![](assets/packages_15.png)

La vue **[!UICONTROL Logs d&#39;exécution]** répertorie toutes les étapes de l&#39;import. Le panneau latéral affiche les informations générales.

![](assets/packages_11.png)

>[!NOTE]
>
>Ces éléments sont accessibles en lecture seule.

### Import d&#39;un package {#importing-a-package}

Un administrateur peut importer manuellement un package issu d&#39;un export réalisé au préalable à partir d&#39;une instance Adobe Campaign. Voir à ce propos la section [Exports de package](#package-exports).

L&#39;import manuel d&#39;un package consiste en deux étapes : il faut d&#39;abord télécharger un fichier avant de pouvoir importer son contenu.

1. Depuis **[!UICONTROL Administration]** > **[!UICONTROL Déploiement]** > **[!UICONTROL Imports de package]**, cliquez sur le bouton **[!UICONTROL Créer]** dans la liste des imports de package.

   L&#39;élément est immédiatement créé. Pour annuler sa création, il faut revenir à la liste et cocher la case correspondante pour le supprimer.

1. Indiquez un nom et un identifiant pour le nouvel import.
1. Sélectionnez le fichier que vous souhaitez télécharger par glisser-déposer ou en cliquant sur le lien **[!UICONTROL parcourez votre disque]**.

   Les fichiers importés doivent être au format XML ou ZIP (contenant un fichier XML).

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Pour remplacer le document téléchargé, supprimez d&#39;abord le fichier à l&#39;aide de la croix située à droite de son nom et renouvelez l&#39;opération.

1. Une fois le fichier téléchargé, importez son contenu dans la base à l&#39;aide du bouton **[!UICONTROL Démarrer l&#39;import]**.

   ![](assets/packages_19.png)

Lorsque l&#39;opération est terminée, plusieurs sections s&#39;affichent :

* **[!UICONTROL La section Statut de l&#39;import]** indique si l&#39;opération s&#39;est correctement déroulée.
* L&#39;onglet **[!UICONTROL Logs d&#39;exécution]** permet de consulter les différentes étapes de l&#39;import. Il est particulièrement important pour l&#39;affichage des erreurs.

   ![](assets/packages_20.png)

Une fois qu&#39;un package a été importé, il n&#39;est pas possible de le réimporter à partir du même élément. Vous pouvez uniquement modifier son libellé et son identifiant.

Pour réimporter le même package, vous devez revenir à la liste des imports de package, créer un élément et télécharger à nouveau le fichier de votre choix.
