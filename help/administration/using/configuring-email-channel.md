---
title: Configuration du canal email dans Adobe Campaign Standard
description: Découvrez comment configurer le canal email dans Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 04709dd9a754ea616f3e695ada072137b9ecce6a

---


# Configuration du canal Email{#configuring-email-channel}

## Paramètres du canal email {#email-channel-parameters}

L&#39;écran Configuration email vous permet de définir les paramètres du canal email.

![](assets/channels_1.png)

* **Paramètres d&#39;en-tête des emails envoyés**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. Au besoin, ces masques doivent être séparés les uns des autres par une virgule. Ce paramétrage est facultatif. Lorsque ces champs sont renseignés, Adobe Campaign contrôle, au moment de la préparation des messages que les adresses renseignées dans l&#39;email sont valables. Ce fonctionnement permet d&#39;éviter l&#39;utilisation d&#39;adresses qui pourraient poser des problèmes de délivrabilité. Les adresses d&#39;expédition doivent être configurées sur le serveur de diffusion.

* **Délivrabilité**

   Cet identifiant vous est fourni par le support. Il est nécessaire au bon fonctionnement des rapports de délivrabilité.

* **Paramètres de la diffusion**

   Adobe Campaign envoie les messages à compter de la date de début. The **[!UICONTROL Message delivery duration]** field allows you to specify the duration during which the messages can be sent.

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. Les ressources de cette page ont une durée de validité limitée (afin d&#39;économiser de l&#39;espace disque).

* **Reprises**

   Les messages qui n&#39;ont pas abouti de manière temporaire font l&#39;objet de reprises automatiques. Cette section indique combien de reprises doivent être effectuées le premier jour après le démarrage de l&#39;envoi (**Nombre de reprises**) ainsi que le délai minimum entre deux reprises (**Période des reprises**).

   Par défaut, cinq reprises sont planifiées le premier jour de l&#39;envoi, avec un intervalle minimum d&#39;une heure, réparties sur les 24h de la journée. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Paramètres de mise en quarantaine des emails**

   In the **[!UICONTROL Time between two significant errors]** field, enter a value to define the time the application waits before incrementing the error counter in case of failure. Valeur par défaut : **&quot;1j&quot;**, pour 1 jour.

   Lorsque la **[!UICONTROL Maximum number of errors before quarantine]** valeur est atteinte, l’adresse électronique est mise en quarantaine. Valeur par défaut : **&quot;5&quot;** : l&#39;adresse est mise en quarantaine à la sixième erreur. Cela signifie que ce contact sera automatiquement exclu des prochaines diffusions.

**Rubrique connexe** :

[Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)

## Comptes de routage email   {#email-routing-accounts}

Le **[!UICONTROL Integrated email routing]** est fourni par défaut. Il contient les paramètres techniques qui permettent à l&#39;application d&#39;envoyer des emails.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Rubrique connexe** :

[Comptes externes](../../administration/using/external-accounts.md)

## Règles de gestion des emails   {#email-processing-rules}

Les administrateurs **[!UICONTROL Email processing rules]** peuvent y accéder par le **[!UICONTROL Administration > Channels > Email]** menu.

Ces règles contiennent la liste des chaînes de caractères qui peuvent être renvoyées par les serveurs distants et qui permettent de qualifier l&#39;erreur en **Hard**, **Soft** ou **Ignoré**.

Les règles par défaut sont les suivantes :

### Mails rebonds {#bounce-mails}

Pour les messages d’erreur d’échec de diffusion synchrone, le MTA amélioré détermine le type et la qualification du bounce et renvoie ces informations à Campaign. Pour plus d’informations sur le serveur de diffusion MTA amélioré d&#39;Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Les rebonds asynchrones sont toujours qualifiés par le processus Campaign dans le courrier via la **[!UICONTROL Bounce mails]** règle.

>[!IMPORTANT]
>
>Once upgraded to the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. Pour plus d&#39;informations sur la qualification du courrier de rebonds, reportez-vous à cette [section](../../sending/using/understanding-delivery-failures.md).

<!--The user can create his own rules.

>[!IMPORTANT]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.-->

### Gestion des domaines de courriel {#managing-email-domains}

<!--The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **SMTP relay**: lets you configure the IP address and the port of a relay server for a particular domain.-->

>[!IMPORTANT]
>
>Once upgraded to the Enhanced MTA, the Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**La signature de l’authentification par messagerie électronique DKIM (DomainKeys Identified Mail)** est effectuée par la MTA améliorée pour tous les messages contenant tous les domaines. Il ne se signe pas avec l’ID **d’expéditeur**, **DomainKeys**, **DKIM** ou **S/MIME sauf indication contraire au niveau MTA amélioré.**

Pour plus d’informations sur le serveur de diffusion MTA amélioré d&#39;Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### MX management {#mx-management}

<!--The MX management rules are used to regulate the flow of outgoing emails for a specific domain. They sample the bounce messages and block sending where appropriate.

The Adobe Campaign messaging server applies rules specific to the domains, and then the rules for the general case represented by an asterisk in the list of rules.

To configure MX management rules, simply set a threshold and select certain SMTP parameters. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.-->

>[!IMPORTANT]
>
>Once upgraded to the Enhanced MTA, the Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

Le MTA amélioré utilise ses propres règles MX. Il peut ainsi personnaliser le débit par domaine en fonction de vos historiques de réputation de diffusion d’emails et des retours en temps réel issus de domaines auxquels vous envoyez des emails.

Pour plus d’informations sur le serveur de diffusion MTA amélioré d&#39;Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

<!--Each rule defines an address mask for the MX. Any MX whose name matches this mask is therefore eligible. The mask can contain "&#42;" and "?" generic characters.

For example, the following addresses:

* a.mx.yahoo.com 
* b.mx.yahoo.com 
* c.mx.yahoo.com

are compatible with the following masks:

* &#42;.yahoo.com
* ?.mx.yahoo.com

These rules are applied in sequence: the first rule whose MX mask is compatible with the targeted MX is applied.

The following parameters are available for each rule:

* **[!UICONTROL Range of IDs]**: this option lets you indicate the ranges of identifiers (publicId) for which the rule applies. You can specify:

    * A number: the rule will only apply to this publicId.
    * A range of numbers (number1-number2): the rule will apply to all publicIds between these two numbers.

  If the field is empty, the rule applies to all IDs.

* **[!UICONTROL Shared]**: this option indicates that the highest number of messages per hour and of connections applies to all MXs linked to this rule. 
* **[!UICONTROL Maximum number of connections]**: maximum number of simultaneous connections to an MX from a given address. 
* **Maximum number of messages**: maximum number of messages that can be sent by one connection. After this amount, the connection is closed and a new one is reopened. 
* **[!UICONTROL Messages per hour]**: maximum number of messages that can be sent in one hour for an MX via a given address.

>[!IMPORTANT]
>
>* The delivery server (MTA) must be restarted if the parameters have been changed. 
>* The modification or creation of management rules is for expert users only. -->

## Liste des propriétés des emails   {#list-of-email-properties}

Cette section décrit la liste des paramètres disponibles dans l&#39;écran des propriétés d&#39;un email ou d&#39;un modèle d&#39;email.

>[!NOTE]
>
>Certains paramètres sont uniquement disponibles dans les modèles. Les paramètres accessibles [dépendent de vos permissions](../../administration/using/users-management.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### Paramètres généraux {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. Ces informations apparaissent dans l&#39;interface mais ne sont pas visibles par les destinataires des messages.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L&#39;identifiant doit être unique.

The **[!UICONTROL Brand]** field allows you to select the brand linked to the delivery. Pour plus d&#39;informations sur l&#39;utilisation des marques et leur paramétrage, voir la section [Marques](../../administration/using/branding.md).

The **[!UICONTROL Campaign]** field allows you to enter the campaign linked to the email.

Vous pouvez également ajouter une **[!UICONTROL Description]** dans le champ correspondant et modifier l&#39;image affichée sur la vignette de l&#39;email, dans les listes.

### Paramètres d&#39;envoi {#sending-parameters}

The **[!UICONTROL Send]** section is only available for email templates. Elle comprend les paramètres suivants :

#### Paramètres de reprises {#retries-parameters}

Les messages qui n&#39;ont pas abouti de manière temporaire font l&#39;objet de reprises automatiques. This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

Par défaut, cinq reprises sont planifiées le premier jour de l&#39;envoi, avec un intervalle minimum d&#39;une heure, réparties sur les 24h de la journée. Après cela, une reprise est programmée chaque jour jusqu&#39;à la date limite de diffusion, qui est définie dans la section [Paramètres de période de validité](#validity-period-parameters).

Le nombre de reprises peut être changé de manière globale (contactez l&#39;administrateur technique Adobe) ou pour chaque diffusion ou modèle de diffusion.

#### Paramètres de format des emails   {#email-format-parameters}

Vous pouvez paramétrer le format des emails envoyés. Trois options sont disponibles :

* **Tenir compte des préférences des destinataires** (mode par défaut) : le format du message est défini en fonction des informations enregistrées dans le profil du destinataire et stockées par défaut dans le champ **Format des emails** (@emailFormat). Si un destinataire souhaite recevoir les messages dans un format particulier, ce format lui est envoyé. Si ce champ n&#39;est pas renseigné, le message sera envoyé en multipart-alternative (voir ci-dessous).
* **Laisser le mailer des destinataires choisir le format le plus adapté (multipart-alternative)** : le message contient les deux formats : texte et HTML. Le format affiché lors de la réception dépend de la configuration du logiciel de messagerie du destinataire (multipart-alternative).

   >[!IMPORTANT]
   >
   >Cette option inclut les deux versions du message et, par conséquent, a un impact sur le débit de diffusion, car la taille du message est supérieure.

* **Envoyer tous les messages au format texte** : le message est envoyé au format texte. Le format HTML ne sera pas envoyé, mais uniquement utilisé pour la page miroir, lorsque le destinataire clique sur le lien dans le message.

#### Mode test SMTP {#smtp-test-mode}

The **[!UICONTROL Enable SMTP test mode]** option allows you to test sending emails via an SMTP connection without actually sending messages.
Les messages sont traités jusqu&#39;à la connexion au serveur SMTP, mais ne sont pas envoyés.

![](assets/smtp-test-mode.png)

Cette option est disponible pour les emails et les modèles d&#39;email.

Si vous activez l&#39;option de mode test SMTP pour un modèle d&#39;email, cette option sera activée pour tous les emails créés à partir de ce modèle.

>[!IMPORTANT]
>
>Lorsque cette option est activée pour un email, aucun message n&#39;est envoyé tant qu&#39;elle n&#39;est pas décochée.
>Un avertissement s&#39;affiche dans le tableau de bord de l&#39;email ou du modèle d&#39;email.

Pour plus d&#39;informations sur la configuration SMTP, reportez-vous à la section [Liste des paramètres SMTP des emails](#list-of-email-smtp-parameters).

### Paramètres de période de validité   {#validity-period-parameters}

La section **[!UICONTROL Validity period]** propose les paramètres suivants :

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: lorsque cette case est désactivée, vous devez saisir une durée dans les **[!UICONTROL Delivery duration]** champs et **[!UICONTROL Resource validity limit]** . Cochez cette case si vous souhaitez définir des dates et heures précises.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**: Adobe Campaign envoie les messages à compter de la date de début. Ce champ permet de définir la durée pendant laquelle les messages pourront être envoyés.

   >[!IMPORTANT]
   >
   >Once upgraded to the Enhanced MTA, the **[!UICONTROL Delivery duration]** parameter in your Campaign deliveries is used only if set to 3.5 days or less. Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte. Tous les impacts sont présentés dans le document [Serveur de diffusion MTA amélioré d&#39;Adobe Campaign](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

* **[!UICONTROL Resource validity duration]**: ce champ est utilisé pour les ressources téléchargées, principalement pour le  et les images. Les ressources de cette page ont une durée de validité limitée (afin d&#39;économiser de l&#39;espace disque).
* **[!UICONTROL Mirror page management]**: le est une page HTML accessible en ligne via un navigateur Web. et dont le contenu est identique à celui de l&#39;email. Par défaut, la page miroir est générée si le lien est inséré dans le contenu du mail. Ce champ permet de modifier le mode de génération de cette page :

   >[!IMPORTANT]
   >
   >Un contenu HTML doit avoir été défini pour l&#39;email pour que la page miroir soit créée.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (mode par défaut) : le  est généré si le lien est inséré dans le contenu du courrier.
   * **Forcer la génération de la page miroir** : même si aucun lien vers la page miroir n&#39;est inséré dans les messages, la page miroir sera créée.
   * **Ne pas générer de page miroir** : aucune page miroir n&#39;est générée, même si le lien est présent dans les messages.
   * **Générer une page miroir accessible depuis l&#39;identifiant du message** : cette option permet d&#39;accéder au contenu de la page miroir, avec les informations de personnalisation, dans l&#39;écran des logs de diffusion.

>[!NOTE]
>
>The **[!UICONTROL Delivery duration]** parameter does not apply to transactional messages. Pour plus d&#39;informations sur les messages transactionnels, voir [cette section](../../channels/using/about-transactional-messaging.md).

### Paramètres du tracking   {#tracking-parameters}

La section **[!UICONTROL Tracking]** propose les paramètres suivants :

* **[!UICONTROL Activate tracking]**: vous permet d’activer/désactiver le suivi des URL de messages. To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. Voir [A propos des URL trackées](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: vous permet de définir la durée pendant laquelle le suivi sera activé sur les URL.
* **[!UICONTROL Substitution URL for expired URLs]**: vous pouvez entrer une URL vers une page Web qui s’affichera une fois le suivi terminé.

### Paramètres avancés {#advanced-parameters}

La **[!UICONTROL Advanced parameters]** section contient plusieurs paramètres.

Les premiers champs vous permettent de saisir les informations nécessaires pour élaborer les en-têtes d’email. Vous pouvez gérer ici l’adresse de réponse et le texte ainsi que l’adresse de l’expéditeur (qui occupe le champ « De : »). Ces informations peuvent être personnalisées.

Cliquez sur le bouton à droite du champ qui va être modifié, puis ajoutez le champ de personnalisation, le bloc de contenu ou le texte dynamique.

![](assets/advancedparameters.png)

L’insertion et l’utilisation du contenu de personnalisation sont présentées dans la documentation [Personnalisation du contenu des emails](../../designing/using/personalization.md).

#### Contexte de ciblage   {#target-context}

Le contexte de ciblage permet de définir l&#39;ensemble les tables qui seront utilisées pour le ciblage (dans l&#39;écran de définition des audiences) et la personnalisation (définition de champs de personnalisation, dans l&#39;éditeur de contenu HTML) de l&#39;email.

#### Routage   {#routing}

Ce champ indique le mode de routage utilisé. Il référence un compte externe. Par exemple, cela peut être utile si vous souhaitez utiliser un compte externe contenant des paramétrages de branding spécifiques.

>[!NOTE]
>
>Les comptes externes sont accessibles via le menu **Administration** > **Paramétrage de l&#39;application** > **Comptes externes**.

#### Préparation   {#preparation}

La préparation des messages est présentée dans la section [Valider les messages](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: avant tout envoi, les messages doivent être préparés pour valider le contenu et la configuration. Les règles de vérification appliquées lors de la phase de préparation sont définies dans une **typologie**. Par exemple, pour les emails, la préparation porte sur la validation de l&#39;objet, des URL et des images, etc. Sélectionnez, dans ce champ, la typologie à appliquer.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery preparation]**: vous permet de calculer la valeur d’étiquette du courrier électronique pendant la phase de préparation du message à l’aide des , des blocs de contenu et du texte dynamique.

   Il est également possible de personnaliser le libellé de la diffusion avec les variables d&#39;événements qui ont été déclarées dans l&#39;activité de signal externe du workflow. Voir à ce propos [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: cette option vous permet d&#39;ajouter des journaux de SQL dans le  pendant la phase de préparation.

### Liste des paramètres SMTP des emails {#list-of-email-smtp-parameters}

La section **[!UICONTROL SMTP]** propose les paramètres suivants :

* **[!UICONTROL Character encoding]**: cochez la **[!UICONTROL Force encoding]** case si vous souhaitez forcer le codage des messages, puis sélectionnez le codage à utiliser.
* **[!UICONTROL Bounce mails]**: par défaut, les messages de retour sont reçus dans la boîte de réception d’erreur de la plateforme (définie dans l’ **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: cette option permet d’ajouter des en-têtes SMTP supplémentaires à vos messages. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Les valeurs sont automatiquement encodées, si nécessaire.

   >[!IMPORTANT]
   >
   >L&#39;ajout d&#39;un script pour l&#39;insertion d&#39;en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés. La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

### Liste des paramètres d&#39;autorisation d&#39;accès   {#list-of-access-authorization-parameters}

La section **[!UICONTROL Access authorization]** propose les paramètres suivants :

* The **[!UICONTROL Organizational unit]** field allows you to restrict access to this email to certain users. Les utilisateurs associés à l&#39;entité spécifiée ou aux entités parentes auront accès, en lecture et écriture, à cet email. Les utilisateurs associés aux entités filles auront accès, en lecture seule, à cet email.

   >[!NOTE]
   >
   >Le paramétrage des entités organisationnelles est accessible via le menu **Administration** > **Utilisateurs &amp; sécurité**.

* Les champs **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** et **[!UICONTROL Last modified]** sont automatiquement complétés.
