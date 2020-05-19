---
title: Gestion des options d’exécution
description: Découvrez comment gérer les options d'exécution des workflows.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 95%

---


# Gestion des options d’exécution {#managing-execution-options}

Pour modifier les propriétés d’exécution de l’ensemble d’un workflow, utilisez le bouton ![](assets/edit_darkgrey-24px.png) pour accéder aux propriétés du workflow et sélectionnez la section **[!UICONTROL Exécution]**.

![](assets/wkf_execution_6.png)

Les options possibles sont les suivantes :

* **[!UICONTROL Affinité par défaut]** : permet de forcer l’exécution d’un workflow ou d’une activité de workflow sur une machine en particulier.

* **[!UICONTROL Jours d’historique]** : indique le nombre de jours après lesquels l’historique doit être purgé. L’historique contient des éléments liés au workflow : logs, tâches, événements (objets techniques liés à l’opération du workflow), ainsi que les fichiers téléchargés par l’activité **[!UICONTROL Transfert de fichier]**. La valeur par défaut est de 30 jours pour les modèles de workflow d’usine.

   La purge de l’historique est effectuée par le workflow technique Nettoyage de la base, qui est exécuté par défaut tous les jours (voir [Liste des workflows techniques](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Si le champ **[!UICONTROL Jours d’historique]** n’est pas renseigné, la valeur prise en compte est « 1 », ce qui signifie que l’historique sera purgé après 1 jour.

* **[!UICONTROL Enregistrer les requêtes SQL dans le journal]** : permet d’enregistrer les requêtes SQL du workflow dans les journaux.

* **[!UICONTROL Conserver les résultats intermédiaires]** : cochez cette option si vous souhaitez pouvoir visualiser le détail des transitions. Attention, en cochant cette option, l’exécution du workflow peut être fortement ralentie.

* **[!UICONTROL Exécuter dans le moteur (ne pas utiliser en production)]** : permet d’exécuter le workflow localement, à des fins de test d’environnement de développement.

* **[!UICONTROL Niveau de criticité]** : permet de définir un niveau de priorité pour l’exécution des workflows de votre instance Adobe Campaign. Les workflows critiques seront exécutés en priorité.

La section **[!UICONTROL Gestion des erreurs]** propose des options supplémentaires pour gérer le comportement des workflows en cas d’erreur. Ces options sont présentées dans la section [Gestion des erreurs](#error-management).
