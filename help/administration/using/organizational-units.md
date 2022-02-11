---
title: Entités organisationnelles
description: Définir les niveaux d’accès de vos utilisateurs à l’aide des entités organisationnelles
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: ht
source-wordcount: '881'
ht-degree: 100%

---

# Entités organisationnelles{#organizational-units}

## À propos des entités {#about-units}

Chaque objet et utilisateur de la plateforme est rattaché à une entité organisationnelle. Cette entité permet de définir une structure hiérarchique afin de filtrer la vue des utilisateurs. L&#39;entité d&#39;un utilisateur définit son niveau d&#39;accès aux différents objets de la plateforme.

>[!IMPORTANT]
>
>Si un utilisateur n&#39;est rattaché à aucune entité, il ne pourra pas se connecter à Adobe Campaign. Si vous souhaitez restreindre les accès d’un utilisateur ou d’un groupe d’utilisateur, ne le rattachez pas à l’entité **[!UICONTROL Tous]**. Nous vous recommandons d’ajouter l’option **Accéder aux champs de gestion des autorisations** avant d’importer des profils. Voir à ce propos cette [section](../../administration/using/organizational-units.md#partitioning-profiles).
>
>Par défaut, l&#39;entité organisationnelle **[!UICONTROL Tous (tous)]** est affectée au groupe de sécurité **[!UICONTROL Administrateurs]**. Elle est en lecture seule et ne peut pas être modifiée.

Un utilisateur a accès, en lecture seule, à tous les objets des entités parentes. Cet utilisateur dispose d’un accès en lecture et écriture à tous les objets de son unité et de ses entités enfants. Un utilisateur n&#39;a pas accès aux objets des branches parallèles.

Par défaut, seules les entités **[!UICONTROL Toutes]** sont disponibles.

Lorsqu&#39;une entité organisationnelle est affectée à l&#39;utilisateur, celle-ci sera toujours appliquée aux objets créés par l&#39;utilisateur.

![](assets/user_management_2.png)

>[!NOTE]
>
>Lorsqu&#39;un utilisateur est présent dans plusieurs groupes rattachés à différentes entités, certaines règles s&#39;appliquent. Pour plus d&#39;informations, consultez la section [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md).

## Création et gestion des entités      {#creating-and-managing-units}

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
1. Dupliquez un modèle existant et personnalisez-le selon vos besoins. Pour plus d&#39;informations, consultez la section [Modèles](../../start/using/marketing-activity-templates.md).
1. Une fois le modèle créé, sélectionnez l&#39;icône **[!UICONTROL Editer les propriétés]** pour lui assigner des entités.

   ![](assets/manage_units_6.png)

1. Dans le menu déroulant **[!UICONTROL Autorisation d&#39;accès]**, sélectionnez l&#39;entité organisationnelle.

   Nous allons créer un modèle avec l&#39;entité organisationnelle Geometrixx que nous avons créée.

   ![](assets/manage_units_5.png)

1. Suivez les mêmes procédures pour créer le second modèle assigné à l&#39;entité organisationnelle Geometrixx Clothes créée précédemment.

Les utilisateurs assignés aux groupes **Utilisateur standard** et **Vêtements Geometrixx** pourront voir les deux modèles. En raison de la structure hiérarchique des entités organisationnelles, ils disposeront d’un accès en lecture et écriture au modèle lié à l’entité Vêtements Geometrixx, et uniquement d’un accès en lecture seule au modèle lié à l’entité Geometrixx.

![](assets/manage_units_7.png)

L’entité Vêtements Geometrixx étant une entité enfant de Geometrixx, le message suivant apparaît lorsqu’un utilisateur tente de modifier le modèle Geometrixx :

![](assets/manage_units_8.png)

Les entités organisationnelles peuvent limiter l’accès aux différentes fonctionnalités telles que les profils. Par exemple, si nos utilisateurs Vêtements Geometrixx accèdent à l’onglet **[!UICONTROL Profils]**, ils bénéficient d’un accès total aux profils de l’unité organisationnelle Vêtements Geometrixx et peuvent les modifier.

Alors que les profils de l’entité organisationnelle Geometrixx seront en lecture seule, l’erreur suivante apparaîtra si des utilisateurs tentent de modifier un profil : **[!UICONTROL Vous n’avez pas les droits nécessaires pour modifier la ressource &#39;profil&#39; d’identifiant]**.

![](assets/manage_units_10.png)

## Partitionnement des profils {#partitioning-profiles}

>[!IMPORTANT]
>
>Nous vous recommandons d’ajouter cette option avant d’importer des profils, car les utilisateurs ne peuvent pas accéder aux profils sans entité organisationnelle.
>
>Si vous avez déjà importé votre base client, il est nécessaire d’effectuer une mise à jour afin de définir les valeurs de l’entité organisationnelle sur les profils déjà importés.

Si votre organisation doit isoler les profils contactés par chacune de vos marques, vous pouvez les partitionner en fonction de leur entité organisationnelle.

Par défaut, les champs de l&#39;entité organisationnelle ne sont pas disponibles dans les profils et doivent être ajoutés.

1. Dans le menu avancé, via le logo Adobe Campaign, sélectionnez **Administration > Développement > Ressources personnalisées**.
1. Sélectionnez **Profil** ou créez une ressource personnalisée pour étendre les profils. Pour plus d’informations sur l&#39;extension des profils, consultez cette [page](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Cochez la case **Ajouter les champs de gestion des autorisations d&#39;accès** pour ajouter les entités organisationnelles à l&#39;extension **Profil**.

   ![](assets/user_management_9.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.
1. Mettez à jour la structure en publiant de nouveau les ressources personnalisées. Pour plus d&#39;informations sur la publication, voir la section [Mettre à jour la structure](../../developing/using/updating-the-database-structure.md).

Les champs de l&#39;entité organisationnelle sont ajoutés à vos profils, dans la section **[!UICONTROL Autorisation d&#39;accès]**.

![](assets/user_management_10.png)

**Rubriques connexes** :

* [À propos des entités](../../administration/using/organizational-units.md#about-units)
* [Gestion des accès](../../administration/using/about-access-management.md)
