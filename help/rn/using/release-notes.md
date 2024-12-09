---
title: Dernières notes de mise à jour
description: Cette page détaille le contenu de la dernière version de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 76%

---


# Dernières notes de mise à jour {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Notes de mise à jour anticipées {#e-new-release}

Cette section décrit les améliorations et modifications incluses dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
>Ce contenu est sujet à des modifications sans préavis jusqu’à la date de mise à niveau des environnements d’évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

### Version 25.1 - Version d’hiver 2025 {#winter-25}

#### Correctifs de sécurité {#winter-25-security}

* Cette version apporte des correctifs de sécurité.
* Cette version est fournie avec la mise à niveau de sécurité suivante : Apache Tomcat a été mis à niveau vers la version 10.1.3.

#### Autres correctifs {#winter-25-fixes}

* Correction d’un problème de duplication dans les modèles (CAMP-56340)
* Correction d’une régression de suivi lors de l’utilisation d’URL dynamiques dans des modèles Adobe Experience Manager (CAMP-51932)
* Correction d’un problème de performances sur le processus de facturation (CAMP-56796)
* Correction d’un problème de codage des HTMLS avec le caractère `>` sur les pages web JSSP (CAMP-56497).
* Correction d’un problème dans les rapports dynamiques lors de l’utilisation de l’option **Afficher sur les lignes sélectionnées** (CAMP-55895)


## Version 24.2 - Version d’été 2024 (LA) {#summer-24}

### Amélioration {#summer-24-rn-improvements}

**Migration vers les informations d’identification OAuth serveur à serveur**

À compter de cette version, les informations d’identification du compte de service (JWT) étant abandonnées par Adobe, les intégrations sortantes de Campaign aux solutions et applications d’Adobe dépendent désormais des informations d’identification OAuth serveur à serveur. Adobe effectuera la migration JWT vers OAuth pour vos intégrations sortantes, telles que l’intégration Campaign-Analytics ou Triggers Experience Cloud.

Si vous avez implémenté des intégrations entrantes avec Campaign et si vous utilisez des [API Campaign](../../api/using/get-started-apis.md), vous devez migrer votre compte technique comme indiqué dans [cette documentation](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Les informations d’identification de compte de service (JWT) existantes continueront à fonctionner jusqu’au **27 janvier 2025**.

### Correctifs {#summer-24-rn-fixes}

* Correction d’un problème en raison duquel le planificateur de workflow démarrait avant l’heure planifiée. (CAMP-55412)
* Correction d’un problème qui provoquait une erreur lors de la duplication de champs personnalisés dans des notifications push transactionnelles. (CAMP-54459)
* Correction de problèmes qui affectaient la facilité d’utilisation du planificateur d’heure et de date pour la messagerie in-app. (CAMP-54495)
* Correction d’un problème en raison duquel le suivi ne fonctionnait pas lors de l’utilisation de la fonctionnalité Alias de suivi personnalisé et le lien complet était dynamique. (CAMP-56044)
* Correction d’un problème en raison duquel un nombre limité de modèles s’affichaient lors de l’utilisation de la recherche pour trouver des modèles spécifiques. (CAMP-55273)
* Ajout des langues suivantes à la liste déroulante des préférences linguistiques : en_kz (anglais - Kazakhstan) et en_ua (anglais - Ukraine). (CAMP-55336)
* Correction d’un problème en raison duquel les boutons d’ajustement temporel ne fonctionnaient pas dans les paramètres du planificateur. (CAMP-53602)
* Correction de plusieurs problèmes de l’interface d’utilisation concernant la barre d’ajustement de l’heure dans les paramètres du planificateur. (CAMP-55291)
