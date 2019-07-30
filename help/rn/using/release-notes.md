---
title: Notes de mise à jour
seo-title: Notes de mise à jour
description: Notes de mise à jour
seo-description: Cette page répertorie toutes les versions récentes d'Adobe Campaign Standard.
page-status-flag: jamais activé
uuid: 1 cf 2 e 40 c-beca -43 db -8261-a 1820 ee 86 ad 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: référence
topic-tags: campagne-standard-release
discoiquuid: 5 c 7 bfb 74-4002-4 ffe -87 e 8-bddb 41 d 34 b 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c1e17942d03250bbe863b2b57a0c810eaec6fa3

---


# Notes de mise à jour{#release-notes}

Vous recherchez une version spécifique d’Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu. Pour connaître la date de la prochaine version, consultez le [calendrier des versions](https://helpx.adobe.com/campaign/kb/acs-release-planning.html).

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d'Adobe Campaign Standard. Si vous recherchez une version précédente, consultez ces pages : [Notes de mise à jour de l'année 2018](../../rn/using/release-notes-2018.md), [Notes de mise à jour de l'année 2017](../../rn/using/release-notes-2017.md), [Notes de mise à jour des années 2015-2016](../../rn/using/release-notes-2015-2016.md). Consultez également la liste des [fonctionnalités supprimées et obsolètes](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Version 19.3 - Juillet 2019 {#release-19-3---july-2019}

### What's new? {#what-s-new-3}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> External API Activity (Public Beta)<br /> </td> 
   <td> <p>Pour une personnalisation plus poussée, l'activité API externe vous permet d'importer des données provenant de systèmes externes dans un flux de travail via un appel API REST. Les points de fin REST peuvent être un système de gestion client, un endpoint de fin Adobe I/S Runtime ou un endpoint de fin REST Adobe Experience Cloud (par exemple, Platform Platform, Target, Analytics, Campaign).</p><p>Cette fonctionnalité est actuellement en version bêta publique.</p><p>For more information, refer to the <a href="../../automating/using/external-api.html">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Report on workflow segment<br /> </td> 
   <td> <p>Cette fonctionnalité permet aux spécialistes du marketing de ventiler leurs performances de diffusion par code de segment. Lorsque vous créez un flux de travail et que vous utilisez une activité de segmentation pour affecter des segments à la population de diffusion, ces segments peuvent maintenant accéder à la même diffusion. Cela vous permet d'afficher les statistiques d'ouverture/clic basées sur plusieurs segments au sein d'une seule diffusion.</p><p>For more information, refer to the <a href="../../reporting/using/creating-a-report-workflow-segment.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">how-to video</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Améliorations de la sécurité {#security-enhancements-2}

* Correction d'un problème de sécurité empêchant les attaques par déni de service (DoS) d'obtenir des images. (CAMP-33454)

### Améliorations du Concepteur d'email {#email-designer-enhancements-3}

* Correction d'un problème qui ajoutait des balises de style HTML supplémentaires à un modèle HTML chaque fois qu'un composant était ajouté, ce qui pouvait considérablement accroître la taille du modèle. (CAMP-34694)
* Correction d'un problème qui empêchait la disponibilité des options de menu de barre d'outils supérieure droite. (CAMP-34577)
* Correction d'un problème survenant lorsque le bloc de contenu de l'URL de la page Miroir était inséré dans un contenu de courrier électronique. (CAMP-34779)
* Correction d'un problème survenant lors de l'utilisation du code JPSP par courriel, rendant difficile la modification du contenu. (CAMP-34574)
* Correction d'un problème en raison duquel les images étaient tronquées en cas d'ajout d'un hyperlien. (CAMP-34382)
* Correction d'un problème d'affichage lors de l'utilisation de Designer Designer avec Firefox. (CAMP-34364)
* Correction de plusieurs problèmes survenant avec le mode Avancé lors de la définition de contenu dynamique par courriel. (CAMP -34351, CAMP -34333, CAMP -34331)
* Correction de plusieurs problèmes survenant avec l'éditeur de règles de contenu dynamique (CAMP -34304, CAMP -34303).
* Correction d'un problème qui empêchait l'affichage du champ Link dans le volet Settings Designer Settings (CAMP -33749).
* Correction d'un problème lié à l'icône YouTube surdimensionnée dans les courriers électroniques envoyés. (CAMP-33726)
* Correction d'un problème de sécurité qui modifiait le contenu de la page miroir. (CAMP-33691)
* Correction d'un problème qui rompt la sortie HTML lors de l'utilisation du symbole plus grand que dans le contenu dynamique. (CAMP-33688)
* Correction d'un problème survenant lors de l'utilisation de l'option Annuler lors de la modification du texte dans Designer. (CAMP-32565)
* Correction d'un problème qui créait des balises supplémentaires lors de l'annulation de styles au lieu de les supprimer. (CAMP-32359)
* Vous pouvez maintenant définir si chaque composant utilisé par courriel s'affiche uniquement sur les périphériques de bureau ou uniquement sur les périphériques mobiles.
* Vous pouvez désormais définir la largeur et la hauteur d'un composant de contenu Social.
* Correction d'un problème en raison duquel le code source ancien du contenu dynamique n'était pas supprimé après suppression du contenu dynamique.
* Correction d'un problème qui empêchait la mise à jour du sujet d'un courrier électronique après sa modification.
* Correction d'un problème qui empêchait un n : n la structure de colonne n'est pas sélectionnée une fois déposée dans l'espace de travail.
* Correction d'un problème en raison duquel la miniature du message apparaissait floue dans le tableau de bord Courriel.
* Correction d'un problème qui empêchait l'affichage correct de l'arrière-plan pour les courriers électroniques reçus dans Outlook.
* Correction de certains problèmes de tri sur la page d'accueil de Designer.
* Correction d'un problème survenant lors de la duplication de variantes lors de l'utilisation du contenu dynamique.
* Certains champs indésirables ont été supprimés du volet Paramètres de Designer.

### Autres améliorations {#other-improvements-3}

* Grâce à l'intégration aux services de localisation Adobe Experience Platform, Adobe Campaign est désormais compatible pour envoyer des messages marketing basés sur l'emplacement aux abonnés de votre application mobile via le SDK d'Experience Platform. Pour plus d'informations, consultez la [documentation détaillée](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La fonctionnalité de création de rapports a été améliorée pour une meilleure expérience. Pour utiliser cette fonctionnalité, vous devez accepter l'accord d'utilisation dynamique des rapports. Consultez à ce sujet la [documentation détaillée](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Dans les flux de travaux, une nouvelle option a été ajoutée pour prévisualiser les dix prochaines exécutions d'un flux de travaux. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Dans l'activité du planificateur, une nouvelle option vous permet de sélectionner un jour spécifique d'une semaine spécifique pour les livraisons mensuelles. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Lors de la création de distributions récurrentes sans période d'agrégation, le tableau de bord de diffusion vous permet désormais de demander confirmation avant l'envoi de la livraison. Consultez à ce sujet la [documentation détaillée](../../sending/using/confirming-the-send.md).
* Vous pouvez désormais personnaliser l'étiquette d'une diffusion avec des variables d'événement qui ont été déclarées dans l'activité du signal externe du processus. Consultez à ce sujet la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md).
* La requête de suppression GDPR a été améliorée pour une meilleure performance. (CAMP-33504)
* L'option « ftp » a été supprimée de l'interface de configuration du compte externe. (CAMP-34472)
* Vous pouvez désormais activer et désactiver l'option Mode de test SMTP pour chaque courrier électronique. Consultez à ce sujet la [documentation détaillée](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

### Autres changements {#other-changes-2}

* Un avertissement a été ajouté à l'interface des propriétés de diffusion. Elle indique que les remises sont préparées en fonction de leur période d'agrégation et de leur appel pour appeler le flux de travail plusieurs fois par jour, vous devez vous assurer qu'elles n'ont aucune période. (CAMP-34393)
* Un avertissement a été ajouté aux écrans de configuration des ressources personnalisées. Nous vous recommandons d'utiliser 30 caractères maximum pour les ID de ressource personnalisés. Cela s'applique également aux champs de ressource personnalisés, aux clés, aux index et aux liens.
* Un message s'affiche désormais lorsque vous tentez de supprimer un message transactionnel utilisé par une page d'entrée comme message de confirmation.
* Un avertissement s'affiche désormais dans les journaux de processus lorsqu'une activité est en cours d'exécution pendant plus de 6 heures. Ceci ne s'applique pas aux activités de notification Push, de livraison, de signal, de début, de fin, de fourchette et de liaison, de planification et d'attente.
* Un avertissement s'affiche désormais dans les journaux de processus lorsque vous atteignez le nombre maximal de flux de travaux en cours d'exécution simultanément.
* Les flux de travaux en pause ou en échec pendant plus de 7 jours sont maintenant arrêtés pour consommer moins d'espace disque. La tâche de nettoyage s'affiche dans les journaux de flux de travaux.
* Lors de l'utilisation d'une activité de transfert de fichier, une erreur est maintenant consignée si la taille du fichier dépasse l'espace disque disponible.
* L'action Rediriger vers l'URL de destination ne peut plus être sélectionnée pour le bouton secondaire dans les messages in-app.

### Correctifs {#patches-3}

* Correction d'un problème qui entraînait l'échec des demandes d'accès GDPR.
* Correction d'un problème qui entraînait l'annulation de déclencheurs lors de la réception de plusieurs déclencheurs pour un profil unique.
* Correction d'un problème qui entraînait un message d'erreur de publication de ressource personnalisée erroné après la connexion.
* Correction d'un problème qui affichait une page vierge lors de la création ou de l'extension d'une ressource personnalisée.
* Correction d'un problème qui empêchait une audience avec appsubscriptionrcp comme dimension de ciblage d'être disponible pour le ciblage dans une diffusion mobile.
* Correction d'une erreur qui empêchait la mise en quarantaine des adresses électroniques de rebonds. (CAMP-24587)
* Correction d'un problème qui survenait lors de l'ajout d'une règle de typologie, puis la supprimait avant d'enregistrer la typologie. (CAMP-32789)
* Correction d'un problème qui empêchait l'affichage du contenu de la page d'entrée lors de la désactivation du contenu dynamique. (CAMP-32924)
* Correction d'un problème lié aux remises périodiques qui survenait lors de l'utilisation de la personnalisation sur les attributs d'une remise principale. (CAMP-32983)
* Correction d'un problème dans les flux de travaux qui empêchait la lecture des résultats d'une transition contenant des données SMS entrants. (CAMP-33134)
* Correction d'un problème dans les flux de travaux qui se produisait lors de la combinaison d'activités de fourre et d'exclusion pour créer des audiences. (CAMP-33401)
* Correction d'un problème qui empêchait l'affichage du contenu de la page miroir et l'envoi des messages d'épreuves pour les remises récurrentes. (CAMP-33413)
* Correction d'un problème qui entraînait une erreur lors de l'utilisation d'une activité Union entre les profils et les audiences. Ce problème était dû à une incompatibilité des clés d'identification dans les transitions d'entrée. (CAMP-33713)
* Correction d'un problème dans les activités Test qui empêchait l'expression « reccount » d'utiliser la syntaxe correcte lors de la double-clic dessus. (CAMP-33756)
* Correction d'un problème qui pouvait entraîner un message d'erreur lors de l'ouverture des journaux de flux de travaux techniques de facturation. (CAMP-34313)
* Correction d'un problème dans les pages d'entrée qui pouvait se produire lors de la configuration des champs de case à cocher avec des abonnements. (CAMP-34369)
* Correction d'un problème survenant lors de la configuration d'une liste et l'ajout du champ « icône ». (CAMP-34585)
* Correction d'un problème qui empêchait l'utilisation de la variable| » et les symboles " %" comme séparateurs de date ou d'heure dans les activités de chargement des fichiers de fichier. (CAMP-34706)
* Correction d'un problème qui survenait lors de l'utilisation de conditions de visibilité avec des cases à cocher dans les pages d'entrée. (CAMP-34802)
* Correction d'un problème de l'activité d'enrichissement qui empêchait l'affichage des champs dans l'onglet « Données supplémentaires » si la dimension de filtrage était définie sur les journaux de suivi et la dimension cible dans le profil.
* Correction d'un problème qui entraînait un message d'erreur lors de l'exportation d'une ressource de type « workflowtemplate ».
* Correction d'un problème lors de la création d'un nouveau profil, qui empêchait l'enregistrement du champ « Pays/région » s'il était sélectionné dans la boîte de dialogue.
* Correction de plusieurs problèmes survenant lors de l'utilisation du modèle d'importation Direct Mail (updatequarantinesdeliverylogsdirectmail).
* Correction d'un problème lié à l'intégration de la demande Ressources on -.
* Correction d'un problème survenant lors du zoom avant sur la vue Chronologie. (CAMP-33628)
* Correction d'un problème qui empêchait l'envoi instantané des épreuves pour les messages électroniques avec une date et une heure planifiées. (CAMP-33723)
* Correction d'un problème lié aux messages transactionnels qui générait des journaux d'erreur lors de la déconnexion d'un utilisateur. (CAMP-31698)
* Correction d'une erreur qui pouvait se produire dans des environnements spécifiques lors de la planification d'un courriel.
* Correction d'un problème en raison duquel le processus d'exécution de remise de la remise échouait.
* Correction d'un problème de sécurité qui rompait le contenu du courrier électronique lorsque le sujet contenait plusieurs lignes.


## Version 19.2.7 - Juillet 2019 {#release-19-2-7---july-2019}

### Améliorations {#improvements-2}

* La requête de suppression GDPR a été améliorée pour une meilleure performance.
* Correction d'un problème qui provoquait des blocages Web après la mise à niveau 19.2. (CAMP-34862)
* Correction d'un problème qui empêchait les utilisateurs non administrateurs d'enregistrer ou de planifier des rapports. (CAMP-31133)
* Correction d'un problème lors de l'utilisation de « | » comme séparateur de date dans l'activité de flux de travail Charger le fichier. (CAMP-34706)

## Version 19.2.4 - Juin 2019 {#release-19-2-4---june-2019}

### Concepteur d'email {#email-designer-2}

* Correction d'un problème qui empêchait les utilisateurs de modifier des fragments lorsque des balises de style vides étaient utilisées dans le code HTML. Il s'agit d'un correctif de suivi pour CAMP-33778 dans la version 19.2.3.

## Version 19.2.3 - Juin 2019 {#release-19-2-3---june-2019}

### Concepteur d'email {#email-designer-1}

Mise en place d'une série d'améliorations et de correctifs afin d'optimiser les fragments dans la version 19.2. Les nouveaux fragments fonctionneront de manière transparente. Les fragments conçus précédemment ont été grisés et devront être migrés vers le nouveau format. Pour cela, cliquez sur chaque fragment et validez sa migration vers le nouveau format. Nous vous recommandons de tester quelques fragments avant de migrer l'ensemble.

* Correction d'un problème qui empêchait les utilisateurs d'éditer un fragment après l'avoir déverrouillé. Ce problème avait une incidence sur les fragments existants lors de la mise à jour vers la version 19.2. (CAMP-33778)
* Correction d'un problème qui se produisait lors de l'utilisation du contenu dynamique. Des espaces supplémentaires étaient ajoutées dans le code HTML.

### Autres améliorations {#other-improvements-2}

* Correction d'un problème qui empêchait la reprise de l'envoi des SMS suite à une déconnexion du connecteur SMS.
* Correction d'un problème qui fermait les connexions SMPP lorsque TLS était activé.
* Correction d'un problème qui fermait les connexions SMPP lorsque TLS était activé.
* L'option "Launch_URL_Campaign" a été ajoutée dans Campaign pour gérer les propriétés des applications mobiles créées avec le SDK Mobile Adobe Experience Platform.
* Correction d'une erreur qui entraînait la désélection de l'option d'environnement sandbox après le téléchargement du certificat d'une nouvelle propriété mobile et la sortie de la page de propriété de l'application mobile.
* Correction d'un problème qui empêchait l'utilisateur d'enrichir le contenu d'un message transactionnel avec des informations de la ressource Service. (CAMP-33707)
* Correction d'un problème lié aux landing pages de blacklistage qui se produisait lors du désabonnement des profils d'un service.

## Version 19.2 - Mai 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Panneau de contrôle<br /> </td> 
   <td> <p>Pour accroître l'efficacité de votre travail en tant qu'utilisateur administrateur, vous pouvez facilement surveiller la capacité de vos instances et gérer leurs paramètres (à commencer par la gestion des serveurs SFTP).</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notifications locales<br /> </td> 
   <td> <p>Les messages de notification locale permettent d'informer les utilisateurs lorsque de nouvelles données deviennent disponibles dans leurs applications mobiles, même sans accès à Internet ou sans l'application mobile s'exécutant au premier plan. Les notifications locales sont déclenchées par une application mobile à une heure donnée et en fonction d'un événement.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentation détaillée</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux workflows : ajout d'une payload à l'activité de signal externe<br /> </td> 
   <td> <p>Démarrez un workflow avec une payload lorsque les conditions définies sont satisfaites à partir d'un autre workflow ou d'un appel d'API REST de façon à intégrer avec vos systèmes externes. Une nouvelle activité de <strong>test</strong> permet aussi d'exécuter des tests sur cette fonctionnalité.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux landing pages : Google reCAPTCHA<br /> </td> 
   <td> <p>Utilisez Google reCAPTCHA pour empêcher tout spam sur vos landing pages sans intervention de vos clients.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">documentation détaillée</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Améliorations de la sécurité {#security-enhancements}

* Correction d'un problème de sécurité potentiel de détournement de clic dans l'espace de travail de reporting.

### Améliorations du Concepteur d'email {#email-designer-enhancements}

* Correction d'un problème qui se produisait lors de la duplication de fragments et de leur utilisation dans le Concepteur d'email. (CAMP-33193)
* Correction d'un problème qui créait des espaces inutiles lors de l'utilisation d'éléments incorporés dans l'interface du Concepteur d'email. (CAMP-32163)
* Correction d'un problème qui supprimait certains attributs de balise HTML supplémentaires ajoutés par l'utilisateur après avoir enregistré le contenu d'un email dans le Concepteur d'email. (CAMP-32162)
* Correction d'un problème qui affichait une balise Microsoft Office en mode HTML du Concepteur d'email, même après sa suppression. (CAMP-32141)
* Si vous avez créé un email à l'aide d'une version antérieure du Concepteur d'email, une fenêtre contextuelle s'ouvre maintenant lors de l'ouverture du contenu de cet email pour inviter l'utilisateur à effectuer une mise à jour vers la version la plus récente. (CAMP-31529)
* Correction d'un problème qui déformait les images d'un email créé avec le Concepteur d'email lorsqu'il était diffusé à certains clients de messagerie. (CAMP-31407)
* Correction d'un problème qui empêchait l'affichage correct de certains éléments (listes ou boutons, par exemple) en mode texte brut lorsqu'ils avaient été créés en mode HTML. (CAMP-32582, CAMP-32542)
* Correction d'un problème qui empêchait l'affichage de plus de 50 entités organisationnelles dans un modèle de contenu ou des propriétés de fragment. (CAMP-32932)
* Correction d'un problème lié à la couleur d'arrière-plan de la fenêtre d'affichage lors de la réception dans Outlook d'un email créé avec le Concepteur d'email. (CAMP-31402)
* Correction d'un problème qui empêchait les contenus d'email créés avec le Concepteur d'email d'être réactifs lorsqu'ils étaient ouverts dans Outlook. (CAMP-31400)
* Correction d'un problème qui empêchait le contenu dynamique de fonctionner correctement lorsqu'il était utilisé dans l'objet d'un email. (CAMP-32837)
* Correction d'un problème lié aux objets des emails qui n'étaient pas correctement placés dans une séquence d'échappement. 
* Correction d'un problème qui empêchait le chargement de fragments dans la palette de gauche du Concepteur d'email. 
* Correction d'un problème qui empêchait l'affichage des fragments créés lors de l'édition du contenu d'email dans la palette de gauche du Concepteur d'email au moment de l'actualisation de la liste des fragments.
* Correction de plusieurs problèmes qui se produisaient lors de l'utilisation de contenu dynamique dans un email.
* Correction d'un problème lié au sélecteur de couleurs qui se produisait lors de la définition d'une couleur à l'aide de valeurs RVB.
* Correction d'un problème qui empêchait la page miroir d'être réactive lors de la réception de l'email sur un mobile.

### Améliorations apportées aux messages transactionnels {#transactional-messaging-enhancements}

Pour optimiser le fonctionnement et les performances, plusieurs améliorations ont été ajoutées au canal Messages transactionnels.

* La durée des messages transactionnels a été prolongée afin que tous les messages soient envoyés avant leur expiration, en particulier lors de reprises.
* Les performances des messages transactionnels ont été améliorées en répartissant la charge sur différents threads d'envoi.
* Le processus des messages transactionnels a été optimisé pour pouvoir lancer en parallèle plusieurs analyses d'un même message.
* Correction d'un problème qui pouvait entraîner une incohérence du débit et de la latence pour les notifications push transactionnelles.
* Correction d'un problème qui affichait une audience cible incorrecte pour les diffusions d'exécution de messages transactionnels.
* Correction d'un problème qui se produisait lors de l'import d'un package avec une configuration d'événement et le message transactionnel associé. Consultez à ce sujet la [documentation détaillée](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Correction d'un problème qui supprimait les données de collecte des profils de test créés pour un message transactionnel contenant des listes de produits.

### Autres changements {#other-changes}

* Une nouvelle option a été ajoutée au compte externe SMS. Elle permet de limiter le nombre maximal de processus MTA envoyant des SMS afin de mieux contrôler le nombre de connexions parallèles. Pour plus d'informations, consultez la technote [Protocole et paramètres du connecteur SMS](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).
* Lors de la publication d'une ressource avec une extension d'API, si l'API a déjà été publiée, elle est automatiquement mise à jour à chaque nouvelle publication. Auparavant, cette action était manuelle et le fait de ne pas mettre à jour l'API pouvait endommager la ressource profil ou les ressources de services de celle-ci. Consultez à ce sujet la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimension de code postal a été supprimée des rapports dynamiques. Il est recommandé d'utiliser plutôt les dimensions de ville, pays et état.
* Le trigger d'événement de cycle de vie "Premier lancement" pour les messages In-App a été supprimé.
* Lors de l'export d'un package avec des groupes de sécurité, celui-ci contient désormais les rôles attribués à chaque groupe. (CAMP-32960)
* Dans l'activité Chargement de fichier, une nouvelle option permet de vérifier que les colonnes du fichier téléchargé correspondent à la définition de colonne. Pour plus d'informations, consultez la [documentation détaillée](../../automating/using/load-file.md). (CAMP-32229)
* Les workflows peuvent maintenant être démarrés avec une payload, ce qui permet d'utiliser et de partager des paramètres externes entre les activités au sein d'un workflow. Pour plus d'informations, consultez la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 et CAMP-29413)
* Les API de Campaign Standard permettent maintenant de mettre à jour les entités géographiques et organisationnelles des profils à l'aide d'une payload. Pour plus d'informations, consultez la [documentation détaillée](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* Les messages d'erreur qui s'affichent lorsqu'un objet de la base de données n'est pas accessible ont été clarifiés.
* Dans l'activité Extraction de fichier, les capacités Javascript ont été mises à jour lors de la définition du nom d'un fichier à exporter. Seule la fonction formatDate est maintenant disponible pour une utilisation dans le champ Sortie. Pour plus d'informations, consultez la [documentation détaillée](../../automating/using/extract-file.md).
* La génération automatique d'ID de séquence a été améliorée pour les ressources personnalisées. Les clés primaires pour les nouvelles ressources personnalisées sont maintenant 64 bits par défaut.
* Le mode de test de publication de ressource personnalisée a été amélioré. Un message d'avertissement s'affiche maintenant si la dernière publication de ressource personnalisée est en échec et n'est pas corrigée. Après un échec de publication de ressource personnalisée, vous pouvez revenir à la dernière version opérationnelle. Pour plus d'informations, consultez la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Une nouvelle option a été ajoutée à l'activité Transfert de fichier. Elle permet de trier les fichiers lorsque vous utilisez l'action de téléchargement de fichier, en mode SFTP. Pour plus d'informations, consultez la [documentation détaillée](../../automating/using/transfer-file.md). (CAMP-33109)

### Correctifs {#patches}

* Correction d'un problème qui entraînait une fuite de mémoire sur le MTA lorsque les paramètres SMS étaient rechargés.
* Correction d'un problème qui empêchait la publication des mises à jour de la base de données en mode de réparation.
* Correction d'un problème qui entraînait des divergences entre les rapports Adobe Analytics et les rapports dynamiques Adobe Campaign. (CAMP-25393)
* Correction d'une erreur qui entraînait l'échec du workflow de partage de rapport.
* Correction d'une erreur qui empêchait les utilisateurs d'envoyer des messages In-App avec uniquement l'URL de média.
* Correction d'un problème qui affichait une application mobile, même si son certificat n'était pas téléchargé sur l'instance.
* Correction d'une erreur qui empêchait les champs de personnalisation de fonctionner lors de l'utilisation du modèle **Cibler tous les utilisateurs d'une application mobile**.
* De nouvelles instances de Campaign Standard ont été configurées. (CAMP-32635 et CAMP-32344)
* Correction d'une erreur qui empêchait la personnalisation de la formule de date dans un workflow. (CAMP-30336)
* Correction d'un problème lors de la définition d'une formule de date personnalisée qui pouvait empêcher les champs "Données additionnelles" et "Code segment" d'être disponibles dans la liste déroulante. (CAMP-32383)
* Correction d'un problème qui pouvait empêcher les activités "Transfert de fichier" et "Extraction de fichier" de rechercher les rejets de fichiers s'ils étaient cryptés. (CAMP-32377)
* Correction d'un problème dans les API qui pouvait empêcher le filtre lineCount d'afficher le nombre total exact. (CAMP-31424)
* Correction d'un problème dans les landing pages qui empêchait les champs d'entrée d'afficher la valeur mise à jour une fois celle-ci modifiée. (CAMP-31401)
* Correction d'un problème qui entraînait l'activation inattendue d'une activité de signal.
* Correction d'un problème qui empêchait l'affichage de l'aperçu d'un email lorsque l'audience était vide.
* Correction d'un problème dans l'activité "Extraction de fichier" qui entraînait la génération d'un fichier alors que l'option "Ne pas générer de fichier si la transition entrante est vide" était activée.
* Correction d'un problème qui entraînait la désactivation du workflow de délivrabilité s'il ne se terminait pas correctement.
* Correction d'un problème qui empêchait les utilisateurs d'enregistrer ou de planifier des rapports. (CAMP-31133)

## Version 19.1.3 - Mars 2019 {#release-19-1-3---march-2019}

### Améliorations du Concepteur d'email {#email-designer-enhancements-1}

* Correction d'un problème qui empêchait la modification d'un modèle après son enregistrement.
* Résolution de divers problèmes qui pouvaient se produire dans les emails lors de l'utilisation d'un modèle créé auparavant.
* Correction d'un problème qui empêchait le masquage des composants dans les modèles importés.

### Autres améliorations {#other-improvements}

* Correction d'une erreur qui se produisait lors de l'affichage des règles de typologie. (CAMP-32059 et CAMP-31849)
* Correction d'un problème qui empêchait l'édition des règles de typologie. (CAMP-31750)
* Correction d'un problème lié au processus inMail qui pouvait s'arrêter de manière inattendue. (CAMP-31238)

## Version 19.1 - Février 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Améliorations du reporting du canal push<br /> </td> 
   <td> <p>Plusieurs améliorations ont été apportées au reporting du canal push afin de mesurer l'engagement des utilisateurs de manière plus intuitive. Avec cette version, la liste des mesures du canal push compte désormais trois mesures différentes : Impressions, Clics, Ouvertures (ouverture de l'application). Celles-ci vous permettent de mesurer et d'analyser plus efficacement l'interaction des utilisateurs avec les notifications push. Nous normalisons également la définition et la mise en œuvre de ces mesures. Le rapport intégré relatif aux notifications push a également été amélioré. Il comporte désormais des visualisations et des mesures couramment utilisées.</p><p> Pour plus d'informations, consultez la <a href="../../reporting/using/push-notification-report.md">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Launch pour les applications mobiles<br /> </td> 
   <td> <p>Cette version contient l'intégration d'Adobe Campaign avec les versions de disponibilité générale des extensions Android et iOS pour Adobe Campaign Standard dans les SDK Adobe Experience Platform Launch et Mobile. Ces extensions prennent en charge la messagerie push, la messagerie In-App et les mises à jour des profils des applications mobiles.</p><p> Pour plus d'informations, consultez la <a href="../../administration/using/about-typology-rules.md#typology-rules">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Messagerie In-App mobile<br /> </td> 
   <td> <p>Cette version contient la version de disponibilité générale du canal In-App dans Campaign. D'un point de vue fonctionnel, les ajouts les plus importants à la version bêta sont les rapports dynamiques pour le canal In-App et l'établissement d'une liaison sécurisée entre le SDK Mobile et MCIAS (service de messagerie In-App Marketing Cloud qui fournit les règles In-App au SDK). L'établissement d'une liaison sécurisée garantit que les données PII de vos utilisateurs ne tombent pas entre des mains malveillantes. Il permet également de préserver la confidentialité de l'utilisateur sur un appareil partagé en effaçant le cache des messages chaque fois que l'utilisateur se déconnecte.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a> et le <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">tutoriel In-App</a> dédié.</p> </td> 
  </tr> 
  <tr> 
   <td> Améliorations des workflows<br /> </td> 
   <td> <p>Les capacités de workflow suivantes ont été ajoutées :</p> 
    <ul> 
     <li> Vous pouvez maintenant copier-coller des activités au sein d'un workflow ou d'un autre à partir d'une même instance de Campaign. Ainsi, vous pouvez facilement dupliquer un workflow entier ou des activités spécifiques, tout en conservant les paramètres initialement définis. Pour plus d'informations, consultez la <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentation détaillée</a>. (CAMP-20014) </li> 
     <li> Lors de l'utilisation de l'activité <strong>Chargement de fichier</strong>, vous pouvez maintenant ajouter un horodatage au nom du fichier contenant les enregistrements rejetés. Pour plus d'informations, consultez la <a href="../../automating/using/load-file.md#configuration">documentation détaillée</a>. </li> 
     <li> Les activités <strong>Requête</strong> et <strong>Segmentation</strong> permettent désormais d'activer une transition sortante si les activités ne récupèrent aucune donnée. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Améliorations de la sécurité {#security-enhancements-1}

* Le code HTML de landing page généré a été mis à jour afin d'empêcher toute indexation par les moteurs de recherche.

### Améliorations du Concepteur d'email {#email-designer-enhancements-2}

* Un ensemble de quatre modèles d'email réactif conçus par des artistes Behance est maintenant disponible.

   Pour plus d'informations, consultez la [documentation détaillée](../../start/using/about-templates.md#content-templates).

* Notre nouvelle expérience d'intégration vous permet de commencer à créer plus rapidement des emails et facilite l'accès à la documentation et aux tutoriels.

   Pour plus d'informations, consultez la [documentation détaillée](../../designing/using/about-email-content-design.md#email-designer-home-page).

* Vous avez maintenant la possibilité de configurer le nombre et la largeur des colonnes en fonction de vos besoins.

   Pour plus d'informations, consultez la [documentation détaillée](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* Lors de l'édition dans la vue mobile, vous pouvez masquer certains composants uniquement dans l'affichage mobile pour utiliser efficacement l'espace.

   Pour plus d'informations, consultez la [documentation détaillée](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* Vous pouvez maintenant ajouter des canaux sociaux personnalisés à votre modèle d'email en plus de ceux déjà disponibles.
* Correction d'un problème qui empêchait de faire défiler le menu de structure lorsque plus de 18 structures étaient utilisées. (CAMP-31173)
* Correction d'un problème qui affichait le pré-en-tête en haut du contenu lors du transfert d'un email contenant un pré-en-tête envoyé avec Adobe Campaign. (CAMP-30736)
* Correction d'un problème qui empêchait la mise à jour de la ligne d'objet lorsque l'utilisateur cliquait sur l'option **Actualiser le contenu AEM** après avoir modifié l'objet dans Adobe Experience Manager. (CAMP-29984)
* Correction de plusieurs problèmes qui empêchaient l'utilisation d'images dynamiques d'Adobe Target.
* Correction d'un problème qui empêchait la mise à jour de l'aperçu lors de la récupération du contenu au moment de la préparation si le contenu avait déjà été importé à partir d'une URL.
* L'icône YouTube a été ajoutée au composant de contenu **Social**.
* La vue **Liste** a été ajoutée pour les composants de contenu et les fragments affichés dans la palette du Concepteur d'email.

### Autres améliorations {#other-improvements-1}

* Adobe Campaign est désormais entièrement compatible FCM pour les applications SDK V4 et SDK AEP.
* Adobe Campaign prend en charge les notifications push sous Wear OS (Android) et watchOS (Apple).
* Les messages d'avertissement et d'erreur pouvant s'afficher lors de la navigation dans l'interface ont été clarifiés et simplifiés.
* Vous pouvez maintenant ajouter à la liste des profils des colonnes relatives à l'opt-in et l'opt-out (champs "Ne plus contacter…").
* La liste déroulante Fuseau horaire de l'écran de création de profil a été déplacée de la section Adresse vers la section supérieure de l'interface.
* Vous pouvez maintenant ajouter des séparateurs lors de la configuration d'écrans de ressources personnalisés, ce qui vous permet d'organiser vos champs en catégories.

   Pour plus d'informations, consultez la [documentation détaillée](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Autres changements {#other-changes-1}

* A compter du printemps 2019 et de la version Campaign Standard 19.2, Adobe Campaign et Adobe Experience Cloud arrêteront la prise en charge de Microsoft Internet Explorer 11. Passez à Microsoft Edge ou tout autre navigateur pris en charge. Consultez la page [Fonctionnalités supprimées et obsolètes](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).
* Le champ **Code pays** de la ressource Profil a été renommé en **Code pays/zone géographique**.

### Correctifs {#patches-1}

* Correction d'un problème qui empêchait l'envoi du message lors de l'ajout d'un profil de test à un message transactionnel d'email. (CAMP-29854)
* Correction d'un problème qui ralentissait l'envoi des messages à partir d'autres canaux si l'envoi était faible pour un canal lorsque l'envoi des messages à partir de tous les canaux était déclenché simultanément.
* Correction d'un problème en raison duquel le MTA commençait à envoyer des SMS lorsque la connexion au compte externe n'était pas encore établie.
* Correction d'un problème lié à la fréquence d'exécution et à l'heure de début de l'activité Planificateur. (CAMP-30745)
* Correction d'un problème lié à la génération PKEY qui se produisait lors de l'utilisation de ressources de profil étendues. (CAMP-30285)
* Correction d'un problème qui se produisait avec les règles de fatigue basées sur un jour calendaire. (CAMP-30136)
* Correction d'un problème qui se produisait lors de la tentative d'accès à des ressources personnalisées dont les noms se terminaient par "Base". (CAMP-30109)
* Correction d'un problème qui empêchait l'utilisation d'un appel PATCH pour abonner un profil à un service. (CAMP-29728)
* Correction d'un problème qui endommageait un workflow lors de l'import d'un fichier XML par le biais de l'activité Chargement de fichier. (CAMP-29208 et CAMP-28205)
* Correction d'un problème qui empêchait la génération de liens de cardinalité inversée lors de la liaison de ressources personnalisées. (CAMP-30476)
* Correction d'un problème qui empêchait l'extension des logs de diffusion lors de l'utilisation du code de segment uniquement.
* Correction d'un problème qui entraînait la duplication de lignes lors de l'utilisation de l'activité Transfert de fichier dans les workflows.
* Correction d'un problème qui empêchait l'envoi des rapports planifiés à l'heure choisie.
* Correction d'un problème qui entraînait une différence entre les KPI "A envoyer" et "Envoyés" pour une diffusion In-App dans un workflow.
* Correction d'un problème qui empêchait le fonctionnement du tracking pour un message In-App créé avec du code HTML personnalisé.
* Correction d'un problème qui empêchait l'enregistrement du contenu d'une diffusion In-App lorsqu'il était utilisé dans un workflow.
* Correction d'un problème qui empêchait l'affichage des applications mobiles pour les administrateurs.
* Correction d'un problème qui entraînait l'échec du workflow technique Mise à jour pour la délivrabilité. (CAMP-26387)
* Correction d'un problème qui entraînait une différence entre les profils ciblés lors de la création d'une diffusion In-App et ceux affichés dans le tableau de bord de la diffusion. (CAMP-28722)
* Correction d'un problème lié à l'intégration de Campaign avec Assets Core Service qui empêchait la sélection d'une ressource partagée dans un email.

## Version 19.0 - Janvier 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Disponibilité générale du Concepteur d'email<br /> </td> 
   <td> <p>Le nouveau Concepteur d'email intuitif (anciennement Creative Designer) est passé à la phase de disponibilité générale. Il prend maintenant en charge toutes les fonctionnalités de l'ancien éditeur de contenu, notamment :</p> 
    <ul> 
     <li> Utilisation des <a href="../../integrating/using/adding-target-dynamic-content.md">images dynamiques d'Adobe Target</a> </li> 
     <li> Possibilité de <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">récupérer automatiquement du contenu depuis une URL au moment de la préparation</a> </li> 
     <li> <a href="../../start/using/about-templates.md#content-templates">Modèles de contenu d'usine</a> entièrement compatibles </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. Les améliorations et les correctifs sont répertoriés ci-dessous.</p><p> Par conséquent, l’ancien éditeur de contenu d’email est maintenant obsolète. Pour plus d'informations, consultez cette <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listes des produits dans les emails transactionnels<br /> </td> 
   <td> <p>Vous pouvez maintenant référencer une ou plusieurs collections de produits dans un email transactionnel. Vous pouvez par exemple envoyer automatiquement un email d'abandon de panier répertoriant tous les produits qui étaient dans le panier de l'utilisateur avec une image, le prix et un lien vers chaque produit.</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vue mobile dans le Concepteur d'email<br /> </td> 
   <td> <p>Vous pouvez maintenant basculer vers une vue mobile dédiée lors de l'édition du contenu d'un email. Vous pouvez ainsi affiner le responsive design d'un email en éditant séparément toutes les options de style pour l'affichage mobile, (adapter les marges, réduire la taille des polices, changer de couleur fond, etc.).</p><p> Pour plus d'informations, consultez la <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Améliorations de la Messagerie In-App (version bêta)<br /> </td> 
   <td> <p>La fonctionnalité Messagerie In-App (version bêta) a été améliorée avec l'ajout des capacités suivantes :</p> 
    <ul> 
     <li> Compatibilité du canal In-App (version bêta) avec le RGPD </li> 
     <li> Intégration avec les API Analytics pour peupler les listes déroulantes des Triggers </li> 
     <li> Aspect intuitif et description des modèles de diffusion </li> 
     <li> Améliorations apportées à l'interface de création du point de vue de la convivialité </li> 
    </ul> <p>Pour plus d'informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Améliorations {#improvements}

* Une nouvelle option de l'activité de chargement de données permet désormais d'appliquer une étape de post-traitement au fichier contenant les enregistrements rejetés (ex. compression au format zip). (CAMP-24521)
* Une nouvelle option de l'activité Mise à jour de données vous permet maintenant de configurer la taille maximale des mises à jour pour les données à télécharger. (CAMP-28400)
* Amélioration de la sélection de l'état des adresses des profils Lors de la sélection d'un pays, la liste déroulante "Etat" est maintenant automatiquement mise à jour avec les valeurs d'état correspondantes. (CAMP-28874)
* Une nouvelle option de l'activité Extraction de fichier empêche désormais la génération d'un fichier si la transition entrante est vide. Ainsi, des fichiers vides ne sont pas créés et téléchargés sur les serveurs SFTP.
* Le rapport Synthèse des diffusions a été amélioré.
* La liste des pays disponibles lors de la définition de l'adresse d'un profil a été enrichie. (CAMP-26707)
* Un message d'erreur s'affiche maintenant lorsque vous essayez d'importer un workflow intégré.

### Concepteur d'email {#email-designer}

* Correction d'un problème qui entraînait l'activation de la fonctionnalité d'entité géographique sur un modèle d'email ou un fragment de contenu créé dans le Concepteur d'email, même si cette fonctionnalité était désactivée dans Adobe Campaign, ce qui rendait le modèle ou le fragment indisponible lors d'une nouvelle tentative d'accès. (CAMP-28174)
* Correction d'un problème qui empêchait l'enregistrement des conditions de contenu dynamique lors de l'édition de contenu dans le Concepteur d'email. (CAMP-27905)
* Correction d'un problème qui entraînait la suppression de la version HTML du contenu de l'email après avoir édité la version en texte brut d'un message et interrompu la synchronisation HTML dans le Concepteur d'email. (CAMP-28507)
* Correction d'un problème qui empêchait l'ouverture de l'interface du Concepteur d'email lors de l'utilisation d'Internet Explorer 11. (CAMP-28273)
* Correction d'un problème qui déformait le rendu des paramètres de style Microsoft Outlook appliqués aux boutons avec le Concepteur d'email.
* Correction d'un problème lié au Concepteur d'email qui rendait éditable l'URL d'un fragment de contenu utilisé dans un email, ce qui n'était pas prévu, le fragment étant verrouillé par défaut.
* Correction d'un problème qui empêchait l'affichage du composant diviseur du Concepteur d'email dans Microsoft Office.
* Correction d'un problème qui entraînait le gel des pages de certains navigateurs Internet lors de l'affichage d'un contenu synchronisé à partir d'AEM à l'aide de l'ancien éditeur de contenu d'email. (CAMP-29068)
* Correction d'une erreur qui se produisait lors d'un clic sur une image dans un email lorsque l'ancien éditeur de contenu d'email était utilisé. (CAMP-30424)
* Correction d'un problème qui empêchait l'affichage des fragments nouvellement créés lors de l'édition d'un email dans le Concepteur d'email. (CAMP-29928)
* Correction d'un problème qui empêchait l'affichage correct du texte des boutons dans les emails créés avec le Concepteur d'email et reçus à l'aide du client webmail Outlook.
* Il est maintenant possible de créer des messages transactionnels de profil à l'aide du Concepteur d'email. (CAMP-28900)
* Correction d'une erreur dans le Concepteur d'email qui rendait le contenu éditable lors de la récupération automatique du contenu d'une URL au moment de la préparation, alors qu'il devait être verrouillé.

### Correctifs {#patches-2}

* Correction d'un problème qui entraînait l'affichage de logs de diffusion incorrects dans les rapports dynamiques. (CAMP-23446)
* Correction d'un problème qui avait un impact sur les chiffres du rapport de synthèse des bounces (CAMP-28703).
* Correction d'un problème lié à l'intégration de Campaign avec Assets Core Service qui empêchait l'affichage des ressources lors de la sélection de l'option **[!UICONTROL Image partagée depuis Adobe Experience Cloud]dans un email (CAMP-28732).**
* Correction d'un problème qui empêchait l'envoi de SMS contenant le caractère 'œ' bien que la translittération soit autorisée dans le compte externe SMPP. (CAMP-29041)
* Correction d'un problème qui entraînait l'affichage d'enregistrements en double lors de l'utilisation d'une activité Segmentation dans des workflows. (CAMP-28743)
* Correction d'un problème qui empêchait la suppression de l'une des correspondances de valeurs sur une colonne dans une activité de workflow. (CAMP-28708)
* Correction d'un problème lié à l'activité Transfert de fichiers lors de l'utilisation de caractères génériques avec l'option "Test d'existence de fichier". (CAMP-28977)
* Correction d'un problème lié à l'activité Transfert de fichiers qui se produisait lors de la mise à jour des paramètres des comptes externes. (CAMP-28894)
* Correction d'un problème lié aux filtres personnalisés dans le requêteur lors de l'utilisation de la condition "Email n'est pas vide". (CAMP-28741)
* Correction d'un problème qui se produisait lors de l'export de tables de ressources personnalisées contenant plus de 100 000 enregistrements. (CAMP-28150)
* Correction d'un problème qui empêchait la suppression des messages transactionnels liés à des triggers. (CAMP-28385)
* Suppression des mots de passe qui étaient affichés de manière non sécurisée dans certains logs SMS.
* Correction d'un problème en raison duquel les connexions au simulateur SMPP échouaient en raison d'un mot de passe vide envoyé par Adobe Campaign.
* Correction d'un problème qui empêchait l'envoi de campagnes lorsque les connexions SMS étaient instables.
* Correction d'un problème qui entraînait l'affichage de diffusions supprimées dans les rapports dynamiques.
* Correction d'un problème qui empêchait la récupération des données additionnelles des tables des exclus, des logs de diffusion et du tracking lors de l'utilisation d'une activité Enrichissement dans un workflow.
* Correction d'un problème lié aux demandes de suppression RGPD qui se produisait lors de l'utilisation d'un type de lien "Lien de collection de cardinalité N" et de l'option "La suppression de l'enregistrement cible entraîne la suppression des enregistrements référencés par le lien".
* Correction d'un problème lié au partage des rapports.
* Correction d'un problème qui entraînait des problèmes de débit lors de l'envoi d'une notification push.
* Correction d'un problème lié à des champs absents dans les fichiers de sortie du courrier.
* Correction d'un problème qui permettait aux utilisateurs de modifier les workflows intégrés.
* Correction d'un problème lors de la création d'une campagne à partir d'un modèle de campagne comprenant un workflow avec une activité d'extraction configurée. (CAMP-29198)
* Correction d'un problème lié à l'activité d'extraction de fichiers qui empêchait d'utiliser la même expression pour plusieurs éléments. (CAMP-29182)
* Dans l'éditeur de requête, correction d'un problème lié à la condition de jointure entre le broadlog et le log de tracking pour rtEvent. (CAMP-28780)
* Correction d'un problème qui empêchait l'enregistrement des modifications apportées à l'option de page d'entrée "Action spécifique". (CAMP-29422)
* Correction d'un problème qui empêchait d'exporter la payload d'un événement dans un workflow. (CAMP-29029)
* Correction d'un problème qui empêchait les numéros de SMS blacklistés d'être exclus dans un message SMS. (CAMP-28898)
* Correction d'un problème qui empêchait les fournisseurs SMPP d'être avertis en cas d'erreur lors du traitement des messages entrants. (CAMP-29804)
* Correction d'un problème qui autorisait la suppression de comptes externes avec les diffusions associées. (CAMP-29738)
* Le débit d'envoi a été amélioré et stabilisé pour les messages SMS.
* Correction d'un problème qui empêchait l'utilisation du caractère "~" dans un message SMS. (CAMP-29172)
* Correction d'un problème de diffusions avec l'option d'optimisation de l'heure d'envoi. (CAMP-29231)

