---
title: Configuration du canal de messagerie dans Adobe Campaign Standard
description: Découvrez comment configurer le canal de messagerie dans Adobe Campaign Standard.
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
source-git-commit: 9163a375a4d2345e94a62e38475cb90bd203ce48

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

## Comptes de routage email  {#email-routing-accounts}

Le compte **[!UICONTROL Integrated email routing]** externe est fourni par défaut. Il contient les paramètres techniques qui permettent à l&#39;application d&#39;envoyer des emails.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Rubrique connexe** :

[Comptes externes](../../administration/using/external-accounts.md)

## Règles de gestion des emails  {#email-processing-rules}

Les administrateurs **[!UICONTROL Email processing rules]** peuvent y accéder par le **[!UICONTROL Administration > Channels > Email]** menu.

Ces règles contiennent la liste des chaînes de caractères qui peuvent être renvoyées par les serveurs distants et qui permettent de qualifier l&#39;erreur en **Hard**, **Soft** ou **Ignoré**.

Les règles par défaut sont les suivantes :

### Mails rebonds {#bounce-mails}

Lors de l&#39;échec d&#39;un envoi d&#39;email, le serveur de messagerie distant renvoie un message d&#39;erreur rebond à l&#39;adresse spécifiée dans les paramètres de l&#39;application.

Adobe Campaign compare le contenu de chaque mail rebond aux chaînes disponibles dans la liste des règles puis attribue l&#39;un des trois types d&#39;erreur.

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, les qualifications de rebonds dans le tableau Campagne ne sont plus utilisées. **[!UICONTROL Message qualification]** Pour les messages d’erreur d’échec de remise synchrone, la MTA améliorée détermine le type et la qualification de rebond et renvoie ces informations à Campaign. Les rebonds asynchrones sont toujours qualifiés par le processus inMail.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

L&#39;utilisateur peut créer ses propres règles.

>[!IMPORTANT]
>
>Lors d&#39;un import de package et lors de la mise à jour des données par le workflow **Mise à jour pour la délivrabilité**, les règles mail créées par l&#39;utilisateur sont écrasées.

### Gestion des domaines emails {#managing-email-domains}

Les règles de gestion de domaine permettent de réguler le flux des courriers électroniques sortants pour un domaine spécifique. Ils échantillonnent les messages de rebond et bloquent l’envoi, le cas échéant.

Le serveur de messagerie d&#39;Adobe Campaign applique les règles spécifiques aux domaines, puis celles du cas général symbolisé par un astérisque dans la liste des règles.

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, la signature de l’authentification par courrier électronique DKIM (DomainKeys Identified Mail) est effectuée par la MTA améliorée. Dans le cadre de la mise à niveau améliorée de la MTA, la signature de la messagerie instantanée par la MTA de campagne native sera désactivée dans le **[!UICONTROL Domain management]** tableau.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Pour configurer des règles de gestion de domaines, il vous suffit de fixer un seuil et de sélectionner certains paramètres SMTP. Le **seuil** est une limite calculée en pourcentage d&#39;erreur au-delà de laquelle tout message vers un domaine spécifique est bloqué.

Les **paramètres SMTP** agissent comme des filtres appliqués pour une règle de blocage.

* Vous pouvez choisir d&#39;activer ou non certaines normes d&#39;identification et clés de cryptage pour vérifier le nom de domaine, comme **Sender ID**, **DomainKeys**, **DKIM**, **S/MIME**.
* **Relais SMTP** : permet de configurer l&#39;adresse IP et le port d&#39;un serveur relais pour un domaine particulier.

### Gestion des MX {#mx-management}

Chaque règle fixe un masque d&#39;adresse du MX. Tout MX dont le nom correspond à ce masque est éligible. Le masque peut contenir les caractères génériques &quot;*&quot; et &quot;?&quot;.

Par exemple, les adresses :

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

sont compatibles avec les masques :

* *.yahoo.com
* ?.mx.yahoo.com

Ces règles sont appliquées dans l&#39;ordre : la première règle dont le masque de MX est compatible avec le MX ciblé est appliquée.

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, les règles de débit de remise de gestion **MX d’Adobe Campaign** ne sont plus utilisées. La MTA améliorée utilise ses propres règles MX qui lui permettent de personnaliser votre débit par domaine en fonction de votre propre réputation de courriel historique et des commentaires en temps réel provenant des domaines où vous envoyez des courriers électroniques.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Les paramètres disponibles pour chacune des règles sont les suivants :

* **[!UICONTROL Range of IDs]**: cette option vous permet d’indiquer les plages d’identifiants (publicId) pour lesquelles la règle s’applique. Vous pouvez indiquer :

   * Un nombre : la règle ne s&#39;appliquera qu&#39;à ce publicId.
   * Une plage de nombres (nombre1-nombre2) la règle s&#39;appliquera à tous les publicId compris entre ces deux nombres.
   Lorsque ce champ est vide, la règle s&#39;applique à tous les identifiants.

* **[!UICONTROL Shared]**: cette option indique que le nombre le plus élevé de messages par heure et de connexions s’applique à tous les MX liés à cette règle.
* **[!UICONTROL Maximum number of connections]**: nombre maximal de connexions simultanées à un MX à partir d’une adresse donnée.
* **Nombre maximum de messages** : nombre maximum de messages qui peuvent être envoyés sur une connexion. Au-delà, la connexion est fermée puis une nouvelle est rouverte.
* **[!UICONTROL Messages per hour]**: nombre maximal de messages pouvant être envoyés en une heure pour un MX via une adresse donnée.

>[!IMPORTANT]
>
>* Le serveur de diffusion (MTA) doit être relancé si les paramètres sont modifiés.
>* La modification ou la création de règles de gestion est réservée à des utilisateurs experts.
>



## Liste des propriétés des emails  {#list-of-email-properties}

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

#### Paramètres de format des emails  {#email-format-parameters}

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

### Paramètres de période de validité  {#validity-period-parameters}

La section **[!UICONTROL Validity period]** propose les paramètres suivants :

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: lorsque cette case est désactivée, vous devez saisir une durée dans les **[!UICONTROL Delivery duration]** champs et **[!UICONTROL Resource validity limit]** . Cochez cette case si vous souhaitez définir des dates et heures précises.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**: Adobe Campaign envoie les messages à compter de la date de début. Ce champ permet de définir la durée pendant laquelle les messages pourront être envoyés.

   >[!IMPORTANT]
   >
   >Une fois la mise à niveau vers la MTA améliorée, le **[!UICONTROL Delivery duration]** paramètre de vos livraisons de campagne n’est utilisé que s’il est défini sur 3,5 jours ou moins. Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte. Tous les impacts sont détaillés dans le document MTA [amélioré d’](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) Adobe Campaign.

* **[!UICONTROL Resource validity duration]**: ce champ est utilisé pour les ressources téléchargées, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d&#39;économiser de l&#39;espace disque).
* **[!UICONTROL Mirror page management]**: la page miroir est une page HTML accessible en ligne via un navigateur Web. et dont le contenu est identique à celui de l&#39;email. Par défaut, la page miroir est générée si le lien est inséré dans le contenu du mail. Ce champ permet de modifier le mode de génération de cette page :

   >[!IMPORTANT]
   >
   >Un contenu HTML doit avoir été défini pour l&#39;email pour que la page miroir soit créée.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (mode par défaut) : la page miroir est générée si le lien est inséré dans le contenu du courrier.
   * **Forcer la génération de la page miroir** : même si aucun lien vers la page miroir n&#39;est inséré dans les messages, la page miroir sera créée.
   * **Ne pas générer de page miroir** : aucune page miroir n&#39;est générée, même si le lien est présent dans les messages.
   * **Générer une page miroir accessible depuis l&#39;identifiant du message** : cette option permet d&#39;accéder au contenu de la page miroir, avec les informations de personnalisation, dans l&#39;écran des logs de diffusion.

>[!NOTE]
>
>Le **[!UICONTROL Delivery duration]** paramètre ne s’applique pas aux messages transactionnels. Pour plus d&#39;informations sur les messages transactionnels, voir [cette section](../../channels/using/about-transactional-messaging.md).

### Paramètres du tracking  {#tracking-parameters}

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

#### Contexte de ciblage  {#target-context}

Le contexte de ciblage permet de définir l&#39;ensemble les tables qui seront utilisées pour le ciblage (dans l&#39;écran de définition des audiences) et la personnalisation (définition de champs de personnalisation, dans l&#39;éditeur de contenu HTML) de l&#39;email.

#### Routage  {#routing}

Ce champ indique le mode de routage utilisé. Il référence un compte externe. Par exemple, cela peut être utile si vous souhaitez utiliser un compte externe contenant des paramétrages de branding spécifiques.

>[!NOTE]
>
>Les comptes externes sont accessibles via le menu **Administration** > **Paramétrage de l&#39;application** > **Comptes externes**.

#### Préparation  {#preparation}

La préparation des messages est présentée dans la section [Valider les messages](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: avant tout envoi, les messages doivent être préparés pour valider le contenu et la configuration. Les règles de vérification appliquées lors de la phase de préparation sont définies dans une **typologie**. Par exemple, pour les emails, la préparation porte sur la validation de l&#39;objet, des URL et des images, etc. Sélectionnez, dans ce champ, la typologie à appliquer.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery preparation]**: permet de calculer la valeur d’étiquette du courrier électronique pendant la phase de préparation du message à l’aide de champs de personnalisation, de blocs de contenu et de texte dynamique.

   Il est également possible de personnaliser le libellé de la diffusion avec les variables d&#39;événements qui ont été déclarées dans l&#39;activité de signal externe du workflow. Voir à ce propos [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: cette option vous permet d&#39;ajouter des journaux de requête SQL dans le journal pendant la phase de préparation.

### Liste des paramètres SMTP des emails {#list-of-email-smtp-parameters}

La section **[!UICONTROL SMTP]** propose les paramètres suivants :

* **[!UICONTROL Character encoding]**: cochez la **[!UICONTROL Force encoding]** case si vous souhaitez forcer le codage des messages, puis sélectionnez le codage à utiliser.
* **[!UICONTROL Bounce mails]**: par défaut, les messages de retour sont reçus dans la boîte de réception d’erreur de la plateforme (définie dans l’ **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: cette option permet d’ajouter des en-têtes SMTP supplémentaires à vos messages. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Les valeurs sont automatiquement encodées, si nécessaire.

   >[!IMPORTANT]
   >
   >L&#39;ajout d&#39;un script pour l&#39;insertion d&#39;en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés. La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

### Liste des paramètres d&#39;autorisation d&#39;accès  {#list-of-access-authorization-parameters}

La section **[!UICONTROL Access authorization]** propose les paramètres suivants :

* The **[!UICONTROL Organizational unit]** field allows you to restrict access to this email to certain users. Les utilisateurs associés à l&#39;entité spécifiée ou aux entités parentes auront accès, en lecture et écriture, à cet email. Les utilisateurs associés aux entités filles auront accès, en lecture seule, à cet email.

   >[!NOTE]
   >
   >Le paramétrage des entités organisationnelles est accessible via le menu **Administration** > **Utilisateurs &amp; sécurité**.

* Les champs **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** et **[!UICONTROL Last modified]** sont automatiquement complétés.

## Archiver des emails {#archiving-emails}

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme.

Toutefois, Adobe Campaign ne gère pas lui-même les fichiers archivés : il vous permet d&#39;envoyer les messages de votre choix à une adresse dédiée, depuis laquelle ils peuvent être traités et archivés dans un système externe.

Lorsqu&#39;elle est activée dans le modèle de diffusion, cette fonctionnalité vous permet d&#39;envoyer une copie exacte des messages envoyés correspondants à une adresse email en bcc (invisible pour les destinataires de diffusion) que vous devez spécifier.

### Recommandations et limitations  {#recommendations-and-limitations}

* Cette fonctionnalité est en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l&#39;activer.
* L’adresse CC de votre choix doit être fournie à l’équipe Adobe qui la configurera pour vous.
* Vous ne pouvez utiliser qu&#39;une seule adresse email en Cci.
* Seuls les emails envoyés sont pris en compte, les rebonds ne le sont pas.
* Pour des raisons de confidentialité, les emails en Cci doivent être traités dans un système d&#39;archivage capable de stocker en toute sécurité les informations d&#39;identification personnelles (PII).
* Lors de la création d&#39;un modèle de diffusion, l&#39;option Email BCC n&#39;est pas activée par défaut, même si elle a été achetée. Vous devez l&#39;activer manuellement dans chaque modèle de diffusion où vous souhaitez l&#39;utiliser.

### Activer l&#39;archivage des emails  {#activating-email-archiving}

La fonctionnalité Email BCC est activée dans le [modèle d&#39;email](../../start/using/marketing-activity-templates.md) par le biais d&#39;une option dédiée :

1. Accédez à **Ressources** > **Modèles** > **Modèles de diffusion**.
1. Dupliquez le **[!UICONTROL Send via email]** modèle prêt à l’emploi.
1. Sélectionnez le modèle dupliqué.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Développez la **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.
