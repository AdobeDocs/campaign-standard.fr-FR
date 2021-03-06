---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 66aed3668dc0eb2041312dcbaebe7c36f54b13a5
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 22.2 - Juin 2022 {#rn-2022}

**Améliorations**

* **Adobe Notification Service** - Campaign est fourni avec Adobe Notification Service, qui permet aux solutions Experience Cloud de tenir les utilisateurs d’Experience Cloud informés des activités qui leur sont importantes. À compter de la version 22.2, l’expérience utilisateur a été améliorée : les notifications sont hiérarchisées et les notifications générées par les produits sont séparées des annonces de statut d’Adobe. En complément, lorsque la notification fait référence à un workflow spécifique, vous pouvez désormais accéder directement au workflow correspondant à partir de l’e-mail ou de la notification intégrée au produit.  Pour plus d’informations sur les notifications d’Adobe Campaign, voir [Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Optimisation du démarrage des workflow** - Adobe a ajouté une nouvelle fonctionnalité qui permet d’ajuster le nombre de workflows qui démarrent à peu près au même moment. Cela permet d’éviter les pics de processeur qui auraient pu entraîner des interruptions de service ou des temps d’arrêt. Adobe l’activerait après la version 22.2. Il n’y a pas d’autre élément d’action concernant le même client.

* **Accessibilité** - Adobe a apporté de nombreux correctifs d’accessibilité pour améliorer la facilité d’utilisation globale de l’application. Ces fonctionnalités sont actuellement activées uniquement pour un ensemble d’utilisateurs initiaux. Elles seront déployées vers tous les clients de la version ACS 2.2.3. Voici quelques exemples d’améliorations de l’accessibilité :

   * Assurance qu’il existe un indicateur de focus visible pour les éléments pouvant être ciblés sur chaque écran
   * Création de repères de page pour une navigation plus facile
   * Ajout du nom, du rôle, de la valeur et de l’état pour de nombreux contrôles
   * Correction des problèmes rencontrés avec l’ordre de focus dynamique sur les écrans principaux


**Correctifs**

* Correction d’un problème du workflow technique de facturation lié à une erreur de clé en double. (CAMP-51029)
* Ajout de la catégorie de navigateur Microsoft Edge manquante dans les rapports de tracking. Ils étaient auparavant catégorisés avec les ouvertures Microsoft Chrome. (CAMP-51165)
* Correction d’un problème lié aux demandes relatives au RGPD qui ne supprimaient pas les données des tables enfants. (CAMP-48276)
* Correction d’un problème dans le Concepteur d’e-mail en raison duquel la condition de visibilité d’un fragment n’était pas enregistrée, dans un modèle de message transactionnel. (CAMP-50338)
* Correction d’un problème dans les rapports de campagne en raison duquel la période n’était pas prise en compte. (CAMP-50991)
* Correction d&#39;une erreur qui provoquait l&#39;échec des e-mails planifiés : l&#39;analyse de la diffusion ne pouvait pas démarrer car la diffusion était toujours dans l&#39;état « Reprise en attente ». (CAMP-50302)
* Correction d’un problème dans le Concepteur d’e-mail lors de la prévisualisation d’un e-mail avec une substitution de profil. (CAMP-49312)
* Correction d’un problème lié à une valeur vide dans les énumérations personnalisées : lors de la création d&#39;une ressource personnalisée avec un champ qui est une énumération de texte et ne contient qu&#39;une seule valeur, cette valeur est maintenant définie par défaut, afin que vous puissiez créer une requête sur ce champ sous la forme d&#39;une requête simple. (CAMP-50606)
