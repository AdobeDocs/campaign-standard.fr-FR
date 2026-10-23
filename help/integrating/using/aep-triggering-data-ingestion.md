---
title: Déclenchement de l'ingestion des données via les API
description: Découvrez comment déclencher l'ingestion des données par le biais des API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 100%
---
# Déclenchement de l&#39;ingestion des données via les API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector est actuellement en version Beta et peut être fréquemment mis à jour sans préavis. L’hébergement des clientes et clients sur Azure (actuellement en version Beta en Amérique du Nord uniquement) est obligatoire pour pouvoir accéder à ces fonctionnalités. Contactez l&#39;Assistance clientèle d&#39;Adobe si vous souhaitez y accéder.

Adobe Campaign Standard permet de déclencher l&#39;ingestion immédiate des mappings de données par le biais des API et de récupérer le statut de vos demandes d&#39;ingestion.

Cette page décrit comment déclencher et récupérer le statut de l&#39;ingestion de vos mappings de données. Pour des informations globales sur les API de Campaign Standard, consultez [cette section](../../api/using/get-started-apis.md).

## Conditions préalables requises {#prerequisites}

Avant d&#39;utiliser les API, le mapping de données doit avoir été configuré et publié dans l&#39;interface de Campaign Standard. Pour plus d’informations, consultez les sections suivantes :

* [Définition d&#39;un mapping](../../integrating/using/aep-mapping-definition.md)
* [Activation du mapping](../../integrating/using/aep-mapping-activation.md)

Une fois le mapping de données créé, vous devez l&#39;arrêter afin de pouvoir le déclencher à votre convenance depuis les API. Pour ce faire, procédez comme suit :

1. Dans Campaign Standard, accédez au menu **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Plateforme]** > **[!UICONTROL Statut de l&#39;export des données vers Platform.]**

1. Double-cliquez sur le mapping de données pour l&#39;ouvrir, puis cliquez sur le bouton **[!UICONTROL Arrêter]**.

   ![](assets/aep_datamapping_stop.png)

1. Enregistrez vos modifications

L&#39;exécution du mapping de données est arrêtée. Vous pouvez utiliser les API de Campaign Standard pour le déclencher manuellement.

## Démarrage de l’ingestion immédiate du mapping de données {#starting-immediate-ingestion}

L&#39;ingestion immédiate d&#39;un mapping XDM dans Adobe Experience Platform est déclenchée par une opération POST :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Pour exécuter lappel dAPI POST dingestion, lutilisateur doit disposer dun rôle d **exécution de fonction SQL**. Ce rôle peut être attribué par un administrateur de Campaign Standard en exécutant le Script JS suivant :
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

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

* **batchId** : ce champ n’est renseigné que si un échec s’est produit après la préparation et le chargement par lots.
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
