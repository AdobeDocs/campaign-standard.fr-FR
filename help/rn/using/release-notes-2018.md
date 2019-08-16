---
title: Notes de mise à jour 2018
seo-title: Notes de mise à jour 2018
description: Notes de mise à jour 2018
seo-description: Cette page répertorie toutes les versions 2018 d'Adobe Campaign Standard.
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
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Notes de mise à jour 2018{#release-notes}

Vous recherchez une version 2018 spécifique d'Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu.

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d'Adobe Campaign Standard. Si vous recherchez une note de mise à jour plus récente, consultez cette [page](../../rn/using/release-notes.md).

## Version 18.9 - Septembre 2018 {#release-18-9---september-2018}

### Nouveautés {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Messagerie in-app (version bêta)<br /> </td> 
   <td> La messagerie in-app permet d'interagir plus efficacement avec les utilisateurs d'application mobile en offrant une interaction contextuelle et en permettant d'atteindre les utilisateurs susceptibles de ne pas s'être abonnés aux notifications push. Utilisez la messagerie in-app avec les notifications push pour créer une expérience hautement personnalisée et pertinente. Vous obtiendrez ainsi une meilleure conversion et rétention des utilisateurs de votre application.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration d'Adobe Launch pour les applications mobiles (version bêta)<br /> </td> 
   <td> L'intégration d'Adobe Launch avec Adobe Campaign simplifie et automatise maintenant le processus d'activation de la propriété Mobile App dans Campaign à l'aide du SDK Mobile V5.<br /> Pour plus d'informations, consultez la <a href="https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Améliorations  {#improvements}

* Adobe Campaign Standard prend maintenant en charge la version 4 de l'API d'Amazon S3.

### Autres changements  {#other-changes}

* Dans les broadlogs, il existe maintenant une distinction entre le nombre maximal de connexions et le nombre maximal de messages par heure. Lorsque les limites sont atteintes, il est alors possible de déterminer pourquoi le débit est limité. Auparavant, le même message ("quota atteint") s'appliquait aux deux cas.
* Lors de la configuration d'une application mobile dans Campaign, l'utilisateur peut désormais savoir si le certificat iOS et la clé du serveur Android ont été téléchargés avec succès et leur date d'expiration.

   Pour plus d'informations, consultez la documentation détaillée sur la configuration d'une application mobile à l'aide du [SDK V4](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html) et du [SDK V5](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

* Ciblez des utilisateurs sur une application mobile spécifique en sélectionnant cette application mobile lorsque vous définissez les propriétés de Campaign. Cette fonctionnalité est destinée aux canaux Push et Messagerie in-app.

   Pour plus d'informations, consultez la [documentation détaillée](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Lors de la sélection d'un bloc de contenu à l'aide de l'interface Creative Designer, tous les blocs de contenu de la liste sont maintenant chargés et affichés. (CAMP-27311)

   Consultez à ce sujet la [documentation détaillée](../../designing/using/adding-a-content-block.md).

### Correctifs  {#patches}

* Correction d'un problème en raison duquel le nombre de logs était différent entre le tableau de bord et le rapport de synthèse des emails transactionnels. (CAMP-28237
* Correction d'une erreur dans les workflows qui pouvait afficher un message d'erreur lors de l'import d'un fichier via une activité Transfert de fichier. (CAMP-27435)
* Correction d'une erreur liée aux landing pages contenant plus de 25 services qui entraînait la désélection aléatoire des services dans le formulaire. (CAMP-26572)
* Correction d'une erreur dans les workflows qui empêchait la configuration des comptes externes avec une URL SFTP lors de l'utilisation de l'activité Transfert de fichier. (CAMP-26475)
* Correction d'une erreur qui empêchait la mise à jour du rapport de synthèse des services. (CAMP-26301)
* Correction d'une erreur dans les workflows lors de l'utilisation d'une activité Enrichissement. Celle-ci empêchait un champ personnalisé d'afficher la date correcte. (CAMP-26242)
* Correction d'une erreur qui empêchait la mise à jour des dates d'abonnement au service lors d'un import via un import de fichier.
* Correction d'une erreur liée à l'activité Chargement du fichier qui empêchait les workflows d'importer des fichiers (CAMP-27068).
* Correction d'une erreur qui affichait un nombre d'abonnements incorrect dans les rapports de synthèse des services (CAMP-25587).
* Correction d'un problème lié à la différence des données entre les rapports Adobe Analytics et Adobe Campaign. (CAMP-25393)
* Correction d'une erreur qui empêchait un utilisateur ayant un accès limité de se connecter. (CAMP-27381)
* Correction d'une erreur qui empêchait l'affichage de la liste de contenu Adobe Experience Manager lors de l'édition d'un email à l'aide de Creative Designer. (CAMP-27181)
* Correction d'un problème qui empêchait l'ouverture de Creative Designer, entraînant une erreur. (CAMP-27304)
* Correction d'une erreur qui empêchait le bon fonctionnement des opérations de glisser-déposer dans Creative Designer lors de l'utilisation d'Internet Explorer 11.
* Correction d'une erreur en raison de laquelle les photos téléchargées depuis un appareil photo et prises en mode portrait s'affichaient dans une position de rotation indésirable.
* Correction d'une erreur qui affichait des informations de sélection imprécises lors de l'utilisation de l'éditeur de requêtes dans Creative Designer.
* Correction d'une erreur qui empêchait la duplication correcte d'un élément lors de l'utilisation de l'éditeur de requêtes dans Creative Designer.
* Correction d'une erreur qui entraînait la poursuite de la diffusion de messages SMS à des destinataires blacklistés même s'ils avaient été désabonnés via une réponse automatique. (CAMP-27128)
* Correction d'un problème qui empêchait l'affichage des erreurs à l'origine de l'échec du workflow **Nettoyage de la base**. (CAMP-26876)
* Correction d'une erreur qui empêchait la suppression de champs personnalisés dans une définition de notification push. (CAMP-25588)

## Version 18.7 - Juillet 2018  {#release-18-7---july-2018}

### Nouveautés {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Drapeau Haute priorité pour les notifications push Android<br /> </td> 
   <td> Drapeau Haute priorité pour Android - Permet de diffuser une notification push haute priorité pour les applications Android qui réveille les appareils en veille et les pousse à exécuter un traitement limité. Notez que la priorité par défaut est Normale et peut retarder la diffusion du message afin d'économiser la batterie. <br /> Pour plus d'informations, consultez la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtre de typologie pour les abonnés aux applications mobiles<br /> </td> 
   <td> Prise en charge des abonnements dans le filtre de typologie - Lorsque vous spécifiez les critères de filtrage pour une règle de typologie, vous pouvez sélectionner les abonnements aux applications comme dimensions de ciblage et de filtrage, de façon à filtrer en fonction des attributs pour les utilisateurs possédant ou non un profil. <br /> Pour plus d'informations, consultez la <a href="../../administration/using/about-typology-rules.md#typology-rules">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importation de contenu automatisée à partir d'une URL lors de la préparation des messages<br /> </td> 
   <td> Il est dorénavant possible d'importer le contenu email à partir d'une URL au cours de la phase de préparation. Pour les diffusions email récurrentes, le dernier contenu HTML est récupéré chaque fois que le message est préparé de façon à ce que le contenu soit toujours à jour lors de l'envoi de l'email. Cette fonctionnalité vous permet également de créer une diffusion différée avec du contenu d'une URL, même si le contenu n'est pas encore prêt.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Message de notification de mise à jour de Campaign<br /> </td> 
   <td> Un message contextuel apparaît maintenant lorsqu'un utilisateur se connecte après la mise à niveau de l'instance vers une nouvelle version. Le message indique le numéro de version et inclut un lien vers les notes de mise à jour. Vous pouvez choisir de masquer le message jusqu'à la prochaine mise à jour. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gestion des utilisateurs<br /> </td> 
   <td> À partir de la version 18.7, la fonctionnalité relative aux entités géographiques n'est plus disponible pour les nouvelles instances de Campaign Standard ainsi que pour les instances existantes sans unités géographiques déjà créées.<br />Pour plus d'informations, consultez cette <a href="https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Améliorations {#improvements-1}

* L'intégration d'Adobe Campaign et Adobe Target vous permet désormais de tirer parti de la fonctionnalité [Autorisations](https://marketing.adobe.com/resources/help/fr_FR/target/target/properties-overview.html) de Target. Lorsque vous incluez dans un email une image dynamique provenant d'Adobe Target, vous pouvez maintenant spécifier une propriété Target (code at_property).
* Les ressources personnalisées disposant d'un lien owncopy vers la ressource de profils sont à présent prises en compte par les demandes d'accès/de suppression des informations personnelles dans le cadre du RGPD. Pour les liens simples de cardinalité 1 et les liens de collection de cardinalité N, vous devez sélectionner "La suppression/duplication de l'enregistrement cible implique celle des enregistrements référencés par le lien" dans la ressource personnalisée. Pour les liens simples de cardinalité 0 ou 1, sélectionnez "La suppression/duplication de l'enregistrement implique celle de l'enregistrement cible référencé par le lien".

### Autres changements  {#other-changes-1}

* Le délai de partage des rapports a été prolongé d'une à quatre minutes afin d'éviter toute erreur de timeout.
* Lors de l'édition du contenu d'un email, le nouveau Creative Designer s'ouvre par défaut. Si vous le souhaitez, vous pouvez revenir à l'éditeur de contenu par défaut à tout moment après avoir enregistré vos modifications. Consultez à ce sujet la [documentation détaillée](../../designing/using/about-email-content-design.md).
* Dans Creative Designer, un nouveau composant de contenu peut désormais être ajouté à un email : le carrousel. Consultez à ce sujet la [documentation détaillée](../../designing/using/defining-the-email-structure.md#about-content-components).
* Si vous cliquez sur le bouton **Charger un profil** dans un rapport Hot clicks de message transactionnel, seuls les profils de test liés à l'événement que vous avez défini pour votre message transactionnel sont maintenant répertoriés.

### Correctifs {#patches-1}

* Correction d'un problème avec le filtre de requête byEmail qui ne renvoyait pas de résultats. (CAMP-23420)
* Correction d'un problème qui permettait à un utilisateur standard d'accéder à certaines fonctionnalités ou à certains écrans réservés aux administrateurs (points de terminaison /rest/head/*, écrans de messages transactionnels et écrans d'import de profils et d'audiences).
* Correction d'un problème qui empêchait le traitement de ressources personnalisées dans le cadre de demandes de suppression des informations personnelles liées au RGPD si leur nom commençait par un nombre.
* Correction d'un problème qui empêchait l'activité Sauvegarde d'audience de partager des abonnés aux applications dans Adobe Experience Cloud.
* Correction d'un problème qui pouvait se produire avec l'activité Transfert de fichier lorsque le nom du fichier contenait des espaces blancs. (CAMP-25936)
* Correction d'un problème qui pouvait se produire lors de l'utilisation du bouton de reconnexion après l'expiration d'une session. (CAMP-25560)
* Correction d'un problème qui pouvait entraîner des exclusions lors de l'envoi des diffusions avec une optimisation des fuseaux horaires associée à des règles de fatigue. (CAMP-25425)
* Correction d'un problème qui pouvait empêcher la suppression des données d'un lien de type 0-1 lors de l'utilisation de la fonctionnalité API RGPD.
* Correction d'un problème qui pouvait engendrer un message d'erreur lors de l'annulation de l'édition d'une règle de typologie de fatigue.
* Correction d'un problème qui pouvait se produire lors de la prévisualisation d'un contenu de diffusion après son édition.
* Correction d'un problème qui pouvait se produire lors du traitement des fichiers zip au format CSV lors de l'utilisation de l'option Décompression.
* Correction d'un problème dans Creative Designer qui entraînait l'apparition d'un formatage et d'une couleur de police non souhaités lors du changement d'un texte avec un style intégré en un lien ou lors de l'édition de ce lien. (CAMP-26001)
* Correction d'un problème qui empêchait le rapport Hot clicks d'afficher les pourcentages pour chaque condition dans les diffusions comportant du contenu dynamique. Auparavant, seuls les clics sur la variante par défaut étaient affichés.

## Version 18.6 - Juin 2018  {#release-18-6---june-2018}

### Améliorations {#improvements-2}

* L'API **[!UICONTROL History]** a été ajoutée à Adobe.IO. Elle permet d'accéder aux informations relatives à l'historique marketing d'un profil : nombre de points de contact, diffusions envoyées, URL de page miroir, etc. Voir à ce propos le [cas pratique dédié](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile).
* Le workflow technique **[!UICONTROL Nettoyage de la base]** a été optimisé pour améliorer les performances du nettoyage de la base de données.
* Creative Designer pour les e-mails est désormais disponible en français et en allemand.

### Autres changements  {#other-changes-2}

* Un bouton **[!UICONTROL Calculer les statistiques]** a été ajouté à la fenêtre **[!UICONTROL Déploiement]** des diffusions envoyées. Il permet de récupérer les derniers KPI, par exemple si la mise à jour des résultats de l'envoi prend trop de temps ou si les résultats n'ont pas été pris en compte. Voir à ce propos cette [section](../../sending/using/confirming-the-send.md).
* Dans le workflow technique d'usine **Mise à jour pour la délivrabilité**, les administrateurs fonctionnels peuvent maintenant définir le nombre d'erreurs consécutives à ignorer dans l'activité javascript **Mise à jour des règles**. Par défaut, la valeur du champ est définie sur 0, ce qui signifie que toutes les erreurs seront ignorées.
* Le code SQL généré lors de la gestion des conditions de restriction d'accès à l'entité a été optimisé.
* L'activité **[!UICONTROL Mise à jour]** permet maintenant d'ajouter, de mettre à jour ou de supprimer des données relatives aux abonnements (table nms:appSubscriptionRcp).
* Le workflow technique **[!UICONTROL Mise à jour de l'exécution des diffusions]** a été divisé en deux workflows afin d'optimiser les performances : - **[!UICONTROL Mise à jour de l'exécution des diffusions]** : met à jour le tracking de la diffusion. Par défaut, il est démarré toutes les 10 minutes. **[!UICONTROL Mise à jour des indicateurs de diffusion]** : met à jour les indicateurs de performance clé (IPC) de la diffusion. Par défaut, il est démarré toutes les heures. Pour plus d'informations sur les workflows techniques, voir cette [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Lorsqu'une diffusion envoie des messages, le statut dans la section **[!UICONTROL Déploiement]** peut maintenant avoir deux valeurs : **[!UICONTROL Envoi]** : les messages sont en cours d'envoi. **[!UICONTROL Envoi (nouvel essai)]** : un nouvel essai est en cours.
* Les utilisateurs disposant du rôle **[!UICONTROL Préparation de la diffusion]** peuvent maintenant envoyer des bons à tirer. (CAMP-24313)
* L'option **Activer TLS via SMPP** a été ajoutée au compte externe **Routage des SMS par SMPP**. Voir à ce propos cette [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Correctifs  {#patches-2}

* Correction d'une erreur qui empêchait l'envoi des e-mails lors de l'inclusion d'une image dynamique depuis Adobe Target (CAMP-24848).
* Correction d'une erreur liée aux workflows techniques **[!UICONTROL Demande d'accès/de suppression des informations personnelles]**. Ils ne se terminaient pas en cas d'échec d'une des demandes.
* Correction d'une erreur qui empêchait Privacy Core service de recevoir les mises à jour des statuts de demande de Campaign.
* Correction d’une erreur qui empêchait le fonctionnement correct du workflow technique **[!UICONTROL Import de l'audience partagée]** (CAMP-25465).
* Correction d'une erreur qui empêchait les demandes d'accès aux informations personnelles de Campaign d'être marquées comme étant terminées dans Privacy Core Service.
* Correction d'une erreur qui empêchait certains utilisateurs de se connecter à Campaign Standard via l'authentification IMS lorsque l'Adobe ID était trop long. (CAMP-24095)
* Correction d'une erreur dans Creative Designer qui se produisait lors de la suppression de modules de contenu. (CAMP-25242)
* Correction d'une erreur lors de l'utilisation des règles de fatigue des notifications push pour les abonnés sans profil dans la base de données. (CAMP-25344)
* Correction d'une erreur qui affichait un message d'erreur lors de l'accès aux exclus des diffusions. (CAMP-24724)
* Correction d'une erreur qui empêchait la préparation des bons à tirer dans les instances avec des envois étendus.
* Correction de deux erreurs qui se produisaient lors de la publication de ressources personnalisées avec l'extension des **[!UICONTROL Envois]** activée.
* Correction d'une erreur liée à la non-prise en compte de la durée de la diffusion dans les diffusions récurrentes.
* Correction d'une erreur qui se produisait lors du tri des données dans le menu **[!UICONTROL Données client]** pour les ressources personnalisées comprenant plus de 100 000 enregistrements. (CAMP-24308)
* Correction d'une erreur liée aux dimensions de profil personnalisées qui n'étaient pas prises en compte lors de l'utilisation de la fonction de recherche dans les rapports dynamiques.
* Correction d'une erreur liée à l'affichage des données internationales pour les niveaux de compte dans les rapports dynamiques.
* Il est désormais possible de créer un service sans message de confirmation d'abonnement ou de désabonnement.

## Version 18.5 - Mai 2018  {#release-18-5---may-2018}

### Nouveautés {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Fonctionnalité<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> RGPD : intégration avec Core Service<br /> </td> 
   <td> L'intégration de Privacy Core Service vous permet d'automatiser vos demandes RGPD dans un contexte multisolution à l'aide d'un seul appel d'API JSON. <br /> Les demandes RGPD émises depuis Privacy Core Service vers toutes les solutions Experience Cloud sont désormais traitées automatiquement par Campaign. <br /> Pour plus d'informations, consultez la <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_GDPR.html">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Améliorations des notifications push – retours détaillés de la diffusion<br /> </td> 
   <td> Adobe Campaign permet désormais de recevoir des retours détaillés (envois et exclus) sur les messages push provenant des fournisseurs (APNS/GCM) via MCPNS.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extension des logs de diffusion<br /> </td> 
   <td> L'extension des logs de diffusion vous permet d'étendre les envois avec des données de profil et un code segment issu de workflows. Ces informations peuvent ensuite être utilisées dans les Rapports dynamiques et vous permettent de conserver un snapshot de certaines informations au moment de l'envoi d'une diffusion.<br /> Deux autres cas pratiques se présentent :<br /> 
    <ul> 
     <li> Export des broadlogs étendus avec des données "figées" : en tant que marketeur, je souhaite exporter tous les profils où le code segment est égal à "A" (provenant du moteur de workflow) </li> 
     <li> Segmentation sur les données "figées" : en tant que marketeur, je souhaite <strong>recibler</strong> tous les profils ayant acquis 1 000 points de fidélité depuis le dernier envoi ou pour lesquels le code segment correspondait à "A". </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dynamique à l'aide de données de profil personnalisées<br /> </td> 
   <td> Cette fonctionnalité vous permet de créer et de gérer des rapports à partir de données de profil personnalisées créées lors de l'extension de la ressource des profils. Vous pouvez répartir les rapports par attribut de profil, tel que le programme de fidélité, le canal préféré, etc.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Améliorations  {#improvements-3}

* Amélioration de l'utilisation globale de la mémoire et du processeur par l'application

### Autres changements  {#other-changes-3}

* L'activité de workflow Lecture d'audience peut désormais lire les audiences Experience Cloud. Cette activité ne pouvait auparavant lire que les audiences de type Requête et Liste. Consultez à ce sujet la [documentation détaillée](../../automating/using/read-audience.md). (CAMP-23623)
* L'identifiant de la Source de données partagée par défaut est désormais en lecture seule uniquement et ne peut plus être modifié. La modification de cet identifiant peut entraîner des problèmes lors du partage d'audiences avec Experience Cloud.
* L'import d'audiences depuis Audience Manager fonctionne désormais avec des fichiers partagés. Auparavant, seul le dernier fichier du segment était importé par le workflow technique importSharedAudience.
* Les comptes externes d'AWS S3 prennent désormais en charge les régions et le mécanisme d'authentification en version 4. Consultez à ce sujet la [documentation détaillée](../../administration/using/external-accounts.md).
* La fenêtre de sélection de ressources se charge plus rapidement et permet de sélectionner une ressource, puis d'être fermée sans problème.
* Les propriétés et la structure des workflows techniques peuvent désormais être modifiées par les utilisateurs disposant de droits d'administration et appartenant aux entités organisationnelles et géographiques "Toutes".
* Des améliorations ont été apportées à l'interface de l'activité Segmentation lors de la création de nouveaux segments : l'onglet Limitation apparaît désormais directement après avoir ajouté une limitation. De nouveaux noms de segments sont maintenant incrémentés ("Segment 1", "Segment 2", etc.).
* Un champ "nextProcessingDate" est ajouté à la ressource Workflow. Ce champ n'est visible que via les appels d'API REST ; il vous permet de visualiser les dates de prochain traitement des workflows.
* Le champ "sourceId" est désormais affiché dans la ressource de tracking (nms:trackingLog).
* Les valeurs "Nombre total d'ouvertures" et "Nombre total de clics" peuvent désormais être exportées dans un fichier plat via un workflow. (CAMP-24186)
* "Anglais - Danemark" est désormais disponible dans la liste des Préférences linguistiques au sein des profils. (CAMP-23728)
* Lors de l'utilisation d'une activité Segmentation avec un lien Données additionnelles (targetData), un message vous informe désormais que les données ne sont pas disponibles en dehors du workflow. Ce message s'affiche lorsque vous cliquez sur le bouton Compter ou Aperçu depuis l'activité Segmentation. (CAMP-23651)
* Des améliorations ont été réalisées pour optimiser l'espace disque utilisé par les workflows : (CAMP-21979) : les fichiers traités par l'activité "Chargement de fichier" sont désormais supprimés par défaut. Une option vous permet de les conserver en cas de besoin. Lorsqu'un workflow est supprimé, son dossier dédié est automatiquement supprimé du répertoire du serveur.

### Correctifs  {#patches-3}

* Correction d'un problème selon lequel des événements de reporting bruts n'avaient pas d'événements de suivi associés, car le champ eventDate n'était pas correctement rempli.
* Correction d'un problème qui empêchait des champs personnalisés de s'afficher dans la fenêtre d'aperçu d'une diffusion de notification push.
* Correction d'un problème qui empêchait le texte d'être renvoyé à la ligne dans le corps du message d'une notification push dans la fenêtre d'aperçu.
* Correction d'un problème lors de l'envoi d'une diffusion récurrente provenant d'un workflow lorsque la cible principale est vide.
* Correction d'un problème qui empêchait l'accès à un mapping de ciblage si celui-ci est lié à un schéma inexistant.
* Correction d'un problème qui pouvait se produire lors de l'importation d'un fichier zip via une activité Chargement de fichier. (CAMP-24309)
* Correction d'un problème qui entraînait une erreur PostgreSQL lors de l'envoi d'une diffusion récurrente. (CAMP-23613)
* Correction d'un problème qui affichait un message d'erreur lors de l'envoi d'une requête API REST avec un attribut JSON vide. (CAMP-23506)
* Correction d'un problème de basculement en majuscule des caractères suivant le caractère "ß" dans les profils. (CAMP-23136)
* Correction d'un problème lors de l'envoi de diffusions utilisées avec les conditions d'éligibilité d'un bloc de contenu dynamique ou de personnalisation, tout en utilisant des attributs provenant d'un schéma de profil lié. (CAMP-22751)
* Correction d'un problème qui empêchait la suppression de services. (CAMP-22050)
* Correction d'un problème qui empêchait de modifier les valeurs Pays ou Etat dans un Profil de test. (CAMP-20426)
* Correction d'un problème qui pouvait empêcher le chargement de Creative Designer. (CAMP-24573)
* Correction d'un problème qui supprimait les caractères ajoutés après des champs de personnalisation dans l'objet d'un email. (CAMP-24113)

## Version 18.4 - Avril 2018  {#release-18-4---april-2018}

### Correctifs {#patches-4}

#### Plate-forme {#platform}

* Corrections d'une erreur qui pouvait empêcher le bon traitement des demandes d'accès ou de suppression du RGPD. Ce comportement a été observé dans de rares cas lorsque les données extraites contenaient l'un des caractères suivants : &amp; &lt;&gt; " '.

#### Emails, SMS et courrier  {#emails--sms-messages-and-direct-mail}

* Correction d'un problème qui pouvait entraîner le remplacement des KPI par des valeurs incorrectes si la synchronisation du broadlog prenait plus d'une heure.

#### Workflows  {#workflows}

* Gestion améliorée de la mémoire et optimisation des performances dans les workflows.

#### Reporting  {#reporting}

* Le workflow de partage des KPI récupère désormais les valeurs des diffusions pour les deux derniers mois au lieu des six derniers. Correction d'un problème lié au compte externe de partage des KPI qui affichait des dates tronquées.
* Correction d'un problème qui pouvait entraîner la non-prise en compte de certains messages dans les mesures **Envoyés**, **Délivrés** et **Bounce**.
* Correction d'un problème qui survenait lorsque la période choisie dans le **Rapport Synthèse des diffusions** était trop étendue.

#### Ressources personnalisées {#custom-resources}

* Correction d'une erreur qui entraînait l'échec de la préparation des ressources personnalisées.

## Version 18.3 - Mars 2018  {#release-18-3---march-2018}

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
   <td> Règlement général sur la protection des données de l'UE (RGPD)<br /> </td> 
   <td> Le RGPD est la nouvelle loi de l'Union européenne (UE) sur la protection de la vie privée qui entre en vigueur le 25 mai 2018. Il harmonise et modernise les exigences en matière de protection des données. Le règlement s'applique aux clients Adobe Campaign qui détiennent des données pour des personnes concernées résidant dans l'UE.<br /> Outre les fonctionnalités de protection des données déjà disponibles dans Adobe Campaign (notamment la gestion des accords, les paramètres de rétention des données et les rôles utilisateur), nous incluons, dans le cadre de notre rôle de fournisseur de service de traitement des données, des fonctionnalités supplémentaires pour faciliter votre préparation en tant que Contrôleur de données à certaines demandes RGPD :<br /> 
    <ul> 
     <li> Droit d'accès : permet à la personne concernée de recevoir une copie de ses données personnelles capturées par les Contrôleurs de données, notamment les données éventuellement stockées dans Adobe Campaign. </li> 
     <li> Droit de suppression : autorise la personne concernée à demander la suppression de ses données personnelles capturées par les Contrôleurs de données, notamment les données éventuellement stockées dans Adobe Campaign. </li> 
    </ul> Pour plus d'informations, consultez la <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_GDPR.html">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer pour les e-mails (version bêta)<br /> </td> 
   <td> Le nouvel outil Creative Designer d'Adobe Campaign offre un environnement de création entièrement intégré dans Campaign, permettant la création rapide et facile d'emails personnalisés, sans avoir à écrire une seule ligne de code. Grâce à sa puissante interface de conception par glisser-déposer, Creative Designer permet de créer facilement des emails à partir de zéro ou en utilisant des fragments ou des modèles de contenu existants. <br />Les fonctionnalités principales sont les suivantes :<br /> 
    <ul> 
     <li> Créez visuellement des emails personnalisés et au design responsive grâce à une interface de conception par glisser-déposer, complétée par des intégrations Creative Cloud natives. </li> 
     <li> Créez et enregistrez un modèle de contenu d'email et utilisez des modèles enregistrés pour faciliter la création d'emails. </li> 
     <li> Créez et enregistrez des fragments de contenu (tels qu'un en-tête, un pied de page, un article, etc.) pour rationaliser la création de contenu et assurer la cohérence de la marque. </li> 
     <li> Passez facilement de la création d'un email dans l'interface de conception par glisser-déposer à l'édition directe de son code HTML en cliquant sur un bouton. </li> 
    </ul> Creative Designer pour les emails est disponible uniquement en anglais.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">documentation détaillée</a> et regardez cette <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vidéo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusions de notifications push multilingues <br /> </td> 
   <td> L'interface multilingue conviviale, qui existe déjà pour les canaux Email et SMS, a été ajoutée au canal Notification push pour vous aider à interagir avec les clients, quelle que soit leur préférence linguistique.<br /> Cette fonctionnalité offre une solution évolutive et automatique aux clients qui gèrent des campagnes push couvrant plusieurs zones géographiques et qui souhaitent cibler les utilisateurs dans la langue de leur choix. Elle permet de télécharger en un seul clic toutes les variantes linguistiques via une feuille de calcul basée sur un modèle dans une seule diffusion push. Adobe Campaign effectue ensuite une segmentation automatique selon la préférence linguistique des utilisateurs, ce qui permet de réduire les redondances en simplifiant les workflows et le reporting.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utilisation des ressources personnalisées dans les messages transactionnels<br /> </td> 
   <td> Outre les champs d'usine, les messages transactionnels permettent désormais d'utiliser des ressources personnalisées pour enrichir le contenu de vos messages.<br /> Par exemple:<br /> 
    <ul> 
     <li> Utilisez des champs personnalisés en tant que critères de réconciliation pour faire correspondre un message transactionnel à un profil. </li> 
     <li> Utilisez des profils complets, des services et des données associées pour personnaliser davantage les messages transactionnels. </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../administration/using/configuring-transactional-messaging.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs  {#patches-5}

#### Plate-forme {#platform-1}

* Correction d'un problème qui empêchait l'export de plus de 5 000 enregistrements d'une liste.
* Correction d'un problème lors de l'export de données vers des fichiers nommés avec des champs de personnalisation.

#### Emails, SMS et courrier  {#emails--sms-messages-and-direct-mail-1}

* Correction d'un problème qui entraînait la troncature des SMS en plusieurs parties, car la taille des parties était calculée en caractères et non en octets.
* Ajout d'une option permettant de mettre à jour en temps réel le KPI **[!UICONTROL Délivrés]** ou **[!UICONTROL Bounces + erreurs]** après l'envoi de la diffusion. Ils sont directement recalculés à partir du SR (Status Report) reçu du fournisseur.
* Correction d'un problème lié au widget de calendrier dans le planificateur de diffusion.
* Correction d'un problème d'affichage lors de l'ouverture d'une cible pour la seconde fois dans une diffusion envoyée.
* Correction d'un problème qui entraînait l'affichage d'un message d'erreur demandant une date de début lors de la création d'un modèle d'email avec une date d'envoi différée.
* Correction d'une erreur qui entraînait des problèmes de rendu d'image lors de l'édition du contenu d'une diffusion.
* Correction d'un problème lié aux bons à tirer lors de la duplication d'une campagne.
* Correction d'une erreur qui entraînait l'affichage d'un message d'erreur lors de l'accès à un modèle de campagne via la barre de navigation, après l'ajout d'une diffusion au workflow.
* Correction d'un problème qui empêchait la sélection automatique du gagnant d'un email de test A/B, ce qui entraînait le non-envoi de l'email. Ce problème se produisait lorsque l'état de la diffusion était **[!UICONTROL retryInProgress]**.
* Correction d'un problème qui entraînait l'affichage d'un message d'erreur lors de la réouverture des paramètres d'un email de test A/B.

#### Audiences et requêtes  {#audiences-e-queries}

* Correction d'un problème qui empêchait d'accéder aux données et de configurer des requêtes pour les destinataires répliqués d'Adobe Campaign Classic vers Standard.
* Correction d'un problème qui se produisait lors de l'utilisation d'un champ de type filtre dans l'éditeur de requêtes, après avoir utilisé le bouton **Compter** ou **Prévisualiser**.

#### Workflows  {#workflows-1}

* Le workflow **Facturation** a été optimisé pour réduire le délai de préparation de la diffusion.
* Correction d'un problème qui empêchait l'affichage des données de population dans une transition sortante lors de l'utilisation d'une activité de diffusion récurrente.
* Correction d'un problème qui empêchait l'affichage des enregistrements de rejet dans une transition après une activité **Mise à jour de données**.
* Correction d'un problème qui entraînait l'échec du workflow technique **deliverabilityUpdate**.

#### Intégrations  {#integrations}

* Correction d'un problème qui empêchait d'envoyer correctement des caractères internationaux à Adobe Analytics.
* Les ressources doivent à présent se charger plus rapidement lorsque vous insérez une image dans un message depuis votre bibliothèque de ressources Experience Cloud.
* Correction d'un problème qui empêchait, dans certains cas, la fermeture de la fenêtre de sélection de ressources.
* Depuis le détail d'une source de données, vous pouvez à présent accéder directement au workflow associé pour en vérifier l'état.
* Vous pouvez maintenant mettre directement à jour le schéma Triggers lors de la définition ou de l'édition d'un événement de trigger. Grâce à cette modification, vous n'avez plus à dépublier le trigger et en créer un autre.

#### Messages transactionnels {#transactional-messages}

* Correction d'une erreur liée au modèle de message transactionnel lors de l'extension de la ressource de diffusion.
* Il est maintenant possible de supprimer les messages transactionnels.

## Version 18.2 - Février 2018  {#release-18-2---february-2018}

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
   <td> Abonnement : abonnez ou désabonnez une liste de profils à plusieurs services.<br /> </td> 
   <td> L'activité de workflow <strong>Services d'abonnements</strong> permet désormais d'abonner ou de désabonner une liste de profils à plusieurs services. Dans votre workflow, importez un fichier contenant les profils, et pour chaque profil, le type d'opération et le service. L'activité <strong>Services d'abonnements</strong> pourra utiliser ces informations et gérer dynamiquement tous les abonnements et désabonnements des profils en même temps.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/subscription-services.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Activité d'enrichissement : enrichissez les données en fonction des transitions précédentes.<br /> </td> 
   <td> La nouvelle activité de workflow <span class="uicontrol">Enrichissement</span> permet d'utiliser les transitions entrantes et de compléter la transition sortante avec des données additionnelles. Si vous ciblez des profils, l'activité d'enrichissement vous permet d'enrichir les informations des profils avec des données additionnelles qui ne sont pas stockées dans la base de données (issues d'un fichier importé, par exemple).<br /> Pour plus d'informations, consultez la <a href="../../automating/using/enrichment.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs  {#patches-6}

#### Plate-forme {#platform-2}

* Mise à jour de la barre supérieure de l'interface d'Adobe Campaign avec le nouveau menu d'Experience Cloud.
* Correction d'une erreur qui empêchait l'affichage du lien vers les **[!UICONTROL Offres]** dans la liste déroulante de la solution.

#### Emails, SMS et courrier {#emails--sms-messages-and-direct-mail-2}

* Amélioration de la phase de préparation des diffusions pour optimiser les performances.
* Correction de plusieurs problèmes qui entraînaient l'endommagement du tracking dans certains cas très spécifiques.
* Correction d'un problème de mise à jour de date de contact qui se produisait lorsque la date de contact était modifiée entre la préparation de la diffusion et sa validation. Vous pouvez modifier la date de contact après la préparation. Vous devrez toutefois préparer à nouveau la diffusion avant de pouvoir valider l'envoi. Consultez la [documentation détaillée](../../sending/using/preparing-the-send.md)..

#### Notifications push {#push-notifications}

* Correction d'une erreur qui empêchait certains champs de personnalisation de fonctionner dans les notifications push iOS.
* Correction d'une erreur qui affichait des taux de clic et d'ouverture de 0 % dans le tableau de bord des notifications push.

#### Rapports {#reports}

* Correction d'une erreur qui affichait une liste de rapports vide dans certains navigateurs.
* Correction d'une erreur qui se produisait dans le workflow technique **[!UICONTROL Partage des rapports]** juste avant l'atteinte de sa limite de validité.

#### Workflows {#workflows-2}

* Correction d'un problème qui empêchait l'accessibilité des activités après les avoir placées dans un workflow.
* Correction d'un problème qui entraînait, dans certains cas, la modification de l'ordre des transitions en sortie d'une activité **[!UICONTROL Segmentation]**.
* Correction d'une erreur qui se produisait lors de la lecture d'une audience contenant un champ de type énumération et ayant été précédemment enregistrée dans un workflow.
* Correction d'une erreur suite à laquelle l'option **[!UICONTROL Demander une confirmation avant d'envoyer les messages]** restait cochée même après avoir été décochée pendant la définition des propriétés de planification d'une diffusion créée dans un workflow.
* La suppression automatique des doublons (clause DISTINCT) peut désormais être désactivée dans les activités **[!UICONTROL Requête]**, via une nouvelle option située dans l'onglet **[!UICONTROL Données additionnelles]**. Pour des raisons de performance, il est recommandé de décocher cette option si vous définissez de nombreuses données additionnelles (plus de 100).

#### Intégrations  {#integrations-1}

* Certaines améliorations ont été apportées à l'écran de configuration **[!UICONTROL Sources de données]**.

### Problèmes connus {#known-issues}

Il est recommandé de ne pas utiliser Internet Explorer version 11 en raison de certains problèmes d'affichage possibles.

Certains problèmes peuvent se produire lors de l'utilisation des liens d'aide contextuelle dans l'interface de Campaign. Ils seront résolus dans la version 18.3.

## Version 18.1 - Janvier 2018  {#release-18-1---january-2018}

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
   <td> Reporting pour la gestion de la fatigue<br /> </td> 
   <td> Le reporting pour la gestion de la fatigue offre un rapport dédié configurable qui montre l'impact des règles de fatigue sur les diffusions via les canaux Email, Push, SMS et Courrier pendant une période spécifiée avant l'envoi. Grâce à la possibilité de détecter rapidement toutes les campagnes en conflit dans une seule vue, les marketeurs peuvent planifier les campagnes marketing en conséquence afin de définir les règles de fatigue plus efficacement et hiérarchiser les communications.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Partage des rapports<br /> </td> 
   <td> Le partage des rapports vous permet de partager vos rapports avec les utilisateurs d'Adobe Campaign sous la forme de pièces jointes à un email, notamment de façon récurrente et automatique. Les utilisateurs recevant des rapports récurrents ont la possibilité de se désabonner de ces communications par le biais d'un lien dédié inclus dans chaque email.<br /> Pour plus d'informations, consultez la <a href="../../reporting/using/reporting-interface.md#share-tab">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nouvelles fonctionnalités push<br /> </td> 
   <td> Prévisualisation des notifications push : prévisualisez les notifications push sur les appareils iOS et Android dans l'éditeur de contenus des notifications push pour voir exactement à quoi elles ressembleront avant de tester ou d'envoyer la diffusion.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentation détaillée</a>.<br /> Contenu disponible : lorsque des applications ne sont pas ouvertes pendant de longues périodes, leurs données peuvent devenir obsolètes. Celles-ci doivent alors être mises à jour ou remplacées au moment où un utilisateur ouvre enfin une application, ce qui peut entraîner un temps d'attente avant de pouvoir l'utiliser. Avec la nouvelle prise en charge du Contenu disponible, les utilisateurs d'Adobe Campaign peuvent mettre en éveil leur application afin d'actualiser ses données en arrière-plan lors de la diffusion d'une notification push, ce qui accroît la cohérence et le contrôle sur l'expérience in-app d'un utilisateur.<br /> Contenu mutable : grâce à la nouvelle prise en charge du Contenu mutable, les utilisateurs d'Adobe Campaign peuvent désormais tirer parti des extensions de leur application mobile pour modifier davantage le contenu ou la présentation des notifications push envoyées depuis Adobe Campaign. Par exemple, les utilisateurs peuvent utiliser l'option Contenu mutable pour :<br /> 
    <ul> 
     <li> décrypter des données diffusées dans un format crypté ; </li> 
     <li> télécharger des images ou d'autres fichiers multimédia et les ajouter sous forme de pièces jointes à une notification ; </li> 
     <li> changer le texte du titre ou du corps d'une notification ; </li> 
     <li> ajouter un identifiant de thread à une notification. </li> 
    </ul> Pour plus d'informations sur les options Contenu mutable et Contenu disponible, consultez la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentation détaillée</a>.<br /> <strong>Avertissement :</strong> ces mises à jour des notifications push requièrent une mise à niveau des applications mobiles des clients. Pour plus d'informations, consultez <a href="https://helpx.adobe.com/fr/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">cette technote</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusions optimisées avec les fuseaux horaires<br /> </td> 
   <td> Planifiez des notifications push, des SMS et des emails récurrents à diffuser à un jour et une heure spécifiques dans le fuseau horaire de chaque destinataire. Vos messages sont ainsi envoyés au bon moment sans configurer plusieurs diffusions. <br /> Pour plus d'informations, consultez la <a href="../../automating/using/scheduler.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Déclenchement de l'activité Signal depuis l'API<br /> </td> 
   <td> Il est désormais possible de déclencher une activité Signal pour vos workflows directement depuis l'API Adobe Campaign Standard.<br /> Pour plus d'informations, consultez la <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">documentation détaillée</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Correctifs  {#patches-7}

#### Plate-forme {#platform-3}

* La recherche de profils a été optimisée afin d'améliorer les performances.
* L'identifiant interne des groupes de sécurité par défaut est désormais en mode de lecture seule pour les utilisateurs standard.

#### Emails, SMS et courrier  {#emails--sms-messages-and-direct-mail-3}

* Correction d'une erreur d'affichage qui se produisait lors de l'insertion d'emojis dans le contenu des diffusions.
* Correction d'une erreur qui permettait à l'utilisateur d'accéder aux envois alors que la diffusion était toujours en édition.
* L'activité **[!UICONTROL Planificateur]** permet désormais d'envoyer des diffusions selon le fuseau horaire du destinataire.
* SMS : l'option **[!UICONTROL Stocker les MO entrants]** dans la base de données a été ajoutée aux comptes externes. Lorsque cette option est cochée, tous les SMS entrants sont stockés dans la table **inSMS**.
* SMS : les services sont désormais attachés à un événement au lieu d'un modèle transactionnel.
* SMS : le timeout des connexions SMTP par défaut a été réduit à 30 secondes.

#### Notifications push  {#push-notifications-1}

* Correction d'une erreur qui empêchait l'arrêt des diffusions des notifications push.
* Ajout d'une option aux options avancées des notifications push qui permet de mettre en éveil une application à l'aide d'une notification push.
* Ajout d'un bouton de pause pour la vidéo de prévisualisation des notifications push.
* La prévisualisation des notifications push est désormais possible pour différents appareils tels que les iPhone, Android ou les tablettes.

   tous les canaux

#### Rapports  {#reports-1}

* Correction d'une erreur qui affichait des taux supérieurs à 100 %.
* Correction d'une erreur qui empêchait les utilisateurs de télécharger les rapports au format CSV.
* Ajout d'un nouvel élément **[!UICONTROL Rapport]** sur la page d'accueil.

#### Workflows {#workflows-3}

* Correction d'un problème qui entraînait l'affichage d'un message d'erreur lors de l'utilisation de données additionnelles dans une requête et de l'ajout d'alias contenant des espaces. Les caractères qui ne sont pas alphanumériques ont été remplacés par "_".
* Correction d'une erreur qui entraînait dans certains cas l'arrêt par défaut du workflow technique calculant les KPI.

#### Profils et audiences  {#profiles-and-audiences}

* Correction d'une erreur qui se produisait lors de l'ajout de plusieurs filtres à une requête d'audience.
* Correction d'une erreur qui se produisait lors du changement de la photo d'un profil.
* Ajout d'une info-bulle affichant le nombre de résultats exact après le comptage de la population d'une requête.
* Correction d'une erreur qui empêchait un utilisateur de sélectionner une audience ou de fermer la fenêtre du sélecteur d'audience.
* Mise à jour de la liste des fonctions disponibles dans l'éditeur d'expression. Suppression des fonctions **FormatCurrency** et **ConvertCurrency**.

