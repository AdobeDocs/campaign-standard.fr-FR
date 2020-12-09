---
solution: Campaign Standard
product: campaign
title: FAQ sur le SDK Adobe Experience Platform et l’intégration d’Adobe Campaign
description: FAQ sur le SDK Adobe Experience Platform et l’intégration d’Adobe Campaign
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '946'
ht-degree: 100%

---


# FAQ sur l’intégration du SDK Experience Platform {#aep-faq}

Pour envoyer des notifications push et des messages In-App avec l’application SDK Experience Platform, une application mobile doit être créée dans le SDK Adobe Experience Platform et configurée dans Adobe Campaign.

La section ci-dessous répertorie les questions courantes sur cette synchronisation.

Pour plus d’informations sur les notifications push ou les messages In-App, consultez les FAQ suivantes :

* [FAQ sur les notifications push](../../channels/using/about-push-notifications.md#push-faq)
* [FAQ sur les messages In-App](../../channels/using/about-in-app-messaging.md#in-app-faq)
* [FAQ sur le workflow technique de synchronisation avec Launch](../../administration/using/syncwithlaunch-faq.md)

## Ressources utiles avant de commencer {#resource-mobile-property}

Consultez les ressources ci-dessous pour plus d’informations sur le SDK Adobe Experience Platform et l’intégration de Campaign Standard :

* [Vidéo de présentation](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video) de Launch/des applications mobiles
* [Guide des conseils et astuces](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf) concernant Launch/les applications mobiles

## L’intégration du SDK Adobe Experience Platform est-elle disponible pour Adobe Campaign Standard et Adobe Campaign Classic ? {#aep-validity}

Oui, l’intégration du [!DNL Adobe Experience Platform SDK] est disponible pour Adobe Campaign Standard et Adobe Campaign Classic. Vous devez installer l’**[!UICONTROL extension]** correspondant à l’aide d’[!DNL Adobe Launch] pour activer l’intégration.

Pour plus d’informations à ce propos, consultez cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

## Quelles fonctionnalités l’intégration du SDK Adobe Experience Platform facilite-t-elle dans Adobe Campaign ? {#aep-capabilities}

Consultez le tableau ci-dessous pour en savoir plus sur ces fonctionnalités.

![](assets/faq.png)

>[!NOTE]
>
>L’intégration de [!DNL Places] inclut les événements Places qui servent de déclencheurs pour les messages In-App (sans objet pour les notifications push), ce qui permet d’enrichir les profils grâce aux données [!DNL Places] et de gérer les notifications locales. Voir cette [page](../../channels/using/preparing-and-sending-an-in-app-message.md) pour plus d’informations. L’intégration limitée de <br>[!DNL Places] comprend l’enrichissement des profils à l’aide de données [!DNL Places].

## Quel cas pratique l’intégration du SDK Adobe Experience Platform dans Adobe Campaign Standard facilite-t-elle ? {#aep-use-cases}

Les cas pratiques suivants sont pris en charge :

* Acquérir un **[!UICONTROL Profil mobile]** dans Campaign (identifié par ECID dans l’onglet **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Application mobile (SDK AEP)]** > **[!UICONTROL Abonnés à l’application mobile]**)
* Enrichir un **[!UICONTROL Profil mobile]** dans Adobe Campaign (nécessite l’extension **[!UICONTROL Ressource personnalisée]** de la table appSubscriberRcp)
* Acquérir un jeton push pour l’envoi de messages push (nécessite l’accord préalable (opt-in) de l’utilisateur pour recevoir les messages push)
* Envoyer des messages push et In-App
* Tracker les interactions de l’utilisateur à l’aide des messages push et In-App et fournir des rapports à ce sujet

## Que dois-je faire pour acquérir un profil mobile dans Campaign ? {#mobile-profile-campaign}

Procédez comme suit :

1. Configurez une **[!UICONTROL propriété mobile]** dans [!DNL Launch].
1. Installez l’extension Adobe Campaign Standard. Notez que l’extension Adobe Campaign Standard nécessite également les extensions **[!UICONTROL Mobile Core]**, **[!UICONTROL Profil]** et **[!UICONTROL Cycle de vie]** qui sont installées par défaut dans [!DNL Launch].
   * Les utilisateurs doivent configurer le délai d’expiration de la session dans l’extension **[!UICONTROL Mobile Core]**, ce qui a un impact sur la fréquence des événements du cycle de vie.
   * Une fois l’extension configurée, les utilisateurs doivent ajouter les dépendances appropriées dans l’application mobile à l’aide de Cocoapods pour iOS et Gradle pour Android. Suivez les instructions décrites [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Choisissez toujours les versions les plus récentes des bibliothèques.
   * Dans l’application mobile, enregistrez les extensions **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identité]**, **[!UICONTROL Cycle de vie]** et **[!UICONTROL Signal]**. Suivez les instructions décrites [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Une fois les extensions enregistrées, lancez ACPCore. Pour Android, veillez à définir Application onCreate(). Suivez scrupuleusement la procédure indiquée dans les instructions d’installation mobile pour la propriété Mobile de Launch.
   * Les API de SDK suivantes seront également nécessaires. Mettez en œuvre les API Début de cycle de vie et Pause comme décrit [ici](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) pour Android et ici pour iOS.
1. Configurez une **[!UICONTROL propriété mobile]** dans Adobe Campaign Standard. Appliquez la procédure décrite [ici](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Que dois-je faire pour enrichir un profil mobile dans Campaign ? {#enrich-mobile-profile}

Vous devez configurer un postback CollectPII (consultez à ce sujet cette [page](https://helpx.adobe.com/fr/campaign/kb/config-app-in-launch.html#PIIpostback)) et mettre en œuvre l’API CollectPII à partir du SDK (consultez à ce sujet cette [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## À quelle fréquence un appel CollectPII doit-il être déclenché ? {#collect-pii}

L’objectif de l’appel CollectPII est d’enrichir le profil mobile dans Campaign. Il doit être déclenché chaque fois qu’il existe de nouvelles informations significatives que les clients souhaitent ajouter au profil en fonction de leurs cas pratiques et de leurs besoins commerciaux.

## Les appels CollectPII peuvent-ils être déclenchés en réponse à plusieurs événements de déclenchement ? {#collect-pii-calls}

Oui. En fonction des besoins de votre entreprise, vous pouvez déclencher des appels CollectPII en réponse à la connexion de l’utilisateur à l’application, à l’achat d’un article, d’un événement de cycle de vie ou à l’entrée d’un utilisateur dans une zone de géorepérage, etc. En résumé, il peut s’agir de toute interaction de l’utilisateur avec l’application générant des informations que vous souhaitez utiliser pour l’enrichissement du profil.

## Puis-je simplement déclencher des appels CollectPII en réponse à tous les événements mobiles ? {#collect-pii-events}

La fréquence et la conception des appels CollectPII doivent être dictées par les besoins de l’entreprise. Ces appels ne doivent pas être déclenchés sans discernement, car ils créent une charge supplémentaire pour la base de données.

### Lorsque j’essaie d’accéder aux applications Adobe Experience Platform dans Campaign ou Launch, j’obtiens parfois une erreur indiquant qu’une propriété n’est pas disponible. {#aep-error}

Il s’agit d’un problème connu résultant de l’expiration des jetons. Vous devriez essayer de vous déconnecter, puis de vous connecter de nouveau.

## Quelles seraient les recommandations de ressources utiles pour en savoir plus sur le SDK Adobe Experience Platform (anciennement appelé SDK V5) ?{#resource-aep}

Consultez les ressources ci-dessous :

* [Documentation](https://aep-sdks.gitbook.io/docs/) du SDK Experience Platform
* [Documentation](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) Prise en main du SDK Launch et Experience Platform
* [Documentation](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep) Mise à niveau vers le SDK Experience Platform
* [Documentation](https://github.com/Adobe-Marketing-Cloud/acp-sdks/) du SDK Github Experience Platform

## L’erreur « Vous n’avez pas d’accès en écriture sur la diffusion » s’affiche lors de la création d’une diffusion de notification push. {#write-access-error}

Vérifiez les points suivants :

* L’application mobile doit être mappée sur l’entité organisationnelle de l’utilisateur qui doit créer et envoyer des diffusions push. L’utilisateur d’une entité organisationnelle fille ne peut pas créer de diffusion push à l’aide d’une application mappée sur l’entité organisationnelle parente.

* Campaign ou le programme au sein duquel la diffusion push est créée doit être mappé sur l’entité organisationnelle de l’utilisateur qui doit créer et envoyer des diffusions push. L’utilisateur de l’entité organisationnelle fille ne peut pas créer de diffusion push dans une campagne ou un programme mappé sur l’entité organisationnelle parente.