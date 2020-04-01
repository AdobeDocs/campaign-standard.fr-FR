---
title: À propos d’Adobe Experience Platform Data Connector
description: Gérez les schémas XDM pour rendre vos données Campaign Standard disponibles sur Adobe Experience Platform.
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
source-git-commit: 2d4140982ee772eda9eecb01a55748c1d439150e

---


# À propos d’Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’Assistance clientèle d’Adobe si vous souhaitez y accéder.

Adobe Experience Platform Data Connector permet aux clients existants de rendre leurs données disponibles sur Adobe Experience Platform en mappant les données XTK (données ingérées dans Campaign) avec les données XDM (Experience Data Model) sur Adobe Experience Platform.

Notez que le connecteur est **unidirectionnel** et envoie les données d’Adobe Campaign Standard vers Adobe Experience Platform. Les données ne sont jamais envoyées d’Adobe Experience Platform vers Adobe Campaign Standard.

Adobe Experience Platform Data Connector est destiné aux **ingénieurs de données** qui comprennent les ressources personnalisées d’Adobe Campaign Standard et connaissent la définition du schéma de données global du client dans Adobe Experience Platform.

Les sections ci-après décrivent les étapes clés pour effectuer un mapping de données entre Campaign Standard et Adobe Experience Platform. Le processus consiste tout d’abord à créer un schéma XDM et un jeu de données.

Des vidéos pratiques sont également proposées sur [cette page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Une fois Adobe Experience Platform Data Connector configuré et les données correctement ingérées dans Adobe Experience Platform, vous devez activer le jeu de données afin que les données soient incluses dans Real-time Customer Profile.
>
>Cette opération peut être effectuée via les API ou à l’aide de l’interface d’Adobe Experience Platform. Pour plus d’informations, consultez la documentation dédiée :
>
>* [Activation d’un jeu de données pour Real-time Customer Profile](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [Configuration d’un jeu de données pour Real-time Customer Profile et Identity Service à l’aide des API](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## Principaux concepts {#key-concepts}

* Le mapping d’usine n’est disponible que pour les champs fournis par défaut dans Campaign Standard. Pour importer tous les champs et ressources personnalisés, chaque client doit définir son propre mapping.

* Adobe Experience Platform Data Connector transmet régulièrement les données de profil par le biais de la plateforme. &#x200B; La durée de l’intervalle est de 15 minutes. This value can be modified using [Adobe Experience Platform APIs](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md).

* Un ingénieur de données peut publier, modifier et suspendre le mapping entre Campaign et Adobe Experience Platform.

* Il est possible de mapper n’importe quelle dimension de ciblage. Il est recommandé d’avoir un mapping unique pour tous les champs d’une seule dimension de ciblage.

* Toutes les mises à jour de profil, y compris les opt-in/opt-out à des canaux, font partie de la mise à jour par lot.

* Toute modification du schéma Adobe Campaign Standard ou XDM doit être remappée manuellement. 

* Le log de tracking et les données de Broadlog sont automatiquement ingérés dans Adobe Experience Platform en tant qu’événements d’expérience. Cette importation est diffusée en temps réel sur Adobe Experience Platform.

* Le service d’ID d’expérience (ECID) est un identifiant de périphérique envoyé par défaut avec  d’expérience.

   Il s’agit d’un identifiant unique et persistant attribué à un, qui peut être utilisé par le service d’identité de plate-forme pour identifier le même et ses données dans différentes solutions Experience Cloud. Pour plus d’informations, reportez-vous à l’aide [du service d’identité](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud.

   >[!NOTE]
   >
   >Sachez que si deux ou plus  partagent un même périphérique, l’ECID sera le même pour ces deux  du service d’identité unifiée.

## Limitations {#limitations}

* Le transfert d’usine des événements d’abonnement n’est pas pris en charge. Pour transférer des événements d’abonnement, vous pouvez créer le fichier XDM et le jeu de données correspondants sur Adobe Experience Platform, puis configurer un mapping de données personnalisé pour ces données.

* En ce qui concerne les demandes d’accès à des informations personnelles, les clients doivent effectuer des demandes distinctes pour Campaign core privacy service et pour Adobe Experience Platform dans le cas des actions d’accès et de suppression.

* Pour chaque champ XDM, la définition du libellé DULE doit être effectuée dans Adobe Experience Platform. Il incombe au client d’appliquer des libellés DULE.

* Les restrictions relatives aux actions marketing ne deviennent applicables qu’après application des libellés DULE dans Adobe Experience Platform. Avant, toutes les données sont disponibles quels que soient les types d&#39;actions marketing.

* Toutes les 15 minutes, le traitement par lot est effectué et identifie les enregistrements modifiés depuis le dernier lot. Si tous les enregistrements ont été modifiés avec un même horodatage, une baisse de performances pourrait freiner l’ingestion des profils.
