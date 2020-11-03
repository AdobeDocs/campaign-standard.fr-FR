---
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
translation-type: tm+mt
source-git-commit: ca0d93129a259635427220dee050fe441346e0b5
workflow-type: tm+mt
source-wordcount: '2412'
ht-degree: 100%

---


# Dernière version{#latest-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Nouvelle version d&#39;octobre du panneau de contrôle** avec configuration de domaine utilisant des CNAME et nouvelles fonctionnalités de surveillance de base de données. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html).

## Version 20.4 - Octobre 2020 {#release-20-4---october-2020}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Populations témoins</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Vous pouvez désormais utiliser des <strong>Populations témoins</strong> pour mesurer l’impact de vos campagnes en excluant une partie de leur audience. Vous pourrez ensuite comparer les comportements de la population cible qui a reçu le message et ceux des contacts qui n’ont pas été ciblés. En fonction des logs d’envoi, vous pouvez également cibler une population témoin dans les futures campagnes.
</p>
<p>Pour plus d’informations, consultez la <a href="../../sending/using/control-group.md">documentation détaillée</a> et visualisez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">vidéo pratique</a>.
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
  <td> <p>Adobe Campaign prend désormais en charge OAuth pour l’authentification dans l’activité de workflow <strong>API externe</strong>. Cette nouvelle fonctionnalité permet à cette activité de communiquer avec des systèmes nécessitant une prise en charge OAuth.
</p>
<p>Pour plus d’informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a>.
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
  <td> <p>Nous sommes ravis d’annoncer Journey AI pour tous les clients Adobe Campaign Standard.</p>
  <p>Journey AI utilise un logiciel de machine learning (ML) avancé pour permettre aux entreprises d’optimiser la conception et la diffusion des parcours des clients en prédisant les préférences d’engagement de chaque individu.</p>
  <P>Journey AI comprend deux fonctions de ML :</p>
<ul> 
     <li> <strong>Évaluation prédictive de l’engagement</strong> - Identifie intelligemment le niveau d’engagement préféré des clients pour mieux cibler et personnaliser les messages afin d’augmenter les conversions et la rétention. Regardez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">vidéo pratique</a>.</li> 
     <li> <strong>Optimisation prédictive du temps d’envoi</strong> - Prévoit le meilleur moment pour envoyer des emails à chaque individu au cours d’une campagne afin d’optimiser les taux d’engagement et d’améliorer le retour sur investissement des campagnes par email. Regardez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">vidéo pratique</a>.</li>
    </ul>
  <p>Si vous souhaitez découvrir la prise en main de Journey AI, veuillez consulter la <a href="../../sending/using/predictive.md">documentation détaillée</a> et contacter votre gestionnaire de compte. Notez que si Journey AI est disponible gratuitement pour les clients Campaign existants, un coût d’implémentation correspondant à environ 50 heures s’applique.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* **Gestion de la confidentialité** : le champ **Option d’Opt-out du CCPA**, qui était disponible via l’interface Campaign et l’API, est maintenant également pris en charge par Privacy Core Service. Ce champ permet aux utilisateurs d’Adobe Campaign de déterminer si un client s’est opposé à la vente de ses informations personnelles. [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#ccpa)
* **Améliorations de l’exécution du workflow** (bêta) : dans le cadre d’une initiative mondiale autour des workflows, des améliorations majeures ont été apportées pour stabiliser la gestion de la mémoire, réduire la latence et optimiser la mémoire consommée par les workflows pendant l’exécution. Ces améliorations sont actuellement en version bêta et ne sont disponibles que pour un certain nombre de clients. La disponibilité générale est prévue pour début 2021.
* Pour améliorer la sécurité, Campaign utilise désormais un **mécanisme de signature** pour le tracking des liens dans les emails.
* La configuration des applications mobiles a été améliorée avec des **messages d’erreur plus clairs** lors du téléchargement de certificats iOS ou de clés Android.
* La **gestion des erreurs SMS** a été améliorée afin d’éviter qu’un trop grand nombre de profils ne soit ajouté à la liste de quarantaine. Par défaut, les erreurs SMS sont désormais configurées en tant qu’erreurs soft plutôt qu’en tant qu’erreurs hard. Consultez à ce sujet [cette page](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html).

**Améliorations du Concepteur d’email**

* Nous avons amélioré l’expérience utilisateur dans le concepteur d’email grâce à la **nouvelle aide contextuelle dynamique** qui connecte entièrement l’interface utilisateur et la documentation, ce qui permet d’accéder facilement aux derniers contenus d’aide.
* Correction d’un problème en raison duquel les sauts de ligne dans un message étaient supprimés lors de la modification de sa version texte. (CAMP-44483)
* Correction d’un problème qui empêchait la génération et la synchronisation automatiques de la version en texte brut d’un modèle HTML. (CAMP-44195)
* Correction d’un problème qui pouvait se produire lors du redimensionnement des images. Une fois les messages envoyés, les images ne s’affichaient pas correctement dans Microsoft Outlook. (CAMP-44656)
* Correction d’un problème qui survenait lors de l’insertion d’un bouton et de la définition de sa largeur sur « auto ». Une fois le message envoyé, le contenu du bouton ne s’affichait pas entièrement. (CAMP-44560)
* Correction d’un problème qui survenait lors du téléchargement de contenus à partir d’un fichier HTML joint. Une fois le message envoyé à une adresse Gmail, la page CSS n’était pas appliquée, ce qui provoquait un problème de rendu. (CAMP-44085)
* Correction d’un problème qui empêchait la mise à jour des fragments de contenu précédemment utilisés dans un message lorsqu’ils étaient modifiés directement dans le modèle de contenu. (CAMP-43973)
* Correction d’un problème avec la barre de recherche **Fragments**. Lors de la recherche d’un fragment existant, la barre de recherche n’affichait aucun résultat. (CAMP-44223)
* Correction d’un problème lié aux barres de recherche **Blocs de contenu** et **Fragments**. Lors de l’utilisation de l’une des barres de recherche, les résultats ne s’affichaient que si vous cliquiez sur **Afficher plus de résultats...**. (CAMP-44205)
* Correction d’un problème qui empêchait l’application du remplissage entre le texte et les images dans Microsoft Outlook. (CAMP-45370)
* Correction d’un problème lors de la duplication d’un fragment. Après avoir dupliqué le fragment, il manquait des lignes HTML dans le fragment d’origine. (CAMP-45207)
* Correction d’une erreur qui provoquait des problèmes de rendu dans Microsoft Outlook. (CAMP-44749)
* Correction d’une erreur qui se produisait lors de la modification du remplissage du **composant de structure** dans un modèle de diffusion. Les balises CSS ne reportaient pas les modifications apportées au remplissage, ce qui provoquait un problème de rendu. (CAMP-45381)
* Correction d’un problème lors du téléchargement d’une image. La hauteur de l’image était automatiquement définie sur 0, ce qui provoquait un problème de rendu. (CAMP-45366)

**Autres changements**

* Des mécanismes de reprise ont été ajoutés en cas d’erreur lors de la tentative d’importation d’une audience Experience Platform à l’aide d’une activité **Lecture d’audience**. (CAMP-43947, CAMP-43366)
* Les entités organisationnelles sont désormais automatiquement définies pour correspondre à l’entité organisationnelle de l’utilisateur qui crée le profil ou l’entité. Les entités organisationnelles ne peuvent plus être supprimées et laissées vides.
* Lors de la publication d’une ressource personnalisée, un pop-up de confirmation s’affiche maintenant après la préparation.
* Le message pop-up qui s’affiche en cas d’échec d’une ressource personnalisée a été amélioré pour une plus grande clarté.
* L’éditeur d’expression des workflows a été amélioré afin d’éviter les erreurs d’exécution. De [nouvelles fonctions](../../automating/using/customizing-workflow-external-parameters.md) sont disponibles : il est possible de les appliquer dans toutes les activités qui permettent d’utiliser des variables d’événement après avoir appelé un workflow avec des paramètres externes. De plus, une info-bulle s’affiche désormais dans l’éditeur d’expression avec la description de la fonction.
* [De nouveaux filtres ont été ajoutés à la liste des événements transactionnels.](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) Ils permettent de filtrer les configurations des événements en fonction de leur statut, ainsi que de la dernière réception d’un événement.
* Les logs qui s’affichent lors de l’exportation de packages ont été rendus plus précis et détaillés sur les erreurs rencontrées en cas d’échec.
* Après l’envoi d’un message, vous pouvez désormais rechercher, filtrer et exporter la liste des [URL trackées](../../sending/using/tracking-messages.md).
* La [synchronisation automatique entre Launch et Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) fait désormais l’objet d’une disponibilité générale (GA) et est activée par défaut.
* La taille des packages d’exportation de workflow a été optimisée en supprimant l’exportation d’envoi de BAT.
* Un nouveau message a été ajouté pour afficher la taille du fichier téléchargé dans l’activité de **Transfert de fichier**.
* Les messages d’erreur relatifs aux jetons de session non valides ont été améliorés.
* Un nouveau mécanisme empêche désormais l’ajout des événements de tracking des proxies aux logs et aux rapports de tracking.
* Un nouveau message d’avertissement a été ajouté pour faciliter le débogage des activités de gestion des données connectées à une activité de diffusion.
* Les libellés de l’espace de travail de rapport ont été améliorés.
* Une nouvelle étape de validation a été ajoutée pour empêcher la suppression des objets techniques dans les messages transactionnels.
* Un nouveau filtre sur le statut de la diffusion a été ajouté dans l’onglet **Liste des exécutions** d’un message transactionnel afin de faciliter la résolution des problèmes.
* Pour améliorer les performances et optimiser le temps d’exécution, les index inutilisés ont été supprimés, en fonction des statistiques d’utilisation des tables identifiées dans l’analyse préliminaire pour plus de 350 clients. Les tables affectées sont les suivantes : nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience, xtkworkflow

**Correctifs**

* Correction d’un problème qui empêchait l’utilisation d’un lien de destination pour les notifications push ou la messagerie In-App lorsque le tracking était activé.
* Correction d’un problème en raison duquel une priorité élevée dans les messages transactionnels n’était pas respectée en cas de diffusion en masse importante.
* Correction d’un problème qui pouvait empêcher d’affecter des marques à un email transactionnel. Plusieurs messages d’erreur peuvent s’afficher pendant l’étape de publication. (CAMP-44988)
* Correction d’un problème dans l’interface utilisateur du workflow en raison duquel les informations ne pouvaient pas être enregistrées dans les champs qui demandaient des valeurs numériques. (CAMP-44025)
* Correction d’un problème qui pouvait afficher un message d’erreur lors de l’utilisation d’une activité **Test** dans un workflow de modèle d’import. (CAMP-42910)
* Correction d’un problème qui se produisait lors de l’utilisation d’une activité **Lecture d’audience** contenant un champ de type énumération, et connectée à des activités **Union** ou **Enrichissement**. (CAMP-42795)
* Correction d’un problème dans les rapports dynamiques lors de l’utilisation de segments d’usine pour filtrer les données dans les rapports. (CAMP-42627)
* Correction d’un problème en raison duquel il n’était pas possible de définir une activité **Planificateur** sur 12 h. (CAMP-42674)
* Correction d’un problème qui pouvait interrompre l’envoi de messages SMS lorsque la connexion SMPP était instable. (CAMP-42789)
* Correction d’un problème qui empêchait l’affichage du bouton **Arrêter la préparation** après l’actualisation de la page. (CAMP-42721)
* Correction d’un problème qui empêchait l’affichage des pourcentages des rapports de hot clicks lors de l’importation de contenu à partir d’une URL. (CAMP-44468)
* Correction d’un problème qui pouvait afficher une erreur de délai dépassé lors de la sélection d’un profil à utiliser dans le contexte de la substitution de profil. (CAMP-44746)
* Correction d’un problème en raison duquel les instances ne fonctionnaient pas après le déploiement de ressources personnalisées contenant des définitions de liens incorrectes. (CAMP-44406)
* Correction d’un problème en raison duquel des entités liées vides (typologies, marques, etc.) étaient créées après avoir copié et collé une diffusion dans un modèle de campagne. (CAMP-44765)
* Correction d’un problème qui empêchait l’envoi de BAT en raison d’une gestion incorrecte des tables de préparation de diffusion en cas de blocage de la base de données ou de redémarrage simple de la base de données sur Azure.
* Correction d’un problème qui pouvait empêcher de supprimer des liens avec du contenu Experience Manager dans une diffusion configurée avec du contenu multilingue. (CAMP-44029)
* Correction d’un problème dans les rapports dynamiques qui pouvait afficher un message d’erreur lors de la tentative de filtrage des dimensions.  (CAMP-43097)
* Correction d’un problème en raison duquel un écran vide s’affichait lors de l’accès à des profils sur une instance configurée avec des ressources personnalisées contenant des définitions de liens spécifiques. (CAMP-41009)
* Correction d’un problème dans les workflows qui pouvait se produire lors de l’utilisation d’une activité **Enrichissement** avec deux activités d’entrée dont les deux ressources cibles étaient liées. (CAMP-42133)
* Correction d’un problème en raison duquel les workflows d’importation fonctionnaient en boucle lors de l’utilisation d’une activité de **Transfert de fichier**. (CAMP-43754)
* Correction d’un problème en raison duquel les doublons n’étaient pas pris en compte lors de la création d’un profil avec des logs exportés. (CAMP-45031)
* Correction d’un problème en raison duquel les données étaient incohérentes entre les rapports d’Adobe Campaign et les rapports exportés dans des fichiers PDF. (CAMP-43010)
* Correction d’une erreur qui entraînait l’échec du workflow de diffusion de courrier en cas d’utilisation de champs de données existants dans des fonctions. (CAMP-42737)
* Correction d’un problème lors de l’import de packages contenant des événements transactionnels et des modèles de message. Le processus d’importation s’arrêtait à 5 %. (CAMP-42544)
* Correction d’un problème qui provoquait une erreur (Uncatch TypeError) après modification de l’activité **Enrichissement** et ajout de données supplémentaires dans un workflow. (CAMP-41877)
* Correction d’une erreur qui empêchait la suppression d’un workflow. Les logs devaient être purgés pour supprimer le workflow. (CAMP-44144)
* Correction d’une erreur lors de la création d’une landing page avec du code HTML. Les cases à cocher obligatoires n’étaient pas reconnues dans Campaign et n’étaient pas disponibles dans la landing page publiée. (CAMP-44181)
* Correction d’un problème en raison duquel les workflows fonctionnaient en boucle lors de l’utilisation de l’activité **Attente**. (CAMP-43981)
* Correction d’un problème lors de l’envoi de messages transactionnels en raison duquel plusieurs adresses email étaient ciblées plusieurs fois dans une même diffusion. (CAMP-44202)
* Correction d’une erreur lors de l’utilisation de la substitution de profil avec la personnalisation targetData. (CAMP-44996)
* Correction d’un problème en raison duquel la prévisualisation de diffusion échouait lors de l’export d’un modèle de diffusion dans un package. (CAMP-44084)
* Correction d’un problème qui empêchait l’envoi de BAT aux profils de test lors de l’utilisation de mappings de ciblage personnalisés. (CAMP-43701)
* Correction d’une erreur qui se produisait dans les workflows lors de l’utilisation de l’activité **Lecture d’audience** et du ciblage d’une audience configurée avec une dimension de ciblage autre que **Profil**.  (CAMP-41885)
* Correction d’un problème qui provoquait des erreurs lorsque le workflow technique **updateEventsStatus** prenait trop de temps pour récupérer l’historique des événements (si le workflow était arrêté). Le champ d’agrégat « sumQueueTime » inutilisé a été supprimé du workflow pour résoudre le problème. (CAMP-43920)
* Correction d’un problème de mémoire lors du déploiement de ressources personnalisées. (CAMP-42909)
* Correction d’un problème de messagerie transactionnelle en raison duquel des attributs manquaient dans des collections. Désormais, tous les attributs manquants sont définis avec une valeur par défaut et inclus dans la payload. (CAMP-42882)
* Correction d’un problème qui pouvait affecter les performances lors de requêtes de logs de diffusion d’événements en temps réel. (CAMP-42759)
* Correction d’une erreur qui se produisait lors de l’utilisation d’extensions de fichier en majuscules avec des ressources partagées. (CAMP-44159)
* Correction d’un problème en raison duquel un message d’erreur s’affichait lors du test de la connexion à un compte externe avant sa création. Le bouton **Tester la connexion** s’affiche désormais uniquement une fois que le compte externe a été créé.
* Correction d’un problème en raison duquel les messages étaient en attente après le redémarrage du MTA amélioré sur les instances configurées avec partage.
* Correction d’un problème en raison duquel le nombre de profils actifs ne correspondait pas au nombre effectif de diffusions envoyées.
* Correction d’un problème susceptible d’entraîner une latence lors de la recherche de ressources dans l’éditeur de requêtes d’un workflow.
* Correction d’un problème lors de la sélection de l’option **Définir les champs à prendre en compte dans la recherche texte** d’une ressource personnalisée. Si la liste de champs n’était pas renseignée, la publication de ressources personnalisées échouait.
* Correction d’un problème de performances lors de l’affichage de l’aperçu des ressources personnalisées avec un volume important de données.
* Correction d’un problème qui empêchait l’import d’une diffusion à l’aide de substitutions de profils.
* Correction d’un problème lors de l’utilisation de la substitution de profil qui empêchait l’envoi immédiat des BAT si la diffusion était planifiée.
* Correction d’un problème survenant lors du téléchargement d’une clé Android pour une application mobile. Le message qui s’affichait après le téléchargement de la clé affichait la valeur de l’ancienne clé.
* Correction d’un problème qui empêchait la création de profils de test à partir de messages transactionnels après la création d’une configuration d’événement avec une collection ne contenant aucun attribut.
* Correction d’un problème qui pouvait vous empêcher de publier des ressources personnalisées après la création d’un nouveau filtre à l’aide d’un agrégat.
* Correction d’un problème en raison duquel un taux d’ouverture de tracking incorrect pour les destinataires Gmail était provoqué par le proxy d’image Gmail.
* Correction d’un problème qui provoquait des erreurs de mémoire insuffisante lors de l’import d’un package.
* Correction d’un problème en raison duquel l’action de dissociation d’Experience Manager échouait lorsque le contenu Experience Manager incluait un chemin d’accès avec un caractère « %20 ».
* Correction d’une erreur sur des libellés lors de la duplication d’activités de workflow.
* Correction d’un problème lié au sélecteur de message transactionnel dans une landing page lorsque l’option **Déclencher l’envoi d’un message** était sélectionnée.
* Correction d’un problème lié aux messages transactionnels ou aux diffusions récurrentes qui empêchait l’initialisation du statut de la diffusion avec la valeur par défaut appropriée. Les logs d’erreurs ont également été améliorés.
* Correction d’un problème lors de l’extension du schéma **Abonnement à une application** (appSubscriptionRcp) avec un lien de profil utilisant un champ personnalisé. L’index n’était pas créé automatiquement, ce qui pouvait affecter le temps d’envoi des notifications push. (CAMP-41120)

