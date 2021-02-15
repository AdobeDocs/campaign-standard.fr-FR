---
solution: Campaign Standard
product: campaign
title: Notes de mise à jour              2020
description: Cette page répertorie toutes les versions 2020 d'Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 36e0f6be4dc8c1a6e4b0d8878d190f2abce99fcd
workflow-type: tm+mt
source-wordcount: '5329'
ht-degree: 100%

---


# Notes de mise à jour 2020{#release-notes-2020}

[Calendrier des versions](https://helpx.adobe.com/fr/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2019.md) | [Fonctionnalités obsolètes](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr)

![](assets/do-not-localize/cp-icon.png) **Nouvelle version de juin du panneau de contrôle** avec surveillance des profils actifs, audit de délivrabilité des sous-domaines et gestion des clés GPG. [En savoir plus](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

![](assets/do-not-localize/cp-icon.png) **Nouvelle version d&#39;octobre du panneau de contrôle** avec configuration de domaine utilisant des CNAME et nouvelles fonctionnalités de surveillance de base de données. [En savoir plus](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

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
<th> <strong>Intégration de l’IA dédiée au parcours</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Nous sommes ravis d’annoncer l’IA dédiée au parcours pour tous les clients Adobe Campaign Standard.</p>
  <p>L’IA dédiée au parcours utilise un logiciel de machine learning (ML) avancé pour permettre aux entreprises d’optimiser la conception et la diffusion des parcours des clients en prédisant les préférences d’engagement de chaque individu.</p>
  <P>L’IA dédiée au parcours comprend deux fonctions de ML :</p>
<ul> 
     <li> <strong>Évaluation prédictive de l’engagement</strong> - Identifie intelligemment le niveau d’engagement préféré des clients pour mieux cibler et personnaliser les messages afin d’augmenter les conversions et la rétention. Regardez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">vidéo pratique</a>.</li> 
     <li> <strong>Optimisation prédictive du temps d’envoi</strong> - Prévoit le meilleur moment pour envoyer des emails à chaque individu au cours d’une campagne afin d’optimiser les taux d’engagement et d’améliorer le retour sur investissement des campagnes par email. Regardez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">vidéo pratique</a>.</li>
    </ul>
  <p>Si vous souhaitez découvrir la prise en main de l’IA dédiée au parcours, veuillez consulter la <a href="../../sending/using/predictive.md">documentation détaillée</a> et contacter votre gestionnaire de compte. Notez que si l’IA dédiée au parcours est disponible gratuitement pour les clients Campaign existants, un coût d’implémentation correspondant à environ 50 heures s’applique.</p>
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
* [De nouveaux filtres ont été ajoutés à la liste des événements transactionnels.](../../channels/using/configuring-transactional-event.md#searching-transactional-events) Ils permettent de filtrer les configurations des événements en fonction de leur statut, ainsi que de la dernière réception d’un événement.
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



## Version 20.3 - Mai 2020 {#release-20-3---may-2020}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Loi thaïlandaise sur la protection des données personnelles (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La loi thaïlandaise sur la protection des données personnelles (PDPA) est la nouvelle loi sur la protection de la vie privée qui harmonise et modernise les exigences en matière de protection des données de la Thaïlande. Ce règlement s’applique aux clients Adobe Campaign qui détiennent des données pour des titulaires de données résidant dans ce pays.</p>
<p>Outre les fonctionnalités de confidentialité déjà disponibles dans Adobe Campaign (notamment la gestion du consentement, les paramètres de conservation des données et les rôles utilisateur), nous profitons de l’occasion pour inclure d’autres fonctionnalités afin de faciliter votre préparation au PDPA :</p>
<ul>
<li>Droit d’accès et droit de suppression : nous tirons parti des capacités qui ont été ajoutées pour le RGPD et le CCPA. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#righttoaccess">En savoir plus</a> </li>
<li><p>Lors de la création d’une demande d’accès à des informations personnelles, le type de réglementation PDPA a été ajouté à Privacy Core Service. Cette méthode est celle que vous devez utiliser pour toutes les demandes d’accès et de suppression. L’utilisation de l’API et de l’interface de Campaign pour les demandes d’accès et de suppression est obsolète.  Consultez l’article <a href="../../rn/using/deprecated-features.md">Fonctionnalités obsolètes et supprimées</a>.</p></li>
</ul>
<p>Reportez-vous à la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/privacy/privacy-overview.html">vidéo pratique</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Activité API externe (DG)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>L’activité <strong>API externe</strong> est en cours de transition de la version bêta vers la version DG (disponibilité générale). Cette version apporte une flexibilité supplémentaire à l’analyseur du corps de réponse JSON. Vous pouvez maintenant :</p>
<ul>
<li>analyser un JSON imbriqué avec une profondeur maximale de 10 niveaux ; </li>
<li>analyser les propriétés sélectionnées sous forme de nœuds feuilles à partir d’un JSON et les aplatir en une seule ligne de tableau ;</li>
<li>sélectionner et utiliser un objet de tableau à partir d’un JSON sans avoir à nommer l’objet « data » ou le mettre au niveau supérieur.</li>
</ul>
<p><strong>Attention :</strong> les clients devront <strong>remplacer toutes les activités API externes bêta</strong> par des activités API externes DG dans leurs workflows.  Les workflows qui utilisent la version bêta de l’API externe cesseront de fonctionner dans la version 20.3.</p>
<p>Pour plus d’informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vidéo de procédure</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Fonctionnalités additionnelles** (à partir du 13 juillet)

* **Optimisation du temps d’envoi et scores de profil optimisés par l’IA** : vous pouvez maintenant optimiser la conception et la diffusion des parcours clients afin de prévoir les préférences d’engagement de chaque particulier. Optimisé par l’IA dédiée au parcours, Adobe Campaign peut analyser et estimer les taux d’ouverture, les temps d’envoi optimaux et l’attrition probable en fonction des mesures d’engagement historiques. [En savoir plus](../../sending/using/predictive.md)
* **Nouvelle réglementation brésilienne sur la protection des informations personnelles** : en plus des fonctionnalités de protection des informations personnelles déjà disponibles dans Campaign, Adobe vous aide à vous préparer au LGDP (Lei Geral de Proteçao de Datos) brésilien. Lors de la création d’une demande d’accès à des informations personnelles, la réglementation LGPD a été ajoutée à Privacy Core Service. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy-overview.html)

**Améliorations**

* Le nombre de caractères pouvant être utilisés dans le champ **Préfixe** pour [tester les messages à l’aide de profils ciblés](../../sending/using/testing-messages-using-target.md) est passé de 32 à 500 caractères.
* Le nombre maximal d’événements en temps réel pouvant être publiés sur une instance est passé de 350 à 2 000. (CAMP-41608)
* La synchronisation entre Adobe Launch et Campaign Standard a été améliorée grâce à l’utilisation du workflow technique syncWithLaunch. Ce workflow permet l’import automatique de toutes les propriétés mobiles d’Adobe Launch dans Adobe Campaign Standard. Pour plus d’informations, consultez [cette page](../../administration/using/technical-workflows.md).

   Vous devrez envoyer une demande à l’Assistance clientèle d’Adobe (directement ou par l’intermédiaire de votre contact Adobe) pour que le workflow technique syncWithLaunch soit activé dans votre instance Campaign. (CAMP-40082)

**Améliorations du Concepteur d’email**

* Le Concepteur d’email peut maintenant gérer une mise en forme HTML plus flexible que le W3C strict. (CAMP-42529)
* Correction d’un problème lié aux [images cliquables](../../designing/using/links.md#inserting-a-link) afin d’empêcher l’affichage des liens en regard de l’image dans les blocs de contenu. (CAMP-41586)
* Correction d’un problème qui empêchait la redirection vers une landing page lorsqu’une catégorie de l’[URL trackée](../../designing/using/links.md#about-tracked-urls) était ajoutée dans le modèle. (CAMP-41537)
* Correction d’un problème lié aux marges intérieures des boutons dans Outlook.
* Correction d’un problème en raison duquel les balises HTML s’affichaient sous la forme de texte brut.
* La recherche des blocs de contenu affiche maintenant les résultats de la recherche sur le serveur, ainsi que les résultats préchargés. (CAMP-41870)

**Autres changements**

* L’interface de publication des ressources personnalisées a été améliorée. Elle propose maintenant des messages d’erreur plus clairs.
* Les mappings de diffusion inutilisés ont été supprimés de l’interface.
* Les rôles d’administrateur inutiles ont été supprimés de l’interface.
* Les cases à cocher peuvent maintenant être obligatoires dans une landing page.
* Lors du téléchargement du fichier CSV d’un rapport dynamique, la limite de 200 lignes a été supprimée. Vous pouvez maintenant inclure chaque ligne de votre rapport. (CAMP-40810)
* Ajout de la langue ES-US dans la liste des langues d’usine pour les emails multilingues. (CAMP-42279)
* Les fichiers téléchargés avec une activité de transfert de fichier seront désormais supprimés au bout de X jours, où X est déterminé par le champ **Jours d’historique** sous le menu **Exécution** dans les propriétés du workflow. [En savoir plus](../../automating/using/managing-execution-options.md)

**Intégrations d’Experience Platform**

*  L’activation des [audiences Experience Platform](../../automating/using/aep-targeting-audiences.md) d’Adobe depuis l’activité **Lecture d’audience** a été améliorée afin d’offrir des performances optimisées et une meilleure stabilité. En outre, les logs des workflows ont été rendus plus clairs et plus détaillés en ce qui concerne les traitements d’activation, ce qui facilite le monitoring et la résolution des problèmes lors de la lecture des audiences d’Adobe Experience Platform.

**Correctifs**

* Correction d’une erreur qui entraînait la création d’une ressource fantôme lors du traitement de publication d’une ressource personnalisée.
* Correction d’un problème qui empêchait l’affichage de l’historique marketing des profils si la ressource de profil était étendue avec une ressource personnalisée. (CAMP-41009)
* Correction d’un problème lié aux modèles de landing page d’usine qui affichaient leur contenu en français lors de l’ouverture de l’éditeur. (CAMP-41639)
* Correction d’un problème lié aux notifications push avec un contenu dynamique qui pouvait empêcher l’affichage des emojis. (CAMP-40715)
* Correction d’un problème dans l’activité de **Déduplication** qui pouvait entraîner l’affectation d’un code segment incorrect à l’une des transitions de complémentaire sortantes. (CAMP-41400)
* Correction d’une erreur qui empêchait la suppression des rapports planifiés. (CAMP-41302)
* Correction d’un problème qui entraînait des incohérences entre le tableau de bord des diffusions et le rapport **Synthèse des diffusions**. (CAMP-41145)
* Correction d’un problème qui entraînait un chevauchement des caractères dans les rapports téléchargés.
* Correction d’un problème qui empêchait l’aperçu d’une diffusion de fonctionner pour la substitution des bons à tirer.
* Correction d’une erreur lors de la suppression de champs personnalisés d’une notification locale In-App.
* Correction d’un problème qui empêchait la fonction charIndex de fonctionner avec une activité de **Fin** ou de **Transfert de fichier** dans un workflow.
* Correction d’un problème lié aux workflows qui pouvait se produire lors de l’utilisation d’une activité d’**Enrichissement** avec deux activités d’entrée incluant des ressources cibles ayant un lien entre elles. (CAMP-42133)
* Correction d’un problème qui empêchait l’exécution d’un workflow lors de l’utilisation de fonctions inconnues. (CAMP-41873)
* Correction d’un problème lié aux workflows qui pouvait se produire lors de la création d’audiences à l’aide de plusieurs activités de **Sauvegarde d’audience** avec des transitions de complémentaire sortantes. (CAMP-39992)
* Correction d’un problème qui entraînait des incohérences dans les données lors de l’utilisation de la personnalisation dans les emails transactionnels. (CAMP-41842)
* Correction de problèmes qui se produisaient lors de la suppression de champs personnalisés dans les diffusions de notifications push. (CAMP-37586)
* Correction d’une erreur qui empêchait les utilisateurs d’apporter des modifications aux rapports. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Nouvelle version de juin du panneau de contrôle** avec renouvellement de certificat pour les sous-domaines CNAME. [En savoir plus](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Version 20.2 - Avril 2020 {#release-20-2---april-2020}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Intégration de Blob de Microsoft Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le connecteur de stockage Blob de Microsoft Azure peut maintenant être utilisé pour importer ou exporter des données vers Adobe Campaign à l’aide d’une activité de workflow <strong>Transfert de fichier</strong>. </p>
    <p>Pour plus d’informations, consultez la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentation détaillée</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Test d’emails à l’aide de profils ciblés</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Outre les profils de test, vous pouvez maintenant tester vos emails sur des profils ciblés réels. Vous obtenez ainsi une représentation exacte du message que le profil recevra : champs personnalisés, informations dynamiques et personnalisées, notamment des données additionnelles provenant des workflows, etc. </p>
    <p>Pour plus d’informations, consultez la <a href="../../sending/using/testing-messages-using-target.md">documentation détaillée</a> et regardez la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">vidéo de tutoriel</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Au mois d’avril, de nouvelles fonctionnalités seront disponibles dans le Panneau de contrôle Campaign, notamment la gestion des enregistrements TXT Google, la surveillance de l’espace des bases de données et les alertes par email. Pour en savoir plus sur ces fonctionnalités, consultez la [note de mise à jour du panneau de contrôle](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

**Améliorations**

* L’expérience client de la messagerie transactionnelle a été améliorée et la cohérence de l’interface également. [En savoir plus](../../channels/using/getting-started-with-transactional-msg.md)
* Campaign Standard permet maintenant d’envoyer des bons à tirer à des profils de test avec des données additionnelles provenant des workflows.
* Les protections pour l’activité API externe ont été mises à jour. [En savoir plus](../../automating/using/external-api.md)

**Améliorations du Concepteur d’email**

* Correction d’un problème ayant un impact sur l’échappement lors de plusieurs clics sur une image personnalisée.
* Correction d’un problème lors de la duplication de composants de texte dynamique qui entraînait la duplication de la mauvaise ligne. (CAMP-41249)
* Correction d’un problème de remplissage dans Outlook lors de la définition du remplissage au niveau du tableau et non au niveau div.
* Correction d’un problème en raison duquel la largeur d’une image était modifiée lors du passage en mode HTML. (CAMP-41116)
* Correction d’un problème qui empêchait l’accessibilité du composant des médias sociaux lors de la fourniture d’un texte de remplacement aux icônes. (CAMP-41345)
* Correction d’un problème en raison duquel les balises `<br>` visibles s’affichaient lors de l’utilisation des opérations de copier-coller dans le Concepteur d’email.
* Correction d’un problème en raison duquel les balises HTML s’affichaient dans l’email après le passage du contenu HTML au texte simple. (CAMP-41138)
* Correction d’un problème empêchant le rendu des boutons avec une seule bordure définie.
* Correction d’un problème de mise en retrait HTML en raison duquel le pied de page des emails était déplacé vers la gauche dans Microsoft Outlook. (CAMP-40987)
* Correction d’un problème en raison duquel les champs de personnalisation ciblant un attribut de collection défini en HTML étaient copiés dans le contenu en texte simple lors du passage en mode de texte simple. (CAMP-40365)
* Correction d’un problème qui empêchait l’insertion de liens dans un segment de texte sélectionné. (CAMP-41406)
* Correction d’un problème en raison duquel la date était modifiée lors de la sélection d’un fuseau horaire dans l’éditeur de requêtes. (CAMP-38277)

**Autres changements**

* Le workflow d’usine **Réconciliation des KPI avec Adobe Analytics** s’exécute maintenant jusqu’à la date courante au lieu de s’exécuter pendant une seule journée.
* Le MCPNS ne prend pas en charge l’ajout d’APNS et d’APNS-SANDBOX en tant que plateformes dans une application. Une fois le certificat ajouté dans Adobe Campaign Standard, vous ne pouvez plus restaurer vos paramètres dans la mesure où une seule plateforme APNS (production ou sandbox) peut être ajoutée à l’application MCPNS.

**Intégrations d’Experience Platform**

>[!NOTE]
>
>Les fonctionnalités Adobe Experience Platform dans Campaign Standard sont actuellement en version bêta et peuvent être fréquemment mises à jour sans préavis. Reportez-vous à la documentation détaillée : [Connecteur Experience Platform](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Dans les logs des workflows, Campaign affiche maintenant toutes les 10 minutes le nombre d’enregistrements déjà traités par le traitement en cours d’exécution.
* Correction d’un problème qui se produisait lors de l’import d’un profil Adobe Experience Platform qui avait été supprimé de la base de données.
* Correction d’un problème dans les logs des workflows, en raison duquel un résultat incorrect pouvait s’afficher pour le nombre total d’enregistrements importés.

**Correctifs**

* Correction d’un problème lié à l’activité de workflow **Enrichissement** qui pouvait se produire lors de l’ajout d’espaces dans le champ **Alias**, ce qui créait ensuite un nouvel élément de ligne. (CAMP-39229)
* Correction d’un problème en raison duquel chaque profil de test pouvait être ciblé lors de l’envoi d’un message de bon à tirer.
* Correction d’un problème qui se produisait après la dépublication et la suppression d’une configuration d’événement. [En savoir plus](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* Correction d’un problème en raison duquel le bouton **Enregistrer** disparaissait lors des modifications apportées aux workflows.
* Correction d’un problème lors de la suppression manuelle d’une demande d’accès à des informations personnelles dans Campaign après son traitement, ce qui empêchait la suppression des données associées à la demande même après le nettoyage.
* Correction d’un problème qui se produisait lors de la prévisualisation ou de l’envoi de messages contenant des caractères spéciaux d’Adobe Experience Manager.
* Correction d’un problème qui se produisait dans les workflows lors de l’exécution d’une activité avec plusieurs transitions entrantes.
* Correction d’un problème qui empêchait les utilisateurs standard d’utiliser les inscriptions à une application comme dimension cible dans une requête de workflow ou une diffusion. (CAMP-37618)

## Version 20.1.4 - Février 2020 {#release-20-1-4---february-2020}

* Correction d’un problème lors de l’ouverture d’une activité **Lecture d’audience** sur des workflows existants. (CAMP-41002)

## Version 20.1.3 - Février 2020 {#release-20-1-3---february-2020}

* Correction d’un problème de régression introduit dans la version 20.1 par CAMP-39273 pour les clients qui utilisaient la faille. CAMP-39273 a été annulé.

## Version 20.1.2 - Février 2020 {#release-20-1-2---february-2020}

**Améliorations du Concepteur d’email**

* Correction d’un problème qui entraînait l’ajout d’un élément de balise HTML dans un fragment obsolète lors de l’application de correctifs, puis de l’enregistrement du contenu. (CAMP-40685)
* Correction d’un problème qui entraînait l’ajout d’un espace lors de l’utilisation de contenu dynamique. (CAMP-40605)
* Correction d’un problème lors de la configuration d’un modèle d’email transactionnel. (CAMP-40604)

## Version 20.1 - Février 2020 {#release-20-1---february-2020}

**Nouveautés**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (version bêta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector est maintenant intégré avec Adobe Campaign Standard. Vous pouvez rendre vos données Campaign disponibles sur Adobe Experience Platform en mappant les données XTK (données ingérées dans Campaign) sur le modèle de données Adobe Experience Platform (XDM). </p>
    <p>Remarque : cette fonctionnalité n’est disponible que pour les clients hébergés sur Azure. Pour plus d’informations sur cette fonctionnalité et les conditions pour l’activer, consultez la <a href="../../developing/using/aep-about-data-connector.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">vidéo pratique</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (version bêta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations permet de partager des segments d’Adobe Experience Platform avec Adobe Campaign.</p>
    <p>Remarque : cette fonctionnalité n’est disponible que pour les clients hébergés sur Azure. Pour plus d’informations sur cette fonctionnalité et les conditions pour l’activer, consultez la <a href="../../audiences/using/aep-about-audience-destinations-service.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">vidéo pratique</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Disponibilité générale du MTA amélioré : les messages (y compris les messages transactionnels) sont maintenant envoyés par le MTA amélioré d’Adobe Campaign. Ce MTA est doté d’une version mise à niveau de l’infrastructure d’envoi qui permet d’améliorer la délivrabilité, le débit et la gestion des bounces. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/campaign-enhanced-mta.html)

* La gestion des fuseaux horaires a été améliorée. Vous pouvez maintenant définir un [fuseau horaire spécifique](../../automating/using/building-a-workflow.md) pour l’ensemble d’un workflow. Le fuseau horaire sélectionné s’applique à toutes les activités du workflow. Les informations sur le fuseau horaire, configurées pour l’opérateur ou le serveur, s’affichent maintenant dans l’interface (dans les logs et après avoir sélectionné un fuseau horaire). (CAMP-37672)

* Les API de Campaign Standard permettent maintenant d’effectuer une pagination lors de l’utilisation de tables volumineuses, en ajoutant le paramètre `_forcePagination=true` à votre URL d’appel. [En savoir plus](../../api/using/pagination.md)

* L’identifiant de log de diffusion (unique pour chaque log) est maintenant disponible dans les ressources des logs de diffusion et de tracking pour toutes les dimensions de ciblage. Vous pouvez ainsi identifier les logs d’envoi ou de tracking, par exemple lors d’un export. [En savoir plus](../../automating/using/exporting-logs.md)

**Améliorations du Concepteur d’email**

* Ajout d’instructions de texte obligatoires manquantes lors de la création d’une audience.
* Correction d’un problème qui se produisait lorsqu’un utilisateur cliquait sur le bouton **Changer de contenu** dans l’assistant de l’ancien éditeur d’email.
* Correction d’un problème qui empêchait l’alignement des en-têtes avec le contenu du rapport Synthèse du service. (CAMP-38103)
* Correction d’un problème qui empêchait la suppression des variantes de contenu dynamique sans répercussion sur le reste de la ligne d’objet. (CAMP-40096)
* Correction d’un problème de test A/B lors de l’utilisation de la variante B sur la ligne d’objet. (CAMP-40327)
* Correction d’un problème qui empêchait d’effectuer un glisser-déposer des fichiers avec la fonctionnalité de chargement d’import de code HTML. (CAMP-39326)
* Correction d’un problème qui empêchait d’effectuer un copier-coller de texte à partir d’un éditeur de texte. (CAMP-39028)
* Correction d’un problème qui empêchait l’affichage des suggestions de mots. (CAMP-38970)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer des fragments. (ATU-2447)
* Correction d’un problème qui empêchait la duplication des structures dynamiques. (CAMP-38367)
* Correction d’un problème qui empêchait le contenu dynamique de conserver les conditions en cas de duplication. (CAMP-39051)

**Autres changements**

* Le filtre « Diffusions avec préparation en échec » prend maintenant en compte la date de création des diffusions plutôt que la date de dernière modification.
* Il n’est plus possible de modifier les entités organisationnelles du groupe de sécurité Administrateurs.
* Lors de la création d’un profil, le champ Entité organisationnelle doit maintenant être renseigné.
* Un trigger Experience Cloud ne peut maintenant être supprimé que si l’événement et le modèle transactionnel associés sont aussi supprimés.
* [!DNL Adobe Creative SDK] a été déclassé. Il est désormais obsolète dans Campaign Standard. Consultez la page [Fonctionnalités obsolètes et supprimées](../../rn/using/deprecated-features.md).


**Correctifs**

* Correction d’un problème lors de l’exécution d’une demande de suppression d’informations personnelles qui empêchait la suppression des données utilisateur dans les logs d’exclusion. (CAMP-39003)
* Correction d’une erreur qui entraînait des problèmes d’accessibilité lors du redimensionnement du texte dans un élément de conteneur.
* Correction d’un problème qui empêchait les utilisateurs de fermer la fenêtre contextuelle Calendrier qui s’affichait lorsqu’ils pointaient sur des activités marketing.
* Correction d’un problème dans l’activité **[!UICONTROL API externe]** qui affichait le bouton **[!UICONTROL Confirmer]** même lorsqu’aucune donnée n’était modifiée.
* Correction d’un problème lors de l’utilisation d’une activité **[!UICONTROL Union]** sur des requêtes avec des dimensions cibles différentes. Les données de transition n’affichaient que les enregistrements de la dimension de ciblage du jeu principal. (CAMP-36831)
* Correction d’un problème qui pouvait entraîner une erreur lors de l’utilisation d’une activité de **[!UICONTROL réconciliation]** dans des contextes spécifiques, par exemple avec deux activités entrantes, l’une étant une activité d’exclusion. (CAMP-37490)
* Correction de problèmes de performances possibles lors de la sélection et de la mise à jour des profils de test. (CAMP-37976)
* Correction d’un problème qui entraînait l’affichage de pages d’erreur lors d’un abonnement ou d’un désabonnement via les landing pages. (CAMP-37771)
* Correction d’un problème qui se produisait lors du téléchargement de contenu au format zip, comportant des fichiers PNG référencés dans le code HTML avec des extensions en majuscules. (CAMP-37913)
* Correction d’un problème qui empêchait l’envoi de messages In-App lors de l’ajout d’un profil de test à la diffusion.
* Correction d’une erreur liée à l’activité de workflow API externe qui échouait lorsqu’elle était liée à des activités d’enrichissement.
* Correction d’un problème susceptible d’entraîner l’affichage incorrect de l’état des messages SMS.
* Correction d’un problème lié aux ressources personnalisées qui entraînait l’apparition d’entrées en double pour différents points d’entrée d’API.
* Correction d’un problème qui empêchait la disponibilité des landing pages après publication. (CAMP-38695)
* Correction d’un bogue qui se produisait lors de l’affichage des données d’une transition Intersection provenant de deux ressources différentes. (CAMP-38974)
* Correction d’un problème qui entraînait une définition incorrecte de la valeur d’énumération dans un modèle de diffusion. (CAMP-38388)
* Correction d’une erreur lors de diffusions email en masse, qui entraînait l’affichage de l’état des diffusions En attente et de l’état Envoyé comme Terminé. (CAMP-35355)
* Correction d’une erreur qui affichait incorrectement le domaine de l’expéditeur dans les rapports dynamiques. (CAMP-33123)
* Correction d’un problème qui entraînait des incohérences dans le nombre de désabonnements dans les rapports dynamiques. (CAMP-39949)
* Correction d’un problème qui empêchait l’affichage des adresses dans l’écran Logs d’envoi lors de l’envoi de messages In-App.
* Correction d’un problème qui empêchait la mise à jour des logs d’envoi des SMS avec le nombre correct de bounces. (CAMP-38395)
* Correction d’une faille qui permettait aux appels POST des abonnements aux applications de mettre à jour les jetons de notification push. (CAMP-39273)
