---
title: Configuration du canal e-mail dans Adobe Campaign Standard
description: Découvrez comment configurer le canal e-mail dans Adobe Campaign Standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: a1b947acf70803a7350dd626e697318e0ed35f26
workflow-type: tm+mt
source-wordcount: '2908'
ht-degree: 100%

---

# Configuration du canal e-mail{#configuring-email-channel}

En tant qu’[administrateur](../../administration/using/users-management.md#functional-administrators) Campaign, vous pouvez configurer les paramètres du canal email. Ces paramètres avancés comprennent les paramètres généraux du canal email, les comptes de routage email, les règles de gestion des emails et les propriétés des emails. Sur cette page, apprenez à modifier les valeurs par défaut des paramètres généraux d&#39;e-mail et d&#39;envoi.

## Paramètres du canal email {#email-channel-parameters}

L’écran Configuration du canal e-mail permet de définir les paramètres du canal e-mail. Les administrateurs peuvent accéder à ces configurations dans le me **[!UICONTROL Administration] > [!UICONTROL Canaux] > [!UICONTROL Email] > [!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Champs de masques autorisés**

   Les **[!UICONTROL Paramètres d’en-tête des emails envoyés]** répertorient les adresses email autorisées que vous pouvez utiliser pour envoyer des emails à vos destinataires (adresse d’expéditeur) et leur permettre de renvoyer des réponses automatisées telles que des bounces asynchrones, des réponses indiquant leur absence, etc. (adresse de l’erreur).  Adobe Campaign vérifie que les adresses saisies sont valides lors de l’étape de préparation du message. Ce fonctionnement permet d’éviter l’utilisation d’adresses qui pourraient poser des problèmes de délivrabilité.
   * Les adresses d’expéditeur et d’erreur sont configurées par Adobe. Ces champs ne peuvent pas être vides.
   * Vous ne pouvez pas modifier ces champs. Pour mettre à jour une adresse, contactez l’assistance clientèle d’Adobe.
   * Si vous souhaitez ajouter une autre adresse, vous pouvez utiliser le [Panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=fr) pour configurer un nouveau sous-domaine ou contacter l&#39;assistance clientèle d&#39;Adobe. Si plusieurs masques sont utilisés, ils doivent être séparés par des virgules.
   * Il est recommandé de définir des adresses à l’aide d’une étoile comme dans l’expression *@votredomaine.com : il est ainsi possible d’utiliser toute adresse se terminant par votre nom de sous-domaine.

* **Délivrabilité**

   L’**[!UICONTROL identifiant pour les rapports de diffusion]** est fourni par l’assistance clientèle d’Adobe. Il identifie chaque instance à l’aide d’un identifiant de délivrabilité utilisé dans les rapports techniques de délivrabilité.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Paramètres de la diffusion**

   Adobe Campaign envoie les messages à compter de la date de début.

   Lorsqu&#39;un message de diffusion est rejeté en raison d&#39;une erreur temporaire ou d&#39;un soft bounce, Campaign tente à nouveau d&#39;envoyer ce message chaque jour. Utilisez le champ **[!UICONTROL Durée de diffusion des messages]** pour spécifier le délai pendant lequel les reprises peuvent se produire.

   >[!IMPORTANT]
   >
   >**Ce paramètre dans Campaign n’est désormais utilisé que s’il est défini sur 3,5 jours ou moins.** Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte.

   Le champ **[!UICONTROL Durée de validité des ressources en ligne]** est utilisé pour les ressources téléchargées, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d’économiser de l’espace disque).

* **Reprises**

   Les messages qui n’ont pas abouti de manière temporaire font l’objet de reprises automatiques. Voir à ce propos [Reprises après un échec temporaire de diffusion](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

   >[!IMPORTANT]
   >
   >Le nombre maximal de reprises à effectuer et le délai minimal entre les reprises se fondent désormais sur la performance historique et actuelle d’une IP sur un domaine donné. Les paramètres **[!UICONTROL Intervalle entre deux reprises]** et **[!UICONTROL Nombre de Reprises]** dans Campaign seront ignorés.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Paramètres de mise en quarantaine des emails**

   Dans le champ **[!UICONTROL Durée entre deux erreurs significatives]**, saisissez une valeur pour définir le temps d’attente de l’application avant d’incrémenter le compteur d’erreurs en cas d’échec lié à un soft bounce. La valeur par défaut est **&quot;1d&quot;**, pour 1 jour.

   Lorsque la valeur **[!UICONTROL Nombre maximum d’erreurs avant mise en quarantaine]** est atteinte, l’adresse email est mise en quarantaine. La valeur par défaut est **&quot;5&quot;** : l&#39;adresse est mise en quarantaine à la cinquième erreur. Cela signifie que ce contact sera automatiquement exclu des prochaines diffusions.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Pour plus d’informations sur ce sujet, voir [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md).

## Comptes de routage email   {#email-routing-accounts}

Le compte externe **[!UICONTROL Routage e-mail intégré]** est fourni par défaut. Il contient les paramètres techniques qui permettent à l’application d’envoyer des emails.

![](assets/channels_2.png)

Le type de compte doit toujours être défini sur **[!UICONTROL Routage]**, le canal sur **[!UICONTROL Email]** et le mode de diffusion sur **[!UICONTROL Envoi en masse]**.

**Rubrique connexe**:

[Comptes externes](../../administration/using/external-accounts.md)

## Règles de gestion des e-mails {#email-processing-rules}

Les **[!UICONTROL règles de gestion des emails]** sont accessibles pour les administrateurs via le menu **[!UICONTROL Administration > Canaux > Email]**.

>[!IMPORTANT]
>
>Les domaines d&#39;email et les règles MX sont désormais gérés automatiquement<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> et ne peuvent pas être modifiés.

* La signature d’authentification des emails **DKIM (DomainKeys Identified Mail)** est effectuée pour tous les messages et tous les domaines. Il ne se signe pas avec **Sender ID**, **DomainKeys** ou **S/MIME**.
* Les règles MX personnalisent automatiquement votre débit par domaine en fonction de votre propre réputation d&#39;email historique et des commentaires en temps réel provenant des domaines où vous envoyez des emails.

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### Mails rebonds {#bounce-mails}

Les bounces asynchrones sont toujours qualifiés par le processus Campaign inMail à l’aide des règles **[!UICONTROL Emails bounce]**.

Ces règles contiennent la liste des chaînes de caractères qui peuvent être renvoyées par les serveurs distants et qui permettent de qualifier l&#39;erreur en **Hard**, **Soft** ou **Ignoré**.

>[!IMPORTANT]
>
>Les messages d’erreur d’échec de diffusion synchrone sont désormais qualifiés par le MTA amélioré d’Adobe Campaign, qui détermine le type et la qualification du bounce et renvoie ces informations à Campaign.

Pour plus d’informations sur la qualification des emails bounce, reportez-vous à cette [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Liste des propriétés des emails   {#list-of-email-properties}

Cette section décrit la liste des paramètres disponibles dans l’écran des propriétés d’un email ou d’un modèle d’email.

>[!NOTE]
>
>Certains paramètres sont uniquement disponibles dans les modèles. Les paramètres accessibles [dépendent de vos autorisations](../../administration/using/users-management.md).

Pour modifier les propriétés d’un e-mail ou d’un modèle d’e-mail, utilisez le bouton **[!UICONTROL Editer les propriétés]**.

![](assets/delivery_options_1.png)

### Paramètres généraux {#general-parameters}

En haut de l’écran des paramètres d’email, identifiez l’email à l’aide des champs **[!UICONTROL Libellé]** et **[!UICONTROL ID]**. Ces informations apparaissent dans l’interface mais ne sont pas visibles par les destinataires des messages.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L’identifiant doit être unique.

Utilisez le champ **[!UICONTROL Marque]** pour sélectionner la marque liée à la diffusion. Pour plus d&#39;informations sur l&#39;utilisation des marques et leur paramétrage, consultez la section [Branding](../../administration/using/branding.md).

Dans le champ **[!UICONTROL Campagne]**, saisissez la campagne associée à l&#39;e-mail.

Vous pouvez également ajouter une **[!UICONTROL Description]** dans le champ correspondant et modifier l’image affichée sur la miniature de l’e-mail, dans les listes.

### Paramètres d’envoi {#sending-parameters}

La section **[!UICONTROL Envoi]** est uniquement disponible pour les modèles d’email. Elle comprend les paramètres suivants :

#### Paramètres de reprises {#retries-parameters}

Les messages qui n’ont pas abouti de manière temporaire font l’objet de reprises automatiques. Voir à ce propos [Reprises après un échec temporaire de diffusion](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!IMPORTANT]
>
>Le délai minimum entre traitements et le nombre maximum de reprises à effectuer se basent désormais sur la performance historique et actuelle d’une IP, à la fois historiquement et sur un domaine donné. L&#39;**[!UICONTROL Intervalle entre deux reprises]** et le **[!UICONTROL Nombre de reprises max.]** dans Campaign seront ignorés.

Le **paramètre de durée de diffusion** (défini dans la section [Paramètres de la période de validité](#validity-period-parameters)) **configuré dans Campaign sera toujours respecté, mais jusqu’à 3,5 jours seulement**. À ce stade, tout message de la file d’attente des reprises est supprimé de la file d’attente et renvoyé sous forme de bounce. Pour plus d’informations sur les échecs de diffusion, consultez cette [section](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Paramètres de format des emails   {#email-format-parameters}

Vous pouvez paramétrer le format des emails envoyés. Trois options sont disponibles :

* **Tenir compte des préférences des destinataires** (mode par défaut) : le format du message est défini en fonction des informations enregistrées dans le profil du destinataire et stockées par défaut dans le champ **Format des emails** (@emailFormat). Si un destinataire souhaite recevoir les messages dans un format particulier, ce format lui est envoyé. Si ce champ n’est pas renseigné, le message sera envoyé en multipart-alternative (voir ci-dessous).
* **Laisser le mailer des destinataires choisir le format le plus adapté (multipart-alternative)** : le message contient les deux formats : texte et HTML. Le format affiché lors de la réception dépend de la configuration du logiciel de messagerie du destinataire (multipart-alternative).

   >[!IMPORTANT]
   >
   >Cette option inclut les deux versions du message et, par conséquent, a un impact sur le débit de diffusion, car la taille du message est supérieure.

* **Envoyer tous les messages au format texte** : le message est envoyé au format texte. Le format HTML ne sera pas envoyé, mais uniquement utilisé pour la page miroir, lorsque le destinataire clique sur le lien dans le message.

#### Mode test SMTP {#smtp-test-mode}

Utilisez l&#39;option **[!UICONTROL Activer le mode test SMTP]** pour tester l&#39;envoi d&#39;e-mails via une connexion SMTP sans envoyer réellement de messages. La diffusion est traitée jusqu&#39;à la connexion au serveur SMTP mais n&#39;est pas envoyée : pour chaque destinataire de la diffusion, Campaign se connecte au serveur du fournisseur SMTP, exécute la commande SMTP RCPT TO et ferme la connexion avant la commande SMTP DATA.

![](assets/smtp-test-mode.png)

Cette option est disponible pour les emails et les modèles d’email.

Si vous activez l’option de mode test SMTP pour un modèle d’email, cette option sera activée pour tous les emails créés à partir de ce modèle.

>[!IMPORTANT]
>
>Lorsque cette option est activée pour un email, aucun message n’est envoyé tant qu’elle n’est pas décochée.
>Un avertissement s’affiche dans le tableau de bord de l’email ou du modèle d’email.

Pour plus d’informations sur la configuration SMTP, reportez-vous à la section [Liste des paramètres SMTP des emails](#list-of-email-smtp-parameters).

### Paramètres de période de validité   {#validity-period-parameters}

La section **[!UICONTROL Période de validité]** propose les paramètres suivants :

![](assets/delivery-validity-period.png)

* **[!UICONTROL Fixer explicitement les dates de validité]** : lorsque cette case est décochée, vous devez renseigner une durée dans les champs **[!UICONTROL Durée de diffusion]** et **[!UICONTROL Validité des ressources.]**

   Cochez cette case si vous souhaitez définir des dates et heures précises.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Durée de diffusion]**  / **[!UICONTROL Limite de validité pour l&#39;envoi des messages]** : Adobe Campaign envoie les messages à partir de la date de début. Utilisez ce champ pour indiquer la période pendant laquelle les messages peuvent être envoyés.

   >[!IMPORTANT]
   >
   >**Vous devez définir une valeur allant jusqu’à 3,5 jours.** Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte.
   >
   >Le paramètre **[!UICONTROL Durée de diffusion]** ne s’applique pas aux messages transactionnels. Pour plus d’informations sur les messages transactionnels, voir [cette section](../../channels/using/getting-started-with-transactional-msg.md).

* **[!UICONTROL Durée de validité des ressources]** / **[!UICONTROL Date limite de validité des ressources]** : ce champ est utilisé pour les ressources mises en ligne, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d’économiser de l’espace disque).
* **[!UICONTROL Gestion de la page miroir]** : la page miroir est une page HTML accessible en ligne via un navigateur web et dont le contenu est identique à celui de l’email. Par défaut, la page miroir est générée si le lien est inséré dans le contenu du mail. Utilisez ce champ pour modifier le mode de génération de cette page :

   * **[!UICONTROL Générer la page miroir si le lien apparaît dans le contenu du message]** (mode par défaut) : la page miroir est générée si le lien est inséré dans le contenu du mail.
   * **Forcer la génération de la page miroir** : même si aucun lien vers la page miroir n’est inséré dans les messages, la page miroir sera créée.
   * **Ne pas générer de page miroir** : aucune page miroir n’est générée, même si le lien est présent dans les messages.
   * **Générer une page miroir accessible depuis l’identifiant du message** : cette option permet d’accéder au contenu de la page miroir, avec les informations de personnalisation, dans l’écran des logs de diffusion.

   >[!IMPORTANT]
   >
   >La page miroir n&#39;est générée que si un contenu HTML a été défini pour l&#39;e-mail.


### Paramètres du tracking {#tracking-parameters}

La section **[!UICONTROL Tracking]** propose les paramètres suivants :

* **[!UICONTROL Activer le tracking]** : utilisez cette option pour activer/désactiver le tracking des URL des messages. Pour gérer le tracking pour chaque URL de message, utilisez l’icône **[!UICONTROL Liens]** dans la barre d’actions Concepteur d’email. Voir [À propos des URL trackées](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Limite de validité du tracking]** : utilisez cette option pour définir la durée d&#39;activation du tracking sur les URL.
* **[!UICONTROL URL de substitution des URL périmées]** : utilisez cette option pour renseigner une URL vers une page web de secours. Elle s&#39;affiche après expiration du tracking.
* **[!UICONTROL Utiliser le pixel de tracking en haut de l&#39;e-mail]** : utilisez cette option pour déplacer le pixel de tracking en haut de l&#39;e-mail plutôt qu&#39;en bas. Par défaut, ce pixel se trouve au bas de vos e-mails. Si vous envoyez des messages volumineux, envisagez de déplacer ce pixel en haut de vos e-mails plutôt qu&#39;en bas afin d&#39;améliorer le tracking des ouvertures. À défaut, le pixel de tracking peut être coupé par certains fournisseurs de messagerie.

### Paramètres avancés {#advanced-parameters}

La section **[!UICONTROL Paramètres avancés]** propose les paramètres suivants :

Les premiers champs vous permettent de saisir les informations nécessaires pour élaborer les en-têtes d’email. Vous pouvez gérer ici l’adresse de réponse et le texte ainsi que l’adresse de l’expéditeur (qui occupe le champ « De : »). Ces informations peuvent être personnalisées.

Cliquez sur le bouton à droite du champ qui va être modifié, puis ajoutez le champ de personnalisation, le bloc de contenu ou le texte dynamique.

![](assets/advancedparameters.png)

L’insertion et l’utilisation du contenu de personnalisation sont présentées dans la documentation [Personnalisation du contenu des emails](../../designing/using/personalization.md).

#### Contexte de ciblage   {#target-context}

Utilisez le contexte de ciblage pour définir l&#39;ensemble des tables qui seront utilisées pour le ciblage (dans l&#39;écran de définition des audiences) et la personnalisation (définition de champs de personnalisation, dans l&#39;éditeur de contenu HTML) de l&#39;e-mail.

#### Routage {#routing}

Ce champ indique le mode de routage utilisé. Il référence un compte externe. Par exemple, cela peut être utile si vous souhaitez utiliser un compte externe contenant des paramétrages de branding spécifiques.

>[!NOTE]
>
>Les comptes externes sont accessibles via le menu **Administration** > **Paramétrage de l’application** > **Comptes externes**.

#### Préparation  {#preparation}

La préparation des messages est présentée dans la section [Valider les messages](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typologie]** : avant tout envoi, vous devez préparer les messages afin d’en valider le contenu et le paramétrage. Les règles de vérification appliquées lors de la phase de préparation sont définies dans une **typologie**. Par exemple, pour les emails, la préparation porte sur la validation de l’objet, des URL et des images, etc. Sélectionnez, dans ce champ, la typologie à appliquer.

   >[!NOTE]
   >
   >Les typologies, accessibles via le menu **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Typologies]**, sont présentées dans [cette section](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Calculer le libellé lors de la préparation de la diffusion]** : utilisez cette option pour calculer la valeur du libellé de l&#39;e-mail pendant la phase de préparation du message à l&#39;aide des champs de personnalisation, des blocs de contenu et du texte dynamique.

   Il est également possible de personnaliser le libellé de la diffusion avec les variables d’événements qui ont été déclarées dans l’activité de signal externe du workflow. Pour plus d’informations, consultez [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Enregistrer les requêtes SQL dans le journal]** : utilisez cette option pour ajouter les logs des requêtes SQL dans le journal lors de la phase de préparation.

#### Paramètres de BAT {#proof-settings}

Dans cette section, vous pouvez configurer le préfixe par défaut à utiliser dans l&#39;objet des messages de BAT. Pour en savoir plus sur les BAT, consultez [cette section](../../sending/using/sending-proofs.md).

### Liste des paramètres SMTP des emails {#list-of-email-smtp-parameters}

La section **[!UICONTROL SMTP]** propose les paramètres suivants :

* **[!UICONTROL Encodage des caractères]** : cochez la case **[!UICONTROL Forcer l’encodage]** si vous souhaitez forcer l’encodage des messages, puis sélectionnez le codage à utiliser.
* **[!UICONTROL Mails rebonds]** : par défaut, les mails rebonds sont récupérés dans la boîte d’erreur de la plateforme (définie dans l’écran **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration).]** Si vous souhaitez définir une adresse d’erreur spécifique pour un email, saisissez l’adresse dans le champ **[!UICONTROL Adresse des erreurs]**.
* **[!UICONTROL En-têtes SMTP supplémentaires]** : cette option permet d’ajouter des en-têtes SMTP supplémentaires à vos messages. Le script saisi dans le champ **[!UICONTROL En-têtes]** doit comporter un en-tête par ligne, sous la forme **nom:valeur**. Les valeurs sont automatiquement encodées, si nécessaire.

   >[!IMPORTANT]
   >
   >L’ajout d’un script pour l’insertion d’en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés. La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

### Liste des paramètres d’autorisation d’accès   {#list-of-access-authorization-parameters}

La section **[!UICONTROL Autorisation d&#39;accès]** propose les paramètres suivants :

* Le champ **[!UICONTROL Entité organisationnelle]** est utilisé pour restreindre l&#39;accès de cet e-mail à certains utilisateurs. Les utilisateurs associés à l’entité spécifiée ou aux entités parentes auront accès, en lecture et écriture, à cet email. Les utilisateurs associés aux entités enfants auront accès, en lecture seule, à cet email.

   >[!NOTE]
   >
   >Le paramétrage des entités organisationnelles est accessible via le menu **Administration** > **Utilisateurs &amp; sécurité**.

* Les champs **[!UICONTROL Créé par]**, **[!UICONTROL Créé le]**, **[!UICONTROL Modification par]** et **[!UICONTROL Dernière modification]** sont automatiquement remplis.

## Paramètres hérités {#legacy-settings}

Si vous n’exécutez **PAS** la dernière version de Campaign, les paramètres et les sections d’interface utilisateur décrits ci-dessous s’appliquent toujours à vous.

### Reprises {#legacy-retries}

Les paramètres **[!UICONTROL Reprises]** dans le [menu Configuration](#email-channel-parameters) et dans les [Paramètres d&#39;envoi](#retries-parameters) des propriétés d&#39;email indiquent le nombre de reprises à effectuer le jour suivant le démarrage de l&#39;envoi (**[!UICONTROL Nombre de Reprises]** / **[!UICONTROL Nombre de reprises max.]**) et délai minimal entre les reprises (**[!UICONTROL Intervalle entre deux reprises]**).

Le nombre de reprises peut être changé de manière globale (contactez l’administrateur technique Adobe) ou pour chaque diffusion ou modèle de diffusion.

Par défaut, cinq reprises sont planifiées le premier jour de l’envoi, avec un intervalle minimum d’une heure, réparties sur les 24h de la journée. Une nouvelle tentative par jour est programmée après cela et jusqu&#39;à l&#39;échéance de la diffusion, définie globalement dans la section **[!UICONTROL Paramètres de diffusion]** du menu **[!UICONTROL Configuration]**, ou dans la section **[!UICONTROL Période de validité]** au niveau de la diffusion (voir la section [Durée de diffusion](#legacy-delivery-duration) ci-dessous).

### Durée de diffusion {#legacy-delivery-duration}

Utilisez le paramètre **[!UICONTROL Durée de diffusion des messages]** dans le [menu Configuration](#email-channel-parameters) pour spécifier la période pendant laquelle tout message contenu dans la diffusion qui entraîne une erreur temporaire ou un soft bounce fera l&#39;objet d&#39;une nouvelle reprise.

Utilisez la **[!UICONTROL Durée de diffusion]** ou la **[!UICONTROL Limite de validité pour l&#39;envoi des messages]** dans la section [Paramètres de période de validité](#validity-period-parameters) pour spécifier la durée pendant laquelle les messages peuvent être envoyés.

### Règles de gestion des e-mails {#legacy-email-processing-rules}

Les règles **[!UICONTROL Gestion des MX]**, **[!UICONTROL E-mails bounce]** et **[!UICONTROL Gestion de domaine]** sont accessibles et modifiables par les administrateurs via le menu **[!UICONTROL Administration > Canaux > E-mail > Règles de gestion des e-mails]**. [En savoir plus](#email-processing-rules).

### Qualification des e-mails bounce {#legacy-bounce-mail-qualification}

Pour répertorier les différents bounces ainsi que les types d&#39;erreur et raisons associés, cliquez sur le logo **Adobe** en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Canaux > Quarantaines > Qualification des messages]**.

Les statuts de qualification des bounces sont les suivants :

* **[!UICONTROL A qualifier]** : le mail bounce n&#39;a pas pu être qualifié. La qualification doit être confiée à l&#39;équipe chargée de la délivrabilité afin de garantir le bon fonctionnement de la délivrabilité de la plateforme. Tant qu&#39;il n&#39;est pas qualifié, le mail bounce n&#39;est pas utilisé pour enrichir la liste des règles de gestion des emails.
* **[!UICONTROL Conserver]** : le mail bounce a été qualifié et sera utilisé par le workflow **Mise à jour pour la délivrabilité** pour être comparé aux règles de gestion des emails existantes et en enrichir la liste.
* **[!UICONTROL Ignorer]** : le mail rebond a été qualifié mais ne sera pas utilisé par le workflow **Mise à jour pour la délivrabilité**. Il ne sera donc pas envoyé vers les instances clientes.

>[!NOTE]
>
>En cas de panne d&#39;un FAI, les emails envoyés via Campaign seront incorrectement marqués comme bounces. Pour corriger ce problème, vous devez mettre à jour la qualification des rebonds. [En savoir plus](../../administration/using/update-bounce-qualification.md).

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### Rapports d&#39;indicateur de messages diffusés {#legacy-delivered-status-report}

Dans la vue **[!UICONTROL Résumé]** de chaque message, le pourcentage **[!UICONTROL Diffusés]** augmentera progressivement tout au long de la période de validité de la diffusion, à mesure que les soft et hard bounces sont signalés.

Les messages soft bounce s&#39;affichent sous la forme **[!UICONTROL Échec]** le premier jour après la diffusion. Ces messages font l&#39;objet de reprises chaque jour, et ce jusqu&#39;à la fin de la période de validité de la diffusion.
