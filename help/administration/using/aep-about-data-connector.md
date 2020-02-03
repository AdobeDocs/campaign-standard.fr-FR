---
title: À propos d’Adobe Experience Platform Data Connector
description: Gérez les schémas XDM pour rendre vos données Campaign Standard disponibles sur Adobe Experience Platform.
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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# À propos d’Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

Adobe Experience Platform Data Connector aide les clients existants à rendre leurs données disponibles sur Adobe Experience Platform en mappant les données XTK (données assimilées dans Campaign) aux données du modèle de données d’expérience (XDM) sur Adobe Experience Platform.

Notez que le connecteur est **unidirectionnel** et envoie les données d’Adobe Campaign Standard vers Adobe Experience Platform. Les données ne sont jamais envoyées d’Adobe Experience Platform à Adobe Campaign Standard.

Le connecteur de données Adobe Experience Platform est destiné aux ingénieurs **de** données qui comprennent les ressources personnalisées d’Adobe Campaign Standard et comprennent comment le schéma de données global du client doit se trouver dans Adobe Experience Platform.

Les sections suivantes décrivent les étapes clés pour effectuer un mappage de données entre Campaign Standard et Adobe Experience Platform. Cela commence par la création d’un schéma XDM et d’un jeu de données.

>[!NOTE]
>Une fois que le connecteur de données d’Adobe Experience Platform est configuré et que les données sont correctement assimilées dans Adobe Experience Platform, vous devez activer le jeu de données afin que les données soient incluses dans le profil client en temps réel.
>
>Cela peut être effectué via les API ou l’interface d’Adobe Experience Platform. Pour plus d&#39;informations, reportez-vous aux documentations dédiées :
>
>* [Activation d’un jeu de données pour le profil client en temps réel](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [Configuration d’un jeu de données pour le profil client et le service d’identité en temps réel à l’aide d’API](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## Principaux concepts {#key-concepts}

* Le mappage hors zone n’est disponible que pour les champs fournis par défaut dans Campaign Standard. Pour importer tous les champs et ressources personnalisés, chaque client doit définir son propre mappage.

* Adobe Experience Platform Data Connector transmettra régulièrement les données de profil à travers la plateforme. &#x200B; La durée de l’intervalle est de 15 mn. Cette valeur n’est pas modifiable.

   >[!NOTE]
   >
   >Cette durée peut être modifiée à l’aide des API [d’](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md)Adobe Experience Platform.

* L’ingénieur de données peut publier, modifier et suspendre le mappage de Campaign à Adobe Experience Platform.

* Toute dimension de ciblage peut être mappée. Il est recommandé d’avoir un mappage unique pour tous les champs d’une seule dimension de ciblage.

* Toutes les mises à jour de profil, y compris les exclusions/exclusions de canal, font partie de la mise à jour par lot.

* Toute modification du schéma Adobe Campaign Standard ou XDM doit être manuellement remappée. &#x200B;

* Le journal de suivi et les données Broadlog sont automatiquement assimilés à Adobe Experience Platform en tant qu’événements d’expérience. Cette importation est diffusée en temps réel sur Adobe Experience Platform.

## Limitations {#limitations}

* Le transfert prêt à l’emploi des événements d’abonnement n’est pas pris en charge. Pour transférer des événements d’abonnement, vous pouvez créer le fichier XDM et le jeu de données correspondants sur Adobe Experience Platform, puis configurer un mappage de données personnalisé pour ces données.

* En ce qui concerne les demandes de confidentialité, les clients doivent placer des requêtes distinctes pour le service de confidentialité principal de Campaign et Adobe Experience Platform pour les actions d’accès et de suppression.

* Pour chaque champ XDM, l’étiquetage DULE doit être effectué dans Adobe Experience Platform. Il est de la responsabilité du client d’appliquer des étiquettes DOLE.

* Les restrictions sur les actions marketing ne s’appliquent qu’après l’application des libellés DULE dans Adobe Experience Platform. Auparavant, toutes les données étaient disponibles pour tous les types d’actions marketing.

* Toutes les 15 minutes, le traitement par lot est en cours d’exécution et identifie les enregistrements qui ont changé depuis le dernier lot. Si tous les enregistrements changent au même horodatage, un goulot d’étranglement des performances peut sembler gérer l’ingestion de tous les profils.
