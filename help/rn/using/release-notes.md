---
solution: Campaign Standard
product: campaign
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 46d864de0ffd5dce718a2a2c055c3194e45fcdd2
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 99%

---


# Dernière version{#latest-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

## Version 21.1 - Février 2021 {#release-21-1---february-2021}

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
<li>Le calcul de l’indicateur <b>Délivrés</b> est désormais fondé sur les commentaires en temps réel du MTA amélioré, ce qui contribue à l’amélioration de la précision et de la réactivité.</li>
<li>Le service EFS résout le problème des retards grâce au reporting synchrone des soft bounces.</li>
</ul>
<p>Pour plus d’informations, consultez la <a href="../../sending/using/confirming-the-send.md#message-indicators">documentation détaillée</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Améliorations de l’intégration Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>L’intégration de Campaign avec Adobe Experience Manager a été améliorée : vous pouvez désormais importer plus facilement du contenu multilingue depuis Adobe Experience Manager. <p>
<p>Adobe Campaign Standard détecte désormais automatiquement les variantes de langues d’un contenu Adobe Experience Manager et permet l’importation et la création de variantes en masse. Cette approche simplifie considérablement le nombre d’étapes nécessaires à un praticien pour créer une campagne multilingue basée sur un contenu Adobe Experience Manager.</p>
<p>Pour plus d’informations, consultez la <a href="../../integrating/using/creating-multilingual-email-aem.md">documentation détaillée</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Interface Experience Cloud unifiée</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La barre d’en-tête d’Adobe Campaign a été modifiée pour unifier et améliorer votre expérience sur tous les produits et services Experience Cloud. Ces modifications visent à faciliter votre expérience des produits et services, notamment :</p>
<ul>
<li>Un basculement plus facile entre différentes entreprises ou vers une autre application.</li>
<li>Guide d'utilisateur amélioré - Avec l’intégration d’Experience League dans le produit, les résultats des recherches incluent également les résultats des forums de la communauté et davantage de contenu vidéo, ce qui permet d’accéder plus facilement à un plus large éventail de contenu pour tirer pleinement parti de l’application. Nous avons également ajouté un mécanisme de commentaires directement dans le menu Aide, ce qui facilite le signalement de problèmes ou le partage d’idées.</li>
<li>Notifications améliorées - La liste déroulante Notifications comporte désormais deux onglets : l’une pour vos propres notifications de produits, l’autre pour des annonces de produits plus globales.</li>
</ul>
<p>Pour plus d’informations, consultez la <a href="../../start/using/interface-description.md#top-bar">documentation détaillée</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* L’**intégration de Microsoft Dynamics 365** a été améliorée avec une application dédiée d’intégration en libre-service et un processus de mise en œuvre amélioré. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

* Une amélioration a été apportée pour faciliter la résolution des problèmes en cas de difficulté avec le processus de messagerie transactionnelle. Les administrateurs techniques d’Adobe peuvent désormais utiliser le suivi sur n’importe quel processus, sans le redémarrer.

* La liste **Profils** permet désormais de rechercher des enregistrements en fonction de l’un de ces champs : email, prénom, nom ou champs personnalisés qui ont été ajoutés dans le filtrage avancé lors de l’extension de la ressource de profil. Cette fonctionnalité est également disponible dans les API de Campaign Standard par le biais du paramètre filterType. [En savoir plus](../../audiences/using/integrated-customer-profile.md)

* Un paramètre a été adapté au nombre de conteneurs exécutant le processus de pool de la base de données de messagerie transactionnelle. Il est ainsi possible de répartir uniformément la charge sur tous les conteneurs utilisés et d’obtenir des performances optimales.

* Une nouvelle fonction **GetOption** est désormais disponible dans les activités utilisant des variables d’événement après avoir appelé un workflow avec des paramètres externes. Elle vous permet de renvoyer la valeur d’une fonction spécifiée. [En savoir plus](../../automating/using/customizing-workflow-external-parameters.md)

* Une nouvelle option permet au Campaign Standard de **vérifier la disponibilité de la mémoire physique** sur votre système avant de démarrer un processus. Si la quantité de mémoire est trop faible, l’exécution du workflow sera retardée jusqu’à ce que la mémoire système atteigne ce seuil. Il est ainsi possible d’éviter une dégradation supplémentaire des performances et d’atténuer le risque de panne. Le workflow reprend automatiquement lorsque la charge du serveur diminue et que la mémoire augmente. Notez que cette option est en lecture seule et ne peut pas être modifiée. [En savoir plus](../../automating/using/best-practices-workflows.md#execution)

* Un nouveau processus est disponible dans Adobe Campaign Standard. Il permet d’effectuer plus facilement une migration depuis l’ancienne application mobile SDK v4 vers le **SDK Mobile Adobe Experience Platform**. Consultez à ce sujet [cette page](../../administration/using/sdkv4-migration.md).

**Autres changements**

* Transformation d’une erreur en avertissement lors de la préparation du message, lorsque la limite de 100 téléchargements de contenu par heure roulante est atteinte. Un avertissement s’affiche désormais lorsque la limite est atteinte, ce qui permet de poursuivre la diffusion.

* Lors de l’enrichissement du contenu d’un message transactionnel, les liens ne sont plus récupérés lors de l’extraction de données du tableau de profil, ce qui réduit la latence pendant la préparation du message et évite les données de profil vides en raison d’une relation incorrecte définie avec le tableau de profil.

* La configuration technique de l’instance a été optimisée pour assurer la stabilité. (CAMP-45681)

* La gestion des sessions a été améliorée pour optimiser la mémoire. (CAMP-45901, CAMP-46767)

* L’activité **Transfert de fichier** génère désormais une variable supplémentaire (filesCount) qui contient le nombre de fichiers transférés ou téléchargés. (CAMP-45842) [En savoir plus](../../automating/using/transfer-file.md#output-variables)

* Le connecteur SMS peut maintenant envoyer plusieurs paramètres facultatifs avec chaque message. [En savoir plus](../../administration/using/sms-protocol.md)

* Les utilisateurs dotés du rôle DATAMODEL peuvent désormais publier les extensions des logs de diffusion. (CAMP-46604)

* Le message d’erreur qui s’affichait lors de la publication d’une ressource ciblant une ressource personnalisée qui n’existe plus a été clarifié. (CAMP-46893)

* Les langues suivantes ont été ajoutées à la liste **Préférence linguistique** : indonésien - Indonésie (in-id), anglais - Suède (en-se), anglais - Asie-Pacifique (en-ap), anglais - Japon (en-jp), espagnol - Amérique latine (es-la). (CAMP-46351)

* Le sélecteur de profils lors du test d’une landing page utilise désormais la ressource profilBase plutôt que le profil afin d’éviter un délai expiré.

* Le format de journal SMPP a été amélioré.

* Des paramètres facultatifs pour les fonctions JS cryptString et decryptString ont été ajoutés pour correspondre aux API Adobe Campaign Classic.

* Amélioration des messages d’avertissement ou d’erreur dans les logs de préparation de diffusion.

* Amélioration des logs d’erreurs lors de la tentative de connexion à Adobe Identity Management Service (IMS).

* Vous pouvez désormais filtrer de manière plus détaillée les dimensions de **diffusion** et de **campagne** à l’aide de la barre de recherche dans les rapports dynamiques.

* La date de validité d’un message SMS transactionnel peut désormais être définie par la valeur indiquée pour le paramètre d’expiration dans l’API Messages transactionnels. (CAMP-36600)

* Dans les rapports dynamiques, le rapport intégré **Synthèse des diffusions** présentait des données incorrectes pour la mesure de taux de désabonnement. Une nouvelle mesure **Désabonnement unique** a été ajoutée pour corriger ce problème. (CAMP-46445)

**Correctifs**

* Correction d’un problème en raison duquel les diffusions s’exécutaient très lentement sous l’effet de certains processus. Ce problème était dû à des unités incorrectes définies pour plusieurs paramètres (millisecondes au lieu de secondes, par exemple).

* Correction d’un problème en raison duquel le SDK Mobile envoyait une requête de suivi d&#39;ouverture à condition que l’identifiant de la diffusion/l’identifiant du message ne soit pas nul. La situation était susceptible de provoquer des erreurs 404 pour les diffusions dont le suivi était désactivé. Une variable supplémentaire (acsDeliveryTracking) contenant des informations sur le statut du suivi de la diffusion est désormais envoyée dans la payload. Cette variable peut avoir deux valeurs, activé ou désactivé, selon le statut de suivi défini. [En savoir plus](../../administration/using/push-tracking.md).

* Correction d’un problème dans les workflows qui pouvait se produire lors du copier-coller d’une activité **Déduplication** qui avait été exécutée une seule fois et qui utilisait une ressource temporaire. Une fois dupliquée, la ressource de l&#39;activité était automatiquement définie sur vide, ce qui entraînait des problèmes dans d’autres activités du workflow. Une fois collée, la ressource de l’activité reste la même, afin que l’erreur soit déclenchée le plus tôt possible et non plus tard dans le workflow. (CAMP-46903)

* Correction d’un problème en raison duquel l’analyse de diffusion échouait lors de l’envoi de messages push transactionnels ciblant les profils, en introduisant un nouveau [mapping de ciblage](../../administration/using/target-mappings-in-campaign.md) : **Profil - Événement temps réel pour les notifications Push** (*mapRtEventAppSubRcp*). Les logs de diffusion, d’exclusion et de tracking des [notifications push transactionnelles ciblant un profil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) seront désormais stockés dans les tables *broadLogAppSubRcp*, *excludeLogAppSubRcp* et *trackingLogAppSubRcp*.
* Correction d’un problème qui empêchait l’exécution des rapports de diffusion lorsque 5 000 lignes étaient affichées.
* Correction d’un problème lié aux tests A/B qui empêchait la mise à jour du contenu de la variante B après modification du modèle de diffusion. (CAMP-45235)
* Correction d’un problème en raison duquel le processus de messagerie transactionnelle restait bloqué, empêchant l’envoi de messages.
* Correction d’un problème qui pouvait entraîner des problèmes de navigation après que l’utilisateur ait cliqué sur un lien interne (par exemple, lors de l’accès à la diffusion parente à partir d’un écran de résumé du BAT).
* Correction d’un problème qui empêchait l’affichage de tous les modèles de contenu Experience Manager disponibles lors de la création d’une diffusion. (CAMP-45990)
* Correction d’un problème dans les workflows qui empêchait l’affichage des messages d’échec dans les logs de diffusion après l’ajout de la colonne **Raison** dans l’onglet Données additionnelles. (CAMP-45139)
* Correction d’un problème qui pouvait se produire lorsque deux appels d’abonnement d’application avaient le même Identifiant Marketing Cloud (message d’erreur &#39;la duplication de la valeur de la clé viole une erreur de contrainte unique&#39;).
* Correction d’un problème susceptible d’entraîner des problèmes de lenteur lors du glisser-déposer d’activités dans un workflow contenant une grande quantité d’activités **Requête** et **Lecture d’audience**. (CAMP-44511)
* Correction d’une erreur qui pouvait se produire à la fin de la préparation d’un message transactionnel, empêchant le transfert des informations de redirection vers les serveurs de tracking.
* Correction d’un problème qui pouvait afficher des messages d’erreur lors de l’ouverture de modèles d’import ou d’anciens traitements d’import après personnalisation de la ressource de workflow. (CAMP-46183)
* Correction d’un problème qui empêchait l’exécution d’une activité **Lecture d’audience** si elle était configurée avec un nom d’audience dynamique. (CAMP-46047)
* Correction d’un problème qui empêchait l’affichage du bouton **Exporter la liste**.
* Correction d’un problème qui pouvait entraîner l’échec du workflow **Agrégats du reporting**. (CAMP-45979)
* Correction d’un problème survenant lors de la création d’une ressource personnalisée avec une clé composite personnalisée (contenu dynamique texte/date).
* Correction d’un problème qui pouvait empêcher l’affichage des données de transition de requête. (CAMP-45669)
* Correction de problèmes de consommation de mémoire liés à la publication de ressources personnalisées.
* Correction d’un problème survenant lors de la configuration d’une diffusion à envoyer à une date spécifique. Si la diffusion était alors définie pour être envoyée immédiatement une fois confirmée, la préparation de la diffusion échouait et la date initialement spécifiée était prise en compte. (CAMP-44107)
* Correction d’un problème qui pouvait empêcher l’ouverture de modèles transactionnels. (CAMP-47181)
* Correction d’un problème survenant dans le processus de publication des messages transactionnels, en raison duquel pouvaient apparaître des typologies et des règles de typologie redondantes dont les noms pouvaient dépasser la taille de chaîne autorisée. (CAMP-47104)
* Correction d’un problème dans l’activité **API externe** qui se produisait lorsqu’un paramètre d’entrée renvoyait un enregistrement qui n’existait pas. (CAMP-47023)
* Correction d’un problème qui pouvait empêcher le connecteur SMPP de se reconnecter.
* Correction d’un problème qui se produisait dans l’activité **Transfert de fichier** lors du téléchargement d’un fichier dont le nom contenait un point. Les caractères qui suivent le point étaient considérés comme une extension du fichier. (CAMP-46624)
* Correction d’un problème qui empêchait l’exécution du pool de base de données, en raison duquel les messages transactionnels étaient bloqués dans la file d’attente du routeur.
* Correction d’une erreur qui n’empêchait pas l’envoi de logs de diffusion annulés.
* Correction d’un problème en raison duquel un processus échouait lors de l’utilisation d’une activité **Rendez-vous**. L’activité modifiait automatiquement l’ensemble principal à la valeur de la dernière transition qui lui avait été connectée, même si elle affichait visuellement la première transition connectée. (CAMP-46900)
* Correction d’un problème en raison duquel le statut des adresses mises en quarantaine avec succès était incorrectement défini sur Valide, ce qui les retirait de la quarantaine.
* Correction d’un problème en raison duquel les champs personnalisés ne s’affichaient pas s’ils contenaient des caractères spéciaux. (CAMP-46805)
* Correction d’un problème qui pouvait empêcher d’afficher une vue détaillée spécifique pour un profil. Cela se produisait si la ressource de profil avait été étendue à l’aide de champs personnalisés, avec l’option **Ajouter une section de champs personnalisés** activée.
* Correction d’un problème qui pouvait renvoyer un code d’erreur 500 lors de l’envoi d’événements transactionnels. (CAMP-46811)
* Correction d’un problème qui pouvait empêcher la réception des rapports différés par email. (CAMP-46891)
* Correction d’un problème survenant lors de la liaison d’une ressource personnalisée à la ressource de profil avec un lien simple de cardinalité 1. Lors de l’accès à un profil dont le champ de ressource personnalisée est vide, un message d’erreur s’affiche désormais au lieu d’une liste vide.
* Correction d’un problème lors de l’utilisation de la substitution de profil dans un workflow en raison duquel la page ne chargeait pas les profils de diffusion lors de la sélection du profil à remplacer. (CAMP-46522)
* Correction d’une régression en raison de laquelle le workflow technique de **nettoyage de la base** tentait d’abandonner les tables de travail de diffusion expirées, provoquant les erreurs suivantes : (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Correction de l’erreur suivante qui se produisait dans certains cas lors de l’utilisation d’un filtre personnalisé sur des ressources personnalisées : (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Correction d’un problème en raison duquel la **préparation de la notification push** prenait trop de temps pour être terminée. Ce problème était dû à l’absence d’index sur les tables de travail transitoires.
* Correction d’une erreur qui pouvait se produire lors de l’utilisation de l’option **Dimension vers laquelle réconcilier** dans une activité **Réconciliation** d’un workflow si une relation était déjà définie entre une ressource personnalisée et une ressource de profil.
* Correction d’un problème qui se produisait lors de l’ajout de liens par le biais d’une activité **Réconciliation** ou **Enrichissement**. Les liens sélectionnés n’étaient pas affichés dans la transition de sortie.
* Correction d’un problème lors de l’utilisation d’une activité **Segmentation** avec des diffusions récurrentes dans un workflow en raison duquel la diffusion était envoyée à une audience incorrecte. (CAMP-46275, CAMP-46470)
* Correction d’une erreur en raison de laquelle la publication de ressources personnalisées échouait lors de la tentative d’extension de la ressource Profil pour créer des dimensions de profil personnalisées pour les rapports dynamiques. (CAMP-46266)
* Correction d’une erreur qui se produisait lors de l’ajout d’un lien à un tableau d’importation de fichier. Après avoir ajouté une activité **Enrichissement** à l’activité **Import de fichier**, le lien précédemment configuré disparaissait. (CAMP-46557)
* Correction d’un problème lors de l’utilisation de ressources personnalisées liées à des données de Profil en raison duquel l’ordre de priorité d’affichage dans l’écran de configuration des **détails** était modifié lors de l’enregistrement. (CAMP-46312)
* Correction d’un problème en raison duquel il était impossible d’afficher les données dans les rapports dynamiques en raison de diffusions basées sur un mapping de diffusion personnalisé.
* Correction d’une erreur qui vous empêchait de sélectionner une collection avec une cible de ressources incorrecte dans une activité de **requête** de workflow.
* Correction d’un problème en raison duquel le processus InMail pouvait valider incorrectement les hard bounces.
* Correction d’une erreur qui se produisait lors de l’ouverture d’un écran de profil en raison d’une erreur de lien.
* Correction d’un problème qui pouvait empêcher la suppression de données RGPD du processus de nettoyage.
* Correction d’une erreur qui se produisait lorsque la configuration de planification était mise à jour manuellement au clavier dans les paramètres de planification de la diffusion email.
* Correction d’un problème qui pouvait vous empêcher de modifier un profil en raison de paramètres incorrects dans l’entité organisationnelle.
* Correction d’un problème en raison duquel le champ Extension de **service** était vide et impossible à définir dans les **propriétés d’email** même s’il était défini dans le modèle de diffusion.
* Correction d’un problème en raison duquel le traitement des BAT pouvait prendre plus de temps. (CAMP-45048)
* Correction d’un problème en raison duquel il était impossible de trier les colonnes dans un écran de présentation de profil.
* Correction d’un problème de génération de miniatures qui pouvait se produire sur Azure dans les variantes d’email contenant des caractères chinois. (CAMP-47152)
* Correction d’une régression introduite dans la version Campaign 20.4 qui pouvait entraîner des taux d’ouverture incorrects pour Gmail en raison du filtrage des événements de tracking reçus de comptes Gmail. (CAMP-46504)
* Correction d’un problème qui pouvait empêcher l&#39;importation de contenu HTML dans un modèle de message transactionnel. (CAMP-47318)
* Correction d’un problème qui pouvait ralentir l’affichage des rendus dans le **rapport de rendu des emails**. (CAMP-46226)
* Correction d’un problème qui pouvait empêcher la publication de ressources personnalisées configurées avec un élément de type Liste dans la définition d’écran. (CAMP-47217)
* Correction d’un problème dans le concepteur d’emails qui empêchait le rendu correct des séparateurs de ligne dans **Microsoft Outlook** lorsqu’ils étaient placés en haut du contenu email. (CAMP-46294)
* Correction d’un problème en raison duquel la réconciliation des KPI avec le workflow technique **Adobe Analytics** était bloquée. (CAMP-46576)
* Correction d’un problème dans le **concepteur d’emails** en raison duquel les fragments ne s’affichaient pas automatiquement dans les zones de recherche lors de l’insertion de blocs de contenu. (CAMP-44205)
* Correction d’un problème dans le **concepteur d’emails** en raison duquel des caractères indésirables s’affichaient dans les emails envoyés lors de l’utilisation d’émoticônes dans des fragments. (CAMP-46621)
* Correction d’une régression introduite dans la version 20.4 du **concepteur d’emails** qui affectait le composant Diviseur, ce qui entraînait des hauteurs de ligne supplémentaires et des distorsions d’image dans le contenu. (CAMP-46663)
* Correction d’un problème en raison duquel les boutons d’usine restaient centrés lorsque le message était envoyé à une boîte aux lettres Outlook, même si ces boutons étaient alignés à droite ou à gauche dans le **concepteur d’emails**. (CAMP-46466)
* Correction d’un problème qui empêchait l’actualisation de la liste des profils de test lors de la recherche de profils dans la prévisualisation du **concepteur d’emails**. (CAMP-45265)
* Correction d’un problème en raison duquel les profils de test personnalisés ne s’affichaient pas dans la liste lors de la recherche de profils dans la prévisualisation du **concepteur d’emails**. (CAMP-45589)
* Correction d’un problème en raison duquel des dates incohérentes s’affichaient lors de la génération de graphiques de tendance à partir du **rapport de synthèse des diffusions.** (CAMP-45521)
