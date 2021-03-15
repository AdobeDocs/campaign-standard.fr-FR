---
solution: Campaign Standard
product: campaign
title: Gestion des données dans Campaign et Microsoft Dynamics 365
description: Découvrez comment Campaign Standard et Microsoft Dynamics 365 gèrent les données communes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Intégration de Microsoft CRM
role: Data Architect
level: Expérience
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '2476'
ht-degree: 99%

---


# Bonnes pratiques et limites {#acs-msdyn-best-practices}

## Gérer les données {#acs-msdyn-manage-data}

En ce qui concerne la synchronisation des contacts et des entités personnalisées, cette intégration traite **Microsoft Dynamics 365 comme la source de vérité**. Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365 et et non dans Adobe Campaign Standard). Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées dans Campaign pendant la synchronisation, car la synchronisation est unidirectionnelle.

L’intégration peut être facultativement configurée pour émettre des appels de suppression de profil vers Campaign lorsqu’un contact est supprimé dans Dynamics 365, afin de préserver l’intégrité des données. Cependant, une suppression de profil est différente d’une suppression des informations personnelles. Une suppression des informations personnelles dans Campaign supprimera l’enregistrement du profil Campaign et les entrées de log associées ; alors qu’une suppression du profil normale ne fera que supprimer l’enregistrement du profil Campaign, laissant des traces dans les logs Campaign. Si la fonction de suppression du profil est activée dans l’intégration, il sera nécessaire de suivre d’autres étapes pour traiter correctement les demandes d’accès à des informations personnelles provenant du titulaire de données. Reportez-vous aux étapes de la [Confidentialité section ci-dessous](#manage-privacy-requests).

## Confidentialité{#acs-msdyn-manage-privacy}

Cette intégration est conçue pour transférer des données d&#39;utilisateur final entre Microsoft Dynamics 365 et Adobe Campaign Standard. Ces données comprennent des informations personnelles si elles sont contenues dans vos données d&#39;utilisateur final. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

Cette intégration a pour but de transférer les données des utilisateurs finaux (notamment les informations personnelles, lesquelles sont dans les données des utilisateurs finaux) entre Microsoft Dynamics 365 et Adobe Campaign Standard. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

L’intégration ne permet pas de supprimer ou de traiter toute autre demande d’accès à des informations personnelles (à l’exception de la désinscription). Lorsque vous traitez des demandes d’accès à des informations personnelles, vous devez le faire indépendamment dans Microsoft Dynamics 365 et Campaign (via Adobe Experience Platform Privacy Service).

Si vous avez configuré l’intégration pour émettre des appels de suppression de profil classiques à Campaign lorsqu’un contact est supprimé dans Dynamics 365, suivez les étapes ci-dessous. Vérifiez qu’aucune mise à jour n’est effectuée sur l’enregistrement concerné au cours de ce processus.

1. Émettre une demande de suppression des informations personnelles à [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Surveiller la demande jusqu’à ce qu’elle soit terminée

1. Vérifier que l’enregistrement ne se trouve plus dans votre instance Campaign

1. (Peu après) Émettre la suppression des informations personnelles dans Dynamics 365

1. Vérifier que l’enregistrement a été supprimé des deux systèmes

Vous trouverez ci-dessous des liens pour vous aider à implémenter et/ou supprimer des demandes liées à la confidentialité dans chaque système :

* [Microsoft Dynamics 365](https://docs.microsoft.com/fr-fr/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr)

>[!IMPORTANT]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, applicables à l’utilisation de Campaign par un client, il doit être lié à un enregistrement de profil Campaign correspondant (soit directement, soit par l’intermédiaire d’une autre ressource personnalisée) afin qu’une suppression liée à la confidentialité dans l’enregistrement de profil puisse également supprimer l’enregistrement de la ressource personnalisée liée contenant des informations personnelles. Les options de liaison et de suppression entre les entités doivent être configurées pour permettre cette suppression en cascade des enregistrements liés. Des informations personnelles ne doivent pas être saisies dans une ressource personnalisée qui n’est pas liée au profil.

## Opt-out{#opt-out}

En raison des différences dans les attributs d’opt-out entre Microsoft Dynamics 365 et Campaign, et des différences dans les besoins commerciaux de chaque client, le mapping d’opt-out a été laissé comme un exercice que le client doit terminer. Il est important de s’assurer que les opt-outs sont correctement mappés entre les systèmes afin que les préférences d’opt-out de l’utilisateur final soient préservées et qu’elles ne reçoivent pas de communication via un canal dont elles se sont désinscrites.

Sachez que seuls les éléments suivants peuvent être utilisés dans les mappings d’opt-out :

* les attributs Campaign avec le préfixe « Ne plus contacter par » (par ex., Ne plus contacter par email), ou

* l&#39;attribut spécifique du CCPA.

Vous trouverez plus d&#39;informations sur les champs d&#39;entité de profil [ici](../../developing/using/datamodel-profile.md).

Dans Dynamics 365, la plupart des champs d’opt-out ont le préfixe « donot », toutefois, vous pouvez également utiliser d’autres attributs personnalisés à des fins d’opt-out si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration d’opt-out dont vous avez besoin pour votre entreprise :

* **Unidirectionnelle (Microsoft Dynamics 365 vers Campaign)** : Dynamics 365 est une source de vérité pour les opt-outs. Les attributs d&#39;opt-out seront synchronisés dans un sens de Dynamics 365 vers Campaign Standard.
* **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** : Campaign Standard est la source de vérité pour les opt-outs. Les attributs d’opt-out seront synchronisés dans un sens, de Campaign Standard vers Dynamics 365.
* **Bidirectionnelle** : Dynamics 365 ET Campaign Standard sont deux sources de vérité. Les attributs d’opt-out seront synchronisés de façon bidirectionnelle entre Campaign Standard et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des opt-outs entre les systèmes, le flux de données d’opt-out de l’intégration peut être désactivé.

La configuration de désinscription bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes. La logique compare la date et l’heure entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut. Si Campaign contient la date et l’heure les plus récentes, alors la valeur Campaign prévaut. Si Dynamics 365 contient la date et l’heure les plus récentes ou identiques, alors opt-out=TRUE gagne (en supposant que l’une des valeurs soit TRUE).

Découvrez comment sélectionner les options d&#39;opt-out/opt-in dans [cette section](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les règles de typologie par défaut et spécifiques dans Adobe Campaign avant d’effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences de désinscription reflètent fidèlement les choix d’intention/de communication du destinataire et n’interrompent pas par inadvertance la diffusion d’une relation ou de messages transactionnels tels que les confirmations de commande client.

Si vous avez sélectionné la configuration d’opt-out **bidirectionnelle** ou **unidirectionnelle de Campaign vers Microsoft Dynamics 365**, les données d’opt-out Campaign seront régulièrement exportées via le workflow vers votre zone de stockage SFTP dans Campaign (voir « Utilisation du stockage SFTP dans Campaign » ci-dessous). Si vos workflows d’opt-out Campaign s’arrêtent, vous devrez les redémarrer manuellement dès que possible afin de réduire le risque de synchronisations d’opt-out manquées.

>[!IMPORTANT]
>
>Si vous avez besoin de la configuration d’opt-out **Bidirectionnelle** ou **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)**, vous devez adresser la demande à votre contact technique Adobe pour que les workflows d’opt-out soient configurés sur votre instance Campaign.

## Utilisation du stockage SFTP dans Campaign

Votre stockage SFTP dans Campaign devra être utilisé par l’intégration dans les cas pratiques ci-dessous.  Vous devez vous assurer que votre compte SFTP dispose d’une capacité de stockage suffisante pour prendre en charge ces cas pratiques. Le dépassement de la capacité de stockage SFTP sous licence peut nuire gravement à l’utilisation fonctionnelle de Campaign, à l’intégration et/ou au compte SFTP.

| Cas pratique | Description |
|---|---|
| Bidirectionnelle et unidirectionnelle (Campaign vers Microsoft Dynamics 365) | Les flux de données d’opt-out bidirectionnels et unidirectionnels (Campaign vers Microsoft Dynamics 365) utiliseront le stockage SFTP dans Campaign. Un workflow Campaign exportera les modifications incrémentales dans le dossier SFTP. À partir de là, l’intégration récupérera les enregistrements et les traitera. |
| Logs d’opt-out | Les logs de sortie du connecteur s’avèrent utiles lors du dépannage de l’intégration. Ils peuvent être activés/désactivés. |


>[!IMPORTANT]
>
>Vous êtes responsable des informations auxquelles vous accédez et que vous téléchargez à partir des dossiers SFTP. Si les informations contiennent des données personnelles, vous êtes tenu de respecter les lois et règlements applicables en matière de confidentialité. [En savoir plus](#acs-msdyn-manage-privacy).

## Gestion des données

### Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Microsoft Dynamics 365 vers Campaign. Les enregistrements Campaign créés en dehors de l’intégration (c.-à-d. non créés par le traitement de synchronisation) ne seront pas modifiés par l’intégration, y compris les enregistrements Campaign existants au moment de la configuration de l’intégration.

Comme cette intégration utilise le champ **[!UICONTROL externalId]** dans Campaign pour synchroniser les enregistrements de profil Campaign avec les enregistrements de contact Dynamics 365, ce champ Campaign (**[!UICONTROL externalId]**) doit être renseigné avec la valeur Microsoft Dynamics 365 **[!UICONTROL contactId]** pour les enregistrements que vous souhaitez synchroniser à partir de Microsoft Dynamics 365.  Les entités personnalisées sont également synchronisées à l’aide d’un identifiant unique Microsoft Dynamics 365. L’entité personnalisée Campaign devra inclure cet attribut d’identifiant dans une colonne de table. La colonne externalId peut être utilisée pour stocker cette valeur d’attribut, mais elle n’est pas requise pour les entités personnalisées Campaign.

N’oubliez pas que Microsoft Dynamics 365 reste la source de vérité et que les données de profil Campaign peuvent être écrasées lorsque l’intégration détecte les mises à jour du côté de Dynamics 365.  D’autres étapes peuvent également être nécessaires pour activer l’intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l’intégration.

### Fréquence de synchronisation des données

L’intégration utilise une architecture qui permet de détecter les mises à jour et de les ajouter à la « file d’attente » de traitement peu de temps après leur apparition dans Microsoft Dynamics 365 (c’est-à-dire, en diffusion, et non en traitement par lots). Pour cette raison, il n’est pas nécessaire de spécifier les fréquences ou les plannings d’exécution des flux de données.

L’exception à cette règle est le flux de données d’opt-out bidirectionnel et de Campaign vers Dynamics 365. Pour ces configurations d’opt-out, les enregistrements Campaign mis à jour sont exportés vers SFTP par le biais d’un workflow Campaign une fois par jour, après quoi l’outil d’intégration lit le fichier et traite l’enregistrement.

### Contrat d’utilisation des données

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux États-Unis dans le cadre de cette intégration. Voir à ce sujet [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Garde-fous et limitations

>[!IMPORTANT]
>
>Certaines actions de votre part (p.ex., l&#39;ingestion initiale des enregistrements, la relecture des données d&#39;enregistrement, etc.) peuvent entraîner une grande quantité d&#39;enregistrements ingérés de Microsoft Dynamics 365 vers votre instance Adobe Campaign. Pour limiter le risque de problèmes de performances, il est recommandé d’arrêter tous les processus Campaign (par exemple, aucune activité marketing, aucune exécution de workflows, etc.) jusqu&#39;à ce que la grande quantité d’enregistrements ait été ingérée dans Campaign.

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
   * Mises à jour d’enregistrement : 2 appels au moteur (un seul appel si l’enregistrement de destination est identique à l’enregistrement source, c’est-à-dire si aucun changement n’est apporté à l’enregistrement Campaign)

   Lors de l’estimation du volume global des appels au moteur Campaign, il est important de prendre en compte d’autres sources d’appels au moteur, notamment les landing pages, les WebApps, les JSSP, les API, les inscriptions aux applications mobiles, etc.

   Consultez des informations sur le package Campaign à cette adresse : https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html

* L’intégration prend en charge un maximum de 30 millions de contacts.

* L’offre d’intégration standard comprend la prise en charge de cinq entités personnalisées au maximum, chacune ayant une taille maximale de 50 colonnes.

* Vous devez créer et publier vos ressources personnalisées avant de mettre en œuvre l’intégration.

* La profondeur maximale de table lors de la liaison des tables est de deux (c’est-à-dire., table1->table2->table3).

* La prise en charge des types de données Microsoft Dynamics 365 est limitée. Si votre modèle de données contient un type de données autre que des types de données simples (par exemple, chaînes, entiers, décimales, etc.), vous devrez peut-être mettre à jour votre modèle de données avant d’utiliser l’intégration.

* Si vous choisissez de conserver les données existantes dans les entités personnalisées Campaign, vous devrez préparer les données pour l’intégration.

* Il peut être nécessaire d&#39;établir des fenêtres de maintenance pour l&#39;intégration entre Adobe et le client.

* Gardez à l’esprit que des augmentations importantes ou des « pics » dans l’utilisation de l’intégration (p.ex., une forte augmentation des enregistrements nouveaux ou mis à jour) peuvent entraîner des ralentissements dans la synchronisation des données.

* Dans le cadre de l’intégration, vous devrez exécuter les étapes de configuration préalable à l’intégration dans Microsoft Azure et Dynamics 365. Voir les étapes de configuration [sur cette page](../../integrating/using/d365-acs-configure-d365.md)

* Il est attendu que vous importerez vos modèles de données Dynamics 365 et Campaign dans l’intégration et que vous les gérerez.

### Limites de l’intégration

L’intégration a été conçue pour résoudre le cas pratique général du mouvement de données communes entre Microsoft Dynamics 365 et Campaign, mais elle n’est pas destinée à traiter chaque cas pratique spécifique à chaque client :

* ’intégration n’émet aucune suppression d’informations personnelles (ex. : RGPD). La responsabilité de répondre aux demandes d’accès à des informations personnelles des utilisateurs finaux incombe au client ; de telles demandes doivent être effectuées indépendamment à la fois dans Campaign (via Adobe Experience Platform Privacy Service) et dans Dynamics 365. L’intégration peut générer des suppressions régulières pour faciliter la synchronisation des données, si nécessaire.   Consultez [la section Confidentialité](#manage-privacy-requests) pour plus d&#39;informations.

* Aucune donnée de profil ou d’entité personnalisée ne sera synchronisée de Campaign vers Dynamics 365, à l’exception des informations d’opt-out (si elles sont configurées par le client).

* La gestion des abonnements Campaign (c’est-à-dire les abonnements/désabonnements) n’est pas prise en charge de manière native.

* La composition et le déclenchement de campagnes email Campaign à partir de Dynamics 365 ne sont pas pris en charge.

* L’intégration **ne prend pas** en charge la réorganisation des données entre les modèles de données Dynamics 365 et Campaign. Il est prévu que l’intégration synchronise une table Dynamics 365 avec une table Campaign.
