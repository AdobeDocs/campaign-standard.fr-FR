---
title: Partage d'audiences avec Audience Manager ou People core service
description: Découvrez comment importer ou exporter votre audience au sein des différentes solutions d'Adobe Experience Cloud.
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '854'
ht-degree: 100%

---


# Partage d&#39;audiences avec Audience Manager ou People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importer une audience {#importing-an-audience}

L&#39;intégration de People core service permet d&#39;importer directement une audience dans Adobe Campaign via un workflow technique afin d&#39;enrichir votre base de données. Pour plus d&#39;informations sur le partage d&#39;audiences dans People core service, consultez cette [documentation](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

L&#39;import des audiences/segments depuis People core service dans Adobe Campaign peut être effectué à partir du menu **[!UICONTROL Audiences]** uniquement par les utilisateurs connectés via IMS (authentification via l&#39;Adobe ID).

1. Accédez au menu **[!UICONTROL Audiences]**.
1. Depuis la barre d&#39;actions, sélectionnez **[!UICONTROL Créer]** pour accéder à l&#39;écran de création d&#39;une audience.
1. Indiquez le libellé de la nouvelle audience.
1. Paramétrez le **[!UICONTROL Type]** de l&#39;audience sur **[!UICONTROL Experience Cloud]** afin d&#39;indiquer que l&#39;audience en cours de création est une audience importée depuis People core service.
1. Depuis le champ **[!UICONTROL Nom de l&#39;audience partagée]**, sélectionnez l&#39;audience à importer. Seuls les segments peuvent être importés. Les données granulaires, notamment les paires clé-valeur, les caractéristiques et les règles ne sont pas prises en charge.

   ![](assets/aam_import_audience.png)

1. Sélectionnez la **[!UICONTROL Data source partagée correspondante]**.

   Si la source de données sélectionnée est configurée pour utiliser un algorithme de cryptage, une option supplémentaire offre la possibilité de **[!UICONTROL Forcer la réconciliation avec un profil]**. Cochez cette option si le champ **[!UICONTROL Canal]** de la source de données est défini sur Email ou Mobile (SMS) et si vous voulez utiliser les données de profil.

   Si vous ne sélectionnez pas l&#39;option **[!UICONTROL Forcer la réconciliation avec un profil]** et si le champ **[!UICONTROL Canal]** est défini dans l&#39;AMC Data source sur Email ou Mobile (SMS), tous les identifiants Declared ID cryptés sont décryptés. Une audience de type **Fichier** avec la liste de toutes les adresses email et de tous les numéros de téléphone mobile est créée/mise à jour. Ainsi, aucune adresse email ni aucun numéro de téléphone mobile n&#39;est perdu lors de l&#39;import d&#39;une audience partagée via cette intégration, et ce même si ce profil n&#39;existe pas dans Campaign. Ces types d&#39;audience ne peuvent pas être utilisés directement car ils doivent être réconciliés manuellement à l&#39;aide de workflows.

1. Validez la création de l&#39;audience.

   L&#39;audience est ensuite importée à l&#39;aide d&#39;un workflow technique. Elle est composée des enregistrements dont l&#39;identifiant (Visitor ID ou Declared ID) a pu être réconcilié avec la dimension des profils. Les identifiants provenant des segments de People core service non reconnus par Adobe Campaign ne sont pas importés.

Votre audience est maintenant importée dans votre base de données Adobe Campaign. Le processus d&#39;import prend entre 24 et 36 heures pour se synchroniser lorsque les segments sont importés directement à partir de People core service ou d&#39;Audience Manager. Au terme de cette période, vous pourrez trouver et utiliser votre nouvelle audience dans Adobe Campaign.

>[!NOTE]
>
>Si vous importez des audiences d&#39;Adobe Analytics vers Adobe Campaign, celles-ci doivent être partagées au préalable dans People Core Service ou Audience Manager. Ce processus prend entre 12 et 24 heures, en plus des 24 à 36 heures de synchronisation avec Campaign. Dans ce cas spécifique, l&#39;échéance de partage d&#39;audience peut aller jusqu&#39;à 60 heures. Pour plus d&#39;informations sur le partage d&#39;audience Adobe Analytics dans People Core service et Audience manager, consultez cette [documentation](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## Exporter une audience {#exporting-an-audience}

L&#39;export d&#39;une audience depuis Adobe Campaign vers Audience Manager ou People core service peut être réalisé à l&#39;aide d&#39;un workflow et de l&#39;activité de **[!UICONTROL Sauvegarde d&#39;audience]**.

Il peut être réalisé dans un nouveau workflow par les utilisateurs connectés via IMS uniquement (authentification via l&#39;Adobe ID).

1. Créez un workflow à partir d&#39;un programme, d&#39;une campagne ou de la liste des activités marketing.
1. En utilisant les différentes activités à votre disposition, ciblez un ensemble de profils.
1. A la suite du ciblage, placez une activité **[!UICONTROL Sauvegarde d&#39;audience]** puis ouvrez-la.
1. Sélectionnez **[!UICONTROL Partager dans Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Définissez l&#39;audience à l&#39;aide du champ **[!UICONTROL Audience partagée]**. Dans la fenêtre qui s&#39;ouvre, vous pouvez sélectionner une audience existante ou créer une nouvelle audience :

   * Si vous sélectionnez une audience existante, seuls les nouveaux enregistrements seront ajoutés à l&#39;audience.
   * Pour exporter votre liste de profils dans une nouvelle audience, renseignez le champ **[!UICONTROL Nom de segment]** puis cliquez sur **[!UICONTROL Créer]** avant de sélectionner l&#39;audience nouvellement créée.

   ![](assets/aam_save_audience_segment_picker.png)

   Pour pouvoir être réconciliés et échangés, les enregistrements doivent posséder un identifiant Adobe Experience Cloud (&#39;Visitor ID&#39; ou &#39;Declared ID&#39;). Les enregistrements non réconciliés sont ignorés lors des exports et des imports d&#39;audiences.

1. Terminez l&#39;opération à l&#39;aide de la coche de validation située en haut à droite de la fenêtre.
1. Sélectionnez la **[!UICONTROL Data source partagée correspondante]**.
1. Si vous le souhaitez, cochez la case **[!UICONTROL Générer une transition sortante]** afin d&#39;exploiter les profils ayant pu être exportés. Seuls les profils pouvant être réconciliés sont exportés.
1. Validez la configuration de l&#39;activité et enregistrez votre workflow.
1. Démarrez votre workflow pour exporter votre audience. La synchronisation entre Adobe Campaign et People core service peut prendre plusieurs heures.

La synchronisation entre Adobe Campaign et People core service prend entre 24 et 36 heures. Au terme de cette période, vous pourrez trouver votre nouvelle audience dans People core service et la réutiliser dans d&#39;autres solutions Adobe Experience Cloud. Pour plus d&#39;informations sur l&#39;utilisation d&#39;une audience partagée Adobe Campaign dans Adobe People core service, consultez cette [documentation](https://docs.adobe.com/content/help/fr-FR/core-services/interface/audiences/t-audience-create.html).

**Rubriques connexes :**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Audiences](../../audiences/using/about-audiences.md)

