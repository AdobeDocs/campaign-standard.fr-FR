---
title: Notes de mise à jour 2015-2016
description: Cette page répertorie toutes les versions 2015 et 2016 d'Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d1ec5dddcf4c1aa3fe6338d35b381986ba32a28d

---


# Notes de mise à jour 2015-2016{#release-notes}

Vous recherchez une version 2015-2016 spécifique d&#39;Adobe Campaign Standard ?

Chaque version contient des nouvelles fonctionnalités et correctifs. Cliquez sur une version pour consulter son contenu.

Découvrez les [mises à jour les plus récentes de la documentation](../../rn/using/documentation-updates.md) d&#39;Adobe Campaign Standard. Si vous recherchez une note de mise à jour plus récente, consultez cette [page](../../rn/using/release-notes.md).

## Version 16.11 - Novembre 2016 {#release-16-11---november-2016}

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
   <td> Règles d'exclusion de délivrabilité<br /> </td> 
   <td> Une liste de suppression globale cryptée est désormais gérée dans l'instance de délivrabilité afin d'éviter tout blacklistage lié à une activité malveillante, notamment l'utilisation d'un spam trap (piège à spam).<br /> Pour chaque diffusion e-mail, deux règles de typologie par défaut comparent les adresses email des destinataires aux adresses ou noms de domaine interdits contenus dans une liste de suppression globale gérée dans l'instance de délivrabilité. S'il existe une correspondance, le message n'est pas envoyé au destinataire concerné.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimisation générale<br /> </td> 
   <td> Cette mise à jour contient de nombreux changements et correctifs qui permettent de résoudre des problèmes rencontrés par les clients. Les performances globales de la plateforme ont également été optimisées. <br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction de plusieurs problèmes de sécurité.
* Correction de plusieurs erreurs concernant les champs vides et les champs en double dans l&#39;API REST.
* Il est désormais possible de créer des messages SMS et des notifications push directement à partir de la page d&#39;accueil de l&#39;application.

_Emails et SMS_

* Correction d&#39;une erreur qui empêchait les utilisateurs de télécharger des fichiers zip dans l&#39;éditeur de contenu.
* Correction d&#39;une erreur qui empêchait l&#39;ouverture d&#39;un bon à tirer après son envoi.
* Résolution d&#39;un problème qui entraînait l&#39;affichage d&#39;un message d&#39;erreur lors de l&#39;accès au rapport **[!UICONTROL Hot Clicks]**à partir d&#39;un email de type test A/B.
* Correction d&#39;une erreur qui empêchait la prise en compte de modifications effectuées en mode **[!UICONTROL Afficher la source]**.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;import des fichiers de modèle XML d&#39;objet prédictif.
* Un nouvel écran dédié à l&#39;import de données pour le modèle entraîné des objets est désormais accessible dans **[!UICONTROL Administration > Canaux > Emails > Objet prédictif]**.
* Correction d&#39;une erreur qui permettait aux utilisateurs non-administrateurs d&#39;éditer des masques autorisés dans l&#39;écran de configuration des emails.

_Notifications push_

* Correction d&#39;une erreur qui empêchait l&#39;affichage des envois et des logs d&#39;événement des destinataires après l&#39;envoi d&#39;une notification push utilisant le modèle **[!UICONTROL Diffuser par notification push (vers profils)]**.
* Correction d&#39;une erreur qui pouvait empêcher la création de nouvelles applications mobiles.

_Workflows_

* Résolution d&#39;un problème de performance lors de l&#39;utilisation de l&#39;activité **[!UICONTROL Inscription]**.
* Correction d&#39;une erreur qui empêchait un workflow de fonctionner lorsque son nom interne contenait une espace.

_Intégrations_

* Résolution d&#39;un problème qui pouvait entraîner l&#39;affichage d&#39;une erreur lors de l&#39;utilisation de l&#39;option **Image partagée depuis Adobe Experience Cloud** dans un email.

_Ressources personnalisées_

* Amélioration de la prévisualisation des logs des API entre deux publications de champs d&#39;API étendus.
* Correction d&#39;une erreur qui empêchait la suppression d&#39;une ressource personnalisée avant sa publication.
* Correction d&#39;une erreur qui empêchait l&#39;extension des profils et la définition des clés d&#39;identifiant avec un champ dynamique.
* Correction d&#39;une erreur qui pouvait survenir lors de l&#39;ajout de liens à une ressource personnalisée.

## Version 16.10 - Octobre 2016 {#release-16-10---october-2016}

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
   <td> Optimisation prédictive de l'objet des emails<br /> </td> 
   <td> Lors de l'édition d'un email, une nouvelle option permet de tester différents objets et d'obtenir une estimation du taux d'ouverture de l'email avant envoi. Ces résultats sont rendus possibles à l'aide de modèles créés en analysant les données de vos anciennes diffusions ou de modèles prédéfinis spécifiques à votre secteur d'activité. Cette fonctionnalité est disponible pour les emails et les bases de données dont le contenu est en anglais uniquement. <br /> Pour plus d'informations sur l'activation et l'utilisation de cette fonctionnalité, consultez la <a href="../../designing/using/subject-line.md#predictive-subject-line">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messages transactionnels : canal SMS<br /> </td> 
   <td> Le canal SMS a été ajouté aux fonctionnalités des messages transactionnels d'Adobe Campaign. Deux canaux sont désormais pris en charge pour les messages transactionnels : email et SMS.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Message de relance pour les messages transactionnels<br /> </td> 
   <td> Il est désormais possible de créer un workflow ciblant un événement. Vous pouvez ainsi envoyer un message de relance aux clients qui ont reçu un message transactionnel. Vous pouvez filtrer la cible selon le type de l'événement, les broadlogs de l'événement et le tracking. Dans le message de rappel, vous pourrez utiliser le contenu de l'événement (payload). <br /> Pour plus d'informations, consultez la <a href="../../channels/using/follow-up-messages.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extension de l'API Profile &amp; Services<br /> </td> 
   <td> Vous pouvez désormais exposer les champs étendus dans l'API Profile &amp; Services. Le mécanisme de publication permet aux API de mapper les champs étendus des ressources personnalisées Profiles ou Services. Pour que ce mappage fonctionne, le rôle <strong>Datamodel</strong> a été ajouté. Ce nouveau rôle permet à l'utilisateur de configurer un groupe d'administrateurs qui auront accès au modèle de données.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction de plusieurs problèmes de sécurité.

_Emails et SMS_

* L&#39;écran de paramétrage des comptes externes SMS (**[!UICONTROL Administration > Canaux > SMS > Comptes SMS]**) a été amélioré. Plusieurs paramètres ont été ajoutés à la section**[!UICONTROL  Spécificités du SMSC]** afin de prendre en charge les codes d&#39;erreur du champ &quot;Texte&quot;.

_Notifications push_

* Correction d&#39;un problème qui empêchait l&#39;affichage des filtres prédéfinis lors de l&#39;édition de l&#39;audience d&#39;une notification push créée à partir du modèle **[!UICONTROL Diffuser par notification push]**(mobileApp).
* L&#39;écran de paramétrage des applications mobiles (**[!UICONTROL Administration > Canaux > Notification push > Applications mobiles]**) affiche désormais un message indiquant que la plateforme iOS ou Android a été créée avec succès.

_Landing pages_

* Correction de problèmes qui empêchaient l&#39;envoi des emails de confirmation lorsque le formulaire d&#39;une landing page était validé.

_Audiences et requêtes_

* Correction de plusieurs problèmes qui survenaient lors de la sélection d&#39;un profil dans l&#39;éditeur de requêtes.

_Messages transactionnels_

* Correction d&#39;une erreur qui empêchait la dépublication d&#39;un modèle transactionnel.
* Correction d&#39;un problème qui entraînait l&#39;affichage des événements déclencheur dans la liste des événements.

_Intégrations_

* Correction d&#39;un problème qui empêchait l&#39;utilisation d&#39;une audience partagée dans une diffusion après la mise à jour de cette audience.
* Correction d&#39;un problème qui empêchait l&#39;utilisation d&#39;une ressource partagée (option **[!UICONTROL Image partagée depuis Adobe Experience Cloud]**) dans une page d&#39;entrée.
* Correction de problèmes qui survenaient lors de l&#39;édition d&#39;une audience partagée importée depuis Adobe Audience Manager.

## Version 16.9 - Septembre 2016 {#release-16-9---september-2016}

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
   <td> Remarketing Triggers<br /> </td> 
   <td> L'intégration entre le core service <span class="uicontrol">Triggers</span> et Adobe Campaign permet d'envoyer des emails personnalisés à vos clients en réaction à des comportements spécifiques trackés sur votre site Web par Adobe Analytics (dans un délai de 15 minutes).<br /> Dans Adobe Experience Cloud, vous définissez les différents Triggers, c'est-à-dire les comportements des clients que vous souhaitez suivre, comme les clients qui ont abandonné leur panier ou formulaire, supprimé un produit du panier ou dont la session a expiré. Lors de la création d'un trigger, vous définissez la condition du trigger et les données qui seront envoyées à Adobe Campaign dans l'événement (pload). <br /> Dans Adobe Campaign, vous sélectionnez le trigger qui a été précédemment créé, vous enrichissez les données de l'événement avec celles du datamart et vous définissez un modèle de message transactionnel lié au trigger. Par exemple, lorsqu'un client abandonne son panier, un événement est envoyé à Adobe Campaign. Adobe Campaign peut ensuite utiliser cet événement par le biais d'un email de remarketing envoyé au client dans un délai de 15 minutes.<br /> Pour plus d'informations, consultez la <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messages transactionnels : pause / dépublication<br /> </td> 
   <td> Vous pouvez désormais suspendre la publication d'un modèle transactionnel pendant la mise à jour de son contenu. Les messages correspondants ne sont plus envoyés, mais ils sont stockés dans la base de données. A la reprise, les messages placés dans la file d'attente sont traités et envoyés s'ils n'ont pas expiré.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">documentation détaillée</a>.<br /> Vous pouvez désormais dépublier des événements et des modèles transactionnels. Les messages correspondants ne sont plus envoyés et ils ne sont pas stockés dans la base de données.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> Les clients qui ont plusieurs marques peuvent désormais les gérer dans une même instance. La fonctionnalité de branding est gérée par l'administrateur de votre instance Adobe Campaign. Elle permet de configurer de manière centrale tous les paramètres liés à une marque dans Adobe Campaign, notamment le logo et des paramètres plus techniques comme les URL de tracking, le Web Analytics, l'URL du serveur, le nom du domaine, etc.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/branding.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperçu du responsive design des emails<br /> </td> 
   <td> Cette fonctionnalité permet de tester la réactivité des emails sur différents types d'appareils. Dans l'écran de prévisualisation des emails, une grille a été ajoutée afin de tester les emails sur différentes tailles d'écran.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifications push<br /> </td> 
   <td> Un nouveau canal a été ajouté afin de permettre aux marketeurs d'envoyer des notifications Push personnalisées et segmentées sur des appareils mobiles iOS et Android. Les messages peuvent être envoyés dans le cadre d'une diffusion ou à l'aide d'une activité de workflow. La compatibilité avec les messages transactionnels sera assurée dans les prochaines versions. Ce canal utilise le SDK Mobile core service (disponible <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">ici</a>).<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-push-notifications.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Cette version introduit de nouvelles fonctionnalités de filtrage et de recherche dans les listes de l&#39;interface. Ces nouvelles fonctionnalités sont par exemple disponibles dans les logs (diffusion, tracking), les audiences et les transitions de workflow.
* Correction de plusieurs problèmes d&#39;affichage concernant le nombre de points de contact dans un profil client.
* Correction de plusieurs problèmes liés aux typologies.

_Emails et SMS_

* Correction d&#39;une erreur qui permettait d&#39;éditer des bons à tirer erronés. Ils sont désormais en lecture seule.
* Correction d&#39;un problème qui entraînait le blacklistage d&#39;un destinataire lorsqu&#39;un SMS était trop long ou qu&#39;il rencontrait des problèmes d&#39;encodage.

_Ressources personnalisées_

* Correction d&#39;une erreur qui empêchait l&#39;affichage de tous les résultats lors de l&#39;utilisation des filtres avancés d&#39;une ressource personnalisée.

_Messages transactionnels_

* Un préfixe est désormais automatiquement ajouté à l&#39;identifiant d&#39;une nouvelle définition d&#39;événement.
* L&#39;icône représentant les messages transactionnels dans l&#39;interface a été changée.

_Intégrations_

* Correction d&#39;une erreur d&#39;affichage qui survenait lorsqu&#39;une image haute résolution était insérée par le biais de l&#39;option **Image dynamique servie par Adobe Target**.
* Correction d&#39;une erreur qui permettait d&#39;enregistrer une audience partagée même si l&#39;identifiant de la destination (destination ID) n&#39;était pas défini dans l&#39;AMC Data Source.

## Version 16.7 - Juillet 2016 {#release-16-7---july-2016}

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
   <td> Messages transactionnels enrichis<br /> </td> 
   <td> Il est désormais possible de lier les modèles transactionnels à la base de données Adobe Campaign afin de récupérer des informations permettant d'enrichir le contenu des messages transactionnels.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL dynamiques pour les images<br /> </td> 
   <td> Cette nouvelle fonctionnalité permet de personnaliser la source d'une image en insérant des blocs de contenu et du texte dynamique à des fins de tracking et de personnalisation.<br /> Il devient entre autres possible de profiter des fonctionnalités de médias dynamiques d'AEM Asset (S7) en passant des paramètres dans les URL des images. Vous pouvez par exemple envoyer un email avec des images personnalisées indiquant “Bonjour Alexandre, découvrez nos prochains événements à Paris !” ou “Bonjour Frank, découvrez nos prochains événements à New York !”.<br /> Pour plus d'informations, consultez la <a href="../../designing/using/personalization.md#personalizing-urls">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration avec People core service<br /> </td> 
   <td> Les identifiants Adobe Experience Cloud de type <strong>Declared ID</strong> sont désormais pris en charge par l'intégration entre Adobe Campaign et People core service (Profiles &amp; Audiences).<br /> Vous pouvez ainsi importer des segments et exporter des audiences composées de <strong>Visitor ID</strong> ou de <strong>Declared ID</strong>.<br /> Pour plus d'informations, consultez la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Logs de diffusion <br /> </td> 
   <td> Les logs MTA (serveur de diffusion) affichent désormais l'historique complet de chaque message, notamment toutes les tentatives d'envoi ainsi que les statuts d'erreur associés, et ce sans impact sur les performances de l'application.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction d&#39;une erreur qui pouvait provoquer l&#39;affichage de champs non pertinents au lieu des champs devant être renseignés après avoir modifié plusieurs fois l&#39;opérateur de comparaison lors de l&#39;édition d&#39;une condition dans une requête.
* Correction du comportement de l&#39;option **[!UICONTROL Les X derniers jours/mois/trimestres/années]**lors de la définition d&#39;une condition de filtrage de type relatif sur un champ de date. La période calculée est désormais glissante par rapport à la date et l&#39;heure du serveur et non plus calendaire.

_Workflows_

* Correction d&#39;une erreur qui renvoyait une mauvaise liste de valeurs dans l&#39;écran de sélection de la dimension de ciblage dans les propriétés d&#39;une activité de **[!UICONTROL Requête]**.
* Correction d&#39;une erreur qui forçait la sélection de l&#39;opérateur **existe** lors de l&#39;ajout d&#39;un agrégat de type moyenne ou comptage sur un élément d&#39;une collection dans une activité de **[!UICONTROL Requête]**.

_Edition de contenus_

* Correction d&#39;une erreur qui pouvait entraîner des problèmes d&#39;affichage (responsive design) lors de l&#39;import d&#39;un contenu HTML : les attributs de style ne sont plus réécrits lors de la première ouverture du contenu après l&#39;import.
* Correction d&#39;une erreur non bloquante provoquée lors de l&#39;ajout d&#39;une condition sur une variante d&#39;un contenu dynamique.
* Correction d&#39;une erreur provoquée lors de l&#39;ajout d&#39;une case à cocher dans le contenu d&#39;une landing page. La case à cocher était inutilisable.
* Correction d&#39;une erreur pouvant être provoquée lors de la suppression de texte dans un bloc si le curseur était placé au début du bloc en question.

_Messages transactionnels_

* Lors de l&#39;intégration à un site web, il est désormais possible de définir une date d&#39;expiration pour un événement donné. Une fois cette date passée, le message correspondant à l&#39;événement ne peut plus être envoyé.

## Version 16.6 - Juin 2016 {#release-16-6---june-2016}

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
   <td> Mise à disposition de l'API Profils et Services<br /> </td> 
   <td> L'API <span class="uicontrol">Profils et Services</span> d'Adobe Campaign est disponible sur le portail <a href="https://www.adobe.io/products/campaign">adobe.io</a>. Elle permet de mettre à jour, ajouter et supprimer des profils Adobe Campaign et les abonner ou désabonner à des services via des appels REST.<br /> Pour plus d'informations, consultez la <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">description détaillée de l'API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Les infobulles sont désormais désactivées sur les appareils mobiles afin de préserver la lisibilité des informations affichées à l&#39;écran.
* Correction d&#39;une erreur qui empêchait de faire défiler le contenu de certaines zones de l&#39;écran sur iPad.
* Correction de plusieurs erreurs de compatibilité rencontrées lors de l&#39;édition d&#39;un contenu sous Internet Explorer 11.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;accéder aux journaux détaillés lors du premier échec d&#39;un import de données.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;enregistrer un filtre de type intervalle.
* Correction d&#39;une erreur qui empêchait d&#39;afficher les éléments d&#39;une ressource lors de la configuration de l&#39;affichage d&#39;une liste.
* Correction d&#39;une erreur dans l&#39;explorateur de l&#39;éditeur de requête. Les résultats renvoyés par le champ de recherche étaient gardés en mémoire et restaient affichés à chaque nouvelle recherche.

_Emails et SMS_

* Correction d&#39;une erreur qui empêchait de récupérer les informations liées aux rebonds dans les journaux d&#39;une diffusion.
* Correction d&#39;une erreur qui empêchait d&#39;accéder au contexte dans un bloc de contenu dynamique d&#39;un message transactionnel.
* Correction d&#39;une erreur qui empêchait de définir un lien de type URL sur un texte dynamique dans le contenu d&#39;un email.
* Correction de l&#39;affichage de la barre supérieure de l&#39;assistant de création d&#39;une diffusion.
* La clé primaire d&#39;une diffusion ne peut plus être utilisée comme champ de personnalisation.

_Workflows_

* Les transitions entre deux activités d&#39;un workflow affichent désormais le comptage des éléments calculés et transmis d&#39;une activité à l&#39;autre.
* Les champs non compatibles sont désormais masqués lors de l&#39;ajout de données additionnelles dans une activité de **[!UICONTROL Requête]**.
* La fenêtre de définition d&#39;un agrégat lors de l&#39;ajout de données additionnelles a été améliorée afin de ne proposer que des options compatibles (par exemple : calculer une moyenne n&#39;est possible que sur des données numériques).
* Le démarrage ou redémarrage d&#39;un workflow technique d&#39;usine est désormais uniquement réalisable par un utilisateur disposant des droits d&#39;administration.

_Landing pages_

* Correction d&#39;une erreur qui pouvait tronquer les clés de chiffrement AES 32 bits dans les propriétés d&#39;une landing page.
* Correction d&#39;une erreur qui empêchait l&#39;éditeur de requête de s&#39;afficher correctement lors de la définition d&#39;une condition de visibilité ou lors de l&#39;ajout de contenu dynamique dans une landing page.

_Ressources personnalisées_

* L&#39;option **[!UICONTROL Définir des paramètres]**est désormais masquée lors de la définition d&#39;un filtre portant sur les abonnements à un service d&#39;un profil.
* Correction d&#39;une erreur qui pouvait être provoquée lorsqu&#39;un lien de type 0 - 1 était paramétré depuis une ressource personnalisée.
* Correction d&#39;une erreur qui empêchait, le cas échéant, d&#39;éditer la **Valeur par défaut constante** définie lors de l&#39;ajout d&#39;un champ de type **Date et heure** dans une ressource personnalisée.

## Version 16.5 - Mai 2016 {#release-16-5---may-2016}

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
   <td> Filtres prédéfinis<br /> </td> 
   <td> Les administrateurs ont désormais la possibilité de créer des filtres avancés qui apparaissent dans l'éditeur de requêtes sous forme de règles pré-paramétrées. La sélection de ces filtres permet aux utilisateurs d'élaborer plus facilement des paramétrages complexes dans une interface simplifiée, lors de la définition d'une audience par exemple.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/configuring-filter-definition.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : Services d'inscription<br /> </td> 
   <td> Une nouvelle activité <span class="uicontrol">Services d'inscriptions</span> permet d'inscrire ou de désinscrire plusieurs profils à un service en une seule action.<br /> Vous pouvez utiliser cette activité après avoir effectué un ciblage ou importé un fichier avec des données identifiées.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/subscription-services.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : enrichissement de données<br /> </td> 
   <td> L'onglet <span class="uicontrol">Données additionnelles</span> est maintenant disponible dans les activités de type <span class="uicontrol">Requête. </span> Cette fonctionnalité permet d'enrichir les données ciblées par la requête et de transmettre ces données aux activités suivantes du workflow, où elles pourront être exploitées.<br /> Après avoir ajouté des données additionnelles, vous pouvez appliquer un niveau de filtre supplémentaire sur les données initialement ciblées en créant des conditions basées sur les données additionnelles définies.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/query.md#enriching-data">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aide contextuelle<br /> </td> 
   <td> Une aide contextuelle est désormais disponible dans les différents écrans d'Adobe Campaign. Vous pouvez ainsi accéder directement et en un seul clic à la documentation relative à la fonctionnalité en cours d'utilisation. Pour afficher l'aide contextuelle, cliquez sur l'icône '?' située en haut à droite de l'écran, comme dans l'exemple ci-dessous.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Diverses nouvelles fonctionnalités de l&#39;interface en accord avec les standards de Experience Cloud.
* Uniformisation des différents types de listes déroulantes.

_Emails et SMS_

* Correction d&#39;une erreur qui empêchait l&#39;envoi des emails lorsque le masque d&#39;adresse d&#39;erreur était renseigné.
* Le protocole TLS est désormais supporté pour l&#39;envoi des emails. Une nouvelle colonne dans la gestion des MX permet de définir le comportement TLS souhaité pour chaque domaine.
* L&#39;interface des SMS a été améliorée.

_Workflows_

* Diverses nouvelles fonctionnalités de l&#39;interface des workflows
* Correction d&#39;une erreur d&#39;affichage des actions rapides.
* Correction d&#39;une erreur qui provoquait l&#39;échec d&#39;un workflow lors de l&#39;utilisation d&#39;une activité de type **[!UICONTROL Segmentation]**contenant un lien 1-N.
* Correction d&#39;une erreur qui empêchait d&#39;ouvrir les transitions d&#39;un workflow sur appareil hybride.
* Correction d&#39;une erreur qui empêchait l&#39;affichage du bouton de pause au premier démarrage d&#39;un workflow.

_Editeur de contenus_

* L&#39;éditeur de contenu permet à présent de personnaliser n&#39;importe quelle URL dans un email ou une landing page. Consultez la [documentation détaillée](../../designing/using/personalization.md#personalizing-urls).
* Correction d&#39;une erreur qui provoquait la perte des images lorsque celles-ci étaient ajoutées dans l&#39;assistant de création de la diffusion, puis que le contenu était modifié par la suite.

_Ressources personnalisées_

* Correction d&#39;une erreur lors de l&#39;ajout d&#39;un lien personnalisé de type 1-N dans l&#39;écran de configuration d&#39;une ressource personnalisée.
* Amélioration de l&#39;affichage de la barre de progression lors de la préparation et publication des ressources personnalisées.
* Correction d&#39;une erreur d&#39;affichage de la liste des liens d&#39;une ressource personnalisée.

_Messages transactionnels_

* L&#39;ergonomie de l&#39;interface, les performances et la robustesse du moteur de messages transactionnels ont été optimisées.
* Il est maintenant possible de suspendre temporairement la publication d&#39;un modèle de message transactionnel. Consultez à ce sujet la [documentation détaillée](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* Correction d&#39;une erreur qui permettait l&#39;ajout, dans un modèle de message transactionnel, d&#39;un bloc de contenu ayant une dimension de ciblage non compatible.
* Correction d&#39;un erreur qui empêchait l&#39;affichage de l&#39;aperçu de l&#39;API dans l&#39;écran de configuration d&#39;un événement.

_Audiences et requêtes_

* Corrections diverses liées à l&#39;utilisation des dates dans l&#39;éditeur de requête. Consultez la [documentation détaillée](../../automating/using/editing-queries.md#creating-queries).

_Administration_

* Correction d&#39;une erreur liée au nom du groupe de sécurité &quot;Utilisateurs standard&quot;, qui empêchait les utilisateurs de se connecter.

## Version 16.3 - Mars 2016 {#release-16-3---march-2016}

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
   <td> Interface et navigation<br /> </td> 
   <td> L'interface d'Adobe Campaign a été améliorée afin de rendre la navigation et les opérations plus simples et intuitives.<br /> La navigation se fait désormais depuis la barre supérieure de l'application. Les menus avancés sont quant à eux accessibles en sélectionnant <strong>Adobe Campaign</strong>.<br /> Pour plus d'informations, consultez la <a href="../../start/using/interface-description.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : sauvegarde d'audience<br /> </td> 
   <td> Une nouvelle option <span class="uicontrol">Créer et mettre à jour une audience</span> est désormais disponible dans l'activité de <span class="uicontrol">Sauvegarde d'audience. </span> Cette option permet de saisir manuellement le libellé d'une audience. Si le libellé entré correspond à une audience existante, elle sera mise à jour. Si l'audience n'existe pas, elle sera créée.<br />De plus, lors des exécutions suivantes du workflow, l'audience sera à chaque fois mise à jour.<br /> Il est toujours possible de sélectionner le mode de mise à jour des audiences : compléter l'audience avec les nouvelles données ou remplacer l'intégralité des données de l'audience à chaque exécution.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/save-audience.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : segmentation<br /> </td> 
   <td> L'activité de <span class="uicontrol">Segmentation</span> permet désormais de segmenter les données d'une ressource temporaire. Par exemple : sur les données d'un fichier importé.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/segmentation.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction d&#39;une erreur d&#39;affichage lors du tri d&#39;une liste : la flèche indiquant l&#39;ordre du tri d&#39;une colonne pouvait être inversée pour certains types de données.
* Correction d&#39;une erreur qui limitait le nombre d&#39;éléments affichés dans un menu déroulant lors de l&#39;ajout d&#39;une règle dans une requête.

_Emails et SMS_

* Correction d&#39;une erreur qui pouvait empêcher d&#39;accéder au rapport de rendu des emails.
* La préparation de l&#39;envoi d&#39;un message renvoie désormais une erreur si l&#39;adresse de l&#39;expéditeur n&#39;est pas renseignée.

_Workflows_

* Certaines options de formatage de fichier étaient visibles mais non prises en compte lors d&#39;une extraction de fichier au format CSV. Ces options ne sont désormais plus visibles.
* Correction d&#39;une erreur provoquée dans le cas d&#39;un transfert de fichier de type **[!UICONTROL SFTP]**pour lequel l&#39;option**[!UICONTROL  Effacer les fichiers source après leur transfert]** était cochée.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;afficher le comptage et la prévisualisation des données d&#39;une **[!UICONTROL Requête]**après avoir actualisé la page.
* Correction d&#39;une erreur provoquée à l&#39;ouverture de certaines transitions dans un workflow, notamment après une activité de diffusion ou une requête dont les dimensions de ciblage et de filtrage étaient différentes.
* Correction d&#39;une erreur qui empêchait d&#39;insérer un champ de personnalisation dans une activité de diffusion d&#39;un workflow si le workflow n&#39;avait pas été sauvegardé après l&#39;ajout de l&#39;activité.
* Correction d&#39;une erreur qui empêchait d&#39;afficher la dimension de ciblage de la transition sortante d&#39;une activité de diffusion par email.

_Landing pages_

* Correction d&#39;une erreur qui empêchait les champs de personnalisation de fonctionner correctement dans un bloc de contenu localisable d&#39;une landing page.

_Ressources personnalisées_

* Correction d&#39;une erreur qui empêchait d&#39;effectuer une recherche sur une ressource personnalisée si l&#39;option **[!UICONTROL Ajouter des champs de recherche]**de la définition des écrans de la ressource était cochée et si plusieurs champs étaient sélectionnés dans la**[!UICONTROL  Composition de la zone de filtre]** .

## Version 16.2 - Février 2016 {#release-16-2---february-2016}

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
   <td> Test A/B d'un email<br /> </td> 
   <td> Vous pouvez désormais réaliser des tests A/B sur le contenu, l'objet ou le nom d'expéditeur de vos emails. Cette nouvelle fonctionnalité permet de tester jusqu'à trois variantes d'un élément.<br /> Lors de la création d'un email à partir de l'un des nouveaux modèles spécifiques aux tests A/B, une nouvelle étape dans l'assistant de création vous permet de définir les paramètres de votre test.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/designing-an-a-b-test-email.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gestion des marques<br /> </td> 
   <td> Vous pouvez désormais définir une ou plusieurs marques afin de renseigner de manière centralisée les paramètres qui touchent à l'identité d'une marque. Adobe Campaign vous permet de créer ces marques et de les associer à des modèles de diffusion ou de landing page.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : requête incrémentale<br /> </td> 
   <td> Une nouvelle activité de workflow <span class="uicontrol">Requête incrémentale</span> vous permet de réaliser une requête qui, à chaque exécution, ne cible que les nouveaux résultats. Les résultats des exécutions précédentes sont automatiquement exclus. Associée à une activité <span class="uicontrol">Planificateur</span>, vous pouvez définir le rythme des exécutions de la <span class="uicontrol">Requête incrémentale</span>.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/incremental-query.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messages transactionnels<br /> </td> 
   <td> L'ergonomie de l'interface des messages transactionnels a été améliorée. Toute la gestion des processus métier liés aux messages transactionnels est à présent centralisée dans le menu <span class="uicontrol">Plans marketing</span> &gt; <span class="uicontrol">Messages transactionnels. </span> La configuration des évènements a également été améliorée, ils sont maintenant gérés indépendamment des ressources personnalisées.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-transactional-messaging.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction de plusieurs erreurs d&#39;affichage au niveau des rapports, des listes et des requêtes.
* Correction de plusieurs erreurs de compatibilité et d&#39;affichage sur support mobile.

_Emails et SMS_

* Correction d&#39;une erreur qui pouvait empêcher l&#39;affichage du bouton permettant d&#39;insérer des champs de personnalisation lors de la création d&#39;un message (email ou SMS).
* Correction d&#39;une erreur qui pouvait empêcher les SMS envoyés via Mblox d&#39;être transmis correctement.

_Audiences et requêtes_

* Correction d&#39;une erreur de comptage qui pouvait être entrainée lors de l&#39;ajout d&#39;une condition supplémentaire dans une requête, après avoir modifié la dimension de filtrage.
* Correction d&#39;une erreur qui pouvait entraîner une pagination incorrecte lors de la prévisualisation des résultats d&#39;une requête.

_Edition de contenus_

* Correction d&#39;une erreur qui pouvait empêcher le paramétrage d&#39;un contenu dynamique d&#39;être correctement pris en compte en cas d&#39;utilisation d&#39;une énumération personnalisée.

_Workflows_

* Correction d&#39;une erreur qui pouvait empêcher d&#39;effectuer toute action dans un workflow en cas de présence d&#39;une ligne vide dans l&#39;onglet **[!UICONTROL Champs à mettre à jour]**d&#39;une activité de**[!UICONTROL  Mise à jour de données]**.
* Correction d&#39;une erreur qui empêchait d&#39;importer des données comportant des informations concernant les entités géographiques et organisationnelles.
* Correction d&#39;une erreur provoquée par l&#39;ajout d&#39;une règle d&#39;**[!UICONTROL Exclusion]**de type**[!UICONTROL  Changement d&#39;axe]**.
* Correction d&#39;une erreur qui pouvait entraîner la création d&#39;un segment supplémentaire non souhaité lors de la manipulation d&#39;une transition sortante d&#39;une activité de **[!UICONTROL Segmentation]**.
* Correction d&#39;une erreur entraînée par le chargement d&#39;un fichier dans un modèle de workflow.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;utiliser des espaces comme séparateurs de colonne dans une activité de **[!UICONTROL Chargement de fichier]**.

_Ressources personnalisées_

* Correction d&#39;une erreur qui empêchait le statut d&#39;une ressource personnalisée d&#39;être réinitialisé après l’import d’un package, si la ressource était publiée au moment de l&#39;export.

_Packages_

* Correction d&#39;une erreur qui empêchait d&#39;exporter un package contenant un workflow.
* Correction d&#39;une erreur qui pouvait empêcher de sélectionner plusieurs éléments d&#39;une même ressource.

## Version 16.1 - Janvier 2016 {#release-16-1---january-2016}

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
   <td> Rapports<br /> </td> 
   <td> Les rapports spécifiques aux emails suivants ont été ajoutés : <span class="uicontrol">Plaintes</span>, <span class="uicontrol">Ouvertures</span> et <span class="uicontrol">Désinscriptions</span>.<br /> Les rapports suivants ont été améliorés : <span class="uicontrol">Synthèse des diffusions</span>, <span class="uicontrol">Synthèse des rebonds</span>, <span class="uicontrol">Débit des diffusions</span> et <span class="uicontrol">Indicateurs de tracking</span>.<br /> Pour plus d'informations, consultez la <a href="../../reporting/using/defining-the-report-period.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edition de requêtes<br /> </td> 
   <td> L'outil d'édition de requêtes a été amélioré et permet désormais de parcourir les liens de type <strong>1-N</strong>.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/editing-queries.md#creating-queries">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Personnalisation de contenu<br /> </td> 
   <td> Dans le cadre de l'édition d'emails ou de landing pages, l'interface de saisie des conditions d'affichage des blocs de contenu a été améliorée.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : définition des colonnes lors d'un import<br /> </td> 
   <td> L'activité de <span class="uicontrol">Chargement de fichier</span> permet désormais de configurer les colonnes d'un fichier importé dans le détail : type de données attendu, format des dates et des heures, traitement à appliquer en cas de valeur vide ou d'erreur, et recodification de valeurs.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/load-file.md#column-format">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping des encodages des SMS<br /> </td> 
   <td> Il est désormais possible de définir des mappings d'encodage des SMS personnalisés pour les fournisseurs n'utilisant pas d'encodage standard. Un administrateur peut effectuer la configuration des mappings personnalisés et définir l'ordre dans lequel ils doivent être pris en compte.<br /> Pour plus d'informations, consultez la <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Amélioration de la compatibilité avec Internet Explorer et Chrome sous appareil hybride/tactile.
* Correction d&#39;une erreur qui pouvait entraîner la perte de toutes les données saisies pour un nouvel utilisateur/profil/profil de test si l&#39;adresse email renseignée comportait des erreurs syntaxiques.

_Emails et SMS_

* Correction d&#39;une erreur qui pouvait empêcher de générer la miniature du contenu depuis l&#39;écran de prévisualisation d&#39;un email.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;afficher le contenu brut d&#39;un message (email ou SMS) depuis l&#39;écran de prévisualisation de ce dernier.

_Audiences et requêtes_

* Correction d&#39;une erreur qui pouvait empêcher de créer une audience de type **Requête** sur la ressource **Service**.
* Correction d&#39;une erreur qui pouvait empêcher la liste des fonctions de correctement s&#39;afficher lors de l&#39;édition d&#39;une condition d&#39;une requête en mode avancé.
* Correction d&#39;une erreur qui pouvait empêcher de créer une audience de type **Requête** comportant des critères basés sur des collections.
* Correction d&#39;une erreur qui pouvait empêcher de créer des requêtes comportant des filtres sur les KPI de diffusions.
* Correction d&#39;une erreur qui pouvait empêcher de prévisualiser le contenu d&#39;une audience créée depuis un workflow.

_Ressources personnalisées_

* Correction d&#39;une erreur qui pouvait entraîner un crash du serveur lorsqu&#39;une ressource personnalisée contenait un champ dont la valeur par défaut était dynamique.
* Correction d&#39;une erreur provoquée lors de la définition des écrans d&#39;une ressource personnalisée, suite au déplacement puis à la suppression d&#39;un élément dans la section **[!UICONTROL Configuration de l&#39;écran de détail]**.
* Correction d&#39;une erreur provoquée lorsqu&#39;une valeur par défaut était définie pour une liste de type **integer** qui ne comptait pas **0** parmi les valeurs possibles.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;ajouter un élément dans la configuration de l&#39;écran de détail d&#39;une ressource personnalisée après une réinitialisation.

_Workflows_

* Correction d&#39;une erreur qui provoquait l&#39;affichage des journaux de toutes les activités d&#39;un workflow au lieu d&#39;afficher uniquement ceux de l&#39;activité sélectionnée.
* Correction d&#39;une erreur au niveau de l&#39;activité **[!UICONTROL Planificateur]**. L&#39;option**[!UICONTROL  Jour du mois]** pouvait ne pas être correctement prise en compte et remplacée par **[!UICONTROL Jour de la semaine]**.
* Correction d&#39;une erreur qui pouvait empêcher une activité **[!UICONTROL Planificateur]**de fonctionner correctement lorsque le mode d&#39;expiration était paramétré sur**[!UICONTROL  Après un certain nombre d&#39;itérations]** .
* Correction d&#39;une erreur lors de l&#39;export de données à l&#39;aide d&#39;une activité d&#39;**[!UICONTROL Extraction de fichier]**. Le nombre de lignes présentes dans le fichier exporté était inférieur au nombre d&#39;éléments exportés.
* Correction d&#39;une erreur qui pouvait empêcher de sélectionner un fichier dans une activité de **[!UICONTROL Chargement de fichier]**.
* Correction d&#39;une erreur qui empêchait de supprimer des champs à mettre à jour dans une activité de **[!UICONTROL Mise à jour de données]**.
* Correction d&#39;une erreur qui empêchait d&#39;enregistrer les modifications apportées à un workflow après avoir ouvert les journaux d&#39;exécution de ce dernier.
* Correction d&#39;une erreur qui conduisait une activité de **[!UICONTROL Chargement de fichier]**à être exécutée deux fois si elle était configurée pour utiliser le fichier provenant de sa transition entrante, et que le fichier était téléchargé via une activité de**[!UICONTROL  Transfert de fichier]**.
* Correction d&#39;une erreur qui pouvait empêcher certaines entités temporaires d&#39;être correctement traitées par une activité d&#39;**Exclusion**.
* Correction d&#39;une erreur qui pouvait empêcher une activité de **[!UICONTROL Requête]**d&#39;être exécutée correctement si la dimension de ciblage et la dimension de filtrage paramétrées dans l&#39;activité étaient différentes.
* Correction d&#39;une erreur de nommage automatique des transitions sortantes ajoutées à une activité de **[!UICONTROL Branchement]**qui pouvait empêcher de sauvegarder le workflow.

_Edition de contenus_

* Correction d&#39;une erreur qui pouvait provoquer l&#39;affichage indésirable d&#39;une icône ou d&#39;une barre de recherche lors de l&#39;édition d&#39;un contenu.

_Landing pages_

* Correction d&#39;une erreur qui empêchait d&#39;importer une landing page via un import de package.

_Messages transactionnels_

* Il est maintenant possible de spécifier une adresse IP de confiance dans les paramètres de sécurité de l&#39;opérateur Agent Push Message Center.
* Correction d&#39;une erreur qui pouvait empêcher de créer un nouveau type d&#39;événement.

## Version 15.11 - Novembre 2015 {#release-15-11---november-2015}

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
   <td> Canal SMS<br /> </td> 
   <td> Vous pouvez désormais envoyer des diffusions de type SMS avec Adobe Campaign.<br /> De la même manière que pour les emails, vous pouvez créer de nouvelles diffusions SMS depuis vos campagnes et depuis la liste des activités marketing. Vous avez également la possibilité de créer des diffusions SMS uniques et récurrentes depuis un workflow.<br /> Ces diffusions SMS sont basées sur des modèles que vous pouvez configurer depuis la liste des modèles de diffusion. Un modèle par défaut est disponible.<br /> Elles utilisent le protocole SMPP 3.4, utilisé par la plupart des routeurs SMS.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-sms-messages.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploration des transitions<br /> </td> 
   <td> Vous pouvez désormais explorer le contenu et la structure des données dans la dernière transition d'un workflow. Cela vous permet de vérifier plus facilement que les traitements appliqués par chaque activité correspondent à vos besoins.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pré et post-traitement de fichier dans les workflows<br /> </td> 
   <td> Vous pouvez désormais appliquer des traitements supplémentaires sur un fichier de données au moment de l'importer ou de l'exporter via les activités de <span class="uicontrol">Chargement de fichier</span> et d'<span class="uicontrol">Extraction de fichier. </span><br /> Par défaut, la décompression et la compression d'un fichier au format GZIP sont disponibles dans ces activités.<br /> Pour plus d'informations, consultez la documentation relative aux activités de <a href="../../automating/using/load-file.md">Chargement de fichier</a> et <a href="../../automating/using/extract-file.md">Extraction de fichier</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapports de déliverabilité<br /> </td> 
   <td> Un rapport de rendu des emails est désormais disponible. Ce rapport permet de visualiser les différents rendus d'un message selon le support et le service de messagerie utilisés pour le lire.<br /> La synthèse du rapport présente également le nombre de messages reçus, indésirables, non reçus et en attente de réception.<br /> Pour plus d'informations, consultez la <a href="../../sending/using/email-rendering.md#email-rendering-report-description">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gestion des packages<br /> </td> 
   <td> Il est désormais possible d'importer et d'exporter des images dans les packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actions rapides<br /> </td> 
   <td> Certaines actions contextuelles au survol ou à la sélection d'un élément d'une liste ou d'un workflow sont désormais affichées sous forme d'icônes autour des éléments concernés afin d'en faciliter l'accès. Par exemple pour dupliquer un élément, le supprimer, ouvrir le détail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction d&#39;une erreur qui pouvait empêcher l&#39;accès aux paramètres généraux d&#39;une instance depuis un compte de type administrateur.
* Le type de données **float** est désormais correctement pris en charge dans les ressources personnalisées.
* Correction d&#39;une erreur d&#39;affichage dans la liste des imports simplifiés exécutés causée après la modification du statut du modèle correspondant.

_Landing pages_

* Correction de certains éléments des modèles de landing pages qui pouvaient être incorrectement affichés en français sur des instances anglaises.

_Audiences_

* Correction d&#39;une erreur qui pouvait empêcher les audiences importées depuis Adobe Experience Cloud d&#39;être visibles dans la liste des audiences.
* Correction d&#39;une erreur qui pouvait forcer la sensibilité à la casse lors de la définition d&#39;une requête.
* Correction d&#39;une erreur qui pouvait empêcher de filtrer les audiences lors de la définition d&#39;une requête.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;annulation d&#39;une action dans une audience.

_Workflows_

* Correction d&#39;une erreur qui pouvait empêcher de configurer manuellement les champs à mettre à jour dans une activité de **[!UICONTROL Mise à jour de données]**.
* Correction d&#39;une erreur qui pouvait provoquer un chargement infini lors de l&#39;ouverture d&#39;une activité de **[!UICONTROL Requête]**si le workflow n&#39;avait pas été sauvegardé après avoir placé l&#39;activité dans le diagramme.
* Correction d&#39;une erreur qui pouvait provoquer l&#39;arrêt du serveur lors du comptage ou de la prévisualisation d&#39;une audience sélectionnée depuis une **[!UICONTROL Requête]**dans un workflow.
* Correction d&#39;une erreur non bloquante qui pouvait s&#39;afficher à l&#39;ouverture d&#39;une activité dans un workflow.
* Correction d&#39;une erreur qui empêchait de configurer une activité **[!UICONTROL Planificateur]**de manière à exécuter un workflow plusieurs fois par jour.
* Correction d&#39;une erreur qui provoquait l&#39;affichage de champs sur lesquels il n&#39;était pas possible d&#39;effectuer une requête dans certaines activités de workflows.
* Correction d&#39;une erreur qui empêchait de retrouver des KPI ajoutés à partir d&#39;une **[!UICONTROL Requête]**sur des diffusions dans la transition sortante.
* Correction d&#39;une erreur qui pouvait empêcher la création d&#39;une audience de type fichier après un import de fichier dans un workflow.
* Correction d&#39;une erreur qui pouvait empêcher la mise à jour de données sur des profils si le champ **location/address3** de la ressource était utilisé.
* Correction d&#39;une erreur qui empêchait la duplication de collections hétérogènes d&#39;activités dans un workflow.
* Correction d&#39;une erreur qui empêchait d&#39;afficher le SQL permettant de diagnostiquer des erreurs pour une diffusion récurrente dans un workflow.

_Editeur de contenus_

* Correction d&#39;une erreur qui rendait impossible la recherche dans le code source d&#39;une landing page ou d&#39;un email.

_Packages_

* Correction de diverses erreurs qui pouvaient empêcher l&#39;export de certains types d&#39;éléments dans des packages (notamment landing pages, workflows).
* Correction d&#39;une erreur qui provoquait l&#39;affichage de l&#39;ancien libellé d&#39;un import de package si le libellé avait été modifié.
* Correction d&#39;une erreur qui pouvait provoquer l&#39;affichage de ressources non compatibles dans la liste des ressources exportables.

## Version 15.10 - Octobre 2015 {#release-15-10---october-2015-}

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
   <td> Workflows : activité de déduplication<br /> </td> 
   <td> Une nouvelle activité dédiée à la déduplication de données est désormais disponible dans les workflows. Cette activité permet de filtrer d'éventuels doublons issus de vos ciblages selon les critères de votre choix.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/deduplication.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : amélioration du diagramme<br /> </td> 
   <td> Depuis l'espace de travail d'un workflow, vous pouvez désormais utiliser plusieurs raccourcis clavier pour sélectionner, ouvrir et supprimer des activités.<br /> L'alignement des activités a également été amélioré et permet une meilleure organisation visuelle du workflow.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/workflow-interface.md#workspace">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité Extraction de fichier<br /> </td> 
   <td> La date et l'heure de l'export sont désormais automatiquement ajoutées au libellé des fichiers exportés à l'aide d'une activité d'<span class="uicontrol">Extraction de fichier</span>. Cela permet de générer des fichiers uniques.<br /> </td> 
  </tr> 
  <tr> 
   <td> Import de données simplifié<br /> </td> 
   <td> Le nom du modèle à partir duquel un import simplifié a été réalisé est désormais visible par défaut au niveau de la liste des imports et du détail de chaque import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ressources personnalisées<br /> </td> 
   <td> Amélioration et enrichissement de la gestion et de la définition des liens pour les ressources personnalisées.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Email_

* Correction d&#39;une erreur qui empêchait un lien de désinscription à un service de fonctionner correctement depuis une page miroir.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;affichage du libellé d&#39;une diffusion email au niveau de la page d&#39;édition de l&#39;email.
* Correction d&#39;une erreur qui pouvait empêcher la sélection d&#39;un compte externe de **[!UICONTROL Routage]**dans un modèle de diffusion dupliqué.

_Audiences_

* Correction d&#39;une erreur provoquée lors du comptage d&#39;une audience si un lien de type 1-N était utilisé dans la requête.
* Correction d&#39;une erreur qui pouvait empêcher la sélection d&#39;un profil dans l&#39;audience cible d&#39;une diffusion email.

_Workflows_

* Correction d&#39;une erreur qui pouvait provoquer des problèmes d&#39;affichage lors du paramétrage d&#39;une diffusion email dans un workflow.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;activité de **[!UICONTROL Chargement de fichier]**de fonctionner correctement. Une erreur sans message s&#39;affichait alors.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;activité de **[!UICONTROL Transfert de fichier]**de fonctionner correctement. Les droits d&#39;accès pouvaient ne pas être correctement pris en compte.
* Correction d&#39;une erreur qui pouvait empêcher d&#39;exporter un fichier si le workflow contenait un **[!UICONTROL Email récurrent]**.
* Correction d&#39;une erreur qui pouvait empêcher de créer une diffusion email dans un workflow ou qui empêchait la prise en compte de l&#39;objet et du contenu défini.
* Correction d&#39;une erreur qui pouvait empêcher de sélectionner une clé de réconciliation dans une activité de **[!UICONTROL Mise à jour de données]**lors du paramétrage du workflow d&#39;un modèle d&#39;import simplifié.
* Correction d&#39;une erreur qui pouvait empêcher la sauvegarde d&#39;un workflow après avoir supprimé une activité.

_Plate-forme_

* Correction d&#39;une erreur qui pouvait empêcher la création d&#39;un nouvel élément si une ressource personnalisée contenait un lien vers le type de ressource de cet élément.
* Correction d&#39;une erreur qui pouvait provoquer un délai de 15 minutes dans l&#39;écriture de certains journaux.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;affichage de la liste des activités marketing en cas de tri sur les colonnes **[!UICONTROL Date]**ou**[!UICONTROL  Indicateurs]**.

_Landing pages_

* Correction d&#39;une erreur provoquée lors de la sélection d&#39;un profil de test pour la prévisualisation d&#39;une landing page.

_Messages transactionnels_

* Correction d&#39;une erreur qui pouvait provoquer un crash de l&#39;application suite à la suppression d&#39;un événement sur un profil de test.

_Rapports_

* Correction d&#39;une erreur qui pouvait provoquer l&#39;envoi de données incorrectes pour les rapports **[!UICONTROL deliveryThroughputReport]**et**[!UICONTROL  deliveryTrackingReport]** .

_Editeur de contenus_

* Correction d&#39;une erreur de gestion des balises HTML lors du traitement de blocs de contenu dynamique.

## Version 15.8 - Août 2015 {#release-15-8---august-2015}

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
   <td> Import de données simplifié<br /> </td> 
   <td> Vous pouvez désormais réaliser des imports de données de manière simplifiée.<br /> Les utilisateurs peuvent simplement sélectionner un modèle d'import préalablement défini par un administrateur et charger le fichier contenant les données à importer. Un workflow, défini dans le modèle, est exécuté de manière transparente pour l'utilisateur, qui a directement accès au résultat de son import ainsi qu'à un fichier d'erreurs.<br /> Les données des fichiers peuvent être insérées dans la base ou servir à créer directement une audience.<br /> Pour plus d'informations, consultez la <a href="../../automating/using/about-data-import-and-export.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Création de programmes et campagnes<br /> </td> 
   <td> Désormais, lors de la création d'un programme ou d'une campagne, la date de début est automatiquement paramétrée à la date du jour.<br /> La date de fin est calculée en fonction de celle du début, comme ceci :<br /> 
    <ul> 
     <li> J+186 pour les programmes, </li> 
     <li> J+61 pour les campagnes. </li> 
    </ul> Pour plus d'informations, consultez la <a href="../../start/using/programs-and-campaigns.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> La liste des URLs trackées est désormais en lecture seule.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messages transactionnels<br /> </td> 
   <td> Il est désormais possible de générer l'envoi de messages transactionnels personnalisés tels qu'un changement de mot de passe ou une confirmation de création de compte.<br /> Pour plus d'informations, consultez la <a href="../../channels/using/about-transactional-messaging.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ressources personnalisées<br /> </td> 
   <td> Plusieurs fonctionnalités sont ajoutées comme : l'extension de profil de test, la gestion par statut et la suppression des ressources.<br /> Pour plus d'informations, consultez la <a href="../../developing/using/resource-statuses.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Affichage_

* Correction d&#39;une erreur qui pouvait entraîner la juxtaposition de deux champs dans l&#39;éditeur de requêtes sous Safari.

_Editeur de contenus_

* Correction d&#39;une erreur qui empêchait l&#39;utilisation des caractères &#39;&lt;&#39;, &#39;&amp;&#39; et &#39;>&#39; dans l&#39;objet d&#39;un email.

_Email_

* Correction d&#39;une erreur qui empêchait d&#39;ajouter du texte à la suite d&#39;un texte dynamique.

_Listes_

* Correction d&#39;une erreur qui empêchait que la colonne **Message** des logs d&#39;exécution d&#39;un workflow soit exportée correctement.

_Profils et audiences_

* Correction d&#39;une erreur qui entraînait la double confirmation d&#39;une duplication ou d&#39;une suppression. **Appareils hybrides utilisant Internet Explorer 11 seulement**.

_Workflows_

* Correction d&#39;une erreur qui pouvait empêcher l&#39;envoi d&#39;emails depuis un workflow.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;exécution d&#39;un workflow lorsque le nom du fichier de rejets n&#39;était pas spécifié dans une activité de **[!UICONTROL Chargement de fichier]**.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;exécution d&#39;un workflow lorsque la **[!UICONTROL Fréquence d&#39;exécution]**d&#39;une activité**[!UICONTROL  Planificateur]** était définie sur **[!UICONTROL Quotidienne]**.

_Plate-forme_

* Correction d&#39;une erreur qui empêchait la génération des miniatures en cas d&#39;utilisation de serveurs de répartition de charges.

## Version 15.7 - Juillet 2015 {#release-15-7---july-2015}

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
   <td> Export de listes<br /> </td> 
   <td> Vous avez désormais la possibilité d'exporter le contenu de vos listes dans un fichier au format CSV. Cette fonction est présente dans tous les écrans disposant d'une vue en mode <strong>Liste</strong> (par exemple : la liste des profils).<br /> Les données exportées sont celles des colonnes affichées au moment de l'export. En éditant la liste, vous pouvez ainsi sélectionner les données que vous souhaitez exporter.<br /> Pour plus d'informations sur l'utilisation de cette fonctionnalité, consultez la <a href="../../automating/using/exporting-lists.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégration avec Adobe Profiles &amp; Audiences<br /> </td> 
   <td> Il est désormais possible de partager des audiences entre Adobe Campaign et vos autres solutions d'Adobe Experience Cloud :<br /> 
    <ul> 
     <li> Export : lorsque vous sauvegardez une audience composée de profils dans un workflow, une nouvelle option <span class="uicontrol">Partager dans Adobe Experience Cloud</span> vous permet d'ajouter les profils à une audience existante ou de créer une nouvelle audience. </li> 
     <li> Import : en créant une audience de type <strong>Liste</strong> depuis l'écran de gestion des audiences, une nouvelle option vous permet de l'identifier comme <span class="uicontrol">Audience Adobe Marketing Cloud</span>. Vous pouvez alors sélectionner une audience partagée existante afin de l'importer dans Adobe Campaign. </li> 
    </ul> Pour plus d'informations sur le paramétrage et l'utilisation de cette fonctionnalité, consultez la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Contenu dynamique<br /> </td> 
   <td> L'interface du contenu dynamique a été améliorée. Des flèches sont désormais disponibles pour naviguer entre les différents contenus dynamiques, directement dans le corps de l'email.<br /> Pour plus d'informations sur l'utilisation de cette fonctionnalité, consultez la <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Texte dynamique<br /> </td> 
   <td> Depuis l'éditeur de contenu d'un email, il est désormais possible de définir du texte dynamique :<br /> 
    <ul> 
     <li> dans l'objet de l'email, </li> 
     <li> en mode HTML, </li> 
     <li> ou en mode Texte. </li> 
    </ul> Pour plus d'informations sur l'utilisation de cette fonctionnalité, consultez la <a href="../../channels/using/defining-dynamic-text.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programmes et campagnes - rapports<br /> </td> 
   <td> L'interface et le graphisme des rapports ont été améliorés.<br /> Pour plus d'informations sur l'utilisation de cette fonctionnalité, consultez la <a href="../../reporting/using/defining-the-report-period.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Installation_

* Le nom des instances Adobe Campaign est désormais limité à 32 caractères.

_Workflows_

* Correction d&#39;une erreur qui pouvait empêcher le ciblage d&#39;une ressource de type &#39;delivery&#39; lors de l&#39;édition d&#39;une requête dans un workflow.
* Correction d&#39;une erreur qui pouvait empêcher de traiter certaines ressources liées lors de l&#39;édition d&#39;une requête dans un workflow.
* Correction d&#39;une erreur qui pouvait empêcher de modifier une activité de **Diffusion récurrente** si le workflow avait déjà été exécuté.

_Emails_

* Correction d&#39;une erreur qui empêchait la vérification des erreurs de syntaxe JavaScript avant l&#39;envoi d&#39;un email lorsqu&#39;un contenu dynamique avait été ajouté au moyen de l&#39;éditeur d&#39;expression.

_Landing pages_

* Correction d&#39;une erreur qui empêchait l&#39;édition d&#39;une landing page depuis une tablette.

_Assets Core Service_

* Lors de la sélection d&#39;une ressource partagée depuis l&#39;édition d&#39;un email ou d&#39;une landing page, la liste des ressources disponibles est désormais filtrée pour Adobe Campaign.

## Version 15.6 - Juin 2015 {#release-15-6---june-2015}

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
   <td> Workflows : activité Réconciliation<br /> </td> 
   <td> Une nouvelle activité <strong>Réconciliation</strong> permet de relier des données non identifiées (par exemple suite à un import de fichier) à des ressources existantes dans le cadre d'un workflow.<br /> Cette activité est essentiellement utilisée à des fins de Data Management. Elle répond à deux cas d'utilisation distincts :<br /> 
    <ul> 
     <li> <strong>Ajout de relations</strong> : un onglet <strong>Relations</strong> permet d'ajouter des liens entre les données entrantes et plusieurs autres dimensions de la base de données Adobe Campaign. </li> 
     <li> <strong>Identification de données</strong> : un onglet <strong>Identification</strong> permet d'associer simplement les données entrantes à des colonnes d'une dimension existante dans la base de données Adobe Campaign. En sortie de l'activité, les données sont identifiées comme appartenant à la dimension définie. </li> 
    </ul> Consultez la <a href="../../automating/using/reconciliation.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité Extraction de fichier<br /> </td> 
   <td> Une nouvelle activité <strong>Extraction de fichier</strong> permet d'exporter des données présentes dans Adobe Campaign sous la forme d'un fichier externe depuis un workflow. <br /> Limitation : il n'est actuellement pas possible d'utiliser des noms dynamiques pour les fichiers de sortie.<br /> Consultez la <a href="../../automating/using/extract-file.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité Planificateur<br /> </td> 
   <td> Amélioration du widget qui permet de sélectionner l'heure d'exécution de l'activité <strong>Planificateur</strong> dans un workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité transfert de fichier<br /> </td> 
   <td> Le protocole SFTP est désormais pris en charge.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ressources personnalisées<br /> </td> 
   <td> Le menu <span class="uicontrol">Développement</span> permet désormais aux utilisateurs disposant de droits d'administration d'enrichir le modèle de données fourni en créant leurs propres ressources personnalisées, comme des tables d'achats ou de produits. <br /> Il est également possible d'étendre les ressources d'usine pour leur ajouter de nouveaux champs.<br /> Enfin, la navigation dans les écrans correspondant à une ressource personnalisée nouvelle ou étendue est configurable.<br /> Consultez la <a href="../../developing/using/data-model-concepts.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profils de test<br /> </td> 
   <td> Le <strong>Deuxième prénom</strong> et la <strong>Civilité</strong> des profils de test peuvent désormais être sélectionnés lors de la configuration de la liste des profils de test.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editeur de contenus : contenu dynamique<br /> </td> 
   <td> Vous pouvez définir différents contenus qui s'afficheront de manière dynamique à l'utilisateur selon les conditions définies au moyen de l'éditeur d'expression.<br /> Consultez la <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> Une colonne <strong>Profils de test</strong> est désormais disponible dans les envois d'un email.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Listes_

* La suppression d&#39;un élément d&#39;une liste entraîne désormais le rafraîchissement automatique de la liste.
* Correction d&#39;une erreur qui empêchait la sélection des éléments d&#39;une liste si la liste ne contenait qu&#39;une seule colonne.
* Correction d&#39;une erreur qui pouvait entraîner la perte des modifications apportées à l&#39;affichage d&#39;une liste après un rafraîchissement de la page.
* Le deuxième prénom et la civilité des profils de test peuvent désormais être affichés dans la liste des profils de test.
* Correction d&#39;une erreur provoquée lors de la sélection d&#39;une case à cocher dans une liste avec Mozilla Firefox.

_Audiences_

* Correction d&#39;une erreur qui empêchait l&#39;utilisation du bouton **[!UICONTROL Ajouter]**depuis l&#39;interface des audiences.

_Emails_

* Correction d&#39;une erreur JavaScript qui empêchait d&#39;utiliser l&#39;option de prévisualisation deux fois de suite lors de l&#39;édition d&#39;un email.
* Correction d&#39;une erreur qui empêchait l&#39;utilisation des boutons **[!UICONTROL Editer les propriétés]**et**[!UICONTROL  Afficher les bons à tirer]** sur les tablettes Microsoft Surface Pro3 utilisant Internet Explorer 11.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;affichage des logs d’envois d&#39;un email.

_Landing pages_

* Correction d&#39;une erreur qui empêchait l&#39;utilisation du bloc de contenu **Logo de la marque** lors de l&#39;édition du contenu d&#39;une landing page.
* Correction d&#39;une erreur qui pouvait empêcher l&#39;affichage des landing pages dans la liste des activités marketing lorsque les dates de validité de la landing page étaient renseignées.

_Workflows_

* Correction d&#39;une erreur qui empêchait la limitation d&#39;un segment en mode groupement de fonctionner correctement lors de la configuration d&#39;une activité de **Segmentation**.
* Correction d&#39;une erreur qui pouvait empêcher la sélection d&#39;une transition après avoir configuré une activité de **Segmentation**.
* Correction d&#39;une erreur qui pouvait empêcher la suppression d&#39;une transition après avoir configuré une activité de **Segmentation**.
* Correction d&#39;une erreur qui empêchait le comptage et la prévisualisation de populations dans une activité de **Segmentation**.
* Correction d&#39;une erreur qui empêchait la suppression d&#39;un email récurrent d&#39;être effective.
* Correction d&#39;une erreur qui provoquait l&#39;affichage des données d&#39;une activité de **Transfert de fichier** supprimée dans une nouvelle activité de **Transfert de fichier**.
* Correction d&#39;une erreur qui pouvait empêcher une règle d&#39;exclusion d&#39;être correctement prise en compte dans une activité d&#39;**Exclusion**.
* Correction d&#39;une erreur lors de la suppression d&#39;une activité de diffusion par email dans un workflow. Les diffusions liées n&#39;étaient pas supprimées dans la liste des activités marketing.

_Navigation_

* L&#39;utilisation de la touche de tabulation permet désormais de naviguer correctement entre les champs d&#39;une page.

## Version 15.4 - Avril 2015 {#release-15-4---april-2015}

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
   <td> Exports de package / Imports de package<br /> </td> 
   <td> Le menu <strong>Déploiement</strong> permet désormais aux utilisateurs disposant de droits d'administration d'échanger des ressources entre différentes instances Adobe Campaign par le biais d'exports et d'imports de packages.<br /> Consultez la <a href="../../automating/using/managing-packages.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapports<br /> </td> 
   <td> Tous les rapports sont désormais accessibles depuis un programme, sauf le rapport <strong>Hot clicks. </strong> Il s'agit des rapports suivants :<br /> 
    <ul> 
     <li> Débit des diffusions du programme </li> 
     <li> Indicateurs de tracking du programme </li> 
     <li> Répartition par domaine du programme </li> 
     <li> Echecs et retours du programme </li> 
     <li> URLs et flux de clics du programme </li> 
    </ul> Ces rapports peuvent être filtrés sur une période donnée (par exemple, trois mois, six mois, etc.). Les rapports de campagne peuvent aussi être filtrés.<br /> Consultez la <a href="../../reporting/using/about-dynamic-reports.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité <strong>Diffusion email</strong><br /> </td> 
   <td> L'activité de <strong>Diffusion email</strong> disponible dans les workflows a été améliorée. Vous pouvez désormais retrouver les emails, les emails récurrents, ainsi que le détail des exécutions des emails récurrents depuis la liste des activités marketing de l'application.<br /> Consultez la <a href="../../automating/using/email-delivery.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows : activité <strong>Segmentation</strong><br /> </td> 
   <td> L'activité <strong>Segmentation</strong> est désormais disponible dans les workflows. Cette activité permet de créer un ou plusieurs segments et de leur associer un code segment à partir d'une population calculée par des activités placées en amont dans le même workflow. En sortie d'activité, les segments peuvent être traités dans une seule transition ou dans des transitions distinctes. Des options permettent de filtrer la population et de limiter la taille de chaque segment afin de les personnaliser au mieux. Par exemple vous pouvez effectuer des sélections aléatoires de profils répondant à des critères spécifiques.<br /> Consultez la <a href="../../automating/using/segmentation.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégrations : <strong>Assets Core Service</strong><br /> </td> 
   <td> Vous pouvez désormais utiliser des ressources partagées via <strong>Assets Core Service</strong> dans le contenu de vos emails et de vos landing pages. Vous pouvez gérer vos ressources partagées directement depuis Adobe Experience Cloud.<br /> Consultez la <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intégrations : <strong>Adobe Target</strong><br /> </td> 
   <td> Vous pouvez désormais insérer des images calculées dynamiquement par <strong>Adobe Target</strong> dans vos emails Adobe Campaign. Cela vous permet de proposer plusieurs versions d'un même email en personnalisant son contenu en fonction de critères définis dans des segments Adobe Target.<br /> Consultez la <a href="../../integrating/using/about-campaign-target-integration.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor : <strong>Sélection des blocs</strong><br /> </td> 
   <td> Lorsqu'un bloc est sélectionné dans l'éditeur de contenus HTML, un fil d'Ariane s'affiche au bas de la zone d'édition, ce qui facilite la navigation et la sélection des différents éléments.<br /> Consultez la <a href="../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Version 15.3 - Mars 2015 {#release-15-3---march-2015}

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
   <td> Rapports<br /> </td> 
   <td> Les rapports sont désormais accessibles directement depuis un programme ou une campagne. Le rapport <strong>Synthèse des diffusions</strong> a été ajouté au niveau des programmes.<br /> Consultez la <a href="../../reporting/using/delivery-summary.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mise à jour de données<br /> </td> 
   <td> Dans les workflows, l'activité <strong>Mise à jour de données</strong> disponible propose une nouvelle option qui permet d'associer automatiquement les champs des données entrantes avec les champs d'un schéma de l'application. Elle permet de faciliter le processus de sélection des champs à mettre à jour.<br /> Consultez la <a href="../../automating/using/update-data.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Diffusion email<br /> </td> 
   <td> Dans les workflows, les options avancées de l'activité <strong>Diffusion email</strong> sont désormais accessibles via un bouton spécifique de la barre d'actions. Ce bouton n'est disponible que si une activité <strong>Diffusion email </strong>est sélectionnée. Il permet notamment d'ajouter une transition sortante à l'activité et de modifier le nom de l'activité affiché dans le workflow.<br /> Consultez la <a href="../../automating/using/email-delivery.md">documentation détaillée</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Correctifs**

_Général_

* Correction d&#39;une erreur qui empêchait l&#39;affichage du destinataire lors de la création d&#39;une diffusion.
* Correction d&#39;une erreur qui empêchait l&#39;utilisation d&#39;une audience basée sur la condition &#39;Ayant ouvert&#39;.
* Correction d&#39;une erreur qui interdisait la suppression d&#39;un profil vide.
* Correction d&#39;une erreur lors de la prévisualisation d&#39;une diffusion.
* Correction d&#39;une erreur qui empêchait la duplication d&#39;une activité marketing.
* Correction d&#39;une erreur lors de la suppression d&#39;une campagne.

