---
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: f9bd5901d68c09ba20d5d48d263f4818c2e1e86a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 16%

---


# Dernière version{#latest-release}

![Panneau de contrôle](assets/do-not-localize/cp-icon.png) **Nouvelle version du panneau de contrôle**. [En savoir plus](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=fr){target="_blank"}.

## Version 23.1 - Version du printemps/été 2023 {#apr-23}

### Améliorations {#e-rn-improvements}

* Le service de messagerie push a été modernisé afin d’améliorer la prise en charge. (CAMP-47959)
* Le service de messagerie SMS a été amélioré afin d’offrir une meilleure stabilité. (CAMP-52217)
* Adobe a apporté de nombreux correctifs d’accessibilité afin d’améliorer la facilité d’utilisation globale de l’application. Voici quelques exemples d’améliorations de l’accessibilité :
   * L’accessibilité clavier de l’interface a été optimisée dans de nombreux écrans.
   * L’application a été améliorée pour les utilisateurs d’écran tactile.
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
