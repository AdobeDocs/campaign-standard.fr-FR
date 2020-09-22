---
title: Data Management Campaign et Microsoft Dynamics 365
description: Découvrez comment Campaign Standard et Microsoft Dynamics 365 gèrent les données communes
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2ef169d9bf76856bb687af88358e0452953313a0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Gérer les données entre Campaign et Microsoft Dynamics 365

## Source de vérité pour la synchronisation unidirectionnelle

Pour la synchronisation des contacts et des entités personnalisées, cette intégration traite Dynamics 365 comme la source de vérité.  Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365, et non Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées dans Campaign pendant la synchronisation, car la synchronisation est unidirectionnelle.

## Suppression de contacts

Si vous le souhaitez, l&#39;intégration peut être configurée pour émettre des appels de suppression de profil à Campaign lorsqu&#39;un contact est supprimé dans Dynamics 365, afin de préserver l&#39;intégrité des données.

Cependant, une suppression de profil est différente d’une suppression de confidentialité. Une suppression de la confidentialité dans Campaign supprimera l&#39;enregistrement du profil Campaign et les entrées de journal associées ; alors qu&#39;une suppression régulière du profil ne fera que supprimer l&#39;enregistrement du profil ACS, laissant des restes dans les journaux Campaign.

Si la fonction de suppression du profil est activée dans l’intégration, d’autres étapes devront être suivies pour traiter correctement les demandes de confidentialité des données. Reportez-vous aux étapes de la [section ci-dessous](#manage-privacy-requests).

## Confidentialité

### Gérer les requêtes de confidentialité {#manage-privacy-requests}

Cette intégration est conçue pour transférer les données d’utilisateur final (y compris, mais sans s&#39;y limiter, les informations personnelles, si elles sont contenues dans vos données d’utilisateur final), entre Microsoft Dynamics 365 et Adobe Campaign Standard. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collection et à votre utilisation des données personnelles.

L&#39;intégration ne permet pas de supprimer ou de traiter toute autre demande de confidentialité (à l&#39;exception de l&#39;exclusion). Lors du traitement des demandes de confidentialité, vous devez le faire dans Dynamics 365 et Campaign (via l&#39;Adobe Experience Platform Privacy Service), indépendamment.

Si vous avez configuré l&#39;intégration pour émettre régulièrement des appels de suppression de profil à Campaign lorsqu&#39;un contact est supprimé dans Dynamics 365, les étapes ci-dessous doivent être suivies. Assurez-vous qu’aucune mise à jour n’est apportée à l’enregistrement en question au cours de ce processus.

1. Émettre une requête de suppression de la confidentialité à [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Surveillance de la demande jusqu’à ce qu’elle soit terminée

1. Vérifier que l&#39;enregistrement n&#39;est plus dans votre instance Campaign

1. (Peu après) Émission de la suppression de la confidentialité dans Dynamics 365

1. Vérifier que l&#39;enregistrement a été supprimé des deux systèmes

Vous trouverez ci-dessous des liens pour vous aider à implémenter et/ou supprimer des demandes liées à la confidentialité dans chaque système :

* [Microsoft Dynamics 365](https://docs.microsoft.com/fr-fr/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Confidentialité et ressources liées {#privacy-linked-resources}

Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, applicables à l’utilisation de Campaign par un client, il doit être lié à un enregistrement de profil Campaign correspondant (soit directement, soit par l’intermédiaire d’une autre ressource personnalisée) afin qu’une suppression liée à la confidentialité dans l’enregistrement de profil puisse également supprimer l’enregistrement de la ressource personnalisée liée contenant des informations personnelles. Les options de liaison et de suppression entre les entités doivent être configurées pour permettre cette suppression en cascade des enregistrements liés. Des informations personnelles ne doivent pas être saisies dans une ressource personnalisée qui n’est pas liée au profil.

Découvrez comment mapper des ressources Campaign et des entités Dynamics 365 [dans cette section](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Désinscription (opt-out)

En raison des différences dans les attributs de désinscription entre Dynamics 365 et Campaign, et des différences dans les besoins commerciaux de chaque client, le mappage de désinscription a été laissé comme un exercice que le client doit terminer. Il est important de s’assurer que les exclusions sont correctement mises en correspondance entre les systèmes afin que les préférences d’exclusion de l’utilisateur final soient maintenues et qu’il ne reçoive pas de communication par le biais d’un canal sur lequel il a choisi de s’exclure.

Sachez que seuls les attributs Campaign avec le préfixe &quot;Plus de contact par&quot; (ex. : Plus de contact par courriel) ou l’attribut spécifique de l’exclusion CCPA peuvent être utilisés dans les mappages d’exclusion. [En savoir plus](../../developing/using/datamodel-profile.md).
Dans Dynamics 365, la plupart des champs d&#39;exclusion comportent le préfixe &quot;donot&quot; ; toutefois, vous pouvez également utiliser d’autres attributs à des fins d’exclusion si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration de désinscription dont vous avez besoin pour votre entreprise :

* Dynamics 365 est une source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Dynamics 365 vers Campaign
* Campaign est la source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Campaign vers Dynamics 365
* Dynamics 365 ET Campaign sont les deux sources de vérité : les attributs de désinscription seront synchronisés de façon bidirectionnelle entre Campaign et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des exclusions entre les systèmes, le flux de données d’exclusion de l’intégration peut être désactivé.

La configuration d’exclusion bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes. La logique compare la date et l’heure entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut. Si Campaign contient la date et l’heure les plus récentes, alors la valeur Campaign prévaut. Si Dynamics 365 contient la date et l’heure les plus récentes ou identiques, alors opt-out=TRUE gagne (en supposant que l’une des valeurs soit TRUE).

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les règles de typologie par défaut et spécifiques dans Adobe Campaign avant d&#39;effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences de désinscription reflètent fidèlement les choix d’intention/de communication du destinataire et n’interrompent pas par inadvertance la diffusion d’une relation ou de messages transactionnels tels que les confirmations de commande client.

Si vous avez sélectionné la configuration d&#39;exclusion bidirectionnelle ou Campaign to Dynamics 365, les données d&#39;exclusion Campaign seront périodiquement exportées via le flux de travail vers votre zone d&#39;enregistrement FTP Campaign (voir &quot;Utilisation SFTP Campaign ci-dessous&quot;). Dans le événement où vos workflows d’exclusion de Campaign s’arrêtent d’être exécutés, vous devrez redémarrer manuellement dès que possible afin de réduire le risque de synchronisations d’exclusion non autorisées.

## Utilisation du protocole SFTP Campaign

Votre enregistrement Campaign SFTP devra être utilisé par l’intégration dans les cas d’utilisation ci-dessous.  Vous devez vous assurer que votre compte SFTP dispose d’une capacité d’enregistrement suffisante pour répondre à ces cas d’utilisation.  Le dépassement de la capacité de l’enregistrement SFTP sous licence peut nuire gravement à l’utilisation fonctionnelle de Campaign, à l’intégration et/ou au compte SFTP.

| Cas pratique | Description |
|---|---|
| Chargement initial des données | Les tables Dynamics 365 de plus de 500 000 enregistrements devront être exportées vers l&#39;enregistrement Campaign SFTP pour être importées via le flux de travail. À partir de ce moment, l’intégration utilisera les API pour les mises à jour incrémentielles. |
| Exclusion bidirectionnelle et exclusion unidirectionnelle Campaign vers Dynamics 365 | Les flux de données d&#39;exclusion bidirectionnelle et de Campaign to Dynamics 365 unidirectionnel utiliseront l&#39;enregistrement Campaign SFTP. Un processus ACS exportera les modifications incrémentielles dans le dossier SFTP. À partir de là, l&#39;intégration récupérera les enregistrements et le processus. |
| Reprise après sinistre | Dans le événement improbable d&#39;une catastrophe système, le cas d&#39;utilisation du &quot;chargement initial des données&quot; sera suivi pour alimenter les mises à jour incrémentielles à Campaign qui ont été ignorées. |

## Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Dynamics 365 à Campaign. Les enregistrements Campaign créés en dehors de l’intégration (c.-à-d. non créés par la tâche de synchronisation) ne seront pas modifiés par l’intégration, y compris les enregistrements Campaign existants au moment de la configuration de l’intégration.

Because this integration uses the **[!UICONTROL externalId]** field in Campaign to sync Campaign profile records with Dynamics 365 contact records, this Campaign field (**[!UICONTROL externalId]** ) must be populated with the Dynamics 365 **[!UICONTROL contactId]** for the records you wish to be synced from Dynamics 365.  Les entités personnalisées sont également synchronisées à l&#39;aide d&#39;un identifiant unique Dynamics 365. L&#39;entité personnalisée Campaign devra inclure cet attribut d&#39;ID dans une colonne de tableau. La colonne externalId peut être utilisée pour stocker cette valeur d&#39;attribut, mais elle n&#39;est pas requise pour les entités personnalisées Campaign.

N&#39;oubliez pas que Dynamics 365 est toujours la source de vérité et que les données du profil Campaign peuvent être remplacées lorsque l&#39;intégration détecte les mises à jour du côté Dynamics 365.  D’autres étapes peuvent également être nécessaires pour activer l’intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l’intégration.

## Fréquence de synchronisation des données

L&#39;intégration utilise une architecture qui permet de détecter les mises à jour et de les ajouter à la &quot;file d&#39;attente&quot; de traitement peu de temps après leur apparition dans Dynamics 365 (c.-à-d. en flux continu, et non en traitement par lots). Pour cette raison, il n’est pas nécessaire de spécifier les fréquences ou les calendriers d’exécution des flux de données.

L&#39;exception à cette règle est le flux de données d&#39;exclusion bidirectionnel et Campaign to Dynamics 365. Pour ces configurations d&#39;exclusion, les enregistrements ACS mis à jour sont exportés vers SFTP par le biais d&#39;un processus ACS une fois par jour, après quoi l&#39;outil d&#39;intégration lit le fichier et traite l&#39;enregistrement.

## Contrat d’utilisation des données

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux États-Unis dans le cadre de cette intégration. Voir à ce sujet [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
