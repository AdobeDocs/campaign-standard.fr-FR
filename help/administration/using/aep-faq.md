---
title: FAQ sur le SDK Adobe Experience Platform et l’intégration Adobe Campaign
description: FAQ sur le SDK Adobe Experience Platform et l’intégration Adobe Campaign
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 762700893c913d9aea884d00438c84b39a800188
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 4%

---


# FAQ sur l’intégration du SDK Experience Platform {#aep-faq}

Pour envoyer des notifications Push et des messages In-App avec l’application Experience Platform SDK, une application mobile doit être configurée dans Adobe Experience Platform SDK et configurée dans Adobe Campaign.

La section ci-dessous liste les questions courantes sur cette synchronisation.

Pour plus d’informations sur les applications Push ou In-App, consultez les FAQ suivantes :

* [FAQ sur les notifications Push](../../channels/using/about-push-notifications.md#push-faq)
* [FAQ in-app](../../channels/using/about-push-notifications.md#in-app-faq)
* [FAQ sur la synchronisation avec le lancement du processus technique](../../administration/using/syncwithlaunch-faq.md)

## Ressources utiles avant de commencer {#resource-mobile-property}

Consultez les ressources ci-dessous pour plus d’informations sur le SDK Adobe Experience Platform et l’intégration des Campaign Standards :

* Vidéo de [présentation du lancement/de la mobilité](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Guide des [conseils et astuces sur les lancements/dispositifs portables](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## L’intégration du SDK Adobe Experience Platform est-elle disponible pour Adobe Campaign Standard et Adobe Campaign Classic ? {#aep-validity}

Oui, [!DNL Adobe Experience Platform SDK] l&#39;intégration est disponible pour Adobe Campaign Standard et Adobe Campaign Classic. Vous devez installer l’ **[!UICONTROL extension]** correspondante via [!DNL Adobe Launch] pour activer l’intégration.

Pour plus d&#39;informations, reportez-vous à cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) pour Campaign Classic et à cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) pour Campaign Standard.

## Quelles fonctionnalités l’intégration du SDK Adobe Experience Platform facilite-t-elle en Adobe Campaign ? {#aep-capabilities}

Consultez le tableau ci-dessous pour en savoir plus sur ces fonctionnalités.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] l’intégration inclut des événements comme déclencheurs pour les messages in-app (s/o pour les notifications Push), enrichissant les profils avec [!DNL Places] des données et prenant en charge les notifications locales. Consultez cette [page](../../channels/using/preparing-and-sending-an-in-app-message.md) pour plus d&#39;informations. <br>[!DNL Places] l&#39;intégration limitée comprend l&#39;enrichissement des profils avec [!DNL Places] des données.

## Quel est le cas d’utilisation de l’intégration du SDK Adobe Experience Platform dans Adobe Campaign Standard ? {#aep-use-cases}

Les cas d’utilisation suivants sont pris en charge :

* Acquérir un Profil **** mobile dans Campaign (identifié par ECID dans **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > Application **[!UICONTROL mobile (SDK AEP) > Abonnés d&#39;applications MobileOnglet]******
* Enrichir un Profil **** Mobile dans Adobe Campaign (nécessite l’extension **[!UICONTROL de ressource]** personnalisée de la table appSubscriberRcp)
* Acquérir un jeton Push pour l’envoi de messages Push (nécessite l’inclusion de l’utilisateur pour recevoir les messages Push)
* Envoi de messages Push et In-App
* Suivre l’interaction de l’utilisateur avec les messages Push et In-App et fournir des rapports sur cette interaction

## Que dois-je faire pour acquérir un Profil mobile à Campaign ? {#mobile-profile-campaign}

Pour ce faire, procédez comme suit :

1. Configurez une propriété **** Mobile dans [!DNL Launch].
1. Installez l’extension Adobe Campaign Standard. Notez que l&#39;extension Adobe Campaign Standard nécessite également des extensions **[!UICONTROL Mobile Core]**, **[!UICONTROL Profil]** et **[!UICONTROL Lifecycle]** qui sont installées par défaut dans [!DNL Launch].
   * Les utilisateurs doivent configurer le délai d’expiration de la session dans l’extension **[!UICONTROL Mobile Core]** qui a un impact sur la fréquence des événements de cycle de vie.
   * Une fois l&#39;extension configurée, les utilisateurs doivent ajouter les dépendances appropriées dans l&#39;application mobile à l&#39;aide de Cocoapods pour iOS et Gradle pour Android. Suivez les instructions [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Prenez toujours les dernières versions des bibliothèques.
   * Dans l’application mobile, enregistrez **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle et Signal extensions.]****** Suivez les instructions [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Une fois les extensions enregistrées, début ACPCore. Pour Android, veillez à définirApplication onCreate(). Suivez les instructions exactes fournies dans les instructions d’installation de Mobile pour votre propriété Mobile dans Launch.
   * Les API SDK suivantes seront également requises. Mettez en oeuvre les API Début de cycle de vie et Pause comme décrit [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) pour Android et ici pour iOS.
1. Configurez une propriété **** Mobile en Adobe Campaign Standard. Suivez la procédure [ici](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Que dois-je faire pour enrichir un Profil mobile à Campaign ? {#enrich-mobile-profile}

Vous devez configurer un postback CollectPII (reportez-vous à cette [page](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#PIIpostback)) et mettre en oeuvre l’API CollectPII à partir du SDK (reportez-vous à cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## À quelle fréquence un appel CollectPII doit-il être déclenché ? {#collect-pii}

L&#39;objectif de l&#39;appel CollectPII est d&#39;enrichir le Profil Mobile de Campaign. Il doit être déclenché chaque fois qu’il existe de nouvelles informations significatives que les clients souhaitent ajouter au profil en fonction de leurs cas d’utilisation et de leurs besoins commerciaux.

## Les appels CollectPII peuvent-ils être déclenchés en réponse à plusieurs événements de déclenchement ? {#collect-pii-calls}

Oui. En fonction des besoins de votre entreprise, vous pouvez déclencher des appels CollectPII en réponse à la connexion de l’utilisateur à l’application, à l’achat d’un article, d’un événement de cycle de vie ou à l’entrée d’un utilisateur dans une géofence, etc. En résumé, une interaction de l’utilisateur avec l’application qui génère des informations que vous souhaitez utiliser pour l’enrichissement du Profil.

## Puis-je simplement déclencher des appels CollectPII en réponse à tous les événements mobiles ? {#collect-pii-events}

La fréquence et la conception des appels CollectPII doivent être dictées par les besoins de l&#39;entreprise et ne doivent pas être déclenchées aveuglément car elles créent une charge supplémentaire sur la base de données.

### Lorsque j&#39;essaie d&#39;accéder aux applications Adobe Experience Platform dans Campaign ou Launch, j&#39;obtiens parfois une erreur de propriété non disponible. {#aep-error}

Il s’agit d’un problème connu qui se produit en raison de l’expiration des jetons. Vous devriez essayer de vous déconnecter et de vous connecter.

## Quelles seraient les recommandations de ressources utiles pour en savoir plus sur le SDK Adobe Experience Platform (anciennement appelé SDK V5) ?{#resource-aep}

Consultez les ressources ci-dessous :

* [Documentation du SDK Experience Platform](https://aep-sdks.gitbook.io/docs/)
* Prise en main de la [documentation sur le SDK de lancement et d’Experience Platform](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Mise à niveau vers la [documentation du SDK Experience Platform](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* [Documentation du SDK Experience Platform Github](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
