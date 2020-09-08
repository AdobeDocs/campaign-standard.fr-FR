---
title: Notes de mise à jour 2018
description: Cette page répertorie toutes les versions 2018 d'Adobe Campaign Standard.
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
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '5454'
ht-degree: 99%

---


# Notes de mise à jour 2018{#release-notes}

Vous recherchez une version 2018 spécifique d&#39;Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu.

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d&#39;Adobe Campaign Standard. Si vous recherchez une note de mise à jour plus récente, consultez cette [page](../../rn/using/release-notes.md).

## Version 18.9 - Septembre 2018 {#release-18-9---september-2018}

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
   <td> Messagerie in-app (version bêta)<br /> </td> 
   <td> La messagerie in-app permet d'interagir plus efficacement avec les utilisateurs d'application mobile en offrant une interaction contextuelle et en permettant d'atteindre les utilisateurs susceptibles de ne pas s'être abonnés aux notifications push. Utilisez la messagerie In-App avec les notifications push pour créer une expérience hautement personnalisée et pertinente. Vous obtiendrez ainsi une meilleure conversion et rétention des utilisateurs de votre application.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-in-app-messaging.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration d'Adobe Launch pour les applications mobiles (version bêta)<br /> </td> 
   <td> L'intégration d'Adobe Launch avec Adobe Campaign simplifie et automatise maintenant le processus d'activation de la propriété Mobile App dans Campaign à l'aide du SDK Mobile V5.<br /> Pour plus d'informations, consultez la <a href="https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Adobe Campaign Standard prend maintenant en charge la version 4 de l&#39;API Amazon S3.

**Autres changements**

* Dans les broadlogs, il est maintenant possible de faire la distinction entre le nombre maximal de connexions et le nombre maximal de messages par heure. Lorsque les limites sont atteintes, il est alors possible de savoir pourquoi le débit est limité. Auparavant, le même message (&quot;quota atteint&quot;) s&#39;appliquait aux deux cas.
* Lors de la configuration d&#39;une application mobile dans Campaign, l&#39;utilisateur peut désormais savoir si le certificat iOS et la clé du serveur Android ont été téléchargés avec succès et leur date d&#39;expiration.

   Pour plus d&#39;informations, consultez la documentation détaillée sur la configuration d&#39;une application mobile à l&#39;aide de [SDK V4](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html) et [SDK V5](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html).

* Ciblez des utilisateurs sur une application mobile spécifique en sélectionnant cette application mobile lorsque vous définissez les propriétés de Campaign. Cette fonctionnalité est destinée aux canaux Push et Messagerie in-app.

   Pour plus d&#39;informations, consultez la [documentation détaillée](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Lors de la sélection d&#39;un bloc de contenu à l&#39;aide de l&#39;interface Creative Designer, tous les blocs de contenu de la liste sont maintenant chargés et affichés. (CAMP-27311)

   Consultez à ce sujet la [documentation détaillée](../../designing/using/personalization.md#adding-a-content-block).

**Correctifs**

* Correction d&#39;un problème en raison duquel le nombre de logs était différent entre le tableau de bord et le rapport de synthèse des emails transactionnels. (CAMP-28237
* Correction d&#39;une erreur dans les workflows qui pouvait afficher un message d&#39;erreur lors de l&#39;import d&#39;un fichier via une activité Transfert de fichier. (CAMP-27435)
* Correction d&#39;une erreur liée aux landing pages contenant plus de 25 services qui entraînait la désélection aléatoire des services dans le formulaire. (CAMP-26572)
* Correction d&#39;une erreur dans les workflows qui empêchait la configuration des comptes externes avec une URL SFTP lors de l&#39;utilisation de l&#39;activité Transfert de fichier. (CAMP-26475)
* Correction d&#39;une erreur qui empêchait la mise à jour du rapport de synthèse des services. (CAMP-26301)
* Correction d&#39;une erreur dans les workflows lors de l&#39;utilisation d&#39;une activité Enrichissement. Celle-ci empêchait un champ personnalisé d&#39;afficher la date correcte. (CAMP-26242)
* Correction d&#39;une erreur qui empêchait la mise à jour des dates d&#39;abonnement au service lors d&#39;un import via un import de fichier.
* Correction d&#39;une erreur liée à l&#39;activité Chargement du fichier qui empêchait les workflows d&#39;importer des fichiers (CAMP-27068).
* Correction d&#39;une erreur qui affichait un nombre d&#39;abonnements incorrect dans les rapports de synthèse des services (CAMP-25587).
* Correction d&#39;un problème lié à la différence des données entre les rapports Adobe Analytics et Adobe Campaign. (CAMP-25393)
* Correction d&#39;une erreur qui empêchait un utilisateur ayant un accès limité de se connecter. (CAMP-27381)
* Correction d&#39;une erreur qui empêchait l&#39;affichage de la liste de contenu Adobe Experience Manager lors de l&#39;édition d&#39;un email à l&#39;aide de Creative Designer. (CAMP-27181)
* Correction d&#39;un problème qui empêchait l&#39;ouverture de Creative Designer, entraînant une erreur. (CAMP-27304)
* Correction d&#39;une erreur qui empêchait le bon fonctionnement des opérations de glisser-déposer dans Creative Designer lors de l&#39;utilisation d&#39;Internet Explorer 11.
* Correction d&#39;une erreur en raison de laquelle les photos téléchargées depuis un appareil photo et prises en mode portrait s&#39;affichaient dans une position de rotation indésirable.
* Correction d&#39;une erreur qui affichait des informations de sélection imprécises lors de l&#39;utilisation de l&#39;éditeur de requêtes dans Creative Designer.
* Correction d&#39;une erreur qui empêchait la duplication correcte d&#39;un élément lors de l&#39;utilisation de l&#39;éditeur de requêtes dans Creative Designer.
* Correction d’un problème en raison duquel les messages SMS n’étaient pas distribués aux destinataires non inscrits, même s’ils avaient été désabonnés par le biais d’une réponse automatique. (CAMP-27128)
* Correction d&#39;un problème qui empêchait l&#39;affichage des erreurs à l&#39;origine de l&#39;échec du workflow **Nettoyage de la base**. (CAMP-26876)
* Correction d&#39;une erreur qui empêchait la suppression de champs personnalisés dans une définition de notification push. (CAMP-25588)

## Version 18.7 - Juillet 2018       {#release-18-7---july-2018}

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
   <td> Drapeau Haute priorité pour les notifications push Android<br /> </td> 
   <td> Drapeau Haute priorité pour Android - Permet de diffuser une notification push haute priorité pour les applications Android qui réveille les appareils en veille et les pousse à exécuter un traitement limité. Notez que la priorité par défaut est Normale et peut retarder la diffusion du message afin d'économiser la batterie. <br /> Pour plus d'informations, consultez la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtre de typologie pour les abonnés aux applications mobiles<br /> </td> 
   <td> Prise en charge des abonnements dans le filtre de typologie - Lorsque vous spécifiez les critères de filtrage pour une règle de typologie, vous pouvez sélectionner les abonnements aux applications comme dimensions de ciblage et de filtrage, de façon à filtrer en fonction des attributs pour les utilisateurs possédant ou non un profil. <br /> Pour plus d'informations, consultez la <a href="../../sending/using/about-typology-rules.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importation de contenu automatisée à partir d'une URL lors de la préparation des messages<br /> </td> 
   <td> Il est dorénavant possible d'importer le contenu email à partir d'une URL au cours de la phase de préparation. Pour les diffusions email récurrentes, le dernier contenu HTML est récupéré chaque fois que le message est préparé de façon à ce que le contenu soit toujours à jour lors de l'envoi de l'email. Cette fonctionnalité vous permet également de créer une diffusion différée avec du contenu d'une URL, même si le contenu n'est pas encore prêt.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Message de notification de mise à jour de Campaign<br /> </td> 
   <td> Un message contextuel apparaît maintenant lorsqu'un utilisateur se connecte après la mise à niveau de l'instance vers une nouvelle version. Le message indique le numéro de version et inclut un lien vers les notes de mise à jour. Vous pouvez choisir de masquer le message jusqu'à la prochaine mise à jour. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gestion des utilisateurs<br /> </td> 
   <td> À partir de la version 18.7, la fonctionnalité relative aux entités géographiques n'est plus disponible pour les nouvelles instances de Campaign Standard ainsi que pour les instances existantes sans unités géographiques déjà créées.<br /> Pour plus d'informations, consultez cette <a href="https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* L&#39;intégration d&#39;Adobe Campaign et Adobe Target vous permet désormais de tirer parti de la fonctionnalité [Autorisations](https://docs.adobe.com/content/help/fr-FR/target/using/administer/manage-users/enterprise/properties-overview.html) de Target. Lorsque vous incluez dans un email une image dynamique provenant d&#39;Adobe Target, vous pouvez maintenant spécifier une propriété Target (code at_property).
* Les ressources personnalisées disposant d&#39;un lien owncopy vers la ressource de profils sont à présent prises en compte par les demandes d&#39;accès/de suppression des informations personnelles dans le cadre du RGPD. Pour les liens simples de cardinalité 1 et les liens de collection de cardinalité N, vous devez sélectionner &quot;La suppression/duplication de l&#39;enregistrement cible implique celle des enregistrements référencés par le lien&quot; dans la ressource personnalisée. Pour les liens simples de cardinalité 0 ou 1, sélectionnez &quot;La suppression/duplication de l&#39;enregistrement implique celle de l&#39;enregistrement cible référencé par le lien&quot;.

**Autres changements**

* Le délai de partage des rapports a été prolongé d&#39;une à quatre minutes afin d&#39;éviter toute erreur de timeout.
* Lors de l&#39;édition du contenu d&#39;un email, le nouveau Creative Designer s&#39;ouvre par défaut. Si vous le souhaitez, vous pouvez revenir à l&#39;éditeur de contenu par défaut à tout moment après avoir enregistré vos modifications. Consultez à ce sujet la [documentation détaillée](../../designing/using/designing-content-in-adobe-campaign.md).
* Dans Creative Designer, un nouveau composant de contenu peut désormais être ajouté à un email : le carrousel. Consultez à ce sujet la [documentation détaillée](../../designing/using/designing-from-scratch.md#about-content-components).
* Si vous cliquez sur le bouton **Charger un profil** dans un rapport Hot clicks de message transactionnel, seuls les profils de test liés à l&#39;événement que vous avez défini pour votre message transactionnel sont maintenant répertoriés.

**Correctifs**

* Correction d&#39;un problème avec le filtre de requête byEmail qui ne renvoyait pas de résultats. (CAMP-23420)
* Correction d&#39;un problème qui permettait à un utilisateur standard d&#39;accéder à certaines fonctionnalités ou à certains écrans réservés aux administrateurs (points de terminaison /rest/head/*, écrans de messages transactionnels et écrans d&#39;import de profils et d&#39;audiences).
* Correction d&#39;un problème qui empêchait le traitement de ressources personnalisées dans le cadre de demandes de suppression des informations personnelles liées au RGPD si leur nom commençait par un nombre.
* Correction d&#39;un problème qui empêchait l&#39;activité Sauvegarde d&#39;audience de partager des abonnés aux applications dans Adobe Experience Cloud.
* Correction d&#39;un problème qui pouvait se produire avec l&#39;activité Transfert de fichier lorsque le nom du fichier contenait des espaces blancs. (CAMP-25936)
* Correction d&#39;un problème qui pouvait se produire lors de l&#39;utilisation du bouton de reconnexion après l&#39;expiration d&#39;une session. (CAMP-25560)
* Correction d&#39;un problème qui pouvait entraîner des exclusions lors de l&#39;envoi des diffusions avec une optimisation des fuseaux horaires associée à des règles de fatigue. (CAMP-25425)
* Correction d&#39;un problème qui pouvait empêcher la suppression des données d&#39;un lien de type 0-1 lors de l&#39;utilisation de la fonctionnalité API RGPD.
* Correction d&#39;un problème qui pouvait engendrer un message d&#39;erreur lors de l&#39;annulation de l&#39;édition d&#39;une règle de typologie de fatigue.
* Correction d&#39;un problème qui pouvait se produire lors de la prévisualisation d&#39;un contenu de diffusion après son édition.
* Correction d&#39;un problème qui pouvait se produire lors du traitement des fichiers zip au format CSV lors de l&#39;utilisation de l&#39;option Décompression.
* Correction d&#39;un problème dans Creative Designer qui entraînait l&#39;apparition d&#39;un formatage et d&#39;une couleur de police non souhaités lors du changement d&#39;un texte avec un style intégré en un lien ou lors de l&#39;édition de ce lien. (CAMP-26001)
* Correction d&#39;un problème qui empêchait le rapport Hot clicks d&#39;afficher les pourcentages pour chaque condition dans les diffusions comportant du contenu dynamique. Auparavant, seuls les clics sur la variante par défaut étaient affichés.

## Version 18.6 - Juin 2018 {#release-18-6---june-2018}

**Améliorations**

* L&#39;API **[!UICONTROL History]** a été ajoutée à Adobe.IO. Elle permet d&#39;accéder aux informations relatives à l&#39;historique marketing d&#39;un profil : nombre de points de contact, diffusions envoyées, URL de page miroir, etc. Voir à ce propos le [cas pratique dédié](../../api/using/interacting-with-marketing-history.md) .
* Le workflow technique **[!UICONTROL Nettoyage de la base]** a été optimisé pour améliorer les performances du nettoyage de la base de données.
* Creative Designer pour les emails est désormais disponible en français et en allemand.

**Autres changements**

* Un bouton **[!UICONTROL Calculer les statistiques]** a été ajouté à la fenêtre **[!UICONTROL Déploiement]** des diffusions envoyées. Il permet de récupérer les derniers KPI, par exemple si la mise à jour des résultats de l&#39;envoi prend trop de temps ou si les résultats n&#39;ont pas été pris en compte. Voir à ce propos cette [section](../../sending/using/confirming-the-send.md).
* Dans le workflow technique d&#39;usine **Mise à jour pour la délivrabilité**, les administrateurs fonctionnels peuvent maintenant définir le nombre d&#39;erreurs consécutives à ignorer dans l&#39;activité javascript **Mise à jour des règles**. Par défaut, la valeur du champ est définie sur 0, ce qui signifie que toutes les erreurs seront ignorées.
* Le code SQL généré lors de la gestion des conditions de restriction d&#39;accès à l&#39;entité a été optimisé.
* L&#39;activité **[!UICONTROL Mise à jour]** permet maintenant d&#39;ajouter, de mettre à jour ou de supprimer des données relatives aux abonnements (table nms:appSubscriptionRcp).
* Le workflow technique **[!UICONTROL Mise à jour de l&#39;exécution des diffusions]** a été divisé en deux workflows afin d&#39;optimiser les performances : - **[!UICONTROL Mise à jour de l&#39;exécution des diffusions]** : met à jour le tracking de la diffusion. Par défaut, il est démarré toutes les 10 minutes. **[!UICONTROL Mise à jour des indicateurs de diffusion]** : met à jour les indicateurs de performance clé (IPC) de la diffusion. Par défaut, il est démarré toutes les heures. Pour plus d&#39;informations sur les workflows techniques, voir cette [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Lorsqu&#39;une diffusion envoie des messages, le statut dans la section **[!UICONTROL Déploiement]** peut maintenant avoir deux valeurs : **[!UICONTROL Envoi]** : les messages sont en cours d&#39;envoi. **[!UICONTROL Envoi (nouvel essai)]** : un nouvel essai est en cours.
* Les utilisateurs disposant du rôle **[!UICONTROL Préparation de la diffusion]** peuvent maintenant envoyer des bons à tirer. (CAMP-24313)
* L&#39;option **Activer TLS via SMPP** a été ajoutée au compte externe **Routage des SMS par SMPP**. Voir à ce propos cette [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Correctifs**

* Correction d&#39;une erreur qui empêchait l&#39;envoi des e-mails lors de l&#39;inclusion d&#39;une image dynamique depuis Adobe Target (CAMP-24848).
* Correction d&#39;une erreur liée aux workflows techniques **[!UICONTROL Demande d&#39;accès/de suppression des informations personnelles]**. Ils ne se terminaient pas en cas d&#39;échec d&#39;une des demandes.
* Correction d&#39;une erreur qui empêchait Privacy Core service de recevoir les mises à jour des statuts de demande de Campaign.
* Correction d’une erreur qui empêchait le fonctionnement correct du workflow technique **[!UICONTROL Import de l&#39;audience partagée]** (CAMP-25465).
* Correction d&#39;une erreur qui empêchait les demandes d&#39;accès aux informations personnelles de Campaign d&#39;être marquées comme étant terminées dans Privacy Core Service.
* Correction d&#39;une erreur qui empêchait certains utilisateurs de se connecter à Campaign Standard via l&#39;authentification IMS lorsque l&#39;Adobe ID était trop long. (CAMP-24095)
* Correction d&#39;une erreur dans Creative Designer qui se produisait lors de la suppression de modules de contenu. (CAMP-25242)
* Correction d&#39;une erreur lors de l&#39;utilisation des règles de fatigue des notifications push pour les abonnés sans profil dans la base de données. (CAMP-25344)
* Correction d&#39;une erreur qui affichait un message d&#39;erreur lors de l&#39;accès aux exclus des diffusions. (CAMP-24724)
* Correction d&#39;une erreur qui empêchait la préparation des bons à tirer dans les instances avec des envois étendus.
* Correction de deux erreurs qui se produisaient lors de la publication de ressources personnalisées avec l&#39;extension des **[!UICONTROL Envois]** activée.
* Correction d&#39;une erreur liée à la non-prise en compte de la durée de la diffusion dans les diffusions récurrentes.
* Correction d&#39;une erreur qui se produisait lors du tri des données dans le menu **[!UICONTROL Données client]** pour les ressources personnalisées comprenant plus de 100 000 enregistrements. (CAMP-24308)
* Correction d&#39;une erreur liée aux dimensions de profil personnalisées qui n&#39;étaient pas prises en compte lors de l&#39;utilisation de la fonction de recherche dans les rapports dynamiques.
* Correction d&#39;une erreur liée à l&#39;affichage des données internationales pour les niveaux de compte dans les rapports dynamiques.
* Il est désormais possible de créer un service sans message de confirmation d&#39;abonnement ou de désabonnement.

## Version 18.5 - Mai 2018 {#release-18-5---may-2018}

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

**Améliorations**

* Amélioration de l&#39;utilisation globale de la mémoire et du processeur par l&#39;application

**Autres changements**

* L&#39;activité de workflow Lecture d&#39;audience peut désormais lire les audiences Experience Cloud. Cette activité ne pouvait auparavant lire que les audiences de type Requête et Liste. Consultez la [documentation détaillée](../../automating/using/read-audience.md). (CAMP-23623)
* L&#39;identifiant de la Source de données partagée par défaut est désormais en lecture seule uniquement et ne peut plus être modifié. La modification de cet identifiant peut entraîner des problèmes lors du partage d&#39;audiences avec Experience Cloud.
* L&#39;import d&#39;audiences depuis Audience Manager est désormais possible avec des fichiers partagés. Auparavant, seul le dernier fichier du segment était importé par le workflow technique importSharedAudience.
* Les comptes externes d&#39;AWS S3 prennent désormais en charge les régions et le mécanisme d&#39;authentification en version 4. Consultez la [documentation détaillée](../../administration/using/external-accounts.md).
* La fenêtre de sélection de ressources se charge plus rapidement et permet de sélectionner une ressource, puis d&#39;être fermée sans problème.
* Les propriétés et la structure des workflows techniques peuvent désormais être modifiées par les utilisateurs disposant de droits d&#39;administration et appartenant aux entités organisationnelles et géographiques &quot;Toutes&quot;.
* Des améliorations ont été apportées à l&#39;interface de l&#39;activité Segmentation lors de la création de nouveaux segments : l&#39;onglet Limitation apparaît désormais directement après avoir ajouté une limitation. De nouveaux noms de segments sont maintenant incrémentés (&quot;Segment 1&quot;, &quot;Segment 2&quot;, etc.).
* Un champ &quot;nextProcessingDate&quot; est ajouté à la ressource Workflow. Ce champ n&#39;est visible que via les appels d&#39;API REST ; il vous permet de visualiser les dates de prochain traitement des workflows.
* Le champ &quot;sourceId&quot; est désormais affiché dans la ressource de tracking (nms:trackingLog).
* Les valeurs &quot;Nombre total d&#39;ouvertures&quot; et &quot;Nombre total de clics&quot; peuvent désormais être exportées dans un fichier plat via un workflow. (CAMP-24186)
* &quot;Anglais - Danemark&quot; est désormais disponible dans la liste des Préférences linguistiques au sein des profils. (CAMP-23728)
* Lors de l&#39;utilisation d&#39;une activité Segmentation avec un lien Données additionnelles (targetData), un message vous informe désormais que les données ne sont pas disponibles en dehors du workflow. Ce message s&#39;affiche lorsque vous cliquez sur le bouton Compter ou Aperçu depuis l&#39;activité Segmentation. (CAMP-23651)
* Des améliorations ont été réalisées pour optimiser l&#39;espace disque utilisé par les workflows : (CAMP-21979) : les fichiers traités par l&#39;activité &quot;Chargement de fichier&quot; sont désormais supprimés par défaut. Une option vous permet de les conserver en cas de besoin. Lorsqu&#39;un workflow est supprimé, son dossier dédié est automatiquement supprimé du répertoire du serveur.

**Correctifs**

* Correction d&#39;un problème selon lequel des événements de reporting bruts n&#39;avaient pas d&#39;événements de suivi associés, car le champ eventDate n&#39;était pas correctement rempli.
* Correction d&#39;un problème qui empêchait des champs personnalisés de s&#39;afficher dans la fenêtre d&#39;aperçu d&#39;une diffusion de notification push.
* Correction d&#39;un problème qui empêchait le texte d&#39;être renvoyé à la ligne dans le corps du message d&#39;une notification push dans la fenêtre d&#39;aperçu.
* Correction d&#39;un problème lors de l&#39;envoi d&#39;une diffusion récurrente provenant d&#39;un workflow lorsque la cible principale est vide.
* Correction d&#39;un problème qui empêchait l&#39;accès à un mapping de ciblage si celui-ci est lié à un schéma inexistant.
* Correction d&#39;un problème qui pouvait se produire lors de l&#39;importation d&#39;un fichier zip via une activité Chargement de fichier. (CAMP-24309)
* Correction d&#39;un problème qui entraînait une erreur PostgreSQL lors de l&#39;envoi d&#39;une diffusion récurrente. (CAMP-23613)
* Correction d&#39;un problème qui affichait un message d&#39;erreur lors de l&#39;envoi d&#39;une requête API REST avec un attribut JSON vide. (CAMP-23506)
* Correction d&#39;un problème de basculement en majuscule des caractères suivant le caractère &quot;ß&quot; dans les profils. (CAMP-23136)
* Correction d&#39;un problème lors de l&#39;envoi de diffusions utilisées avec les conditions d&#39;éligibilité d&#39;un bloc de contenu dynamique ou de personnalisation, tout en utilisant des attributs provenant d&#39;un schéma de profil lié. (CAMP-22751)
* Correction d&#39;un problème qui empêchait la suppression de services. (CAMP-22050)
* Correction d&#39;un problème qui empêchait de modifier les valeurs Pays ou Etat dans un Profil de test. (CAMP-20426)
* Correction d&#39;un problème qui pouvait empêcher le chargement de Creative Designer. (CAMP-24573)
* Correction d&#39;un problème qui supprimait les caractères ajoutés après des champs de personnalisation dans l&#39;objet d&#39;un email. (CAMP-24113)

## Version 18.4 - Avril 2018       {#release-18-4---april-2018}

**Correctifs**

_Plate-forme_

* Corrections d&#39;une erreur qui pouvait empêcher le bon traitement des demandes d&#39;accès ou de suppression du RGPD. Ce comportement a été observé dans de rares cas lorsque les données extraites contenaient l&#39;un des caractères suivants : &amp; &lt; > &quot; &#39;.

_Emails, SMS et courrier_

* Correction d&#39;un problème qui pouvait entraîner le remplacement des KPI par des valeurs incorrectes si la synchronisation du broadlog prenait plus d&#39;une heure.

_Workflows_

* Gestion améliorée de la mémoire et optimisation des performances dans les workflows.

_Reporting_

* Le workflow de partage des KPI récupère désormais les valeurs des diffusions pour les deux derniers mois au lieu des six derniers. Correction d&#39;un problème lié au compte externe de partage des KPI qui affichait des dates tronquées.
* Correction d&#39;un problème qui pouvait entraîner la non-prise en compte de certains messages dans les mesures **Envoyés**, **Délivrés** et **Bounce**.
* Correction d&#39;un problème qui survenait lorsque la période choisie dans le **Rapport Synthèse des diffusions** était trop étendue.

_Ressources personnalisées_

* Correction d&#39;une erreur qui entraînait l&#39;échec de la préparation des ressources personnalisées.

## Version 18.3 - Mars 2018       {#release-18-3---march-2018}

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
   <td> Règlement général sur la protection des données (RGPD) de l'UE<br /> </td> 
   <td> Le RGPD, qui entrera en vigueur le 25 mai 2018, est la nouvelle loi de l'Union européenne (UE) sur la protection de la vie privée. Il harmonise et modernise les exigences en matière de protection des données. Il s'applique aux clients Adobe Campaign qui détiennent des données pour des titulaires de données résidant dans l'UE.<br /> Outre les fonctionnalités de protection des données déjà disponibles dans Adobe Campaign (notamment la gestion du consentement, les paramètres de conservation des données et les rôles utilisateur), nous incluons, en qualité de responsable du traitement des données, d'autres fonctionnalités pour faciliter votre préparation en tant que contrôleur de données à certaines demandes RGPD:<br /> 
    <ul> 
     <li> Droit d'accès : permet au titulaire de données de recevoir une copie de ses données personnelles collectées par les contrôleurs de données, notamment les données éventuellement stockées dans Adobe Campaign. </li> 
     <li> Droit de suppression : autorise le titulaire de données à demander la suppression de ses données personnelles collectées par les contrôleurs de données, notamment les données éventuellement stockées dans Adobe Campaign. </li> 
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
    </ul> Creative Designer pour les emails est disponible uniquement en anglais.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentation détaillée</a> et regardez cette <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vidéo</a>.<br /> </td> 
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

**Correctifs**

_Plate-forme_

* Correction d&#39;un problème qui empêchait l&#39;export de plus de 5 000 enregistrements d&#39;une liste.
* Correction d&#39;un problème lors de l&#39;export de données vers des fichiers nommés avec des champs de personnalisation.

_Emails, SMS et courrier_

* Correction d&#39;un problème qui entraînait la troncature des SMS en plusieurs parties, car la taille des parties était calculée en caractères et non en octets.
* Ajout d&#39;une option permettant de mettre à jour en temps réel le KPI **[!UICONTROL Délivrés]** ou **[!UICONTROL Bounces + erreurs]** après l&#39;envoi de la diffusion. Ils sont directement recalculés à partir du SR (Status Report) reçu du fournisseur.
* Correction d&#39;un problème lié au widget de calendrier dans le planificateur de diffusion.
* Correction d&#39;un problème d&#39;affichage lors de l&#39;ouverture d&#39;une cible pour la seconde fois dans une diffusion envoyée.
* Correction d&#39;un problème qui entraînait l&#39;affichage d&#39;un message d&#39;erreur demandant une date de début lors de la création d&#39;un modèle d&#39;email avec une date d&#39;envoi différée.
* Correction d&#39;une erreur qui entraînait des problèmes de rendu d&#39;image lors de l&#39;édition du contenu d&#39;une diffusion.
* Correction d&#39;un problème lié aux bons à tirer lors de la duplication d&#39;une campagne.
* Correction d&#39;une erreur qui entraînait l&#39;affichage d&#39;un message d&#39;erreur lors de l&#39;accès à un modèle de campagne via la barre de navigation, après l&#39;ajout d&#39;une diffusion au workflow.
* Correction d&#39;un problème qui empêchait la sélection automatique du gagnant d&#39;un email de test A/B, ce qui entraînait le non-envoi de l&#39;email. Ce problème se produisait lorsque l&#39;état de la diffusion était **[!UICONTROL retryInProgress]**.
* Correction d&#39;un problème qui entraînait l&#39;affichage d&#39;un message d&#39;erreur lors de la réouverture des paramètres d&#39;un email de test A/B.

_Audiences et requêtes_

* Correction d&#39;un problème qui empêchait d&#39;accéder aux données et de configurer des requêtes pour les destinataires répliqués d&#39;Adobe Campaign Classic vers Standard.
* Correction d&#39;un problème qui se produisait lors de l&#39;utilisation d&#39;un champ de type filtre dans l&#39;éditeur de requêtes, après avoir utilisé le bouton **Compter** ou **Prévisualiser**.

_Workflows_

* Le workflow **Facturation** a été optimisé pour réduire le délai de préparation de la diffusion.
* Correction d&#39;un problème qui empêchait l&#39;affichage des données de population dans une transition sortante lors de l&#39;utilisation d&#39;une activité de diffusion récurrente.
* Correction d&#39;un problème qui empêchait l&#39;affichage des enregistrements de rejet dans une transition après une activité **Mise à jour de données**.
* Correction d&#39;un problème qui entraînait l&#39;échec du workflow technique **deliverabilityUpdate**.

_Intégrations_

* Correction d&#39;un problème qui empêchait d&#39;envoyer correctement des caractères internationaux à Adobe Analytics.
* Les ressources doivent à présent se charger plus rapidement lorsque vous insérez une image dans un message depuis votre bibliothèque de ressources Experience Cloud.
* Correction d&#39;un problème qui empêchait, dans certains cas, la fermeture de la fenêtre de sélection de ressources.
* Depuis le détail d&#39;une source de données, vous pouvez à présent accéder directement au workflow associé pour en vérifier l&#39;état.
* Vous pouvez maintenant mettre directement à jour le schéma Triggers lors de la définition ou de l&#39;édition d&#39;un événement de trigger. Grâce à cette modification, vous n&#39;avez plus à dépublier le trigger et en créer un autre.

_Messages transactionnels_

* Correction d&#39;une erreur liée au modèle de message transactionnel lors de l&#39;extension de la ressource de diffusion.
* Il est maintenant possible de supprimer les messages transactionnels.

## Version 18.2 - Février 2018       {#release-18-2---february-2018}

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
   <td> Abonnement : abonnez ou désabonnez une liste de profils à plusieurs services.<br /> </td> 
   <td> L'activité de workflow <strong>Services d'abonnements</strong> permet désormais d'abonner ou de désabonner une liste de profils à plusieurs services. Dans votre workflow, importez un fichier contenant les profils, et pour chaque profil, le type d'opération et le service. L'activité <strong>Services d'abonnements</strong> pourra utiliser ces informations et gérer dynamiquement tous les abonnements et désabonnements des profils en même temps.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/subscription-services.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Activité d'enrichissement : enrichissez les données en fonction des transitions précédentes.<br /> </td> 
   <td> La nouvelle activité de workflow <span class="uicontrol">Enrichissement</span> permet d'utiliser les transitions entrantes et de compléter la transition sortante avec des données additionnelles. Si vous ciblez des profils, l'activité d'enrichissement vous permet d'enrichir les informations des profils avec des données additionnelles qui ne sont pas stockées dans la base de données (issues d'un fichier importé, par exemple).<br /> Pour plus d'informations, consultez la <a href="../../automating/using/enrichment.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Plate-forme_

* Mise à jour de la barre supérieure de l&#39;interface d&#39;Adobe Campaign avec le nouveau menu d&#39;Experience Cloud.
* Correction d&#39;une erreur qui empêchait l&#39;affichage du lien vers les **[!UICONTROL Offres]** dans la liste déroulante de la solution.

_Emails, SMS et courrier_

* Amélioration de la phase de préparation des diffusions pour optimiser les performances.
* Correction de plusieurs problèmes qui entraînaient l&#39;endommagement du tracking dans certains cas très spécifiques.
* Correction d&#39;un problème de mise à jour de date de contact qui se produisait lorsque la date de contact était modifiée entre la préparation de la diffusion et sa validation. Vous pouvez modifier la date de contact après la préparation. Vous devrez toutefois préparer à nouveau la diffusion avant de pouvoir valider l&#39;envoi. Consultez la [documentation détaillée](../../sending/using/preparing-the-send.md)..

_Notifications push_

* Correction d&#39;une erreur qui empêchait certains champs de personnalisation de fonctionner dans les notifications push iOS.
* Correction d&#39;une erreur qui affichait des taux de clic et d&#39;ouverture de 0 % dans le tableau de bord des notifications push.

_Rapports_

* Correction d&#39;une erreur qui affichait une liste de rapports vide dans certains navigateurs.
* Correction d&#39;une erreur qui se produisait dans le workflow technique **[!UICONTROL Partage des rapports]** juste avant l&#39;atteinte de sa limite de validité.

_Workflows_

* Correction d&#39;un problème qui empêchait l&#39;accessibilité des activités après les avoir placées dans un workflow.
* Correction d&#39;un problème qui entraînait, dans certains cas, la modification de l&#39;ordre des transitions en sortie d&#39;une activité **[!UICONTROL Segmentation]**.
* Correction d&#39;une erreur qui se produisait lors de la lecture d&#39;une audience contenant un champ de type énumération et ayant été précédemment enregistrée dans un workflow.
* Correction d&#39;une erreur suite à laquelle l&#39;option **[!UICONTROL Demander une confirmation avant d&#39;envoyer les messages]** restait cochée même après avoir été décochée pendant la définition des propriétés de planification d&#39;une diffusion créée dans un workflow.
* La suppression automatique des doublons (clause DISTINCT) peut désormais être désactivée dans les activités **[!UICONTROL Requête]**, via une nouvelle option située dans l&#39;onglet **[!UICONTROL Données additionnelles]**. Pour des raisons de performance, il est recommandé de décocher cette option si vous définissez de nombreuses données additionnelles (plus de 100).

_Intégrations_

* Certaines améliorations ont été apportées à l&#39;écran de configuration **[!UICONTROL Sources de données]**.

_Problèmes connus_

Il est recommandé de ne pas utiliser Internet Explorer version 11 en raison de certains problèmes d&#39;affichage possibles.

Certains problèmes peuvent se produire lors de l&#39;utilisation des liens d&#39;aide contextuelle dans l&#39;interface de Campaign. Ils seront résolus dans la version 18.3.

## Version 18.1 - Janvier 2018       {#release-18-1---january-2018}

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
   <td> Reporting pour la gestion de la fatigue<br /> </td> 
   <td> Le reporting pour la gestion de la fatigue offre un rapport dédié configurable qui montre l'impact des règles de fatigue sur les diffusions via les canaux Email, Push, SMS et Courrier pendant une période spécifiée avant l'envoi. Grâce à la possibilité de détecter rapidement toutes les campagnes en conflit dans une seule vue, les marketeurs peuvent planifier les campagnes marketing en conséquence afin de définir les règles de fatigue plus efficacement et hiérarchiser les communications.<br /> Pour plus d'informations, consultez la <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentation détaillée</a>.<br /> </td> 
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
   <td> Il est désormais possible de déclencher une activité Signal pour vos workflows directement depuis l'API Adobe Campaign Standard.<br /> Pour plus d'informations, consultez la <a href="/help/api/using/triggering-a-signal-activity.md">documentation détaillée</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Plate-forme_

* La recherche de profils a été optimisée afin d&#39;améliorer les performances.
* L&#39;identifiant interne des groupes de sécurité par défaut est désormais en mode de lecture seule pour les utilisateurs standard.

_Emails, SMS et courrier_

* Correction d&#39;une erreur d&#39;affichage qui se produisait lors de l&#39;insertion d&#39;emojis dans le contenu des diffusions.
* Correction d&#39;une erreur qui permettait à l&#39;utilisateur d&#39;accéder aux envois alors que la diffusion était toujours en édition.
* L&#39;activité **[!UICONTROL Planificateur]** permet désormais d&#39;envoyer des diffusions selon le fuseau horaire du destinataire.
* SMS : l&#39;option **[!UICONTROL Stocker les MO entrants]** dans la base de données a été ajoutée aux comptes externes. Lorsque cette option est cochée, tous les SMS entrants sont stockés dans la table **inSMS**.
* SMS : les services sont désormais attachés à un événement au lieu d&#39;un modèle transactionnel.
* SMS : le timeout des connexions SMTP par défaut a été réduit à 30 secondes.

_Notifications push_

* Correction d&#39;une erreur qui empêchait l&#39;arrêt des diffusions des notifications push.
* Ajout d&#39;une option aux options avancées des notifications push qui permet de mettre en éveil une application à l&#39;aide d&#39;une notification push.
* Ajout d&#39;un bouton de pause pour la vidéo de prévisualisation des notifications push.
* La prévisualisation des notifications push est désormais possible pour différents appareils tels que les iPhone, Android ou les tablettes.

_Rapports_

* Correction d&#39;une erreur qui affichait des taux supérieurs à 100 %.
* Correction d&#39;une erreur qui empêchait les utilisateurs de télécharger les rapports au format CSV.
* Ajout d&#39;un nouvel élément **[!UICONTROL Rapport]** sur la page d&#39;accueil.

_Workflows_

* Correction d&#39;un problème qui entraînait l&#39;affichage d&#39;un message d&#39;erreur lors de l&#39;utilisation de données additionnelles dans une requête et de l&#39;ajout d&#39;alias contenant des espaces. Les caractères qui ne sont pas alphanumériques ont été remplacés par &quot;_&quot;.
* Correction d&#39;une erreur qui entraînait dans certains cas l&#39;arrêt par défaut du workflow technique calculant les KPI.

_Profils et audiences_

* Correction d&#39;une erreur qui se produisait lors de l&#39;ajout de plusieurs filtres à une requête d&#39;audience.
* Correction d&#39;une erreur qui se produisait lors du changement de la photo d&#39;un profil.
* Ajout d&#39;une info-bulle affichant le nombre de résultats exact après le comptage de la population d&#39;une requête.
* Correction d&#39;une erreur qui empêchait un utilisateur de sélectionner une audience ou de fermer la fenêtre du sélecteur d&#39;audience.
* Mise à jour de la liste des fonctions disponibles dans l&#39;éditeur d&#39;expression. Suppression des fonctions **FormatCurrency** et **ConvertCurrency**.

