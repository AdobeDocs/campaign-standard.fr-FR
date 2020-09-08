---
title: Notes de mise à jour 2017
description: Cette page répertorie toutes les versions 2017 d'Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '4688'
ht-degree: 98%

---


# Notes de mise à jour 2017{#release-notes}

Vous recherchez une version 2017 spécifique d&#39;Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu.

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d&#39;Adobe Campaign Standard. Si vous recherchez une note de mise à jour plus récente, consultez cette [page](../../rn/using/release-notes.md).

## Version 17.10 - Octobre 2017        {#release-17-10---october-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Gestion de la fatigue<br /> </td> 
   <td> La gestion de la fatigue permet de créer des règles de fatigue pour gérer la sur-sollicitation des profils en matière de communications. Bien que les règles de fatigue soient faciles à créer, elles sont extrêmement flexibles, avec des fonctionnalités telles que le comptage des messages sur plusieurs canaux (y compris les messages transactionnels), le comptage de diffusions spécifiques uniquement ou l'application de règles à des profils spécifiques.<br /> Pour plus d'informations, consultez la <a href="../../sending/using/fatigue-rules.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Création de contenu : import depuis une URL<br /> </td> 
   <td> L'import depuis une URL permet de récupérer rapidement votre contenu créatif à partir d'un site web afin de créer des emails pour n'importe quelle diffusion. Vous pouvez en outre rationaliser votre processus de création en permettant à des tiers de partager du contenu directement via une URL. Le contenu importé peut être utilisé de manière flexible dans le cadre d'une diffusion unique ou au niveau des modèles, ce qui garantit la cohérence de la marque pour toutes les campagnes associées, qu'il s'agisse de messages basés sur un workflow ou transactionnels, et comprenant des tests A/B ou multivariés. L'import depuis une URL convertit et effectue automatiquement le tracking de tous les liens afin de surveiller les performances des emails via le reporting dynamique.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Plate-forme_

* Correction d&#39;une erreur qui empêchait la décompression correcte des fichiers compressés volumineux.
* La sécurité a été renforcée dans la gestion des marques. La modification du nom d&#39;une marque et de l&#39;adresse de l&#39;expéditeur est maintenant réservée aux administrateurs techniques Adobe.
* Pour renforcer la sécurité, le contenu généré par l&#39;utilisateur (images, pages miroir, landing pages, etc.) ne peut plus être fourni par le domaine adobe.com. Vous devez maintenant utiliser obligatoirement votre propre domaine pour gérer ces ressources via l&#39;utilisation des marques.
* Correction d&#39;une erreur d&#39;interface lors de l&#39;affichage et du filtrage des activités marketing.
* Correction d&#39;une erreur qui empêchait la mise à jour des champs de date d&#39;abonnement avec un appel d&#39;API REST POST.

_Emails, SMS et courrier_

* Correction d&#39;une erreur qui empêchait le ciblage d&#39;une audience de type Liste dans un message, ce qui provoquait l&#39;échec de la préparation.
* Des langues manquantes ont été ajoutées aux fonctionnalités de diffusion email multilingue.
* La miniature du contenu, affichée dans le tableau de bord des diffusions, est désormais mise à jour automatiquement lorsque l&#39;utilisateur modifie le contenu et enregistre les modifications.
* Correction d&#39;une erreur liée aux fuseaux horaires qui empêchait l&#39;ouverture d&#39;une diffusion.

_Notifications push_

* Lors de la configuration du canal Notification push, la plateforme du provider de push doit être **apns** pour iOS, et **gcm** pour Android.
* Correction d&#39;une erreur qui empêchait l&#39;ajout d&#39;une application mobile iOS dans l&#39;interface d&#39;Adobe Campaign.
* Les notifications push sont désormais prises en charge sur les applications mobiles Android reposant sur GCM et FCM.
* Correction d&#39;une erreur qui empêchait l&#39;enregistrement du contenu lors de la duplication d&#39;un modèle de notification push.
* Il est désormais possible de créer ou de mettre à jour un profil de la base de données Adobe Campaign en réconciliant les données des utilisateurs de l&#39;application mobile.
* Adobe Campaign privilégie maintenant le traitement des notifications push transactionnelles par rapport aux notifications push standard.

_Rapports_

* Correction d&#39;une erreur qui empêchait l&#39;affichage des pourcentages de hot clicks dans le contenu de l&#39;email.
* Correction d’un problème lié à la mesure de liste bloquée qui était comptabilisé comme un rebond dur au lieu d’un rebond.
* Correction d&#39;un problème qui entraînait l&#39;affichage de comptes négatifs dans les données de synthèse.
* Correction d&#39;une erreur qui entraînait le comptage des profils dans un segment d&#39;âge incorrect.
* Les formules de calcul des soft et hard bounces ont été modifiées.

_Workflows_

* Correction d&#39;un problème lié à l&#39;activité **[!UICONTROL Chargement de fichier]** qui entraînait des erreurs après l&#39;ajout et la suppression manuels de colonnes dans l&#39;activité.
* L&#39;exécution du workflow technique **[!UICONTROL deliverabilityUpdate]** est désormais planifiée à 2h00, heure du serveur.
* Correction d&#39;un problème de sécurité qui permettait l&#39;export d&#39;une liste sans détenir le rôle Export.
* Correction d&#39;une erreur liée à l&#39;activité **[!UICONTROL Réconciliation]**.
* Correction d&#39;une erreur liée à l&#39;utilisation des jokers dans l&#39;activité **[!UICONTROL Transfert de fichier]**.

_Profils et audiences_

* Correction d&#39;une erreur qui empêchait la prise en compte d&#39;une condition d&#39;une requête dans certains cas spécifiques, ce qui donnait des résultats erronés.
* Correction d&#39;une erreur qui empêchait l&#39;accès aux profils s&#39;ils étaient ciblés dans un message préparé, mais jamais envoyé et arrivé à expiration.

_Intégrations_

* Correction d&#39;une erreur qui empêchait l&#39;affichage et la sélection de certaines Data sources créées pour les Triggers.

_Ressources personnalisées_

* Correction d&#39;une erreur qui se produisait dans les écrans de type Liste dans lesquels les lignes de ressources personnalisées étaient affichées sans aucune donnée.
* Correction d&#39;une erreur qui empêchait les champs de type booléen avec la valeur &#39;False&#39; de s&#39;afficher dans les ressources personnalisées.

## Version 17.9 - Septembre 2017 {#release-17-9---september-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bibliothèque de modèles d'email<br /> </td> 
   <td> Cette version propose dix-huit nouveaux modèles réactifs, proposés dans deux thèmes attrayants : Astro et Feather. Ces modèles personnalisables, indépendants du secteur, peuvent être utilisés immédiatement. Ils comprennent du contenu pour diverses utilisations afin que vos campagnes marketing par email soient conçues de façon attrayante et diffusées plus rapidement et plus efficacement que jamais.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/using-reusable-content.md#content-templates">documentation détaillée</a>.<br /> </td> 
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

**Correctifs**

_Plate-forme_

* Certains clients doivent pouvoir utiliser un identifiant provenant d&#39;Adobe Campaign Standard, car ils ne gèrent pas de clé unique pour identifier leurs enregistrements. Cet identifiant (**Identifiant ACS**) peut être exporté et utilisé comme clé de réconciliation lors de la mise à jour des données. Pour plus d&#39;informations, consultez la [documentation détaillée](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Le protocole FTP devient obsolète. Vous devez à présent utiliser le protocole SFTP à la place. Pour ne pas bloquer les implémentations existantes, les configurations sur FTP continueront à fonctionner comme avant, mais l&#39;option ne sera plus visible pour les nouvelles activités.

_Emails, SMS et courrier_

* Il est désormais possible de créer des critères d&#39;alerte afin de les utiliser dans les notifications d&#39;alerte de diffusion. Pour plus d&#39;informations, consultez la [documentation détaillée](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Les notifications d&#39;alerte de diffusion sont dotées d&#39;un nouveau design et l&#39;expérience utilisateur du tableau de bord des alertes de diffusion a été améliorée.
* Désormais, lorsqu&#39;un compte externe de routage est désactivé, un avertissement s&#39;affiche dans les diffusions concernées (email, SMS et push) et le bouton **Prévisualiser** est masqué dans celles-ci.
* Résolution d&#39;un problème qui entraînait une erreur lors de l&#39;aperçu d&#39;un test A/B sur le contenu d&#39;un email lorsque le texte dynamique était activé dans l&#39;objet.

_Messages transactionnels_

* Il est désormais possible de définir à quel moment envoyer un message de relance, par exemple 3 jours après l&#39;envoi d&#39;un message transactionnel. Pour plus d&#39;informations, consultez la [documentation détaillée](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Il est désormais possible de définir la date à partir de laquelle les messages transactionnels associés à un événement doivent être envoyés.
* Correction d&#39;un problème qui entraînait une erreur SQL lors de l&#39;exécution d&#39;un workflow contenant un message de relance après la suppression des profils associés aux événements reçus et traités.
* Correction d&#39;une erreur qui empêchait la suppression d&#39;un profil associé à un événement.
* Correction d&#39;une erreur qui empêchait le fonctionnement de la redirection des liens trackés.
* Correction d&#39;une erreur qui empêchait la désactivation du tracking de certains liens dans un email ou un SMS.

_Rapports_

* Le rapport **Hot clicks** a été amélioré. En outre, il est désormais possible d&#39;afficher les hot clicks selon chaque contenu conditionnel défini dans une diffusion et pour chaque exécution des diffusions récurrentes ou des messages transactionnels. Pour plus d&#39;informations, consultez la [documentation détaillée](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Correction d&#39;une erreur qui empêchait la mesure de quarantaine de récupérer les données correctes.
* Une nouvelle période de temps prédéfinie a été ajoutée au widget de calendrier.
* Les [mesures des rapports dynamiques](../../reporting/using/indicator-calculation.md) et les [KPI des campagnes](../../sending/using/confirming-the-send.md) (affichés dans le tableau de bord des messages envoyés) ont été harmonisés pour plus de cohérence.
* Correction d&#39;une erreur qui entraînait l&#39;arrêt du pipeline sur debian 7.

_Workflows_

* Correction d&#39;une erreur qui empêchait le fonctionnement de la rétention des fichiers importés.

_Intégrations_

* Les eVars et les événements sont maintenant pris en charge pour l&#39;intégration Analytics et Campaign.
* Lors de l&#39;envoi d&#39;un email comportant le contenu du panier abandonné, le paramètre de payload pour les éléments supprimés du panier est désormais facultatif.

_Profils et audiences_

* Adobe Campaign contient désormais un rapport qui indique le nombre de profils actifs. Ce rapport est fourni uniquement à titre d&#39;information ; il n&#39;a aucune incidence directe sur la facturation. Pour plus d&#39;informations, consultez la [documentation détaillée](../../audiences/using/active-profiles.md).
* Correction d&#39;une erreur qui empêchait l&#39;inscription des profils à un service lors de l&#39;utilisation de l&#39;API Profils et Services.

## Version 17.7 - Juillet 2017        {#release-17-7---july-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
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

**Correctifs**

_Général_

* Correction d&#39;une erreur qui permettait à n&#39;importe quel utilisateur d&#39;exporter des listes. Désormais, seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Export]** peuvent effectuer cette action.

_Emails, SMS et courrier_

* Correction d&#39;une erreur liée au workflow **updateDeliveryExecInfo** qui définissait l&#39;indicateur **To deliver** sur 0 pour les diffusions SMS.
* Dans les **Paramètres avancés** des propriétés du modèle de diffusion, la liste déroulante **Routage** n&#39;affiche désormais que les comptes externes qui correspondent au type du message du modèle. Par exemple, un modèle de diffusion email affiche uniquement les comptes externes de type email.
* Correction d&#39;une erreur liée à la préférence de format d&#39;email **[!UICONTROL Texte]** définie pour les profils de test.
* Correction d&#39;un problème qui entraînait une erreur Javascript lors de la sélection du fuseau horaire par défaut dans l&#39;écran de sélection de planning d&#39;une diffusion.
* Correction d&#39;une erreur qui empêchait l&#39;affichage des pièges dans les envois.
* Dans l&#39;écran de sélection de modèle de l&#39;assistant de création de diffusion, les modèles de relance et de test A/B sont désormais masqués par défaut. Pour plus d&#39;informations, consultez la [documentation détaillée](../../channels/using/creating-an-email.md).
* Correction d&#39;une erreur qui permettait à n&#39;importe quel utilisateur d&#39;envoyer des diffusions. Désormais, seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Démarrer des diffusions]** peuvent effectuer cette action. Pour plus d&#39;informations, consultez la [documentation détaillée](../../sending/using/confirming-the-send.md).

_Notifications push_

* Correction d&#39;une erreur liée à l&#39;URL **Point de terminaison de tracking Campaign** qui empêchait le reporting.
* Correction d&#39;une erreur qui empêchait l&#39;affichage du titre des notifications push sur les appareils Android.
* Correction d&#39;une erreur qui empêchait l&#39;affichage d&#39;une notification push sur les appareils iOS lorsque celle-ci ne contenait qu&#39;un titre (et pas de texte dans le corps du message).
* Correction d&#39;une erreur qui forçait le tracking des URL de pièce jointe multimédia dans une diffusion, ce qui empêchait l&#39;incorporation des vidéos et des images dans la diffusion. Le tracking des URL du type mediaAttachmentURL est désormais désactivé par défaut pour les notifications push.

_Rapports_

* Correction d&#39;une erreur en raison de laquelle les valeurs des graphiques étaient différentes dans les tableaux.
* Correction d&#39;une erreur en raison de laquelle les valeurs des notifications push étaient affichées en tant que valeurs d&#39;email.
* Correction d&#39;une erreur qui indiquait des valeurs comme inconnues lorsqu&#39;une diffusion était créée en dehors d&#39;une campagne.
* Correction d&#39;une erreur en raison de laquelle les données des rapports SMS étaient affichées en tant que données des applications mobiles.

_Workflows_

* Vous pouvez désormais filtrer les logs des workflows (période et recherche de texte). Pour plus d&#39;informations, consultez la [documentation détaillée](../../automating/using/monitoring-workflow-execution.md).
* Dans les diffusions des workflows, une option est désormais disponible pour désactiver la confirmation avant l&#39;envoi.
* Correction d&#39;une erreur qui vous empêchait de définir une transition sortante dans l&#39;assistant de création de diffusion récurrente.
* Correction d&#39;une erreur qui se produisait lors de l&#39;utilisation d&#39;une activité de requête de workflow basée sur un champ de ressource personnalisée avec une énumération comportant un grand nombre de valeurs.

## Version 17.5 - Mai 2017        {#release-17-5---may-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
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
   <td> Email BCC donne la possibilité de conserver les emails envoyés aux destinataires permettant ainsi à la marque de les archiver. En ajoutant une adresse email en “copie cachée” (BCC en anglais) à tous les emails, les clients Adobe Campaign Standard peuvent conserver une copie exacte de chaque email. Il s'agit d'une obligation juridique courante dans le secteur financier. De plus, cette fonctionnalité s'avère utile pour aider les centres de service client lors de la résolution de conflits en temps réel.<br /> Pour plus d'informations, consultez la <a href="../../sending/using/archiving.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Mises à jour de l&#39;interface_

* Dans la barre supérieure, le lien **[!UICONTROL Planning]** a été supprimé. Il a été remplacé par un lien vers **[!UICONTROL Programmes et Campagnes]** .

_Emails et SMS_

* Correction d&#39;une erreur qui affichait une couleur incorrecte pour l&#39;état de diffusion **[!UICONTROL Reprise en cours]**. La couleur était grise au lieu d&#39;être bleue.

_Workflows_

* Correction d&#39;une erreur qui se produisait lors du changement de l&#39;action à exécuter dans une activité **[!UICONTROL Transfert de fichier]**.

_Rapports_

* Les calculs des indicateurs **[!UICONTROL Spam]** et **[!UICONTROL Taux de spam]** ont été modifiés.
* Les mesures de **[!UICONTROL Rebond]** ont été améliorées pour un résultat plus précis.

_Notifications push_

* Correction d&#39;une erreur qui vous empêchait de cliquer sur une notification push dans l&#39;historique marketing d&#39;un profil.
* L&#39;utilisation des notifications push dans les workflows a été améliorée.

## Version 17.4 - Avril 2017        {#release-17-4---april-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Des capacités d'édition d'images enrichies grâce au Creative SDK<br /> </td> 
   <td> Grâce au Creative SDK, vous avez désormais accès à un ensemble complet de fonctionnalités afin d'améliorer vos images directement dans l'éditeur de contenu lors de l'édition des emails ou des landing pages.<br /> Cette fonctionnalité ne nécessite pas l'achat de solutions Creative Cloud supplémentaires.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentation détaillée</a>.<br /> </td> 
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
   <td> Le connecteur Amazon Simple Storage Service (S3) peut désormais être utilisé pour importer ou exporter des données vers Adobe Campaign. Il peut être configuré dans une activité de workflow. La configuration est réalisée dans un compte externe.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/external-accounts.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration de Dreamweaver en ligne<br /> </td> 
   <td> L'intégration entre Adobe Campaign et Dreamweaver est désormais pleinement opérationnelle. Elle fonctionne avec la dernière version officielle de Dreamweaver (17.0.2).<br /> L'intégration nécessite l'installation de l'extension Adobe Campaign Integration à partir de la page suivante : <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_addon </a><br />. Pour plus d'informations, regardez cette <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">vidéo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Plate-forme_

* Résolution d&#39;un problème de consommation de mémoire.

_Emails et SMS_

* Correction d&#39;une erreur suite à laquelle le contenu ne pouvait pas être synchronisé correctement avec les dernières modifications lors de la prévisualisation d&#39;un message.
* Correction d&#39;une erreur qui empêchait la création ou la suppression d&#39;une règle de gestion des emails MX ou de domaine.
* Correction d&#39;une erreur qui vous empêchait d&#39;envoyer des emails avec plusieurs alias.
* Correction d&#39;une erreur qui empêchait l&#39;affichage des logs de diffusion aux adresses pièges dans les envois de la diffusion.
* Résolution d&#39;un problème qui entraînait une erreur lors de l&#39;affichage des URL trackées d&#39;une diffusion dont le contenu ne comportait aucune URL.
* Correction d&#39;une erreur qui empêchait l&#39;application correcte des attributs de taille d&#39;une image dans le message envoyé.

_Messages transactionnels_

* Le champ rtEventHistoId n&#39;est plus exposé en tant que champ de personnalisation dans un modèle de message transactionnel.

_Landing pages_

* Le filtre **[!UICONTROL par email]** utilisé dans les landing pages a été optimisé pour réconcilier les nouveaux abonnés avec les profils de la base de données.
* Correction d&#39;une erreur qui affichait des entrées de texte libre à la place de cases à cocher lors de l&#39;utilisation de champs booléens dans une configuration de formulaire.
* Correction d&#39;une erreur qui empêchait la génération des miniatures des landing pages.

_Workflows_

* Correction d&#39;une erreur d&#39;affichage lors de l&#39;édition d&#39;une activité **[!UICONTROL Fin]** ou **[!UICONTROL Signal externe]** (dans Safari uniquement).
* Amélioration du message d&#39;erreur affiché lors de l&#39;édition d&#39;une activité **[!UICONTROL Lecture d&#39;audience]** contenant une audience en erreur.
* Résolution d&#39;un problème qui entraînait une erreur SQL lors de l&#39;exécution d&#39;une activité d&#39;abonnement.

_Intégrations_

* Données de points ciblés : correction d&#39;une erreur qui se produisait lors du comptage des abonnés de localisation.

_Audiences et requêtes_

* Correction d&#39;une erreur qui empêchait l&#39;utilisation des agrégats (somme et moyenne) sur une collection dans l&#39;éditeur de requêtes.
* Correction d&#39;une erreur qui empêchait le rechargement de l&#39;éditeur de requêtes après le changement de la ressource du filtre.

_Rapports_

* Correction d&#39;une erreur qui empêchait le calcul correct des mesures de taux d&#39;ouverture lors de la sélection de plusieurs lignes dans un tableau.
* Correction d&#39;une erreur qui affichait les mesures sous la forme de valeurs entières uniquement. Les mesures peuvent désormais s&#39;afficher avec des décimales.

_Notifications push_

* Correction d&#39;une erreur en raison de laquelle un message d&#39;erreur n&#39;était pas affiché lors de la création d&#39;une application Android associée à une application mobile n&#39;ayant pas pu être créée sur MCPNS.
* Correction d&#39;une erreur qui permettait à un utilisateur d&#39;ajouter des sons à une notification silencieuse.

## Version 17.2 - Mars 2017        {#release-17-2---march-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
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
   <td> Avec l'intégration d'Adobe Campaign et de Dreamweaver, vous disposez à présent d'un processus intégré pour créer des campagnes email avec des solutions Adobe.<br /> Vous pouvez modifier les emails Adobe Campaign dans Dreamweaver. Le contenu est synchronisé de manière automatique et transparente entre les deux solutions.<br /> Pour la release initiale, l'intégration est disponible en tant que fonctionnalité « Labs » et fonctionne uniquement avec Dreamweaver Pre Release Beta. Pour l'activer, veuillez contacter AC-DW-integration@adobe.com.<br /> Pour plus d'informations, regardez cette <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">vidéo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimisation manuelle de l'heure d'envoi<br /> </td> 
   <td> Vous pouvez à présent définir une heure d'envoi personnalisée par destinataire – au niveau de la diffusion ou via un workflow. <br /> Deux nouvelles options sont disponibles : <br /> 
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
   <td> Données Points of Interest<br /> </td> 
   <td> Les données de points ciblés sont une intégration entre Adobe Campaign et Adobe Analytics pour Mobile. Il est possible de collecter des données sur localisations mobiles d'un utilisateur - appelées <strong>points ciblés</strong> - lorsque celui-ci ouvre l'application d'une marque. Celle-ci peut alors utiliser les workflows Adobe Campaign pour envoyer des messages personnalisés en fonction de la localisation de ses clients. Ce canal utilise le SDK de Adobe Mobile Services.<br /> Notez que l'utilisation de cette fonctionnalité requiert Analytics pour Mobile, une solution payante.<br /> Pour plus d'informations, consultez la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API REST<br /> </td> 
   <td> Les ressources liées, à n'importe quel niveau, aux ressources de profils ou de service, sont à présent disponibles dans les API.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Il est à présent possible d&#39;ajouter des données de profil lors de l&#39;import de logs de diffusion.

_Emails et SMS_

* Correction d&#39;une erreur suite à laquelle l&#39;option **[!UICONTROL Demander une confirmation avant d&#39;envoyer les messages]** restait sélectionnée même après avoir été décochée et la diffusion sauvegardée.
* Correction d&#39;une erreur qui pouvait provoquer la dépublication d&#39;emails transactionnels.
* Correction d&#39;une erreur suite à laquelle le contenu ne pouvait pas être synchronisé correctement avec les dernières modifications avant la prévisualisation d&#39;une diffusion.

_Landing pages_

* Correction d&#39;une erreur qui empêchait l&#39;édition en cliquant dans le contenu d&#39;une landing page.

_Workflows_

* Correction d&#39;une erreur qui pouvait empêcher la lecture de la transition Rejet d&#39;une activité **[!UICONTROL Chargement de fichier]**.
* Correction d&#39;une erreur qui empêchait la prise en compte correcte des colonnes échangées lors de la configuration d&#39;une activité **[!UICONTROL Chargement de fichier]**.

## Version 17.1 - Janvier 2017 {#release-17-1---january-2017}

**Nouvelles fonctionnalités**

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalités<br /> </th> 
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
     <li> Apply marketing typology rules such as <span class="uicontrol">Denylisted address</span> . </li> 
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
     <li> L’authentification est désormais effectuée à l’aide de l’authentification basée sur les jetons adobe.io plutôt que de l’liste autorisée IP, ce qui simplifie le processus de sécurité. </li> 
     <li> Toutes les API sont désormais intégrées sur une seule plate-forme, ce qui facilite plus que jamais l'ajout des fonctionnalités de messages transactionnels à votre intégration si vous prenez déjà en charge l'API Profile &amp; Services. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Les options d&#39;**[!UICONTROL Autorisation d&#39;accès]** figurent à nouveau dans les propriétés des landing pages.
* Correction d&#39;une erreur qui était susceptible d&#39;entraîner le rendu d&#39;une ancienne image au lieu de la bonne. Cette erreur se produisait lorsque l&#39;image source avait été mise à jour dans la définition du contenu d&#39;une diffusion ou d&#39;une landing page.
* Correction d&#39;un problème qui empêchait les utilisateurs d&#39;éditer certains champs dans un compte externe SFTP existant.
* Correction de plusieurs problèmes liés à l&#39;interface utilisateur. Par exemple, les utilisateurs peuvent désormais éditer les attributs des profils et enregistrer les modifications sans rencontrer de problème dans l&#39;interface utilisateur.

_Emails et SMS_

* Correction d&#39;une erreur liée aux modèles de diffusion comportant du contenu HTML avec une

_Notifications push_

* Correction d&#39;une erreur qui était susceptible d&#39;empêcher une publication (postback) depuis une application sur le serveur Adobe Campaign.
* Correction d&#39;une erreur qui était susceptible d&#39;empêcher la prise en compte de **[!UICONTROL Jouer un son]** et de **[!UICONTROL Champs personnalisés]** pour Android.
* Correction d&#39;une erreur qui était susceptible d&#39;entraîner l&#39;ajout d&#39;un caractère d&#39;échappement supplémentaire aux caractères Unicode utilisés pour les emojis.
* Lorsqu’un jeton d’enregistrement d’un abonné est placé sur la liste bloquée, l’état correspondant est maintenant immédiatement mis à jour dans la liste de l’application relative aux abonnés de Adobe Campaign.

_Workflows_

* Correction d&#39;une erreur qui était susceptible d&#39;empêcher les prévisualisations des requêtes sur les ressources d&#39;événement (rtEvent, par exemple).
* Le fichier de rejets généré par une activité **[!UICONTROL Chargement de fichier]** peut désormais être récupéré dans sa transition sortante et traité dans l&#39;activité suivante. Par exemple, transférez le fichier de rejets via un serveur SFTP à l&#39;aide d&#39;une activité **[!UICONTROL Transfert de fichier]** .
* Correction d&#39;une erreur qui était susceptible d&#39;empêcher un utilisateur de limiter la population d&#39;un segment lorsque **[!UICONTROL Ressource temporaire]** était sélectionnée dans l&#39;onglet **[!UICONTROL Général]** de l&#39;activité **[!UICONTROL Segmentation]** .
* **[!UICONTROL Les activités Planificateur]** ne peuvent plus être définies pour exécuter un workflow plusieurs fois toutes les 10 minutes.
* Correction d&#39;une erreur qui était susceptible d&#39;empêcher le bon fonctionnement de l&#39;option **[!UICONTROL Utiliser uniquement les données additionnelles communes]** dans une activité **[!UICONTROL Union]**.

_Intégrations_

* Correction d&#39;un problème qui était susceptible d&#39;entraîner une erreur lors du déploiement d&#39;un déclenchement d&#39;événement dans Adobe Campaign. Cette erreur se produisait lorsque les métadonnées &quot;Probabilité de retour avant 30 jours&quot; avait été ajoutées au trigger Abandon dans Adobe Experience Cloud.
* Correction d&#39;une erreur qui était susceptible d&#39;entraîner l&#39;effacement du champ Dimension cible par un workflow technique lors de l&#39;import des audiences depuis People core service. Les requêtes suivantes ne pouvaient pas récupérer les audiences importées.
* Correction d&#39;une erreur qui était susceptible d&#39;entraîner l&#39;échec d&#39;une activité **[!UICONTROL Sauvegarde d&#39;audience]** d&#39;un workflow lorsque l&#39;option **[!UICONTROL Partager dans Adobe Experience Cloud]** était cochée.

