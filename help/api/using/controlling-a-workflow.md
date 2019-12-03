---
title: Contrôle d’un processus
description: Découvrez comment contrôler un flux de travail à l’aide d’API.
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Contrôle d’un processus {#controlling-a-workflow}

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
