---
title: Comptes externes
description: Paramétrez des comptes externes pour configurer des connexions à des systèmes externes tels que des serveurs SFTP.
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: ht
source-git-commit: 9c04148a6c0eafdd909c461fc3e927ec8c8fbfed

---


# Comptes externes{#external-accounts}

Un compte externe est un paramétrage qui permet de configurer et de tester l&#39;accès à un serveur externe à Adobe Campaign.

Ces comptes externes peuvent être utilisés dans les workflows de Campaign pour accéder aux données et les gérer.

Vous pouvez configurer les types de comptes externes suivants :

* SFTP. Voir à ce propos [cette section](#sftp-external-account).
* Amazon Storage Service (S3). Voir à ce propos [cette section](#amazon-s3-external-account).
* Adobe Experience Manager. Voir à ce propos [cette section](#adobe-experience-manager-external-account).
* Adobe Analytics. Voir à ce propos [cette section](../../integrating/using/configure-campaign-analytics-integration.md).
* reCAPTCHA Google. Voir à ce propos [cette section](#google-recaptcha-external-account).

>[!NOTE]
>
>Adobe utilise d&#39;autres types de comptes externes pendant la configuration du produit. Depuis la version Campaign Standard 17.9, les comptes externes FTP peuvent toujours être définis, mais ne sont plus utilisables dans les nouvelles activités de workflow. Si une connexion est déjà configurée, elle reste activée.

Les comptes externes peuvent être configurés par les administrateurs depuis le menu **[!UICONTROL Administration > Paramétrage de l&#39;application > Comptes externes]**.

## Création d&#39;un compte externe {#creating-an-external-account}

Adobe Campaign est livré avec un ensemble de comptes externes prédéfinis. Pour configurer des connexions avec des systèmes externes comme des serveurs FTP utilisés pour les transferts de fichiers, vous pouvez créer vos propres comptes externes.

Les comptes externes sont utilisés par des processus techniques, tels que des workflows techniques ou des workflows des opérations. Lors de la configuration d&#39;un transfert de fichier dans un workflow ou d&#39;un échange de données avec une autre application (Adobe Target, Experience Manager, etc.), vous devez sélectionner un compte externe.

1. Cliquez sur le bouton **[!UICONTROL Créer]**.
1. Saisissez un libellé. Le libellé et l&#39;identifiant seront utilisés lors de la sélection des comptes externes dans les workflows.
1. Sélectionnez le type de compte que vous souhaitez créer.
1. Configurez l&#39;accès au compte en indiquant les identifiants, l&#39;adresse du serveur, le numéro de port et les clés, le cas échéant.

   Les informations nécessaires sont généralement fournies par le fournisseur du serveur auquel vous vous connectez.

1. Enregistrez votre compte.

Le compte externe est créé et ajouté à la liste des comptes. Il peut être désormais utilisé pour vos transferts de fichiers/données ou vos configurations de routage dans les activités de workflow et les propriétés de diffusion.

## Compte externe SFTP   {#sftp-external-account}

Des informations différentes doivent être spécifiées en fonction des types de compte externe.

Pour un compte externe SFTP, indiquez les informations suivantes :

* Adresse du serveur. Par exemple, **ftp.domaine.com**.
* Numéro de port. Par exemple, **22**.
* Identifiants du serveur SFTP : nom de compte et mot de passe utilisés pour se connecter au serveur.

### Recommandations relatives au serveur SFTP hébergé par Adobe   {#adobe-hosted-sftp-server-recommendations}

Lors de la gestion de fichiers et de données à des fins d&#39;ETL, les fichiers sont stockés sur un serveur SFTP hébergé fourni par Adobe. Ce serveur SFTP est conçu pour être un espace de stockage temporaire pour lequel vous pouvez contrôler la conservation et la suppression des fichiers.

Lorsqu&#39;il n&#39;est pas correctement utilisé ou suivi, cet espace peut rapidement remplir l&#39;espace physique disponible sur le serveur et entraîner de graves problèmes, tels que la perte ou l&#39;endommagement de données sur votre plateforme.

Pour éviter ces problèmes, Adobe recommande de suivre les bonnes pratiques suivantes :

* Conservez le minimum de données possible.
* Utilisez l&#39;authentification par clé pour éviter l&#39;expiration du mot de passe. Seuls les formats **OpenSSH** et **SSH2** sont pris en charge. Vous devrez fournir la clé publique à l&#39;équipe de support Adobe pour qu&#39;elle soit téléchargée sur le serveur Campaign.
* Conservez les données que le temps nécessaire. 15 jours est la durée maximale.
* Utilisez des workflows pour supprimer correctement les données (gérez la conservation depuis les workflows utilisant les données).
* Utilisez des batchs dans les téléchargements SFTP ainsi que dans les workflows.
* Gérez les erreurs/exceptions.
* Connectez-vous de temps à autre au SFTP afin de vérifier directement ce qui s&#39;y trouve.
* Gardez à l&#39;esprit que la gestion des disques SFTP relève principalement de votre responsabilité.

Notez également que les adresses IP publiques à partir desquelles vous tentez d&#39;initier la connexion SFTP doivent être whitelistées sur l&#39;instance Campaign. Le whitelistage des adresses IP et la clé publique à utiliser pour l&#39;authentification peuvent être demandés par le biais d&#39;un [ticket d&#39;assistance](https://support.neolane.net).

Les serveurs SFTP peuvent être gérés à partir du Panneau de contrôle. Pour plus d&#39;informations, consultez la [documentation du Panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/sftp-management/about-sftp-management.html).

>[!NOTE]
>
>Le Panneau de contrôle est disponible uniquement pour les utilisateurs administrateurs des clients hébergés sur AWS.
Vérifiez [ici](https://docs.adobe.com/content/help/fr-FR/control-panel/using/faq.html#ims-org-id) si votre instance est hébergée sur AWS.

## Compte externe Amazon S3 {#amazon-s3-external-account}

Le champ du serveur Amazon S3 doit être renseigné de la manière suivante :

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Pour stocker votre fichier en mode crypté dans S3, cochez la case **[!UICONTROL Conserver les fichiers cryptés dans S3]**.

![](assets/external_accounts_2.png)

Les informations nécessaires sont généralement fournies par le fournisseur du serveur auquel vous vous connectez.

Indiquez la **[!UICONTROL région AWS]**associée à votre point d&#39;entrée. Pour vérifier les régions et les versions de signatures prises en charge, consultez la[documentation officielle d&#39;Amazon S3](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region).

>[!NOTE]
>
>Le **[!UICONTROL serveur récepteur]**doit être saisi sans votre région AWS. Il sera ajouté ultérieurement et de manière automatique à votre URL.

### Recommandations relatives au compte Amazon S3 {#amazon-s3-account-recommendations}

Pour configurer un compte Amazon S3, nous vous conseillons de suivre les recommandations suivantes :

* Créez une stratégie de compartiment stricte afin de limiter l&#39;accès aux compartiments S3. Vous pouvez configurer la stratégie de compartiment pendant la création d&#39;un compartiment. Pour plus d&#39;informations, consultez la [documentation d&#39;Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* Lors de la création d&#39;un compte externe, activez le cryptage pour stocker les données sensibles dans le compartiment S3 en cochant la case **[!UICONTROL Conserver les fichiers cryptés dans S3]**.
* Octroyez des autorisations de compartiment pour indiquer qui peut accéder à l&#39;objet dans un compartiment. Pour plus d&#39;informations sur les autorisations de compartiment, consultez la [documentation d&#39;Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)..

## Compte externe Adobe Experience Manager {#adobe-experience-manager-external-account}

Les comptes externes Adobe Experience Manager sont utilisés lors de l&#39;intégration de Campaign avec Experience Manager.

La procédure et les exigences relatives à cette intégration sont présentées dans [ce document](../../integrating/using/about-campaign-integrations.md).

Lors de la configuration de ce nouveau compte externe, vous devez indiquer les informations suivantes :

* Serveur : saisissez l&#39;URL du serveur Adobe Experience Manager. Par exemple, **http://aem.domaine.com:4502**.
* Identifiants du compte AEM : utilisez le compte qui accédera à l&#39;instance d&#39;Adobe Experience Manager. Il doit s&#39;agir d&#39;un compte appartenant au groupe distant de campagnes dans Experience Manager.

## Compte externe Google reCAPTCHA   {#google-recaptcha-external-account}

>[!NOTE]
>
>La configuration Google reCAPTCHA nécessite un compte Google.

Le mécanisme Google reCAPTCHA vous permet de protéger votre landing page du spam et des abus causés par les bots. Il ne présente pas d&#39;intrusion par rapport à vos clients, car il ne nécessite aucune interaction de leur part et repose sur les interactions avec votre site. Pour inscrire votre site, consultez cette [page](https://www.google.com/recaptcha/admin/create). Vous devez choisir le type reCAPTCHA version 3.

Pour ajouter le Google reCAPTCHA version 3 à votre landing page, vous devez tout d&#39;abord le configurer dans votre compte externe. Pour plus d&#39;informations sur la façon de l&#39;ajouter à votre landing page, consultez [cette section](../../channels/using/configuring-landing-page.md#setting-google-recaptcha).

Pour un compte externe Google reCAPTCHA version 3, fournissez les détails suivants :

* Un **[!UICONTROL Libellé]**et l&#39;**[!UICONTROL  ID]** de votre compte externe
* **[!UICONTROL Type]** : Google reCAPTCHA
* Votre **[!UICONTROL Clé du site]**et**[!UICONTROL  Secret du site]**
* Un **[!UICONTROL Seuil]**compris entre 0 et 1

   Une valeur de **[!UICONTROL Seuil]**de 0.0 signifie qu&#39;il s&#39;agit vraisemblablement d&#39;un bot, tandis qu&#39;une valeur de 1.0 représente une bonne interaction. Par défaut, vous pouvez utiliser un seuil de 0.5.

![](assets/external_accounts_3.png)
