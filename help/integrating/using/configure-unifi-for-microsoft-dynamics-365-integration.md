---
title: Configuration d’Unifi pour l'intégration Microsoft Dynamics 365
description: Découvrez comment configurer Unifi pour l’intégration Microsoft Dynamics 365
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
translation-type: ht
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Configuration d’Unifi pour l&#39;intégration Microsoft Dynamics 365

Configurez Unifi pour configurer et activer l&#39;intégration Microsoft Dynamics 365 - Adobe Campaign.

## Prérequis

Avant d’exécuter les étapes post-approvisionnement de cet article, on suppose que vous avez déjà terminé les [étapes de post-approvisionnement pour Campaign](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) et [pour Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).  Si ce n’est pas le cas, vous devrez suivre ces étapes pour terminer le post-approvisionnement de Campaign Standard et de Dynamics 365.

Il s’entend également que vous avez contacté Unifi, que l’on a créé un compte Unifi pour vous et que vous avez réussi à vous connecter.  Si ce n&#39;est pas le cas, suivez les étapes décrites dans [cet article](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>Il est vivement recommandé de travailler avec le service de conseil Unifi et/ou Adobe (contactez votre CSM Adobe) lors de la configuration d’Unifi.

## Configuration de l’intégration Campaign

Lors de votre première connexion, cliquez sur **[!UICONTROL Adobe Campaign Standard]** pour entrer vos informations d’identification Campaign.

La plupart de ces informations d’identification proviennent de l’intégration que vous avez créée dans la console d’I/O d’Adobe lors des [étapes de configuration Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

>[!NOTE]
>
>Pour garantir la sécurité et la confidentialité, des champs d’informations d’identification sensibles apparaissent vides lors de la révision de ces écrans de configuration.

1. Pour l’URL d’authentification Adobe, saisissez `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Entrez votre **[!UICONTROL ID d’organisation Adobe IO]** et votre **[!UICONTROL ID d’intégration Adobe IO]**.

Pour obtenir vos ID d’organisation et d’intégration Adobe IO, accédez à l’écran Intégration de la console d’Adobe IO et notez l’URL Web.

Cela devrait ressembler à ceci : `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, où l’ID d’organisation et l’ID interne sont des nombres.

1. Entrez votre **[!UICONTROL identifiant de tenant]**

Pour obtenir votre ID de tenant, procédez comme suit :

1. Accédez à [Adobe Admin Console](https://adminconsole.adobe.com/) et sélectionnez votre organisation IMS dans le menu déroulant supérieur droit.
1. Sélectionnez votre produit Adobe Campaign Standard, puis sélectionnez votre instance Campaign Standard (si vous en avez plusieurs).  Cela permettra d&#39;obtenir une liste des profils de produits.

   Les descriptions de profils de produits s’affichent généralement dans l’un des formats suivants, où `<tenantID>` correspond à l’ID de tenant de votre instance.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Si vous rencontrez des problèmes pour identifier votre ID de tenant, contactez votre contact technique Adobe ou l’assistance clientèle d’Adobe.
>
>Les ID de tenant d’instance sandbox partenaire suivent généralement le modèle `https://<tenantId>`, où `tenantId` est `tbd.campaign-sandbox.adobe.com`.

1. Entrez votre **[!UICONTROL ID d’instance Campaign]**.

Pour obtenir votre ID d’instance, procédez comme suit :

    1. Saisissez « https://&lt;acs-instance-url>/r/test » dans un navigateur Web, en remplaçant « &lt;acs-instance-url> » par l’URL de votre instance Campaign Standard.
    1. La réponse contient « instance= », suivi de l’ID d’instance.

1. Sélectionnez la région de votre instance Campaign.

1. Vous pouvez laisser le **[!UICONTROL répertoire de base]** vide.

1. Sélectionnez l’option **[!UICONTROL Autoriser comme destination de sortie]**.

Une fois les paramètres définis, cliquez sur **[!UICONTROL CONNECT]** et vérifiez la connexion.

Dans le cas contraire, cliquez sur **[!UICONTROL CLOSE]** et vérifiez les paramètres.

>[!NOTE]
>
>Si vous ne parvenez pas à terminer cette étape, contactez le [service client d’Unifi](mailto:support@unifisoftware.atlassian.net).

## Configuration de l’intégration Dynamics 365

Cliquez sur Microsoft Dynamics CRM pour configurer les informations d’identification de Dynamics 365. La plupart de ces informations d’identification proviennent de l’intégration que vous avez créée dans Microsoft Dynamics 365 lors des étapes de configuration de Microsoft Dynamics 365.

>[!NOTE]
>
>Pour garantir la sécurité et la confidentialité, des champs d’informations d’identification sensibles apparaissent vides lors de la révision de ces écrans de configuration.

1. Pour **[!UICONTROL URL]**, saisissez l’URL de votre instance Dynamics 365, en veillant à insérer « .api » avant « .crm » (par exemple `https://mydynamicsinstance.api.crm.dynamics.com`).

1. Pour **[!UICONTROL clientId]**, utulisez l’ID de l’application générée lors de la création de l&#39;enregistrement de l&#39;application en tant que [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Pour **[!UICONTROL clientsecret]**, utilisez le secret client généré lorsque vous avez ajouté un secret client à l’enregistrement de l’application en tant que [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Pour **[!UICONTROL callbackurl]**, ajoutez `http://localhost:33333`.

1. Pour **[!UICONTROL jeton d’actualisation]**, laissez vide.

1. Pour **[!UICONTROLID de tenant]**, utilisez l’ID de tenant que vous avez obtenu de portal.azure.com comme [configuration de Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Enfin, cochez la case **[!UICONTROL Autoriser comme destination de sortie]**.

Une fois les paramètres saisis, cliquez sur **[!UICONTROL CONNECT]** et vérifiez la connexion. 

Dans le cas contraire, cliquez sur **[!UICONTROL FERMER]** et vérifiez les paramètres.

>[!NOTE]
>
>Si vous ne parvenez pas à terminer cette étape, contactez le service [clientèle](mailto:support@unifisoftware.atlassian.net)Unifi.

## Finalisation de la configuration Unifi

Une fois vos informations d’identification configurées, vous devez en avertir Unifi car d’autres étapes doivent être effectuées avant de pouvoir terminer la configuration de l’intégration.  Contactez-les aux coordonnées Unifi fournies pour indiquer que vous avez configuré vos informations d’identification.

Vous devez sélectionner une option de désinscription et en informer Unifi une fois l’opération terminée (en indiquant à Unifi quelle option de désinscription est sélectionnée).  Vous trouverez une explication des options de désinscription dans le [Guide de l’utilisateur Unifi](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn).

Une fois que le module Unifi a terminé son travail, il vous en informera et vous fournira des informations supplémentaires pour vous aider à configurer votre instance Unifi, à exécuter l&#39;entrée de données une fois puis, une fois le travail terminé, vous pourrez activer les plannings.

La fréquence suivante est recommandée pour divers cas d’utilisation :

* Entrée : Toutes les 15 minutes
* Sortie : Toutes les 15 minutes
* Suppression : Tous les jours
* Désinscriptions : Tous les jours

>[!NOTE]
>
>Par défaut, les événements marketing envoyés sont filtrés hors de la tâche de sortie.  Si vous souhaitez voir les événements marketing envoyés dans Dynamic 365, vous devez modifier le filtre (étape 5) de la tâche de sortie dans Unifi.

Il existe deux rôles distincts dans Unifi, un utilisateur propriétaire et un utilisateur analyste en lecture seule. Un utilisateur propriétaire peut modifier des traitements et des plannings, contrairement à l’analyste en lecture seule, qui ne peut pas.  Il ne peut y avoir qu’un seul utilisateur propriétaire pour une instance de client donnée.  Si le client doit modifier la personne affectée en tant qu’utilisateur propriétaire, il peut envoyer un e-mail à [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) avec la demande de modification.

La configuration Unifi, les détails du traitement, la configuration et la surveillance sont présentés dans les vidéos ci-dessous.

## Traitements Unifi

### Présentation des traitements Unifi

>[!VIDEO](https://video.tv.adobe.com/v/27392?captions=fre_fr)

Cette vidéo explique les différents traitements Unifi requis pour l&#39;intégration Adobe Campaign Standard avec Microsoft Dynamics 365 (02:10 min)

### Détails du traitement Unifi : entrée et sortie

>[!VIDEO](https://video.tv.adobe.com/v/27396?captions=fre_fr)

Cette vidéo explique les traitements d&#39;entrée et de sortie dans Unifi (04:27 min)

### Mise en opération et surveillance

>[!VIDEO](https://video.tv.adobe.com/v/27391?captions=fre_fr)

Cette vidéo explique les workflows et plannings (03:03 min)

Plus comme suit
* [Utilisation d&#39;Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuration de Microsoft Dynamics 365 pour l&#39;intégration Campaign](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Configuration d’Adobe IO pour l’intégration Microsoft Dynamics 365 - Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Page des fonctionnalités d&#39;intégration de Microsoft Dynamics 365](https://helpx.adobe.com/fr/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)