---
solution: Campaign Standard
product: campaign
title: Contrôle d’un workflow
description: Découvrez comment contrôler un workflow à l’aide des API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingénieur de données
level: Expérimenté
translation-type: ht
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: ht
source-wordcount: '100'
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

***Exemples de demande***

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
