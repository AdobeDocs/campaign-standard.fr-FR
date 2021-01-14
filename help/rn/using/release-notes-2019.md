---
solution: Campaign Standard
product: campaign
title: Notes de mise à jour            2019
description: Cette page répertorie toutes les versions 2019 d’Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: ht
source-git-commit: 5758e5f0f6811a97f51e995fa3c378a7c7117ff5
workflow-type: ht
source-wordcount: '7630'
ht-degree: 100%

---


# Notes de mise à jour 2019{#release-notes-2019}

[Calendrier des versions](https://helpx.adobe.com/fr/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour les plus récentes](../../rn/using/release-notes.md) | [Fonctionnalités obsolètes](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr)

## Version 19.4 - Décembre 2019 {#release-19-4---october-2019}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le CCPA est la nouvelle loi sur la protection de la vie privée de l’État de Californie. Il harmonise et modernise les exigences en matière de protection des données qui entreront en vigueur le 1er janvier 2020. Il s’applique aux clients Adobe Campaign qui détiennent des données pour des titulaires de données résidant en Californie.</p>
   <p>Outre les fonctionnalités de confidentialité déjà disponibles dans Adobe Campaign (notamment la gestion du consentement, les paramètres de conservation des données et les rôles utilisateur), nous incluons d’autres fonctionnalités pour faciliter votre préparation au CCPA :</p>
   <ul>
    <li>Droit d’accès et droit de suppression : nous tirons parti des capacités qui ont été ajoutées pour le RGPD. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#righttoaccess">En savoir plus</a> </li>
    <li><p>Lors de la création d’une demande d’accès à des informations personnelles, le type de réglementation (RGPD ou CCPA) a été ajouté à Privacy Core Service. Cette méthode est celle que vous devez utiliser pour toutes les demandes d’accès et de suppression. L’utilisation de l’API et de l’interface de Campaign pour les demandes d’accès et de suppression est obsolète.  Consultez l’article <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr">Fonctionnalités obsolètes et supprimées</a>.</p></li>
    <li>Un champ <strong>Option d’opt-out du CCPA</strong> a été ajouté à la ressource Profils pour permettre aux utilisateurs d’Adobe Campaign de déterminer si un client s’est opposé à la vente de ses informations personnelles. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#ccpa">En savoir plus</a>.</li>
  </ul>
    <p>Reportez-vous à la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/privacy/privacy-overview.html">vidéo pratique</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Intégration de Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>L’intégration entre Adobe Campaign Standard et Microsoft Dynamics 365 est maintenant disponible. Vous pourrez transférer vos enregistrements de contacts et d’entités personnalisées de Dynamics 365 vers Campaign et récupérer les données d’événement d’email à partir de Campaign dans Dynamics 365 pour un meilleur alignement du marketing sur les ventes.</p>
    <p>Reportez-vous à la <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">documentation détaillée</a> pour configurer cette intégration et voir la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">vidéo pratique</a>.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Le pop-up de consentement pour la création de rapports dynamiques a été mis à jour afin d’inclure l’intégration de Microsoft Dynamics 365 et Adobe Campaign Standard. En acceptant les termes, les données de profil seront incluses lors de l’utilisation de l’intégration Adobe Campaign Standard/Microsoft Dynamics 365 et de la création de rapports dynamiques. [En savoir plus](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Correction d’un problème qui affichait des dates de contact incorrectes lors de la réception d’alertes de diffusion.
* Lorsqu’un événement de message transactionnel est envoyé avec un paramètre de contexte inconnu, Campaign renvoie maintenant un message d’erreur « 400 »au lieu de « 500 ». (CAMP-28632)
* Un nouveau segment **Exclure le BAT** a été ajouté dans les rapports dynamiques. Ce segment est désormais sélectionné par défaut pour filtrer les rapports. [En savoir plus](../../reporting/using/list-of-components-.md#segments)
* L’option **Expiration du message** a été ajoutée à la notification push. Elle vous permet de spécifier une date d’expiration à laquelle le message ne sera plus envoyé par Apple (APNS) ou Android (FCM). [En savoir plus](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Des améliorations ont été apportées à l’activité **Chargement de fichier** : les logs des workflows ont été rendus plus clairs et plus détaillés sur l’erreur qui se produit lorsqu’un fichier ne se charge pas. La transition sortante générée lors de l’activation de l’option **Conserver les rejets dans un fichier** a été renommée **Rejets**. [En savoir plus](../../automating/using/load-file.md)
* Des logs associés multilingues ont été ajoutés aux logs d’envoi afin de mieux comprendre les échecs d’envoi en raison de langues manquantes dans les fichiers CSV téléchargés.

**Améliorations de la sécurité**

* Correction d’un problème lors de la suppression des informations d’un profil en quarantaine par le biais d’une demande d’accès à des informations personnelles. Celui-ci entraînait la suppression de toutes les données, à l’exception de l’adresse email dans la liste de quarantaine.
* La sécurité de la protection contre les injections dans les en-têtes d’email a été améliorée.
* La sécurité a été renforcée pour la protection contre les attaques SSRF où les expressions xtk peuvent être utilisées (HTML d’email, contenu texte et objet, SMS et contenu de notification push).

**Améliorations du Concepteur d’email**

* Correction d’un problème qui empêchait le suivi des liens de désabonnement, d’abonnement et de landing page lorsqu’ils étaient insérés dans un email. (CAMP-37809)
* Correction d’un problème susceptible d’entraîner des erreurs lors de la création d’un email et de la sélection d’un modèle. (CAMP-38000)
* Lors de l’édition d’un lien à l’aide du Concepteur d’email, vous pouvez désormais utiliser l’option **Souligner le lien**. En outre, la propriété **Cible** a été ajoutée avec la valeur par défaut définie sur **Aucune**. [En savoir plus](../../designing/using/styles.md#about-styling-links)
* Correction d’un problème de couleur sur les liens au sein des composants de texte dans le corps d’un email. (CAMP-37330)
* Correction d’un problème qui empêchait la suppression des liens associés lors de la suppression d’une image. (CAMP-37234)
* Correction d’un problème qui empêchait l’enregistrement des modifications des paramètres **Ordre de priorité** du contenu dynamique dans une condition. (CAMP-36883)
* Correction d’un problème lors de la recherche de landing pages. La recherche a été étendue des 50 premiers enregistrements créés à toute la base de données. (CAMP-36839)
* Correction d’un problème lors de l’enregistrement des modifications de l’expéditeur de l’email dans le champ **De : Nom**. (CAMP-36606)
* L’avertissement de compatibilité des composants du carrousel a été modifié pour prendre en compte les clients d’email pris en charge.
* Correction d’un problème d’affichage sur mobile. L’attribut height est maintenant toujours défini sur &quot;height: auto&quot; lors de l’ajout ou du téléchargement d’une nouvelle image dans un email. (CAMP-35497)
* Correction d’un problème en raison duquel les balises style et meta étaient conservées dans le code HTML lors de la suppression d’un fragment d’un composant de structure. (CAMP-35390)
* Correction d’un problème lié aux fragments lors de la mise à jour d’un contenu réutilisable. (CAMP-35186)
* Correction d’un problème lors de l’affichage du contenu conditionnel pour mobiles uniquement dans les emails. (CAMP-35155)
* Correction d’un problème qui affichait de manière aléatoire des espaces insécables de largeur nulle. (CAMP-35116)
* Correction d’un problème lié à la position des boutons dans la boîte de dialogue **Enregistrer en tant que fragment**.
* Correction d’un problème d’aperçu lors de l’ajout d’une balise HTML dans un titre d’image et un texte alternatif.
* Correction d’un problème lors de l’édition, dans le Concepteur d’email, des liens créés dans des emails à partir de l’ancien éditeur.
* Correction d’un problème en raison duquel les balises de style étaient dupliquées dans le contenu.
* Correction d’un problème lié au format de date lors de l’insertion d’un champ de personnalisation dans un email.
* Correction d’un problème d’enregistrement lors du passage du mode HTML au texte brut.
* Correction d’un problème en cas de clic sur l’option de verrouillage et de déverrouillage. Celui-ci ajoutait des valeurs de marge dans le panneau des propriétés de style intégré.
* Correction d’un problème lié à la taille de l’aperçu mobile pour un meilleur rendu.
* Correction d’un problème lié à la taille des boutons dans les modèles et les fragments.
* Correction d’un problème lié à la taille des images lorsqu’elles étaient insérées dans un composant de bouton.

**Autres changements**

* La période par défaut pour laquelle les données sont affichées sur les pages des KPI de diffusion et sur la page de création de rapports dynamiques a été alignée afin d’éviter toute incohérence dans les résultats des rapports. (CAMP-35148)
* Un message d’erreur a été ajouté dans les logs lors de l’expiration du certificat de l’application.
* L’aperçu du calcul de payload inclut maintenant une taille de champ personnalisée afin d’éviter les échecs de notification push. (CAMP-35303)
* Le nom du **fichier Rejets** dans l’activité **Chargement de fichier** peut maintenant être personnalisé de la même manière que dans l’activité **Exportation de fichier**.
* Toutes les entités personnalisées qui ne sont liées à aucune entité d’usine sont désormais accessibles via l’API.
* Amélioration des performances de la base de données sur les ressources volumineuses.
* La description de certaines erreurs se produisant lors de l’envoi de SMS a été rendue plus claire. (CAMP-36558)
* Un message d’erreur s’affiche maintenant lors de l’exécution de l’activité **Planificateur** d’un workflow qui est connecté à lui-même, soit directement, soit par le biais de plusieurs activités, car cela peut entraîner le blocage du serveur des workflows de l’instance.
* Des améliorations ont été apportées pour résoudre les problèmes de messagerie transactionnelle : le lien &quot;Données&quot; a été renommé &quot;Derniers événements transactionnels&quot; dans l’écran de configuration de l’événement. Il répertorie désormais les événements reçus triés dans un ordre décroissant. Un nouvel état d’événement transactionnel a également été créé : &quot;targetingFailed&quot;. Lorsque le module de messagerie transactionnelle ne parvient pas à enrichir un lien utilisé pour le ciblage des messages, l’événement transactionnel se trouve désormais dans ce nouvel état (au lieu de l’état &quot;routingFailed&quot;).
* Des améliorations ont été apportées à l’interface lors de la limitation de l’accès à une landing page à des entités géographiques ou organisationnelles spécifiques. L’objectif est d’avertir que la landing page peut être soumise à des conditions de visibilité : la sélection d’une entité géographique et organisationnelle lors de la création d’une landing page est désormais obligatoire. Une bannière contenant des informations connexes s’affiche désormais une fois qu’une entité est sélectionnée. Le message d’erreur qui s’affiche lors du test de la landing page est plus clair.
* Dans les API Campaign Standard, les clés personnalisées ne peuvent pas être modifiées à l’aide d’une opération PATCH si la valeur de la clé est différente de celle de la clé d’origine ou si vous utilisez votre propre clé d’entreprise comme URI au lieu de celle fournie par Adobe.
* La langue &quot;Albanais - Macédoine&quot; a été ajoutée à la liste déroulante des préférences linguistiques. (CAMP-35396)

**Correctifs**

* Correction d’un problème qui empêchait le tri ou la recherche des rapports planifiés.
* Correction d’un problème lié aux règles Triggers en raison duquel les règles ET et OU étaient mélangées.
* Correction d’un problème en raison duquel la propriété Mobile s’affichait comme Supprimé dans Launch. (CAMP-35382)
* Correction d’un problème qui empêchait la synchronisation des propriétés mobiles d’Adobe Launch dans Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Correction d’un problème en raison duquel les messages push transactionnels échouaient lorsque des événements étaient enrichis avec des données de profil. (CAMP-34385)
* Correction d’un problème en raison duquel les propriétés mobiles ne se synchronisaient pas dans plusieurs environnements. (CAMP-37060)
* Correction d’un problème lors de la sélection, dans une notification push, d’un modèle à l’aide d’une formule de date de contact. (CAMP-35300)
* Correction d’un problème en raison duquel le service d’envoi de messages pouvait se bloquer. (CAMP-35287)
* Correction d’un problème lié aux courriers récurrents, tous définis avec la date du premier événement. (CAMP-35139)
* Correction d’un problème lié aux ressources personnalisées **Profils** nouvellement étendues qui n’étaient pas disponibles pour les requêtes. (CAMP-35119)
* Correction du mode **Réparer la structure de la base de données** pour les instances avec la configuration de partage activée. (CAMP-35118)
* Correction d’un problème qui entraînait une erreur de log SQL lors de l’ajout de données agrégées sur les broadlogs. (CAMP-35034)
* Correction d’un problème lié aux transitions lors de la création d’une activité **Segmentation**. (CAMP-35033)
* Correction d’un problème dans l’activité **Requête** qui empêchait la fonction **encryption_aescbcDecrypt** de déchiffrer la fonction **encryption_aescbcEncrypt**. (CAMP-34952)
* Correction d’un problème qui pouvait empêcher l’affichage des **Logs de tracking** dans les diffusions. (CAMP-34855)
* Correction d’un problème lors de l’utilisation d’une formule de date personnalisée d’**optimisation du temps d’envoi**, qui pouvait empêcher l’envoi de notifications push en raison d’erreurs liées aux données additionnelles du workflow. (CAMP-30336)
* Correction d’un problème qui pouvait empêcher la publication des ressources personnalisées. (CAMP-37425)
* Correction d’un problème qui empêchait les utilisateurs administrateurs de modifier les packages d’import.  (CAMP-37176)
* Correction d’un problème dans les workflows qui empêchait l’envoi de BAT si l’activité de diffusion était reliée à une activité **Lecture d’audience** vide. (CAMP-37164)
* Correction d’un problème qui empêchait l’import de ressources personnalisées dans un nouvel environnement. (CAMP-36506)
* Correction d’un problème dans les rapports Hot clicks, en raison duquel les pourcentages étaient masqués par les images (CAMP-36407).
* Correction d’un problème qui se produisait lors de l’export d’un champ de description de diffusion. (CAMP-35467)
* Correction d’un problème en raison duquel l’état d’une diffusion pouvait être &quot;Démarrage en attente&quot; même si la diffusion était terminée. (CAMP-35355)
* Correction d’un problème qui empêchait l’affichage des logs des workflows après activation, puis désactivation des logs SQL.

## Version 19.3 - Juillet 2019 {#release-19-3---july-2019}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Activité API externe (version bêta publique)<br /> </td> 
   <td> <p>Pour accroître la personnalisation, l’activité API externe permet de récupérer des données provenant de systèmes externes dans un workflow via un appel API REST. Les points d’entrée REST peuvent être un système de gestion client, le Runtime Adobe I/O Runtime ou un point d’entrée REST Adobe Experience Cloud (par exemple, Data Platform, Target, Analytics, Campaign).</p><p>Cette fonctionnalité est actuellement en version bêta publique.</p><p>Pour plus d’informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapport sur le segment de workflow<br /> </td> 
   <td> <p>Cette fonctionnalité permet aux marketeurs de répartir les performances de diffusion par code segment. Lorsque vous créez un workflow et que vous utilisez une activité de segmentation pour affecter des segments à la population de la diffusion, ces derniers peuvent maintenant être intégrés dans la même diffusion. Vous pouvez ainsi afficher les statistiques d’ouverture/clic selon plusieurs segments au sein d’une seule diffusion.</p><p>Pour plus d’informations, consultez la <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/reporting/report-on-workflow-segments.html">vidéo de procédure</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Améliorations de la sécurité**

* Correction d’un problème de sécurité pour empêcher les attaques par déni de service (DoS) sur les demandes d’obtention d’images non valides. (CAMP-33454)

**Améliorations du Concepteur d’email**

* Correction d’un problème qui ajoutait des balises de style HTML supplémentaires à un modèle HTML chaque fois qu’un composant était ajouté, ce qui augmentait considérablement la taille du modèle. (CAMP-34694)
* Correction d’un problème qui empêchait la disponibilité de certaines options de menu de la barre d’outils supérieure droite. (CAMP-34577)
* Correction d’un problème qui se produisait lorsque le bloc de contenu URL de la page miroir était inséré dans un contenu d’email. (CAMP-34779)
* Correction d’un problème qui se produisait lors de l’utilisation du code JPSP dans un email, rendant difficile l’édition du contenu. (CAMP-34574)
* Correction d’un problème en raison duquel les images étaient tronquées dans la partie supérieure en cas d’ajout d’un lien hypertexte sur celles-ci. (CAMP-34382)
* Correction d’un problème d’affichage lors de l’utilisation du Concepteur d’email avec Firefox. (CAMP-34364)
* Correction de plusieurs problèmes liés au mode Avancé qui se produisaient lors de la définition du contenu dynamique d’un email. (CAMP-34351, CAMP-34333, CAMP-34331)
* Correction de plusieurs problèmes liés à l’éditeur de règles de contenu dynamique (CAMP-34304, CAMP-34303).
* Correction d’un problème qui empêchait l’affichage du champ Lien dans le volet Paramètres du Concepteur d’email (CAMP-33749).
* Correction d’un problème lié à l’icône YouTube qui était surdimensionnée dans les emails envoyés. (CAMP-33726)
* Correction d’un problème de sécurité qui permettait d’éditer le contenu de la page miroir. (CAMP-33691)
* Correction d’un problème qui endommageait la sortie HTML lors de l’utilisation du symbole supérieur à dans du contenu dynamique. (CAMP-33688)
* Correction d’un problème qui se produisait lors de l’utilisation de l’option Annuler pendant l’édition de texte dans le Concepteur d’email. (CAMP-32565)
* Correction d’un problème qui créait des balises supplémentaires lors de l’annulation de styles au lieu de les supprimer. (CAMP-32359)
* Vous pouvez maintenant définir si chaque composant utilisé dans un email s’affichera uniquement sur les postes de travail ou sur les appareils mobiles.
* Vous pouvez désormais définir la largeur et la hauteur d’un composant de contenu Social.
* Correction d’un problème qui empêchait l’ancien code source d’un contenu dynamique d’être supprimé après la suppression de ce contenu dynamique.
* Correction d’un problème qui empêchait la mise à jour de l’objet d’un email après sa modification.
* Correction d’un problème qui empêchait la sélection d’une structure de colonne n:n une fois déposée dans l’espace de travail.
* Correction d’un problème en raison duquel la miniature du message apparaissait floue dans le tableau de bord de l’email.
* Correction d’un problème qui empêchait l’affichage correct de l’arrière-plan des emails reçus dans Outlook.
* Correction de certains problèmes de tri sur la page d’accueil du Concepteur d’email.
* Correction d’un problème qui se produisait lors de la duplication de variantes pendant l’utilisation de contenu dynamique.
* Certains champs indésirables ont été supprimés du volet Paramètres du Concepteur d’email.

**Autres améliorations**

* Grâce à l’intégration avec Adobe Experience Platform Location Services, Adobe Campaign est maintenant compatible pour envoyer des messages marketing géolocalisés aux abonnés de votre application mobile via le SDK Experience Platform. Pour plus d’informations, consultez la [documentation détaillée](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La fonctionnalité de reporting a été améliorée pour offrir une meilleure expérience. Pour utiliser cette fonctionnalité, vous devez accepter le contrat d’utilisation des rapports dynamiques. Consultez à ce sujet la [documentation détaillée](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Dans les workflows, une option a été ajoutée pour prévisualiser les dix prochaines exécutions d’un workflow. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Dans l’activité Planificateur, une nouvelle option permet de sélectionner un jour spécifique d’une semaine particulière pour les diffusions mensuelles. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Lors de la création de diffusions récurrentes sans période d’agrégation, le tableau de bord de diffusion permet maintenant de demander confirmation avant l’envoi de la diffusion. Consultez à ce sujet la [documentation détaillée](../../sending/using/confirming-the-send.md).
* Vous pouvez maintenant personnaliser le libellé d’une diffusion avec des variables d’événements qui ont été déclarées dans l’activité de signal externe du workflow. Consultez à ce sujet la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md).
* Amélioration de la requête de suppression RGPD pour de meilleures performances. (CAMP-33504)
* Suppression de l’option &quot;ftp&quot; de l’interface de configuration des comptes externes. (CAMP-34472)
* Vous pouvez maintenant activer et désactiver l’option Mode test SMTP pour chaque email. Consultez à ce sujet la [documentation détaillée](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Autres changements**

* Un avertissement a été ajouté à l’interface des propriétés de diffusion. Il indique que les diffusions sont préparées en fonction de leur période d’agrégation. Pour appeler le workflow plusieurs fois par jour, vous devez donc vérifier qu’elles n’ont aucune période. (CAMP-34393)
* Un avertissement a été ajouté aux écrans de configuration des ressources personnalisées. Il est recommandé d’utiliser 30 caractères maximum pour les identifiants des ressources personnalisées. Cette recommandation s’applique également aux champs de ressources personnalisées, aux clés, aux index et aux liens.
* Un message s’affiche maintenant lorsque vous essayez de supprimer un message transactionnel utilisé par une landing page en tant que message de confirmation.
* Un avertissement s’affiche maintenant dans les logs de workflow lorsqu’une activité est en cours d’exécution pendant plus de 6 heures. Cela ne s’applique pas aux activités Notification push, Diffusion, Signal, Début, Fin, Branchement, Union, Planificateur et Attente.
* Un avertissement s’affiche maintenant dans les logs de workflow lorsque vous atteignez le nombre maximal de workflows en cours d’exécution simultanément.
* Les workflows en pause ou en échec pendant plus de 7 jours sont maintenant arrêtés pour consommer moins d’espace disque. La tâche de nettoyage s’affiche dans les logs de workflow.
* Lors de l’utilisation d’une activité &quot;Transfert de fichier&quot;, une erreur est maintenant consignée si la taille du fichier dépasse l’espace disque disponible.
* L’action Rediriger vers l’URL de destination ne peut plus être sélectionnée pour le bouton secondaire dans les messages in-app.

**Correctifs**

* Correction d’un problème qui entraînait l’échec des demandes d’accès RGPD.
* Correction d’un problème qui entraînait l’annulation des Triggers lors de la réception de plusieurs Triggers pour un profil unique.
* Correction d’un problème qui entraînait un message d’erreur de publication de ressource personnalisée erroné après la connexion.
* Correction d’un problème qui affichait une page vierge lors de la création ou de l’extension d’une ressource personnalisée.
* Correction d’un problème qui empêchait une audience avec appSubscriptionrcp comme dimension de ciblage d’être disponible pour le ciblage dans une diffusion mobile.
* Correction d’une erreur qui empêchait la mise en quarantaine des adresses hard bounce. (CAMP-24587)
* Correction d’un problème qui se produisait lors de l’ajout d’une règle de typologie et qui la supprimait avant de l’enregistrer. (CAMP-32789)
* Correction d’un problème qui empêchait l’affichage du contenu de la landing page lors de la désactivation du contenu dynamique. (CAMP-32924)
* Correction d’un problème lié aux diffusions récurrentes qui se produisait lors de l’utilisation de la personnalisation sur les attributs d’une diffusion principale. (CAMP-32983)
* Correction d’un problème dans les workflows qui empêchait la lecture des résultats d’une transition contenant des données de SMS entrants. (CAMP-33134)
* Correction d’un problème dans les workflows qui se produisait lors de la combinaison d’activités de branchement et d’exclusion pour créer des audiences. (CAMP-33401)
* Correction d’un problème qui empêchait l’affichage du contenu de la page miroir et l’envoi des messages du BAT pour les diffusions récurrentes. (CAMP-33413)
* Correction d’un problème qui entraînait une erreur lors de l’utilisation d’une activité Union entre les profils et les audiences. Ce problème était dû à une incompatibilité des clés d’identification dans les transitions d’entrée. (CAMP-33713)
* Correction d’un problème dans les activités Test qui empêchait l’expression &quot;recCount&quot; d’utiliser la syntaxe correcte lors d’un double-clic dessus. (CAMP-33756)
* Correction d’un problème qui entraînait un message d’erreur lors de l’ouverture des logs de workflow technique de facturation. (CAMP-34313)
* Correction d’un problème dans les landing pages qui se produisait lors de la configuration des champs de case à cocher avec des abonnements. (CAMP-34369)
* Correction d’un problème qui se produisait lors de la configuration d’une liste et de l’ajout du champ &quot;icône&quot; à celle-ci. (CAMP-34585)
* Correction d’un problème qui empêchait l’utilisation des symboles &quot;|&quot; et &quot;%&quot; en tant que séparateurs de date ou d’heure dans les activités de workflow de chargement de fichier. (CAMP-34706)
* Correction d’un problème qui se produisait lors de l’utilisation des conditions de visibilité avec des cases à cocher dans les landing pages. (CAMP-34802)
* Correction d’un problème dans l’activité Enrichissement qui empêchait l’affichage des champs de l’onglet &quot;Données additionnelles&quot; si la dimension de filtrage était définie sur les logs de tracking et la dimension cible dans le profil.
* Correction d’un problème qui entraînait un message d’erreur lors de l’export d’une ressource « workflowTemplate ».
* Correction d’un problème qui empêchait, lors de la création d’un profil, d’enregistrer le champ « Code pays/zone géographique » s’il était sélectionné dans la boîte de dialogue.
* Correction de plusieurs problèmes qui se produisaient lors de l’utilisation du modèle d’import de courrier (updateQuarantinesDeliveryLogsDirectMail).
* Correction d’un problème lié à l’intégration d’Assets on Demand.
* Correction d’un problème qui se produisait lors de la réalisation d’un zoom avant dans la vue Planning. (CAMP-33628)
* Correction d’un problème qui empêchait l’envoi instantané des BAT pour les emails avec une date et une heure planifiées. (CAMP-33723)
* Correction d’un problème lié aux messages transactionnels qui générait des logs d’erreur lors de la déconnexion d’un utilisateur. (CAMP-31698)
* Correction d’une erreur qui se produisait dans des environnements spécifiques lors de la planification d’un email.
* Correction d’un problème qui entraînait l’échec du workflow Mise à jour de l’exécution des diffusions.
* Correction d’un problème de sécurité qui endommageait le contenu d’un email lorsque l’objet contenait plusieurs lignes.


## Version 19.2.7 - Juillet 2019 {#release-19-2-7---july-2019}

**Améliorations**

* Amélioration de la requête de suppression RGPD pour de meilleures performances.
* Correction d’un problème qui entraînait des blocages web après la mise à niveau 19.2. (CAMP-34862)
* Correction d’un problème qui empêchait les utilisateurs autres qu’administrateurs d’enregistrer ou de planifier des rapports. (CAMP-31133)
* Correction d’un problème lors de l’utilisation de du caractère &quot;|&quot; comme séparateur de date dans l’activité de workflow Chargement de fichier. (CAMP-34706)

## Version 19.2.4 - Juin 2019 {#release-19-2-4---june-2019}

**Concepteur d’email**

* Correction d’un problème qui empêchait les utilisateurs d’éditer des fragments si le code HTML contenait des balises &lt;style> vides. Il s’agit d’un correctif de suivi pour CAMP-33778 dans la version 19.2.3.

## Version 19.2.3 - Juin 2019 {#release-19-2-3---june-2019}

**Concepteur d’email**

Mise en place d’une série d’améliorations et de correctifs afin d’optimiser les fragments dans la version 19.2. Les nouveaux fragments fonctionneront de manière transparente. Les fragments conçus précédemment ont été grisés et devront être migrés vers le nouveau format. Pour cela, cliquez sur chaque fragment et validez sa migration vers le nouveau format. Nous vous recommandons de tester quelques fragments avant de migrer l’ensemble.

* Correction d’un problème qui empêchait les utilisateurs d’éditer un fragment après l’avoir déverrouillé. Ce problème avait une incidence sur les fragments existants lors de la mise à jour vers la version 19.2. (CAMP-33778)
* Correction d’un problème qui se produisait lors de l’utilisation du contenu dynamique. Des espaces supplémentaires étaient ajoutées dans le code HTML.

**Autres améliorations**

* Correction d’un problème qui empêchait la reprise de l’envoi des SMS suite à une déconnexion du connecteur SMS.
* Correction d’un problème qui fermait les connexions SMPP lorsque TLS était activé.
* Correction d’un problème qui fermait les connexions SMPP lorsque TLS était activé.
* L’option &quot;Launch_URL_Campaign&quot; a été ajoutée dans Campaign pour gérer les propriétés des applications mobiles créées avec le SDK Mobile Adobe Experience Platform.
* Correction d’une erreur qui entraînait la désélection de l’option d’environnement sandbox après le téléchargement du certificat d’une nouvelle propriété mobile et la sortie de la page de propriété de l’application mobile.
* Correction d’un problème qui empêchait l’utilisateur d’enrichir le contenu d’un message transactionnel avec des informations de la ressource Service. (CAMP-33707)
* Correction d’un problème lié aux landing pages de liste bloquée qui se produisait lors du désabonnement des profils d’un service.

## Version 19.2 - Mai 2019 {#release-19-2---may-2019}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Panneau de contrôle<br /> </td> 
   <td> <p>Pour accroître l’efficacité de votre travail en tant qu’utilisateur administrateur, vous pouvez facilement surveiller la capacité de vos instances et gérer leurs paramètres (à commencer par la gestion des serveurs SFTP).</p><p>Pour plus d’informations, consultez la <a href="https://docs.adobe.com/content/help/fr-FR/control-panel/using/control-panel-home.html">documentation détaillée</a> et la <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/subdomains-and-certificates/delegating-subdomains-using-cname.html?lang=fr">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notifications locales<br /> </td> 
   <td> <p>Les messages de notification locale permettent d’informer les utilisateurs lorsque de nouvelles données deviennent disponibles dans leurs applications mobiles, même sans accès à Internet ou sans l’application mobile s’exécutant au premier plan. Les notifications locales sont déclenchées par une application mobile à une heure donnée et en fonction d’un événement.</p><p>Pour plus d’informations, consultez la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentation détaillée</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux workflows : ajout d’une payload à l’activité de signal externe<br /> </td> 
   <td> <p>Démarrez un workflow avec une payload lorsque les conditions définies sont satisfaites à partir d’un autre workflow ou d’un appel d’API REST de façon à intégrer avec vos systèmes externes. Une nouvelle activité de <strong>test</strong> permet aussi d’exécuter des tests sur cette fonctionnalité.</p><p>Pour plus d’informations, consultez la <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux landing pages : Google reCAPTCHA<br /> </td> 
   <td> <p>Utilisez Google reCAPTCHA pour empêcher tout spam sur vos landing pages sans intervention de vos clients.</p><p>Pour plus d’informations, consultez la <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentation détaillée</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Améliorations de la sécurité**

* Correction d’un problème de sécurité potentiel de détournement de clic dans l’espace de travail de reporting.

**Améliorations du Concepteur d’email**

* Correction d’un problème qui se produisait lors de la duplication de fragments et de leur utilisation dans le Concepteur d’email. (CAMP-33193)
* Correction d’un problème qui créait des espaces inutiles lors de l’utilisation d’éléments incorporés dans l’interface du Concepteur d’email. (CAMP-32163)
* Correction d’un problème qui supprimait certains attributs de balise HTML supplémentaires ajoutés par l’utilisateur après avoir enregistré le contenu d’un email dans le Concepteur d’email. (CAMP-32162)
* Correction d’un problème qui affichait une balise Microsoft Office en mode HTML du Concepteur d’email, même après sa suppression. (CAMP-32141)
* Si vous avez créé un email à l’aide d’une version antérieure du Concepteur d’email, une fenêtre contextuelle s’ouvre maintenant lors de l’ouverture du contenu de cet email pour inviter l’utilisateur à effectuer une mise à jour vers la version la plus récente. (CAMP-31529)
* Correction d’un problème qui déformait les images d’un email créé avec le Concepteur d’email lorsqu’il était diffusé à certains clients de messagerie. (CAMP-31407)
* Correction d’un problème qui empêchait l’affichage correct de certains éléments (listes ou boutons, par exemple) en mode texte brut lorsqu’ils avaient été créés en mode HTML. (CAMP-32582, CAMP-32542)
* Correction d’un problème qui empêchait l’affichage de plus de 50 entités organisationnelles dans un modèle de contenu ou des propriétés de fragment. (CAMP-32932)
* Correction d’un problème lié à la couleur d’arrière-plan de la fenêtre d’affichage lors de la réception dans Outlook d’un email créé avec le Concepteur d’email. (CAMP-31402)
* Correction d’un problème qui empêchait les contenus d’email créés avec le Concepteur d’email d’être réactifs lorsqu’ils étaient ouverts dans Outlook. (CAMP-31400)
* Correction d’un problème qui empêchait le contenu dynamique de fonctionner correctement lorsqu’il était utilisé dans l’objet d’un email. (CAMP-32837)
* Correction d’un problème lié aux objets des emails qui n’étaient pas correctement placés dans une séquence d’échappement.
* Correction d’un problème qui empêchait le chargement de fragments dans la palette de gauche du Concepteur d’email.
* Correction d’un problème qui empêchait l’affichage des fragments créés lors de l’édition du contenu d’email dans la palette de gauche du Concepteur d’email au moment de l’actualisation de la liste des fragments.
* Correction de plusieurs problèmes qui se produisaient lors de l’utilisation de contenu dynamique dans un email.
* Correction d’un problème lié au sélecteur de couleurs qui se produisait lors de la définition d’une couleur à l’aide de valeurs RVB.
* Correction d’un problème qui empêchait la page miroir d’être réactive lors de la réception de l’email sur un mobile.

**Améliorations apportées aux messages transactionnels**

Pour optimiser le fonctionnement et les performances, plusieurs améliorations ont été ajoutées au canal Messages transactionnels.

* La durée des messages transactionnels a été prolongée afin que tous les messages soient envoyés avant leur expiration, en particulier lors de reprises.
* Les performances des messages transactionnels ont été améliorées en répartissant la charge sur différents threads d’envoi.
* Le processus des messages transactionnels a été optimisé pour pouvoir lancer en parallèle plusieurs analyses d’un même message.
* Correction d’un problème qui pouvait entraîner une incohérence du débit et de la latence pour les notifications push transactionnelles.
* Correction d’un problème qui affichait une audience cible incorrecte pour les diffusions d’exécution de messages transactionnels.
* Correction d’un problème qui se produisait lors de l’import d’un package avec une configuration d’événement et le message transactionnel associé. Consultez à ce sujet la [documentation détaillée](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Correction d’un problème qui supprimait les données de collecte des profils de test créés pour un message transactionnel contenant des listes de produits.

**Autres changements**

* Une nouvelle option a été ajoutée au compte externe SMS. Elle permet de limiter le nombre maximal de processus MTA envoyant des SMS afin de mieux contrôler le nombre de connexions parallèles. Pour plus d’informations, consultez la technote [Protocole et paramètres du connecteur SMS](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html).
* Lors de la publication d’une ressource avec une extension d’API, si l’API a déjà été publiée, elle est automatiquement mise à jour à chaque nouvelle publication. Auparavant, cette action était manuelle et le fait de ne pas mettre à jour l’API pouvait endommager la ressource profil ou les ressources de services de celle-ci. Consultez à ce sujet la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimension de code postal a été supprimée des rapports dynamiques. Il est recommandé d’utiliser plutôt les dimensions de ville, pays et état.
* Le trigger d’événement de cycle de vie &quot;Premier lancement&quot; pour les messages In-App a été supprimé.
* Lors de l’export d’un package avec des groupes de sécurité, celui-ci contient désormais les rôles attribués à chaque groupe. (CAMP-32960)
* Dans l’activité Chargement de fichier, une nouvelle option permet de vérifier que les colonnes du fichier téléchargé correspondent à la définition de colonne. Pour plus d’informations, consultez la [documentation détaillée](../../automating/using/load-file.md). (CAMP-32229)
* Les workflows peuvent maintenant être démarrés avec une payload, ce qui permet d’utiliser et de partager des paramètres externes entre les activités au sein d’un workflow. Pour plus d’informations, consultez la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 et CAMP-29413)
* Les API de Campaign Standard permettent maintenant de mettre à jour les entités géographiques et organisationnelles des profils à l’aide d’une payload. Pour plus d’informations, consultez la [documentation détaillée](../../api/using/get-started-apis.md).
* Les messages d’erreur qui s’affichent lorsqu’un objet de la base de données n’est pas accessible ont été clarifiés.
* Dans l’activité Extraction de fichier, les capacités Javascript ont été mises à jour lors de la définition du nom d’un fichier à exporter. Seule la fonction formatDate est maintenant disponible pour une utilisation dans le champ Sortie. Pour plus d’informations, consultez la [documentation détaillée](../../automating/using/extract-file.md).
* La génération automatique d’ID de séquence a été améliorée pour les ressources personnalisées. Les clés primaires pour les nouvelles ressources personnalisées sont maintenant 64 bits par défaut.
* Le mode de test de publication de ressource personnalisée a été amélioré. Un message d’avertissement s’affiche maintenant si la dernière publication de ressource personnalisée est en échec et n’est pas corrigée. Après un échec de publication de ressource personnalisée, vous pouvez revenir à la dernière version opérationnelle. Pour plus d’informations, consultez la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Une nouvelle option a été ajoutée à l’activité Transfert de fichier. Elle permet de trier les fichiers lorsque vous utilisez l’action de téléchargement de fichier, en mode SFTP. Pour plus d’informations, consultez la [documentation détaillée](../../automating/using/transfer-file.md). (CAMP-33109)

**Correctifs**

* Correction d’un problème qui entraînait une fuite de mémoire sur le MTA lorsque les paramètres SMS étaient rechargés.
* Correction d’un problème qui empêchait la publication des mises à jour de la base de données en mode de réparation.
* Correction d’un problème qui entraînait des divergences entre les rapports Adobe Analytics et les rapports dynamiques Adobe Campaign. (CAMP-25393)
* Correction d’une erreur qui entraînait l’échec du workflow de partage de rapport.
* Correction d’une erreur qui empêchait les utilisateurs d’envoyer des messages In-App avec uniquement l’URL de média.
* Correction d’un problème qui affichait une application mobile, même si son certificat n’était pas téléchargé sur l’instance.
* Correction d’une erreur qui empêchait les champs de personnalisation de fonctionner lors de l’utilisation du modèle **Cibler tous les utilisateurs d’une application mobile**.
* De nouvelles instances de Campaign Standard ont été configurées. (CAMP-32635 et CAMP-32344)
* Correction d’une erreur qui empêchait la personnalisation de la formule de date dans un workflow. (CAMP-30336)
* Correction d’un problème lors de la définition d’une formule de date personnalisée qui pouvait empêcher les champs &quot;Données additionnelles&quot; et &quot;Code segment&quot; d’être disponibles dans la liste déroulante. (CAMP-32383)
* Correction d’un problème qui pouvait empêcher les activités &quot;Transfert de fichier&quot; et &quot;Extraction de fichier&quot; de rechercher les rejets de fichiers s’ils étaient cryptés. (CAMP-32377)
* Correction d’un problème dans les API qui pouvait empêcher le filtre lineCount d’afficher le nombre total exact. (CAMP-31424)
* Correction d’un problème dans les landing pages qui empêchait les champs d’entrée d’afficher la valeur mise à jour une fois celle-ci modifiée. (CAMP-31401)
* Correction d’un problème qui entraînait l’activation inattendue d’une activité de signal.
* Correction d’un problème qui empêchait l’affichage de l’aperçu d’un email lorsque l’audience était vide.
* Correction d’un problème dans l’activité &quot;Extraction de fichier&quot; qui entraînait la génération d’un fichier alors que l’option &quot;Ne pas générer de fichier si la transition entrante est vide&quot; était activée.
* Correction d’un problème qui entraînait la désactivation du workflow de délivrabilité s’il ne se terminait pas correctement.
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer ou de planifier des rapports. (CAMP-31133)

## Version 19.1.3 - Mars 2019              {#release-19-1-3---march-2019}

**Améliorations du Concepteur d’email**

* Correction d’un problème qui empêchait la modification d’un modèle après son enregistrement.
* Résolution de divers problèmes qui pouvaient se produire dans les emails lors de l’utilisation d’un modèle créé auparavant.
* Correction d’un problème qui empêchait le masquage des composants dans les modèles importés.

**Autres améliorations**

* Correction d’une erreur qui se produisait lors de l’affichage des règles de typologie. (CAMP-32059 et CAMP-31849)
* Correction d’un problème qui empêchait l’édition des règles de typologie. (CAMP-31750)
* Correction d’un problème lié au processus inMail qui pouvait s’arrêter de manière inattendue. (CAMP-31238)

## Version 19.1 - Février 2019 {#release-19-1---february-2019}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Améliorations du reporting du canal push<br /> </td> 
   <td> <p>Plusieurs améliorations ont été apportées au reporting du canal push afin de mesurer l’engagement des utilisateurs de manière plus intuitive. Avec cette version, la liste des mesures du canal push compte désormais trois mesures différentes : Impressions, Clics, Ouvertures (ouverture de l’application). Celles-ci vous permettent de mesurer et d’analyser plus efficacement l’interaction des utilisateurs avec les notifications push. Nous normalisons également la définition et la mise en œuvre de ces mesures. Le rapport intégré relatif aux notifications push a également été amélioré. Il comporte désormais des visualisations et des mesures couramment utilisées.</p><p> Pour plus d’informations, consultez la <a href="../../reporting/using/push-notification-report.md">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Launch pour les applications mobiles<br /> </td> 
   <td> <p>Cette version contient l’intégration d’Adobe Campaign avec les versions de disponibilité générale des extensions Android et iOS pour Adobe Campaign Standard dans les SDK Adobe Experience Platform Launch et Mobile. Ces extensions prennent en charge la messagerie push, la messagerie In-App et les mises à jour des profils des applications mobiles.</p><p> Pour plus d’informations, consultez la <a href="https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Messagerie In-App mobile<br /> </td> 
   <td> <p>Cette version contient la version de disponibilité générale du canal In-App dans Campaign. D’un point de vue fonctionnel, les ajouts les plus importants à la version bêta sont les rapports dynamiques pour le canal In-App et l’établissement d’une liaison sécurisée entre le SDK Mobile et MCIAS (service de messagerie In-App Experience Cloud qui fournit les règles In-App au SDK). L’établissement d’une liaison sécurisée garantit que les données PII de vos utilisateurs ne tombent pas entre des mains malveillantes. Il permet également de préserver la confidentialité de l’utilisateur sur un appareil partagé en effaçant le cache des messages chaque fois que l’utilisateur se déconnecte.</p><p>Pour plus d’informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a> et le <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">tutoriel In-App</a> dédié.</p> </td> 
  </tr> 
  <tr> 
   <td> Améliorations des workflows<br /> </td> 
   <td> <p>Les capacités de workflow suivantes ont été ajoutées :</p> 
    <ul> 
     <li> Vous pouvez maintenant copier-coller des activités au sein d’un workflow ou d’un autre à partir d’une même instance de Campaign. Ainsi, vous pouvez facilement dupliquer un workflow entier ou des activités spécifiques, tout en conservant les paramètres initialement définis. Pour plus d’informations, consultez la <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentation détaillée</a>. (CAMP-20014) </li> 
     <li> Lors de l’utilisation de l’activité <strong>Chargement de fichier</strong>, vous pouvez maintenant ajouter un horodatage au nom du fichier contenant les enregistrements rejetés. Pour plus d’informations, consultez la <a href="../../automating/using/load-file.md#configuration">documentation détaillée</a>. </li> 
     <li> Les activités <strong>Requête</strong> et <strong>Segmentation</strong> permettent désormais d’activer une transition sortante si les activités ne récupèrent aucune donnée. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations de la sécurité**

* Le code HTML de landing page généré a été mis à jour afin d’empêcher toute indexation par les moteurs de recherche.

**Améliorations du Concepteur d’email**

* Un ensemble de quatre modèles d’email réactif conçus par des artistes Behance est maintenant disponible.

   Pour plus d’informations, consultez la [documentation détaillée](../../designing/using/using-reusable-content.md#content-templates).

* Notre nouvelle expérience d’intégration vous permet de commencer à créer plus rapidement des emails et facilite l’accès à la documentation et aux tutoriels.

   Pour plus d’informations, consultez la [documentation détaillée](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Vous avez maintenant la possibilité de configurer le nombre et la largeur des colonnes en fonction de vos besoins.

   Pour plus d’informations, consultez la [documentation détaillée](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Lors de l’édition dans la vue mobile, vous pouvez masquer certains composants uniquement dans l’affichage mobile pour utiliser efficacement l’espace.

   Pour plus d’informations, consultez la [documentation détaillée](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Vous pouvez maintenant ajouter des canaux sociaux personnalisés à votre modèle d’email en plus de ceux déjà disponibles.
* Correction d’un problème qui empêchait de faire défiler le menu de structure lorsque plus de 18 structures étaient utilisées. (CAMP-31173)
* Correction d’un problème qui affichait le pré-en-tête en haut du contenu lors du transfert d’un email contenant un pré-en-tête envoyé avec Adobe Campaign. (CAMP-30736)
* Correction d’un problème qui empêchait la mise à jour de la ligne d’objet lorsque l’utilisateur cliquait sur l’option **Actualiser le contenu AEM** après avoir modifié l’objet dans Adobe Experience Manager. (CAMP-29984)
* Correction de plusieurs problèmes qui empêchaient l’utilisation d’images dynamiques d’Adobe Target.
* Correction d’un problème qui empêchait la mise à jour de l’aperçu lors de la récupération du contenu au moment de la préparation si le contenu avait déjà été importé à partir d’une URL.
* L’icône YouTube a été ajoutée au composant de contenu **Social**.
* La vue **Liste** a été ajoutée pour les composants de contenu et les fragments affichés dans la palette du Concepteur d’email.

**Autres améliorations**

* Adobe Campaign est désormais entièrement compatible FCM pour les applications SDK V4 et SDK AEP.
* Adobe Campaign prend en charge les notifications push sous Wear OS (Android) et watchOS (Apple).
* Les messages d’avertissement et d’erreur pouvant s’afficher lors de la navigation dans l’interface ont été clarifiés et simplifiés.
* Vous pouvez maintenant ajouter à la liste des profils des colonnes relatives à l’opt-in et l’opt-out (champs &quot;Ne plus contacter…&quot;).
* La liste déroulante Fuseau horaire de l’écran de création de profil a été déplacée de la section Adresse vers la section supérieure de l’interface.
* Vous pouvez maintenant ajouter des séparateurs lors de la configuration d’écrans de ressources personnalisés, ce qui vous permet d’organiser vos champs en catégories.

   Pour plus d’informations, consultez la [documentation détaillée](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Autres changements**

* A compter du printemps 2019 et de la version Campaign Standard 19.2, Adobe Campaign et Adobe Experience Cloud arrêteront la prise en charge de Microsoft Internet Explorer 11. Passez à Microsoft Edge ou tout autre navigateur pris en charge. Consultez la page [Fonctionnalités supprimées et obsolètes](../../rn/using/deprecated-features.md).
* Le champ **Code pays** de la ressource Profil a été renommé en **Code pays/zone géographique**.

**Correctifs**

* Correction d’un problème qui empêchait l’envoi du message lors de l’ajout d’un profil de test à un message transactionnel d’email. (CAMP-29854)
* Correction d’un problème qui ralentissait l’envoi des messages à partir d’autres canaux si l’envoi était faible pour un canal lorsque l’envoi des messages à partir de tous les canaux était déclenché simultanément.
* Correction d’un problème en raison duquel le MTA commençait à envoyer des SMS lorsque la connexion au compte externe n’était pas encore établie.
* Correction d’un problème lié à la fréquence d’exécution et à l’heure de début de l’activité Planificateur. (CAMP-30745)
* Correction d’un problème lié à la génération PKEY qui se produisait lors de l’utilisation de ressources de profil étendues. (CAMP-30285)
* Correction d’un problème qui se produisait avec les règles de fatigue basées sur un jour calendaire. (CAMP-30136)
* Correction d’un problème qui se produisait lors de la tentative d’accès à des ressources personnalisées dont les noms se terminaient par &quot;Base&quot;. (CAMP-30109)
* Correction d’un problème qui empêchait l’utilisation d’un appel PATCH pour abonner un profil à un service. (CAMP-29728)
* Correction d’un problème qui endommageait un workflow lors de l’import d’un fichier XML par le biais de l’activité Chargement de fichier. (CAMP-29208 et CAMP-28205)
* Correction d’un problème qui empêchait la génération de liens de cardinalité inversée lors de la liaison de ressources personnalisées. (CAMP-30476)
* Correction d’un problème qui empêchait l’extension des logs de diffusion lors de l’utilisation du code de segment uniquement.
* Correction d’un problème qui entraînait la duplication de lignes lors de l’utilisation de l’activité Transfert de fichier dans les workflows.
* Correction d’un problème qui empêchait l’envoi des rapports planifiés à l’heure choisie.
* Correction d’un problème qui entraînait une différence entre les KPI &quot;A envoyer&quot; et &quot;Envoyés&quot; pour une diffusion In-App dans un workflow.
* Correction d’un problème qui empêchait le fonctionnement du tracking pour un message In-App créé avec du code HTML personnalisé.
* Correction d’un problème qui empêchait l’enregistrement du contenu d’une diffusion In-App lorsqu’il était utilisé dans un workflow.
* Correction d’un problème qui empêchait l’affichage des applications mobiles pour les administrateurs.
* Correction d’un problème qui entraînait l’échec du workflow technique Mise à jour pour la délivrabilité. (CAMP-26387)
* Correction d’un problème qui entraînait une différence entre les profils ciblés lors de la création d’une diffusion In-App et ceux affichés dans le tableau de bord de la diffusion. (CAMP-28722)
* Correction d’un problème lié à l’intégration de Campaign avec Assets Core Service qui empêchait la sélection d’une ressource partagée dans un email.

## Version 19.0 - Janvier 2019 {#release-19-0---january-2019}

**Nouveautés**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Disponibilité générale du Concepteur d’email<br /> </td> 
   <td> <p>Le nouveau Concepteur d’email intuitif (anciennement Creative Designer) est passé à la phase de disponibilité générale. Il prend maintenant en charge toutes les fonctionnalités de l’ancien éditeur de contenu, notamment :</p> 
    <ul> 
     <li> Utilisation des <a href="../../integrating/using/adding-target-dynamic-content.md">images dynamiques d’Adobe Target</a> </li> 
     <li> Possibilité de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">récupérer automatiquement du contenu depuis une URL au moment de la préparation</a> </li> 
     <li> <a href="../../designing/using/using-reusable-content.md#content-templates">Modèles de contenu d’usine</a> entièrement compatibles </li> 
    </ul> 
    <p>Pour plus d’informations, consultez la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/designing-content/email-designer/email-designer-overview.html">vidéo de procédure</a>. Les améliorations et les correctifs sont répertoriés ci-dessous.</p><p>Par conséquent, l’ancien éditeur de contenu d’email est maintenant obsolète. Pour plus d’informations, consultez cette <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listes des produits dans les emails transactionnels<br /> </td> 
   <td> <p>Vous pouvez maintenant référencer une ou plusieurs collections de produits dans un email transactionnel. Vous pouvez par exemple envoyer automatiquement un email d’abandon de panier répertoriant tous les produits qui étaient dans le panier de l’utilisateur avec une image, le prix et un lien vers chaque produit.</p><p>Pour plus d’informations, consultez la <a href="../../designing/using/using-product-listings.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html">vidéo de procédure</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vue mobile dans le Concepteur d’email<br /> </td> 
   <td> <p>Vous pouvez maintenant basculer vers une vue mobile dédiée lors de l’édition du contenu d’un email. Vous pouvez ainsi affiner le responsive design d’un email en éditant séparément toutes les options de style pour l’affichage mobile, (adapter les marges, réduire la taille des polices, changer de couleur fond, etc.).</p><p> Pour plus d’informations, consultez la <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Améliorations de la Messagerie In-App (version bêta)<br /> </td> 
   <td> <p>La fonctionnalité Messagerie In-App (version bêta) a été améliorée avec l’ajout des capacités suivantes :</p> 
    <ul> 
     <li> Compatibilité du canal In-App (version bêta) avec le RGPD </li> 
     <li> Intégration avec les API Analytics pour peupler les listes déroulantes des Triggers </li> 
     <li> Aspect intuitif et description des modèles de diffusion </li> 
     <li> Améliorations apportées à l’interface de création du point de vue de la convivialité </li> 
    </ul> <p>Pour plus d’informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Une nouvelle option de l’activité de chargement de données permet désormais d’appliquer une étape de post-traitement au fichier contenant les enregistrements rejetés (ex. compression au format zip) – (CAMP-24521)
* Une nouvelle option de l’activité Mise à jour de données vous permet maintenant de configurer la taille maximale des mises à jour pour les données à télécharger. (CAMP-28400)
* Amélioration de la sélection de l’état des adresses des profils Lors de la sélection d’un pays, la liste déroulante &quot;Etat&quot; est maintenant automatiquement mise à jour avec les valeurs d’état correspondantes. (CAMP-28874)
* Une nouvelle option de l’activité Extraction de fichier empêche désormais la génération d’un fichier si la transition entrante est vide. Ainsi, des fichiers vides ne sont pas créés et téléchargés sur les serveurs SFTP.
* Le rapport Synthèse des diffusions a été amélioré.
* La liste des pays disponibles lors de la définition de l’adresse d’un profil a été enrichie. (CAMP-26707)
* Un message d’erreur s’affiche maintenant lorsque vous essayez d’importer un workflow intégré.

**Concepteur d’email**

* Correction d’un problème qui entraînait l’activation de la fonctionnalité d’entité géographique sur un modèle d’email ou un fragment de contenu créé dans le Concepteur d’email, même si cette fonctionnalité était désactivée dans Adobe Campaign, ce qui rendait le modèle ou le fragment indisponible lors d’une nouvelle tentative d’accès. (CAMP-28174)
* Correction d’un problème qui empêchait l’enregistrement des conditions de contenu dynamique lors de l’édition de contenu dans le Concepteur d’email. (CAMP-27905)
* Correction d’un problème qui entraînait la suppression de la version HTML du contenu de l’email après avoir édité la version en texte brut d’un message et interrompu la synchronisation HTML dans le Concepteur d’email. (CAMP-28507)
* Correction d’un problème qui empêchait l’ouverture de l’interface du Concepteur d’email lors de l’utilisation d’Internet Explorer 11. (CAMP-28273)
* Correction d’un problème qui déformait le rendu des paramètres de style Microsoft Outlook appliqués aux boutons avec le Concepteur d’email.
* Correction d’un problème lié au Concepteur d’email qui rendait éditable l’URL d’un fragment de contenu utilisé dans un email, ce qui n’était pas prévu, le fragment étant verrouillé par défaut.
* Correction d’un problème qui empêchait l’affichage du composant diviseur du Concepteur d’email dans Microsoft Office.
* Correction d’un problème qui entraînait le gel des pages de certains navigateurs Internet lors de l’affichage d’un contenu synchronisé à partir d’AEM à l’aide de l’ancien éditeur de contenu d’email. (CAMP-29068)
* Correction d’une erreur qui se produisait lors d’un clic sur une image dans un email lorsque l’ancien éditeur de contenu d’email était utilisé. (CAMP-30424)
* Correction d’un problème qui empêchait l’affichage des fragments nouvellement créés lors de l’édition d’un email dans le Concepteur d’email. (CAMP-29928)
* Correction d’un problème qui empêchait l’affichage correct du texte des boutons dans les emails créés avec le Concepteur d’email et reçus à l’aide du client webmail Outlook.
* Il est maintenant possible de créer des messages transactionnels de profil à l’aide du Concepteur d’email. (CAMP-28900)
* Correction d’une erreur dans le Concepteur d’email qui rendait le contenu éditable lors de la récupération automatique du contenu d’une URL au moment de la préparation, alors qu’il devait être verrouillé.

**Correctifs**

* Correction d’un problème qui entraînait l’affichage de logs de diffusion incorrects dans les rapports dynamiques. (CAMP-23446)
* Correction d’un problème qui avait un impact sur les chiffres du rapport de synthèse des bounces (CAMP-28703).
* Correction d’un problème lié à l’intégration de Campaign avec Assets Core Service qui empêchait l’affichage des ressources lors de la sélection de l’option **[!UICONTROL Image partagée depuis Adobe Experience Cloud]** dans un email (CAMP-28732).
* Correction d’un problème qui empêchait l’envoi de SMS contenant le caractère ’œ’ bien que la translittération soit autorisée dans le compte externe SMPP. (CAMP-29041)
* Correction d’un problème qui entraînait l’affichage d’enregistrements en double lors de l’utilisation d’une activité Segmentation dans des workflows. (CAMP-28743)
* Correction d’un problème qui empêchait la suppression de l’une des correspondances de valeurs sur une colonne dans une activité de workflow. (CAMP-28708)
* Correction d’un problème lié à l’activité Transfert de fichiers lors de l’utilisation de caractères génériques avec l’option &quot;Test d’existence de fichier&quot;. (CAMP-28977)
* Correction d’un problème lié à l’activité Transfert de fichiers qui se produisait lors de la mise à jour des paramètres des comptes externes. (CAMP-28894)
* Correction d’un problème lié aux filtres personnalisés dans le requêteur lors de l’utilisation de la condition &quot;Email n’est pas vide&quot;. (CAMP-28741)
* Correction d’un problème qui se produisait lors de l’export de tables de ressources personnalisées contenant plus de 100 000 enregistrements. (CAMP-28150)
* Correction d’un problème qui empêchait la suppression des messages transactionnels liés à des Triggers. (CAMP-28385)
* Suppression des mots de passe qui étaient affichés de manière non sécurisée dans certains logs SMS.
* Correction d’un problème en raison duquel les connexions au simulateur SMPP échouaient en raison d’un mot de passe vide envoyé par Adobe Campaign.
* Correction d’un problème qui empêchait l’envoi de campagnes lorsque les connexions SMS étaient instables.
* Correction d’un problème qui entraînait l’affichage de diffusions supprimées dans les rapports dynamiques.
* Correction d’un problème qui empêchait la récupération des données additionnelles des tables des exclus, des logs de diffusion et du tracking lors de l’utilisation d’une activité Enrichissement dans un workflow.
* Correction d’un problème lié aux demandes de suppression RGPD qui se produisait lors de l’utilisation d’un type de lien &quot;Lien de collection de cardinalité N&quot; et de l’option &quot;La suppression de l’enregistrement cible entraîne la suppression des enregistrements référencés par le lien&quot;.
* Correction d’un problème lié au partage des rapports.
* Correction d’un problème qui entraînait des problèmes de débit lors de l’envoi d’une notification push.
* Correction d’un problème lié à des champs absents dans les fichiers de sortie du courrier.
* Correction d’un problème qui permettait aux utilisateurs de modifier les workflows intégrés.
* Correction d’un problème lors de la création d’une campagne à partir d’un modèle de campagne comprenant un workflow avec une activité d’extraction configurée. (CAMP-29198)
* Correction d’un problème lié à l’activité d’extraction de fichiers qui empêchait d’utiliser la même expression pour plusieurs éléments. (CAMP-29182)
* Dans l’éditeur de requête, correction d’un problème lié à la condition de jointure entre le broadlog et le log de tracking pour rtEvent. (CAMP-28780)
* Correction d’un problème qui empêchait l’enregistrement des modifications apportées à l’option de page d’entrée &quot;Action spécifique&quot;. (CAMP-29422)
* Correction d’un problème qui empêchait d’exporter la payload d’un événement dans un workflow. (CAMP-29029)
* Correction d’un problème qui empêchait l’exclusion des numéros de SMS sur la liste bloquée dans un message SMS. (CAMP-28898)
* Correction d’un problème qui empêchait les fournisseurs SMPP d’être avertis en cas d’erreur lors du traitement des messages entrants. (CAMP-29804)
* Correction d’un problème qui autorisait la suppression de comptes externes avec les diffusions associées. (CAMP-29738)
* Le débit d’envoi a été amélioré et stabilisé pour les messages SMS.
* Correction d’un problème qui empêchait l’utilisation du caractère &quot;~&quot; dans un message SMS. (CAMP-29172)
* Correction d’un problème de diffusions avec l’option d’optimisation de l’heure d’envoi. (CAMP-29231)

