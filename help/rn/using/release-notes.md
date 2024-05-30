---
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# Dernière version{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Version 24.1 - Version d’hiver 2024 {#winter-24}

### Améliorations {#e-rn-improvements}

* **Notifications push Android** - Adobe Campaign Standard 24.1 utilise les API HTTP v1 pour envoyer des messages de notification push Android, afin d’assurer la compatibilité avec les modifications FCM à venir. Consultez [cette note technique](../../administration/using/push-technote.md) pour en savoir plus.

* **Notifications push iOS** - Adobe Campaign Standard 24.1 prend désormais en charge les certificats d’authentification p8 pour les notifications push iOS. Votre mise en œuvre doit être adaptée pour activer ces modifications. Consultez [cette note technique](../../administration/using/push-technote.md) pour en savoir plus.

**Liste-Unsubscribe en un clic** - à partir du 1er juin 2024, Google et Yahoo! exigeront que les expéditeurs et expéditrices se conforment à One-Click List-Unsubscribe. Campaign prend désormais en charge cette fonctionnalité prête à l’emploi. En savoir plus dans [cette section](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastructure** - La base de données Postgres a été mise à niveau de la version 11.22 vers la version 12.17.

* **Suivi CTA** - Lorsque les utilisateurs s’ouvrent et cliquent sur une URL personnalisée, l’URL personnalisée résolue est désormais suivie à la place de l’URL personnalisée codée. Cette modification n’est pas activée par défaut. Pour l’activer sur votre instance Campaign, contactez votre représentant d’Adobe.

* **Liste déroulante des champs de personnalisation** - Lors de la création de modèles de messages électroniques transactionnels dans Adobe Experience Manager, vous pouvez désormais sélectionner des champs de personnalisation dans une liste déroulante. Cette modification n’est pas activée par défaut. Pour l’activer sur votre instance Campaign, contactez votre représentant d’Adobe.

### Correctifs {#e-rn-fixes}

* Correction d’un problème qui empêchait le retrait de la quarantaine des mails rebonds au bout de 30 jours. (CAMP-52977)
* Correction d’un problème qui arrêtait le workflow Alertes de diffusion avec l’erreur suivante : `division by zero`. (CAMP-49786)

