---
title: Entités organisationnelles
description: Définissez les niveaux d'accès de vos utilisateurs à l'aide des entités organisationnelles.
page-status-flag: never-activated
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 100%

---


# Entités organisationnelles{#organizational-units}

## A propos des entités {#about-units}

Chaque objet et utilisateur de la plate-forme est rattaché à une entité organisationnelle. Cette entité permet de définir une structure hiérarchique afin de filtrer la vue des utilisateurs. L&#39;entité d&#39;un utilisateur définit son niveau d&#39;accès aux différents objets de la plateforme.

>[!IMPORTANT]
>
>Si un utilisateur n&#39;est rattaché à aucune entité, il ne pourra pas se connecter à Adobe Campaign. Si vous souhaitez restreindre les accès d&#39;un utilisateur ou d&#39;un groupe d&#39;utilisateur, ne le rattachez pas à l&#39;entité **[!UICONTROL Toutes]**.
>
>Par défaut, l&#39;entité organisationnelle **[!UICONTROL Tous (tous)]** est affectée au groupe de sécurité **[!UICONTROL Administrateurs]**. Elle est en lecture seule et ne peut pas être modifiée.

Un utilisateur a accès, en lecture seule, à tous les objets des entités parentes. Il a accès en lecture et écriture à tous les objets de son entité et des entités filles. Un utilisateur n&#39;a pas accès aux objets des branches parallèles.

Par défaut, seules les entités **[!UICONTROL Toutes]** sont disponibles.

Lorsqu&#39;une entité organisationnelle est affectée à l&#39;utilisateur, celle-ci sera toujours appliquée aux objets créés par l&#39;utilisateur.

![](assets/user_management_2.png)

>[!NOTE]
>
>Lorsqu&#39;un utilisateur est présent dans plusieurs groupes rattachés à différentes entités, certaines règles s&#39;appliquent. Voir à ce propos la section [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md).

## Création et gestion des entités   {#creating-and-managing-units}

Les entités organisationnelles vous permettent de filtrer votre instance en fonction de l&#39;organisation à laquelle vos utilisateurs sont liés. Cette entité peut représenter une région, un pays et même une marque dans votre instance.

Nous avons auparavant créé des groupes de sécurité avec différents rôles attribués à deux utilisateurs : un utilisateur est assigné aux groupes de sécurité Administrateurs et Geometrixx, tandis que l&#39;autre appartient aux groupes de sécurité Utilisateurs standard et Geometrixx Clothes. Pour consulter l&#39;exemple complet, reportez-vous à la section [Créer un groupe de sécurité et affecter des utilisateurs](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).

Il nous faut à présent créer les entités organisationnelles pour les groupes de sécurité Geometrixx Clothes et Geometrixx :

1. Dans le menu avancé d&#39;Adobe Campaign, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs &amp; sécurité]** > **[!UICONTROL Entités organisationnelles]**.
1. Cliquez sur **[!UICONTROL Créer]** pour commencer à configurer votre entité organisationnelle.

   ![](assets/manage_units_1.png)

1. Remplacez le **[!UICONTROL Libellé]** et l&#39;**[!UICONTROL Identifiant]** par défaut par Geometrixx.
1. Liez ensuite cette entité à une entité parente. Nous choisissons ici **[!UICONTROL Toutes]**.

   ![](assets/manage_units_2.png)

1. Enfin, cliquez sur **[!UICONTROL Créer]** pour commencer à assigner votre entité organisationnelle au groupe de sécurité.
1. Suivez la même procédure pour l&#39;entité Geometrixx Clothes, à l&#39;exception que l&#39;entité parente doit être l&#39;entité créée précédemment : Geometrixx.

   ![](assets/manage_units_3.png)

Pour connaître l&#39;impact de l&#39;assignation de différentes entités à différents groupes de sécurité, l&#39;utilisateur assigné aux groupes Administrateur et Geometrixx créera deux modèles d&#39;email pour déterminer ce à quoi l&#39;autre utilisateur assigné à Utilisateur standard et Geometrixx Clothes peut ou non accéder.

1. Dans le menu avancé, sélectionnez **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]**.
1. Dupliquez un modèle existant et personnalisez-le selon vos besoins. Voir à ce propos la section [Modèles](../../start/using/marketing-activity-templates.md).
1. Une fois le modèle créé, sélectionnez l&#39;icône **[!UICONTROL Editer les propriétés]** pour lui assigner des entités.

   ![](assets/manage_units_6.png)

1. Dans le menu déroulant **[!UICONTROL Autorisation d&#39;accès]**, sélectionnez l&#39;entité organisationnelle.

   Nous allons créer un modèle avec l&#39;entité organisationnelle Geometrixx que nous avons créée.

   ![](assets/manage_units_5.png)

1. Suivez les mêmes procédures pour créer le second modèle assigné à l&#39;entité organisationnelle Geometrixx Clothes créée précédemment.

L&#39;utilisateur assigné aux groupes Utilisateurs standard et Geometrixx Clothes pourra voir les deux modèles. En raison de la structure hiérarchique des entités organisationnelles, il disposera d&#39;un accès en lecture et écriture au modèle lié à l&#39;entité Geometrixx Clothes, et uniquement d&#39;un accès en lecture seule au modèle à l&#39;entité Geometrixx.

![](assets/manage_units_7.png)

L&#39;entité Geometrixx Clothes étant une entité fille de Geometrixx, le message suivant apparaît lorsque l&#39;utilisateur tente de modifier le modèle Geometrixx :

![](assets/manage_units_8.png)

Les entités organisationnelles peuvent restreindre l&#39;accès aux différentes fonctionnalités telles que les profils. Par exemple, si notre utilisateur Geometrixx Clothes accède à l&#39;onglet **[!UICONTROL Profils]**, il aura un accès complet aux profils de l&#39;entité organisationnelle Geometrixx Clothes et pourra les modifier.

Alors que les profils de l&#39;entité organisationnelle Geometrixx seront en lecture seule, l&#39;erreur suivante apparaîtra si notre utilisateur tente de modifier un profil : **[!UICONTROL Vous n&#39;avez pas les droits nécessaires pour modifier la ressource &#39;profil&#39; d&#39;identifiant]**.

![](assets/manage_units_10.png)

## Partitionnement des profils {#partitioning-profiles}

Si votre organisation doit isoler les profils contactés par chacune de vos marques, vous pouvez les partitionner en fonction de leur entité organisationnelle.

Par défaut, les champs de l&#39;entité organisationnelle ne sont pas disponibles dans les profils et doivent être ajoutés.

Les profils sans entité organisationnelle ne sont pas accessibles par les utilisateurs.

>[!IMPORTANT]
>
>Il est recommandé d&#39;ajouter cette option avant d&#39;importer des profils. Si vous avez déjà importé votre base client, il est nécessaire d&#39;effectuer une mise à jour afin de définir les valeurs de l&#39;entité organisationnelle sur les profils déjà importés.

1. Dans le menu avancé, via le logo Adobe Campaign, sélectionnez **Administration > Développement > Ressources personnalisées**.
1. Sélectionnez **Profil** ou créez une ressource personnalisée pour étendre les profils.
1. Cochez la case **Ajouter les champs de gestion des autorisations d&#39;accès** pour ajouter les entités organisationnelles à l&#39;extension **Profil**.

   ![](assets/user_management_9.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Mettez à jour la structure en publiant de nouveau les ressources personnalisées. Pour plus d&#39;informations sur la publication, voir la section [Mettre à jour la structure](../../developing/using/data-model-concepts.md).

Les champs de l&#39;entité organisationnelle sont ajoutés à vos profils, dans la section **[!UICONTROL Autorisation d&#39;accès]**.

![](assets/user_management_10.png)

**Rubriques connexes** :

* [A propos des entités](../../administration/using/organizational-units.md#about-units)
* [Gestion des accès](../../administration/using/about-access-management.md)

