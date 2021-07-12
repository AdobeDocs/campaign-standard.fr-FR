---
solution: Campaign Standard
product: campaign
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Vue d'ensemble
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 100%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).


## Version 21.2 - Juin 2021 {#release-21-2---june-2021}

**Améliorations**

* Lors de la conception d&#39;une landing page, vous pouvez désormais ajouter une case à cocher obligatoire que les profils doivent sélectionner avant d&#39;envoyer le formulaire.

* Pour l&#39;intégration des Triggers, le message d&#39;erreur affiché en l&#39;absence de données de réconciliation entrant dans la payload du déclencheur a été amélioré : &quot;Données d&#39;alias manquantes dans la payload&quot;.

* Les performances pour récupérer les notifications push de la file d&#39;attente ont été améliorées.

**Autres changements**

* Le mécanisme de signature d&#39;URL pour les liens de suivi a été désactivé afin d&#39;éviter qu&#39;un problème ne bloque incorrectement certains liens de suivi signés valides après avoir été modifiés par des outils de sécurité tiers.

* Dans les diffusions à plusieurs variantes, les utilisateurs ne peuvent plus créer de copies de la langue si la variante par défaut a été supprimée. Un message s&#39;affiche maintenant lors de la création de la copie de la langue. (CAMP-48235)

* Le processus de suppression de profil en deux étapes (obsolète à partir de la version 19.4 de Campaign) est désormais désactivé par défaut. Auparavant, il devait être désactivé manuellement à partir de l&#39;interface de Campaign avant d&#39;utiliser Privacy Core Service. Si vous ne le faites pas, les demandes de suppression restent en attente et ne terminent pas.

* Une nouvelle fonction d&#39;agrégat &#39;StringAgg&#39; a été introduite pour concaténer les valeurs d&#39;une colonne de type chaîne. (CAMP-47077)

* Dans les rapports dynamiques, le segment **Exclure le BAT** a été supprimé. (CAMP-46161)

* Un nouveau message d&#39;avertissement a été ajouté pour informer l&#39;utilisateur qu&#39;un certificat iOS est téléchargé sans la valeur platformPrincipal dans l&#39;application Campaign.

* La taille maximale d&#39;un e-mail est désormais définie sur 100 Mo par défaut. Cette limite permet d&#39;éviter toute erreur qui pourrait augmenter indéfiniment la taille d&#39;un e-mail, ce qui peut entraîner un blocage du système. (CAMP-47445)

* L&#39;intégration d&#39;Asset Core Service avec le concepteur d&#39;e-mails peut désormais être utilisée par les utilisateurs standard.

* Un nouveau message a été ajouté pour confirmer la réussite de la migration d&#39;une application push v4 vers une application push v5.

* Lors de la création de jetons JSONWeb pour l&#39;authentification auprès de l&#39;API Campaign Standard, les profils de produit sont désormais **considérés**. Cela signifie que les entités organisationnelles et les rôles attribués au groupe de sécurité (qui correspond au profil de produit sur AdobeIO) seront appliqués au compte technique IMS nécessaire pour les appels de l&#39;API REST de Campaign Standard. (CAMP-47479)


**Correctifs**

* Correction d&#39;un problème qui empêchait l&#39;application de l&#39;option d&#39;expiration du tableau des logs de traitement par lot (**xtkjoblog**). Cela empêchait la purge correcte du tableau.

* Correction d&#39;un problème qui empêchait de modifier l&#39;ordre des filtres dans une activité de workflow **Segmentation**. (CAMP-48357)

* Correction d&#39;une régression de la version 20.4 qui entraînait l&#39;échec des diffusions avec une erreur de valeur nulle. (CAMP-48591)

* Correction d&#39;un problème qui empêchait l&#39;envoi d&#39;un rapport par le biais du menu **Partager** > **Envoyer le rapport maintenant** ou **Envoyer le rapport selon le calendrier**. (CAMP-47798)

* Correction d&#39;une régression qui pouvait entraîner des taux d&#39;ouverture incorrects pour Gmail en raison du filtrage des événements de tracking reçus de comptes Gmail. (CAMP-46504)

* Correction de divers problèmes provoquant des incohérences de données entre les rapports dans Adobe Campaign Standard et les rapports dans Adobe Analytics. (CAMP-47671, CAMP-47296)

* Correction d&#39;un problème qui empêchait l&#39;accès aux logs de diffusion après l&#39;échec de la préparation. (CAMP-48296)

* Correction d&#39;un problème qui entraînait l&#39;affichage d&#39;un message d&#39;erreur lors de la tentative de modification, de suppression ou d&#39;envoi d&#39;un rapport personnalisé. (CAMP-47789, CAMP-47798)

* Correction d&#39;un problème en raison duquel les appels d&#39;API échouaient lors de la création d&#39;une ressource personnalisée et de l&#39;activation de l&#39;option **Ne pas synchroniser**. (CAMP-48014)

* Correction d&#39;un problème en raison duquel les ressources personnalisées avec l&#39;option **Ne pas synchroniser** activée pouvaient référencer un schéma qui avait été réinitialisé ou supprimé. Ce problème provoquait une erreur lors de la publication des ressources personnalisées.

* Correction d&#39;un problème lié aux désinscriptions des SMS lors de l&#39;utilisation de plusieurs numéros courts sur le même compte externe.

* Correction d&#39;un problème qui empêchait l&#39;accès à un nouveau critère d&#39;alerte de diffusion (&quot;la ressource à laquelle vous essayez d&#39;accéder est inatteignable&quot;) après la publication de la base de données. (CAMP-48221)

* Correction d&#39;un problème en raison duquel les logs de tracking manquaient dans certains cas. Un nouveau workflow technique a été ajouté (**trackingLogRecovery**) pour restaurer ces logs de tracking perdus et ne doit être utilisé que par les personnes internes à Adobe.

* Correction d&#39;un problème en raison duquel aucune donnée de diffusion ne s&#39;affichait dans les rapports dynamiques. Les rapports étaient définis sur 0. (CAMP-47480)

* Correction d&#39;un problème qui empêchait le client HTTP JavaScript du serveur de se connecter à une URL externe.

* Correction d&#39;un problème qui réinitialisait une activité de **Requête incrémentale** après avoir modifié le nom interne du workflow. Cela se produisait lorsqu&#39;un champ de date était utilisé comme mode incrémental. (CAMP-47674)

* Correction d&#39;un problème qui empêchait l&#39;affichage de la miniature de prévisualisation dans la synthèse de la diffusion, lors de la création d&#39;un e-mail multilingue avec l&#39;intégration Adobe Experience Manager. Ce problème se produisait lors de l&#39;utilisation du bouton **Création de la copie de la langue** pour créer les variantes d&#39;e-mail. (CAMP-47810)

* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;accéder à la diffusion parente à partir de la diffusion enfant e-mail ou SMS. (CAMP-47986)

* Correction d&#39;un problème qui entraînait une consommation excessive de processeur et de mémoire lors de l&#39;envoi de messages transactionnels via l&#39;API REST avec un événement personnalisé manquant. (CAMP-47147)

* Correction d&#39;une erreur liée à l&#39;API des messages transactionnels qui empêchait parfois l&#39;envoi de messages en temps réel.

* Correction d&#39;un problème en raison duquel les rapports n&#39;étaient pas reçus après l&#39;utilisation de l&#39;option **Envoyer le rapport selon le calendrier**. (CAMP-48583)

* Correction d&#39;un problème en raison duquel les rapports reçus après l&#39;utilisation de l&#39;option **Envoyer le rapport maintenant** étaient incomplets et certaines données étaient manquantes. (CAMP-48583)

* Correction d&#39;un problème lié à l&#39;option **Envoyer le rapport selon le calendrier** dans les rapports dynamiques où le workflow intégré **Partage instantané des rapports** (reportSendingNow) ne pouvait pas générer de rapports. (CAMP-47786)

* Correction d&#39;un problème lié au concepteur d&#39;e-mails en raison duquel les dimensions d&#39;une image étaient réduites lors du téléchargement d&#39;une image. (CAMP-47017)

* Correction d&#39;un problème qui empêchait l&#39;affichage de tous les modèles Experience Manager disponibles lors de la création d&#39;une diffusion. (CAMP-48132)

* Correction d&#39;une erreur qui empêchait le lien Campagne de la page Résumé d&#39;une diffusion envoyée de rediriger les utilisateurs vers la campagne associée. (CAMP-48012)

* Correction d&#39;un problème dans le concepteur d&#39;e-mails en raison duquel l&#39;intégration d&#39;Asset Core Service échouait toujours lors de la sélection d&#39;une ressource. (CAMP-47446)

* Correction d&#39;un problème qui bloquait certaines diffusions de Journey Orchestration en raison de la non-prise en charge de la date et de l&#39;heure avec une valeur exacte (c&#39;est-à-dire se terminant par 00) envoyés par les événements de Journey Orchestration.
