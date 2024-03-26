---
title: Gestion des données dans Campaign et Microsoft Dynamics 365
description: Découvrez comment Campaign Standard et Microsoft Dynamics 365 gèrent les données communes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2526'
ht-degree: 100%

---

# Bonnes pratiques et limites {#acs-msdyn-best-practices}

## Gestion des données {#acs-msdyn-manage-data}

En ce qui concerne la synchronisation des contacts et des entités personnalisées, cette intégration traite **Microsoft Dynamics 365 comme la source de vérité**. Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365 et et non dans Adobe Campaign Standard). Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées dans Campaign pendant la synchronisation, car la synchronisation est unidirectionnelle.

L&#39;intégration peut être facultativement configurée pour émettre des appels de suppression de profil vers Campaign lorsqu&#39;un contact est supprimé dans Dynamics 365, afin de préserver l&#39;intégrité des données. Cependant, une suppression de profil est différente d&#39;une suppression des informations personnelles. Une suppression des informations personnelles dans Campaign supprimera l&#39;enregistrement du profil Campaign et les entrées de log associées ; alors qu&#39;une suppression du profil normale ne fera que supprimer l&#39;enregistrement du profil Campaign, laissant des traces dans les logs Campaign. Si la fonction de suppression du profil est activée dans l’intégration, il sera nécessaire de suivre d’autres étapes pour traiter correctement les demandes d’accès à des informations personnelles provenant du titulaire de données. Reportez-vous aux étapes de la [Confidentialité section ci-dessous](#manage-privacy-requests).

## Confidentialité{#acs-msdyn-manage-privacy}

Cette intégration est conçue pour transférer des données d&#39;utilisateur final entre Microsoft Dynamics 365 et Adobe Campaign Standard. Ces données comprennent des informations personnelles si elles sont contenues dans vos données d&#39;utilisateur final. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

Cette intégration a pour but de transférer les données des utilisateurs finaux (notamment les informations personnelles, lesquelles sont dans les données des utilisateurs finaux) entre Microsoft Dynamics 365 et Adobe Campaign Standard. En tant que contrôleur de données, votre société est tenue de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

L’intégration n’émet pas de demandes de suppression relatives aux informations personnelles des titulaires de données (RGPD, par exemple) et ne traitent pas d’autres demandes d’accès à des informations personnelles (à l’exception du processus d’opt-out). Lorsque vous traitez des demandes d&#39;accès à des informations personnelles, vous devez le faire indépendamment dans Microsoft Dynamics 365 et Campaign (via Adobe Experience Platform Privacy Service).

Si vous avez configuré l&#39;intégration pour émettre des appels de suppression de profil classiques à Campaign lorsqu&#39;un contact est supprimé dans Dynamics 365, suivez les étapes ci-dessous. Vérifiez qu&#39;aucune mise à jour n&#39;est effectuée sur l&#39;enregistrement concerné au cours de ce processus.

1. Émettre une demande de suppression des informations personnelles à [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Surveiller la demande jusqu&#39;à ce qu&#39;elle soit terminée

1. Vérifier que l&#39;enregistrement ne se trouve plus dans votre instance Campaign

1. (Peu après) Émettre la suppression des informations personnelles dans Dynamics 365

1. Vérifier que l&#39;enregistrement a été supprimé des deux systèmes


>[!IMPORTANT]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, applicables à l&#39;utilisation de Campaign par un client, il doit être lié à un enregistrement de profil Campaign correspondant (soit directement, soit par l&#39;intermédiaire d&#39;une autre ressource personnalisée) afin qu&#39;une suppression liée à la confidentialité dans l&#39;enregistrement de profil puisse également supprimer l&#39;enregistrement de la ressource personnalisée liée contenant des informations personnelles. Les options de liaison et de suppression entre les entités doivent être configurées pour permettre cette suppression en cascade des enregistrements liés. Des informations personnelles ne doivent pas être saisies dans une ressource personnalisée qui n&#39;est pas liée au profil.

## Désinscription (opt-out) {#opt-out}

En raison des différences dans les attributs d&#39;opt-out entre Microsoft Dynamics 365 et Campaign, et des différences dans les besoins commerciaux de chaque client, le mapping d&#39;opt-out a été laissé comme un exercice que le client doit terminer. Il est important de s&#39;assurer que les opt-outs sont correctement mappés entre les systèmes afin que les préférences d&#39;opt-out de l&#39;utilisateur final soient préservées et qu&#39;elles ne reçoivent pas de communication via un canal dont elles se sont désinscrites.

Sachez que seuls les éléments suivants peuvent être utilisés dans les mappings d&#39;opt-out :

* les attributs Campaign avec le préfixe &quot;Ne plus contacter par&quot; (par ex., Ne plus contacter par e-mail), ou

* l&#39;attribut spécifique du CCPA.

Vous trouverez plus d&#39;informations sur les champs d&#39;entité de profil [ici](../../developing/using/datamodel-profile.md).

Dans Dynamics 365, la plupart des champs d&#39;opt-out ont le préfixe &quot;donot&quot;, toutefois, vous pouvez également utiliser d&#39;autres attributs personnalisés à des fins d&#39;opt-out si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration d’opt-out dont vous avez besoin pour votre entreprise :

* **Unidirectionnelle (Microsoft Dynamics 365 vers Campaign)** : Dynamics 365 est une source de vérité pour les opt-outs. Les attributs d&#39;opt-out seront synchronisés dans un sens de Dynamics 365 vers Campaign Standard.
* **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)** : Campaign Standard est la source de vérité pour les opt-outs. Les attributs d’opt-out seront synchronisés dans un sens, de Campaign Standard vers Dynamics 365.
* **Bidirectionnelle** : Dynamics 365 ET Campaign Standard sont deux sources de vérité. Les attributs d’opt-out seront synchronisés de façon bidirectionnelle entre Campaign Standard et Dynamics 365

Si vous disposez également d&#39;un processus distinct pour gérer la synchronisation des opt-outs entre les systèmes, le flux de données d&#39;opt-out de l&#39;intégration peut être désactivé.

La configuration d&#39;opt-out bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes. La logique compare la date et l&#39;heure entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut. Si Campaign contient la date et l&#39;heure les plus récentes, alors la valeur Campaign prévaut. Si Dynamics 365 contient la date et l&#39;heure les plus récentes ou identiques, alors opt-out=TRUE gagne (en supposant que l&#39;une des valeurs soit TRUE).

Découvrez comment sélectionner les options d&#39;opt-out/opt-in dans [cette section](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les règles de typologie par défaut et spécifiques dans Adobe Campaign avant d&#39;effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences d&#39;opt-out reflètent fidèlement les choix d&#39;intention/de communication du destinataire et n&#39;interrompent pas par inadvertance la diffusion d&#39;une relation ou de messages transactionnels tels que les confirmations de commande client.

Si vous avez sélectionné la configuration d’opt-out **bidirectionnelle** ou **unidirectionnelle de Campaign vers Microsoft Dynamics 365**, les données d’opt-out Campaign seront régulièrement exportées via le workflow vers votre zone de stockage SFTP dans Campaign (voir « Utilisation du stockage SFTP dans Campaign » ci-dessous). Si vos workflows d&#39;opt-out Campaign s&#39;arrêtent, vous devrez les redémarrer manuellement dès que possible afin de réduire le risque de synchronisations d&#39;opt-out manquées.

>[!IMPORTANT]
>
>Si vous avez besoin de la configuration d&#39;opt-out **Bidirectionnelle** ou **Unidirectionnelle (Campaign vers Microsoft Dynamics 365)**, vous devez adresser la demande à votre contact technique Adobe pour que les workflows d&#39;opt-out soient configurés sur votre instance Campaign.

## Utilisation du stockage SFTP dans Campaign

Votre stockage SFTP dans Campaign devra être utilisé par l’intégration dans les cas pratiques ci-dessous.  Vous devez vous assurer que votre compte SFTP dispose d’une capacité de stockage suffisante pour prendre en charge ces cas pratiques. Le dépassement de la capacité de stockage SFTP sous licence peut nuire gravement à l&#39;utilisation fonctionnelle de Campaign, à l&#39;intégration et/ou au compte SFTP.

| Cas pratique | Description |
|---|---|
| Bidirectionnelle et unidirectionnelle (Campaign vers Microsoft Dynamics 365) | Les flux de données d’opt-out bidirectionnels et unidirectionnels (Campaign vers Microsoft Dynamics 365) utiliseront le stockage SFTP dans Campaign. Un workflow Campaign exportera les modifications incrémentales dans le dossier SFTP. À partir de là, l&#39;intégration récupérera les enregistrements et les traitera. |
| Logs d&#39;opt-out | Les logs de sortie du connecteur s&#39;avèrent utiles lors du dépannage de l&#39;intégration. Ils peuvent être activés/désactivés. |


>[!IMPORTANT]
>
>Vous êtes responsable des informations auxquelles vous accédez et que vous téléchargez à partir des dossiers SFTP. Si les informations contiennent des données personnelles, vous êtes tenu de respecter les lois et règlements applicables en matière de confidentialité. [En savoir plus](#acs-msdyn-manage-privacy).

## Gestion des données

### Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Microsoft Dynamics 365 vers Campaign. Les enregistrements Campaign créés en dehors de l&#39;intégration (c.-à-d. non créés par le traitement de synchronisation) ne seront pas modifiés par l&#39;intégration, y compris les enregistrements Campaign existants au moment de la configuration de l&#39;intégration.

Comme cette intégration utilise le champ **[!UICONTROL externalId]** dans Campaign pour synchroniser les enregistrements de profil Campaign avec les enregistrements de contact Dynamics 365, ce champ Campaign (**[!UICONTROL externalId]**) doit être renseigné avec la valeur Microsoft Dynamics 365 **[!UICONTROL contactId]** pour les enregistrements que vous souhaitez synchroniser à partir de Microsoft Dynamics 365.  Les entités personnalisées sont également synchronisées à l&#39;aide d&#39;un identifiant unique Microsoft Dynamics 365. L&#39;entité personnalisée Campaign devra inclure cet attribut d&#39;identifiant dans une colonne de table. La colonne externalId peut être utilisée pour stocker cette valeur d&#39;attribut, mais elle n&#39;est pas requise pour les entités personnalisées Campaign.

N&#39;oubliez pas que Microsoft Dynamics 365 reste la source de vérité et que les données de profil Campaign peuvent être écrasées lorsque l&#39;intégration détecte les mises à jour du côté de Dynamics 365.  D&#39;autres étapes peuvent également être nécessaires pour activer l&#39;intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l&#39;intégration.

### Fréquence de synchronisation des données

L&#39;intégration utilise une architecture qui permet de détecter les mises à jour et de les ajouter à la &quot;file d&#39;attente&quot; de traitement peu de temps après leur apparition dans Microsoft Dynamics 365 (c&#39;est-à-dire, en diffusion, et non en traitement par lots). Pour cette raison, il n&#39;est pas nécessaire de spécifier les fréquences ou les plannings d&#39;exécution des flux de données.

L&#39;exception à cette règle est le flux de données d&#39;opt-out bidirectionnel et de Campaign vers Dynamics 365. Pour ces configurations d’opt-out, les enregistrements Campaign mis à jour sont exportés vers SFTP par le biais d’un workflow Campaign une fois par jour, après quoi l’outil d’intégration lit le fichier et traite l’enregistrement.

### Contrat d&#39;utilisation des données

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux États-Unis dans le cadre de cette intégration. Pour plus d’informations, consultez [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Limites et mécanismes de sécurisation

>[!IMPORTANT]
>
>Certaines actions de votre part (p.ex., l&#39;ingestion initiale des enregistrements, la relecture des données d&#39;enregistrement, etc.) peuvent entraîner une grande quantité d&#39;enregistrements ingérés de Microsoft Dynamics 365 vers votre instance Adobe Campaign. Pour limiter le risque de problèmes de performances, il est recommandé d&#39;arrêter tous les processus Campaign (par exemple, aucune activité marketing, aucune exécution de workflows, etc.) jusqu&#39;à ce que la grande quantité d&#39;enregistrements ait été ingérée dans Campaign.

### Entités personnalisées

L’[intégration Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) prend en charge les entités personnalisées, ce qui permet de synchroniser les entités personnalisées de Dynamics 365 avec les ressources personnalisées correspondantes dans Campaign.

L&#39;intégration prend en charge les tables liées et non liées.

Lors de la configuration des flux de données d&#39;entités personnalisées, il est important de tenir compte des points suivants :

* La création et la modification de ressources personnalisées Campaign sont des opérations délicates qui doivent être effectuées uniquement par des utilisateurs experts.
* Pour les flux de données d&#39;entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.
* Si un enregistrement parent et et un enregistrement enfant lié sont créés presque au même moment dans Dynamics 365, en raison du traitement parallèle de l&#39;intégration, il peut arriver qu&#39;un nouvel enregistrement enfant soit créé dans Campaign avant l&#39;enregistrement de son parent.

* Si les enregistrements parent et enfant sont liés du côté Campaign à l&#39;aide de l&#39;option **Lien simple de cardinalité 1**, l&#39;enregistrement enfant reste masqué et inaccessible (via l&#39;interface utilisateur ou l&#39;API) jusqu&#39;à ce que l&#39;enregistrement parent arrive dans Campaign.

* (En supposant que le **lien simple de cardinalité 1** est présent dans Campaign) Si l&#39;enregistrement enfant est mis à jour ou supprimé dans Dynamics 365 et que cette modification est écrite dans Campaign avant que l&#39;enregistrement parent ne s&#39;affiche dans Campaign (ce qui est peu probable, mais qui peut parfois arriver), cette mise à jour ou suppression ne sera pas traitée dans Campaign et une erreur sera générée. Dans le cas d&#39;une mise à jour, l&#39;enregistrement en question devra de nouveau être mis à jour dans Dynamics 365 pour synchroniser l&#39;enregistrement mis à jour. Dans le cas de la suppression, l&#39;enregistrement en question devra être pris en charge séparément du côté Campaign, car il n&#39;y aura plus d&#39;enregistrement dans Dynamics 365 à supprimer ou à mettre à jour.

* Si vous vous trouvez dans une situation où vous pensez avoir masqué des enregistrements enfants sans avoir aucun moyen d&#39;y accéder, vous pouvez temporairement changer le type de lien de cardinalité en **lien simple de cardinalité 0 ou 1** pour accéder à ces enregistrements.

Vous trouverez une présentation plus exhaustive des ressources personnalisées de Campaign dans [cette section](../../developing/using/key-steps-to-add-a-resource.md).

### Mécanismes de sécurisation de l&#39;intégration

Les mécanismes de sécurisation suivants doivent être pris en compte lors de la planification de l&#39;utilisation de cette intégration. Consultez votre représentant technique Adobe si vous pensez que vous ne respectez pas ces mécanismes de sécurisation.

* Vous devez activer la licence du package Campaign approprié pour prendre en charge le volume d&#39;appels au moteur généré par l&#39;intégration. Le dépassement du volume d&#39;appels du moteur sous licence peut entraîner une baisse des performances de Campaign.

  Utilisez les éléments suivants pour estimer le volume d&#39;appels au moteur à partir de l&#39;intégration :

   * Insertions d&#39;enregistrements (c&#39;est-à-dire, nouvel enregistrement) : 1 appel au moteur
   * Suppressions d&#39;enregistrements : 1 appel au moteur
   * Mises à jour d&#39;enregistrement : 2 appels au moteur (un seul appel si l&#39;enregistrement de destination est identique à l&#39;enregistrement source, c&#39;est-à-dire si aucun changement n&#39;est apporté à l&#39;enregistrement Campaign)

  Lors de l&#39;estimation du volume global des appels au moteur Campaign, il est important de prendre en compte d&#39;autres sources d&#39;appels au moteur, notamment les landing pages, les WebApps, les JSSP, les API, les inscriptions aux applications mobiles, etc.

  [Consultez des informations sur le package Adobe Campaign Standard ici : https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html)

* L&#39;intégration prend en charge un maximum de 15 millions d&#39;enregistrements au total pour la synchronisation initiale avec les ressources dans Campaign. La synchronisation incrémentielle est limitée par le package Adobe Campaign Standard.

* L&#39;offre d&#39;intégration standard comprend la prise en charge de vingt entités personnalisées au maximum, chacune d&#39;elles d&#39;une taille maximale de 50 colonnes.

* Vous devez créer et publier vos ressources personnalisées avant de mettre en œuvre l&#39;intégration.

* La profondeur maximale de table lors de la liaison des tables est de deux (c&#39;est-à-dire., table1->table2->table3).

* L&#39;intégration prend en charge jusqu&#39;à 5 colonnes liées par ressource personnalisée. La liaison de plusieurs colonnes entre des ressources personnalisées peut avoir des répercussions considérables sur les performances. **Le lien simple de cardinalité 0 ou 1** est préférable au **lien simple de cardinalité 1**.

* L&#39;intégration prend en charge la transformation entre les types de données Microsoft Dynamics 365 primitifs (booléen, entier, décimal, double, chaîne, date et heure, date) et les types de données Adobe Campaign Standard (entier, booléen, flottant, double, date, date et heure, chaîne). Les types de données plus avancés sont interprétés comme des chaînes et synchronisés en l&#39;état.

* Il peut être nécessaire d&#39;établir des fenêtres de maintenance pour l&#39;intégration entre Adobe et le client.

* Gardez à l&#39;esprit que des augmentations importantes ou des &quot;pics&quot; dans l&#39;utilisation de l&#39;intégration (p.ex., une forte augmentation des enregistrements nouveaux ou mis à jour) peuvent entraîner des ralentissements dans la synchronisation des données.

* Dans le cadre de l&#39;intégration, vous devrez exécuter les étapes de configuration préalable à l&#39;intégration dans Microsoft Azure et Dynamics 365. Voir les étapes de configuration [sur cette page](../../integrating/using/d365-acs-configure-d365.md)

* Il est attendu que vous importerez vos modèles de données Dynamics 365 et Campaign dans l&#39;intégration et que vous les gérerez.

### Limites de l&#39;intégration

L&#39;intégration a été conçue pour résoudre le cas pratique général du mouvement de données communes entre Microsoft Dynamics 365 et Campaign, mais elle n&#39;est pas destinée à traiter chaque cas pratique spécifique à chaque client :

* ’intégration n’émet aucune suppression d’informations personnelles (ex. : RGPD). La responsabilité de répondre aux demandes d&#39;accès à des informations personnelles des utilisateurs finaux incombe au client ; de telles demandes doivent être effectuées indépendamment à la fois dans Campaign (via Adobe Experience Platform Privacy Service) et dans Dynamics 365. L&#39;intégration peut générer des suppressions régulières pour faciliter la synchronisation des données, si nécessaire.   Consultez [la section Confidentialité](#manage-privacy-requests) pour plus d&#39;informations.

* Aucune donnée de profil ou d&#39;entité personnalisée ne sera synchronisée de Campaign vers Dynamics 365, à l&#39;exception des informations d&#39;opt-out (si elles sont configurées par le client).

* La gestion des abonnements Campaign (c&#39;est-à-dire les abonnements/désabonnements) n&#39;est pas prise en charge de manière native.

* La composition et le déclenchement de campagnes e-mail Campaign à partir de Dynamics 365 ne sont pas pris en charge.

* L&#39;intégration **ne prend pas** en charge la réorganisation des données entre les modèles de données Dynamics 365 et Campaign. Il est prévu que l&#39;intégration synchronise une table Dynamics 365 avec une table Campaign.
