---
solution: Campaign Standard
product: campaign
title: Gestion des données dans Campaign et Microsoft Dynamics 365
description: Découvrez comment Campaign Standard et Microsoft Dynamics 365 gèrent les données communes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2470'
ht-degree: 58%

---


# Bonnes pratiques et limites {#acs-msdyn-best-practices}

## Gérer les données {#acs-msdyn-manage-data}

Pour la synchronisation des contacts et des entités personnalisées, cette intégration traite **Microsoft Dynamics 365 comme la source de vérité**.  Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365 et non en Adobe Campaign Standard).  Si des modifications sont effectuées dans Campaign, elles peuvent éventuellement être remplacées dans Campaign pendant la synchronisation, car la synchronisation est dans une direction.

L&#39;intégration peut être éventuellement configurée pour émettre des appels de suppression de profil à Campaign lorsqu&#39;un contact est supprimé dans Dynamics 365 afin de préserver l&#39;intégrité des données. Cependant, une suppression de profil est différente d’une suppression des informations personnelles. Une suppression de la confidentialité dans Campaign supprimera l&#39;enregistrement du profil Campaign et les entrées de journal associées ; alors qu&#39;une suppression régulière du profil ne fera que supprimer l&#39;enregistrement du profil de Campaign, laissant des restes dans les journaux de Campaign. Si la fonction de suppression du profil est activée dans l’intégration, il sera nécessaire de suivre d’autres étapes pour traiter correctement les demandes d’accès à des informations personnelles provenant du titulaire de données. Reportez-vous à la section [Confidentialité ci-dessous](#manage-privacy-requests).

## Confidentialité{#acs-msdyn-manage-privacy}

Cette intégration est conçue pour transférer des données d&#39;utilisateur final entre Microsoft Dynamics 365 et Adobe Campaign Standard. Ces données incluent des informations personnelles si elles sont contenues dans vos données d&#39;utilisateur final.  En tant que responsable du traitement des données, votre société est responsable du respect des lois et règlements en matière de confidentialité applicables à votre collecte et utilisation des données à caractère personnel.

Cette intégration est conçue pour transférer les données d’utilisateur final (y compris, mais sans s’y limiter, les informations personnelles, si elles sont contenues dans vos données d’utilisateur final), entre Microsoft Dynamics 365 et Adobe Campaign Standard. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

L’intégration ne permet pas de supprimer ou de traiter toute autre demande d’accès à des informations personnelles (à l’exception de la désinscription). Lors du traitement des demandes de confidentialité, vous devez le faire dans Microsoft Dynamics 365 et Campaign (via l&#39;Adobe Experience Platform Privacy Service), indépendamment.

Si vous avez configuré l’intégration pour émettre des appels de suppression de profil classiques à Campaign lorsqu’un contact est supprimé dans Dynamics 365, suivez les étapes ci-dessous. Vérifiez qu’aucune mise à jour n’est effectuée sur l’enregistrement concerné au cours de ce processus.

1. Émettre une demande de suppression des informations personnelles à [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Surveiller la demande jusqu’à ce qu’elle soit terminée

1. Vérifier que l’enregistrement ne se trouve plus dans votre instance Campaign

1. (Peu après) Émettre la suppression des informations personnelles dans Dynamics 365

1. Vérifier que l’enregistrement a été supprimé des deux systèmes

Vous trouverez ci-dessous des liens pour vous aider à implémenter et/ou supprimer des demandes liées à la confidentialité dans chaque système :

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, applicables à l’utilisation de Campaign par un client, il doit être lié à un enregistrement de profil Campaign correspondant (soit directement, soit par l’intermédiaire d’une autre ressource personnalisée) afin qu’une suppression liée à la confidentialité dans l’enregistrement de profil puisse également supprimer l’enregistrement de la ressource personnalisée liée contenant des informations personnelles. Les options de liaison et de suppression entre les entités doivent être configurées pour permettre cette suppression en cascade des enregistrements liés. Des informations personnelles ne doivent pas être saisies dans une ressource personnalisée qui n’est pas liée au profil.

## Désinscription (opt-out){#opt-out}

En raison des différences dans les attributs d&#39;exclusion entre Microsoft Dynamics 365 et Campaign, et des différences dans les besoins commerciaux de chaque client, le mappage d&#39;exclusion a été laissé comme un exercice que le client doit effectuer.  Il est important de s’assurer que les exclusions sont correctement mises en correspondance entre les systèmes afin que les préférences d’exclusion de l’utilisateur final soient maintenues et qu’il ne reçoive pas de communication par le biais d’un canal sur lequel il a choisi de s’exclure.

Sachez que seuls les éléments suivants peuvent être utilisés dans les mappages d’exclusion :

* les attributs Campaign avec le préfixe &quot;Plus de contact par&quot; (par ex., Plus de contact par courrier électronique), ou

* l&#39;attribut spécifique de l&#39;ACFPC

Vous trouverez plus d&#39;informations sur les champs d&#39;entité de Profil [ici](../../developing/using/datamodel-profile.md).

Dans Dynamics 365, la plupart des champs d&#39;exclusion comportent le préfixe &quot;donot&quot;. Cependant, vous pouvez également utiliser d&#39;autres attributs à des fins d&#39;exclusion si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration de désinscription dont vous avez besoin pour votre entreprise :

* **Unidirectionnel (Microsoft Dynamics 365 à Campaign)** : Dynamics 365 est une source de vérité pour les exclusions. Les attributs d&#39;exclusion seront synchronisés dans une direction entre Dynamics 365 et Campaign Standard.
* **Unidirectionnel (Campaign vers Microsoft Dynamics 365)** : Le Campaign Standard est la source de vérité pour les exclusions. Les attributs d&#39;exclusion seront synchronisés dans une direction, du Campaign Standard à Dynamics 365
* **Bidirectionnel** : Dynamics 365 AND Campaign Standard sont deux sources de vérité. Les attributs d&#39;exclusion seront synchronisés bidirectionnellement entre Campaign Standard et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des désinscriptions entre les systèmes, le flux de données de désinscription de l’intégration peut être désactivé.

La configuration de désinscription bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes. La logique compare la date et l’heure entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut. Si Campaign contient la date et l’heure les plus récentes, alors la valeur Campaign prévaut. Si Dynamics 365 contient la date et l’heure les plus récentes ou identiques, alors opt-out=TRUE gagne (en supposant que l’une des valeurs soit TRUE).

Découvrez comment sélectionner les options d&#39;inclusion/exclusion dans [cette section](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les règles de typologie par défaut et spécifiques dans Adobe Campaign avant d’effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences de désinscription reflètent fidèlement les choix d’intention/de communication du destinataire et n’interrompent pas par inadvertance la diffusion d’une relation ou de messages transactionnels tels que les confirmations de commande client.

Si vous avez sélectionné la configuration d&#39;exclusion **Bidirectionnelle** ou **Unidirectionnelle (Campaign à Microsoft Dynamics 365)**, les données d&#39;exclusion Campaign seront périodiquement exportées par le biais du flux de travail vers votre enregistrement FTP Campaign (voir &quot;Utilisation du protocole FTP Campaign ci-ci&quot;). Si vos workflows de désinscription Campaign s’arrêtent, vous devrez les redémarrer manuellement dès que possible afin de réduire le risque de synchronisations de désinscription manquées.

>[!IMPORTANT]
>
>Si vous avez besoin de la configuration d&#39;exclusion **Bidirectionnelle** ou **Unidirectionnelle (Campaign à Microsoft Dynamics 365)**, vous devez adresser la demande à votre contact technique Adobe pour que les workflows d&#39;exclusion soient configurés sur votre instance Campaign.

## Utilisation du stockage SFTP dans Campaign

Votre stockage SFTP dans Campaign devra être utilisé par l’intégration dans les cas pratiques ci-dessous.  Vous devez vous assurer que votre compte SFTP dispose d’une capacité de stockage suffisante pour prendre en charge ces cas pratiques. Le dépassement de la capacité de stockage SFTP sous licence peut nuire gravement à l’utilisation fonctionnelle de Campaign, à l’intégration et/ou au compte SFTP.

| Cas pratique | Description |
|---|---|
| Bidirectionnel et unidirectionnel (Campaign vers Microsoft Dynamics 365) | Les flux de données d&#39;exclusion bidirectionnelles et unidirectionnelles (Campaign to Microsoft Dynamics 365) utiliseront l&#39;enregistrement Campaign SFTP. Un processus Campaign exportera les modifications incrémentielles dans le dossier SFTP. À partir de là, l’intégration récupérera les enregistrements et les traitera. |
| Journaux d’exclusion | Les journaux de sortie du connecteur seront utiles lors du dépannage de l’intégration. Les journaux de sortie peuvent être activés/désactivés. |


>[!IMPORTANT]
>
>Vous êtes responsable des informations que vous accédez et téléchargez à partir des dossiers SFTP. Si les renseignements contiennent des données personnelles, vous êtes responsable de respecter les lois et règlements applicables en matière de protection de la vie privée. [En savoir plus](#acs-msdyn-manage-privacy).

## Gestion des données

### Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Microsoft Dynamics 365 vers Campaign. Les enregistrements Campaign créés en dehors de l’intégration (c.-à-d. non créés par le traitement de synchronisation) ne seront pas modifiés par l’intégration, y compris les enregistrements Campaign existants au moment de la configuration de l’intégration.

Cette intégration utilisant le champ **[!UICONTROL externalId]** dans Campaign pour synchroniser les enregistrements du profil Campaign avec les enregistrements de contact Dynamics 365, ce champ Campaign (**[!UICONTROL externalId]** ) doit être renseigné avec Microsoft Dynamics 365 **[!UICONTROL contactId]** pour les enregistrements que vous souhaitez synchroniser à partir de Microsoft Dynamics 365.  Les entités personnalisées sont également synchronisées à l&#39;aide d&#39;un identifiant unique Microsoft Dynamics 365. L’entité personnalisée Campaign devra inclure cet attribut d’identifiant dans une colonne de table. La colonne externalId peut être utilisée pour stocker cette valeur d’attribut, mais elle n’est pas requise pour les entités personnalisées Campaign.

N&#39;oubliez pas que Microsoft Dynamics 365 est toujours la source de vérité et que les données du profil Campaign peuvent être remplacées lorsque l&#39;intégration détecte les mises à jour du côté Dynamics 365.  D’autres étapes peuvent également être nécessaires pour activer l’intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l’intégration.

### Fréquence de synchronisation des données

L&#39;intégration utilise une architecture qui permet de détecter les mises à jour et de les ajouter à la &quot;file d&#39;attente&quot; de traitement peu de temps après leur apparition dans Microsoft Dynamics 365 (c.-à-d. en flux continu, et non en traitement par lots). Pour cette raison, il n’est pas nécessaire de spécifier les fréquences ou les plannings d’exécution des flux de données.

L&#39;exception à cette règle concerne les flux de données d&#39;exclusion bidirectionnels et Campaign to Dynamics 365. Pour ces configurations d’exclusion, les enregistrements Campaign mis à jour sont exportés vers SFTP via un flux de travail Campaign une fois par jour, après quoi l’outil d’intégration lit le fichier et traite l’enregistrement.

### Contrat d’utilisation des données

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux États-Unis dans le cadre de cette intégration. Voir à ce sujet [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Gardiens et limites

>[!IMPORTANT]
>
>Certaines actions de votre part (p. ex., l&#39;assimilation initiale des enregistrements, la relecture des données d&#39;enregistrement, etc.) peut entraîner une charge importante d&#39;enregistrements ingérés de Microsoft Dynamics 365 vers votre instance Adobe Campaign. Pour réduire le risque de problèmes de performances, il est recommandé d’arrêter tous les processus Campaign (par exemple, aucune activité marketing, aucune exécution de workflows, etc.) jusqu&#39;à ce que la grande quantité de dossiers ait été ingérée à Campaign.

### Entités personnalisées

L’[intégration Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) prend en charge les entités personnalisées, ce qui permet de synchroniser les entités personnalisées de Dynamics 365 avec les ressources personnalisées correspondantes dans Campaign.

L’intégration prend en charge les tables liées et non liées.

Lors de la configuration des flux de données d’entités personnalisées, il est important de tenir compte des points suivants :

* La création et la modification de ressources personnalisées Campaign sont des opérations délicates qui doivent être effectuées uniquement par des utilisateurs experts.
* Pour les flux de données d’entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.
* Si un enregistrement parent et et un enregistrement enfant lié sont créés presque au même moment dans Dynamics 365, en raison du traitement parallèle de l’intégration, il peut arriver qu’un nouvel enregistrement enfant soit créé dans Campaign avant l’enregistrement de son parent.

* Si les enregistrements parent et enfant sont liés du côté Campaign à l’aide de l’option **Lien simple de cardinalité 1**, l’enregistrement enfant reste masqué et inaccessible (via l’interface utilisateur ou l’API) jusqu’à ce que l’enregistrement parent arrive dans Campaign.

* (En supposant que le **lien simple de cardinalité 1** est présent dans Campaign) Si l’enregistrement enfant est mis à jour ou supprimé dans Dynamics 365 et que cette modification est écrite dans Campaign avant que l’enregistrement parent ne s’affiche dans Campaign (ce qui est peu probable, mais qui peut parfois arriver), cette mise à jour ou suppression ne sera pas traitée dans Campaign et une erreur sera générée. Dans le cas d’une mise à jour, l’enregistrement en question devra de nouveau être mis à jour dans Dynamics 365 pour synchroniser l’enregistrement mis à jour. Dans le cas de la suppression, l’enregistrement en question devra être pris en charge séparément du côté Campaign, car il n’y aura plus d’enregistrement dans Dynamics 365 à supprimer ou à mettre à jour.

* Si vous vous trouvez dans une situation où vous pensez avoir masqué des enregistrements enfants sans avoir aucun moyen d’y accéder, vous pouvez temporairement changer le type de lien de cardinalité en **lien simple de cardinalité 0 ou 1** pour accéder à ces enregistrements.

Vous trouverez une présentation plus exhaustive des ressources personnalisées de Campaign dans [cette section](../../developing/using/key-steps-to-add-a-resource.md).

### Barrières de sécurité de l’intégration

Les barrières de sécurité suivantes doivent être prises en compte lors de la planification de l’utilisation de cette intégration. Consultez votre représentant technique Adobe si vous pensez que vous ne respectez pas ces barrières de sécurité.

* Vous devez activer la licence du package Campaign approprié pour prendre en charge le volume d’appels au moteur généré par l’intégration. Le dépassement du volume d’appels du moteur sous licence peut entraîner une baisse des performances de Campaign.

   Utilisez les éléments suivants pour estimer le volume d’appels au moteur à partir de l’intégration :

   * Insertions d’enregistrements (c’est-à-dire, nouvel enregistrement) : 1 appel au moteur
   * Suppressions d’enregistrements : 1 appel au moteur
   * Enregistrer les mises à jour : 2 appels au moteur (un seul appel si l&#39;enregistrement de destination est identique à l&#39;enregistrement source, c&#39;est-à-dire si aucun changement n&#39;est apporté à l&#39;enregistrement Campaign)

   Lors de l’estimation du volume global des appels du moteur Campaign, il est important de tenir compte d’autres sources d’appels du moteur, notamment les landings page, les applications Web, les JSSP, les API, les inscriptions d’applications mobiles, etc.

   Consultez des informations sur le package Campaign à cette adresse : https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html

* L’intégration prend en charge un maximum de 30 millions de contacts.

* L’offre d’intégration standard comprend la prise en charge de cinq entités personnalisées au maximum., chacune ayant une taille maximale de 50 colonnes.

* Vous devez créer et publier vos ressources personnalisées avant de mettre en œuvre l’intégration.

* La profondeur maximale de table lors de la liaison des tables est de deux (c’est-à-dire., table1->table2->table3).

* La prise en charge des types de données Microsoft Dynamic 365 est limitée. Si votre modèle de données contient un type de données autre que des types de données simples (par exemple, chaînes, entiers, décimales, etc.), vous devrez peut-être mettre à jour votre modèle de données avant d’utiliser l’intégration.

* Si vous choisissez de conserver les données existantes dans les entités personnalisées Campaign, vous devrez préparer les données pour l’intégration.

* Il peut être nécessaire d&#39;établir des fenêtres de maintenance à l&#39;intégration entre l&#39;Adobe et le client.

* Gardez à l’esprit que des augmentations importantes ou des &quot;pics&quot; dans l’utilisation de l’intégration (p. ex., une forte augmentation des enregistrements nouveaux ou mis à jour) peuvent entraîner des ralentissements dans la synchronisation des données.

* Dans le cadre de l’intégration, vous devrez exécuter les étapes de configuration préalable à l’intégration dans Microsoft Azure et Dynamics 365. Voir les étapes de configuration [sur cette page](../../integrating/using/d365-acs-configure-d365.md)

* Il est attendu que vous importerez vos modèles de données Dynamics 365 et Campaign dans l’intégration et que vous les gérerez.

### Limites de l’intégration

L&#39;intégration a été conçue pour résoudre le cas d&#39;utilisation générale du déplacement de données commun entre Microsoft Dynamics 365 et Campaign, mais elle n&#39;a pas pour but de traiter chaque cas d&#39;utilisation spécifique à chaque client :

* L’intégration n’émet aucune suppression de confidentialité (ex. : RGPD). La responsabilité de répondre aux demandes d’accès à des informations personnelles des utilisateurs finaux incombe au client ; de telles demandes doivent être effectuées indépendamment à la fois dans Campaign (via Adobe Experience Platform Privacy Service) et dans Dynamics 365. L’intégration peut générer des suppressions régulières pour faciliter la synchronisation des données, si nécessaire.   Consultez [la section Confidentialité](#manage-privacy-requests) pour plus d&#39;informations.

* Aucune donnée de profil ou d’entité personnalisée ne sera synchronisée de Campaign vers Dynamics 365, à l’exception des informations d’opt-out (si elles sont configurées par le client).

* La gestion des abonnements Campaign (c’est-à-dire les abonnements/désabonnements) n’est pas prise en charge de manière native.

* La composition et le déclenchement de campagnes email Campaign à partir de Dynamics 365 ne sont pas pris en charge.

* L&#39;intégration **ne prend pas** en charge la réorganisation des données entre les modèles de données Dynamics 365 et Campaign Standard. Il est prévu que l’intégration synchronise une table Dynamics 365 avec une table Campaign.
