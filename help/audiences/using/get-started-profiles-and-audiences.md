---
title: Prise en main des profils et des audiences
description: Définissez des populations ciblées, sélectionnez des audiences, filtrez les destinataires, collectez des données et mettez à jour des profils.
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Profiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 100%

---

# Prise en main des profils et des audiences{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">Segmentation et ciblage</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">Autorisation et consentement</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">Respect de la confidentialité</a></p></td></tr>
</table>

Les profils client intégrés de Campaign permettent de tracker chaque interaction avec les clients sur tous les canaux dans une vue unique, et de diffuser ainsi des messages pertinents et personnalisés à vos clients.

Segmentez votre base de données en différentes audiences pour optimiser la cible de vos campagnes marketing.

Gérez les autorisations et le consentement des clients à l’aide de services et de landing pages pour configurer des mécanismes simples d’opt-in et d&#39;opt-out.

## Segmentation et ciblage {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

Lorsque vous créez des campagnes ou des messages, vous pouvez spécifier la cible des diffusions en sélectionnant des contacts dans la base de données de Campaign, à l’aide de critères simples ou avancés, ou en sélectionnant des audiences.

Identifiez les clients plus efficacement sur tous les canaux à l’aide des **profils client intégrés**, **des segments personnalisés** et des **populations témoins**. Lorsque vous connaissez vos clients, leurs centres d’intérêt, leurs données démographiques et leurs préférences en matière de canaux, vous pouvez créer plus facilement des expériences personnalisées qui seront remarquées.

Adobe Campaign crée des profils client complets en temps réel, ce qui vous permet de diffuser des offres plus pertinentes et personnalisées à mesure que les préférences de vos clients changent. De plus, Adobe Campaign intègre des fonctionnalités avancées d’analyse, de gestion des données et de ciblage pour créer des audiences.

**Les profils sont des contacts individuels stockés dans la base de données.** Chaque profil correspond à une entrée dans la base de données qui contient les informations nécessaires pour faire l&#39;objet de ciblage, de qualification et de tracking individuel : Adobe Campaign peut tracker chaque interaction sur les canaux on-line et off-line, et les fusionner en un seul profil.

**Les audiences sont des listes de profils créées selon un critère spécifique ou un ensemble de critères.** Grâce aux workflows et au requêteur, vous avez la possibilité de construire les audiences qui seront ciblées par vos campagnes marketing, selon les informations dont vous disposez sur elles, leurs activités et leur historique marketing. Vous pouvez ainsi filtrer les profils d’inscrits, échantillonner ou créer des audiences cibles sur un nombre illimité de critères.

En savoir plus :

* [À propos des profils](../../audiences/using/about-profiles.md)
* [Profils actifs](../../audiences/using/active-profiles.md)
* [Gestion des profils de test](../../audiences/using/managing-test-profiles.md)
* [Enrichissement de la base de données Campaign](../../audiences/using/enriching-campaign-database.md)
* [À propos des audiences](../../audiences/using/about-audiences.md)
* [Sélectionner une audience dans un message](../../audiences/using/selecting-an-audience-in-a-message.md)
* [Ajouter une population témoin](../../sending/using/control-group.md)

## Autorisation et consentement {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

Avant de commencer à envoyer des messages à un contact, vous devez obtenir son autorisation. Sinon, vos emails peuvent être marqués comme spam, ce qui peut avoir un impact sur la délivrabilité de votre plateforme. Pour veiller à créer une base de données de profils fiables, obtenez tout d’abord cette autorisation.

Avec Campaign, il est recommandé d’utiliser les **mécanismes simples d’opt-in et d’opt-out** par le biais des [services](../../audiences/using/creating-a-service.md) et des [landing pages](../../channels/using/getting-started-with-landing-pages.md) afin de mettre à jour les informations des contacts et de développer votre base de données.

Fournir des **liens de désabonnement** dans vos messages permet l’ajout de profils à la liste bloquée, si nécessaire, et améliore donc la délivrabilité de votre plateforme. Pour plus d’informations sur la gestion des listes bloquées, voir la section [À propos des processus d’opt-in et d’opt-out dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!IMPORTANT]
>
>Vous devez respecter la [politique d’utilisation acceptable d’Adobe Campaign](https://www.adobe.com/fr/legal/terms/aup.html).

En savoir plus :

* [À propos des abonnements](../../audiences/using/about-subscriptions.md)
* [À propos des processus d&#39;opt-in et d&#39;opt-out dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Respect de la confidentialité {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign propose un ensemble d’outils pour vous aider à appliquer les mesures relatives au **respect de la confidentialité** dans le cadre des règlements RGPD, CCPA et d’autres lois concernant la protection des données.

Pour en savoir plus, consultez [cet article](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy.html) sur la gestion de la confidentialité et les fonctionnalités que nous offrons pour gérer le droit d’accès, le droit à l’oubli, le consentement, la rétention des données et les rôles utilisateur.

[Cette section](../../start/using/privacy.md) aborde la confidentialité et le consentement dans Campaign et comment les gérer. Vous y trouverez également les bonnes pratiques les plus efficaces pour garantir la conformité aux obligations légales en utilisant notre service.

## Autres ressources

* [Ingérer des audiences Adobe Experience Platform dans Campaign](../../integrating/using/ingest-aep-data.md)
* [Utilisation de Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Audiences partagées Adobe](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [Utilisation des workflows pour l’import de profils](../../automating/using/creating-import-workflow-templates.md)
* [Vidéos sur les profils et les audiences](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html?lang=fr)
