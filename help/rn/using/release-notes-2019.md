---
title: Notes de mise à jour    2019
description: Cette page répertorie toutes les versions 2019 d'Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: ht
source-git-commit: 85dc2b3ba9a781483f88238fbf5a9208a0c18c37
workflow-type: ht
source-wordcount: '7633'
ht-degree: 100%

---


# Notes de mise à jour 2019{#release-notes-2019}

[Calendrier des versions](https://helpx.adobe.com/fr/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour les plus récentes](../../rn/using/release-notes.md) | [Fonctionnalités obsolètes](https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html)

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
   <td> <p>La CCPA est la nouvelle loi sur la protection des renseignements personnels de l'Etat de Californie qui harmonise et modernise les exigences en matière de protection des données qui entreront en vigueur le 1er janvier 2020. Cette loi s'applique aux clients Adobe Campaign qui détiennent des données pour des personnes concernées résidant en Californie.</p>
   <p>Outre les fonctionnalités de confidentialité déjà disponibles dans Adobe Campaign (notamment la gestion du consentement, les paramètres de rétention des données et les rôles utilisateur), nous profitons de l'occasion pour inclure des fonctionnalités supplémentaires afin de faciliter votre préparation à la CCPA :</p>
   <ul>
    <li>Droit d'accès et droit de suppression : nous tirons parti des capacités qui ont été ajoutées pour le RGPD. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#righttoaccess">En savoir plus</a> </li>
    <li><p>Lors de la création d’une demande d'accès à des informations personnelles, le type de réglementation (RGPD ou CCPA) a été ajouté à Privacy Core Service. Cette méthode est celle que vous devez utiliser pour toutes les demandes d'accès et de suppression. L'utilisation de l'API et de l'interface de Campaign pour les demandes d'accès et de suppression est obsolète.  Consultez l'article <a href="https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html">Fonctionnalités obsolètes et supprimées</a>.</p></li>
    <li>Un champ <strong>Opt-out CCPA</strong> a été ajouté à la ressource Profils pour permettre aux utilisateurs d'Adobe Campaign de déterminer si un client s'est opposé à la vente de ses informations personnelles. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#ccpa">En savoir plus</a>.</li>
  </ul>
    <p>Reportez-vous à la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">vidéo pratique</a>.</p>
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
    <p>L'intégration entre Adobe Campaign Standard et Microsoft Dynamics 365 est maintenant disponible. Vous pourrez transférer vos enregistrements de contacts et d'entités personnalisées de Dynamics 365 vers Campaign et récupérer les données d'événement d'email à partir de Campaign dans Dynamics 365 pour un meilleur alignement du marketing sur les ventes.</p>
    <p>Reportez-vous à la <a href="../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md">documentation détaillée</a> pour configurer cette intégration et voir la <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/integrating-with-adobe-cloud/campaign-and-microsoft-dynamics-365/working-with-campaign-standard-and-microsoft-dynamics-365.html">vidéo pratique</a>.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Le pop-up de consentement pour la création de rapports dynamiques a été mis à jour afin d&#39;inclure l&#39;intégration de Microsoft Dynamics 365 à Adobe Campaign Standard. En acceptant les termes, les données de profil seront incluses lors de l&#39;utilisation de l&#39;intégration Adobe Campaign Standard/Microsoft Dynamics 365 et de la création de rapports dynamiques. [En savoir plus](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Correction d&#39;un problème qui affichait des dates de contact incorrectes lors de la réception d&#39;alertes de diffusion.
* Lorsqu&#39;un événement de message transactionnel est envoyé avec un paramètre de contexte inconnu, Campaign renvoie maintenant un message d&#39;erreur &quot;400&quot; au lieu de &quot;500&quot;. (CAMP-28632)
* Un nouveau segment **Exclure le BAT** a été ajouté dans les rapports dynamiques. Ce segment est désormais sélectionné par défaut pour filtrer les rapports. [En savoir plus](../../reporting/using/list-of-components-.md#segments)
* L&#39;option **Expiration du message** a été ajoutée à la notification push. Elle vous permet de spécifier une date d&#39;expiration à laquelle le message ne sera plus envoyé par Apple (APNS) ou Android (FCM). [En savoir plus](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Des améliorations ont été apportées à l&#39;activité **Chargement de fichier** : les logs des workflows ont été rendus plus clairs et plus détaillés sur l&#39;erreur qui se produit lorsqu&#39;un fichier ne se charge pas. La transition sortante générée lors de l&#39;activation de l&#39;option **Conserver les rejets dans un fichier** a été renommée **Rejets**. [En savoir plus](../../automating/using/load-file.md)
* Des logs associés multilingues ont été ajoutés aux logs d&#39;envoi afin de mieux comprendre les échecs d&#39;envoi en raison de langues manquantes dans les fichiers CSV téléchargés.

**Améliorations de la sécurité**

* Correction d&#39;un problème lors de la suppression des informations d&#39;un profil en quarantaine par le biais d&#39;une demande d&#39;accès à des informations personnelles. Celui-ci entraînait la suppression de toutes les données, à l&#39;exception de l&#39;adresse email dans la liste de quarantaine.
* La sécurité de la protection contre les injections dans les en-têtes d&#39;email a été améliorée.
* La sécurité a été renforcée pour la protection contre les attaques SSRF où les expressions xtk peuvent être utilisées (HTML d&#39;email, contenu texte et objet, SMS et contenu de notification push).

**Améliorations du Concepteur d&#39;email**

* Correction d&#39;un problème qui empêchait le suivi des liens de désabonnement, d&#39;abonnement et de landing page lorsqu&#39;ils étaient insérés dans un email. (CAMP-37809)
* Correction d&#39;un problème susceptible d&#39;entraîner des erreurs lors de la création d&#39;un email et de la sélection d&#39;un modèle. (CAMP-38000)
* Lors de l’édition d&#39;un lien à l’aide du Concepteur d’email, vous pouvez désormais utiliser l’option **Souligner le lien**. En outre, la propriété **Cible** a été ajoutée avec la valeur par défaut définie sur **Aucune**. [En savoir plus](../../designing/using/styles.md#about-styling-links)
* Correction d&#39;un problème de couleur sur les liens au sein des composants de texte dans le corps d&#39;un email. (CAMP-37330)
* Correction d&#39;un problème qui empêchait la suppression des liens associés lors de la suppression d&#39;une image. (CAMP-37234)
* Correction d&#39;un problème qui empêchait l&#39;enregistrement des modifications des paramètres **Ordre de priorité** du contenu dynamique dans une condition. (CAMP-36883)
* Correction d&#39;un problème lors de la recherche de landing pages. La recherche a été étendue des 50 premiers enregistrements créés à toute la base de données. (CAMP-36839)
* Correction d&#39;un problème lors de l&#39;enregistrement des modifications de l&#39;expéditeur de l&#39;email dans le champ **De : Nom**. (CAMP-36606)
* L&#39;avertissement de compatibilité des composants du carrousel a été modifié pour prendre en compte les clients d&#39;email pris en charge.
* Correction d&#39;un problème d&#39;affichage sur mobile. L&#39;attribut height est maintenant toujours défini sur &quot;height: auto&quot; lors de l&#39;ajout ou du téléchargement d&#39;une nouvelle image dans un email. (CAMP-35497)
* Correction d&#39;un problème en raison duquel les balises style et meta étaient conservées dans le code HTML lors de la suppression d&#39;un fragment d&#39;un composant de structure. (CAMP-35390)
* Correction d&#39;un problème lié aux fragments lors de la mise à jour d&#39;un contenu réutilisable. (CAMP-35186)
* Correction d&#39;un problème lors de l&#39;affichage du contenu conditionnel pour mobiles uniquement dans les emails. (CAMP-35155)
* Correction d&#39;un problème qui affichait de manière aléatoire des espaces insécables de largeur nulle. (CAMP-35116)
* Correction d&#39;un problème lié à la position des boutons dans la boîte de dialogue **Enregistrer en tant que fragment**.
* Correction d&#39;un problème d&#39;aperçu lors de l&#39;ajout d&#39;une balise HTML dans un titre d&#39;image et un texte alternatif.
* Correction d&#39;un problème lors de l&#39;édition, dans le Concepteur d&#39;email, des liens créés dans des emails à partir de l&#39;ancien éditeur.
* Correction d&#39;un problème en raison duquel les balises de style étaient dupliquées dans le contenu.
* Correction d&#39;un problème lié au format de date lors de l&#39;insertion d&#39;un champ de personnalisation dans un email.
* Correction d&#39;un problème d&#39;enregistrement lors du passage du mode HTML au texte brut.
* Correction d&#39;un problème en cas de clic sur l&#39;option de verrouillage et de déverrouillage. Celui-ci ajoutait des valeurs de marge dans le panneau des propriétés de style intégré.
* Correction d&#39;un problème lié à la taille de l&#39;aperçu mobile pour un meilleur rendu.
* Correction d&#39;un problème lié à la taille des boutons dans les modèles et les fragments.
* Correction d&#39;un problème lié à la taille des images lorsqu&#39;elles étaient insérées dans un composant de bouton.

**Autres changements**

* La période par défaut pour laquelle les données sont affichées sur les pages des KPI de diffusion et sur la page de création de rapports dynamiques a été alignée afin d&#39;éviter toute incohérence dans les résultats des rapports. (CAMP-35148)
* Un message d&#39;erreur a été ajouté dans les logs lors de l&#39;expiration du certificat de l&#39;application.
* L&#39;aperçu du calcul de payload inclut maintenant une taille de champ personnalisée afin d&#39;éviter les échecs de notification push. (CAMP-35303)
* Le nom du **fichier Rejets** dans l&#39;activité **Chargement de fichier** peut maintenant être personnalisé de la même manière que dans l&#39;activité **Exportation de fichier**.
* Toutes les entités personnalisées qui ne sont liées à aucune entité d&#39;usine sont désormais accessibles via l&#39;API.
* Amélioration des performances de la base de données sur les ressources volumineuses.
* La description de certaines erreurs se produisant lors de l&#39;envoi de SMS a été rendue plus claire. (CAMP-36558)
* Un message d&#39;erreur s&#39;affiche maintenant lors de l&#39;exécution de l&#39;activité **Planificateur** d&#39;un workflow qui est connecté à lui-même, soit directement, soit par le biais de plusieurs activités, car cela peut entraîner le blocage du serveur des workflows de l&#39;instance.
* Des améliorations ont été apportées pour résoudre les problèmes de messagerie transactionnelle : le lien &quot;Données&quot; a été renommé &quot;Derniers événements transactionnels&quot; dans l&#39;écran de configuration de l&#39;événement. Il répertorie désormais les événements reçus triés dans un ordre décroissant. Un nouvel état d&#39;événement transactionnel a également été créé : &quot;targetingFailed&quot;. Lorsque le module de messagerie transactionnelle ne parvient pas à enrichir un lien utilisé pour le ciblage des messages, l&#39;événement transactionnel se trouve désormais dans ce nouvel état (au lieu de l&#39;état &quot;routingFailed&quot;).
* Des améliorations ont été apportées à l&#39;interface lors de la limitation de l&#39;accès à une landing page à des entités géographiques ou organisationnelles spécifiques. L&#39;objectif est d&#39;avertir que la landing page peut être soumise à des conditions de visibilité : la sélection d&#39;une entité géographique et organisationnelle lors de la création d&#39;une landing page est désormais obligatoire. Une bannière contenant des informations connexes s&#39;affiche désormais une fois qu&#39;une entité est sélectionnée. Le message d&#39;erreur qui s&#39;affiche lors du test de la landing page est plus clair.
* Dans les API Campaign Standard, les clés personnalisées ne peuvent pas être modifiées à l&#39;aide d&#39;une opération PATCH si la valeur de la clé est différente de celle de la clé d&#39;origine ou si vous utilisez votre propre clé d&#39;entreprise comme URI au lieu de celle fournie par Adobe.
* La langue &quot;Albanais - Macédoine&quot; a été ajoutée à la liste déroulante des préférences linguistiques. (CAMP-35396)

**Correctifs**

* Correction d&#39;un problème qui empêchait le tri ou la recherche des rapports planifiés.
* Correction d&#39;un problème lié aux règles Triggers en raison duquel les règles ET et OU étaient mélangées.
* Correction d&#39;un problème en raison duquel la propriété Mobile s&#39;affichait comme Supprimé dans Launch. (CAMP-35382)
* Correction d&#39;un problème qui empêchait la synchronisation des propriétés mobiles d&#39;Adobe Launch dans Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Correction d&#39;un problème en raison duquel les messages push transactionnels échouaient lorsque des événements étaient enrichis avec des données de profil. (CAMP-34385)
* Correction d&#39;un problème en raison duquel les propriétés mobiles ne se synchronisaient pas dans plusieurs environnements. (CAMP-37060)
* Correction d&#39;un problème lors de la sélection, dans une notification push, d&#39;un modèle à l&#39;aide d&#39;une formule de date de contact. (CAMP-35300)
* Correction d&#39;un problème en raison duquel le service d&#39;envoi de messages pouvait se bloquer. (CAMP-35287)
* Correction d&#39;un problème lié aux courriers récurrents, tous définis avec la date du premier événement. (CAMP-35139)
* Correction d&#39;un problème lié aux ressources personnalisées **Profils** nouvellement étendues qui n&#39;étaient pas disponibles pour les requêtes. (CAMP-35119)
* Correction du mode **Réparer la structure de la base de données** pour les instances avec la configuration de partage activée. (CAMP-35118)
* Correction d&#39;un problème qui entraînait une erreur de log SQL lors de l&#39;ajout de données agrégées sur les broadlogs. (CAMP-35034)
* Correction d&#39;un problème lié aux transitions lors de la création d&#39;une activité **Segmentation**. (CAMP-35033)
* Correction d&#39;un problème dans l&#39;activité **Requête** qui empêchait la fonction **encryption_aescbcDecrypt** de déchiffrer la fonction **encryption_aescbcEncrypt**. (CAMP-34952)
* Correction d&#39;un problème qui pouvait empêcher l&#39;affichage des **Logs de tracking** dans les diffusions. (CAMP-34855)
* Correction d&#39;un problème lors de l&#39;utilisation d&#39;une formule de date personnalisée d&#39;**optimisation du temps d&#39;envoi**, qui pouvait empêcher l&#39;envoi de notifications push en raison d&#39;erreurs liées aux données additionnelles du workflow. (CAMP-30336)
* Correction d&#39;un problème qui pouvait empêcher la publication des ressources personnalisées. (CAMP-37425)
* Correction d&#39;un problème qui empêchait les utilisateurs administrateurs de modifier les packages d&#39;import.  (CAMP-37176)
* Correction d&#39;un problème dans les workflows qui empêchait l&#39;envoi de BAT si l&#39;activité de diffusion était reliée à une activité **Lecture d&#39;audience** vide. (CAMP-37164)
* Correction d&#39;un problème qui empêchait l&#39;import de ressources personnalisées dans un nouvel environnement. (CAMP-36506)
* Correction d&#39;un problème dans les rapports Hot clicks, en raison duquel les pourcentages étaient masqués par les images (CAMP-36407).
* Correction d&#39;un problème qui se produisait lors de l&#39;export d&#39;un champ de description de diffusion. (CAMP-35467)
* Correction d&#39;un problème en raison duquel l&#39;état d&#39;une diffusion pouvait être &quot;Démarrage en attente&quot; même si la diffusion était terminée. (CAMP-35355)
* Correction d&#39;un problème qui empêchait l&#39;affichage des logs des workflows après activation, puis désactivation des logs SQL.

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
   <td> <p>Pour accroître la personnalisation, l'activité API externe permet de récupérer des données provenant de systèmes externes dans un workflow via un appel API REST. Les points d'entrée REST peuvent être un système de gestion client, le Runtime Adobe I/O Runtime ou un point d'entrée REST Adobe Experience Cloud (par exemple, Data Platform, Target, Analytics, Campaign).</p><p>Cette fonctionnalité est actuellement en version bêta publique.</p><p>Pour plus d'informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapport sur le segment de workflow<br /> </td> 
   <td> <p>Cette fonctionnalité permet aux marketeurs de répartir les performances de diffusion par code segment. Lorsque vous créez un workflow et que vous utilisez une activité de segmentation pour affecter des segments à la population de la diffusion, ces derniers peuvent maintenant être intégrés dans la même diffusion. Vous pouvez ainsi afficher les statistiques d'ouverture/clic selon plusieurs segments au sein d'une seule diffusion.</p><p>Pour plus d'informations, consultez la <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">vidéo de procédure</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Améliorations de la sécurité**

* Correction d&#39;un problème de sécurité pour empêcher les attaques par déni de service (DoS) sur les demandes d&#39;obtention d&#39;images non valides. (CAMP-33454)

**Améliorations du Concepteur d&#39;email**

* Correction d&#39;un problème qui ajoutait des balises de style HTML supplémentaires à un modèle HTML chaque fois qu&#39;un composant était ajouté, ce qui augmentait considérablement la taille du modèle. (CAMP-34694)
* Correction d&#39;un problème qui empêchait la disponibilité de certaines options de menu de la barre d&#39;outils supérieure droite. (CAMP-34577)
* Correction d&#39;un problème qui se produisait lorsque le bloc de contenu URL de la page miroir était inséré dans un contenu d&#39;email. (CAMP-34779)
* Correction d&#39;un problème qui se produisait lors de l&#39;utilisation du code JPSP dans un email, rendant difficile l&#39;édition du contenu. (CAMP-34574)
* Correction d&#39;un problème en raison duquel les images étaient tronquées dans la partie supérieure en cas d&#39;ajout d&#39;un lien hypertexte sur celles-ci. (CAMP-34382)
* Correction d&#39;un problème d&#39;affichage lors de l&#39;utilisation du Concepteur d&#39;email avec Firefox. (CAMP-34364)
* Correction de plusieurs problèmes liés au mode Avancé qui se produisaient lors de la définition du contenu dynamique d&#39;un email. (CAMP-34351, CAMP-34333, CAMP-34331)
* Correction de plusieurs problèmes liés à l&#39;éditeur de règles de contenu dynamique (CAMP-34304, CAMP-34303).
* Correction d&#39;un problème qui empêchait l&#39;affichage du champ Lien dans le volet Paramètres du Concepteur d&#39;email (CAMP-33749).
* Correction d&#39;un problème lié à l&#39;icône YouTube qui était surdimensionnée dans les emails envoyés. (CAMP-33726)
* Correction d&#39;un problème de sécurité qui permettait d&#39;éditer le contenu de la page miroir. (CAMP-33691)
* Correction d&#39;un problème qui endommageait la sortie HTML lors de l&#39;utilisation du symbole supérieur à dans du contenu dynamique. (CAMP-33688)
* Correction d&#39;un problème qui se produisait lors de l&#39;utilisation de l&#39;option Annuler pendant l&#39;édition de texte dans le Concepteur d&#39;email. (CAMP-32565)
* Correction d&#39;un problème qui créait des balises supplémentaires lors de l&#39;annulation de styles au lieu de les supprimer. (CAMP-32359)
* Vous pouvez maintenant définir si chaque composant utilisé dans un email s&#39;affichera uniquement sur les postes de travail ou sur les appareils mobiles.
* Vous pouvez désormais définir la largeur et la hauteur d&#39;un composant de contenu Social.
* Correction d&#39;un problème qui empêchait l&#39;ancien code source d&#39;un contenu dynamique d&#39;être supprimé après la suppression de ce contenu dynamique.
* Correction d&#39;un problème qui empêchait la mise à jour de l&#39;objet d&#39;un email après sa modification.
* Correction d&#39;un problème qui empêchait la sélection d&#39;une structure de colonne n:n une fois déposée dans l&#39;espace de travail.
* Correction d&#39;un problème en raison duquel la miniature du message apparaissait floue dans le tableau de bord de l&#39;email.
* Correction d&#39;un problème qui empêchait l&#39;affichage correct de l&#39;arrière-plan des emails reçus dans Outlook.
* Correction de certains problèmes de tri sur la page d&#39;accueil du Concepteur d&#39;email.
* Correction d&#39;un problème qui se produisait lors de la duplication de variantes pendant l&#39;utilisation de contenu dynamique.
* Certains champs indésirables ont été supprimés du volet Paramètres du Concepteur d&#39;email.

**Autres améliorations**

* Grâce à l&#39;intégration avec Adobe Experience Platform Location Services, Adobe Campaign est maintenant compatible pour envoyer des messages marketing géolocalisés aux abonnés de votre application mobile via le SDK Experience Platform. Pour plus d&#39;informations, consultez la [documentation détaillée](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La fonctionnalité de reporting a été améliorée pour offrir une meilleure expérience. Pour utiliser cette fonctionnalité, vous devez accepter le contrat d&#39;utilisation des rapports dynamiques. Consultez à ce sujet la [documentation détaillée](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Dans les workflows, une option a été ajoutée pour prévisualiser les dix prochaines exécutions d&#39;un workflow. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Dans l&#39;activité Planificateur, une nouvelle option permet de sélectionner un jour spécifique d&#39;une semaine particulière pour les diffusions mensuelles. Consultez à ce sujet la [documentation détaillée](../../automating/using/scheduler.md).
* Lors de la création de diffusions récurrentes sans période d&#39;agrégation, le tableau de bord de diffusion permet maintenant de demander confirmation avant l&#39;envoi de la diffusion. Consultez à ce sujet la [documentation détaillée](../../sending/using/confirming-the-send.md).
* Vous pouvez maintenant personnaliser le libellé d&#39;une diffusion avec des variables d&#39;événements qui ont été déclarées dans l&#39;activité de signal externe du workflow. Consultez à ce sujet la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md).
* Amélioration de la requête de suppression RGPD pour de meilleures performances. (CAMP-33504)
* Suppression de l&#39;option &quot;ftp&quot; de l&#39;interface de configuration des comptes externes. (CAMP-34472)
* Vous pouvez maintenant activer et désactiver l&#39;option Mode test SMTP pour chaque email. Consultez à ce sujet la [documentation détaillée](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Autres changements**

* Un avertissement a été ajouté à l&#39;interface des propriétés de diffusion. Il indique que les diffusions sont préparées en fonction de leur période d&#39;agrégation. Pour appeler le workflow plusieurs fois par jour, vous devez donc vérifier qu&#39;elles n&#39;ont aucune période. (CAMP-34393)
* Un avertissement a été ajouté aux écrans de configuration des ressources personnalisées. Il est recommandé d&#39;utiliser 30 caractères maximum pour les identifiants des ressources personnalisées. Cette recommandation s&#39;applique également aux champs de ressources personnalisées, aux clés, aux index et aux liens.
* Un message s&#39;affiche maintenant lorsque vous essayez de supprimer un message transactionnel utilisé par une landing page en tant que message de confirmation.
* Un avertissement s&#39;affiche maintenant dans les logs de workflow lorsqu&#39;une activité est en cours d&#39;exécution pendant plus de 6 heures. Cela ne s&#39;applique pas aux activités Notification push, Diffusion, Signal, Début, Fin, Branchement, Union, Planificateur et Attente.
* Un avertissement s&#39;affiche maintenant dans les logs de workflow lorsque vous atteignez le nombre maximal de workflows en cours d&#39;exécution simultanément.
* Les workflows en pause ou en échec pendant plus de 7 jours sont maintenant arrêtés pour consommer moins d&#39;espace disque. La tâche de nettoyage s&#39;affiche dans les logs de workflow.
* Lors de l&#39;utilisation d&#39;une activité &quot;Transfert de fichier&quot;, une erreur est maintenant consignée si la taille du fichier dépasse l&#39;espace disque disponible.
* L&#39;action Rediriger vers l&#39;URL de destination ne peut plus être sélectionnée pour le bouton secondaire dans les messages in-app.

**Correctifs**

* Correction d&#39;un problème qui entraînait l&#39;échec des demandes d&#39;accès RGPD.
* Correction d&#39;un problème qui entraînait l&#39;annulation des Triggers lors de la réception de plusieurs Triggers pour un profil unique.
* Correction d&#39;un problème qui entraînait un message d&#39;erreur de publication de ressource personnalisée erroné après la connexion.
* Correction d&#39;un problème qui affichait une page vierge lors de la création ou de l&#39;extension d&#39;une ressource personnalisée.
* Correction d&#39;un problème qui empêchait une audience avec appSubscriptionrcp comme dimension de ciblage d&#39;être disponible pour le ciblage dans une diffusion mobile.
* Correction d&#39;une erreur qui empêchait la mise en quarantaine des adresses hard bounce. (CAMP-24587)
* Correction d&#39;un problème qui se produisait lors de l&#39;ajout d&#39;une règle de typologie et qui la supprimait avant de l&#39;enregistrer. (CAMP-32789)
* Correction d&#39;un problème qui empêchait l&#39;affichage du contenu de la landing page lors de la désactivation du contenu dynamique. (CAMP-32924)
* Correction d&#39;un problème lié aux diffusions récurrentes qui se produisait lors de l&#39;utilisation de la personnalisation sur les attributs d&#39;une diffusion principale. (CAMP-32983)
* Correction d&#39;un problème dans les workflows qui empêchait la lecture des résultats d&#39;une transition contenant des données de SMS entrants. (CAMP-33134)
* Correction d&#39;un problème dans les workflows qui se produisait lors de la combinaison d&#39;activités de branchement et d&#39;exclusion pour créer des audiences. (CAMP-33401)
* Correction d&#39;un problème qui empêchait l&#39;affichage du contenu de la page miroir et l&#39;envoi des messages du BAT pour les diffusions récurrentes. (CAMP-33413)
* Correction d&#39;un problème qui entraînait une erreur lors de l&#39;utilisation d&#39;une activité Union entre les profils et les audiences. Ce problème était dû à une incompatibilité des clés d&#39;identification dans les transitions d&#39;entrée. (CAMP-33713)
* Correction d&#39;un problème dans les activités Test qui empêchait l&#39;expression &quot;recCount&quot; d&#39;utiliser la syntaxe correcte lors d&#39;un double-clic dessus. (CAMP-33756)
* Correction d&#39;un problème qui entraînait un message d&#39;erreur lors de l&#39;ouverture des logs de workflow technique de facturation. (CAMP-34313)
* Correction d&#39;un problème dans les landing pages qui se produisait lors de la configuration des champs de case à cocher avec des abonnements. (CAMP-34369)
* Correction d&#39;un problème qui se produisait lors de la configuration d&#39;une liste et de l&#39;ajout du champ &quot;icône&quot; à celle-ci. (CAMP-34585)
* Correction d&#39;un problème qui empêchait l&#39;utilisation des symboles &quot;|&quot; et &quot;%&quot; en tant que séparateurs de date ou d&#39;heure dans les activités de workflow de chargement de fichier. (CAMP-34706)
* Correction d&#39;un problème qui se produisait lors de l&#39;utilisation des conditions de visibilité avec des cases à cocher dans les landing pages. (CAMP-34802)
* Correction d&#39;un problème dans l&#39;activité Enrichissement qui empêchait l&#39;affichage des champs de l&#39;onglet &quot;Données additionnelles&quot; si la dimension de filtrage était définie sur les logs de tracking et la dimension cible dans le profil.
* Correction d&#39;un problème qui entraînait un message d&#39;erreur lors de l&#39;export d&#39;une ressource « workflowTemplate ».
* Correction d&#39;un problème qui empêchait, lors de la création d&#39;un profil, d&#39;enregistrer le champ « Code pays/zone géographique » s&#39;il était sélectionné dans la boîte de dialogue.
* Correction de plusieurs problèmes qui se produisaient lors de l&#39;utilisation du modèle d&#39;import de courrier (updateQuarantinesDeliveryLogsDirectMail).
* Correction d&#39;un problème lié à l&#39;intégration d&#39;Assets on Demand.
* Correction d&#39;un problème qui se produisait lors de la réalisation d&#39;un zoom avant dans la vue Planning. (CAMP-33628)
* Correction d&#39;un problème qui empêchait l&#39;envoi instantané des BAT pour les emails avec une date et une heure planifiées. (CAMP-33723)
* Correction d&#39;un problème lié aux messages transactionnels qui générait des logs d&#39;erreur lors de la déconnexion d&#39;un utilisateur. (CAMP-31698)
* Correction d&#39;une erreur qui se produisait dans des environnements spécifiques lors de la planification d&#39;un email.
* Correction d&#39;un problème qui entraînait l&#39;échec du workflow Mise à jour de l&#39;exécution des diffusions.
* Correction d&#39;un problème de sécurité qui endommageait le contenu d&#39;un email lorsque l&#39;objet contenait plusieurs lignes.


## Version 19.2.7 - Juillet 2019 {#release-19-2-7---july-2019}

**Améliorations**

* Amélioration de la requête de suppression RGPD pour de meilleures performances.
* Correction d&#39;un problème qui entraînait des blocages web après la mise à niveau 19.2. (CAMP-34862)
* Correction d&#39;un problème qui empêchait les utilisateurs autres qu&#39;administrateurs d&#39;enregistrer ou de planifier des rapports. (CAMP-31133)
* Correction d&#39;un problème lors de l&#39;utilisation de du caractère &quot;|&quot; comme séparateur de date dans l&#39;activité de workflow Chargement de fichier. (CAMP-34706)

## Version 19.2.4 - Juin 2019 {#release-19-2-4---june-2019}

**Concepteur d&#39;email**

* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;éditer des fragments si le code HTML contenait des balises &lt;style> vides. Il s&#39;agit d&#39;un correctif de suivi pour CAMP-33778 dans la version 19.2.3.

## Version 19.2.3 - Juin 2019 {#release-19-2-3---june-2019}

**Concepteur d&#39;email**

Mise en place d&#39;une série d&#39;améliorations et de correctifs afin d&#39;optimiser les fragments dans la version 19.2. Les nouveaux fragments fonctionneront de manière transparente. Les fragments conçus précédemment ont été grisés et devront être migrés vers le nouveau format. Pour cela, cliquez sur chaque fragment et validez sa migration vers le nouveau format. Nous vous recommandons de tester quelques fragments avant de migrer l&#39;ensemble.

* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;éditer un fragment après l&#39;avoir déverrouillé. Ce problème avait une incidence sur les fragments existants lors de la mise à jour vers la version 19.2. (CAMP-33778)
* Correction d&#39;un problème qui se produisait lors de l&#39;utilisation du contenu dynamique. Des espaces supplémentaires étaient ajoutées dans le code HTML.

**Autres améliorations**

* Correction d&#39;un problème qui empêchait la reprise de l&#39;envoi des SMS suite à une déconnexion du connecteur SMS.
* Correction d&#39;un problème qui fermait les connexions SMPP lorsque TLS était activé.
* Correction d&#39;un problème qui fermait les connexions SMPP lorsque TLS était activé.
* L&#39;option &quot;Launch_URL_Campaign&quot; a été ajoutée dans Campaign pour gérer les propriétés des applications mobiles créées avec le SDK Mobile Adobe Experience Platform.
* Correction d&#39;une erreur qui entraînait la désélection de l&#39;option d&#39;environnement sandbox après le téléchargement du certificat d&#39;une nouvelle propriété mobile et la sortie de la page de propriété de l&#39;application mobile.
* Correction d&#39;un problème qui empêchait l&#39;utilisateur d&#39;enrichir le contenu d&#39;un message transactionnel avec des informations de la ressource Service. (CAMP-33707)
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
   <td> <p>Pour accroître l'efficacité de votre travail en tant qu'utilisateur administrateur, vous pouvez facilement surveiller la capacité de vos instances et gérer leurs paramètres (à commencer par la gestion des serveurs SFTP).</p><p>Pour plus d'informations, consultez la <a href="https://docs.adobe.com/content/help/fr-FR/control-panel/using/control-panel-home.html">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/control-panel-overview.html">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notifications locales<br /> </td> 
   <td> <p>Les messages de notification locale permettent d'informer les utilisateurs lorsque de nouvelles données deviennent disponibles dans leurs applications mobiles, même sans accès à Internet ou sans l'application mobile s'exécutant au premier plan. Les notifications locales sont déclenchées par une application mobile à une heure donnée et en fonction d'un événement.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentation détaillée</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux workflows : ajout d'une payload à l'activité de signal externe<br /> </td> 
   <td> <p>Démarrez un workflow avec une payload lorsque les conditions définies sont satisfaites à partir d'un autre workflow ou d'un appel d'API REST de façon à intégrer avec vos systèmes externes. Une nouvelle activité de <strong>test</strong> permet aussi d'exécuter des tests sur cette fonctionnalité.</p><p>Pour plus d'informations, consultez la <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">vidéo de procédure</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Amélioration apportée aux landing pages : Google reCAPTCHA<br /> </td> 
   <td> <p>Utilisez Google reCAPTCHA pour empêcher tout spam sur vos landing pages sans intervention de vos clients.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentation détaillée</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Améliorations de la sécurité**

* Correction d&#39;un problème de sécurité potentiel de détournement de clic dans l&#39;espace de travail de reporting.

**Améliorations du Concepteur d&#39;email**

* Correction d&#39;un problème qui se produisait lors de la duplication de fragments et de leur utilisation dans le Concepteur d&#39;email. (CAMP-33193)
* Correction d&#39;un problème qui créait des espaces inutiles lors de l&#39;utilisation d&#39;éléments incorporés dans l&#39;interface du Concepteur d&#39;email. (CAMP-32163)
* Correction d&#39;un problème qui supprimait certains attributs de balise HTML supplémentaires ajoutés par l&#39;utilisateur après avoir enregistré le contenu d&#39;un email dans le Concepteur d&#39;email. (CAMP-32162)
* Correction d&#39;un problème qui affichait une balise Microsoft Office en mode HTML du Concepteur d&#39;email, même après sa suppression. (CAMP-32141)
* Si vous avez créé un email à l&#39;aide d&#39;une version antérieure du Concepteur d&#39;email, une fenêtre contextuelle s&#39;ouvre maintenant lors de l&#39;ouverture du contenu de cet email pour inviter l&#39;utilisateur à effectuer une mise à jour vers la version la plus récente. (CAMP-31529)
* Correction d&#39;un problème qui déformait les images d&#39;un email créé avec le Concepteur d&#39;email lorsqu&#39;il était diffusé à certains clients de messagerie. (CAMP-31407)
* Correction d&#39;un problème qui empêchait l&#39;affichage correct de certains éléments (listes ou boutons, par exemple) en mode texte brut lorsqu&#39;ils avaient été créés en mode HTML. (CAMP-32582, CAMP-32542)
* Correction d&#39;un problème qui empêchait l&#39;affichage de plus de 50 entités organisationnelles dans un modèle de contenu ou des propriétés de fragment. (CAMP-32932)
* Correction d&#39;un problème lié à la couleur d&#39;arrière-plan de la fenêtre d&#39;affichage lors de la réception dans Outlook d&#39;un email créé avec le Concepteur d&#39;email. (CAMP-31402)
* Correction d&#39;un problème qui empêchait les contenus d&#39;email créés avec le Concepteur d&#39;email d&#39;être réactifs lorsqu&#39;ils étaient ouverts dans Outlook. (CAMP-31400)
* Correction d&#39;un problème qui empêchait le contenu dynamique de fonctionner correctement lorsqu&#39;il était utilisé dans l&#39;objet d&#39;un email. (CAMP-32837)
* Correction d&#39;un problème lié aux objets des emails qui n&#39;étaient pas correctement placés dans une séquence d&#39;échappement.
* Correction d&#39;un problème qui empêchait le chargement de fragments dans la palette de gauche du Concepteur d&#39;email.
* Correction d&#39;un problème qui empêchait l&#39;affichage des fragments créés lors de l&#39;édition du contenu d&#39;email dans la palette de gauche du Concepteur d&#39;email au moment de l&#39;actualisation de la liste des fragments.
* Correction de plusieurs problèmes qui se produisaient lors de l&#39;utilisation de contenu dynamique dans un email.
* Correction d&#39;un problème lié au sélecteur de couleurs qui se produisait lors de la définition d&#39;une couleur à l&#39;aide de valeurs RVB.
* Correction d&#39;un problème qui empêchait la page miroir d&#39;être réactive lors de la réception de l&#39;email sur un mobile.

**Améliorations apportées aux messages transactionnels**

Pour optimiser le fonctionnement et les performances, plusieurs améliorations ont été ajoutées au canal Messages transactionnels.

* La durée des messages transactionnels a été prolongée afin que tous les messages soient envoyés avant leur expiration, en particulier lors de reprises.
* Les performances des messages transactionnels ont été améliorées en répartissant la charge sur différents threads d&#39;envoi.
* Le processus des messages transactionnels a été optimisé pour pouvoir lancer en parallèle plusieurs analyses d&#39;un même message.
* Correction d&#39;un problème qui pouvait entraîner une incohérence du débit et de la latence pour les notifications push transactionnelles.
* Correction d&#39;un problème qui affichait une audience cible incorrecte pour les diffusions d&#39;exécution de messages transactionnels.
* Correction d&#39;un problème qui se produisait lors de l&#39;import d&#39;un package avec une configuration d&#39;événement et le message transactionnel associé. Consultez à ce sujet la [documentation détaillée](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Correction d&#39;un problème qui supprimait les données de collecte des profils de test créés pour un message transactionnel contenant des listes de produits.

**Autres changements**

* Une nouvelle option a été ajoutée au compte externe SMS. Elle permet de limiter le nombre maximal de processus MTA envoyant des SMS afin de mieux contrôler le nombre de connexions parallèles. Pour plus d&#39;informations, consultez la technote [Protocole et paramètres du connecteur SMS](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html).
* Lors de la publication d&#39;une ressource avec une extension d&#39;API, si l&#39;API a déjà été publiée, elle est automatiquement mise à jour à chaque nouvelle publication. Auparavant, cette action était manuelle et le fait de ne pas mettre à jour l&#39;API pouvait endommager la ressource profil ou les ressources de services de celle-ci. Consultez à ce sujet la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimension de code postal a été supprimée des rapports dynamiques. Il est recommandé d&#39;utiliser plutôt les dimensions de ville, pays et état.
* Le trigger d&#39;événement de cycle de vie &quot;Premier lancement&quot; pour les messages In-App a été supprimé.
* Lors de l&#39;export d&#39;un package avec des groupes de sécurité, celui-ci contient désormais les rôles attribués à chaque groupe. (CAMP-32960)
* Dans l&#39;activité Chargement de fichier, une nouvelle option permet de vérifier que les colonnes du fichier téléchargé correspondent à la définition de colonne. Pour plus d&#39;informations, consultez la [documentation détaillée](../../automating/using/load-file.md). (CAMP-32229)
* Les workflows peuvent maintenant être démarrés avec une payload, ce qui permet d&#39;utiliser et de partager des paramètres externes entre les activités au sein d&#39;un workflow. Pour plus d&#39;informations, consultez la [documentation détaillée](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 et CAMP-29413)
* Les API de Campaign Standard permettent maintenant de mettre à jour les entités géographiques et organisationnelles des profils à l&#39;aide d&#39;une payload. Pour plus d&#39;informations, consultez la [documentation détaillée](../../api/using/get-started-apis.md).
* Les messages d&#39;erreur qui s&#39;affichent lorsqu&#39;un objet de la base de données n&#39;est pas accessible ont été clarifiés.
* Dans l&#39;activité Extraction de fichier, les capacités Javascript ont été mises à jour lors de la définition du nom d&#39;un fichier à exporter. Seule la fonction formatDate est maintenant disponible pour une utilisation dans le champ Sortie. Pour plus d&#39;informations, consultez la [documentation détaillée](../../automating/using/extract-file.md).
* La génération automatique d&#39;ID de séquence a été améliorée pour les ressources personnalisées. Les clés primaires pour les nouvelles ressources personnalisées sont maintenant 64 bits par défaut.
* Le mode de test de publication de ressource personnalisée a été amélioré. Un message d&#39;avertissement s&#39;affiche maintenant si la dernière publication de ressource personnalisée est en échec et n&#39;est pas corrigée. Après un échec de publication de ressource personnalisée, vous pouvez revenir à la dernière version opérationnelle. Pour plus d&#39;informations, consultez la [documentation détaillée](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Une nouvelle option a été ajoutée à l&#39;activité Transfert de fichier. Elle permet de trier les fichiers lorsque vous utilisez l&#39;action de téléchargement de fichier, en mode SFTP. Pour plus d&#39;informations, consultez la [documentation détaillée](../../automating/using/transfer-file.md). (CAMP-33109)

**Correctifs**

* Correction d&#39;un problème qui entraînait une fuite de mémoire sur le MTA lorsque les paramètres SMS étaient rechargés.
* Correction d&#39;un problème qui empêchait la publication des mises à jour de la base de données en mode de réparation.
* Correction d&#39;un problème qui entraînait des divergences entre les rapports Adobe Analytics et les rapports dynamiques Adobe Campaign. (CAMP-25393)
* Correction d&#39;une erreur qui entraînait l&#39;échec du workflow de partage de rapport.
* Correction d&#39;une erreur qui empêchait les utilisateurs d&#39;envoyer des messages In-App avec uniquement l&#39;URL de média.
* Correction d&#39;un problème qui affichait une application mobile, même si son certificat n&#39;était pas téléchargé sur l&#39;instance.
* Correction d&#39;une erreur qui empêchait les champs de personnalisation de fonctionner lors de l&#39;utilisation du modèle **Cibler tous les utilisateurs d&#39;une application mobile**.
* De nouvelles instances de Campaign Standard ont été configurées. (CAMP-32635 et CAMP-32344)
* Correction d&#39;une erreur qui empêchait la personnalisation de la formule de date dans un workflow. (CAMP-30336)
* Correction d&#39;un problème lors de la définition d&#39;une formule de date personnalisée qui pouvait empêcher les champs &quot;Données additionnelles&quot; et &quot;Code segment&quot; d&#39;être disponibles dans la liste déroulante. (CAMP-32383)
* Correction d&#39;un problème qui pouvait empêcher les activités &quot;Transfert de fichier&quot; et &quot;Extraction de fichier&quot; de rechercher les rejets de fichiers s&#39;ils étaient cryptés. (CAMP-32377)
* Correction d&#39;un problème dans les API qui pouvait empêcher le filtre lineCount d&#39;afficher le nombre total exact. (CAMP-31424)
* Correction d&#39;un problème dans les landing pages qui empêchait les champs d&#39;entrée d&#39;afficher la valeur mise à jour une fois celle-ci modifiée. (CAMP-31401)
* Correction d&#39;un problème qui entraînait l&#39;activation inattendue d&#39;une activité de signal.
* Correction d&#39;un problème qui empêchait l&#39;affichage de l&#39;aperçu d&#39;un email lorsque l&#39;audience était vide.
* Correction d&#39;un problème dans l&#39;activité &quot;Extraction de fichier&quot; qui entraînait la génération d&#39;un fichier alors que l&#39;option &quot;Ne pas générer de fichier si la transition entrante est vide&quot; était activée.
* Correction d&#39;un problème qui entraînait la désactivation du workflow de délivrabilité s&#39;il ne se terminait pas correctement.
* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;enregistrer ou de planifier des rapports. (CAMP-31133)

## Version 19.1.3 - Mars 2019      {#release-19-1-3---march-2019}

**Améliorations du Concepteur d&#39;email**

* Correction d&#39;un problème qui empêchait la modification d&#39;un modèle après son enregistrement.
* Résolution de divers problèmes qui pouvaient se produire dans les emails lors de l&#39;utilisation d&#39;un modèle créé auparavant.
* Correction d&#39;un problème qui empêchait le masquage des composants dans les modèles importés.

**Autres améliorations**

* Correction d&#39;une erreur qui se produisait lors de l&#39;affichage des règles de typologie. (CAMP-32059 et CAMP-31849)
* Correction d&#39;un problème qui empêchait l&#39;édition des règles de typologie. (CAMP-31750)
* Correction d&#39;un problème lié au processus inMail qui pouvait s&#39;arrêter de manière inattendue. (CAMP-31238)

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
   <td> <p>Plusieurs améliorations ont été apportées au reporting du canal push afin de mesurer l'engagement des utilisateurs de manière plus intuitive. Avec cette version, la liste des mesures du canal push compte désormais trois mesures différentes : Impressions, Clics, Ouvertures (ouverture de l'application). Celles-ci vous permettent de mesurer et d'analyser plus efficacement l'interaction des utilisateurs avec les notifications push. Nous normalisons également la définition et la mise en œuvre de ces mesures. Le rapport intégré relatif aux notifications push a également été amélioré. Il comporte désormais des visualisations et des mesures couramment utilisées.</p><p> Pour plus d'informations, consultez la <a href="../../reporting/using/push-notification-report.md">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Launch pour les applications mobiles<br /> </td> 
   <td> <p>Cette version contient l'intégration d'Adobe Campaign avec les versions de disponibilité générale des extensions Android et iOS pour Adobe Campaign Standard dans les SDK Adobe Experience Platform Launch et Mobile. Ces extensions prennent en charge la messagerie push, la messagerie In-App et les mises à jour des profils des applications mobiles.</p><p> Pour plus d'informations, consultez la <a href="https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html">documentation détaillée</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Messagerie In-App mobile<br /> </td> 
   <td> <p>Cette version contient la version de disponibilité générale du canal In-App dans Campaign. D'un point de vue fonctionnel, les ajouts les plus importants à la version bêta sont les rapports dynamiques pour le canal In-App et l'établissement d'une liaison sécurisée entre le SDK Mobile et MCIAS (service de messagerie In-App Experience Cloud qui fournit les règles In-App au SDK). L'établissement d'une liaison sécurisée garantit que les données PII de vos utilisateurs ne tombent pas entre des mains malveillantes. Il permet également de préserver la confidentialité de l'utilisateur sur un appareil partagé en effaçant le cache des messages chaque fois que l'utilisateur se déconnecte.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a> et le <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">tutoriel In-App</a> dédié.</p> </td> 
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

**Améliorations de la sécurité**

* Le code HTML de landing page généré a été mis à jour afin d&#39;empêcher toute indexation par les moteurs de recherche.

**Améliorations du Concepteur d&#39;email**

* Un ensemble de quatre modèles d&#39;email réactif conçus par des artistes Behance est maintenant disponible.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../designing/using/using-reusable-content.md#content-templates).

* Notre nouvelle expérience d&#39;intégration vous permet de commencer à créer plus rapidement des emails et facilite l&#39;accès à la documentation et aux tutoriels.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Vous avez maintenant la possibilité de configurer le nombre et la largeur des colonnes en fonction de vos besoins.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Lors de l&#39;édition dans la vue mobile, vous pouvez masquer certains composants uniquement dans l&#39;affichage mobile pour utiliser efficacement l&#39;espace.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Vous pouvez maintenant ajouter des canaux sociaux personnalisés à votre modèle d&#39;email en plus de ceux déjà disponibles.
* Correction d&#39;un problème qui empêchait de faire défiler le menu de structure lorsque plus de 18 structures étaient utilisées. (CAMP-31173)
* Correction d&#39;un problème qui affichait le pré-en-tête en haut du contenu lors du transfert d&#39;un email contenant un pré-en-tête envoyé avec Adobe Campaign. (CAMP-30736)
* Correction d&#39;un problème qui empêchait la mise à jour de la ligne d&#39;objet lorsque l&#39;utilisateur cliquait sur l&#39;option **Actualiser le contenu AEM** après avoir modifié l&#39;objet dans Adobe Experience Manager. (CAMP-29984)
* Correction de plusieurs problèmes qui empêchaient l&#39;utilisation d&#39;images dynamiques d&#39;Adobe Target.
* Correction d&#39;un problème qui empêchait la mise à jour de l&#39;aperçu lors de la récupération du contenu au moment de la préparation si le contenu avait déjà été importé à partir d&#39;une URL.
* L&#39;icône YouTube a été ajoutée au composant de contenu **Social**.
* La vue **Liste** a été ajoutée pour les composants de contenu et les fragments affichés dans la palette du Concepteur d&#39;email.

**Autres améliorations**

* Adobe Campaign est désormais entièrement compatible FCM pour les applications SDK V4 et SDK AEP.
* Adobe Campaign prend en charge les notifications push sous Wear OS (Android) et watchOS (Apple).
* Les messages d&#39;avertissement et d&#39;erreur pouvant s&#39;afficher lors de la navigation dans l&#39;interface ont été clarifiés et simplifiés.
* Vous pouvez maintenant ajouter à la liste des profils des colonnes relatives à l&#39;opt-in et l&#39;opt-out (champs &quot;Ne plus contacter…&quot;).
* La liste déroulante Fuseau horaire de l&#39;écran de création de profil a été déplacée de la section Adresse vers la section supérieure de l&#39;interface.
* Vous pouvez maintenant ajouter des séparateurs lors de la configuration d&#39;écrans de ressources personnalisés, ce qui vous permet d&#39;organiser vos champs en catégories.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Autres changements**

* A compter du printemps 2019 et de la version Campaign Standard 19.2, Adobe Campaign et Adobe Experience Cloud arrêteront la prise en charge de Microsoft Internet Explorer 11. Passez à Microsoft Edge ou tout autre navigateur pris en charge. Consultez la page [Fonctionnalités supprimées et obsolètes](https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html).
* Le champ **Code pays** de la ressource Profil a été renommé en **Code pays/zone géographique**.

**Correctifs**

* Correction d&#39;un problème qui empêchait l&#39;envoi du message lors de l&#39;ajout d&#39;un profil de test à un message transactionnel d&#39;email. (CAMP-29854)
* Correction d&#39;un problème qui ralentissait l&#39;envoi des messages à partir d&#39;autres canaux si l&#39;envoi était faible pour un canal lorsque l&#39;envoi des messages à partir de tous les canaux était déclenché simultanément.
* Correction d&#39;un problème en raison duquel le MTA commençait à envoyer des SMS lorsque la connexion au compte externe n&#39;était pas encore établie.
* Correction d&#39;un problème lié à la fréquence d&#39;exécution et à l&#39;heure de début de l&#39;activité Planificateur. (CAMP-30745)
* Correction d&#39;un problème lié à la génération PKEY qui se produisait lors de l&#39;utilisation de ressources de profil étendues. (CAMP-30285)
* Correction d&#39;un problème qui se produisait avec les règles de fatigue basées sur un jour calendaire. (CAMP-30136)
* Correction d&#39;un problème qui se produisait lors de la tentative d&#39;accès à des ressources personnalisées dont les noms se terminaient par &quot;Base&quot;. (CAMP-30109)
* Correction d&#39;un problème qui empêchait l&#39;utilisation d&#39;un appel PATCH pour abonner un profil à un service. (CAMP-29728)
* Correction d&#39;un problème qui endommageait un workflow lors de l&#39;import d&#39;un fichier XML par le biais de l&#39;activité Chargement de fichier. (CAMP-29208 et CAMP-28205)
* Correction d&#39;un problème qui empêchait la génération de liens de cardinalité inversée lors de la liaison de ressources personnalisées. (CAMP-30476)
* Correction d&#39;un problème qui empêchait l&#39;extension des logs de diffusion lors de l&#39;utilisation du code de segment uniquement.
* Correction d&#39;un problème qui entraînait la duplication de lignes lors de l&#39;utilisation de l&#39;activité Transfert de fichier dans les workflows.
* Correction d&#39;un problème qui empêchait l&#39;envoi des rapports planifiés à l&#39;heure choisie.
* Correction d&#39;un problème qui entraînait une différence entre les KPI &quot;A envoyer&quot; et &quot;Envoyés&quot; pour une diffusion In-App dans un workflow.
* Correction d&#39;un problème qui empêchait le fonctionnement du tracking pour un message In-App créé avec du code HTML personnalisé.
* Correction d&#39;un problème qui empêchait l&#39;enregistrement du contenu d&#39;une diffusion In-App lorsqu&#39;il était utilisé dans un workflow.
* Correction d&#39;un problème qui empêchait l&#39;affichage des applications mobiles pour les administrateurs.
* Correction d&#39;un problème qui entraînait l&#39;échec du workflow technique Mise à jour pour la délivrabilité. (CAMP-26387)
* Correction d&#39;un problème qui entraînait une différence entre les profils ciblés lors de la création d&#39;une diffusion In-App et ceux affichés dans le tableau de bord de la diffusion. (CAMP-28722)
* Correction d&#39;un problème lié à l&#39;intégration de Campaign avec Assets Core Service qui empêchait la sélection d&#39;une ressource partagée dans un email.

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
   <td> Disponibilité générale du Concepteur d'email<br /> </td> 
   <td> <p>Le nouveau Concepteur d'email intuitif (anciennement Creative Designer) est passé à la phase de disponibilité générale. Il prend maintenant en charge toutes les fonctionnalités de l'ancien éditeur de contenu, notamment :</p> 
    <ul> 
     <li> Utilisation des <a href="../../integrating/using/adding-target-dynamic-content.md">images dynamiques d'Adobe Target</a> </li> 
     <li> Possibilité de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">récupérer automatiquement du contenu depuis une URL au moment de la préparation</a> </li> 
     <li> <a href="../../designing/using/using-reusable-content.md#content-templates">Modèles de contenu d'usine</a> entièrement compatibles </li> 
    </ul> 
    <p>Pour plus d'informations, consultez la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">vidéo de procédure</a>. Les améliorations et les correctifs sont répertoriés ci-dessous.</p><p>Par conséquent, l’ancien éditeur de contenu d’email est maintenant obsolète. Pour plus d'informations, consultez cette <a href="https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listes des produits dans les emails transactionnels<br /> </td> 
   <td> <p>Vous pouvez maintenant référencer une ou plusieurs collections de produits dans un email transactionnel. Vous pouvez par exemple envoyer automatiquement un email d'abandon de panier répertoriant tous les produits qui étaient dans le panier de l'utilisateur avec une image, le prix et un lien vers chaque produit.</p><p>Pour plus d'informations, consultez la <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">vidéo de procédure</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vue mobile dans le Concepteur d'email<br /> </td> 
   <td> <p>Vous pouvez maintenant basculer vers une vue mobile dédiée lors de l'édition du contenu d'un email. Vous pouvez ainsi affiner le responsive design d'un email en éditant séparément toutes les options de style pour l'affichage mobile, (adapter les marges, réduire la taille des polices, changer de couleur fond, etc.).</p><p> Pour plus d'informations, consultez la <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentation détaillée</a>.</p> </td> 
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

**Améliorations**

* Une nouvelle option de l&#39;activité de chargement de données permet désormais d&#39;appliquer une étape de post-traitement au fichier contenant les enregistrements rejetés (ex. compression au format zip). (CAMP-24521)
* Une nouvelle option de l&#39;activité Mise à jour de données vous permet maintenant de configurer la taille maximale des mises à jour pour les données à télécharger. (CAMP-28400)
* Amélioration de la sélection de l&#39;état des adresses des profils Lors de la sélection d&#39;un pays, la liste déroulante &quot;Etat&quot; est maintenant automatiquement mise à jour avec les valeurs d&#39;état correspondantes. (CAMP-28874)
* Une nouvelle option de l&#39;activité Extraction de fichier empêche désormais la génération d&#39;un fichier si la transition entrante est vide. Ainsi, des fichiers vides ne sont pas créés et téléchargés sur les serveurs SFTP.
* Le rapport Synthèse des diffusions a été amélioré.
* La liste des pays disponibles lors de la définition de l&#39;adresse d&#39;un profil a été enrichie. (CAMP-26707)
* Un message d&#39;erreur s&#39;affiche maintenant lorsque vous essayez d&#39;importer un workflow intégré.

**Concepteur d&#39;email**

* Correction d&#39;un problème qui entraînait l&#39;activation de la fonctionnalité d&#39;entité géographique sur un modèle d&#39;email ou un fragment de contenu créé dans le Concepteur d&#39;email, même si cette fonctionnalité était désactivée dans Adobe Campaign, ce qui rendait le modèle ou le fragment indisponible lors d&#39;une nouvelle tentative d&#39;accès. (CAMP-28174)
* Correction d&#39;un problème qui empêchait l&#39;enregistrement des conditions de contenu dynamique lors de l&#39;édition de contenu dans le Concepteur d&#39;email. (CAMP-27905)
* Correction d&#39;un problème qui entraînait la suppression de la version HTML du contenu de l&#39;email après avoir édité la version en texte brut d&#39;un message et interrompu la synchronisation HTML dans le Concepteur d&#39;email. (CAMP-28507)
* Correction d&#39;un problème qui empêchait l&#39;ouverture de l&#39;interface du Concepteur d&#39;email lors de l&#39;utilisation d&#39;Internet Explorer 11. (CAMP-28273)
* Correction d&#39;un problème qui déformait le rendu des paramètres de style Microsoft Outlook appliqués aux boutons avec le Concepteur d&#39;email.
* Correction d&#39;un problème lié au Concepteur d&#39;email qui rendait éditable l&#39;URL d&#39;un fragment de contenu utilisé dans un email, ce qui n&#39;était pas prévu, le fragment étant verrouillé par défaut.
* Correction d&#39;un problème qui empêchait l&#39;affichage du composant diviseur du Concepteur d&#39;email dans Microsoft Office.
* Correction d&#39;un problème qui entraînait le gel des pages de certains navigateurs Internet lors de l&#39;affichage d&#39;un contenu synchronisé à partir d&#39;AEM à l&#39;aide de l&#39;ancien éditeur de contenu d&#39;email. (CAMP-29068)
* Correction d&#39;une erreur qui se produisait lors d&#39;un clic sur une image dans un email lorsque l&#39;ancien éditeur de contenu d&#39;email était utilisé. (CAMP-30424)
* Correction d&#39;un problème qui empêchait l&#39;affichage des fragments nouvellement créés lors de l&#39;édition d&#39;un email dans le Concepteur d&#39;email. (CAMP-29928)
* Correction d&#39;un problème qui empêchait l&#39;affichage correct du texte des boutons dans les emails créés avec le Concepteur d&#39;email et reçus à l&#39;aide du client webmail Outlook.
* Il est maintenant possible de créer des messages transactionnels de profil à l&#39;aide du Concepteur d&#39;email. (CAMP-28900)
* Correction d&#39;une erreur dans le Concepteur d&#39;email qui rendait le contenu éditable lors de la récupération automatique du contenu d&#39;une URL au moment de la préparation, alors qu&#39;il devait être verrouillé.

**Correctifs**

* Correction d&#39;un problème qui entraînait l&#39;affichage de logs de diffusion incorrects dans les rapports dynamiques. (CAMP-23446)
* Correction d&#39;un problème qui avait un impact sur les chiffres du rapport de synthèse des bounces (CAMP-28703).
* Correction d&#39;un problème lié à l&#39;intégration de Campaign avec Assets Core Service qui empêchait l&#39;affichage des ressources lors de la sélection de l&#39;option **[!UICONTROL Image partagée depuis Adobe Experience Cloud]** dans un email (CAMP-28732).
* Correction d&#39;un problème qui empêchait l&#39;envoi de SMS contenant le caractère &#39;œ&#39; bien que la translittération soit autorisée dans le compte externe SMPP. (CAMP-29041)
* Correction d&#39;un problème qui entraînait l&#39;affichage d&#39;enregistrements en double lors de l&#39;utilisation d&#39;une activité Segmentation dans des workflows. (CAMP-28743)
* Correction d&#39;un problème qui empêchait la suppression de l&#39;une des correspondances de valeurs sur une colonne dans une activité de workflow. (CAMP-28708)
* Correction d&#39;un problème lié à l&#39;activité Transfert de fichiers lors de l&#39;utilisation de caractères génériques avec l&#39;option &quot;Test d&#39;existence de fichier&quot;. (CAMP-28977)
* Correction d&#39;un problème lié à l&#39;activité Transfert de fichiers qui se produisait lors de la mise à jour des paramètres des comptes externes. (CAMP-28894)
* Correction d&#39;un problème lié aux filtres personnalisés dans le requêteur lors de l&#39;utilisation de la condition &quot;Email n&#39;est pas vide&quot;. (CAMP-28741)
* Correction d&#39;un problème qui se produisait lors de l&#39;export de tables de ressources personnalisées contenant plus de 100 000 enregistrements. (CAMP-28150)
* Correction d&#39;un problème qui empêchait la suppression des messages transactionnels liés à des Triggers. (CAMP-28385)
* Suppression des mots de passe qui étaient affichés de manière non sécurisée dans certains logs SMS.
* Correction d&#39;un problème en raison duquel les connexions au simulateur SMPP échouaient en raison d&#39;un mot de passe vide envoyé par Adobe Campaign.
* Correction d&#39;un problème qui empêchait l&#39;envoi de campagnes lorsque les connexions SMS étaient instables.
* Correction d&#39;un problème qui entraînait l&#39;affichage de diffusions supprimées dans les rapports dynamiques.
* Correction d&#39;un problème qui empêchait la récupération des données additionnelles des tables des exclus, des logs de diffusion et du tracking lors de l&#39;utilisation d&#39;une activité Enrichissement dans un workflow.
* Correction d&#39;un problème lié aux demandes de suppression RGPD qui se produisait lors de l&#39;utilisation d&#39;un type de lien &quot;Lien de collection de cardinalité N&quot; et de l&#39;option &quot;La suppression de l&#39;enregistrement cible entraîne la suppression des enregistrements référencés par le lien&quot;.
* Correction d&#39;un problème lié au partage des rapports.
* Correction d&#39;un problème qui entraînait des problèmes de débit lors de l&#39;envoi d&#39;une notification push.
* Correction d&#39;un problème lié à des champs absents dans les fichiers de sortie du courrier.
* Correction d&#39;un problème qui permettait aux utilisateurs de modifier les workflows intégrés.
* Correction d&#39;un problème lors de la création d&#39;une campagne à partir d&#39;un modèle de campagne comprenant un workflow avec une activité d&#39;extraction configurée. (CAMP-29198)
* Correction d&#39;un problème lié à l&#39;activité d&#39;extraction de fichiers qui empêchait d&#39;utiliser la même expression pour plusieurs éléments. (CAMP-29182)
* Dans l&#39;éditeur de requête, correction d&#39;un problème lié à la condition de jointure entre le broadlog et le log de tracking pour rtEvent. (CAMP-28780)
* Correction d&#39;un problème qui empêchait l&#39;enregistrement des modifications apportées à l&#39;option de page d&#39;entrée &quot;Action spécifique&quot;. (CAMP-29422)
* Correction d&#39;un problème qui empêchait d&#39;exporter la payload d&#39;un événement dans un workflow. (CAMP-29029)
* Correction d’un problème qui empêchait l’exclusion des numéros de SMS sur la liste bloquée dans un message SMS. (CAMP-28898)
* Correction d&#39;un problème qui empêchait les fournisseurs SMPP d&#39;être avertis en cas d&#39;erreur lors du traitement des messages entrants. (CAMP-29804)
* Correction d&#39;un problème qui autorisait la suppression de comptes externes avec les diffusions associées. (CAMP-29738)
* Le débit d&#39;envoi a été amélioré et stabilisé pour les messages SMS.
* Correction d&#39;un problème qui empêchait l&#39;utilisation du caractère &quot;~&quot; dans un message SMS. (CAMP-29172)
* Correction d&#39;un problème de diffusions avec l&#39;option d&#39;optimisation de l&#39;heure d&#39;envoi. (CAMP-29231)

