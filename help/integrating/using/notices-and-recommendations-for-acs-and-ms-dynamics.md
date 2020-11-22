---
solution: Campaign Standard
product: campaign
title: Gestion des données dans Campaign et Microsoft Dynamics 365
description: Découvrez comment Campaign Standard et Microsoft Dynamics 365 gèrent les données communes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 100%

---


# Gérer les données entre Campaign et Microsoft Dynamics 365

## Source de vérité pour la synchronisation unidirectionnelle

En ce qui concerne la synchronisation des contacts et des entités personnalisées, cette intégration traite Dynamics 365 comme la source de vérité. Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées dans Campaign pendant la synchronisation, car la synchronisation est unidirectionnelle.

## Suppression de contacts

Si vous le souhaitez, l’intégration peut être configurée pour émettre des appels de suppression de profil vers Campaign lorsqu’un contact est supprimé dans Dynamics 365, afin de préserver l’intégrité des données.

Cependant, une suppression de profil est différente d’une suppression des informations personnelles. Une suppression des informations personnelles dans Campaign supprimera l’enregistrement du profil Campaign et les entrées de log associées ; alors qu’une suppression du profil normale ne fera que supprimer l’enregistrement du profil ACS, laissant des traces dans les logs Campaign.

Si la fonction de suppression du profil est activée dans l’intégration, il sera nécessaire de suivre d’autres étapes pour traiter correctement les demandes d’accès à des informations personnelles provenant du titulaire de données. Reportez-vous aux étapes de la [section ci-dessous](#manage-privacy-requests).

## Confidentialité

### Gérer les demandes d’accès à des informations personnelles {#manage-privacy-requests}

Cette intégration est conçue pour transférer les données d’utilisateur final (y compris, mais sans s’y limiter, les informations personnelles, si elles sont contenues dans vos données d’utilisateur final), entre Microsoft Dynamics 365 et Adobe Campaign Standard. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

L’intégration ne permet pas de supprimer ou de traiter toute autre demande d’accès à des informations personnelles (à l’exception de la désinscription). Lorsque vous traitez des demandes d’accès à des informations personnelles, vous devez le faire indépendamment dans Dynamics 365 et Campaign (via Adobe Experience Platform Privacy Service).

Si vous avez configuré l’intégration pour émettre des appels de suppression de profil classiques à Campaign lorsqu’un contact est supprimé dans Dynamics 365, suivez les étapes ci-dessous. Vérifiez qu’aucune mise à jour n’est effectuée sur l’enregistrement concerné au cours de ce processus.

1. Émettre une demande de suppression des informations personnelles à [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Surveiller la demande jusqu’à ce qu’elle soit terminée

1. Vérifier que l’enregistrement ne se trouve plus dans votre instance Campaign

1. (Peu après) Émettre la suppression des informations personnelles dans Dynamics 365

1. Vérifier que l’enregistrement a été supprimé des deux systèmes

Vous trouverez ci-dessous des liens pour vous aider à implémenter et/ou supprimer des demandes liées à la confidentialité dans chaque système :

* [Microsoft Dynamics 365](https://docs.microsoft.com/fr-fr/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Confidentialité et ressources liées {#privacy-linked-resources}

Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, applicables à l’utilisation de Campaign par un client, il doit être lié à un enregistrement de profil Campaign correspondant (soit directement, soit par l’intermédiaire d’une autre ressource personnalisée) afin qu’une suppression liée à la confidentialité dans l’enregistrement de profil puisse également supprimer l’enregistrement de la ressource personnalisée liée contenant des informations personnelles. Les options de liaison et de suppression entre les entités doivent être configurées pour permettre cette suppression en cascade des enregistrements liés. Des informations personnelles ne doivent pas être saisies dans une ressource personnalisée qui n’est pas liée au profil.

Découvrez comment mapper des ressources Campaign et des entités Dynamics 365 [dans cette section](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Désinscription (opt-out)

En raison des différences dans les attributs de désinscription entre Dynamics 365 et Campaign, et des différences dans les besoins commerciaux de chaque client, le mappage de désinscription a été laissé comme un exercice que le client doit terminer. Il est important de s’assurer que les désinscriptions sont correctement mappées entre les systèmes afin que les préférences de désinscription de l’utilisateur final soient préservées et qu’elles ne reçoivent pas de communication via un canal dont elles se sont désinscrites.

Sachez que seuls les attributs Campaign avec le préfixe « Ne plus contacter par » (ex. : Ne plus contacter par email) ou l’attribut spécifique de l’option d’Opt-out du CCPA peuvent être utilisés dans les mappages de désinscription. [En savoir plus](../../developing/using/datamodel-profile.md).
Dans Dynamics 365, la plupart des champs de désinscription ont le préfixe « donot » ; toutefois, vous pouvez également utiliser d’autres attributs personnalisés à des fins de désinscription si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration de désinscription dont vous avez besoin pour votre entreprise :

* Dynamics 365 est une source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Dynamics 365 vers Campaign
* Campaign est la source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Campaign vers Dynamics 365
* Dynamics 365 ET Campaign sont les deux sources de vérité : les attributs de désinscription seront synchronisés de façon bidirectionnelle entre Campaign et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des désinscriptions entre les systèmes, le flux de données de désinscription de l’intégration peut être désactivé.

La configuration de désinscription bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes. La logique compare la date et l’heure entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut. Si Campaign contient la date et l’heure les plus récentes, alors la valeur Campaign prévaut. Si Dynamics 365 contient la date et l’heure les plus récentes ou identiques, alors opt-out=TRUE gagne (en supposant que l’une des valeurs soit TRUE).

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les règles de typologie par défaut et spécifiques dans Adobe Campaign avant d’effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences de désinscription reflètent fidèlement les choix d’intention/de communication du destinataire et n’interrompent pas par inadvertance la diffusion d’une relation ou de messages transactionnels tels que les confirmations de commande client.

Si vous avez sélectionné la configuration de désinscription bidirectionnelle ou de Campaign vers Dynamics 365, les données de désinscription Campaign seront régulièrement exportées via le workflow vers votre zone de stockage SFTP dans Campaign (voir « Utilisation du stockage SFTP dans Campaign ci-dessous »). Si vos workflows de désinscription Campaign s’arrêtent, vous devrez les redémarrer manuellement dès que possible afin de réduire le risque de synchronisations de désinscription manquées.

## Utilisation du stockage SFTP dans Campaign

Votre stockage SFTP dans Campaign devra être utilisé par l’intégration dans les cas pratiques ci-dessous.  Vous devez vous assurer que votre compte SFTP dispose d’une capacité de stockage suffisante pour prendre en charge ces cas pratiques.  Le dépassement de la capacité de stockage SFTP sous licence peut nuire gravement à l’utilisation fonctionnelle de Campaign, à l’intégration et/ou au compte SFTP.

| Cas pratique | Description |
|---|---|
| Chargement initial des données | Les tables Dynamics 365 de plus de 500 000 enregistrements devront être exportées vers le stockage SFTP dans Campaign pour être importées via le workflow. À partir de ce moment, l’intégration utilisera les API pour les mises à jour incrémentielles. |
| Désinscription bidirectionnelle et désinscription unidirectionnelle de Campaign vers Dynamics 365 | Les flux de données de désinscription bidirectionnelle et de désinscription unidirectionnelle de Campaign vers Dynamics 365 utiliseront le stockage SFTP dans Campaign. Un workflow ACS exportera les modifications incrémentielles dans le dossier SFTP. À partir de là, l’intégration récupérera les enregistrements et les traitera. |
| Récupération après sinistre | Dans le cas improbable d’un sinistre lié au système, le cas pratique « Chargement initial des données » sera suivi pour alimenter les mises à jour incrémentielles dans Campaign qui ont été manquées. |

## Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Dynamics 365 vers Campaign. Les enregistrements Campaign créés en dehors de l’intégration (c.-à-d. non créés par le traitement de synchronisation) ne seront pas modifiés par l’intégration, y compris les enregistrements Campaign existants au moment de la configuration de l’intégration.

Comme cette intégration utilise le champ **[!UICONTROL externalId]** dans Campaign pour synchroniser les enregistrements de profil Campaign avec les enregistrements de contact Dynamics 365, ce champ Campaign (**[!UICONTROL externalId]**) doit être renseigné avec la valeur Dynamics 365 **[!UICONTROL contactId]** pour les enregistrements que vous souhaitez synchroniser à partir de Dynamics 365.  Les entités personnalisées sont également synchronisées à l’aide d’un identifiant unique Dynamics 365. L’entité personnalisée Campaign devra inclure cet attribut d’identifiant dans une colonne de table. La colonne externalId peut être utilisée pour stocker cette valeur d’attribut, mais elle n’est pas requise pour les entités personnalisées Campaign.

N’oubliez pas que Dynamics 365 reste la source de vérité et que les données de profil Campaign peuvent être écrasées lorsque l’intégration détecte les mises à jour du côté de Dynamics 365.  D’autres étapes peuvent également être nécessaires pour activer l’intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l’intégration.

## Fréquence de synchronisation des données

L’intégration utilise une architecture qui permet de détecter les mises à jour et de les ajouter à la « file d’attente » de traitement peu de temps après leur apparition dans Dynamics 365 (c’est-à-dire, en diffusion, et non en traitement par lots). Pour cette raison, il n’est pas nécessaire de spécifier les fréquences ou les plannings d’exécution des flux de données.

L’exception à cette règle est le flux de données de désinscription bidirectionnelle et de Campaign vers Dynamics 365. Pour ces configurations de désinscription, les enregistrements ACS mis à jour sont exportés vers SFTP par le biais d’un workflow ACS une fois par jour, après quoi l’outil d’intégration lit le fichier et traite l’enregistrement.

## Contrat d’utilisation des données

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux États-Unis dans le cadre de cette intégration. Voir à ce sujet [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
