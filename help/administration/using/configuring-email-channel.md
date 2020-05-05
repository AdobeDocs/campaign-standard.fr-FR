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
source-git-commit: faddcc870adcf9e71e50004a69a219b16ddc044f

---


# Configuration du canal Email{#configuring-email-channel}

En tant qu’ [administrateur](../../administration/using/users-management.md#functional-administrators)Campaign, vous pouvez configurer les paramètres de canal électronique. Ces paramètres avancés incluent des paramètres généraux de canal de courriel, des comptes de routage de courriel, des règles de traitement de courriel et des propriétés de courriel. Sur cette page, vous apprendrez comment modifier les valeurs par défaut pour le courrier électronique général et les paramètres d’envoi.

Notez que certains paramètres de courrier électronique sont désormais gérés par l’application Adobe Campaign Enhanced MTA. Par conséquent :
* Certaines configurations de l’interface utilisateur Campaign ne sont plus appliquées :
   * Les **[!UICONTROL Retries]** paramètres du menu [](#email-channel-parameters) Configuration et des paramètres [](#retries-parameters) d’envoi des propriétés de courrier électronique.
   * Règles **[!UICONTROL MX management]** et **[!UICONTROL Domain management]** dans le menu [Règles de traitement des](#email-processing-rules)courriels.

* D’autres paramètres sont maintenant partiellement gérés par l’AMT améliorée, tandis que certaines configurations peuvent encore être effectuées dans Campaign. Les paramètres concernés sont les suivants :
   * Le **[!UICONTROL Message delivery duration]** paramètre dans le **[!UICONTROL Configuration]** menu. Voir à ce propos [cette section](#email-channel-parameters).
   * Paramètre **[!UICONTROL Delivery duration]** ou **[!UICONTROL Validity limit for sending messages]** dans la **[!UICONTROL Validity period]** section. Voir à ce propos [cette section](#validity-period-parameters).
   * Les **[!UICONTROL Bounce mails]** règles dans le **[!UICONTROL Email processing rules]**. Voir à ce propos [cette section](#email-processing-rules).

## Paramètres du canal email {#email-channel-parameters}

L’écran de configuration du courrier électronique permet de définir les paramètres du canal de courrier électronique. Administrators can access these configurations in the **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**menu.

![](assets/channels_1.png)

* **Champs de masques autorisés**

   Les **[!UICONTROL Header parameters of sent emails]** listes d&#39;adresses électroniques autorisées que vous pouvez utiliser pour envoyer des courriers électroniques à vos destinataires (adresse de l&#39;expéditeur) et pour les avertir de toute erreur (adresse d&#39;erreur).  Adobe Campaign vérifie la validité des adresses saisies au cours de la préparation du message. Ce fonctionnement permet d’éviter l’utilisation d’adresses qui pourraient poser des problèmes de délivrabilité.
   * Les adresses d’expéditeur et d’erreur sont configurées par Adobe. Ces champs ne peuvent pas être vides.
   * Vous ne pouvez pas modifier ces champs. Pour mettre à jour une adresse, contactez l’équipe d’assistance clientèle d’Adobe.
   * Pour ajouter une autre adresse, vous pouvez utiliser le panneau [de](https://docs.adobe.com/content/help/fr-FR/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html) configuration pour configurer un nouveau sous-domaine ou contacter l’équipe d’assistance clientèle d’Adobe. Notez que si plusieurs masques sont utilisés, ils sont séparés par des virgules.
   * Il est recommandé de définir des adresses à l&#39;aide d&#39;une étoile telle que *@votredomaine.com : il vous permet d&#39;utiliser toute adresse se terminant par votre nom de sous-domaine.

* **Délivrabilité**

   L’ **[!UICONTROL Delivery reports ID]** assistance clientèle d’Adobe est chargée de l’aider. Il identifie chaque instance avec un ID de délivrabilité qui est utilisé dans les rapports de délivrabilité technique.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Paramètres de la diffusion**

   Adobe Campaign envoie les messages à compter de la date de début. The **[!UICONTROL Message delivery duration]** field allows you to specify the duration during which the messages can be sent.

   >[!IMPORTANT]
   >
   >**Ce paramètre dans Campaign n’est désormais utilisé que s’il est défini sur 3,5 jours ou moins.** Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte car elle est désormais gérée par l’AMT Adobe Campaign Enhanced.

   The **[!UICONTROL Online resources validity duration]** field is used for uploaded resources, mainly for the mirror page and images. Les ressources de cette page ont une durée de validité limitée (afin d’économiser de l’espace disque).

* **Reprises**

   Les messages qui n’ont pas abouti de manière temporaire font l’objet de reprises automatiques. Voir à ce propos [Reprises après un échec temporaire de diffusion](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!NOTE]
   >
   >Le nombre maximal de Reprises à effectuer et le délai minimal entre les Reprises sont maintenant gérés par l’accord de plateforme de test étendu Adobe Campaign, en fonction de l’efficacité historique et actuelle d’une IP sur un domaine donné. Les paramètres des **Reprises** dans Campaign seront ignorés.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Paramètres de mise en quarantaine des emails**

   In the **[!UICONTROL Time between two significant errors]** field, enter a value to define the time the application waits before incrementing the error counter in case of failure. La valeur par défaut est **&quot;1d&quot;**, pour 1 jour.

   Une fois la **[!UICONTROL Maximum number of errors before quarantine]** valeur atteinte, l’adresse électronique est mise en quarantaine. The default value is **&quot;5&quot;**: the address will be quarantined on the fifth error. Cela signifie que ce contact sera automatiquement exclu des prochaines diffusions.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   For more on quarantines, see [Understanding quarantine management](../../sending/using/understanding-quarantine-management.md).

## Comptes de routage email     {#email-routing-accounts}

Le **[!UICONTROL Integrated email routing]** compte externe est fourni par défaut. Il contient les paramètres techniques qui permettent à l’application d’envoyer des emails.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Rubrique connexe**:

[Comptes externes](../../administration/using/external-accounts.md)

## Règles de gestion des emails     {#email-processing-rules}

Les administrateurs **[!UICONTROL Email processing rules]** peuvent y accéder par le **[!UICONTROL Administration > Channels > Email]** menu.

Notez que les domaines de courriel et les règles MX sont maintenant gérés par l’accord de plateforme de test MTA amélioré Adobe Campaign :
* La signature d’authentification des emails **DKIM (DomainKeys Identified Mail)** est effectuée par le MTA amélioré pour tous les messages et tous les domaines. La signature n’utilise ni **Sender ID**, ni **DomainKeys** ou **S/MIME**, sauf indication contraire du MTA amélioré.
* La MTA améliorée utilise ses propres règles MX qui lui permettent de personnaliser votre débit par domaine en fonction de votre propre réputation de courriel historique et des commentaires en temps réel provenant des domaines où vous envoyez des courriels.

### Mails rebonds {#bounce-mails}

Asynchronous bounces are still qualified by the Campaign inMail process through the **[!UICONTROL Bounce mails]** rule.

This rule contains the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

>[!NOTE]
>
>Pour les messages d’erreur d’échec de diffusion synchrone, la MTA améliorée Adobe Campaign détermine le type et la qualification de rebond et renvoie ces informations à Campaign.

Pour plus d’informations sur la qualification des emails bounce, reportez-vous à cette [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Liste des propriétés des emails     {#list-of-email-properties}

Cette section décrit la liste des paramètres disponibles dans l’écran des propriétés d’un email ou d’un modèle d’email.

>[!NOTE]
>
>Certains paramètres sont uniquement disponibles dans les modèles. Les paramètres accessibles [dépendent de vos permissions](../../administration/using/users-management.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### Paramètres généraux {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. Ces informations apparaissent dans l’interface mais ne sont pas visibles par les destinataires des messages.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L’identifiant doit être unique.

The **[!UICONTROL Brand]** field allows you to select the brand linked to the delivery. Pour plus d’informations sur l’utilisation des marques et leur paramétrage, voir la section [Marques](../../administration/using/branding.md).

The **[!UICONTROL Campaign]** field allows you to enter the campaign linked to the email.

Vous pouvez également ajouter une **[!UICONTROL Description]** dans le champ correspondant et modifier l’image affichée sur la vignette de l’email, dans les listes.

### Paramètres d’envoi {#sending-parameters}

The **[!UICONTROL Send]** section is only available for email templates. Elle comprend les paramètres suivants :

#### Paramètres de reprises {#retries-parameters}

Les messages qui n’ont pas abouti de manière temporaire font l’objet de reprises automatiques. Voir à ce propos [Reprises après un échec temporaire de diffusion](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Le délai minimal entre les Reprises et le nombre maximal de Reprises à effectuer sont maintenant gérés par l’accord de plateforme de test étendu Adobe Campaign, en fonction de l’efficacité historique et actuelle d’une IP sur un domaine donné. Les paramètres des **Reprises** Campaign seront ignorés.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

Le paramètre **de durée de** diffusion (défini dans la section Paramètres [de la période de](#validity-period-parameters) validité) **configuré dans Campaign sera toujours respecté, mais jusqu&#39;à 3,5 jours**. À ce stade, tout message de la file d’attente des tentatives est supprimé de la file d’attente et renvoyé en tant que rebond. For more on delivery failures, see this [section](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Paramètres de format des emails     {#email-format-parameters}

Vous pouvez paramétrer le format des emails envoyés. Trois options sont disponibles :

* **Tenir compte des préférences des destinataires** (mode par défaut) : le format du message est défini en fonction des informations enregistrées dans le profil du destinataire et stockées par défaut dans le champ **Format des emails** (@emailFormat). Si un destinataire souhaite recevoir les messages dans un format particulier, ce format lui est envoyé. Si ce champ n’est pas renseigné, le message sera envoyé en multipart-alternative (voir ci-dessous).
* **Laisser le mailer des destinataires choisir le format le plus adapté (multipart-alternative)** : le message contient les deux formats : texte et HTML. Le format affiché lors de la réception dépend de la configuration du logiciel de messagerie du destinataire (multipart-alternative).

   >[!IMPORTANT]
   >
   >Cette option inclut les deux versions du message et, par conséquent, a un impact sur le débit de diffusion, car la taille du message est supérieure.

* **Envoyer tous les messages au format texte** : le message est envoyé au format texte. Le format HTML ne sera pas envoyé, mais uniquement utilisé pour la page miroir, lorsque le destinataire clique sur le lien dans le message.

#### Mode test SMTP {#smtp-test-mode}

The **[!UICONTROL Enable SMTP test mode]** option allows you to test sending emails via an SMTP connection without actually sending messages.
Les messages sont traités jusqu’à la connexion au serveur SMTP, mais ne sont pas envoyés.

![](assets/smtp-test-mode.png)

Cette option est disponible pour les emails et les modèles d’email.

Si vous activez l’option de mode test SMTP pour un modèle d’email, cette option sera activée pour tous les emails créés à partir de ce modèle.

>[!IMPORTANT]
>
>Lorsque cette option est activée pour un email, aucun message n’est envoyé tant qu’elle n’est pas décochée.
>Un avertissement s’affiche dans le tableau de bord de l’email ou du modèle d’email.

Pour plus d’informations sur la configuration SMTP, reportez-vous à la section [Liste des paramètres SMTP des emails](#list-of-email-smtp-parameters).

### Paramètres de période de validité     {#validity-period-parameters}

La section **[!UICONTROL Validity period]** propose les paramètres suivants :

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: lorsque cette case est désactivée, vous devez entrer une durée dans les **[!UICONTROL Delivery duration]** champs et **[!UICONTROL Resource validity limit]** .

   Cochez cette case si vous souhaitez définir des dates et heures précises.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign envoie les messages à compter de la date de début. Ce champ permet de définir la durée pendant laquelle les messages pourront être envoyés.

   >[!IMPORTANT]
   >
   >Ce paramètre est désormais géré par la MTA améliorée Adobe Campaign. **Vous devez définir une valeur allant jusqu’à 3,5 jours.** Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: ce champ est utilisé pour les ressources téléchargées, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d’économiser de l’espace disque).
* **[!UICONTROL Mirror page management]**: la page miroir est une page HTML accessible en ligne via un navigateur Web. et dont le contenu est identique à celui de l’email. Par défaut, la page miroir est générée si le lien est inséré dans le contenu du mail. Ce champ permet de modifier le mode de génération de cette page :

   >[!IMPORTANT]
   >
   >Le contenu HTML doit avoir été défini pour le courrier électronique pour que la page miroir soit créée.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (mode par défaut) : la page miroir est générée si le lien est inséré dans le contenu du courrier.
   * **Forcer la génération de la page miroir** : même si aucun lien vers la page miroir n’est inséré dans les messages, la page miroir sera créée.
   * **Ne pas générer de page miroir** : aucune page miroir n’est générée, même si le lien est présent dans les messages.
   * **Générer une page miroir accessible depuis l’identifiant du message** : cette option permet d’accéder au contenu de la page miroir, avec les informations de personnalisation, dans l’écran des logs de diffusion.

>[!NOTE]
>
>The **[!UICONTROL Delivery duration]** parameter does not apply to transactional messages. Pour plus d’informations sur les messages transactionnels, voir [cette section](../../channels/using/about-transactional-messaging.md).

### Paramètres du tracking     {#tracking-parameters}

La section **[!UICONTROL Tracking]** propose les paramètres suivants :

* **[!UICONTROL Activate tracking]**: vous permet d’activer/désactiver le suivi des URL de messages. To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. Voir [A propos des URL trackées](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: vous permet de définir la durée pendant laquelle le suivi sera activé sur les URL.
* **[!UICONTROL Substitution URL for expired URLs]**: vous pouvez entrer une URL vers une page Web qui s’affichera une fois le suivi expiré.

### Paramètres avancés {#advanced-parameters}

La **[!UICONTROL Advanced parameters]** section contient plusieurs paramètres.

Les premiers champs vous permettent de saisir les informations nécessaires pour élaborer les en-têtes d’email. Vous pouvez gérer ici l’adresse de réponse et le texte ainsi que l’adresse de l’expéditeur (qui occupe le champ « De : »). Ces informations peuvent être personnalisées.

Cliquez sur le bouton à droite du champ qui va être modifié, puis ajoutez le champ de personnalisation, le bloc de contenu ou le texte dynamique.

![](assets/advancedparameters.png)

L’insertion et l’utilisation du contenu de personnalisation sont présentées dans la documentation [Personnalisation du contenu des emails](../../designing/using/personalization.md).

#### Contexte de ciblage     {#target-context}

Le contexte de ciblage permet de définir l’ensemble les tables qui seront utilisées pour le ciblage (dans l’écran de définition des audiences) et la personnalisation (définition de champs de personnalisation, dans l’éditeur de contenu HTML) de l’email.

#### Routage     {#routing}

Ce champ indique le mode de routage utilisé. Il référence un compte externe. Par exemple, cela peut être utile si vous souhaitez utiliser un compte externe contenant des paramétrages de branding spécifiques.

>[!NOTE]
>
>Les comptes externes sont accessibles via le menu **Administration** > **Paramétrage de l’application** > **Comptes externes**.

#### Préparation     {#preparation}

La préparation des messages est présentée dans la section [Valider les messages](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: avant tout envoi, les messages doivent être préparés pour valider le contenu et la configuration. Les règles de vérification appliquées lors de la phase de préparation sont définies dans une **typologie**. Par exemple, pour les emails, la préparation porte sur la validation de l’objet, des URL et des images, etc. Sélectionnez, dans ce champ, la typologie à appliquer.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** menu, are presented in [this section](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: permet de calculer la valeur d’étiquette du courrier électronique au cours de la phase de préparation du message à l’aide de champs de personnalisation, de blocs de contenu et de texte dynamique.

   Il est également possible de personnaliser le libellé de la diffusion avec les variables d’événements qui ont été déclarées dans l’activité de signal externe du workflow. Voir à ce propos [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: cette option vous permet d&#39;ajouter des journaux de requête SQL dans le journal pendant la phase de préparation.

#### Paramètres de BAT {#proof-settings}

Cette section vous permet de configurer le préfixe par défaut à utiliser dans l’objet. Voir à ce propos [cette section](../../sending/using/sending-proofs.md).

### Liste des paramètres SMTP des emails {#list-of-email-smtp-parameters}

La section **[!UICONTROL SMTP]** propose les paramètres suivants :

* **[!UICONTROL Character encoding]**: cochez la **[!UICONTROL Force encoding]** case si vous souhaitez forcer le codage des messages, puis sélectionnez le codage à utiliser.
* **[!UICONTROL Bounce mails]**: par défaut, les courriers de retour sont reçus dans la boîte de réception d’erreur de la plateforme (définie dans l’écran **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: cette option permet l&#39;ajout d&#39;en-têtes SMTP supplémentaires à vos messages. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Les valeurs sont automatiquement encodées, si nécessaire.

   >[!IMPORTANT]
   >
   >L’ajout d’un script pour l’insertion d’en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés. La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

### Liste des paramètres d’autorisation d’accès     {#list-of-access-authorization-parameters}

La section **[!UICONTROL Access authorization]** propose les paramètres suivants :

* The **[!UICONTROL Organizational unit]** field allows you to restrict access to this email to certain users. Les utilisateurs associés à l’entité spécifiée ou aux entités parentes auront accès, en lecture et écriture, à cet email. Les utilisateurs associés aux entités filles auront accès, en lecture seule, à cet email.

   >[!NOTE]
   >
   >Le paramétrage des entités organisationnelles est accessible via le menu **Administration** > **Utilisateurs &amp; sécurité**.

* Les **[!UICONTROL Created by]** champs **[!UICONTROL Created]**, **[!UICONTROL Modified by]** et **[!UICONTROL Last modified]** sont automatiquement renseignés.
