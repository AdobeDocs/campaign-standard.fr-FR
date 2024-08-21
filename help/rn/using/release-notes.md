---
title: Dernières notes de mise à jour
description: Cette page détaille le contenu de la dernière version de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 0beb4934d1412c3f64d28106f9243673907629f3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Dernières notes de mise à jour {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

<!--
## Early release notes {#e-new-release}

This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).
-->

## Version 24.2 - Version été 2024 {#summer-24}

**Date de publication** : août 2024 (disponibilité limitée) - [En savoir plus](../../rn/using/release-planning.md).

### Amélioration {#summer-24-rn-improvements}

**Migration vers les informations d’identification OAuth serveur à serveur**

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. Adobe effectuera la migration JWT vers OAuth pour vos intégrations sortantes, telles que l’intégration Campaign-Analytics ou Triggers Experience Cloud.

Si vous avez implémenté des intégrations entrantes avec Campaign et si vous utilisez des [API Campaign](../../api/using/get-started-apis.md), vous devez migrer votre compte technique comme indiqué dans [cette documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Les informations d’identification de compte de service (JWT) existantes continueront à fonctionner jusqu’au **27 janvier 2025**.

### Correctifs {#summer-24-rn-fixes}

* Correction d’un problème en raison duquel le planificateur de workflow démarrait avant l’heure planifiée. (CAMP-55412)
* Correction d’un problème qui provoquait une erreur lors de la duplication de champs personnalisés dans des notifications push transactionnelles. (CAMP-54459)
* Correction de problèmes qui affectaient la facilité d’utilisation du planificateur d’heure et de date pour la messagerie in-app. (CAMP-54495)
* Correction d’un problème en raison duquel le suivi ne fonctionnait pas lors de l’utilisation de la fonctionnalité Alias de suivi personnalisé et le lien complet était dynamique. (CAMP-56044)
* Correction d’un problème en raison duquel un nombre limité de modèles s’affichaient lors de l’utilisation de la recherche pour trouver des modèles spécifiques. (CAMP-55273)
* Ajout des langues suivantes à la liste déroulante des préférences linguistiques : en_kz (anglais - Kazakhstan) et en_ua (anglais - Ukraine). (CAMP-55336)
* Correction d’un problème en raison duquel les boutons d’ajustement temporel ne fonctionnaient pas dans les paramètres du planificateur. (CAMP-53602)
* Correction de plusieurs problèmes de l’interface d’utilisation concernant la barre d’ajustement de l’heure dans les paramètres du planificateur. (CAMP-55291)

## Version 24.1 - Version d’hiver 2024 {#winter-24}

### Améliorations {#e-rn-improvements}

* **Notifications push Android** : Adobe Campaign Standard 24.1 utilise les API HTTP v1 pour envoyer des messages de notification push Android, afin d’assurer la compatibilité avec les modifications FCM à venir. Consultez [cette note technique](../../administration/using/push-technote.md) pour en savoir plus.

* **Notifications push iOS** : Adobe Campaign Standard 24.1 prend désormais en charge les certificats d’authentification p8 pour les notifications push iOS. Votre mise en œuvre doit être adaptée pour activer ces modifications. Consultez [cette note technique](../../administration/using/push-technote.md) pour en savoir plus.

* **One-Click List-Unsubscribe** : à compter du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à One-Click List-Unsubscribe. Campaign prend désormais en charge cette fonctionnalité prête à l’emploi. En savoir plus dans [cette section](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastructure** : la base de données Postgres a été mise à niveau de la version 11.22 vers la version 12.17.

* **Tracking CTA** : lorsque les personnes ouvrent une URL personnalisée et cliquent dessus, l’URL personnalisée résolue est désormais suivie à la place de l’URL personnalisée codée. Ce changement n’est pas activé par défaut. Pour l’activer sur votre instance Campaign, contactez votre représentant ou représentante Adobe.

* **Liste déroulante des champs de personnalisation** : lors de la création de modèles d’e-mails transactionnels dans Adobe Experience Manager, vous pouvez désormais sélectionner des champs de personnalisation dans une liste déroulante. Ce changement n’est pas activé par défaut. Pour l’activer sur votre instance Campaign, contactez votre représentant ou représentante Adobe.

### Correctifs {#e-rn-fixes}

* Correction d’un problème qui empêchait le retrait de la quarantaine des mails rebonds au bout de 30 jours. (CAMP-52977)
* Correction d’un problème qui arrêtait le workflow Alertes de diffusion avec l’erreur suivante : `division by zero`. (CAMP-49786)

