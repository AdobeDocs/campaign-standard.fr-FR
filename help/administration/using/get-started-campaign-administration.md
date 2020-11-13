---
title: Prise en main de l’administration de Campaign Standard
description: Découvrez la gestion des utilisateurs et des autorisations, les conseils de surveillance, les configurations spécifiques à un canal et les instructions de paramétrage d’application.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '655'
ht-degree: 100%

---


# Prise en main de l’administration de Campaign Standard{#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Administration</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Utilisateurs et sécurité</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuration des canaux</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Paramétrage de l’application</a></p></td></tr>
</table>

En tant que solution cloud, Adobe Campaign propose aux administrateurs plusieurs méthodes pour configurer l&#39;application. Bien que la configuration de l’infrastructure soit effectuée par Adobe, les administrateurs fonctionnels peuvent effectuer diverses opérations de configuration, détaillées ci-dessous.

>[!NOTE]
>
>Pour toute question ou demande concernant l&#39;implémentation et la configuration, contactez votre chargé de compte Adobe.

## Menu Administration {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Les différentes opérations d’administration d’Adobe Campaign sont effectuées à l’aide du menu **[!UICONTROL Administration]**, accessible après avoir cliqué sur le logo d’Adobe Campaign dans le coin supérieur gauche. Cette partie de l&#39;interface est uniquement accessible aux administrateurs fonctionnels de la plateforme.

Voici la liste des différents menus disponibles :

* [Utilisateurs &amp; sécurité](../../administration/using/about-access-management.md) : ce menu vous permet de gérer les accès à la plateforme (utilisateurs, rôles, groupes de sécurité, entités).
* [Canaux](../../administration/using/about-channel-configuration.md) : ce menu regroupe les paramètres techniques liés aux différents canaux de la plateforme (email, mobile) ainsi que la gestion des typologies et des quarantaines.
* [Paramétrage de l&#39;application](../../administration/using/external-accounts.md) : permet de configurer différents éléments de l&#39;application (comptes externes, options, workflows techniques).
* [Développement](../../developing/using/data-model-concepts.md) : ce menu vous permet de gérer vos ressources personnalisées et d&#39;accéder aux outils de diagnostic.
* [Paramétrage de l&#39;instance](../../administration/using/branding.md) : c&#39;est ici que vous définissez vos différentes marques et configurez leurs paramètres (logo, gestion du tracking, domaine d&#39;URL d&#39;accès aux landing pages, etc.).
* [Déploiement](../../automating/using/managing-packages.md) : ce menu regroupe l&#39;import et l&#39;export de packages.
* [Mesures des clients](../../audiences/using/active-profiles.md) : Adobe Campaign contient un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d’information ; il n’a aucune incidence directe sur la facturation.
* [Outils d&#39;accès à des informations personnelles](https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_GDPR.html) : ce menu vous permet de créer un accès RGPD, de supprimer les demandes et de tracker leur évolution.

## Utilisateurs et sécurité {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invitez les utilisateurs à accéder à l’application et à gérer les **groupes de sécurité**, c’est-à-dire des ensembles d’utilisateurs partageant les mêmes rôles et droits au sein de votre organisation. Par défaut, Adobe Campaign propose un ensemble de **rôles** qui permettent de définir les autorisations unitaires attribuées aux utilisateurs et groupes d’utilisateurs. Combinés avec les **entités organisationnelles**, les rôles donnent aux utilisateurs une vue filtrée de l’interface et définissent leur accès aux différentes fonctionnalités

Campaign standard permet également de surveiller les informations relatives à la sécurité. Vous pouvez récupérer des informations concernant les exports de données effectués par les utilisateurs via l’écran **[!UICONTROL Audits des exports]** et utiliser l’écran **[!UICONTROL Licences]** pour surveiller toutes les licences Campaign installées au sein de votre entreprise, ainsi que différentes informations telles que le numéro de build, la version publiée et les conditions d’utilisation.

En savoir plus :

* [Gestion des utilisateurs](../../administration/using/users-management.md)
* [Entités organisationnelles](../../administration/using/organizational-units.md)
* [Liste des rôles](../../administration/using/list-of-roles.md)
* [Gestion des groupes et des utilisateurs](../../administration/using/managing-groups-and-users.md)
* [Audit des logs d’export](../../administration/using/auditing-export-logs.md)
* [Licences](../../administration/using/licenses.md)

## Configuration des canaux {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Tous les canaux de communication d’Adobe Campaign doivent être correctement configurés pour pouvoir envoyer efficacement des messages. Le menu **[!UICONTROL Canal]** permet de gérer les paramètres techniques liés aux différents canaux.

Configurez les différents paramètres des **emails** : règles de traitement pour les bounces, les quarantaines, les propriétés des emails et les paramètres de routage, ainsi que les règles de typologie. Définissez les configurations et les propriétés du routage pour le canal **SMS**, ainsi que le codage et les formats SMS.

Configurez les **applications mobiles** pour envoyer des messages In-App et des notifications push à l’aide des SDK Adobe Experience Platform et configurez les **messages transactionnels** en créant et en configurant des événements.

En savoir plus :

* [A propos de la configuration des canaux](../../administration/using/about-channel-configuration.md)
* [Configuration du canal Email](../../administration/using/configuring-email-channel.md)
* [Configuration du canal SMS](../../administration/using/configuring-sms-channel.md)
* [Configuration d’une application mobile](../../administration/using/configuring-a-mobile-application.md)
* [Configuration des messages transactionnels](../../administration/using/configuring-transactional-messaging.md)

## Paramétrage de l’application {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard est fourni avec différents éléments d’application configurables en fonction de vos besoins.

Configurez les **comptes externes** qui servent à connecter Adobe Campaign à des serveurs externes. Accédez aux mappings de ciblage de Campaign Standard et surveillez votre plateforme à l’aide de **workflows techniques**.

Définissez une ou plusieurs **marques** pour votre organisation et configurez l’envoi de **notifications en temps réel** dans l’application en cas d’activités importantes du système.

En savoir plus :

* [A propos des paramètres de Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Comptes externes](../../administration/using/external-accounts.md)
* [Mappings de ciblage dans Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Workflows techniques](../../administration/using/technical-workflows.md)
* [Marques](../../administration/using/branding.md)
* [Envoi de notifications internes](../../administration/using/sending-internal-notifications.md)

## Autres ressources

* [Gestion des droits d’accès des utilisateurs (vidéo)](https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Documentation relative au Panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/control-panel-home.html)
