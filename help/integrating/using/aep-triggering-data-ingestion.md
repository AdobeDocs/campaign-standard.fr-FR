---
title: Déclenchement de l'ingestion des données via les API
description: Découvrez comment déclencher l'ingestion des données par le biais des API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 100%

---

# Déclenchement de l&#39;ingestion des données via les API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version bêta et peut être fréquemment mis à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta en Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez l’assistance clientèle d’Adobe si vous souhaitez y accéder.

Adobe Campaign Standard permet de déclencher l&#39;ingestion immédiate des mappings de données par le biais des API et de récupérer le statut de vos demandes d&#39;ingestion.

Cette page décrit comment déclencher et récupérer le statut de l&#39;ingestion de vos mappings de données. Pour des informations globales sur les API de Campaign Standard, consultez [cette section](../../api/using/get-started-apis.md).

## Conditions préalables requises {#prerequisites}

Avant d&#39;utiliser les API, le mapping de données doit avoir été configuré et publié dans l&#39;interface de Campaign Standard. Voir à ce propos les sections suivantes :

* [Définition d&#39;un mapping](../../integrating/using/aep-mapping-definition.md)
* [Activation du mapping](../../integrating/using/aep-mapping-activation.md)

Une fois le mapping de données créé, vous devez l&#39;arrêter afin de pouvoir le déclencher à votre convenance depuis les API. Pour ce faire, procédez comme suit :

1. Dans Campaign Standard, accédez au menu **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Statut de l&#39;export des données vers Platform.]**

1. Double-cliquez sur le mapping de données pour l&#39;ouvrir, puis cliquez sur le bouton **[!UICONTROL Arrêter]**.

   ![](assets/aep_datamapping_stop.png)

1. Enregistrez vos modifications

L&#39;exécution du mapping de données est arrêtée. Vous pouvez utiliser les API de Campaign Standard pour le déclencher manuellement.

## Démarrage de l&#39;ingestion immédiate des données {#starting-immediate-ingestion}

L&#39;ingestion immédiate d&#39;un mapping XDM dans Adobe Experience Platform est déclenchée par une opération POST :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Pour exécuter l&#39;appel d&#39;API POST d&#39;ingestion, l&#39;utilisateur doit disposer d&#39;un rôle d&#39;**exécution de fonction SQL**. Ce rôle peut être attribué par un administrateur de Campaign Standard en exécutant le Script JS suivant :
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

L&#39;opération POST renvoie des informations concernant le statut de la demande créée :

* Demande envoyée avec succès pour le mapping XDM :

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Demande déjà en cours pour le mapping XDM :

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Échec de la demande, car le mapping XDM n&#39;est pas publié ou est arrêté :

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## Récupération du statut d&#39;une demande d&#39;ingestion {#retrieving-status}

Il est possible de récupérer le statut d&#39;une demande d&#39;ingestion à l&#39;aide d&#39;une opération GET et de l&#39;identifiant de la demande souhaitée dans les paramètres :

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Des informations détaillées sur le statut de la demande de mapping XDM et ses traitements associés sont disponibles dans l&#39;interface Campaign Standard, dans le menu **[!UICONTROL Statut de l&#39;export des données vers Platform]** (voir [Activation du mapping](../../integrating/using/aep-mapping-activation.md)).

L&#39;opération GET renvoie les informations suivantes :

* **batchId** : ce champ n&#39;est renseigné que si un échec s&#39;est produit après la préparation et le transfert par lots.
* **info** : identifiant du mapping XDM.
* **numRecords** : nombre d&#39;enregistrements ingérés (statut de succès uniquement).
* **status** : statut de la demande d&#39;ingestion (succès/échec/en cours).

Les réponses possibles à l&#39;opération GET sont les suivantes :

* Demande d&#39;ingestion réussie :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* Échec de la demande d&#39;ingestion sans aucun enregistrement ingéré :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* Échec de la demande d&#39;ingestion, avec un enregistrement chargé dans un lot :

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* Demande d&#39;ingestion abandonnée après ingestion de certains enregistrements (cette situation est possible en cas de blocage) :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Demande d&#39;ingestion en cours (lorsque la demande a chargé les données dans un lot ou lorsque le lot est en cours de préparation pour la demande) :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
