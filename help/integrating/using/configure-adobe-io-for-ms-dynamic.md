---
title: Configuration de l’intégration d’Adobe IO pour Microsoft Dynamics 365
description: Découvrez comment configurer l'intégration d'Adobe IO pour Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Configuration de l’intégration d’Adobe IO pour Microsoft Dynamics 365

Activez vos données de gestion de la relation client lors d’une communication entre  : découvrez les étapes requises lors de la post-mise en service pour créer une nouvelle intégration pour Microsoft Dynamics 365.

## Présentation

 Adobe Campaign Standard - L&#39;intégration de Microsoft Dynamics 365 est décrite dans [cette page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Avant d’exécuter les étapes de post-mise en service décrites dans cet article, on suppose que vous avez déjà reçu des privilèges d’accès et que vous disposez d’un accès administrateur à l’instance Campaign Standard de votre organisation.  Si cela ne s’est pas produit, vous devrez contacter le service à la clientèle d’Adobe pour terminer l’attribution des Campaign.

>[!CAUTION]
>
>Les étapes décrites ci-dessous doivent être exécutées par un administrateur.

## Configuration 

Vous devez configurer l’accès aux API et configurer une nouvelle intégration pour Unifi.

La configuration s’effectue dans les E/S Adobe : vous devez créer une nouvelle intégration pour Unifi, comme le montre cette vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/27308)

### Création d’une intégration

Pour ce faire, procédez comme suit :

1. Accédez à [Adobe IO Console](https://console.adobe.io/home#) et sélectionnez votre ID d’organisation Adobe IMS dans le menu déroulant en haut à gauche (voir ci-dessous).

Cliquez ensuite **[!UICONTROL New Integration]** en haut à droite.

>[!NOTE]
>
>S’il s’agit de la première intégration de votre entreprise, le bouton de **[!UICONTROL New Integration]** peut se trouver au centre de la page.

1. Sélectionnez **[!UICONTROL Access an API]** puis cliquez sur **[!UICONTROL Continue]**.

1. Sélectionnez _Adobe Campaign_ dans la **[!UICONTROL Experience Cloud]** section et cliquez sur **[!UICONTROL Continue]**.

1. Générez un certificat et une clé.

**Pour les plates-formes MacOs et Linux**

Ouvrez une application Terminal Server et exécutez la commande suivante :

```
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Pour les plateformes Windows**

* Téléchargez un client openssl pour générer des certificats publics (client [Openssl Windows](https://bintray.com/vszakats/generic/download_file?file_path=openssl-1.1.1-win64-mingw.zip)par exemple).

* Extraire le dossier du fichier zip

* Ouvrez l’invite de ligne de commande et exécutez les commandes ci-dessous.

Remplacez `<containing folder path>` ci-dessous par le chemin du dossier extrait (par exemple, C:\Users\labuser\Downloads\openssl-1.1.1-win64-mingw\openssl-1.1.1-win64-mingw) :

```
set OPENSSL_CONF=<containing folder path>/openssl.cnf
 
cd <containing folder path>/
 
openssl req -x509 -sha256 -nodes -days 365 -newkey rsa:2048 -keyout private.key -out certificate_pub.crt
```

**Pour toutes les plateformes**

Suivez les invites pour terminer la demande de certificat :

```
Generating a 2048 bit RSA private key
 
.................+++
 
.......................................+++
 
writing new private key to 'private.key'
 
-----
 
You are about to be asked to enter information that will be incorporated
 
into your certificate request.
 
What you are about to enter is what is called a Distinguished Name or a DN.
 
There are quite a few fields but you can leave some blank
 
For some fields there will be a default value,
 
If you enter '.', the field will be left blank.
 
-----
```

Une fois les informations saisies, deux fichiers sont générés : **[!UICONTROL certificate_pub.crt]** et **[!UICONTROL private.key]**.

* **[!UICONTROL certificate_pub.crt]** expirera dans 365 jours. Vous pouvez modifier la période d’expiration en modifiant la valeur des jours dans la commande openssl ci-dessus, mais la rotation périodique des informations d’identification est une bonne pratique de sécurité.

* **[!UICONTROL certificate_pub.crt]** sera utilisé dans l’écran suivant pour terminer l’intégration dans la console d’E/S d’Adobe.

>[!NOTE]
>
> **[!UICONTROL private.key]** sera utilisée ultérieurement lors des étapes post-mise en service pour Unifi.

1. Revenez à la console d’E/S Adobe, puis saisissez un nom et une description pour l’intégration.

1. Télécharger **[!UICONTROL certificate_pub.crt]**

1. Sélectionnez le de produits dont le titre est  :

* ID d’organisation de votre instance Campaign
* **[!UICONTROL Administrators]**

Exemple :  Campaign Standard - your-campaign-organisationID - Administrateurs

Cliquez sur **[!UICONTROL Create Integration]**.

![](assets/MSdynACSIntegration-4B.png)

### Configuration des détails de l’intégration

1. Sélectionner **[!UICONTROL Continue to Integration Details]**

Consultez les détails de l’intégration.  Vous devez y faire référence lorsque vous exécutez les étapes de post-mise en service Unifi.

![](assets/MSdynACSIntegration-5.png)

1. Cliquez sur l’ **[!UICONTROL Services]** onglet et ajoutez **[!UICONTROL I/O Events]** **[!UICONTROL I/O Management API]** des services.  Pour ajouter le service, cliquez sur le bouton radio, puis **[!UICONTROL Add service]**.  Vous le ferez séparément pour chaque service.

Lorsque vous avez terminé, vos services devraient apparaître en haut comme l&#39;image ci-dessous. Vous n’aurez pas besoin de compléter la section A-on pour générer un  JWT et un.

![](assets/MSdynACSIntegration-6.png)

La mise en service des publications dans Campaign est maintenant terminée.  Passez à la procédure de configuration [post-publication pour Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Rubriques connexes**

* [Adobe IO - Intégration de comptes de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuration de l’accès à l’API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard - Intégration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
