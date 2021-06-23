---
solution: Campaign Standard
product: campaign
title: À propos d’Adobe Experience Platform Data Connector
description: Gérez les schémas XDM pour rendre vos données Campaign Standard disponibles sur Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Intégration de Microsoft CRM
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: ht
source-wordcount: '774'
ht-degree: 100%

---

# À propos d’Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Adobe Experience Platform Data Connector permet aux clients existants de rendre leurs données disponibles sur Adobe Experience Platform en mappant les données XTK (données ingérées dans Campaign) avec les données XDM (Experience Data Model) sur Adobe Experience Platform.

Notez que le connecteur est **unidirectionnel** et envoie les données d’Adobe Campaign Standard vers Adobe Experience Platform. Les données ne sont jamais envoyées d’Adobe Experience Platform vers Adobe Campaign Standard.

Adobe Experience Platform Data Connector est destiné aux **ingénieurs de données** qui comprennent les ressources personnalisées d’Adobe Campaign Standard et connaissent la définition du schéma de données global du client dans Adobe Experience Platform.

Les sections ci-après décrivent les étapes clés pour effectuer un mapping de données entre Campaign Standard et Adobe Experience Platform. Le processus consiste tout d’abord à créer un schéma XDM et un jeu de données.

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#video)

>[!NOTE]
>Une fois Adobe Experience Platform Data Connector configuré et les données correctement ingérées dans Adobe Experience Platform, vous devez activer le jeu de données afin que les données soient incluses dans le profil client en temps réel.
>
>Cette opération peut être effectuée via les API ou à l’aide de l’interface d’Adobe Experience Platform. Pour plus d’informations, consultez la documentation dédiée :
>
>* [Activation d’un jeu de données pour Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html?lang=fr)
>* [Configuration d’un jeu de données pour Real-time Customer Profile et Identity Service à l’aide des API](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html?lang=fr)


## Principaux concepts {#key-concepts}

* Le mapping d’usine n’est disponible que pour les champs fournis par défaut dans Campaign Standard. Pour importer tous les champs et ressources personnalisés, chaque client doit définir son propre mapping.

* Adobe Experience Platform Data Connector transmet régulièrement les données de profil par le biais de la plateforme. &#x200B; La durée de l’intervalle est de 15 minutes. Cette valeur peut être modifiée à l’aide des [API Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=fr).

* Un ingénieur de données peut publier, modifier et suspendre le mapping entre Campaign et Adobe Experience Platform.

* Il est possible de mapper n’importe quelle dimension de ciblage. Il est recommandé d’avoir un mapping unique pour tous les champs d’une seule dimension de ciblage.

* Toutes les mises à jour de profil, y compris les opt-in/opt-out à des canaux, font partie de la mise à jour par lot.

* Toute modification du schéma Adobe Campaign Standard ou XDM doit être remappée manuellement. 

* Le log de tracking et les données de Broadlog sont automatiquement ingérés dans Adobe Experience Platform en tant qu’événements d’expérience. Cette ingestion est diffusée en temps réel vers Adobe Experience Platform.

* Le service d’identifiant Experience Cloud (ECID) est un identifiant d’appareil envoyé par défaut avec les événements Experience.

   Il s’agit d’un identifiant unique et persistant attribué à un visiteur, qui peut être utilisé par le service d’identité de la plate-forme pour identifier le même visiteur et ses données dans différentes solutions Experience Cloud. Pour plus d’informations, reportez-vous à l’[Aide du service d’identité Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

   >[!NOTE]
   >
   >Sachez que si deux personnes ou plus partagent un même appareil, l’ECID sera le même pour ces deux profils dans le service d’identité unifiée.

## Limites {#limitations}

* Le transfert d’usine des événements d’abonnement n’est pas pris en charge. Pour transférer des événements d’abonnement, vous pouvez créer le fichier XDM et le jeu de données correspondants sur Adobe Experience Platform, puis configurer un mapping de données personnalisé pour ces données.

* En ce qui concerne les demandes d’accès à des informations personnelles (actions d’accès et de suppression), les clients doivent effectuer des demandes distinctes par le biais du [Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr#how-to-use-privacy-service-to-manage-privacy-job-requests) : l’une pour Campaign et l’autre pour Adobe Experience Platform. Pour plus d’informations à ce sujet, voir [À propos des demandes d’accès à des informations personnelles](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#righttoaccess) et [Gestion des demandes d’accès à des informations personnelles](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) dans Campaign.

* Pour chaque champ XDM, la définition du libellé DULE doit être effectuée dans Adobe Experience Platform. Il incombe au client d’appliquer des libellés DULE.

* Les restrictions relatives aux actions marketing ne deviennent applicables qu’après application des libellés DULE dans Adobe Experience Platform. Avant, toutes les données sont disponibles quels que soient les types d&#39;actions marketing.

* Toutes les 15 minutes, le traitement par lot est effectué et identifie les enregistrements modifiés depuis le dernier lot. Si tous les enregistrements ont été modifiés avec un même horodatage, une baisse de performances pourrait freiner l’ingestion des profils.

## Tutoriel vidéo {#video}

Cette vidéo présente un aperçu du connecteur de données Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

D’autres vidéos relatives au connecteur de données Adobe Experience Platform sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=fr).
