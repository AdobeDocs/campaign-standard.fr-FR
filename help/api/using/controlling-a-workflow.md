---
title: Contrôle d’un workflow
description: Découvrez comment contrôler un workflow à l’aide des API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 100%

---


# Contrôle d’un workflow {#controlling-a-workflow}

Vous pouvez contrôler un workflow directement à partir de l’API REST, par le biais d’une requête POST contenant l’identifiant du workflow et la commande d’exécution requise :

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si l’identifiant du workflow est modifié dans Adobe Campaign, la requête d’API ne fonctionnera plus.

Quatre commandes d’exécution sont disponibles pour contrôler un workflow :

* Démarrer
* Pause
* Reprendre
* Arrêter

Pour plus d’informations sur les commandes d’exécution, reportez-vous à la [documentation de Campaign](https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html).

<br/>

***Exemples de requêtes***

* Démarrer un workflow.

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

* Arrêter un processus.

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
