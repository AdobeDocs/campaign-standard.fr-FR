---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 20a59e064afeb93a2a6260439b09790692971071
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 100%

---


# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 22.3 - Automne/hiver 2022 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}


**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.
-->

### Mise à jour de sécurité{#e-rn-security}

Cette version est fournie avec la mise à niveau de sécurité suivante : Apache Tomcat a été mis à niveau de la v7.0 vers la v8.0.

### Correctifs{#e-rn-fixes}

* Correction d’un problème lié aux rapports planifiés, qui étaient déclenchés une heure avant la planification. (CAMP-51502)
* Correction d’un problème sur les indicateurs de diffusion dans le tableau de bord Diffusion qui ne correspondait pas aux logs d’envois (nms:broadLogRcp). (CAMP-51127)
* Correction d’un problème qui empêchait l’extension des ressources personnalisées avec ACS Connector (Prime Offering). (CAMP-51033)
* Amélioration du processus de publication des réponses aux demandes d’accès à des informations personnelles afin d’éviter tout retard. (CAMP-50613)