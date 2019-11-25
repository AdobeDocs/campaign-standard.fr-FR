---
title: Gestion des workflows
description: Découvrez comment gérer des processus à l’aide d’API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestion des workflows {#managing-workflows}

## Contrôle d’un processus

Vous pouvez contrôler un flux de travail directement à partir de l’API REST, par le biais d’une requête POST contenant l’ID de flux de travail et la commande d’exécution requise :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si l’ID de travail est modifié dans Adobe Campaign, la demande d’API ne fonctionnera plus.

Quatre commandes d’exécution sont disponibles pour contrôler un flux de travail :

* Début
* Pause
* Reprendre
* Stopper

Pour plus d’informations sur les commandes d’exécution, reportez-vous à la documentation [](https://helpx.adobe.com/campaign/standard/automating/using/executing-a-workflow.html)Campaign.

<br/>

***Exemples de requêtes***

* Démarrez un processus.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* Arrêt d’un processus.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->

## Déclenchement d’une activité de signal

Dans un processus Adobe Campaign Standard, il peut y avoir une ou plusieurs activités de signal **** externe. Ces activités sont des "écouteurs" qui attendent d’être déclenchées.

Les API de Campaign Standard vous permettent de déclencher une activité de signal **** externe pour appeler un flux de travail. L’appel d’API peut inclure des paramètres qui seront assimilés aux variables d’événements du flux de travail (un nom d’audience à cibler, un nom de fichier à importer, une partie du contenu du message, etc.). De cette façon, vous pouvez facilement intégrer vos automatisations Campaign avec votre système externe.

>[!NOTE]
>
>Les activités de signal externe ne peuvent pas être déclenchées plus souvent que toutes les 10 minutes et le flux de travail de destination doit être déjà en cours d’exécution.

Pour déclencher un processus, procédez comme suit :

1. Exécutez une requête **GET** sur le flux de travail pour récupérer l’URL du déclencheur d’activité de signal externe.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Exécutez une requête **POST** sur l’URL renvoyée pour déclencher l’activité du signal, avec le paramètre **"source"** dans la charge utile. Cet attribut est obligatoire. Il vous permet d’indiquer la source de la demande de déclenchement.

Si vous souhaitez appeler le processus avec des paramètres, ajoutez-les à la charge utile avec l’attribut **"paramètres"** . La syntaxe se compose du nom du paramètre suivi de sa valeur (les types suivants sont pris en charge : **chaîne**, **nombre**, **valeur booléenne** et **date/heure).**

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Lors de l’ajout d’un paramètre à la charge utile, assurez-vous que son **nom** et ses valeurs de **type** sont cohérents avec les informations déclarées dans l’activité de signal externe. De plus, la taille de la charge utile ne doit pas dépasser 64Ko.

<br/>

***Exemple de requête***

Exécutez une requête GET dans le flux de travaux.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Elle renvoie l’activité du signal de flux de travail et l’URL de déclenchement associée.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Pour déclencher une activité de signal, exécutez une requête POST sur l’URL du déclencheur avec la "source". Ajoutez les attributs "paramètres" si vous souhaitez appeler le processus avec des paramètres.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Si l’un des paramètres n’est pas déclaré dans l’activité de signal externe, la requête POST renvoie l’erreur ci-dessous, indiquant le paramètre manquant.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
