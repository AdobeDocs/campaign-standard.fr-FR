---
solution: Campaign Standard
product: campaign
title: Notes de mise à jour anticipées
description: Notes de mise à jour anticipées
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 1bf35c654b9c526330a70f7647ec7d9fd87e2335
workflow-type: tm+mt
source-wordcount: '2586'
ht-degree: 4%

---


# Nouvelle version {#new-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour les plus récentes](../../rn/using/release-notes.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version du Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu’à la date de mise à niveau de l’environnement d’étape. Pour en savoir plus, consultez la [page de planification des versions](../../rn/using/release-planning.md).


## Version 21.1 - février 2021 {#release-21-1---febuary-2021}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Service de commentaires par courriel</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Le service de commentaires par courrier électronique (EFS) est un service évolutif qui améliore la précision des rapports en capturant les commentaires par courrier électronique directement à partir de la MTA améliorée.</p>
<ul>
<li>Toutes les catégories de événements sont capturées : Retards, Livraisons, Envoi, Désabonnement (lien, Liste), Commentaires (plaintes de spam, événements asynchrones).</li>
<li>Le calcul des indicateurs envoyés/distribués est maintenant fondé sur les commentaires en temps réel de l’AMT améliorée pour une précision et une réactivité améliorées.</li>
<li>EFS résout le problème des retards de rapports de rebonds synchrones et retire 80 % de la charge du processus inMail.</li>
</ul>
<p>Cette fonctionnalité est disponible en tant que <strong>bêta privée</strong> et sera progressivement accessible à tous les clients dans les prochaines versions.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Améliorations de l’intégration de Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>L'intégration de Campaign avec Adobe Experience Manager a été améliorée : vous pouvez désormais importer plus facilement du contenu multilingue à partir de Adobe Experience Manager. <p>
<p>Adobe Campaign Standard détecte désormais automatiquement les variantes de langue du contenu Adobe Experience Manager et permet l’importation et la création de variantes en masse, ce qui simplifie considérablement le nombre d’étapes qu’un praticien doit franchir pour créer une campagne multilingue basée sur le contenu Adobe Experience Manager.</p>
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
<p>La barre d’en-tête Adobe Campaign a été modifiée afin d’unifier et d’améliorer votre expérience sur tous les produits et services Experience Cloud. Ces modifications visent à faciliter votre vie, notamment :</p>
<ul>
<li>Il est plus facile de basculer entre vos entreprises ou vers une autre application.</li>
<li>Aide à l'utilisateur améliorée - L'intégration de l'Experience League dans le produit, les résultats de la recherche incluent également les résultats des forums de la communauté et davantage de contenu vidéo, ce qui vous permet d'accéder plus facilement à davantage de contenu pour tirer le meilleur parti de l'application. Nous avons également ajouté un mécanisme de rétroaction directement dans le menu Aide, ce qui facilite le signalement de problèmes ou le partage de vos idées.</li>
<li>Notifications améliorées - La liste déroulante Notifications comporte désormais deux onglets : l'une pour vos propres notifications de produits, l'autre pour des annonces de produits plus globales.</li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* **L&#39;** intégration de Microsoft Dynamics 365a été améliorée grâce à une application d&#39;intégration en libre-service dédiée et à un processus de mise en oeuvre amélioré. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

* Une amélioration a été apportée afin de faciliter le dépannage en cas de problème avec le **processus de messagerie transactionnelle**. Les administrateurs techniques d’Adobe peuvent désormais utiliser le suivi sur n’importe quel processus sans le redémarrer.

* La liste **Profils** vous permet désormais de rechercher des enregistrements en fonction de l’un de ces champs : e-mail, prénom, nom ou champs personnalisés qui ont été ajoutés dans le filtrage avancé lors de l’extension de la ressource profil. Cette fonctionnalité est également disponible dans les API de Campaign Standard à l’aide du paramètre filterType.

* Un paramètre a été ajusté au nombre de conteneurs exécutant le processus de regroupement de base de données **Transactional messaging**. Cela permet de répartir uniformément la charge sur tous les conteneurs utilisés et d&#39;atteindre des performances optimales.

* Une nouvelle fonction **GetOption** est désormais disponible dans les activités à l&#39;aide de variables de événement après avoir appelé un processus avec des paramètres externes. Il vous permet de renvoyer la valeur d’une fonction spécifiée.

* Une nouvelle option permet au Campaign Standard de **vérifier la disponibilité de la mémoire physique** sur votre système avant de démarrer un processus. Si la quantité de mémoire est trop faible, l&#39;exécution du flux de travail sera retardée jusqu&#39;à ce que la mémoire système atteigne ce seuil. Cela permet d&#39;éviter une dégradation supplémentaire des performances et d&#39;atténuer le risque de panne. Le flux de travaux reprend automatiquement lorsque la charge sur le serveur diminue et que la mémoire augmente. Notez que cette option est en lecture seule et ne peut pas être modifiée.


**Autres changements**

* Modification d’une erreur en avertissement lors de la préparation du message, lorsque la limite de 100 téléchargements de contenu par heure roulante est atteinte. Un avertissement s’affiche désormais lorsque la limite est atteinte, ce qui permet de poursuivre la diffusion.

* Lors de l’enrichissement du contenu d’un message transactionnel, les liens ne sont plus récupérés lors de l’extraction de données du tableau de Profil, ce qui réduit la latence pendant la préparation du message et évite les données de profil vides en raison d’une relation incorrecte définie avec le tableau de profil.

* La configuration technique de l&#39;instance a été optimisée pour assurer la stabilité. (CAMP-45681)

* La gestion des sessions a été améliorée pour optimiser la mémoire. (CAMP-45901, CAMP-46767)

* L’activité **Transférer le fichier** génère désormais une variable supplémentaire (filesCount) qui contient le nombre de fichiers téléchargés ou téléchargés. (CAMP-45842)

* Le **connecteur SMS** peut désormais envoyer plusieurs paramètres facultatifs avec chaque message.

* Les utilisateurs dotés du rôle DATAMODEL peuvent désormais publier les extensions du journal de diffusion. (CAMP-46604)

* Le message d’erreur qui s’affichait lors de la publication d’une ressource ciblant une ressource personnalisée qui n’existe plus a été clarifié. (CAMP-46893)

* Les langues suivantes ont été ajoutées à la liste **Langue préférée** : indonésien - Indonésie (in-id), anglais - Suède (en-se), anglais - Asie-Pacifique (en-ap), anglais - Japon (en-jp), espagnol - Amérique latine (es-la). (CAMP-46351)

* Le sélecteur de profils sélectionné lors du test d’un landing page utilise désormais la ressource profilBase plutôt que le profil pour éviter le délai d’attente.

* Le format de journal SMPP a été amélioré.

* Des paramètres facultatifs pour les fonctions JS cryptString et decryptString ont été ajoutés pour correspondre aux API Adobe Campaign Classic.

* Amélioration des messages d’avertissement ou d’erreur dans les journaux de préparation de diffusion.

* Amélioration des journaux des erreurs lors de la tentative de connexion à Adobe Identity Management Service (IMS).

* Vous pouvez désormais filtrer davantage les dimensions de la Diffusion et de Campaign à l’aide de la barre de recherche dans **rapports dynamique**.

* La date de validité du message SMS transactionnel peut désormais être définie par la valeur définie pour le paramètre d&#39;expiration dans l&#39;API **Messages transactionnels**. (CAMP-36600)

* Dans le rapports dynamique, le rapport intégré **Résumé de la Diffusion** présentait des données incorrectes pour la mesure de taux de désabonnement. Une nouvelle mesure **désinscription unique** a été ajoutée pour corriger ce problème. (CAMP-46445)

**Correctifs**

* Correction d’un problème en raison duquel les diffusions s’exécutaient très lentement en raison de certains processus. Ceci est dû à des unités incorrectes définies pour plusieurs paramètres (millisecondes au lieu de secondes, par exemple).
* Correction d’un problème dans les workflows qui pouvait se produire lors du copier-coller d’une activité **Déduplication** qui avait été exécutée une seule fois et qui utilisait une ressource temporaire. Une fois dupliquée, la ressource d’activité était automatiquement définie sur vide, ce qui entraînait des problèmes dans d’autres activités du flux de travail. Une fois collée, la ressource de l’activité reste la même, afin que l’erreur soit déclenchée le plus tôt possible et non plus plus tard dans le flux de travail. (CAMP-46903)
* Correction d’un problème en raison duquel le SDK mobile envoyait une demande de suivi ouverte à condition que l’ID de diffusion/ID de message ne soit pas nul. Cela provoquerait 404 erreurs pour les diffusions dont le suivi est désactivé. Une variable supplémentaire (acsDeliveryTracking) contenant des informations sur l’état de suivi de la diffusion est maintenant envoyée dans la charge utile. Cette variable peut avoir deux valeurs activées ou désactivées selon l’état de suivi défini.
* Correction d’un problème qui empêchait l’exécution des rapports de diffusion lorsque 5 000 lignes étaient affichées.
* Correction d’un problème lié aux tests A/B qui empêchait la mise à jour du contenu de la variante B après la modification du modèle de diffusion. (CAMP-45235)
* Correction d’un problème en raison duquel le processus de messagerie transactionnelle restait bloqué, empêchant l’envoi de messages.
* Correction d’un problème en raison duquel l’analyse de l’diffusion échouait lors de l’envoi d’un message Push transactionnel utilisant la dimension cible de Profil. Un nouveau mapping de diffusion (mapRtEventAppSubRcp) est désormais disponible pour les messages push transactionnels ciblant les profils. La diffusion, l’exclusion et les logs de tracking de ces diffusions seront désormais disponibles dans les tables broadLogAppSubRcp, excludeLogAppSubRcp et trackingLogAppSubRcp.
* Correction d’un problème qui pouvait entraîner des problèmes de navigation après avoir cliqué sur un lien interne (par exemple, lors de l’accès à la diffusion parent à partir d’un écran de résumé du BAT).
* Correction d’un problème qui empêchait l’affichage de tous les modèles de contenu de Experience Manager disponibles lors de la création d’une diffusion. (CAMP-45990)
* Correction d’un problème dans les workflows qui empêchait l’affichage des messages d’échec dans les logs de diffusion après l’ajout de la colonne **Motif** à l’onglet Données supplémentaires. (CAMP-45139)
* Correction d’un problème qui pouvait se produire lorsque deux appels d’abonnement d’application avaient le même ID de Marketing Cloud (la valeur de clé de duplicata violait l’erreur de contrainte unique).
* Correction d’un problème susceptible d’entraîner des problèmes de lenteur lors du glisser-déposer d’activités dans un processus contenant une grande quantité d’activités **Requête** et **Lire l’audience**. (CAMP-44511)
* Correction d’une erreur qui pouvait se produire à la fin de la préparation du message transactionnel, empêchant le transfert des informations de redirection vers les serveurs de suivi.
* Correction d’un problème qui pouvait afficher des messages d’erreur lors de l’ouverture de modèles d&#39;import ou d’anciennes tâches d’importation après avoir personnalisé la ressource de processus. (CAMP-46183)
* Correction d’un problème qui empêchait l’exécution d’une activité **Lire l’audience** si elle était configurée avec un nom d’audience dynamique. (CAMP-46047)
* Correction d’un problème qui empêchait l’affichage du bouton **Exporter la liste**.
* Correction d’un problème qui pouvait entraîner l’échec du flux de travail **agrégats de Rapports**. (CAMP-45979)
* Correction d’un problème lors de la création d’une ressource personnalisée avec une clé composite personnalisée (contenu dynamique texte/date).
* Correction d’un problème qui pouvait empêcher l’affichage des données de transition de requête. (CAMP-45669)
* Correction de problèmes de consommation de mémoire liés à la publication de ressources personnalisées.
* Correction d’un problème survenant lors de la configuration d’une diffusion à envoyer à une date spécifique. Si la diffusion était alors définie pour être envoyée immédiatement une fois confirmée, la préparation de la diffusion a échoué et la date initialement spécifiée a été prise en compte. (CAMP-44107)
* Correction d’un problème qui pouvait empêcher l’ouverture de modèles transactionnels. (CAMP-47181)
* Correction d’un problème dans le processus de publication des messages transactionnels, en raison duquel les noms pouvaient dépasser la taille de chaîne autorisée pour les typologies et les règles de typologie de duplicata. (CAMP-47104)
* Correction d’un problème dans l’activité **API externe** qui se produisait lorsqu’un paramètre d’entrée renvoyait un enregistrement qui n’existait pas. (CAMP-47023)
* Correction d’un problème qui empêchait le connecteur SMPP de se reconnecter.
* Correction d’un problème qui se produisait dans l’activité **Transfert de fichier** lors du téléchargement d’un fichier contenant un point dans son nom. Les caractères qui suivent le point sont considérés comme l’extension du fichier. (CAMP-46624)
* Correction d’un problème qui empêchait l’exécution du pool de base de données, en raison duquel les messages transactionnels étaient bloqués dans la file d’attente du routeur.
* Correction d’une erreur qui n’empêchait pas l’envoi des logs de diffusion annulés.
* Correction d’un problème en raison duquel un processus échouait lors de l’utilisation d’une activité **AND-join**. L’activité a automatiquement modifié le jeu de Principal en dernière transition, même si elle affichait visuellement la première transition câblée. (CAMP-46900)
* Correction d’un problème en raison duquel l’état des adresses mises en quarantaine avec succès était incorrectement défini sur Valide, ce qui les supprimait de la quarantaine.
* Correction d’un problème en raison duquel les champs personnalisés ne s’affichaient pas s’ils contenaient des caractères spéciaux. (CAMP-46805)
* Correction d’un problème qui pouvait vous empêcher d’afficher une vue détaillée spécifique pour un profil. Cela se produisait si la ressource de profil avait été étendue avec des champs personnalisés avec l&#39;option **Ajouter une section de champs personnalisés** activée.
* Correction d’un problème qui pouvait renvoyer un code d’erreur 500 lors de l’envoi de événements transactionnels. (CAMP-46811)
* Correction d’un problème qui pouvait vous empêcher de recevoir des rapports planifiés par courriel. (CAMP-46891)
* Correction d’un problème survenant lors de la liaison d’une ressource personnalisée à la ressource de profil avec un lien simple de cardinalité 1. Lors de l’accès à un profil dont le champ de ressource personnalisée est vide, un message d’erreur s’affiche désormais au lieu d’une liste vide.
* Correction d’un problème lors de l’utilisation de la substitution de profil dans un processus en raison duquel la page ne chargeait pas les profils de diffusion lors de la sélection du profil à remplacer. (CAMP-46522)
* Correction d’une régression en raison de laquelle le processus technique de nettoyage de base de données **a1/> tentait d’abandonner les tables de travail de diffusion expirées, provoquant les erreurs suivantes : (CAMP-46536)**

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Correction de l’erreur suivante qui se produisait dans certains cas lors de l’utilisation d’un filtre personnalisé sur des ressources personnalisées : (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Correction d’un problème en raison duquel la préparation de la notification Push prenait trop de temps pour être terminée. Cela est dû à l&#39;absence d&#39;index sur les tables de travail transitoires.
* Correction d’une erreur qui pouvait se produire lors de l’utilisation de l’option **Dimension pour rapprocher** dans une activité **Réconciliation** dans un workflow si une relation était déjà définie entre une ressource personnalisée et une ressource de profil.
* Correction d’un problème qui se produisait lors de l’ajout de liens par le biais d’une activité **Réconciliation** ou **Enrichissement**. Les liens sélectionnés n’étaient pas affichés dans la transition de sortie.
* Correction d’un problème lors de l’utilisation d’une activité **Segmentation** avec des diffusions récurrentes dans un processus en raison duquel la diffusion était envoyée à une audience incorrecte. (CAMP-46275, CAMP-46470)
* Correction d’une erreur en raison de laquelle la publication de ressources personnalisées échouait lors de la tentative d’extension de la ressource Profil pour créer des dimensions de profil personnalisées pour le rapports dynamique. (CAMP-46266)
* Correction d’une erreur qui se produisait lors de l’ajout d’un lien à une table d’importation de fichier. Après avoir ajouté une activité **Enrichissement** à l&#39;activité **Importation de fichier**, le lien précédemment configuré a disparu. (CAMP-46557)
* Correction d’un problème lors de l’utilisation de ressources personnalisées liées à des données de Profil en raison duquel l’ordre d’affichage dans l’écran de configuration des détails était modifié lors de l’enregistrement. (CAMP-46312)
* Correction d’un problème en raison duquel vous ne pouviez pas afficher les données dans le rapports dynamique en raison de diffusions basées sur un mappage de diffusions personnalisé.
* Correction d’une erreur qui pouvait vous empêcher de sélectionner une collection avec une cible de ressources incorrecte dans une activité de requête de processus.
* Correction d’un problème en raison duquel le processus InMail pouvait valider incorrectement les rebonds en dur.
* Correction d’une erreur qui se produisait lors de l’ouverture d’un écran de profil en raison d’une erreur de lien.
* Correction d’un problème qui pouvait vous empêcher de supprimer les données GDPR du processus de nettoyage.
* Correction d’une erreur qui se produisait lorsque la configuration de planification était mise à jour manuellement avec le clavier de saisie dans les paramètres de planification de la diffusion de courriel.
* Correction d’un problème qui pouvait vous empêcher de modifier un profil en raison de paramètres incorrects dans l’unité d’organisation.
* Correction d’un problème en raison duquel le champ Extension de service était vide et impossible à définir dans les propriétés de courriel, même s’il était défini dans le modèle de diffusion.
* Correction d’un problème en raison duquel le traitement des BAT pouvait prendre plus de temps. (CAMP-45048)
* Correction d’un problème en raison duquel vous ne pouviez pas trier les colonnes dans un écran de présentation de profil.
* Correction d&#39;un problème de génération de miniatures qui pouvait se produire sur Azure dans les variantes de courrier électronique contenant des caractères chinois. (CAMP-47152)
* Correction d’une régression introduite dans la version 20.4 qui pouvait entraîner des taux d’ouverture incorrects pour Gmail en raison du filtrage des événements de suivi reçus des comptes Gmail. (CAMP-46504)
* Correction d’un problème qui pouvait vous empêcher d’importer du contenu HTML dans un modèle de message transactionnel. (CAMP-47318)
* Correction d’un problème qui pouvait ralentir l’affichage des rendus dans le rapport Rendu par courriel. (CAMP-46226)
* Correction d’un problème qui pouvait vous empêcher de publier des ressources personnalisées configurées avec un élément de type Liste dans la définition d’écran. (CAMP-47217)
* Correction d’un problème dans le concepteur de courrier électronique qui empêchait le rendu correct des séparateurs de ligne dans Microsoft Outlook lorsqu’ils étaient placés en haut du contenu du courrier électronique. (CAMP-46294)
* Correction d’un problème en raison duquel la réconciliation des indicateurs de performance clés avec le processus technique Adobe Analytics était bloquée. (CAMP-46576)
* Correction d’un problème dans le Concepteur de courriers électroniques en raison duquel les fragments ne s’affichaient pas automatiquement dans les zones de recherche lors de l’insertion de blocs de contenu. (CAMP-44205)
* Correction d’un problème dans le Concepteur de courriers électroniques en raison duquel des caractères indésirables s’affichaient dans les courriers électroniques envoyés lors de l’utilisation d’émoticônes dans des fragments. (CAMP-46621)
* Correction d’une régression introduite dans la version 20.4 du Concepteur de courriers électroniques qui affectait le composant Divider, ce qui entraînait des hauteurs de ligne supplémentaires et des distorsions d’image dans le contenu. (CAMP-46663)
* Correction d’un problème en raison duquel les boutons prêts à l’emploi restaient centrés lorsque le message était envoyé à une boîte aux lettres Outlook, même si ces boutons étaient alignés à droite ou à gauche dans le concepteur de courrier électronique. (CAMP-46466)
* Correction d’un problème qui empêchait l’actualisation de la liste des profils de test lors de la recherche de profils dans la prévisualisation de Designer de messagerie. (CAMP-45265)
* Correction d’un problème en raison duquel les profils de test personnalisés ne s’affichaient pas dans la liste lors de la recherche de profils dans la prévisualisation Designer de messagerie. (CAMP-45589)
* Correction d’un problème en raison duquel des dates incohérentes s’affichaient lors de la génération de graphiques de tendance à partir du rapport de synthèse de la diffusion. (CAMP-45521)
