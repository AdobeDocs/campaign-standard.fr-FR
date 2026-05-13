---
title: Notes de mise à jour 2024
description: Cette page répertorie toutes les versions 2024 d’Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
TQID: https://experienceleague.adobe.com/L1RnV5WNdVWVn8oRUtFp4BDW-GzuP6xWZXpFYgupbQs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
  - id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 100%

---

# Notes de mise à jour 2024 {#release-notes-2024}


## Version 24.2 - Version été 2024 {#summer-24}

### Amélioration {#summer-24-rn-improvements}

**Migration vers les informations d’identification OAuth serveur à serveur**

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. Adobe effectuera la migration JWT vers OAuth pour vos intégrations sortantes, telles que l’intégration Campaign-Analytics ou Triggers Experience Cloud.

Si vous avez implémenté des intégrations entrantes pour Campaign, et si vous utilisez les [API Campaign](../../api/using/get-started-apis.md), vous devez migrer votre compte technique comme décrit dans [cette documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Les informations d’identification de compte de service (JWT) existantes continueront à fonctionner jusqu’au **27 janvier 2025**.

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
