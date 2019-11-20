---
title: '"Cas d''utilisation du processus : Groupe de contrôle"'
seo-title: '"Cas d''utilisation du processus : Groupe de contrôle"'
description: '"Cas d''utilisation du processus : Groupe de contrôle"'
seo-description: '"Cas d''utilisation du processus : Groupe de contrôle"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2912e3b75b817347b832f9c89ca2320868cbc355

---


# Cas d’utilisation du flux de travail : Création d’un groupe de contrôle {#building-control-group}

Pour mesurer l’impact d’une diffusion, vous pouvez exclure certains profils de votre cible afin qu’ils ne reçoivent pas un message donné. Ce groupe de contrôle peut être utilisé pour comparer le comportement de la population cible qui a reçu le message.

Pour ce faire dans Adobe Campaign Standard, vous pouvez créer un flux de travaux comprenant les activités suivantes :
* Activité de requête pour cibler une population donnée.
* Activité de segmentation pour isoler un groupe de contrôle aléatoire de cette population.
* Activité de remise de courrier électronique pour envoyer un message à la cible principale.
* Une activité de données Update pour mettre à jour les profils qui ont été exclus de la cible (le groupe de contrôle aléatoire).

![](assets/wkf_control-group.png)

## Extension de la ressource de profil {#extending-profile}

Tout d’abord, vous devez étendre la ressource **[!UICONTROL Profil]** avec un nouveau champ correspondant au groupe de contrôle. Une fois le flux de travail exécuté, ce champ est vérifié pour les profils qui ont été exclus de la cible.

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, click **[!UICONTROL Create]**.
1. Si vous ne l’avez pas encore étendu, sélectionnez **[!UICONTROL Étendre une ressource]** existante et choisissez la ressource **[!UICONTROL Profil]** .
1. Dans l’onglet Structure **[!UICONTROL des]** données, ajoutez un nouveau champ pour le groupe de contrôle et sélectionnez **[!UICONTROL Boolean]** pour le champ **[!UICONTROL Type]** .

   ![](assets/wkf_control-group-profile-field.png)

1. Dans l’onglet Définition **** d’écran, dépliez la section Configuration **[!UICONTROL de l’écran]** des détails et sélectionnez le champ que vous venez de créer afin qu’il s’affiche pour chaque profil.

   ![](assets/wkf_control-group-profile-field-screen.png)

1. Enregistrez vos modifications.
1. Mettez à jour la structure de la base de données pour publier la ressource étendue **[!UICONTROL Profile]** . See [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

Pour plus d’informations sur l’extension d’une ressource personnalisée, voir Procédure [clé pour ajouter une ressource](../../developing/using/key-steps-to-add-a-resource.md).

## Créer un workflow {#creating-a-workflow}

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur **[!UICONTROL Créer]** et sélectionnez **[!UICONTROL Workflow]**.
1. Sélectionnez **[!UICONTROL Nouveau workflow]** en tant que type de workflow et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés du workflow, puis cliquez sur **[!UICONTROL Créer]**.

Les étapes détaillées pour créer un flux de travail sont présentées dans la section [Création d’un flux de travail](../../automating/using/building-a-workflow.md) .

## Créer une activité Requête {#create-a-query-activity}

1. Dans **[!UICONTROL Activités]** &gt; **[!UICONTROL Ciblage]**, effectuez un glisser-déposer d'une activité **[!UICONTROL Requête]**.
1. Cliquez deux fois sur l’activité pour définir votre cible.
1. Par exemple, dans **[!UICONTROL Raccourcis]**, faites glisser et déposez le **[!UICONTROL profil]**, sélectionnez **[!UICONTROL Age]** avec l’opérateur **[!UICONTROL Supérieur à et saisissez 25 dans le champ Value.]******
1. Cliquez sur **[!UICONTROL Confirmer]**.

Les étapes détaillées pour créer une activité de requête sont présentées dans la section [Requête](../../automating/using/query.md) .

## Créer une activité Segmentation {#creating-a-segmentation-activity}

1. Effectuez un glisser-déposer d'une activité **[!UICONTROL Segmentation]** et double-cliquez dessus.
1. Dans l’onglet **[!UICONTROL Segments]** , sélectionnez un segment à modifier.
1. Dans l’onglet **[!UICONTROL Configuration]** de ce segment, sélectionnez l’option **[!UICONTROL Limiter la population de ce segment]** .

   ![](assets/wkf_control-segment-configuration.png)

1. Dans l’onglet **[!UICONTROL Limitation]** , vérifiez que l’option d’échantillonnage **** aléatoire est sélectionnée.

   ![](assets/wkf_control-segment-limitation.png)

1. Définissez un pourcentage de la population initiale, par exemple 10 %, puis cliquez sur **[!UICONTROL Confirmer]**. Le groupe témoin sera constitué de 10 % de la population ciblée, choisis au hasard.
1. Dans l’onglet Options **** avancées, sélectionnez l’option **[!UICONTROL Générer le complément]** et renseignez les champs Libellé **[!UICONTROL de]** transition et Code de **[!UICONTROL segment.]**

   ![](assets/wkf_control-segment-advanced.png)

1. Cliquez sur **[!UICONTROL Confirmer]**.

Les étapes détaillées pour créer une activité de segmentation sont présentées dans la section [Segmentation](../../automating/using/segmentation.md) .

## Création d’une activité de courrier électronique {#creating-an-email-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, drag and drop an **[!UICONTROL Email Delivery]** after the main target segment.
1. Click the activity and select ![](assets/edit_darkgrey-24px.png) to edit it.
1. Sélectionnez **[!UICONTROL Email unique]** et cliquez sur **[!UICONTROL Suivant]**.
1. Sélectionnez un modèle d'email et cliquez sur **[!UICONTROL Suivant]**.
1. Saisissez les propriétés de l'email et cliquez sur **[!UICONTROL Suivant]**.
1. To create the layout of your email, click on **[!UICONTROL Use the Email Designer]**.
1. Modifiez et enregistrez votre contenu.
1. Dans la section **[!UICONTROL Planifier]** du tableau de bord du message, désélectionnez l' **[!UICONTROL Request confirmation avant d'envoyer des messages}** .

Les étapes détaillées pour créer une activité de courrier électronique sont présentées dans la section Livraison [par](../../automating/using/email-delivery.md) courrier électronique.

## Création d’une activité de données de mise à jour {#creating-update-data-activity}

1. Faites glisser et déposez une activité de données **** Update après le segment du groupe de contrôle.
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s'affichent.
1. Dans l’onglet **[!UICONTROL Général]** , sélectionnez **[!UICONTROL Mettre à jour]** dans la liste déroulante Type **[!UICONTROL d’]** opération.
1. Dans l’onglet **[!UICONTROL Identification]** , sélectionnez l’option **[!UICONTROL Directement à l’aide de la dimension]** de ciblage.
1. Sélectionnez la ressource de **[!UICONTROL profil]** que vous avez précédemment étendue comme dimension à mettre à jour.

   ![](assets/wkf_control-update-identification.png)

1. Dans l’onglet **[!UICONTROL Champs à mettre à jour]** , sélectionnez le champ de groupe de contrôle que vous avez ajouté à la ressource **[!UICONTROL Profil]** en tant que **[!UICONTROL destination]** et saisissez true comme condition.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Cliquez sur **[!UICONTROL Confirmer]**.

Les étapes détaillées pour créer une activité de données de mise à jour sont présentées dans la section [Mettre à jour les données](../../automating/using/update-data.md) .

## Exécution du processus {#running-the-workflow}

Click **[!UICONTROL Start]** to run the workflow.

Une fois le processus exécuté, la population du groupe de contrôle est exclue et le message est envoyé à la cible principale restante.

La ressource **[!UICONTROL Profil]** est mise à jour comme suit : si un profil se trouvait dans le groupe de contrôle, le champ correspondant est coché.

![](assets/wkf_control-group-profile-checked.png)

Vous pouvez maintenant comparer la réaction des destinataires du message par rapport au petit groupe qui a été exclu du message et ne l’a pas reçu.

## Réutilisation du même groupe de contrôle {#reusing-same-control-group}

L’exemple ci-dessus permet de créer un groupe de contrôle global, car il est stocké en tant qu’attribut de profil indépendamment des livraisons. En effet, le nouveau champ "Groupe de contrôle" créé dans le cadre de l’extension de ressource **[!UICONTROL Profil]** est mis à jour après l’exécution du processus ci-dessus.

Par conséquent, la prochaine fois que vous souhaitez utiliser le même groupe de contrôle, vous pouvez segmenter sur le nouveau champ "Groupe de contrôle" plutôt que d’effectuer une segmentation aléatoire.

Pour cela :
1. Lors de la création de l’activité **[!UICONTROL Segmentation]** , sélectionnez le segment à modifier dans l’onglet **[!UICONTROL Segments]** .
1. Dans l’onglet **[!UICONTROL Configuration]** de ce segment, veillez à ne pas sélectionner l’option **[!UICONTROL Limiter la population de ce segment]** .
1. Dans l’onglet **[!UICONTROL Filtrage]** , faites glisser **[!UICONTROL Profils (attributs)]** vers l’espace de travail principal.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. Dans la fenêtre **[!UICONTROL Ajouter une règle - Profils (attributs)]** , sélectionnez "Groupe de contrôle" (le champ que vous avez ajouté à la ressource **[!UICONTROL Profil]** ) et sélectionnez **[!UICONTROL Oui]** comme condition de filtre.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)