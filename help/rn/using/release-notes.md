---
title: Dernière version
description: Cette page détaille le contenu de la dernière version du Campaign Standard
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 893cd3a07063f8349dfeeae0f3274a6f54bf04f7
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 4%

---


# Dernière version{#latest-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

## Version 20.4 - Octobre 2020        {#release-20-4---october-2020}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Populations témoins</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Vous pouvez désormais utiliser <strong>des Populations témoins</strong> pour mesurer l’impact de vos campagnes en excluant une partie de leur audience. Vous pourrez ensuite comparer le comportement de la population de cibles qui a reçu le message au comportement des contacts qui n'ont pas été ciblés. En fonction des journaux d’envoi, vous pouvez également cible une Population témoin dans les futures campagnes.
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API externe - Prise en charge OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>adobe campaign prend désormais en charge OAuth pour l’authentification dans l’activité de processus des API <strong></strong> externes. Cette nouvelle fonctionnalité permet à cette activité de communiquer avec des systèmes nécessitant une prise en charge OAuth.
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Intégration de Journey AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Nous sommes ravis d'annoncer Journey AI pour tous les clients Adobe Campaign Standard.</p>
  <p>L’IA Journey utilise l’apprentissage automatique avancé (ML) pour permettre aux sociétés d’optimiser la conception et la diffusion des voyages des clients en prédisant les préférences d’engagement de chaque individu.</p>
  <P>Journey AI comprend deux fonctions ML :</p>
<ul> 
     <li> <strong>Score d’engagement prédictif</strong> - Identifie intelligemment le niveau d’engagement préféré des clients afin de mieux cible et de personnaliser les messages pour augmenter les conversions et la rétention. Regardez la vidéo <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html"></a>pratique.</li> 
     <li> <strong>Optimisation</strong> du temps d’envoi prédictif - Prévoit le meilleur moment pour envoyer des courriers électroniques à chaque individu d’une campagne afin d’optimiser les taux d’engagement et d’améliorer le retour sur investissement des campagnes par courrier électronique. Regardez la vidéo <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html"></a>pratique.</li>
    </ul>
  <p>Si vous souhaitez apprendre à démarrer avec Journey AI, veuillez consulter la documentation <a href="../../sending/using/predictive.md"></a> détaillée et contacter votre gestionnaire de compte. Notez que si Journey AI est disponible gratuitement pour les clients Campaign existants, il y a un coût d'implémentation d'environ 50 heures.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* **Gestion** de la confidentialité : le champ d’exclusion **de l’** ACCP, qui était disponible via l’interface et l’API Campaign, est maintenant également pris en charge par le service principal de confidentialité. Ce champ permet aux utilisateurs d’Adobe Campaign de déterminer si un consommateur a choisi de ne pas vendre de renseignements personnels. [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#ccpa)
* **Améliorations** de l’exécution du flux de travaux (bêta) : dans le cadre d&#39;une initiative mondiale autour des workflows, des améliorations majeures ont été apportées pour stabiliser la gestion de la mémoire, réduire la latence et optimiser la mémoire consommée par les workflows pendant l&#39;exécution. Ces améliorations sont actuellement en version bêta et ne sont disponibles que pour un ensemble de clients. La disponibilité générale est prévue pour le début de 2021.
* Pour améliorer la sécurité, Campaign utilise désormais un mécanisme **de** signature pour le suivi des liens dans les courriers électroniques.
* La configuration des applications mobiles a été améliorée avec des messages **d’erreur** plus clairs lors du téléchargement de certificats iOS ou de clés Android.
* Un **nouveau mappage** de diffusion (mapRtEventAppSubRcp) est désormais disponible pour les messages Push transactionnels ciblant les profils. La diffusion, l&#39;exclusion et les logs de tracking de ces diffusions seront désormais disponibles dans les tables wideLogAppSubRcp, excludeLogAppSubRcp et trackingLogAppSubRcp. Ceci résout un problème en raison duquel l’analyse de l’diffusion échouait lors de l’envoi d’un message push transactionnel utilisant la dimension de cible de **Profil** .
* **La gestion des** erreurs SMS a été améliorée afin d&#39;éviter que trop de profils ne soient ajoutés à la liste de quarantaine. Par défaut, les erreurs SMS sont désormais configurées en tant qu’erreurs paramétrées plutôt qu’en tant qu’erreurs dures. Refer to [this page](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html).

**Améliorations du Concepteur d’email**

* Nous avons amélioré l’expérience des utilisateurs dans le concepteur de courriels grâce à la **nouvelle aide** contextuelle dynamique qui connecte entièrement l’interface utilisateur et la documentation, ce qui permet d’accéder facilement aux derniers contenus d’aide.
* Correction d’un problème en raison duquel les sauts de ligne dans un message étaient supprimés lors de la modification de sa version de texte. (CAMP-44483)
* Correction d’un problème qui empêchait la génération et la synchronisation automatiques de la version en texte brut d’un modèle HTML. (CAMP-44195)
* Correction d’un problème qui pouvait se produire lors du redimensionnement des images. Une fois les messages envoyés, les images ne s&#39;affichaient pas correctement dans Microsoft Outlook. (CAMP-44656)
* Correction d’un problème survenant lors de l’insertion d’un bouton et de la définition de sa largeur sur &quot;auto&quot;. Une fois le message envoyé, le contenu du bouton ne s’affichait pas entièrement. (CAMP-44560)
* Correction d’un problème survenant lors du transfert de contenu à partir d’un fichier HTML joint. Une fois le message envoyé à une adresse Gmail, la page CSS n’était pas appliquée, ce qui provoquait un problème de rendu. (CAMP-44085)
* Correction d’un problème qui empêchait la mise à jour des fragments de contenu précédemment utilisés dans un message lorsqu’ils étaient modifiés directement dans le modèle de contenu. (CAMP-43973)
* Correction d’un problème de la barre de recherche **Fragments** . Lors de la recherche d’un fragment existant, la barre de recherche n’affichait aucun résultat. (CAMP-44223)
* Correction d’un problème lié aux barres de recherche Blocs **de** contenu et **Fragments** . Lors de l&#39;utilisation de l&#39;une des barres de recherche, les résultats ne s&#39;affichaient que si vous cliquiez sur **Afficher plus de résultats...**. (CAMP-44205)
* Correction d’un problème qui empêchait l’application du remplissage entre le texte et les images dans Microsoft Outlook. (CAMP-45370)
* Correction d’un problème lors de la duplication d’un fragment. Après avoir dupliqué le fragment, il manquait des lignes HTML dans le fragment d’origine. (CAMP-45207)
* Correction d’une erreur qui provoquait des problèmes de rendu dans Microsoft Outlook. (CAMP-44749)
* Correction d’une erreur qui se produisait lors de la modification du remplissage du composant **de** structure dans un modèle de diffusion. Les balises CSS ne reportaient pas les modifications apportées au remplissage, ce qui provoquait un problème de rendu. (CAMP-45381)
* Correction d’un problème lors du téléchargement d’une image. La hauteur de l’image était automatiquement définie sur 0, ce qui provoquait un problème de rendu. (CAMP-45366)

**Autres changements**

* Des mécanismes de nouvelle tentative ont été ajoutés en cas d&#39;erreur lors de la tentative d&#39;importation d&#39;une audience Experience Platform à l&#39;aide d&#39;une activité d&#39;audience **de** lecture. (CAMP-43947, CAMP-43366)
* Les unités organisationnelles sont désormais automatiquement définies pour correspondre à l&#39;unité organisationnelle de l&#39;utilisateur qui crée le profil ou l&#39;entité. Les unités organisationnelles ne peuvent plus être supprimées et laissées vides.
* Lors de la publication d’une ressource personnalisée, une fenêtre contextuelle de confirmation s’affiche maintenant après la préparation.
* Le message contextuel qui s’affiche en cas d’échec d’une ressource personnalisée a été amélioré pour une meilleure clarté.
* L’éditeur d’expressions dans les workflows a été amélioré afin d’éviter les erreurs d’exécution. [De nouvelles fonctions](../../automating/using/customizing-workflow-external-parameters.md) sont disponibles : elles peuvent être utilisées dans toutes les activités qui vous permettent d’utiliser des variables de événement après avoir appelé un processus avec des paramètres externes. De plus, une info-bulle s’affiche désormais dans l’éditeur d’expressions avec la description de la fonction.
* De nouveaux filtres ont été ajoutés à la liste des événements transactionnels. Ils vous permettent de filtrer les configurations de événement en fonction de leur état, ainsi que de la dernière réception d’un événement.
* Les journaux qui s&#39;affichent lors de l&#39;exportation de packages ont été rendus plus précis et détaillés sur les erreurs rencontrées en cas d&#39;échec.
* Après l’envoi d’un message, vous pouvez désormais rechercher, filtrer et exporter la liste des URL [](../../sending/using/tracking-messages.md)suivies.
* La [synchronisation automatique entre Launch et Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) est désormais GA et activée par défaut.
* Les messages transactionnels peuvent être envoyés avec une priorité élevée, même en cas de charge de diffusion importante.
* La taille des packages d&#39;exportation de flux de travail a été optimisée en supprimant l&#39;exportation de BAT d&#39;envoi.
* Un nouveau message a été ajouté pour afficher la taille du fichier téléchargé dans l’activité de transfert **de** fichier.
* Les messages d&#39;erreur relatifs aux jetons de session non valides ont été améliorés.
* Un nouveau mécanisme empêche désormais l’ajout de proxies aux logs de tracking et aux rapports pour le suivi des événements.
* Un nouveau message d’avertissement a été ajouté pour aider au débogage des activités d’data Management connectées à une activité de diffusion.
* Les étiquettes de l’espace de travail rapports ont été améliorées.
* Une nouvelle étape de validation a été ajoutée pour empêcher la suppression des objets techniques dans les messages transactionnels.
* Un nouveau filtre sur l’état de la diffusion a été ajouté dans l’onglet **Exécution de la liste** d’un message transactionnel afin d’améliorer la résolution des problèmes.
* Pour améliorer les performances et optimiser le temps d’exécution, les index inutilisés ont été supprimés, en fonction des statistiques d’utilisation des tableaux identifiés dans l’analyse préliminaire pour plus de 350 clients. Les tableaux affectés sont les suivants : nmsaddressStatus, nmscamcampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsRecipient, nmsseedmembers, nmsservice, nmssubhistorcp, nmsaudience, xtkworkflow

**Correctifs**

* Correction d’un problème qui empêchait l’utilisation d’un lien de destination pour les notifications Push ou la messagerie in-app lorsque le suivi était activé.
* Correction d’un problème qui pouvait vous empêcher d’affecter des marques à un courrier électronique transactionnel. Plusieurs messages d’erreur peuvent s’afficher pendant l’étape de publication. (CAMP-44988)
* Correction d’un problème dans l’interface utilisateur du processus en raison duquel les informations ne pouvaient pas être enregistrées dans les champs demandant des valeurs numériques. (CAMP-44025)
* Correction d’un problème qui pouvait afficher un message d’erreur lors de l’utilisation d’une activité de **test** dans un processus de modèle d&#39;import. (CAMP-42910)
* Correction d’un problème qui se produisait lors de l’utilisation d’une activité d’audience **** Lu contenant un champ de type de énumération et connecté à des activités **Union** ou **Enrichissement** . (CAMP-42795)
* Correction d’un problème dans les rapports dynamiques lors de l’utilisation de segments prêts à l’emploi pour filtrer les données dans les rapports. (CAMP-42627)
* Correction d’un problème en raison duquel vous ne pouviez pas définir une activité **Planificateur** sur 12 heures. (CAMP-42674)
* Correction d’un problème qui pouvait interrompre l’envoi de messages SMS lorsque la connexion SMPP était instable. (CAMP-42789)
* Correction d’un problème qui empêchait l’affichage du bouton **Arrêter la préparation** après l’actualisation de la page. (CAMP-42721)
* Correction d’un problème qui empêchait l’affichage des pourcentages des rapports de clic rapide lors de l’importation de contenu à partir d’une URL. (CAMP-44468)
* Correction d’un problème qui pouvait afficher une erreur de délai d’expiration lors de la sélection d’un profil à utiliser dans le contexte de la substitution de profil. (CAMP-44746)
* Correction d’un problème en raison duquel les instances ne fonctionnaient pas après le déploiement de ressources personnalisées contenant des définitions de lien incorrectes. (CAMP-44406)
* Correction d’un problème en raison duquel des entités liées vides (typologies, marques, etc.) étaient créées. après avoir copié et collé une diffusion dans un modèle de campagne. (CAMP-44765)
* Correction d&#39;un problème qui empêchait l&#39;envoi de BAT en raison d&#39;une gestion incorrecte des tables de préparation de diffusion en cas de blocage de la base de données ou de redémarrage simple de la base de données sur Azure.
* Correction d’un problème qui pouvait vous empêcher de supprimer des liens avec du contenu Experience Manager dans une diffusion configurée avec du contenu multilingue. (CAMP-44029)
* Correction d’un problème dans les rapports dynamiques qui pouvait afficher un message d’erreur lors de la tentative de filtrage des dimensions.  (CAMP-43097)
* Correction d’un problème en raison duquel un écran vide s’affichait lors de l’accès à des profils sur une instance configurée avec des ressources personnalisées contenant des définitions de liens spécifiques. (CAMP-41009)
* Correction d’un problème dans les workflows qui pouvait se produire lors de l’utilisation d’une activité **d’Enrichissement** avec deux activités d’entrée dont les deux ressources de cible étaient liées. (CAMP-42133)
* Correction d’un problème en raison duquel les workflows d’importation étaient en boucle lors de l’utilisation d’une activité de transfert **de** fichier. (CAMP-43754)
* Correction d’un problème en raison duquel les duplicata n’étaient pas pris en compte lors de la création d’un profil avec des journaux exportés. (CAMP-45031)
* Correction d’un problème en raison duquel les données étaient incohérentes entre les rapports dans Adobe Campaign et les rapports exportés dans des fichiers PDF. (CAMP-43010)
* Correction d’une erreur qui entraînait l’échec du flux de travaux de diffusion de messagerie directe lors de l’utilisation de champs de données existants dans des fonctions. (CAMP-42737)
* Correction d’un problème lors de l’importation de packs incluant des événements transactionnels et des modèles de message. Le processus d&#39;importation s&#39;est arrêté à 5 %. (CAMP-42544)
* Correction d’un problème qui provoquait une erreur (Uncatch TypeError) après modification de l’activité de l’ **Enrichissement** et ajout de données supplémentaires dans un processus. (CAMP-41877)
* Correction d’une erreur qui empêchait la suppression du flux de travail. Les journaux devaient être purgés pour supprimer le flux de travail. (CAMP-44144)
* Correction d’une erreur lors de la création d’un landing page avec du code HTML. Les cases à cocher obligatoires n’étaient pas reconnues à Campaign et n’étaient pas disponibles dans le landing page publié. (CAMP-44181)
* Correction d’un problème en raison duquel les workflows étaient en boucle lors de l’utilisation de l’activité **Attente** . (CAMP-43981)
* Correction d’un problème lors de l’envoi de messages transactionnels en raison duquel plusieurs adresses électroniques étaient ciblées plusieurs fois dans une même diffusion. (CAMP-44202)
* Correction d’une erreur lors de l’utilisation de la substitution de profil avec la personnalisation de targetData. (CAMP-44996)
* Correction d’un problème en raison duquel la prévisualisation de diffusion échouait lors de l’exportation d’un modèle de diffusion dans un package. (CAMP-44084)
* Correction d’un problème qui empêchait l’envoi de BAT aux profils de test lors de l’utilisation de mappings de ciblage personnalisés. (CAMP-43701)
* Correction d’une erreur qui se produisait dans les workflows lors de l’utilisation de l’activité d’Audience **de** lecture et du ciblage d’une audience configurée avec une dimension de ciblage autre que le **Profil**.  (CAMP-41885)
* Correction d’un problème qui provoquait des erreurs lorsque le processus technique **updateEventsStatus** prenait trop de temps pour récupérer l’historique des événements (lorsque le processus était arrêté). Le champ d&#39;agrégat &quot;sumQueueTime&quot; inutilisé a été supprimé du flux de travail pour résoudre le problème. (CAMP-43920)
* Correction d’un problème de mémoire lors du déploiement de ressources personnalisées. (CAMP-42909)
* Correction d’un problème de messagerie transactionnelle en raison duquel les attributs manquaient dans les collections. Désormais, tous les attributs manquants sont définis avec une valeur par défaut et inclus dans la charge utile. (CAMP-42882)
* Correction d’un problème qui pouvait affecter les performances lors de l’interrogation de logs de diffusion de événement en temps réel. (CAMP-42759)
* Correction d’une erreur qui se produisait lors de l’utilisation d’extensions de fichier en majuscules avec des ressources partagées. (CAMP-44159)
* Correction d’un problème en raison duquel un message d’erreur s’affichait lors du test de la connexion à un compte externe avant sa création. Le bouton **Tester la connexion** s’affiche désormais uniquement une fois le compte externe créé.
* Correction d’un problème en raison duquel les messages étaient en attente après le redémarrage de la MTA améliorée sur les instances configurées avec le partage.
* Correction d’un problème en raison duquel le nombre de profils principaux ne correspondait pas au nombre effectif de diffusions envoyées.
* Correction d’un problème susceptible d’entraîner une latence lors de la recherche de ressources dans l’éditeur de requêtes d’un processus.
* Correction d’un problème lors de la sélection des champs **Spécifier à prendre en compte dans l’option de recherche** de texte d’une ressource personnalisée. Si la liste de champ n&#39;était pas renseignée, la publication de ressources personnalisées a échoué.
* Correction d’un problème de performances lors de l’affichage de l’aperçu des ressources personnalisées avec un volume important de données.
* Correction d’un problème qui empêchait l’importation d’une diffusion à l’aide de substitutions de profil.
* Correction d’un problème lors de l’utilisation de la substitution de profil qui empêchait l’envoi immédiat des BAT si la diffusion était planifiée.
* Correction d’un problème survenant lors du chargement d’une clé Android pour une application mobile. Le message qui s’affichait après le chargement de la clé affichait la valeur de l’ancienne clé.
* Correction d’un problème qui empêchait la création de profils de test à partir de messages transactionnels après la création d’une configuration de événement avec une collection ne contenant aucun attribut.
* Correction d’un problème qui pouvait vous empêcher de publier des ressources personnalisées après la création d’un nouveau filtre à l’aide d’un agrégat.
* Correction d’un problème en raison duquel un taux d’ouverture de suivi incorrect pour les destinataires Gmail était provoqué par le proxy d’image Gmail.
* Correction d’un problème qui provoquait des erreurs de mémoire insuffisante lors de l’importation d’un package.
* Correction d’un problème en raison duquel l’action de dissociation du Experience Manager échouait lorsque le contenu du Experience Manager incluait un chemin d’accès avec un caractère &quot;%20&quot;.
* Correction d’une erreur sur les étiquettes lors de la duplication des activités de processus.
* Correction d’un problème lié au sélecteur de message transactionnel dans un landing page lorsque l’option **Début d’envoi de message** était sélectionnée.
* Correction d’un problème lié aux messages transactionnels ou aux diffusions récurrentes qui empêchait l’initialisation de l’état de la diffusion avec la valeur par défaut appropriée. Les journaux d’erreurs ont également été améliorés.
* Correction d’un problème lors de l’extension de l’ **Abonnement à un schéma d’application** (appSubscriptionRcp) avec un lien de profil utilisant un champ personnalisé. L&#39;index n&#39;a pas été créé automatiquement, ce qui peut affecter le temps d&#39;envoi des notifications Push. (CAMP-41120)

