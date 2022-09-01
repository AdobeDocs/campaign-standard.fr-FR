---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 3f9adbf4e8c9066b1954a1443654d82ee7b53fea
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 20%

---


# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et les correctifs inclus dans la prochaine version du Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 22.3 - Septembre 2022  {#e-rn-2022}


### Amélioration{#e-rn-improvements}

**Accessibilité**

Campaign Standard 2.2.3 comprend des correctifs et améliorations d’accessibilité qui permettent aux utilisateurs de naviguer et de tirer le meilleur parti d’Adobe Campaign.

Ces fonctionnalités sont publiées dans Disponibilité limitée et déployées uniquement vers un ensemble de clients. Pour que ces améliorations soient activées dans votre ou vos environnements Campaign, contactez votre représentant Adobe.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Mise à jour de sécurité{#e-rn-security}

Cette version est fournie avec la mise à niveau de sécurité suivante : Apache Tomcat a été mis à niveau de la v7.0 vers la v8.0.

### Correctifs{#e-rn-fixes}

* Correction d’un problème lié aux rapports planifiés, qui étaient déclenchés une heure avant la planification. (CAMP-51502)
* Correction d’un problème sur les indicateurs de diffusion dans le tableau de bord Diffusion qui ne correspondait pas aux Envois (nms:broadLogRcp). (CAMP-51127)
* Correction d’un problème qui empêchait l’extension des ressources personnalisées avec ACS Connector (Prime Offering). (CAMP-51033)
* Amélioration du processus de publication des réponses aux demandes d’accès à des informations personnelles afin d’éviter tout retard. (CAMP-50613)