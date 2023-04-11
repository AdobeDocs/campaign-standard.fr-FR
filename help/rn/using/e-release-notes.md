---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 21%

---


# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign Standard.
>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 23.1 - Version du printemps/été 2023 {#apr-23}

### Améliorations {#e-rn-improvements}

* Le service de messagerie push a été modernisé afin d’améliorer la prise en charge. (CAMP-47959)
* Le service de messagerie SMS a été amélioré afin d’offrir une meilleure stabilité. (CAMP-52217)
* Adobe a apporté de nombreux correctifs d’accessibilité afin d’améliorer la facilité d’utilisation globale de l’application. Voici quelques exemples d’améliorations de l’accessibilité :
   * L’accessibilité clavier de l’interface a été optimisée dans de nombreux écrans.
   * L’application a été ravie pour les utilisateurs d’écran tactile.
   * La couleur de plusieurs éléments de l’interface a été modifiée afin d’améliorer la visibilité.

### Autres changements  {#e-rn-changes}

* La clé en main **Workflow de création de rapports d’enrichissement** a été ajouté. Après l&#39;import d&#39;un mapping de ciblage d&#39;une instance vers une autre, exécutez simplement le workflow pour importer les entrées d&#39;enrichissement de reporting correspondantes. (CAMP-52452)

### Problèmes résolus{#e-rn-patches}

* Correction d’un problème qui entraînait une erreur de délai d’expiration lors de l’affichage de la variable **Hot click** rapport. (CAMP-51582)
* Correction d’un problème qui empêchait l’utilisation de l’intégration avec la variable **Places** service. (CAMP-51923)
* Correction d’un problème qui empêchait le bon fonctionnement du planificateur de workflow. (CAMP-52003)
* Correction d’un problème qui empêchait l’affichage des détails de la ventilation lors de l’affichage de la version PDF d’un rapport dynamique personnalisé avec un grand volume de données. (CAMP-52178)
* Correction d’un problème qui entraînait l’affichage d’une erreur lors de l’accès aux rapports. (CAMP-52500)
* Correction d’un problème qui appliquait incorrectement la variable **Limiter les instances MTA pour ce compte** Paramètre du connecteur SMS à tous les canaux au lieu de s’appliquer uniquement aux SMS. (CAMP-52640)
