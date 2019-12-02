---
title: Types d'utilisateurs
seo-title: Types d'utilisateurs
description: Types d'utilisateurs
seo-description: 'Les utilisateurs d''Adobe Campaign détiennent des rôles spécifiques. Découvrez les principaux types d''utilisateurs. '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: ht
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Types d'utilisateurs{#types-of-users}

Les administrateurs peuvent gérer les utilisateurs depuis la console d'administration. Les utilisateurs sont ensuite automatiquement synchronisés avec Adobe Campaign.

Pour plus d'informations à ce sujet, consultez la documentation relative à la [console d'administration](https://helpx.adobe.com/fr/enterprise/using/users.html).

Pour visualiser les utilisateurs dans Adobe Campaign, cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration &gt; Utilisateurs &amp; sécurité &gt; Utilisateurs]**.

Pour accéder à l'interface de gestion des utilisateurs à partir d'Adobe Campaign, cliquez sur **[!UICONTROL Administrer les utilisateurs]**.

![](assets/user_management_5.png)

Adobe Campaign permet d'affecter un ensemble de rôles à vos utilisateurs afin de définir la partie de l'interface à laquelle ils ont accès.

Les rôles spécifiques et les autorisations correspondantes sont présentés dans les sections suivantes : [Rôles](../../administration/using/list-of-roles.md) et [Autorisations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Cette répartition des utilisateurs n'est pas obligatoire ; elle représente uniquement l'utilisation la plus courante d'Adobe Campaign.

Cette section présente les principaux types d'utilisateurs Adobe Campaign. Elle ne décrit pas tous les rôles spécifiques pouvant être attribués à un utilisateur (démarrer les diffusions, effectuer des exports, préparer les diffusions, etc.). Pour en savoir plus sur les rôles, référez-vous aux pages [Liste des rôles](../../administration/using/list-of-roles.md) et [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md).

Elle est axée sur la répartition des différentes tâches entre trois types d'utilisateurs principaux dans Adobe Campaign :

* [Administrateurs fonctionnels](../../administration/using/types-of-users.md#functional-administrators) : il s'agit des utilisateurs les plus techniques parmi tous les utilisateurs de votre organisation.
* [Utilisateurs experts](../../administration/using/types-of-users.md#advanced-users) : ils configurent tous les éléments dont les marketeurs ont besoin pour envoyer et contrôler leurs diffusions.
* [Utilisateurs de base](../../administration/using/types-of-users.md#basic-users) : il s'agit des marketeurs qui personnalisent, diffusent et contrôlent leurs campagnes.

>[!NOTE]
>
>Les administrateurs fonctionnels diffèrent des administrateurs techniques Adobe. Les administrateurs techniques Adobe assument un rôle interne à Adobe qui ne peut être utilisé par aucun client. Ils gèrent la configuration et l'hébergement de l'instance, le contrôle et la supervision de l'infrastructure et la résolution des problèmes techniques.

**Rubriques connexes :**

* Vidéo [Gérer les permissions utilisateur](https://helpx.adobe.com/fr/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html)
* [Liste des rôles](../../administration/using/list-of-roles.md)
* [Liste des autorisations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Administrateurs fonctionnels {#functional-administrators}

Les administrateurs fonctionnels sont les utilisateurs pouvant accéder aux parties les plus techniques de l'interface. Ils détiennent le rôle **[!UICONTROL Administration]** et veillent à ce que la plate-forme soit configurée de sorte que les marketeurs puissent se concentrer exclusivement sur la diffusion de leurs campagnes.

Les administrateurs fonctionnels sont les seuls utilisateurs ayant accès au menu **[!UICONTROL Administration]** dans l'interface Adobe Campaign. Etant donné que ces utilisateurs doivent accéder à des ressources techniques, des rôles plus avancés doivent leur être attribués, tels que les rôles d'usine **[!UICONTROL Administration]** et **[!UICONTROL Datamodel]**. Ces rôles sont combinés dans le groupe de sécurité d'usine **[!UICONTROL Administrateurs]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu'ils peuvent effectuer :

* [Gérer les utilisateurs et les permissions](../../administration/using/about-access-management.md) : gérez les accès à la plate-forme (utilisateurs, rôles, groupes de sécurité, entités).
* [Configurer les différents canaux](../../administration/using/about-channel-configuration.md) : configurez les différents canaux de la plate-forme ainsi que la gestion des typologies et des quarantaines.
* [Configurer les paramètres généraux de l'application ](../../administration/using/external-accounts.md) : configurez les différents éléments de l'application (comptes externes, options, workflows techniques).
* [Développer de nouvelles fonctionnalités pour améliorer les fonctions d'usine](../../developing/using/data-model-concepts.md) : gérez vos ressources personnalisées et accédez aux outils de diagnostic.
* [Configurer les paramètres de l'instance](../../administration/using/branding.md) : définissez vos différentes marques et configurez leurs paramètres (logo, gestion du tracking, domaine d'URL d'accès aux landing pages, etc.).
* [Exporter et importer des packages de données](../../automating/using/managing-packages.md) : échangez des ressources entre différentes instances Adobe Campaign par le biais de fichiers structurés au format XML.
* [Exporter des logs](../../automating/using/exporting-logs.md) et [définir des modèles d'import](../../automating/using/defining-import-templates.md).

## Utilisateurs experts  {#advanced-users}

Les utilisateurs experts sont des utilisateurs marketing qui effectuent les tâches les plus techniques dans Adobe Campaign. Ils préconfigurent tous les éléments utilisés par les marketeurs pour envoyer et contrôler leurs diffusions.

Ce type d'utilisateur requiert des rôles plus généraux que les administrateurs fonctionnels, mais doit néanmoins être en mesure d'effectuer certaines opérations techniques. Pour cela, ils doivent se faire attribuer, par exemple, les rôles d'usine **[!UICONTROL Export]**, **[!UICONTROL Import générique]** ou **[!UICONTROL Workflow]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu'ils peuvent effectuer :

* [Créer et exécuter des workflows complexes de Data Management](../../automating/using/about-data-management-activities.md) : importez, enrichissez et transformez les données pour alimenter votre base de données ou exportez les données dont vous avez besoin dans des fichiers externes afin de les exploiter dans vos propres outils.
* [Gérer les modèles](../../start/using/about-templates.md) : gérez vos modèles pour préconfigurer certains paramètres de vos activités marketing selon vos besoins.
* [Créer des requêtes](../../automating/using/editing-queries.md#about-query-editor) et [gérer les audiences](../../audiences/using/about-audiences.md) : créez vos audiences manuellement à travers des requêtes ou automatiquement via des workflows dédiés.
* [Utiliser l'édition avancée d'expressions](../../automating/using/editing-queries.md#about-query-editor) : utilisez des fonctions avancées pour manipuler les valeurs utilisées afin de réaliser des requêtes spécifiques : manipulation de dates, de chaînes, de champs numériques, tris, etc.
* [Exporter des listes](../../automating/using/exporting-lists.md) et [importer des données à l'aide de modèles d'import existants](../../automating/using/importing-data-with-import-templates.md).

## Utilisateurs de base  {#basic-users}

Grâce à l'administrateur fonctionnel et aux utilisateurs experts, les marketeurs peuvent personnaliser, diffuser et contrôler leurs campagnes sans se soucier de la configuration technique. Pour cela, ils doivent se faire attribuer, par exemple, les rôles d'usine **[!UICONTROL Préparer des diffusions]**, **[!UICONTROL Workflow]** et **[!UICONTROL Démarrer des diffusions]**. Ces rôles sont combinés dans le groupe de sécurité d'usine **[!UICONTROL Utilisateurs standard]**. Voir à ce propos cette [section](../../administration/using/list-of-roles.md).

Voici les principales tâches qu'ils peuvent effectuer :

* [Gérer les programmes et campagnes](../../start/using/programs-and-campaigns.md) : créez des campagnes marketing incluant différents types d'activités (emails, SMS, notifications push, workflows, landing pages).
* Gérer les [profils](../../audiences/using/about-profiles.md) et les [profils de test](../../sending/using/managing-test-profiles-and-sending-proofs.md) : gérez les destinataires identifiés et les profils de test que vos diffusions cibleront. Ajoutez des informations comme le prénom, le nom, les coordonnées, les abonnements, les emails, etc.
* [Créer et envoyer des messages](../../sending/using/confirming-the-send.md) : créez votre message, sélectionnez l'audience, définissez le contenu du message et ses éléments de personnalisation, envoyez les bons à tirer puis le message final à votre audience.
* [Créer et publier des landing pages](../../channels/using/getting-started-with-landing-pages.md) : créez et gérez un ensemble de services que vous souhaitez proposer à vos clients, comme des formulaires d'inscription ou de désinscription.
* [Créer et exécuter des workflows d'opérations](../../automating/using/building-a-workflow.md) : automatisez les processus de campagne à l'aide de workflows.
* Contrôler les activités marketing par le biais des [rapports disponibles](../../reporting/using/defining-the-report-period.md).

