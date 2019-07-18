---
title: Notes de mise à jour 2017
seo-title: Notes de mise à jour 2017
description: Notes de mise à jour 2017
seo-description: Cette page répertorie toutes les versions 2017 d'Adobe Campaign Standard.
page-status-flag: jamais activé
uuid: d 73 f 8186-e 309-441 b -969 d -71 d 0 a 1 c 33 cf 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: référence
topic-tags: campagne-standard-release
discoiquuid: 1 cfd 9 b 3 b -9 b 3 e -4587-9 c 46-b 6 fb 02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Notes de mise à jour 2017{#release-notes}

Vous recherchez une version 2017 spécifique d'Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu.

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d'Adobe Campaign Standard. Si vous recherchez une note de mise à jour plus récente, consultez cette [page](../../rn/using/release-notes.md).

## Version 17.10 - Octobre 2017 {#release-17-10---october-2017}

### Nouvelles fonctionnalités {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Gestion de la fatigue<br /> </td> 
   <td> La gestion de la fatigue permet de créer des règles de fatigue pour gérer la sur-sollicitation des profils en matière de communications. Bien que les règles de fatigue soient faciles à créer, elles sont extrêmement flexibles, avec des fonctionnalités telles que le comptage des messages sur plusieurs canaux (y compris les messages transactionnels), le comptage de diffusions spécifiques uniquement ou l'application de règles à des profils spécifiques.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/fatigue-rules.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Création de contenu : import depuis une URL<br /> </td> 
   <td> L'import depuis une URL permet de récupérer rapidement votre contenu créatif à partir d'un site web afin de créer des emails pour n'importe quelle diffusion. Vous pouvez en outre rationaliser votre processus de création en permettant à des tiers de partager du contenu directement via une URL. Le contenu importé peut être utilisé de manière flexible dans le cadre d'une diffusion unique ou au niveau des modèles, ce qui garantit la cohérence de la marque pour toutes les campagnes associées, qu'il s'agisse de messages basés sur un workflow ou transactionnels, et comprenant des tests A/B ou multivariés. L'import depuis une URL convertit et effectue automatiquement le tracking de tous les liens afin de surveiller les performances des emails via le reporting dynamique.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/importing-content-from-a-url.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches}

#### Plate-forme {#platform}

* Correction d'une erreur qui empêchait la décompression correcte des fichiers compressés volumineux.
* La sécurité a été renforcée dans la gestion des marques. La modification du nom d'une marque et de l'adresse de l'expéditeur est maintenant réservée aux administrateurs techniques Adobe.
* Pour renforcer la sécurité, le contenu généré par l'utilisateur (images, pages miroir, landing pages, etc.) ne peut plus être fourni par le domaine adobe.com. Vous devez maintenant utiliser obligatoirement votre propre domaine pour gérer ces ressources via l'utilisation des marques.
* Correction d'une erreur d'interface lors de l'affichage et du filtrage des activités marketing.
* Correction d'une erreur qui empêchait la mise à jour des champs de date d'abonnement avec un appel d'API REST POST.

#### Emails, SMS et courrier {#emails--sms-messages-and-direct-mail}

* Correction d'une erreur qui empêchait le ciblage d'une audience de type Liste dans un message, ce qui provoquait l'échec de la préparation.
* Des langues manquantes ont été ajoutées aux fonctionnalités de diffusion email multilingue.
* La miniature du contenu, affichée dans le tableau de bord des diffusions, est désormais mise à jour automatiquement lorsque l'utilisateur modifie le contenu et enregistre les modifications.
* Correction d'une erreur liée aux fuseaux horaires qui empêchait l'ouverture d'une diffusion.

#### Notifications push {#push-notifications}

* Lors de la configuration du canal Notification push, la plateforme du provider de push doit être **apns** pour iOS, et **gcm** pour Android.
* Correction d'une erreur qui empêchait l'ajout d'une application mobile iOS dans l'interface d'Adobe Campaign.
* Les notifications push sont désormais prises en charge sur les applications mobiles Android reposant sur GCM et FCM.
* Correction d'une erreur qui empêchait l'enregistrement du contenu lors de la duplication d'un modèle de notification push.
* Il est désormais possible de créer ou de mettre à jour un profil de la base de données Adobe Campaign en réconciliant les données des utilisateurs de l'application mobile.
* Adobe Campaign privilégie maintenant le traitement des notifications push transactionnelles par rapport aux notifications push standard.

#### Rapports {#reports}

* Correction d'une erreur qui empêchait l'affichage des pourcentages de hot clicks dans le contenu de l'email.
* Correction d'une erreur en raison de laquelle la mesure de blacklistage était comptabilisée en tant que hard bounce au lieu de bounce.
* Correction d'un problème qui entraînait l'affichage de comptes négatifs dans les données de synthèse.
* Correction d'une erreur qui entraînait le comptage des profils dans un segment d'âge incorrect.
* Les formules de calcul des soft et hard bounces ont été modifiées.

#### Workflows {#workflows}

* Correction d'un problème lié à l'activité **[!UICONTROL Chargement de fichier]qui entraînait des erreurs après l'ajout et la suppression manuels de colonnes dans l'activité.**
* L'exécution du workflow technique **[!UICONTROL deliverabilityUpdate]est désormais planifiée à 2h00, heure du serveur.**
* Correction d'un problème de sécurité qui permettait l'export d'une liste sans détenir le rôle Export.
* Correction d'une erreur liée à l'activité **[!UICONTROL Réconciliation].**
* Correction d'une erreur liée à l'utilisation des jokers dans l'activité **[!UICONTROL Transfert de fichier].**

#### Profils et audiences {#profiles-and-audiences}

* Correction d'une erreur qui empêchait la prise en compte d'une condition d'une requête dans certains cas spécifiques, ce qui donnait des résultats erronés.
* Correction d'une erreur qui empêchait l'accès aux profils s'ils étaient ciblés dans un message préparé, mais jamais envoyé et arrivé à expiration.

#### Intégrations {#integrations}

* Correction d'une erreur qui empêchait l'affichage et la sélection de certaines Data sources créées pour les triggers.

#### Ressources personnalisées {#custom-resources}

* Correction d'une erreur qui se produisait dans les écrans de type Liste dans lesquels les lignes de ressources personnalisées étaient affichées sans aucune donnée.
* Correction d'une erreur qui empêchait les champs de type booléen avec la valeur 'False' de s'afficher dans les ressources personnalisées.

## Version 17.9 - Septembre 2017 {#release-17-9---september-2017}

### Nouvelles fonctionnalités {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bibliothèque de modèles d'email<br /> </td> 
   <td> Cette version propose dix-huit nouveaux modèles réactifs, proposés dans deux thèmes attrayants : Astro et Feather. Ces modèles personnalisables, indépendants du secteur, peuvent être utilisés immédiatement. Ils comprennent du contenu pour diverses utilisations afin que vos campagnes marketing par email soient conçues de façon attrayante et diffusées plus rapidement et plus efficacement que jamais.<br /> Pour plus d'informations, consultez la <a href="../../start/using/about-templates.md#content-templates">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dynamique avec les données de profil<br /> </td> 
   <td> Le reporting dynamique offre des rapports métier en temps réel entièrement personnalisables. Dans cette version, une amélioration apportée au reporting dynamique offre un accès aux données de profil, ce qui permet d'effectuer des analyses démographiques par dimension de profil (genre, ville, code postal et âge) en plus des données fonctionnelles des campagnes email comme les ouvertures et les clics Avec la même interface intuitive de type glisser-déposer, il n'a jamais été aussi simple de déterminer les performances de votre campagne email pour les segments clients les plus importants.<br /> Pour plus d'informations, consultez la <a href="../../reporting/using/about-dynamic-reports.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscription en masse avec l'origine et la date<br /> </td> 
   <td> Grâce à l'amélioration apportée à l'inscription en masse, vous pouvez désormais stocker les informations d'inscription (origine et date) directement dans la base de données d'Adobe Campaign Standard par le biais de l'activité Services d'inscription d'un workflow.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/subscription-services.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-1}

#### Plate-forme {#platform-1}

* Certains clients doivent pouvoir utiliser un identifiant provenant d'Adobe Campaign Standard, car ils ne gèrent pas de clé unique pour identifier leurs enregistrements. Cet identifiant (**Identifiant ACS**) peut être exporté et utilisé comme clé de réconciliation lors de la mise à jour des données. Pour plus d'informations, consultez la [documentation détaillée](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Le protocole FTP devient obsolète. Vous devez à présent utiliser le protocole SFTP à la place. Pour ne pas bloquer les implémentations existantes, les configurations sur FTP continueront à fonctionner comme avant, mais l'option ne sera plus visible pour les nouvelles activités.

#### Emails, SMS et courrier {#emails--sms-messages-and-direct-mail-1}

* Il est désormais possible de créer des critères d'alerte afin de les utiliser dans les notifications d'alerte de diffusion. Pour plus d'informations, consultez la [documentation détaillée](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Les notifications d'alerte de diffusion sont dotées d'un nouveau design et l'expérience utilisateur du tableau de bord des alertes de diffusion a été améliorée.
* Désormais, lorsqu'un compte externe de routage est désactivé, un avertissement s'affiche dans les diffusions concernées (email, SMS et push) et le bouton **Prévisualiser** est masqué dans celles-ci.
* Résolution d'un problème qui entraînait une erreur lors de l'aperçu d'un test A/B sur le contenu d'un email lorsque le texte dynamique était activé dans l'objet.

#### Messages transactionnels {#transactional-messages}

* Il est désormais possible de définir à quel moment envoyer un message de relance, par exemple 3 jours après l'envoi d'un message transactionnel. Pour plus d'informations, consultez la [documentation détaillée](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Il est désormais possible de définir la date à partir de laquelle les messages transactionnels associés à un événement doivent être envoyés.
* Correction d'un problème qui entraînait une erreur SQL lors de l'exécution d'un workflow contenant un message de relance après la suppression des profils associés aux événements reçus et traités.
* Correction d'une erreur qui empêchait la suppression d'un profil associé à un événement.
* Correction d'une erreur qui empêchait le fonctionnement de la redirection des liens trackés.
* Correction d'une erreur qui empêchait la désactivation du tracking de certains liens dans un email ou un SMS.

#### Rapports {#reports-1}

* Le rapport **Hot clicks** a été amélioré. En outre, il est désormais possible d'afficher les hot clicks selon chaque contenu conditionnel défini dans une diffusion et pour chaque exécution des diffusions récurrentes ou des messages transactionnels. Pour plus d'informations, consultez la [documentation détaillée](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correction d'une erreur qui empêchait la mesure de quarantaine de récupérer les données correctes.
* Une nouvelle période de temps prédéfinie a été ajoutée au widget de calendrier.
* Les [mesures des rapports dynamiques](../../reporting/using/indicator-calculation.md) et les [KPI des campagnes](../../sending/using/confirming-the-send.md) (affichés dans le tableau de bord des messages envoyés) ont été harmonisés pour plus de cohérence.
* Correction d'une erreur qui entraînait l'arrêt du pipeline sur debian 7.

#### Workflows {#workflows-1}

* Correction d'une erreur qui empêchait le fonctionnement de la rétention des fichiers importés.

#### Intégrations {#integrations-1}

* Les eVars et les événements sont maintenant pris en charge pour l'intégration Analytics et Campaign.
* Lors de l'envoi d'un email comportant le contenu du panier abandonné, le paramètre de payload pour les éléments supprimés du panier est désormais facultatif.

#### Profils et audiences {#profiles-and-audiences-1}

* Adobe Campaign contient désormais un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d'information ; il n'a aucune incidence directe sur la facturation. Pour plus d'informations, consultez la [documentation détaillée](../../audiences/using/active-profiles.md).
* Correction d'une erreur qui empêchait l'inscription des profils à un service lors de l'utilisation de l'API Profils et Services.

## Version 17.7 - Juillet 2017 {#release-17-7---july-2017}

### Nouvelles fonctionnalités {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Diffusions email et SMS multilingues<br /> </td> 
   <td> Définissez et exécutez des diffusions email et SMS en une seule vague à partir des préférences linguistiques de vos clients segmentés automatiquement. Créez des rapports sur les performances de chaque diffusion en affinant par langue et par niveau individuel.<br /> De plus en plus d'entreprises doivent relever le défi que constitue la diffusion de contenu dans plusieurs langues à mesure qu'elles se développent au niveau local et international. Ainsi, la rationalisation de la diffusion de messages traduits est au cœur d'une stratégie de communication client efficace pour les entreprises multinationales, les entreprises implantées dans des pays multilingues et les entreprises qui souhaitent personnaliser davantage leur contenu au niveau linguistique, quel que soit le lieu d'implantation de leurs clients. Pour plus d'informations, consultez la <a href="../../channels/using/creating-a-multilingual-email.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifications Adobe Campaign<br /> </td> 
   <td> Recevez des notifications sur les activités système importantes directement dans Adobe Campaign Standard. Par exemple, vous serez averti de l'avancement de vos diffusions en cours ou des erreurs au sein d'un workflow.<br /> Les notifications en temps réel maintiennent les parties concernées informées et permettent aux utilisateurs d'agir immédiatement et directement dans l'application en fonction des notifications d'activité. Pour les équipes, il en résulte une meilleure agilité, une plus grande efficacité et une exécution des campagnes sans accrocs. Pour plus d'informations, consultez la <a href="../../administration/using/sending-internal-notifications.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alertes de diffusion<br /> </td> 
   <td> En plus de visualiser les notifications directement dans Adobe Campaign Standard, Adobe Campaign propose également un système d'alerte par email, qui déclenche l'envoi d'alertes par email aux utilisateurs ou aux membres externes afin de les informer d'activités système importantes. Créez, gérez et recevez des alertes et des tableaux de bord personnalisables pour suivre les performances des diffusions.<br /> Les alertes de diffusion d'Adobe Campaign accroissent l'efficacité en maintenant automatiquement informés tous les utilisateurs actifs d'Adobe Campaign en ce qui concerne le statut d'exécution des diffusions, par email ou par le biais d'un tableau de bord. Pour plus d'informations, consultez la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Identifiant Declared ID crypté dans les sources de données<br /> </td> 
   <td> Envoyez des emails et des SMS sans avoir besoin d'un profil existant dans Campaign à l'aide d'informations de contact cryptées (adresse email ou numéro de téléphone) sous forme d'identifiant Declared ID. Dans la mesure où les identifiants Declared ID cryptés peuvent être décodés par Adobe Campaign Standard, Campaign peut désormais créer des profils marketing lors de la réception d'audiences d'autres solutions Experience Cloud contenant des contacts encore inconnus.<br /> Ciblez des clients et des prospects inconnus en temps réel par email et SMS pour à la fois accroître la fidélité de votre clientèle actuelle et acquérir de nouveaux clients. Tirez pleinement parti des données des cookies propriétaires (depuis Adobe Audience Manager*) une fois les prospects authentifiés et exploitez ces informations dans Adobe Campaign. <br /> *Adobe Audience Manager est requis. Pour plus d'informations, consultez la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Partage des KPI de Campaign vers Analytics<br /> </td> 
   <td> Partagez des données sur les campagnes avec Adobe Analytics afin de comparer les mesures de marketing par email issues de Campaign à d'autres efforts de marketing et de publicité en analysant le comportement de conversion avant et après clic.<br /> Effectuez directement le suivi des performances générales et découvrez des synergies avec des programmes externes dans Analytics. Appliquez les conclusions tirées de cette vue consolidée à vos campagnes ; améliorez ainsi les taux de conversion, de clics publicitaires et d'ouvertures et optimisez votre chiffre d'affaires et les performances globales de la campagne. <br /> Adobe Analytics est requis. Pour plus d'informations, consultez la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal Courrier - Retour à l'expéditeur<br /> </td> 
   <td> Les échanges de fichiers plats avec les opérateurs de services postaux intégrant les informations de retour à l'expéditeur sont désormais pris en charge. Cette amélioration du canal Courrier permet d'exclure les adresses postales correspondantes des communications futures.<br /> Les marketeurs peuvent ainsi être avertis si une adresse est incorrecte, interagir avec le client à travers d'autres canaux ou l'inciter à mettre à jour son adresse postale. Comme ils n'envoient plus de courrier à des adresses incorrectes, les dépenses marketing inutiles sont également réduites. <br /> Le canal Courrier est disponible en tant que canal additionnel. Pour plus d'informations, consultez la <a href="../../channels/using/return-to-sender.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-2}

#### Général {#general}

* Correction d'une erreur qui permettait à n'importe quel utilisateur d'exporter des listes. Désormais, seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Export]peuvent effectuer cette action.**

#### Emails, SMS et courrier {#emails--sms-messages-and-direct-mail-2}

* Correction d'une erreur liée au workflow **updateDeliveryExecInfo** qui définissait l'indicateur **To deliver** sur 0 pour les diffusions SMS.
* Dans les **Paramètres avancés** des propriétés du modèle de diffusion, la liste déroulante **Routage** n'affiche désormais que les comptes externes qui correspondent au type du message du modèle. Par exemple, un modèle de diffusion email affiche uniquement les comptes externes de type email.
* Correction d'une erreur liée à la préférence de format d'email **[!UICONTROL Texte]définie pour les profils de test.**
* Correction d'un problème qui entraînait une erreur Javascript lors de la sélection du fuseau horaire par défaut dans l'écran de sélection de planning d'une diffusion.
* Correction d'une erreur qui empêchait l'affichage des pièges dans les envois.
* Dans l'écran de sélection de modèle de l'assistant de création de diffusion, les modèles de relance et de test A/B sont désormais masqués par défaut. Pour plus d'informations, consultez la [documentation détaillée](../../channels/using/creating-an-email.md).
* Correction d'une erreur qui permettait à n'importe quel utilisateur d'envoyer des diffusions. Désormais, seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Démarrer des diffusions]peuvent effectuer cette action.** Pour plus d'informations, consultez la [documentation détaillée](../../sending/using/confirming-the-send.md).

#### Notifications push {#push-notifications-1}

* Correction d'une erreur liée à l'URL **Point de terminaison de tracking Campaign** qui empêchait le reporting.
* Correction d'une erreur qui empêchait l'affichage du titre des notifications push sur les appareils Android.
* Correction d'une erreur qui empêchait l'affichage d'une notification push sur les appareils iOS lorsque celle-ci ne contenait qu'un titre (et pas de texte dans le corps du message).
* Correction d'une erreur qui forçait le tracking des URL de pièce jointe multimédia dans une diffusion, ce qui empêchait l'incorporation des vidéos et des images dans la diffusion. Le tracking des URL du type mediaAttachmentURL est désormais désactivé par défaut pour les notifications push.

#### Rapports {#reports-2}

* Correction d'une erreur en raison de laquelle les valeurs des graphiques étaient différentes dans les tableaux.
* Correction d'une erreur en raison de laquelle les valeurs des notifications push étaient affichées en tant que valeurs d'email.
* Correction d'une erreur qui indiquait des valeurs comme inconnues lorsqu'une diffusion était créée en dehors d'une campagne.
* Correction d'une erreur en raison de laquelle les données des rapports SMS étaient affichées en tant que données des applications mobiles.

#### Workflows {#workflows-2}

* Vous pouvez désormais filtrer les logs des workflows (période et recherche de texte). Pour plus d'informations, consultez la [documentation détaillée](../../automating/using/executing-a-workflow.md#monitoring).
* Dans les diffusions des workflows, une option est désormais disponible pour désactiver la confirmation avant l'envoi.
* Correction d'une erreur qui vous empêchait de définir une transition sortante dans l'assistant de création de diffusion récurrente.
* Correction d'une erreur qui se produisait lors de l'utilisation d'une activité de requête de workflow basée sur un champ de ressource personnalisée avec une énumération comportant un grand nombre de valeurs.

## Version 17.5 - Mai 2017 {#release-17-5---may-2017}

### Nouvelles fonctionnalités {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Canal Courrier<br /> </td> 
   <td> Reconnectez avec les fondamentaux de la communication grâce au premier canal off-line d'Adobe Campaign. Le canal Courrier vous permet de personnaliser et de générer le fichier requis par les opérateurs de services postaux dans le cadre de vos campagnes cross-canal. Utilisez le canal Courrier pour relancer vos clients et leur proposer une expérience unique qui les conduira vers votre application, site web ou magasin.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-direct-mail.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> Email BCC donne la possibilité de conserver les emails envoyés aux destinataires permettant ainsi à la marque de les archiver. En ajoutant une adresse email en “copie cachée” (BCC en anglais) à tous les emails, les clients Adobe Campaign Standard peuvent conserver une copie exacte de chaque email. Il s'agit d'une obligation juridique courante dans le secteur financier. De plus, cette fonctionnalité s'avère utile pour aider les centres de service client lors de la résolution de conflits en temps réel.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/configuring-email-channel.md#archiving-emails">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-3}

#### Mises à jour de l'interface {#interface-updates}

* Dans la barre supérieure, le lien **[!UICONTROL Planning]** a été supprimé. Il a été remplacé par un lien vers **[!UICONTROL Programmes et Campagnes]** .

#### Emails et SMS {#emails-and-sms-messages}

* Correction d'une erreur qui affichait une couleur incorrecte pour l'état de diffusion **[!UICONTROL Reprise en cours.]** La couleur était grise au lieu d'être bleue.

#### Workflows {#workflows-3}

* Correction d'une erreur qui se produisait lors du changement de l'action à exécuter dans une activité **[!UICONTROL Transfert de fichier].**

#### Rapports {#reports-3}

* Les calculs des indicateurs **[!UICONTROL Spam]** et **Taux de spam]ont été modifiés.[!UICONTROL **
* Les mesures de **[!UICONTROL Rebond]ont été améliorées pour un résultat plus précis.**

#### Notifications push {#push-notifications-2}

* Correction d'une erreur qui vous empêchait de cliquer sur une notification push dans l'historique marketing d'un profil.
* L'utilisation des notifications push dans les workflows a été améliorée.

## Version 17.4 - Avril 2017 {#release-17-4---april-2017}

### Nouvelles fonctionnalités {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Amélioration des fonctionnalités d'édition d'image avec le Creative SDK<br /> </td> 
   <td> Grâce au Creative SDK, vous avez désormais accès à un ensemble complet de fonctionnalités afin d'améliorer vos images directement dans l'éditeur de contenu lors de l'édition des emails ou des landing pages.<br /> Cette fonctionnalité ne nécessite pas l'achat de solutions Creative Cloud supplémentaires.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifications push transactionnelles<br /> </td> 
   <td> Le canal des applications mobiles a été ajouté aux fonctionnalités des messages transactionnels d'Adobe Campaign. Trois canaux sont désormais pris en charge pour les messages transactionnels : email, SMS et notifications push.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/transactional-push-notifications.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifications push récurrentes<br /> </td> 
   <td> Vous pouvez désormais configurer des notifications push récurrentes dans un workflow. Vous pouvez les utiliser dans les cas où les utilisateurs s'attendent à recevoir des mises à jour régulières, comme des rappels hebdomadaires, pour découvrir des nouveaux contenus ou des promotions.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/push-notification-delivery.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Connecteur Amazon Simple Storage Service (S3)<br /> </td> 
   <td> Le connecteur Amazon Simple Storage Service (S3) peut désormais être utilisé pour importer ou exporter des données vers Adobe Campaign. Il peut être configuré dans une activité de workflow. La configuration est réalisée dans un compte externe.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/external-accounts.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Dreamweaver disponible<br /> </td> 
   <td> L'intégration entre Adobe Campaign et Dreamweaver est désormais pleinement opérationnelle. Elle fonctionne avec la dernière version officielle de Dreamweaver (17.0.2).<br /> L'intégration nécessite l'installation de l'extension Adobe Campaign Integration à partir de la page suivante : <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br />. Pour plus d'informations, regardez cette <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vidéo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-4}

#### Plate-forme {#platform-2}

* Résolution d'un problème de consommation de mémoire.

#### Emails et SMS {#emails-and-sms-messages-1}

* Correction d'une erreur suite à laquelle le contenu ne pouvait pas être synchronisé correctement avec les dernières modifications lors de la prévisualisation d'un message.
* Correction d'une erreur qui empêchait la création ou la suppression d'une règle de gestion des emails MX ou de domaine.
* Correction d'une erreur qui vous empêchait d'envoyer des emails avec plusieurs alias.
* Correction d'une erreur qui empêchait l'affichage des logs de diffusion aux adresses pièges dans les envois de la diffusion.
* Résolution d'un problème qui entraînait une erreur lors de l'affichage des URL trackées d'une diffusion dont le contenu ne comportait aucune URL.
* Correction d'une erreur qui empêchait l'application correcte des attributs de taille d'une image dans le message envoyé.

#### Messages transactionnels {#transactional-messages-1}

* Le champ rtEventHistoId n'est plus exposé en tant que champ de personnalisation dans un modèle de message transactionnel.

#### Landing pages {#landing-pages}

* Le filtre **[!UICONTROL par email]utilisé dans les landing pages a été optimisé pour réconcilier les nouveaux abonnés avec les profils de la base de données.**
* Correction d'une erreur qui affichait des entrées de texte libre à la place de cases à cocher lors de l'utilisation de champs booléens dans une configuration de formulaire.
* Correction d'une erreur qui empêchait la génération des miniatures des landing pages.

#### Workflows {#workflows-4}

* Correction d'une erreur d'affichage lors de l'édition d'une activité **[!UICONTROL Fin]** ou **Signal externe](dans Safari uniquement).[!UICONTROL **
* Amélioration du message d'erreur affiché lors de l'édition d'une activité **[!UICONTROL Lecture d'audience]contenant une audience en erreur.**
* Résolution d'un problème qui entraînait une erreur SQL lors de l'exécution d'une activité d'inscription.

#### Intégrations {#integrations-2}

* Données de points ciblés : correction d'une erreur qui se produisait lors du comptage des abonnés.

#### Audiences et requêtes {#audiences-and-queries}

* Correction d'une erreur qui empêchait l'utilisation des agrégats (somme et moyenne) sur une collection dans l'éditeur de requêtes.
* Correction d'une erreur qui empêchait le rechargement de l'éditeur de requêtes après le changement de la ressource du filtre.

#### Rapports {#reports-4}

* Correction d'une erreur qui empêchait le calcul correct des mesures de taux d'ouverture lors de la sélection de plusieurs lignes dans un tableau.
* Correction d'une erreur qui affichait les mesures sous la forme de valeurs entières uniquement. Les mesures peuvent désormais s'afficher avec des décimales.

#### Notifications push {#push-notifications-3}

* Correction d'une erreur en raison de laquelle un message d'erreur n'était pas affiché lors de la création d'une application Android associée à une application mobile n'ayant pas pu être créée sur MCPNS.
* Correction d'une erreur qui permettait à un utilisateur d'ajouter des sons à une notification silencieuse.

## Version 17.2 - Mars 2017 {#release-17-2---march-2017}

### Nouvelles fonctionnalités {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reporting dynamique<br /> </td> 
   <td> Le reporting dynamique offre une nouvelle génération de rapports en temps réel, orientés métier et entièrement personnalisables. Cette fonctionnalité, qui se base sur des tableaux croisés dynamiques visuels et sur des graphiques, vous permet de positionner des variables et des dimensions afin d'analyser l'efficacité de vos campagnes marketing. Le reporting dynamique vous permet également de créer vos propres rapports de gestion et de les sauvegarder pour une utilisation ultérieure.<br /> Pour plus d'informations, consultez la <a href="../../reporting/using/about-dynamic-reports.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Dreamweaver (Labs)<br /> </td> 
   <td> Avec l'intégration d'Adobe Campaign et de Dreamweaver, vous disposez à présent d'un processus intégré pour créer des campagnes email avec des solutions Adobe.<br /> Vous pouvez modifier les emails Adobe Campaign dans Dreamweaver. Le contenu est synchronisé de manière automatique et transparente entre les deux solutions.<br /> Pour la release initiale, l'intégration est disponible en tant que fonctionnalité « Labs » et fonctionne uniquement avec Dreamweaver Pre Release Beta. Pour l'activer, veuillez contacter AC-DW-integration@adobe.com.<br /> Pour plus d'informations, regardez cette <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vidéo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimisation manuelle de l'heure d'envoi<br /> </td> 
   <td> Vous pouvez maintenant définir manuellement une heure d'envoi personnalisée par destinataire au niveau de remise ou à l'aide d'un processus. <br /> Deux nouvelles options sont disponibles : <br /> 
    <ul> 
     <li> Tous les destinataires reçoivent le message avec la prise en compte de leur fuseau horaire. </li> 
     <li> Chaque destinataire reçoit le message à une date et une heure calculées selon une formule. </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../sending/using/optimizing-the-sending-time.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nouvelles fonctionnalités des notifications push<br /> </td> 
   <td> Le canal des notifications push a été enrichi de plusieurs nouvelles fonctionnalités :<br /> 
    <ul> 
     <li> Nouvelle interface de création </li> 
     <li> Notifications silencieuses </li> 
     <li> Push interactif </li> 
     <li> Prise en charge de contenus multimédia </li> 
     <li> Calcul de la taille du message </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../channels/using/about-push-notifications.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : nouvelle activité Signal<br /> </td> 
   <td> Déclenchez un workflow à partir d'un autre workflow grâce à la nouvelle activité <span class="uicontrol">Signal. </span><br /> La possibilité de démarrer un workflow à partir d'un autre vous permet désormais de prendre en charge des parcours client plus complexes. Vous pouvez mieux suivre les parcours client et intervenir en cas de problèmes.<br /> Plusieurs activités de workflow ont été mises à jour :<br /> 
    <ul> 
     <li> Activité <span class="uicontrol">Fin</span> : un nouvel onglet vous permet de spécifier un workflow à déclencher une fois l'exécution de cette activité terminée. </li> 
     <li> Activité <span class="uicontrol">Mise à jour de données</span> : utilisez la nouvelle transition sortante vide pour ajouter une activité <strong>Fin</strong> qui déclenchera un autre workflow. Les transitions sortantes vides ne contiennent pas de données et n'occupent pas d'espace inutilement sur le système </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../automating/using/external-signal.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : nouvelle activité Lecture d'audience<br /> </td> 
   <td> Démarrez votre processus de ciblage avec une audience existante qui peut facilement être sélectionnée et affinée dans une même activité.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/read-audience.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Données de points ciblés<br /> </td> 
   <td> Les données de points ciblés sont une intégration entre Adobe Campaign et Adobe Analytics pour Mobile. Il est possible de collecter des données sur localisations mobiles d'un utilisateur - appelées <strong>points ciblés</strong> - lorsque celui-ci ouvre l'application d'une marque. Celle-ci peut alors utiliser les workflows Adobe Campaign pour envoyer des messages personnalisés en fonction de la localisation de ses clients. Ce canal utilise le SDK de Adobe Mobile Services.<br /> Notez que l'utilisation de cette fonctionnalité requiert Analytics pour Mobile, une solution payante.<br /> Pour plus d'informations, consultez la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API REST<br /> </td> 
   <td> Les ressources liées, à n'importe quel niveau, aux ressources de profils ou de service, sont à présent disponibles dans les API.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-5}

#### Général {#general-1}

* Il est à présent possible d'ajouter des données de profil lors de l'import de logs de diffusion.

#### Emails et SMS {#emails-and-sms-messages-2}

* Correction d'une erreur suite à laquelle l'option **[!UICONTROL Demander une confirmation avant d'envoyer les messages]restait sélectionnée même après avoir été décochée et la diffusion sauvegardée.**
* Correction d'une erreur qui pouvait provoquer la dépublication d'emails transactionnels.
* Correction d'une erreur suite à laquelle le contenu ne pouvait pas être synchronisé correctement avec les dernières modifications avant la prévisualisation d'une diffusion.

#### Landing pages {#landing-pages-1}

* Correction d'une erreur qui empêchait l'édition en cliquant dans le contenu d'une landing page.

#### Workflows {#workflows-5}

* Correction d'une erreur qui pouvait empêcher la lecture de la transition Rejet d'une activité **[!UICONTROL Chargement de fichier].**
* Correction d'une erreur qui empêchait la prise en compte correcte des colonnes échangées lors de la configuration d'une activité **[!UICONTROL Chargement de fichier].**

## Version 17.1 - Janvier 2017 {#release-17-1---january-2017}

### Nouvelles fonctionnalités {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Export des logs pour un reporting externe<br /> </td> 
   <td> Exportez des logs tels que les logs de diffusion et le tracking pour les traiter dans les outils de reporting et de Business Intelligence de votre choix. Vous pouvez utiliser des workflows simples avec des requêtes incrémentales pour automatiser des exports réguliers des nouveaux logs.<br /> En plus de la disponibilité des ressources de log dans le sélecteur de ressources, des améliorations ont été apportées aux activités <a href="../../automating/using/incremental-query.md">Requête incrémentale</a> et <a href="../../automating/using/extract-file.md">Extraction de fichier</a> :<br /> 
    <ul> 
     <li> L'activité <span class="uicontrol">Requête incrémentale</span> permet désormais d'utiliser un champ date pour récupérer des données mises à jour ou nouvelles. Auparavant, tous les résultats des exécutions précédentes étaient automatiquement exclus, même s'ils avaient été mis à jour depuis la dernière exécution. </li> 
     <li> L'activité <span class="uicontrol">Extraction de fichier</span> peut désormais exporter des libellés pour les valeurs d'énumération à la place d'identifiants. </li> 
    </ul> Ces activités sont disponibles pour les administrateurs qui ont un accès à toutes les entités organisationnelles et géographiques.<br /> Pour plus d'informations sur l'export des logs, consultez la <a href="../../automating/using/exporting-logs.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Capacités marketing des messages transactionnels<br /> </td> 
   <td> Les marketeurs peuvent désormais envoyer des messages transactionnels selon les profils marketing des clients. Ils peuvent ainsi :<br /> 
    <ul> 
     <li> appliquer des règles de typologie marketing telles que <span class="uicontrol">Adresse en blackliste</span> ; </li> 
     <li> inclure le lien de désinscription dans les messages ; </li> 
     <li> ajouter les messages transactionnels au reporting de diffusion globale ; </li> 
     <li> utiliser les messages transactionnels dans le parcours client. </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../channels/using/profile-transactional-messages.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API des messages transactionnels<br /> </td> 
   <td> L'API des messages transactionnels est maintenant disponible sur le site <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, ce qui facilite son utilisation et son contrôle :<br /> 
    <ul> 
     <li> Vous pouvez tirer parti des capacités de contrôle et de reporting de la plate-forme adobe.io. </li> 
     <li> L'authentification est désormais effectuée en utilisant l'authentification basée sur les jetons adobe.io plutôt que le blacklistage des adresses IP, ce qui simplifie le processus de sécurité. </li> 
     <li> Toutes les API sont désormais intégrées sur une seule plate-forme, ce qui facilite plus que jamais l'ajout des fonctionnalités de messages transactionnels à votre intégration si vous prenez déjà en charge l'API Profile &amp; Services. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs {#patches-6}

#### Général {#general-2}

* Les options d'**[!UICONTROL Autorisation d'accès]figurent à nouveau dans les propriétés des landing pages.**
* Correction d'une erreur qui était susceptible d'entraîner le rendu d'une ancienne image au lieu de la bonne. Cette erreur se produisait lorsque l'image source avait été mise à jour dans la définition du contenu d'une diffusion ou d'une landing page.
* Correction d'un problème qui empêchait les utilisateurs d'éditer certains champs dans un compte externe SFTP existant.
* Correction de plusieurs problèmes liés à l'interface utilisateur. Par exemple, les utilisateurs peuvent désormais éditer les attributs des profils et enregistrer les modifications sans rencontrer de problème dans l'interface utilisateur.

#### Emails et SMS {#emails-and-sms-messages-3}

* Correction d'une erreur liée aux modèles de diffusion comportant du contenu HTML avec une

#### Notifications push {#push-notifications-4}

* Correction d'une erreur qui était susceptible d'empêcher une publication (postback) depuis une application sur le serveur Adobe Campaign.
* Correction d'une erreur qui était susceptible d'empêcher la prise en compte de **[!UICONTROL Jouer un son]** et de **Champs personnalisés]pour Android.[!UICONTROL **
* Correction d'une erreur qui était susceptible d'entraîner l'ajout d'un caractère d'échappement supplémentaire aux caractères Unicode utilisés pour les emojis.
* Lorsque le jeton d'enregistrement d'un abonné devient blacklisté, le statut correspondant est désormais mis immédiatement à jour dans la liste des abonnés de l'application, dans Adobe Campaign.

#### Workflows {#workflows-6}

* Correction d'une erreur qui était susceptible d'empêcher les prévisualisations des requêtes sur les ressources d'événement (rtEvent, par exemple).
* Le fichier de rejets généré par une activité **[!UICONTROL Chargement de fichier]peut désormais être récupéré dans sa transition sortante et traité dans l'activité suivante.** Par exemple, transférez le fichier de rejets via un serveur SFTP à l'aide d'une activité **[!UICONTROL Transfert de fichier]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Les activités Planificateur]** ne peuvent plus être définies pour exécuter un workflow plusieurs fois toutes les 10 minutes.
* Correction d'une erreur qui était susceptible d'empêcher le bon fonctionnement de l'option **[!UICONTROL Utiliser uniquement les données additionnelles communes]** dans une activité **Union[!UICONTROL .]**

#### Intégrations {#integrations-3}

* Correction d'un problème qui était susceptible d'entraîner une erreur lors du déploiement d'un déclenchement d'événement dans Adobe Campaign. Cette erreur se produisait lorsque les métadonnées "Probabilité de retour avant 30 jours" avait été ajoutées au trigger Abandon dans Adobe Marketing Cloud.
* Correction d'une erreur qui était susceptible d'entraîner l'effacement du champ Dimension cible par un workflow technique lors de l'import des audiences depuis People core service. Les requêtes suivantes ne pouvaient pas récupérer les audiences importées.
* Correction d'une erreur qui était susceptible d'entraîner l'échec d'une activité **[!UICONTROL Sauvegarde d'audience]** d'un workflow lorsque l'option **Partager dans Adobe Marketing Cloud]était cochée.[!UICONTROL **

