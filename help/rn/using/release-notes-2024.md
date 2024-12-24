---
title: Notes de mise à jour 2024
description: Cette page répertorie toutes les versions 2024 d’Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
source-git-commit: f5e8b3f1a2c235094eedf32199ea792cfa891fcd
workflow-type: ht
source-wordcount: '246'
ht-degree: 100%

---

# Notes de mise à jour 2024 {#release-notes-2024}

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
