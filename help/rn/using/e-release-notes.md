---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign Standard.
>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 23.1 - Version du printemps/été 2023 {#apr-23}

### Améliorations {#e-rn-improvements}

* Le service de messagerie push a été modernisé afin d’optimiser la maintenance. (CAMP-47959)
* Le service de messagerie SMS a été modernisé afin d’offrir une meilleure stabilité. (CAMP-52217)
* La clé en main **Workflow de création de rapports d’enrichissement** a été ajouté. Après l&#39;import d&#39;un mapping de ciblage d&#39;une instance vers une autre, exécutez simplement le workflow pour importer les entrées d&#39;enrichissement de reporting correspondantes. (CAMP-52452)

### Correctifs {#e-rn-patches}

* Correction d’un problème qui entraînait une erreur de délai d’expiration lors de l’affichage de la variable **Hot click** rapport. (CAMP-51582)
* Correction d’un problème qui empêchait l’utilisation de l’intégration avec la variable **Places** service. (CAMP-51923)
* Correction d’un problème qui empêchait le bon fonctionnement du planificateur de workflow. (CAMP-52003)
* Correction d’un problème qui empêchait l’affichage des détails de la ventilation lors de l’affichage de la version PDF d’un rapport dynamique personnalisé avec un grand volume de données. (CAMP-52178)
* Correction d’un problème qui entraînait l’affichage d’une erreur lors de l’accès aux rapports. (CAMP-52500)
* Correction d’un problème qui appliquait incorrectement la variable **Limiter les instances MTA pour ce compte** Paramètre du connecteur SMS à tous les canaux au lieu de s’appliquer uniquement aux SMS. (CAMP-52640)
