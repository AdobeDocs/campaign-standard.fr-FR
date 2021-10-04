---
title: Gestion des groupes et des utilisateurs
description: Découvrez comment créer des groupes de sécurité et gérer les utilisateurs.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: user,overview;user,main;security,overview;security,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 4b9834ab-0f7c-419e-a210-77a018ba874d
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 86%

---

# Gestion des groupes et des utilisateurs{#managing-groups-and-users}

## Groupes de sécurité {#about-security-groups}

Les groupes de sécurité sont des ensembles d&#39;utilisateurs qui partagent les mêmes rôles et droits au sein de votre entreprise.

Les utilisateurs doivent toujours être rattachés à un groupe de sécurité afin que vous puissiez leur affecter des rôles spécifiques et des entités organisationnelles.

Pour plus d’informations sur les rôles, le tableau de la page suivante reprend les différentes opérations possibles en fonction du ou des rôle des l’utilisateur : [Autorisations dans Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=fr).

Les groupes de sécurité par défaut sont :

* **[!UICONTROL Administrateurs]**
* **[!UICONTROL Superviseurs de diffusion]**
* **[!UICONTROL Utilisateurs standard]**
* **[!UICONTROL Superviseurs de workflow]**

>[!IMPORTANT]
>
>Les groupes de sécurité **[!UICONTROL Accès aux paramètres de délivrabilité (délivrabilité)]** et **[!UICONTROL Agents de Message Center (mcExec)]** sont uniquement internes et ne doivent pas être affectés aux utilisateurs.

Pour pouvoir accéder à Adobe Campaign, chaque utilisateur doit être affecté à un groupe de sécurité.

Si vous souhaitez restreindre les accès d&#39;un utilisateur, ne l&#39;ajoutez pas dans le groupe des utilisateurs standard (Campaign Standard users), car celui-ci est rattaché à **[!UICONTROL toute]** l&#39;entité organisationnelle.

>[!NOTE]
>
>Par défaut, l’entité organisationnelle **[!UICONTROL Tous (tous)]** est affectée au groupe de sécurité **[!UICONTROL Administrateurs]**. Elle est en lecture seule et ne peut pas être modifiée.

## Créer un groupe de sécurité et affecter des utilisateurs {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Dans le Admin Console, les groupes de sécurité sont appelés profils.

Vous pouvez créer vos propres groupes de sécurité si les groupes d&#39;usine ne suffisent pas pour gérer vos utilisateurs. Ils peuvent être gérés par les administrateurs qui ont accès aux menus d’administration d’Adobe Campaign et au Admin Console. Pour plus d’informations sur le Admin Console, consultez cette [documentation](https://helpx.adobe.com/fr/enterprise/managing/user-guide.html).

Il nous faut tout d&#39;abord assigner les deux groupes d&#39;usine Utilisateurs standard et Administrateurs à nos utilisateurs. Ces groupes de sécurité limitent certaines fonctionnalités d&#39;Adobe Campaign : l&#39;Utilisateur standard dispose d&#39;un accès simple à Adobe Campaign, tandis que l&#39;Administrateur peut accéder aux menus d&#39;administration, par exemple.

Notez que toute modification apportée aux groupes de sécurité sur la console d&#39;administration sera synchronisée dès que les utilisateurs se connecteront à Adobe Campaign.

Nous souhaitons ensuite créer un ensemble de groupes de sécurité Geometrixx et Geometrixx Clothes qui limitent certains accès en fonction des entités organisationnelles de nos Utilisateur standard et Administrateur.

![](assets/ootb_security_group_1.png)

Pour commencer, vous devez assigner l&#39;un des groupes d&#39;usine à vos utilisateurs :

1. Dans le Admin Console, sélectionnez votre instance, puis l’onglet **Utilisateurs** .

   ![](assets/manage_security_group_2.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter un utilisateur]** et saisissez l&#39;adresse email de votre utilisateur.
1. Dans l&#39;onglet **[!UICONTROL Assigner des produits]**, sélectionnez votre instance, puis le groupe de sécurité d&#39;usine **[!UICONTROL Administrateurs]** dans la liste déroulante. L&#39;utilisateur pourra ainsi accéder aux menus d&#39;administration et créer les prochains groupes de sécurité.

   ![](assets/ootb_security_group_2.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** et suivez les mêmes procédures afin d&#39;assigner le groupe de sécurité d&#39;usine **[!UICONTROL Utilisateurs standard]** à votre nouvel utilisateur.

   ![](assets/ootb_security_group_3.png)

Une fois vos deux utilisateurs associés aux groupes de sécurité d&#39;usine **[!UICONTROL Administrateurs]** et **[!UICONTROL Utilisateurs standard]** qui assignent des rôles à nos utilisateurs, l&#39;utilisateur Administrateur peut créer les deux groupes de sécurité **Geometrixx** et **Geometrixx Clothes** qui assigneront les entités organisationnelles à nos utilisateurs en plus des groupes de sécurité d&#39;usine.

1. Dans le Admin Console, sélectionnez votre instance, puis l’onglet **Produits** .
1. Cliquez sur le bouton **Nouveau profil** pour créer le groupe de sécurité **Geometrixx**.

   ![](assets/create_security_1.png)

1. Saisissez le **[!UICONTROL Nom du profil]** en suivant cette syntaxe : **[!UICONTROL Campaign Standard- nom de l&#39;instance - Identifiant du groupe de sécurité]**, puis cliquez sur **[!UICONTROL Terminé]**.

   L&#39;identifiant choisi servira ensuite à créer le groupe de sécurité dans Adobe Campaign.

   >[!NOTE]
   >
   >Si la syntaxe ci-dessus semble ne pas fonctionner avec une instance plus ancienne, elle doit être remplacée par **[!UICONTROL Campaign - nom de l&#39;instance - Identifiant du groupe de sécurité]**.

   ![](assets/manage_security_group_1.png)

1. Suivez ensuite la même procédure pour créer le groupe de sécurité **Geometrixx Clothes**.
1. Assignez votre groupe de sécurité à votre utilisateur en sélectionnant l&#39;onglet **[!UICONTROL Utilisateurs]**.

   ![](assets/manage_security_group_2.png)

1. Cliquez sur l&#39;utilisateur que vous avez créé, puis sur l&#39;icône ![](assets/managing_security_group_10.png) dans la catégorie **[!UICONTROL Produits]**.

   Sélectionnez **[!UICONTROL Editer les produits assignés directement]** pour commencer à assigner un nouveau groupe de sécurité à votre utilisateur.

   ![](assets/manage_security_group_8.png)

1. Dans l&#39;onglet **[!UICONTROL Assigner des produits]**, sélectionnez votre instance, puis le groupe de sécurité Geometrixx que vous avez créé dans la liste déroulante pour l&#39;affecter à votre utilisateur Administrateur.

   Cliquez sur **[!UICONTROL Enregistrer]**.

   ![](assets/manage_security_group_3.png)

   Si un utilisateur se trouve dans plusieurs groupes :

   * Les rôles des différents groupes sont cumulés. Les utilisateurs figurent ici dans deux groupes différents : l&#39;un agira sur les rôles, l&#39;autre sur les entités.
   * C&#39;est l&#39;entité ayant le niveau le plus élevé dans la hiérarchie qui sera utilisée (voir l&#39;exemple de la section [Entités organisationnelles](../../administration/using/organizational-units.md)).
   * L&#39;utilisateur ne sera plus en mesure de se connecter si les entités présentent le même niveau équivalent et se situent dans des branches parallèles de la hiérarchie.

1. Suivez la même procédure pour assigner le groupe de sécurité Geometrixx Clothes à votre Utilisateur standard.

   ![](assets/manage_security_group_9.png)

Les groupes de sécurité nouvellement créés sont désormais créés dans le Admin Console . Pour qu&#39;ils soient totalement synchronisés, vous devrez également les créer dans Adobe Campaign.

L&#39;utilisateur Administrateur doit créer le jeu de groupes de sécurité utilisé pour assigner des entités organisationnelles : Geometrixx et Geometrixx Clothes. Pour découvrir comment créer des entités organisationnelles, voir [Création et gestion des entités](../../administration/using/organizational-units.md#creating-and-managing-units).

1. Cliquez sur le logo **Adobe**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Utilisateurs et sécurité > Groupes de sécurité]**.
1. Créez votre groupe de sécurité et indiquez ses **[!UICONTROL Libellé]** et **[!UICONTROL Identifiant]**.

   L’identifiant doit être le même que celui choisi dans le Admin Console.

1. Dans le champ **[!UICONTROL Accès des utilisateurs]**, assignez l&#39;entité organisationnelle. Le groupe de sécurité Geometrixx est ici assigné à l&#39;entité **[!UICONTROL Toute]**.

   >[!NOTE]
   >
   >Si vous attribuez un groupe de sécurité d’usine à vos utilisateurs, vous devez réinitialiser l’entité organisationnelle.

   ![](assets/manage_security_group_6.png)

1. Vous pouvez également assigner des rôles à votre groupe de sécurité. Dans notre cas, cette étape n&#39;est pas nécessaire, car les groupes de sécurité d&#39;usine **[!UICONTROL Administrateurs]** et **[!UICONTROL Utilisateurs standard]** sont utilisés pour assigner des rôles.
1. Suivez les mêmes procédures pour créer le dernier groupe de sécurité Geometrixx Clothes et assigner l&#39;entité organisationnelle Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Vos utilisateurs sont maintenant affectés à un groupe de sécurité et peuvent se connecter à Adobe Campaign.

>[!IMPORTANT]
>
>Si les utilisateurs sont supprimés d’un groupe de sécurité dans le Admin Console, ils restent membres du groupe de sécurité Adobe Campaign et ne pourront plus se connecter à Adobe Campaign. Dans un tel cas, il convient de supprimer les adresses email des utilisateurs dans Admin Console pour éviter qu’ils ne reçoivent des informations sensibles.
