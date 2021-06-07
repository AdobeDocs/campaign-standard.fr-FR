---
solution: Campaign Standard
product: campaign
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Vue d’ensemble
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: e492009166ba94cdd27613f2391229179ba9f8a4
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 6%

---

# Dernière version{#latest-release}

## Version 21.2 - Juin 2021 {#release-21-2---june-2021}

Les nouvelles fonctionnalités, améliorations et correctifs inclus dans la prochaine version du Campaign Standard sont répertoriés ci-dessous.

**Améliorations**

* Lors de la conception d’une landing page, vous pouvez désormais ajouter une case à cocher obligatoire que les profils doivent sélectionner avant d’envoyer le formulaire. Pour plus d’informations, consultez la [documentation détaillée](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Pour l&#39;intégration des Triggers, le message d&#39;erreur affiché en l&#39;absence de données de réconciliation entrant dans la payload du déclencheur a été amélioré : &quot;Données d’alias manquantes dans la payload&quot;.

* Les performances pour récupérer les notifications push de la file d’attente ont été améliorées.

**Autres changements**

* Le mécanisme de signature d’URL pour les liens de suivi a été désactivé afin d’éviter qu’un problème ne bloque incorrectement certains liens de suivi signés valides après avoir été modifiés par des outils de sécurité tiers.

* Dans les diffusions à plusieurs variantes, les utilisateurs ne peuvent plus créer de copies de langue si la variante par défaut a été supprimée. Un message s’affiche maintenant lors de la création de la copie de langue. (CAMP-48235)

* Le processus de suppression de profil en deux étapes (obsolète à partir de la version 19.4 de Campaign) est désormais désactivé par défaut. Auparavant, il devait être désactivé manuellement à partir de l’interface de Campaign avant d’utiliser Privacy Core Service. Si vous ne le faites pas, les demandes de suppression restent en attente sans avoir terminé.

* Une nouvelle fonction d&#39;agrégat &#39;StringAgg&#39; a été introduite pour concaténer les valeurs d&#39;une colonne de type chaîne. (CAMP-47077) [En savoir plus](../../automating/using/list-of-functions.md#aggregates)

* Dans les rapports dynamiques, le segment **Exclure le bon à tirer** a été supprimé. (CAMP-46161)

* Un nouveau message d’avertissement a été ajouté pour informer l’utilisateur qu’un certificat iOS est téléchargé sans la valeur platformPrincipal dans l’application Campaign.

* La taille maximale d’un email est désormais définie sur 100 Mo par défaut. Cette limite permet d’éviter toute erreur qui pourrait augmenter indéfiniment la taille d’un email, ce qui peut entraîner un blocage du système. (CAMP-47445) [En savoir plus](../../sending/using/design-and-personalize.md#email-size)

* L’intégration du service principal Asset avec le Concepteur d’email peut désormais être utilisée par les utilisateurs standard.

* Un nouveau message a été ajouté pour confirmer la réussite de la migration d’une application push v4 vers une application push v5.

* Lors de la création de jetons JSONWeb pour l’authentification auprès de l’API du Campaign Standard, les profils de produit sont désormais **considérés**. Cela signifie que les entités organisationnelles et les rôles attribués au groupe de sécurité (qui correspond au profil de produit sur Adobe IO) seront appliqués au compte technique IMS nécessaire pour les appels de l’API REST du Campaign Standard. (CAMP-47479)

**Correctifs**

* Correction d’un problème qui empêchait l’application de l’option d’expiration de la table des logs de traitement par lot (**xtkjoblog**). Cela empêchait la purge correcte du tableau.

* Correction d’un problème qui empêchait de modifier l’ordre des filtres dans une activité de workflow **Segmentation**. (CAMP-48357)

* Correction d’une régression de la version 20.4 qui entraînait l’échec des diffusions avec une erreur de valeur nulle. (CAMP-48591)

* Correction d’un problème qui empêchait l’envoi d’un rapport par le biais du menu **Partager** > **Envoyer le rapport maintenant** ou **Envoyer le rapport selon le calendrier**. (CAMP-47798)

* Correction d&#39;une régression qui pouvait entraîner des taux d&#39;ouverture incorrects pour Gmail en raison du filtrage des événements de tracking reçus de comptes Gmail. (CAMP-46504)

* Correction de divers problèmes provoquant des incohérences de données entre les rapports dans Adobe Campaign Standard et les rapports dans Adobe Analytics. (CAMP-47671, CAMP-47296)

* Correction d’un problème qui empêchait l’accès aux logs de diffusion après l’échec de la préparation. (CAMP-48296)

* Correction d’un problème qui entraînait l’affichage d’un message d’erreur lors de la tentative de modification, de suppression ou d’envoi d’un rapport personnalisé. (CAMP-47789, CAMP-47798)

* Correction d’un problème en raison duquel les appels d’API échouaient lors de la création d’une ressource personnalisée et de l’activation de l’option **Ne pas synchroniser**. (CAMP-48014)

* Correction d’un problème en raison duquel les ressources personnalisées avec l’option **Ne pas synchroniser** activée pouvaient référencer un schéma qui avait été réinitialisé ou supprimé. Ce problème provoquait une erreur lors de la publication des ressources personnalisées.

* Correction d’un problème d’exclusion des SMS lors de l’utilisation de plusieurs codes courts sur le même compte externe.

* Correction d’un problème qui empêchait l’accès à un nouveau critère d’alerte de diffusion (&quot;la ressource à laquelle vous essayez d’accéder est inatteignable&quot;) après la publication de la base de données. (CAMP-48221)

* Correction d’un problème en raison duquel les logs de tracking manquaient dans certaines instances de Campaign avec les rapports dynamiques. Un nouveau [workflow technique](../../administration/using/technical-workflows.md) a été ajouté pour restaurer ces logs de tracking. (CAMP-47885)

* Correction d’un problème en raison duquel aucune donnée de diffusion ne s’affichait dans les rapports dynamiques. Les rapports étaient définis sur 0. (CAMP-47480)

* Correction d’un problème qui empêchait le client HTTP JavaScript du serveur de se connecter à une URL externe.

* Correction d’un problème qui réinitialisait une activité de **Requête incrémentale** après avoir modifié le nom interne du workflow. Cela se produisait lorsqu’un champ de date était utilisé comme mode incrémentiel. (CAMP-47674)

* Correction d’un problème qui empêchait l’affichage de la miniature de prévisualisation dans la synthèse de la diffusion, lors de la création d’un email multilingue avec l’intégration Adobe Experience Manager. Ce problème se produisait lors de l’utilisation du bouton **Création d’une copie de langue** pour créer les variantes d’email. (CAMP-47810)

* Correction d’un problème qui empêchait les utilisateurs d’accéder à la diffusion parente à partir de la diffusion enfant Email ou SMS . (CAMP-47986)

* Correction d’un problème qui entraînait une consommation excessive de processeur et de mémoire lors de l’envoi de messages transactionnels via l’API REST avec un événement personnalisé manquant. (CAMP-47147)

* Correction d’une erreur liée à l’API des messages transactionnels qui empêchait parfois l’envoi de messages en temps réel.

* Correction d’un problème en raison duquel les rapports n’étaient pas reçus après l’utilisation de l’option **Envoyer le rapport selon le calendrier** . (CAMP-48583, CAMP-47786)

* Correction d’un problème en raison duquel les rapports reçus après l’utilisation de l’option **Envoyer le rapport maintenant** étaient incomplets et manquaient de données. (CAMP-48583)

* Correction d’un problème lié au Concepteur d’email en raison duquel les dimensions d’une image étaient réduites lors du téléchargement d’une image. (CAMP-47017)

* Correction d’un problème qui empêchait l’affichage de tous les modèles de Experience Manager disponibles lors de la création d’une diffusion. (CAMP-48132)

* Correction d&#39;une erreur qui empêchait le lien Campagne de la page Résumé d&#39;une diffusion envoyée de rediriger les utilisateurs vers la campagne associée. (CAMP-48012)

* Correction d’un problème dans le Concepteur d’email en raison duquel l’intégration d’Asset Core Service échouait toujours lors de la sélection d’une ressource. (CAMP-47446)

* Correction d’un problème qui bloquait certaines diffusions de Journey Orchestration en raison de la non-prise en charge des horodatages avec une valeur exacte (c’est-à-dire se terminant par 00) envoyés par les événements de Journey Orchestration.
