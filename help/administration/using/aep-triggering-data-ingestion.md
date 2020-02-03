---
title: Déclenchement de l’assimilation de données via les API
description: Découvrez comment déclencher l’assimilation de données par le biais des API.
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
source-git-commit: 5f3bf4c2d0bba095182194ac28b3107eae2c54a6

---


# Déclenchement de l’assimilation de données via les API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Le service de données de Campaign Standard est actuellement en version bêta, qui peut faire l’objet de fréquentes mises à jour sans préavis. Les clients doivent être hébergés sur Azure (actuellement en version bêta pour l&#39;Amérique du Nord uniquement) pour accéder à ces fonctionnalités. Contactez le service à la clientèle d’Adobe si vous souhaitez y accéder.

Adobe Campaign Standard vous permet de déclencher l’assimilation immédiate des mappages de données via des API et de récupérer l’état de vos demandes d’assimilation.

>[!NOTE]
>
>Cette page décrit comment déclencher et récupérer l’état d’assimilation de vos mappages de données. Pour plus d&#39;informations sur les API de Campaign Standard, reportez-vous à [cette section](../../api/using/about-campaign-standard-apis.md).

## Prérequis {#prerequisites}

Avant d’utiliser les API, le mappage des données doit d’abord avoir été configuré et publié dans l’interface de Campaign Standard. Pour plus d’informations, reportez-vous aux sections suivantes :

* [Définition de mappage](../../administration/using/aep-mapping-definition.md)
* [Activation de mappage](../../administration/using/aep-mapping-activation.md)

Une fois le mappage des données créé, vous devez l’arrêter afin de pouvoir le déclencher à partir des API à votre convenance. Pour ce faire, procédez comme suit :

1. Dans Campaign Standard, accédez au menu **[!UICONTROL Administration]**>**[!UICONTROL  Développement]** > **[!UICONTROL Plate-forme]**>**!UICONTROL État de l’exportation des données vers la plateforme].**

1. Cliquez deux fois sur le mappage de données pour l’ouvrir, puis cliquez sur le bouton **[!UICONTROL Arrêter]**.

   ![](assets/aep_datamapping_stop.png)

1. Enregistrez vos modifications

L’exécution du mappage de données est maintenant arrêtée. Vous pouvez utiliser les API de Campaign Standard pour le déclencher manuellement.

## Démarrage immédiat de l’assimilation des données {#starting-immediate-ingestion}

L’assimilation immédiate d’un mappage XDM dans Adobe Experience Platform est déclenchée par une opération POST :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Pour exécuter l&#39;appel d&#39;API POST d&#39;assimilation, l&#39;utilisateur doit avoir un rôle d&#39;exécution **de fonction** SQL, qui peut être fourni par un administrateur de Campaign Standard en s&#39;exécutant sous Script JS :
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

L’opération POST renvoie des informations concernant l’état de la requête créée :

* Demande envoyée avec succès pour le mappage XDM :

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Demande déjà en cours pour le mappage XDM :

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Échec de la demande, car le mappage XDM n’est pas publié ou est arrêté :

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

## Récupération de l’état d’une demande d’assimilation {#retrieving-status}

L’état d’une demande d’assimilation peut être récupéré avec une opération GET et l’ID de demande souhaité dans les paramètres :

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
Des informations détaillées sur l’état de la demande de mappage XDM et ses tâches associées sont disponibles dans l’interface Campaign Standard, dans le menu **!UICONTROL [Status of data export to platform]** (voir Activation [du](../../administration/using/aep-mapping-activation.md)mappage).

L’opération GET renvoie les informations suivantes :

* **batchId**: ce champ n’est renseigné que si un échec s’est produit après la préparation et le transfert par lots,
* **info**: l&#39;ID de mappage XDM,
* **numRecords**: le nombre d&#39;enregistrements qui ont été assimilés (état de réussite uniquement),
* **status**: l’état de la demande d’assimilation (succès/échec/en cours)

Les réponses possibles à l’opération GET sont les suivantes :

* Demande d&#39;assimilation réussie :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ````

* Échec de la demande d&#39;assimilation avec 0 enregistrement assimilé :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* Échec de la demande d&#39;assimilation, avec un enregistrement transféré sous un lot :

   ````
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```
   
* Demande d’assimilation abandonnée après l’assimilation de certains enregistrements (cela peut se produire dans les scénarios de plantage) :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Demande d’assimilation en cours (lorsque la demande a transféré les données dans un lot ou lorsque le lot est en cours de préparation pour la demande) :

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
