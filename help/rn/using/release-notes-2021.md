---
title: Notes de mise à jour 2021
description: Cette page répertorie toutes les versions 2021 d'Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '3509'
ht-degree: 100%

---

# Notes de mise à jour 2021{#release-notes-2021}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=fr) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

## Version 21.2 - Juin 2021 {#release-21-2---june-2021}

Les nouvelles fonctionnalités, améliorations et corrections incluses dans la prochaine version de Campaign Standard sont répertoriées ci-dessous. Les nouvelles fonctionnalités, améliorations et corrections incluses dans cette version de Campaign Standard sont répertoriées ci-dessous.

**Améliorations**

* Lors de la conception d&#39;une landing page, vous pouvez désormais ajouter une case à cocher obligatoire que les profils doivent sélectionner avant d&#39;envoyer le formulaire. Pour plus d&#39;informations, consultez la [documentation détaillée](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Pour l&#39;intégration des Triggers, le message d&#39;erreur affiché en l&#39;absence de données de réconciliation entrant dans la payload du déclencheur a été amélioré : &quot;Données d&#39;alias manquantes dans la payload&quot;.

* Les performances pour récupérer les notifications push de la file d&#39;attente ont été améliorées.

**Autres changements**

* Le mécanisme de signature d&#39;URL pour les liens de suivi a été désactivé afin d&#39;éviter qu&#39;un problème ne bloque incorrectement certains liens de suivi signés valides après avoir été modifiés par des outils de sécurité tiers.

* Dans les diffusions à plusieurs variantes, les utilisateurs ne peuvent plus créer de copies de la langue si la variante par défaut a été supprimée. Un message s&#39;affiche maintenant lors de la création de la copie de la langue. (CAMP-48235)

* Le processus de suppression de profil en deux étapes (obsolète à partir de la version 19.4 de Campaign) est désormais désactivé par défaut. Auparavant, il devait être désactivé manuellement à partir de l&#39;interface de Campaign avant d&#39;utiliser Privacy Core Service. Si vous ne le faites pas, les demandes de suppression restent en attente et ne terminent pas.

* Dans les rapports dynamiques, le segment **Exclure le BAT** a été supprimé. (CAMP-46161)

* Un nouveau message d&#39;avertissement a été ajouté pour informer l&#39;utilisateur qu&#39;un certificat iOS est téléchargé sans la valeur platformPrincipal dans l&#39;application Campaign.

* La taille maximale d&#39;un e-mail est désormais définie sur 100 Mo par défaut. Cette limite permet d&#39;éviter toute erreur qui pourrait augmenter indéfiniment la taille d&#39;un e-mail, ce qui peut entraîner un blocage du système. (CAMP-47445) [En savoir plus](../../sending/using/design-and-personalize.md#email-size)

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

* Correction d&#39;un problème en raison duquel les logs de tracking étaient manquants dans certaines instances de Campaign avec les rapports dynamiques. Un nouveau [workflow technique](../../administration/using/technical-workflows.md) a été ajouté pour restaurer ces logs de tracking. (CAMP-47885)

* Correction d&#39;un problème en raison duquel aucune donnée de diffusion ne s&#39;affichait dans les rapports dynamiques. Les rapports étaient définis sur 0. (CAMP-47480)

* Correction d&#39;un problème qui empêchait le client HTTP JavaScript du serveur de se connecter à une URL externe.

* Correction d&#39;un problème qui réinitialisait une activité de **Requête incrémentale** après avoir modifié le nom interne du workflow. Cela se produisait lorsqu&#39;un champ de date était utilisé comme mode incrémental. (CAMP-47674)

* Correction d&#39;un problème qui empêchait l&#39;affichage de la miniature de prévisualisation dans la synthèse de la diffusion, lors de la création d&#39;un e-mail multilingue avec l&#39;intégration Adobe Experience Manager. Ce problème se produisait lors de l&#39;utilisation du bouton **Création de la copie de la langue** pour créer les variantes d&#39;e-mail. (CAMP-47810)

* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;accéder à la diffusion parente à partir de la diffusion enfant e-mail ou SMS. (CAMP-47986)

* Correction d&#39;un problème qui entraînait une consommation excessive de processeur et de mémoire lors de l&#39;envoi de messages transactionnels via l&#39;API REST avec un événement personnalisé manquant. (CAMP-47147)

* Correction d&#39;une erreur liée à l&#39;API des messages transactionnels qui empêchait parfois l&#39;envoi de messages en temps réel.

* Correction d&#39;un problème en raison duquel les rapports n&#39;étaient pas reçus après l&#39;utilisation de l&#39;option **Envoyer le rapport selon le calendrier**. (CAMP-48583, CAMP-47786)

* Correction d&#39;un problème en raison duquel les rapports reçus après l&#39;utilisation de l&#39;option **Envoyer le rapport maintenant** étaient incomplets et certaines données étaient manquantes. (CAMP-48583)

* Correction d&#39;un problème lié au concepteur d&#39;e-mails en raison duquel les dimensions d&#39;une image étaient réduites lors du téléchargement d&#39;une image. (CAMP-47017)

* Correction d&#39;un problème qui empêchait l&#39;affichage de tous les modèles Experience Manager disponibles lors de la création d&#39;une diffusion. (CAMP-48132)

* Correction d&#39;une erreur qui empêchait le lien Campagne de la page Résumé d&#39;une diffusion envoyée de rediriger les utilisateurs vers la campagne associée. (CAMP-48012)

* Correction d&#39;un problème dans le concepteur d&#39;e-mails en raison duquel l&#39;intégration d&#39;Asset Core Service échouait toujours lors de la sélection d&#39;une ressource. (CAMP-47446)

* Correction d&#39;un problème qui bloquait certaines diffusions de Journey Orchestration en raison de la non-prise en charge de la date et de l&#39;heure avec une valeur exacte (c&#39;est-à-dire se terminant par 00) envoyés par les événements de Journey Orchestration.

## Version 21.1 - Février 2021               {#release-21-1---february-2021}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Service de commentaires par email</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Le service de commentaires par email (EFS) est un service évolutif chargé de capturer directement les commentaires issus du MTA amélioré, contribuant ainsi à la précision des rapports. Cette fonctionnalité est disponible en version bêta privée et sera progressivement disponible pour tous les clients dans les prochaines versions.</p>
<ul>
<li>Toutes les catégories de commentaires sont maintenant capturées pour créer des rapports complets et précis.</li>
<li>Le calcul de l'indicateur <b>Délivrés</b> est désormais fondé sur les commentaires en temps réel du MTA amélioré, ce qui contribue à l'amélioration de la précision et de la réactivité.</li>
<li>Le service EFS résout le problème des retards grâce au reporting synchrone des soft bounces.</li>
</ul>
<p>Pour plus d'informations, consultez la <a href="../../sending/using/confirming-the-send.md">documentation détaillée</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Améliorations de l'intégration Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>L'intégration de Campaign avec Adobe Experience Manager a été améliorée : vous pouvez désormais importer plus facilement du contenu multilingue depuis Adobe Experience Manager. <p>
<p>Adobe Campaign Standard détecte désormais automatiquement les variantes de langues d'un contenu Adobe Experience Manager, et permet l'importation et la création de variantes en masse. Cette approche simplifie considérablement le nombre d’étapes nécessaires pour créer une campagne multilingue basée sur un contenu Adobe Experience Manager.</p>
<p>Pour plus d'informations, consultez la <a href="../../integrating/using/creating-multilingual-email-aem.md">documentation détaillée</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Améliorations**

* L&#39;**intégration de Microsoft Dynamics 365** a été améliorée avec une application dédiée d&#39;intégration en libre-service et un processus de mise en œuvre amélioré. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

* Une amélioration a été apportée pour faciliter la résolution des problèmes en cas de difficulté avec le processus de messagerie transactionnelle. Les administrateurs techniques d&#39;Adobe peuvent désormais utiliser le suivi sur n&#39;importe quel processus, sans le redémarrer.

* La liste **Profils** permet désormais de rechercher des enregistrements en fonction de l&#39;un de ces champs : email, prénom, nom ou champs personnalisés qui ont été ajoutés dans le filtrage avancé lors de l&#39;extension de la ressource de profil. Cette fonctionnalité est également disponible dans les API de Campaign Standard par le biais du paramètre filterType. [En savoir plus](../../audiences/using/integrated-customer-profile.md)

* Un paramètre a été adapté au nombre de conteneurs exécutant le processus de pool de la base de données de messagerie transactionnelle. Il est ainsi possible de répartir uniformément la charge sur tous les conteneurs utilisés et d&#39;obtenir des performances optimales.

* Une nouvelle fonction **GetOption** est désormais disponible dans les activités utilisant des variables d&#39;événement après avoir appelé un workflow avec des paramètres externes. Elle vous permet de renvoyer la valeur d&#39;une fonction spécifiée. [En savoir plus](../../automating/using/customizing-workflow-external-parameters.md)

* Une nouvelle option permet à Campaign Standard de **vérifier la disponibilité de la mémoire physique** dans votre système avant de démarrer un workflow. Si la quantité de mémoire est trop faible, l&#39;exécution du workflow sera retardée jusqu&#39;à ce que la mémoire système atteigne ce seuil. Il est ainsi possible d&#39;éviter une dégradation supplémentaire des performances et d&#39;atténuer le risque de panne. Le workflow reprend automatiquement lorsque la charge du serveur diminue et que la mémoire augmente. Notez que cette option est en lecture seule et ne peut pas être modifiée. [En savoir plus](../../automating/using/best-practices-workflows.md#execution)

* Un nouveau processus est disponible dans Adobe Campaign Standard. Il permet d&#39;effectuer plus facilement une migration depuis l&#39;ancienne application mobile SDK v4 vers le **SDK Mobile Adobe Experience Platform**. Pour plus d’informations, consultez [cette page](../../administration/using/sdkv4-migration.md).

**Autres changements**

* Transformation d’une erreur en avertissement lors de la préparation du message, lorsque la limite de 100 téléchargements de contenu par heure glissante est atteinte. Un avertissement s&#39;affiche désormais lorsque la limite est atteinte, ce qui permet de poursuivre la diffusion.

* Lors de l&#39;enrichissement du contenu d&#39;un message transactionnel, les liens ne sont plus récupérés lors de l&#39;extraction de données du tableau de profil, ce qui réduit la latence pendant la préparation du message et évite les données de profil vides en raison d&#39;une relation incorrecte définie avec le tableau de profil.

* La configuration technique de l&#39;instance a été optimisée pour assurer la stabilité. (CAMP-45681)

* La gestion des sessions a été améliorée pour optimiser la mémoire. (CAMP-45901, CAMP-46767)

* L&#39;activité **Transfert de fichier** génère désormais une variable supplémentaire (filesCount) qui contient le nombre de fichiers transférés ou téléchargés. (CAMP-45842) [En savoir plus](../../automating/using/transfer-file.md#output-variables)

* Le connecteur SMS peut maintenant envoyer plusieurs paramètres facultatifs avec chaque message. [En savoir plus](../../administration/using/sms-protocol.md)

* Les utilisateurs dotés du rôle DATAMODEL peuvent désormais publier les extensions des logs de diffusion. (CAMP-46604)

* Le message d&#39;erreur qui s&#39;affichait lors de la publication d&#39;une ressource ciblant une ressource personnalisée qui n&#39;existe plus a été clarifié. (CAMP-46893)

* Les langues suivantes ont été ajoutées à la liste **Préférence linguistique** : indonésien - Indonésie (in-id), anglais - Suède (en-se), anglais - Asie-Pacifique (en-ap), anglais - Japon (en-jp), espagnol - Amérique latine (es-la). (CAMP-46351)

* Le sélecteur de profils lors du test d’une landing page utilise désormais la ressource profilBase plutôt que le profil afin d’éviter l’expiration du délai.

* Le format de journal SMPP a été amélioré.

* Des paramètres facultatifs pour les fonctions JS cryptString et decryptString ont été ajoutés pour correspondre aux API Adobe Campaign Classic.

* Amélioration des messages d&#39;avertissement ou d&#39;erreur dans les logs de préparation de diffusion.

* Amélioration des logs d&#39;erreurs lors de la tentative de connexion à Adobe Identity Management Service (IMS).

* Vous pouvez désormais filtrer de manière plus détaillée les dimensions de **diffusion** et de **campagne** à l&#39;aide de la barre de recherche dans les rapports dynamiques.

* La date de validité d&#39;un message SMS transactionnel peut désormais être définie par la valeur indiquée pour le paramètre d&#39;expiration dans l&#39;API Messages transactionnels. (CAMP-36600)

* Dans les rapports dynamiques, le rapport intégré **Synthèse des diffusions** présentait des données incorrectes pour la mesure de taux de désabonnement. Une nouvelle mesure **Désabonnement unique** a été ajoutée pour corriger ce problème. (CAMP-46445)

**Correctifs**

* Correction d&#39;un problème en raison duquel les diffusions s&#39;exécutaient très lentement sous l&#39;effet de certains processus. Ce problème était dû à des unités incorrectes définies pour plusieurs paramètres (millisecondes au lieu de secondes, par exemple).

* Correction d&#39;un problème en raison duquel le SDK Mobile envoyait une requête de suivi d&#39;ouverture à condition que l&#39;identifiant de la diffusion/l&#39;identifiant du message ne soit pas nul. La situation était susceptible de provoquer des erreurs 404 pour les diffusions dont le suivi était désactivé. Une variable supplémentaire (acsDeliveryTracking) contenant des informations sur le statut du suivi de la diffusion est désormais envoyée dans la payload. Cette variable peut avoir deux valeurs, activé ou désactivé, selon le statut de suivi défini. [En savoir plus](../../administration/using/push-tracking.md).

* Correction d&#39;un problème dans les workflows qui pouvait se produire lors du copier-coller d&#39;une activité **Déduplication** qui avait été exécutée une seule fois et qui utilisait une ressource temporaire. Une fois dupliquée, la ressource de l&#39;activité était automatiquement définie sur vide, ce qui entraînait des problèmes dans d&#39;autres activités du workflow. Une fois collée, la ressource de l&#39;activité reste la même, afin que l&#39;erreur soit déclenchée le plus tôt possible et non plus tard dans le workflow. (CAMP-46903)

* Correction de problèmes en raison desquels l&#39;analyse de diffusion échouait lors de l&#39;envoi de notifications push transactionnelles ciblant les profils, en introduisant un nouveau [mapping de ciblage](../../administration/using/target-mappings-in-campaign.md) : **Profil - Événement en temps réel pour les notifications Push** (*mapRtEventAppSubRcp*). Les logs de diffusion, d&#39;exclusion et de tracking pour les [notifications push transactionnelles basées sur les profils](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) seront désormais stockés dans les tables *broadLogAppSubRcp*, *excludeLogAppSubRcp* et *trackingLogAppSubRcp*.

   >[!IMPORTANT]
   >
   >En raison de cette modification, si vous utilisez une notification transactionnelle push basée sur les profils existante (créée avant la mise à niveau vers Adobe Campaign 21.1), il est recommandé de mettre à jour le mapping de ciblage vers le nouveau et de publier à nouveau le message. Voir les étapes détaillées [ici](../../channels/using/transactional-push-notifications.md#change-target-mapping). L&#39;utilisation du mapping de ciblage précédent **Profil - Evénement temps réel** (*mapRtEventRcp*) peut entraîner des temps de préparation de diffusion plus longs et une dégradation des performances.

* Correction d&#39;un problème qui empêchait l&#39;exécution des rapports de diffusion lorsque 5 000 lignes étaient affichées.
* Correction d&#39;un problème lié aux tests A/B qui empêchait la mise à jour du contenu de la variante B après modification du modèle de diffusion. (CAMP-45235)
* Correction d&#39;un problème en raison duquel le processus de messagerie transactionnelle restait bloqué, empêchant l&#39;envoi de messages.
* Correction d’un problème qui pouvait entraîner des problèmes de navigation en cas de clic sur un lien interne (par exemple, lors de l’accès à la diffusion parente à partir d’un écran de résumé du BAT).
* Correction d&#39;un problème qui empêchait l&#39;affichage de tous les modèles de contenu Experience Manager disponibles lors de la création d&#39;une diffusion. (CAMP-45990)
* Correction d&#39;un problème dans les workflows qui empêchait l&#39;affichage des messages d&#39;échec dans les logs de diffusion après l&#39;ajout de la colonne **Raison** dans l&#39;onglet Données additionnelles. (CAMP-45139)
* Correction d’un problème qui pouvait se produire lorsque deux appels d’abonnement d’application avaient le même identifiant Marketing Cloud (message d’erreur « la duplication de la valeur de la clé viole une erreur de contrainte unique »).
* Correction d&#39;un problème susceptible d&#39;entraîner des problèmes de lenteur lors du glisser-déposer d&#39;activités dans un workflow contenant une grande quantité d&#39;activités **Requête** et **Lecture d&#39;audience**. (CAMP-44511)
* Correction d&#39;une erreur qui pouvait se produire à la fin de la préparation d&#39;un message transactionnel, empêchant le transfert des informations de redirection vers les serveurs de tracking.
* Correction d&#39;un problème qui pouvait afficher des messages d&#39;erreur lors de l&#39;ouverture de modèles d&#39;import ou d&#39;anciens traitements d&#39;import après personnalisation de la ressource de workflow. (CAMP-46183)
* Correction d&#39;un problème qui empêchait l&#39;exécution d&#39;une activité **Lecture d&#39;audience** si elle était configurée avec un nom d&#39;audience dynamique. (CAMP-46047)
* Correction d&#39;un problème qui empêchait l&#39;affichage du bouton **Exporter la liste**.
* Correction d&#39;un problème qui pouvait entraîner l&#39;échec du workflow **Agrégats du reporting**. (CAMP-45979)
* Correction d&#39;un problème survenant lors de la création d&#39;une ressource personnalisée avec une clé composite personnalisée (contenu dynamique texte/date).
* Correction d&#39;un problème qui pouvait empêcher l&#39;affichage des données de transition de requête. (CAMP-45669)
* Correction de problèmes de consommation de mémoire liés à la publication de ressources personnalisées.
* Correction d&#39;un problème survenant lors de la configuration d&#39;une diffusion à envoyer à une date spécifique. Si la diffusion était alors définie pour être envoyée immédiatement une fois confirmée, la préparation de la diffusion échouait et la date initialement spécifiée était prise en compte. (CAMP-44107)
* Correction d&#39;un problème qui pouvait empêcher l&#39;ouverture de modèles transactionnels. (CAMP-47181)
* Correction d&#39;un problème survenant dans le processus de publication des messages transactionnels, en raison duquel pouvaient apparaître des typologies et des règles de typologie redondantes dont les noms pouvaient dépasser la taille de chaîne autorisée. (CAMP-47104)
* Correction d&#39;un problème dans l&#39;activité **API externe** qui se produisait lorsqu&#39;un paramètre d&#39;entrée renvoyait un enregistrement qui n&#39;existait pas. (CAMP-47023)
* Correction d&#39;un problème qui pouvait empêcher le connecteur SMPP de se reconnecter.
* Correction d&#39;un problème qui se produisait dans l&#39;activité **Transfert de fichier** lors du téléchargement d&#39;un fichier dont le nom contenait un point. Les caractères qui suivent le point étaient considérés comme une extension du fichier. (CAMP-46624)
* Correction d’un problème qui empêchait l’exécution du pool de base de données et en raison duquel les messages transactionnels étaient bloqués dans la file d’attente du routeur.
* Correction d&#39;une erreur qui n&#39;empêchait pas l&#39;envoi de logs de diffusion annulés.
* Correction d’un problème en raison duquel un processus échouait lors de l’utilisation d’une activité **AND-join**. L&#39;activité modifiait automatiquement l&#39;ensemble principal à la valeur de la dernière transition qui lui avait été connectée, même si elle affichait visuellement la première transition connectée. (CAMP-46900)
* Correction d&#39;un problème en raison duquel le statut des adresses mises en quarantaine avec succès était incorrectement défini sur Valide, ce qui les retirait de la quarantaine.
* Correction d&#39;un problème en raison duquel les champs personnalisés ne s&#39;affichaient pas s&#39;ils contenaient des caractères spéciaux. (CAMP-46805)
* Correction d&#39;un problème qui pouvait empêcher d&#39;afficher une vue détaillée spécifique pour un profil. Cela se produisait si la ressource de profil avait été étendue à l&#39;aide de champs personnalisés, avec l&#39;option **Ajouter une section de champs personnalisés** activée.
* Correction d&#39;un problème qui pouvait renvoyer un code d&#39;erreur 500 lors de l&#39;envoi d&#39;événements transactionnels. (CAMP-46811)
* Correction d&#39;un problème qui pouvait empêcher la réception des rapports différés par email. (CAMP-46891)
* Correction d&#39;un problème survenant lors de la liaison d&#39;une ressource personnalisée à la ressource de profil avec un lien simple de cardinalité 1. Lors de l&#39;accès à un profil dont le champ de ressource personnalisée est vide, un message d&#39;erreur s&#39;affiche désormais au lieu d&#39;une liste vide.
* Correction d&#39;un problème lors de l&#39;utilisation de la substitution de profil dans un workflow en raison duquel la page ne chargeait pas les profils de diffusion lors de la sélection du profil à remplacer. (CAMP-46522)
* Correction d&#39;une régression en raison de laquelle le workflow technique de **nettoyage de la base** tentait d&#39;abandonner les tables de travail de diffusion expirées, provoquant les erreurs suivantes : (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Correction de l&#39;erreur suivante qui se produisait dans certains cas lors de l&#39;utilisation d&#39;un filtre personnalisé sur des ressources personnalisées : (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Correction d&#39;un problème en raison duquel la **préparation de la notification push** prenait trop de temps pour être terminée. Ce problème était dû à l&#39;absence d&#39;index sur les tables de travail transitoires.
* Correction d&#39;une erreur qui pouvait se produire lors de l&#39;utilisation de l&#39;option **Dimension vers laquelle réconcilier** dans une activité **Réconciliation** d&#39;un workflow si une relation était déjà définie entre une ressource personnalisée et une ressource de profil.
* Correction d&#39;un problème qui se produisait lors de l&#39;ajout de liens par le biais d&#39;une activité **Réconciliation** ou **Enrichissement**. Les liens sélectionnés n&#39;étaient pas affichés dans la transition de sortie.
* Correction d&#39;un problème lors de l&#39;utilisation d&#39;une activité **Segmentation** avec des diffusions récurrentes dans un workflow en raison duquel la diffusion était envoyée à une audience incorrecte. (CAMP-46275, CAMP-46470)
* Correction d&#39;une erreur en raison de laquelle la publication de ressources personnalisées échouait lors de la tentative d&#39;extension de la ressource Profil pour créer des dimensions de profil personnalisées pour les rapports dynamiques. (CAMP-46266)
* Correction d&#39;une erreur qui se produisait lors de l&#39;ajout d&#39;un lien à un tableau d&#39;importation de fichier. Après avoir ajouté une activité **Enrichissement** à l&#39;activité **Import de fichier**, le lien précédemment configuré disparaissait. (CAMP-46557)
* Correction d&#39;un problème lors de l&#39;utilisation de ressources personnalisées liées à des données de Profil en raison duquel l&#39;ordre de priorité d&#39;affichage dans l&#39;écran de configuration des **détails** était modifié lors de l&#39;enregistrement. (CAMP-46312)
* Correction d&#39;un problème en raison duquel il était impossible d&#39;afficher les données dans les rapports dynamiques en raison de diffusions basées sur un mapping de diffusion personnalisé.
* Correction d&#39;une erreur qui vous empêchait de sélectionner une collection avec une cible de ressources incorrecte dans une activité de **requête** de workflow.
* Correction d&#39;un problème en raison duquel le processus InMail pouvait valider incorrectement les hard bounces.
* Correction d&#39;une erreur qui se produisait lors de l&#39;ouverture d&#39;un écran de profil en raison d&#39;une erreur de lien.
* Correction d&#39;un problème qui pouvait empêcher la suppression de données RGPD du processus de nettoyage.
* Correction d&#39;une erreur qui se produisait lorsque la configuration de planification était mise à jour manuellement au clavier dans les paramètres de planification de la diffusion email.
* Correction d&#39;un problème qui pouvait vous empêcher de modifier un profil en raison de paramètres incorrects dans l&#39;entité organisationnelle.
* Correction d&#39;un problème en raison duquel le champ Extension de **service** était vide et impossible à définir dans les **propriétés d&#39;email** même s&#39;il était défini dans le modèle de diffusion.
* Correction d&#39;un problème en raison duquel le traitement des BAT pouvait prendre plus de temps. (CAMP-45048)
* Correction d&#39;un problème en raison duquel il était impossible de trier les colonnes dans un écran de présentation de profil.
* Correction d&#39;un problème de génération de miniatures qui pouvait se produire sur Azure dans les variantes d&#39;email contenant des caractères chinois. (CAMP-47152)
* Correction d&#39;une régression introduite dans la version Campaign 20.4 qui pouvait entraîner des taux d&#39;ouverture incorrects pour Gmail en raison du filtrage des événements de tracking reçus de comptes Gmail. (CAMP-46504)
* Correction d&#39;un problème qui pouvait empêcher l&#39;importation de contenu HTML dans un modèle de message transactionnel. (CAMP-47318)
* Correction d&#39;un problème qui pouvait ralentir l&#39;affichage des rendus dans le **rapport de rendu des emails**. (CAMP-46226)
* Correction d&#39;un problème qui pouvait empêcher la publication de ressources personnalisées configurées avec un élément de type Liste dans la définition d&#39;écran. (CAMP-47217)
* Correction d&#39;un problème dans le concepteur d&#39;emails qui empêchait le rendu correct des séparateurs de ligne dans **Microsoft Outlook** lorsqu&#39;ils étaient placés en haut du contenu email. (CAMP-46294)
* Correction d&#39;un problème en raison duquel la réconciliation des KPI avec le workflow technique **Adobe Analytics** était bloquée. (CAMP-46576)
* Correction d&#39;un problème dans le **concepteur d&#39;emails** en raison duquel les fragments ne s&#39;affichaient pas automatiquement dans les zones de recherche lors de l&#39;insertion de blocs de contenu. (CAMP-44205)
* Correction d&#39;un problème dans le **concepteur d&#39;emails** en raison duquel des caractères indésirables s&#39;affichaient dans les emails envoyés lors de l&#39;utilisation d&#39;émoticônes dans des fragments. (CAMP-46621)
* Correction d&#39;une régression introduite dans la version 20.4 du **concepteur d&#39;emails** qui affectait le composant Diviseur, ce qui entraînait des hauteurs de ligne supplémentaires et des distorsions d&#39;image dans le contenu. (CAMP-46663)
* Correction d&#39;un problème en raison duquel les boutons d&#39;usine restaient centrés lorsque le message était envoyé à une boîte aux lettres Outlook, même si ces boutons étaient alignés à droite ou à gauche dans le **concepteur d&#39;emails**. (CAMP-46466)
* Correction d&#39;un problème qui empêchait l&#39;actualisation de la liste des profils de test lors de la recherche de profils dans la prévisualisation du **concepteur d&#39;emails**. (CAMP-45265)
* Correction d&#39;un problème en raison duquel les profils de test personnalisés ne s&#39;affichaient pas dans la liste lors de la recherche de profils dans la prévisualisation du **concepteur d&#39;emails**. (CAMP-45589)
* Correction d&#39;un problème en raison duquel des dates incohérentes s&#39;affichaient lors de la génération de graphiques de tendance à partir du **rapport de synthèse des diffusions.** (CAMP-45521)
