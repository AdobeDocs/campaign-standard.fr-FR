---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 9a57517f308c5394012a92622d62d5e900fb3955
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 29%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 22.2 - Juin 2022 {#rn-2022}

**Améliorations**

* **Adobe Notification Service** - Campaign est fourni avec Adobe Notification Service qui permet aux solutions Experience Cloud d’alerter les utilisateurs sur les activités qui sont importantes pour eux dans l’ensemble de l’Experience Cloud. À compter de la version 2.2, l’expérience utilisateur a été améliorée : les notifications sont hiérarchisées et les notifications générées par un produit sont séparées des annonces d’état d’Adobe. De plus, lorsque la notification fait référence à un workflow spécifique, vous pouvez désormais accéder directement au workflow correspondant à partir de l&#39;email ou de la notification intégrée au produit.  Pour plus d’informations sur les notifications d’Adobe Campaign, voir [Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Démarrage retardé du workflow** - Vous pouvez maintenant retarder l&#39;exécution de vos workflows pour éviter toute surcharge. Activé par Adobe par le biais d’une option dédiée, cette barrière de sécurité assure un délai de démarrage entre les workflows. Les options de la fonctionnalité définissent le nombre de workflows pouvant s’exécuter simultanément et le délai (en secondes) entre eux.


**Mise à niveau de sécurité**

* Cette version est fournie avec une activité de mise à niveau de sécurité pour atténuer la vulnérabilité Apache et rendre votre environnement d’instance plus sécurisé. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-classic/using/technotes/technote-migration/acc-apache-upgrade.html){target=&quot;_blank&quot;}.

