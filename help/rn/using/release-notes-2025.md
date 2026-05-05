---
title: Notes de mise à jour (2025)
description: Cette page répertorie toutes les versions d’Adobe Campaign Standard publiées en 2025.
feature: Overview
role: User
level: Beginner
exl-id: 9046db34-f610-4721-b6eb-92334149366d
source-git-commit: 4e39100c19fa7bd943b16e3ed87b8c2d82bdf814
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# Notes de mise à jour (2025) {#release-notes-2025}

## Version 25.2 - Version d’été 2025 {#summer-25}

### Correctifs de sécurité {#summer-25-security}

* Cette version contient des correctifs de sécurité.
* Cette version est fournie avec la mise à niveau de sécurité suivante : PostgreSQL 14.18, migration de CentOS vers Rocky pour les instances Azure.

### Autres correctifs {#summer-25-fixes}

* Amélioration de la gestion de l’épuisement de la séquence pour améliorer la fiabilité du système. (CAMP-57281)
* Mises à jour générales pour la stabilisation du produit. (CAMP-57339)
* Amélioration des rapports dynamiques pour une meilleure robustesse et une réduction des incohérences des données.(CAMP-58157)
* Correction d’un problème en raison duquel les menus déroulants n’affichaient pas correctement le retour à la ligne du texte. (CAMP-57360)
* Mise à jour de la fonctionnalité de création de rapports pour empêcher les utilisateurs et utilisatrices d’interroger les données datant de plus de 2 ans. (CAMP-59262)

## Version 25.1.2 {#25.1.2}

### Correctifs de sécurité {#25.1.2-security}

* Cette version contient des correctifs de sécurité.
* Cette version est fournie avec la mise à niveau de sécurité suivante : Apache Tomcat a été mis à niveau vers la version 10.1.36.

### Autres correctifs {#25.1.2-fixes}

* Correction d’un problème d’analyse des jetons qui pouvait empêcher les utilisateurs et utilisatrices de se connecter via IMS. (CAMP-57337)
* Le mécanisme de génération d’ID de séquence automatique a été amélioré pour optimiser la fiabilité du système. (CAMP-57281)

## Version 25.1 - Version d’hiver 2025 {#winter-25}

### Correctifs de sécurité {#winter-25-security}

* Cette version contient des correctifs de sécurité.
* Cette version est fournie avec la mise à niveau de sécurité suivante : Apache Tomcat a été mis à niveau vers la version v10.1.33.

### Autres correctifs {#winter-25-fixes}


* Correction de l’URL « Schéma de données » dans l’écran de résumé des abonnements (CAMP-56168, CAMP-56296)
* Correction d’un problème permettant de contourner les règles de fatigue lorsque l’option **Message à envoyer immédiatement** est utilisée (CAMP-56866, CAMP-57033)
* Correction d’un problème de doublons dans les modèles (CAMP-56340)
* Correction d’une régression du tracking lorsque des URL dynamiques étaient utilisées dans les modèles Adobe Experience Manager (CAMP-51932)
* Correction d’un problème de performances du processus de facturation (CAMP-56796)
* Correction d’un problème de codage HTML avec le caractère `>` sur les pages web JSSP (CAMP-56497)
* Correction d’un problème dans les rapports dynamiques lors de l’utilisation de l’option **Afficher sur les lignes sélectionnées** (CAMP-55895)
