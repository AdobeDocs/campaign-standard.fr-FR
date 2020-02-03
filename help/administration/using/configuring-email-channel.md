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
source-git-commit: 28d92b0024576c78fc8d71e3f1b59ac4508f9c34

---


# Configuration du canal Email{#configuring-email-channel}

## Paramètres du canal email {#email-channel-parameters}

L&#39;écran Configuration email vous permet de définir les paramètres du canal email.

![](assets/channels_1.png)

* **Paramètres d&#39;en-tête des emails envoyés**

   Cette section vous permet d&#39;indiquer les **[!UICONTROL masques]**autorisés pour l&#39;adresse expéditeur et l&#39;adresse d&#39;erreur. Au besoin, ces masques doivent être séparés les uns des autres par une virgule. Ce paramétrage est facultatif. Lorsque ces champs sont renseignés, Adobe Campaign contrôle, au moment de la préparation des messages que les adresses renseignées dans l&#39;email sont valables. Ce fonctionnement permet d&#39;éviter l&#39;utilisation d&#39;adresses qui pourraient poser des problèmes de délivrabilité. Les adresses d&#39;expédition doivent être configurées sur le serveur de diffusion.

* **Délivrabilité**

   Cet identifiant vous est fourni par le support. Il est nécessaire au bon fonctionnement des rapports de délivrabilité.

* **Paramètres de la diffusion**

   Adobe Campaign envoie les messages à compter de la date de début. Le champ **[!UICONTROL Durée de diffusion des messages]**vous permet de spécifier la durée pendant laquelle les messages peuvent être envoyés.

   Le champ **[!UICONTROL Durée de validité des ressources en ligne]**est utilisé pour les ressources téléchargées, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d&#39;économiser de l&#39;espace disque).

* **Reprises**

   Les messages qui n&#39;ont pas abouti de manière temporaire font l&#39;objet de reprises automatiques. Cette section indique combien de reprises doivent être effectuées le premier jour après le démarrage de l&#39;envoi (**Nombre de reprises**) ainsi que le délai minimum entre deux reprises (**Période des reprises**).

   Par défaut, cinq reprises sont planifiées le premier jour de l&#39;envoi, avec un intervalle minimum d&#39;une heure, réparties sur les 24h de la journée. Les jours suivants, une reprise par jour est programmée jusqu&#39;à la date limite d&#39;envoi, définie dans la section **[!UICONTROL Paramètres de diffusion]**.

* **Paramètres de mise en quarantaine des emails**

   Dans le champ **[!UICONTROL Durée entre deux erreurs significatives]**, saisissez une valeur pour définir le temps d&#39;attente de l&#39;application avant d&#39;incrémenter le compteur d&#39;erreurs en cas d&#39;échec. Valeur par défaut :**&quot;1j&quot;**, pour 1 jour.

   Lorsque la valeur **[!UICONTROL Nombre maximum d&#39;erreurs avant mise en quarantaine]**est atteinte, l&#39;adresse email est mise en quarantaine. Valeur par défaut :**&quot;5&quot;** : l&#39;adresse est mise en quarantaine à la sixième erreur. Cela signifie que ce contact sera automatiquement exclu des prochaines diffusions.

**Rubrique connexe** :

[Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)

## Comptes de routage email {#email-routing-accounts}

Le compte externe **[!UICONTROL Routage e-mail intégré]**est fourni par défaut. Il contient les paramètres techniques qui permettent à l&#39;application d&#39;envoyer des emails.

![](assets/channels_2.png)

Le type de compte doit toujours être défini sur **[!UICONTROL Routage]**, le canal sur**[!UICONTROL  Email]** et le mode de diffusion sur **[!UICONTROL Envoi en masse]**.

**Rubrique connexe** :

[Comptes externes](../../administration/using/external-accounts.md)

## Règles de gestion des emails {#email-processing-rules}

Les règles **[!UICONTROL de traitement du]**courrier électronique sont accessibles par les administrateurs via le menu**[!UICONTROL  Administration > Canaux > Courriel]** .

Ces règles contiennent la liste des chaînes de caractères qui peuvent être renvoyées par les serveurs distants et qui permettent de qualifier l&#39;erreur en **Hard**, **Soft** ou **Ignoré**.

Les règles par défaut sont les suivantes :

### Mails rebonds {#bounce-mails}

Lors de l&#39;échec d&#39;un envoi d&#39;email, le serveur de messagerie distant renvoie un message d&#39;erreur rebond à l&#39;adresse spécifiée dans les paramètres de l&#39;application. Adobe Campaign compare le contenu de chaque mail rebond aux chaînes disponibles dans la liste des règles puis attribue l&#39;un des trois types d&#39;erreur.

L&#39;utilisateur peut créer ses propres règles.

>[!IMPORTANT]
>
>Lors d&#39;un import de package et lors de la mise à jour des données par le workflow **Mise à jour pour la délivrabilité**, les règles mail créées par l&#39;utilisateur sont écrasées.

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, les qualifications de rebond dans le tableau de qualification ****Message de campagne ne sont plus utilisées. Pour les messages d’erreur d’échec de remise synchrone, la MTA améliorée détermine le type et la qualification de rebond et renvoie ces informations à Campaign. Les rebonds asynchrones sont toujours qualifiés par le processus inMail.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### Gestion des domaines emails {#managing-email-domains}

Les règles de gestion de domaine permettent de réguler le flux des courriers électroniques sortants pour un domaine spécifique. Ils échantillonnent les messages de rebond et bloquent l’envoi, le cas échéant. Le serveur de messagerie Adobe Campaign applique des règles spécifiques aux domaines, puis les règles de la casse générale représentée par un astérisque dans la liste des règles.

Pour configurer des règles de gestion de domaines, il vous suffit de fixer un seuil et de sélectionner certains paramètres SMTP. Le **seuil** est une limite calculée en pourcentage d&#39;erreur au-delà de laquelle tout message vers un domaine spécifique est bloqué.

Les **paramètres SMTP** agissent comme des filtres appliqués pour une règle de blocage.

* Vous pouvez choisir d&#39;activer ou non certaines normes d&#39;identification et clés de cryptage pour vérifier le nom de domaine, comme **Sender ID**, **DomainKeys**, **DKIM**, **S/MIME**.
* **Relais SMTP** : permet de configurer l&#39;adresse IP et le port d&#39;un serveur relais pour un domaine particulier.

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, la signature de l’authentification par courrier électronique DKIM (DomainKeys Identified Mail) est effectuée par la MTA améliorée. Dans le cadre de la mise à niveau améliorée de la MTA, la signature de la messagerie instantanée par la MTA de campagne native sera désactivée dans la table de gestion **[!UICONTROL des]**domaines.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

### Gestion des MX {#mx-management}

>[!IMPORTANT]
>
>Une fois la mise à niveau vers la MTA améliorée, les règles de débit de remise de gestion **MX d’Adobe Campaign** ne sont plus utilisées. La MTA améliorée utilise ses propres règles MX qui lui permettent de personnaliser votre débit par domaine en fonction de votre propre réputation de courriel historique et des commentaires en temps réel provenant des domaines où vous envoyez des courriers électroniques.
>
>Pour plus d’informations sur la MTA améliorée d’Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Chaque règle fixe un masque d&#39;adresse du MX. Tout MX dont le nom correspond à ce masque est éligible. Le masque peut contenir les caractères génériques &quot;*&quot; et &quot;?&quot;.

Par exemple, les adresses :

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

sont compatibles avec les masques :

* *.yahoo.com
* ?.mx.yahoo.com

Ces règles sont appliquées dans l&#39;ordre : la première règle dont le masque de MX est compatible avec le MX ciblé est appliquée.

Les paramètres disponibles pour chacune des règles sont les suivants :

* **[!UICONTROL Plage des identifiants]**: cette option permet d&#39;indiquer les plages d&#39;identifiants (publicId) pour lesquelles la règle s&#39;applique. Vous pouvez indiquer :

   * Un nombre : la règle ne s&#39;appliquera qu&#39;à ce publicId.
   * Une plage de nombres (nombre1-nombre2) la règle s&#39;appliquera à tous les publicId compris entre ces deux nombres.
   Lorsque ce champ est vide, la règle s&#39;applique à tous les identifiants.

* **[!UICONTROL Partagé]**: cette option indique que la limite du nombre de messages par heure et du nombre de connexions s&#39;applique à l&#39;ensemble des MX associés à cette règle.
* **[!UICONTROL Nombre maximum de connexions]**: nombre maximum de connexions simultanées à un MX depuis une adresse donnée.
* **Nombre maximum de messages** : nombre maximum de messages qui peuvent être envoyés sur une connexion. Au-delà, la connexion est fermée puis une nouvelle est rouverte.
* **[!UICONTROL Messages par heure]**: nombre maximum de messages qui peuvent être envoyés sur une période d&#39;une heure pour un MX depuis une adresse donnée.

>[!IMPORTANT]
>
>* Le serveur de diffusion (MTA) doit être relancé si les paramètres sont modifiés.
>* La modification ou la création de règles de gestion est réservée à des utilisateurs experts.
>



## Liste des propriétés des emails {#list-of-email-properties}

Cette section décrit la liste des paramètres disponibles dans l&#39;écran des propriétés d&#39;un email ou d&#39;un modèle d&#39;email.

>[!NOTE]
>
>Certains paramètres sont uniquement disponibles dans les modèles. Les paramètres accessibles [dépendent de vos permissions](../../administration/using/users-management.md).

Pour éditer les propriétés d&#39;un email ou d&#39;un modèle d&#39;email, utilisez le bouton **[!UICONTROL Editer les propriétés]**.

![](assets/delivery_options_1.png)

### Paramètres généraux {#general-parameters}

En haut de l&#39;écran des paramètres d&#39;email, identifiez l&#39;email à l&#39;aide des champs **[!UICONTROL Libellé]**et**[!UICONTROL  ID]**. Ces informations apparaissent dans l&#39;interface mais ne sont pas visibles par les destinataires des messages.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L&#39;identifiant doit être unique.

Le champ **[!UICONTROL Marque]**permet de sélectionner la marque liée à la diffusion. Pour plus d&#39;informations sur l&#39;utilisation des marques et leur paramétrage, voir la section[Marques](../../administration/using/branding.md).

Le champ **[!UICONTROL Campagne]**permet de renseigner la campagne associée à l&#39;email.

Vous pouvez également ajouter une **[!UICONTROL Description]**dans le champ correspondant et modifier l&#39;image affichée sur la vignette de l&#39;email, dans les listes.

### Paramètres d&#39;envoi {#sending-parameters}

La section **[!UICONTROL Envoi]**est uniquement disponible pour les modèles d&#39;email. Elle comprend les paramètres suivants :

#### Paramètres de reprises {#retries-parameters}

Les messages qui n&#39;ont pas abouti de manière temporaire font l&#39;objet de reprises automatiques. Cette section indique combien de reprises doivent être effectuées le jour du démarrage de l&#39;envoi (**[!UICONTROL Nombre max. de reprises]**) ainsi que le délai minimum entre deux reprises (**[!UICONTROL  Intervalle entre deux reprises]** ).

Par défaut, cinq reprises sont planifiées le premier jour de l&#39;envoi, avec un intervalle minimum d&#39;une heure, réparties sur les 24h de la journée. Après cela, une reprise est programmée chaque jour jusqu&#39;à la date limite de diffusion, qui est définie dans la section [Paramètres de période de validité](#validity-period-parameters).

Le nombre de reprises peut être changé de manière globale (contactez l&#39;administrateur technique Adobe) ou pour chaque diffusion ou modèle de diffusion.

#### Paramètres de format des emails {#email-format-parameters}

Vous pouvez paramétrer le format des emails envoyés. Trois options sont disponibles :

* **Tenir compte des préférences des destinataires** (mode par défaut) : le format du message est défini en fonction des informations enregistrées dans le profil du destinataire et stockées par défaut dans le champ **Format des emails** (@emailFormat). Si un destinataire souhaite recevoir les messages dans un format particulier, ce format lui est envoyé. Si ce champ n&#39;est pas renseigné, le message sera envoyé en multipart-alternative (voir ci-dessous).
* **Laisser le mailer des destinataires choisir le format le plus adapté (multipart-alternative)** : le message contient les deux formats : texte et HTML. Le format affiché lors de la réception dépend de la configuration du logiciel de messagerie du destinataire (multipart-alternative).

   >[!IMPORTANT]
   >
   >Cette option inclut les deux versions du message et, par conséquent, a un impact sur le débit de diffusion, car la taille du message est supérieure.

* **Envoyer tous les messages au format texte** : le message est envoyé au format texte. Le format HTML ne sera pas envoyé, mais uniquement utilisé pour la page miroir, lorsque le destinataire clique sur le lien dans le message.

#### Mode test SMTP {#smtp-test-mode}

L&#39;option **[!UICONTROL Activer le mode test SMTP]**permet de tester l&#39;envoi des emails via une connexion SMTP sans envoyer réellement de messages.
Les messages sont traités jusqu&#39;à la connexion au serveur SMTP, mais ne sont pas envoyés.

![](assets/smtp-test-mode.png)

Cette option est disponible pour les emails et les modèles d&#39;email.

Si vous activez l&#39;option de mode test SMTP pour un modèle d&#39;email, cette option sera activée pour tous les emails créés à partir de ce modèle.

>[!IMPORTANT]
>
>Lorsque cette option est activée pour un email, aucun message n&#39;est envoyé tant qu&#39;elle n&#39;est pas décochée.
>Un avertissement s&#39;affiche dans le tableau de bord de l&#39;email ou du modèle d&#39;email.

Pour plus d&#39;informations sur la configuration SMTP, reportez-vous à la section [Liste des paramètres SMTP des emails](#list-of-email-smtp-parameters).

### Paramètres de période de validité {#validity-period-parameters}

The **[!UICONTROL Validity period]**section contains the following parameters:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Fixer explicitement les dates de validité]** : lorsque cette case est décochée, vous devez renseigner une durée dans les champs**[!UICONTROL  Durée de diffusion]** et **[!UICONTROL Validité des ressources]**. Cochez cette case si vous souhaitez définir des dates et heures précises.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Durée de diffusion]** : Adobe Campaign diffuse les messages à partir de la date de démarrage de l&#39;envoi. Ce champ permet de définir la durée pendant laquelle les messages pourront être envoyés.

   >[!IMPORTANT]
   >
   >Une fois la mise à niveau vers la MTA améliorée, le paramètre **[!UICONTROL Durée] de remise ** dans vos livraisons de campagne n’est utilisé que si la valeur est définie sur 3,5 jours ou moins. Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte. Tous les impacts sont détaillés dans le document MTA [amélioré d’](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html) Adobe Campaign.

* **[!UICONTROL Validité des ressources]** : ce champ est utilisé pour les ressources mises en ligne, principalement pour la page miroir et les images. Les ressources de cette page ont une durée de validité limitée (afin d&#39;économiser de l&#39;espace disque).
* **[!UICONTROL Gestion de la page miroir]** : la page miroir est une page HTML accessible en ligne via un navigateur web et dont le contenu est identique à celui de l&#39;email. Par défaut, la page miroir est générée si le lien est inséré dans le contenu du mail. Ce champ permet de modifier le mode de génération de cette page :

   >[!IMPORTANT]
   >
   >Un contenu HTML doit avoir été défini pour l&#39;email pour que la page miroir soit créée.

   * **[!UICONTROL Générer la page miroir si le lien apparaît dans le contenu du message]**(mode par défaut) : la page miroir est générée si le lien est inséré dans le contenu du mail.
   * **Forcer la génération de la page miroir** : même si aucun lien vers la page miroir n&#39;est inséré dans les messages, la page miroir sera créée.
   * **Ne pas générer de page miroir** : aucune page miroir n&#39;est générée, même si le lien est présent dans les messages.
   * **Générer une page miroir accessible depuis l&#39;identifiant du message** : cette option permet d&#39;accéder au contenu de la page miroir, avec les informations de personnalisation, dans l&#39;écran des logs de diffusion.

>[!NOTE]
>
>Le paramètre de durée **[!UICONTROL de]**remise ne s’applique pas aux messages transactionnels. Pour plus d&#39;informations sur les messages transactionnels, voir[cette section](../../channels/using/about-transactional-messaging.md).

### Paramètres du tracking {#tracking-parameters}

La section **[!UICONTROL Tracking]**propose les paramètres suivants :

* **[!UICONTROL Activer le tracking]** : permet d&#39;activer/désactiver le tracking des URL des messages. Pour gérer le tracking pour chaque URL de message, utilisez l&#39;icône**[!UICONTROL  Liens]** dans la barre d&#39;actions Concepteur d&#39;email. Voir [A propos des URL trackées](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Limite de validité du tracking]** : permet de définir la durée d&#39;activation du tracking sur les URL.
* **[!UICONTROL URL de substitution des URL périmées]** : vous pouvez renseigner une URL vers une page web qui sera affichée après expiration du tracking.

### Paramètres avancés {#advanced-parameters}

La section **[!UICONTROL Paramètres avancés]**propose les paramètres suivants :

Les premiers champs vous permettent de saisir les informations nécessaires pour développer les en-têtes de courrier électronique. Vous pouvez gérer ici l&#39;adresse de réponse et le texte ainsi que l&#39;adresse de l&#39;expéditeur (qui remplit le champ &quot;De :&quot;). Ces informations peuvent être personnalisées.

Cliquez sur le bouton à droite du champ qui va être modifié, puis ajoutez le champ de personnalisation, le bloc de contenu ou le texte dynamique.

![](assets/advancedparameters.png)

L’insertion et l’utilisation du contenu de personnalisation sont détaillées dans la documentation sur le contenu [de l’e-mail de](../../designing/using/personalization.md) personnalisation.

#### Contexte de ciblage {#target-context}

Le contexte de ciblage permet de définir l&#39;ensemble les tables qui seront utilisées pour le ciblage (dans l&#39;écran de définition des audiences) et la personnalisation (définition de champs de personnalisation, dans l&#39;éditeur de contenu HTML) de l&#39;email.

#### Routage {#routing}

Ce champ indique le mode de routage utilisé. Il référence un compte externe. Par exemple, cela peut être utile si vous souhaitez utiliser un compte externe contenant des paramétrages de branding spécifiques.

>[!NOTE]
>
>Les comptes externes sont accessibles via le menu **Administration** > **Paramétrage de l&#39;application** > **Comptes externes**.

#### Préparation {#preparation}

La préparation des messages est présentée dans la section [Valider les messages](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typologie]** : avant tout envoi, vous devez préparer les messages afin d&#39;en valider le contenu et le paramétrage. Les règles de vérification appliquées lors de la phase de préparation sont définies dans une** typologie **. Par exemple, pour les emails, la préparation porte sur la validation de l&#39;objet, des URL et des images, etc. Sélectionnez, dans ce champ, la typologie à appliquer.

   >[!NOTE]
   >
   >Les typologies, accessibles via le menu **[!UICONTROL Administration]**>**[!UICONTROL  Canaux]** > **[!UICONTROL Typologies]**, sont présentées dans la section[Typologies](../../administration/using/about-typology-rules.md).

* **[!UICONTROL Calculer le libellé lors de la préparation de la diffusion]** : permet de calculer la valeur du libellé de l&#39;email pendant la phase de préparation du message à l&#39;aide des champs de personnalisation, des blocs de contenu et du texte dynamique.

   Il est également possible de personnaliser le libellé de la diffusion avec les variables d&#39;événements qui ont été déclarées dans l&#39;activité de signal externe du workflow. Voir à ce propos [cette section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Enregistrer les requêtes SQL dans le journal]** : cette option permet d&#39;ajouter les logs des requêtes SQL dans le journal lors de la phase de préparation.

### Liste des paramètres SMTP des emails {#list-of-email-smtp-parameters}

La section **[!UICONTROL SMTP]**propose les paramètres suivants :

* **[!UICONTROL Encodage des caractères]** : cochez la case**[!UICONTROL  Forcer l&#39;encodage]** si vous souhaitez forcer l&#39;encodage des messages, puis sélectionnez le codage à utiliser.
* **[!UICONTROL Mails rebonds]** : par défaut, les mails rebonds sont récupérés dans la boîte d&#39;erreur de la plateforme (définie dans l&#39;écran**[!UICONTROL  Administration]** > **[!UICONTROL Canaux]**>**[!UICONTROL  Email]** > **[!UICONTROL Configuration).]**Si vous souhaitez définir une adresse d&#39;erreur spécifique pour un email, saisissez l&#39;adresse dans le champ**[!UICONTROL  Adresse des erreurs]**.
* **[!UICONTROL En-têtes SMTP supplémentaires]** : cette option permet d&#39;ajouter des en-têtes SMTP supplémentaires à vos messages. Le script saisi dans le champ**[!UICONTROL  En-têtes]** doit comporter un en-tête par ligne, sous la forme **nom:valeur**. Les valeurs sont automatiquement encodées, si nécessaire.

   >[!IMPORTANT]
   >
   >L&#39;ajout d&#39;un script pour l&#39;insertion d&#39;en-têtes SMTP supplémentaires est réservé aux utilisateurs expérimentés. La syntaxe de ce script doit être strictement conforme aux exigences de ce type de contenu : aucun espace superflu, aucune ligne vide, etc.

### Liste des paramètres d&#39;autorisation d&#39;accès {#list-of-access-authorization-parameters}

La section **[!UICONTROL Autorisation d&#39;accès]**propose les paramètres suivants :

* Le champ **[!UICONTROL Entité organisationnelle]**permet de restreindre l&#39;accès de cet email à certains utilisateurs. Les utilisateurs associés à l&#39;entité spécifiée ou aux entités parentes auront accès, en lecture et écriture, à cet email. Les utilisateurs associés aux entités filles auront accès, en lecture seule, à cet email.

   >[!NOTE]
   >
   >Le paramétrage des entités organisationnelles est accessible via le menu **Administration** > **Utilisateurs &amp; sécurité**.

* Les champs **[!UICONTROL Créé par]**,**[!UICONTROL  Créé le]**, **[!UICONTROL Modifié par]**et**[!UICONTROL  Modifié le]** sont automatiquement remplis.

## Archiver des emails {#archiving-emails}

Vous pouvez paramétrer Adobe Campaign pour conserver une copie des emails envoyés depuis votre plateforme.

Toutefois, Adobe Campaign ne gère pas lui-même les fichiers archivés : il vous permet d&#39;envoyer les messages de votre choix à une adresse dédiée, depuis laquelle ils peuvent être traités et archivés dans un système externe.

Lorsqu&#39;elle est activée dans le modèle de diffusion, cette fonctionnalité vous permet d&#39;envoyer une copie exacte des messages envoyés correspondants à une adresse email en bcc (invisible pour les destinataires de diffusion) que vous devez spécifier.

### Recommandations et limitations {#recommendations-and-limitations}

* Cette fonctionnalité est en option. Vérifiez votre contrat de licence et contactez votre chargé de compte pour l&#39;activer.
* Vous ne pouvez utiliser qu&#39;une seule adresse email en Cci.
* Seuls les emails envoyés sont pris en compte, les rebonds ne le sont pas.
* Pour des raisons de confidentialité, les emails en Cci doivent être traités dans un système d&#39;archivage capable de stocker en toute sécurité les informations d&#39;identification personnelles (PII).
* Lors de la création d&#39;un modèle de diffusion, l&#39;option Email BCC n&#39;est pas activée par défaut, même si elle a été achetée. Vous devez l&#39;activer manuellement dans chaque modèle de diffusion où vous souhaitez l&#39;utiliser.

### Activer l&#39;archivage des emails {#activating-email-archiving}

La fonctionnalité Email BCC est activée dans le [modèle d&#39;email](../../start/using/marketing-activity-templates.md) par le biais d&#39;une option dédiée :

1. Accédez à **Ressources** > **Modèles** > **Modèles de diffusion**.
1. Dupliquez le modèle d&#39;usine **[!UICONTROL Diffuser par email]**.
1. Sélectionnez le modèle dupliqué.
1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]**pour éditer les propriétés du modèle.
1. Développez la section **[!UICONTROL Envoi]**.
1. Cochez la case **[!UICONTROL Archiver les emails]**pour conserver une copie de tous les messages envoyés pour chaque diffusion selon ce modèle.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Si les emails envoyés à l&#39;adresse en bcc sont ouverts et font l&#39;objet de clics, cela sera pris en compte dans les **[!UICONTROL Ouvertures totales]**et les**[!UICONTROL  Clics]** provenant de l&#39;analyse d&#39;envoi, ce qui pourrait entraîner des erreurs de calcul.
