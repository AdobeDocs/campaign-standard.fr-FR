---
title: Gestion des utilisateurs
description: Les utilisateurs d’Adobe Campaign détiennent des rôles spécifiques. Découvrez les principaux types d’utilisateurs.
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 6605203e-78f8-4ebd-b256-a621a3a9d638
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 100%

---

# Gestion des utilisateurs{#users-management}

## À propos des utilisateurs {#about-users}

Adobe Campaign permet d’affecter un ensemble de rôles à vos utilisateurs afin de définir la partie de l’interface à laquelle ils ont accès.

Les rôles spécifiques et les autorisations correspondantes sont présentés dans les sections suivantes : [Rôles](../../administration/using/list-of-roles.md) et [Autorisations](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf).

Les administrateurs peuvent gérer les utilisateurs depuis Admin Console. Les utilisateurs sont ensuite automatiquement synchronisés avec Adobe Campaign. Pour plus d’informations, consultez la documentation relative à [Admin Console](https://helpx.adobe.com/fr/enterprise/using/users.html).

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#video)

Pour visualiser les utilisateurs dans Adobe Campaign, cliquez sur le logo **Adobe**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Utilisateurs &amp; Sécurité > Utilisateurs]**.

Pour accéder à l&#39;interface de gestion des utilisateurs à partir d&#39;Adobe Campaign, cliquez sur **[!UICONTROL Administrer les utilisateurs]**.

![](assets/user_management_5.png)

**Rubriques connexes :**

* Vidéo [Gérer les autorisations utilisateur](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html?lang=fr)
* [Liste des rôles](../../administration/using/list-of-roles.md)
* [Liste des autorisations](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

## Type d’utilisateurs {#type-of-users}

Cette répartition des utilisateurs n’est pas obligatoire ; elle représente uniquement l’utilisation la plus courante d’Adobe Campaign.

Cette section présente les principaux types d’utilisateurs Adobe Campaign. Pour plus d’informations sur les rôles spécifiques qu’un utilisateur peut détenir (démarrer des diffusions, exporter, préparer des diffusions, etc.), reportez-vous aux pages [Liste des rôles](../../administration/using/list-of-roles.md) et [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md).

Elle est axée sur la répartition des différentes tâches entre trois types d’utilisateurs principaux dans Adobe Campaign :

* [Administrateurs fonctionnels](#functional-administrators) : il s’agit des utilisateurs les plus techniques parmi tous les utilisateurs de votre organisation.
* [Utilisateurs experts](#advanced-users) : ils configurent tous les éléments dont les spécialistes marketing ont besoin pour envoyer et contrôler leurs diffusions.
* [Utilisateurs de base](#basic-users) : il s’agit des spécialistes marketing qui personnalisent, diffusent et contrôlent leurs campagnes.

>[!NOTE]
>
>Les administrateurs fonctionnels diffèrent des administrateurs techniques Adobe. Les administrateurs techniques Adobe assument un rôle interne à Adobe qui ne peut être utilisé par aucun client. Ils gèrent l’approvisionnement et l’hébergement de l’instance, le contrôle et la supervision de l’infrastructure et la résolution des problèmes techniques.

### Administrateurs fonctionnels {#functional-administrators}

Les administrateurs fonctionnels sont les utilisateurs pouvant accéder aux parties les plus techniques de l’interface. Ils détiennent le rôle **[!UICONTROL Administration]** et veillent à ce que la plateforme soit configurée de sorte que les spécialistes marketing puissent se concentrer exclusivement sur la diffusion de leurs campagnes.

>[!IMPORTANT]
>
>Seuls les administrateurs fonctionnels, avec un rôle d’**[!UICONTROL administration]** et un accès aux entités **Toutes**, peuvent accéder aux logs d’envoi, aux logs de messages, aux logs de tracking, aux logs d’exclusion, aux logs de proposition et aux logs d’abonnement. Un utilisateur autre qu’administrateur peut cibler ces logs mais en commençant par une table liée (profils, diffusion).

Les administrateurs fonctionnels sont les seuls utilisateurs ayant accès au menu **[!UICONTROL Administration]** dans l’interface Adobe Campaign. Etant donné que ces utilisateurs doivent accéder à des ressources techniques, des rôles plus avancés doivent leur être attribués, tels que les rôles d’usine **[!UICONTROL Administration]** et **[!UICONTROL Datamodel]**. Ces rôles sont combinés dans le groupe de sécurité d’usine **[!UICONTROL Administrateurs]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu’ils peuvent effectuer :

* [Gérer les utilisateurs et les autorisations](../../administration/using/about-access-management.md) : gérez les accès à la Plateforme (utilisateurs, rôles, groupes de sécurité, entités).
* [Configurer les différents canaux](../../administration/using/about-channel-configuration.md) : configurez les différents canaux de la plateforme ainsi que la gestion des typologies et des quarantaines.
* [Configurer les paramètres généraux de l’application](../../administration/using/external-accounts.md) : configurez les différents éléments de l’application (comptes externes, options, workflows techniques).
* [Développer de nouvelles fonctionnalités pour améliorer les fonctions d’usine](../../developing/using/data-model-concepts.md) : gérez vos ressources personnalisées et accédez aux outils de diagnostic.
* [Configurer les paramètres de l’instance](../../administration/using/branding.md) : définissez vos différentes marques et configurez leurs paramètres (logo, gestion du tracking, domaine d’URL d’accès aux landing pages, etc.).
* [Exporter et importer des packages de données](../../automating/using/managing-packages.md) : échangez des ressources entre différentes instances Adobe Campaign par le biais de fichiers structurés au format XML.
* [Exporter des logs](../../automating/using/exporting-logs.md) et [définir des modèles d’import](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Utilisateurs experts             {#advanced-users}

Les utilisateurs experts sont des utilisateurs marketing qui effectuent les tâches les plus techniques dans Adobe Campaign. Ils préconfigurent tous les éléments utilisés par les marketeurs pour envoyer et contrôler leurs diffusions.

Ce type d’utilisateur requiert des rôles plus généraux que les administrateurs fonctionnels, mais doit néanmoins être en mesure d’effectuer certaines opérations techniques. Pour cela, ils doivent se faire attribuer, par exemple, les rôles d’usine **[!UICONTROL Export]**, **[!UICONTROL Import générique]** ou **[!UICONTROL Workflow]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu’ils peuvent effectuer :

* [Créer et exécuter des workflows complexes de Data Management](../../automating/using/about-data-management-activities.md) : importez, enrichissez et transformez les données pour alimenter votre base de données ou exportez les données dont vous avez besoin dans des fichiers externes afin de les exploiter dans vos propres outils.
* [Gérer les modèles](../../start/using/marketing-activity-templates.md) : gérez vos modèles pour préconfigurer certains paramètres de vos activités marketing selon vos besoins.
* [Créer des requêtes](../../automating/using/editing-queries.md#about-query-editor) et [gérer les audiences](../../audiences/using/about-audiences.md) : créez vos audiences manuellement à travers des requêtes ou automatiquement via des workflows dédiés.
* [Utiliser l’édition avancée d’expressions](../../automating/using/editing-queries.md#about-query-editor) : utilisez des fonctions avancées pour manipuler les valeurs utilisées afin de réaliser des requêtes spécifiques : manipulation de dates, de chaînes, de champs numériques, tris, etc.
* [Exporter des listes](../../automating/using/exporting-lists.md) et [importer des données à l’aide de modèles d’import existants](../../automating/using/importing-data-with-import-templates.md).

### Utilisateurs de base             {#basic-users}

Grâce à l’administrateur fonctionnel et aux utilisateurs experts, les spécialistes marketing peuvent personnaliser, diffuser et contrôler leurs campagnes sans se soucier de la configuration technique. Pour cela, ils doivent se faire attribuer, par exemple, les rôles d’usine **[!UICONTROL Préparer des diffusions]**, **[!UICONTROL Workflow]** et **[!UICONTROL Démarrer des diffusions]**. Ces rôles sont combinés dans le groupe de sécurité d’usine **[!UICONTROL Utilisateurs standard]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu’ils peuvent effectuer :

* [Gérer les programmes et campagnes](../../start/using/programs-and-campaigns.md) : créez des campagnes marketing incluant différents types d’activités (emails, SMS, notifications push, workflows, landing pages).
* Gérer les [profils](../../audiences/using/about-profiles.md) et les [profils de test](../../audiences/using/managing-test-profiles.md) : gérez les destinataires identifiés et les profils de test que vos diffusions cibleront. Ajoutez des informations comme le prénom, le nom, les coordonnées, les abonnements, les emails, etc.
* [Créer et envoyer des messages](../../sending/using/confirming-the-send.md) : créez votre message, sélectionnez l’audience, définissez le contenu du message et ses éléments de personnalisation, envoyez les bons à tirer puis le message final à votre audience.
* [Créer et publier des landing pages](../../channels/using/getting-started-with-landing-pages.md) : créez et gérez un ensemble de services que vous souhaitez proposer à vos clients, comme des formulaires d’inscription ou de désinscription.
* [Créer et exécuter des workflows d’opérations](../../automating/using/building-a-workflow.md) : automatisez les processus de campagne à l’aide de workflows.
* Contrôler les activités marketing par le biais des [rapports disponibles](../../reporting/using/defining-the-report-period.md).

## Création d’un utilisateur {#creating-a-user}

Pour ajouter un utilisateur à votre instance, vous devez d’abord le créer dans Admin Console avant de le gérer dans Adobe Campaign Standard.

1. Dans le menu avancé, sélectionnez **[!UICONTROL Administration > Utilisateurs &amp; sécurité > Utilisateurs]** et cliquez sur **[!UICONTROL Administrer les utilisateurs]** pour accéder à la console d’administration.

   ![](assets/user_management_5.png)

1. Dans **[!UICONTROL Admin Console]**, cliquez sur l’onglet **[!UICONTROL Utilisateurs]**.

1. Cliquez sur **[!UICONTROL Ajouter un utilisateur]**.

   ![](assets/create_user_2.png)

1. Dans l’onglet **[!UICONTROL Détails de l’utilisateur]**, renseignez les détails de l’utilisateur, tels que l’adresse email, le prénom et le nom.

   ![](assets/create_user_3.png)

1. Dans l’onglet **[!UICONTROL Attribuer des produits]**, attribuez un ou plusieurs groupes de sécurité à votre utilisateur. Pour plus d’informations sur les groupes de sécurité, consultez cette [page](../../administration/using/managing-groups-and-users.md).

   Cliquez sur **[!UICONTROL Enregistrer]** lorsque vous avez terminé la configuration.

   ![](assets/create_user_4.png)

Votre utilisateur est maintenant créé et doit recevoir un email le redirigeant vers la fenêtre suivante, où il doit définir un mot de passe puis accepter le contrat d’utilisation. Cet utilisateur pourra alors se connecter à votre instance Adobe Campaign Standard.

![](assets/create_user_5.png)

Lorsque vous vous connectez à votre instance, cet utilisateur est synchronisé avec Adobe Campaign Standard.

Vous pourrez ensuite vérifier si votre utilisateur a été correctement synchronisé avec Adobe Campaign :

1. Dans le menu avancé **[!UICONTROL Administration > Utilisateurs &amp; sécurité > Utilisateurs]**, sélectionnez l’utilisateur créé précédemment.

1. Au besoin, mettez à jour les paramètres **[!UICONTROL Mobile]**, **[!UICONTROL Fuseau horaire]** ou **[!UICONTROL Paramètres régionaux]**.

1. Vérifiez le groupe de sécurité de l’utilisateur. Vous pouvez constater ici que le groupe de sécurité **[!UICONTROL Administrateurs]** a été attribué à l’utilisateur.

   >[!NOTE]
   >
   >Les groupes de sécurité peuvent uniquement être supprimés ou ajoutés à un utilisateur dans l’Admin Console.

   ![](assets/create_user_6.png)

1. Cochez la case **[!UICONTROL Compte désactivé]** si vous souhaitez désactiver cet utilisateur.

1. Dans le champ **[!UICONTROL Zone de connexion autorisée]**, sélectionnez la manière dont votre utilisateur se connecte à cette instance, par exemple réseau interne ou VPN.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Votre utilisateur peut maintenant utiliser Adobe Campaign Standard.

## Tutoriel vidéo {#video}

Cette vidéo montre comment gérer les droits d’accès des utilisateurs.

>[!VIDEO](https://video.tv.adobe.com/v/24671?quality=12)

D’autres vidéos pratiques sur Campaign Standard sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=fr).
