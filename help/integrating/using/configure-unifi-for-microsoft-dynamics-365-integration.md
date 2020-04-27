---
title: Configuration de l’intégration Unifi pour Microsoft Dynamics 365
description: Découvrez comment configurer l'intégration Unifi pour Microsoft Dynamics 365
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
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Configuration de l’intégration Unifi pour Microsoft Dynamics 365

Configurez Unifi pour configurer et activer Microsoft Dynamics 365 -  l&#39;intégration Adobe Campaign.

## Prérequis

Avant d’exécuter les étapes post-mise en service de cet article, on suppose que vous avez déjà terminé les étapes [post-mise en service pour Campaign](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) et [pour Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).  Si cela ne s’est pas produit, vous devrez suivre ces étapes pour terminer Campaign Standard et la post-mise en service de Dynamics 365.

Nous supposons également que vous avez contacté Unifi, que vous avez créé un compte Unifi et que vous avez réussi à vous connecter.  Si ce n&#39;est pas le cas, suivez les étapes décrites dans [cet article](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>Il est vivement recommandé de travailler avec le service de conseil Unifi et/ou Adobe (contactez votre service de conseil Adobe CSM) lors de la configuration d’Unifi.

## Configuration de l’intégration Campaign

Lors de votre première connexion, cliquez **[!UICONTROL Adobe Campaign Standard]** pour entrer vos informations d’identification Campaign.

La plupart de ces informations d’identification proviennent de l’intégration que vous avez créée dans la console d’E/S d’Adobe lors des étapes [de configuration](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)Campaign Standard.

>[!NOTE]
>
>Pour garantir la sécurité et la confidentialité, les champs d’informations d’identification sensibles apparaissent vides lors de la révision de ces écrans de configuration.

1. Pour l’URL d’authentification Adobe, saisissez `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Entrez votre **[!UICONTROL Adobe IO Organization ID]** et votre **[!UICONTROL Adobe IO Integration ID]**.

Pour obtenir vos ID d’organisation et d’intégration d’E/S Adobe, accédez à l’écran Intégration de la console d’E/S Adobe et notez l’URL Web.

Voici à quoi ça ressemble : `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, où ID d’organisation et ID d’entrée sont des nombres.

1. Entrez votre **[!UICONTROL Tenant ID]**

Pour obtenir votre ID de client, procédez comme suit :

1. Accédez à la console [d’administration](https://adminconsole.adobe.com/) Adobe et sélectionnez votre organisation IMS dans le menu déroulant supérieur droit.
1. Sélectionnez votre produit  Adobe Campaign Standard, puis sélectionnez votre instance Campaign Standard (si vous en avez plusieurs).  Cela permettra d&#39;obtenir un  de  de de produits.

   Les descriptions des  de produits s’affichent généralement dans l’un des formats suivants, où `<tenantID>` correspond à l’ID de client de votre instance.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Si vous rencontrez des problèmes pour identifier votre ID de client, contactez-vous > contact technique Adobe ou le service à la clientèle Adobe.
>
>Les ID de client d’instance de sandbox partenaire suivent généralement le modèle `https://<tenantId>`, où `tenantId` se trouve `tbd.campaign-sandbox.adobe.com`.

1. Entrez votre **[!UICONTROL Campaign Instance ID]**.

Pour obtenir votre ID d’instance, procédez comme suit :

    1. Saisissez &quot;https://&lt;acs-instance-url>/r/test&quot; dans un navigateur Web, en remplaçant `&lt;acs-instance-url>&quot; par l’URL de votre instance Campaign Standard.
    1. La réponse contient &quot;instance=&quot;, suivi de l’ID d’instance.

1. Sélectionnez la région de votre instance Campaign.

1. Vous pouvez laisser **[!UICONTROL Base Directory]** vide.

1. Select the **[!UICONTROL Allow as Output Destination]** option.

Une fois les paramètres définis, cliquez **[!UICONTROL CONNECT]** et vérifiez la connexion.

Dans le cas contraire, cliquez sur **[!UICONTROL CLOSE]** et vérifiez les paramètres.

>[!NOTE]
>
>Si vous ne parvenez pas à terminer cette étape, contactez le service [clientèle](mailto:support@unifisoftware.atlassian.net)Unifi.

## Configuration de l’intégration de Dynamics 365

Cliquez sur Microsoft Dynamics CRM pour configurer les informations d’identification de Dynamics 365. La plupart de ces informations d’identification proviennent de l’intégration que vous avez créée dans Microsoft Dynamics 365 lors des étapes de configuration de Microsoft Dynamics 365.

>[!NOTE]
>
>Pour garantir la sécurité et la confidentialité, les champs d’informations d’identification sensibles apparaissent vides lors de la révision de ces écrans de configuration.

1. Par **[!UICONTROL URL]** exemple, saisissez l’URL de votre instance Dynamics 365, en veillant à insérer &quot;.api&quot; avant &quot;.crm&quot; (par ex., `https://mydynamicsinstance.api.crm.dynamics.com`).

1. Vous utiliserez **[!UICONTROL clientid]** par exemple le généré lors de la création de l’enregistrement de l’application en tant que [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Par exemple, **[!UICONTROL clientsecret]** vous utiliserez le secret client généré lorsque vous ajoutez un secret client à l’enregistrement de l’application en tant que [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Pour **[!UICONTROL callbackurl]**, ajoutez `http://localhost:33333`.

1. Par exemple, **[!UICONTROL refresh token]** laissez vide.

1. Pour l’ID de **[!UICONTROLclient]**, utilisez l’ID de client que vous avez obtenu de portal.azure.com comme [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Enfin, cochez la case **[!UICONTROL Allow as Output Destination]**.

Une fois les paramètres entrés, cliquez **[!UICONTROL CONNECT]** et vérifiez la connexion.

Dans le cas contraire, cliquez sur **[!UICONTROL CLOSE]** et vérifiez les paramètres.

>[!NOTE]
>
>Si vous ne parvenez pas à terminer cette étape, contactez le service [clientèle](mailto:support@unifisoftware.atlassian.net)Unifi.

## Fin de la configuration Unifi

Une fois vos informations d’identification configurées, vous devez en avertir Unifi car d’autres étapes doivent être effectuées avant de pouvoir terminer la configuration de l’intégration.  Contactez les coordonnées Unifi fournies pour indiquer que vous avez configuré vos informations d’identification.

Vous devez sélectionner une option d’exclusion et en informer Unifi une fois l’opération terminée (en indiquant à Unifi quelle option d’exclusion est sélectionnée).  Vous trouverez une explication des options d’exclusion dans le Guide [de l’utilisateur](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)Unifi.

Une fois que le module Unifi a terminé son travail, il vous en informera et vous fournira des informations supplémentaires pour vous aider à configurer votre instance Unifi, à exécuter l&#39;entrée de données une fois puis, une fois le travail terminé, vous pourrez activer les planifications.

La fréquence suivante est recommandée pour divers cas d’utilisation :

* Insent : Toutes les 15 minutes
* Entrée : Toutes les 15 minutes
* Supprime : Chaque jour
* Exclusions : Chaque jour

>[!NOTE]
>
>Par défaut, les  marketing SEND sont filtrées hors de la tâche d’insertion.  Si vous souhaitez voir ENVOYER des  marketing dans Dynamics 365, vous devez modifier le filtre (étape 5) de la tâche d&#39;insertion dans Unifi.

Il existe deux rôles distincts dans Unifi, un utilisateur propriétaire et un utilisateur analyste en lecture seule. Un utilisateur propriétaire peut modifier des tâches et des planifications, contrairement à l’analyste en lecture seule.  Il ne peut y avoir qu’un seul utilisateur propriétaire pour une instance de client donnée.  Si le client doit modifier la personne affectée en tant qu’utilisateur propriétaire, il peut envoyer un courrier électronique à [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) avec la modification demandée.

La configuration Unifi, les détails de la tâche, la configuration et la surveillance sont présentés dans les vidéos ci-dessous.

## Tâches Unifi

### Présentation des tâches Unifi

>[!VIDEO](https://video.tv.adobe.com/v/27392)

Cette vidéo explique les différentes tâches Unifi requises pour l&#39;intégration  Adobe Campaign Standard avec Microsoft Dynamics 365 (02:10 min)

### Détails de la tâche Unifi : Entrée et entrée

>[!VIDEO](https://video.tv.adobe.com/v/27396)

Cette vidéo explique les tâches d&#39;entrée et de sortie en Unifi (04:27 min)

### Opérationalisation et surveillance

>[!VIDEO](https://video.tv.adobe.com/v/27391)

Cette vidéo explique le  et les calendriers (03:03 min)

Plus comme suit
* [Utilisation de  Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuration de Microsoft Dynamics 365 pour Campaign intégration](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Configuration des E/S Adobe pour Microsoft Dynamics 365 - Intégration Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Page des fonctionnalités d&#39;intégration de Microsoft Dynamics 365](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)