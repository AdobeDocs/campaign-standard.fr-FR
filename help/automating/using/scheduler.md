---
title: Planificateur
description: L'activité Planificateur permet de planifier le déclenchement d'un workflow ou d'une activité.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 39f7b216-b3cd-4aa6-b5df-23e6805076df
source-git-commit: 7deb1147febfcc8956768715a65416806752c92f
workflow-type: ht
source-wordcount: '949'
ht-degree: 100%

---

# Planificateur{#scheduler}

## Description {#description}

![](assets/scheduler.png)

L&#39;activité **[!UICONTROL Planificateur]** permet de planifier le déclenchement d&#39;un workflow ou d&#39;une activité.

## Contexte d&#39;utilisation  {#context-of-use}

L&#39;activité **[!UICONTROL Planificateur]** est à considérer comme un départ planifié. Les règles de positionnement de l&#39;activité dans le diagramme sont les mêmes que pour l&#39;activité **[!UICONTROL Début]**. L&#39;activité ne doit jamais comporter de transition entrante.

Lors de la construction de votre workflow, n&#39;utilisez pas plus d&#39;une activité **[!UICONTROL Planificateur]** par branche et pensez à définir un fuseau horaire. Cette méthode permet de démarrer votre workflow pour un fuseau horaire spécifique, faute de quoi il s’exécutera dans le fuseau horaire défini dans les propriétés du workflow (voir [Construire un workflow](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>La **[!UICONTROL Fréquence de répétition]** de l&#39;activité ne peut pas être inférieure à 10 minutes, ce qui signifie qu&#39;un workflow ne peut pas être exécuté automatiquement plusieurs fois toutes les 10 minutes.

Lors de la conception d’un workflow planifié incluant plusieurs activités, vous devez vous assurer que le workflow n’est pas replanifié tant qu’il n’est pas terminé. Pour ce faire, vous devez configurer votre workflow afin d’empêcher son exécution si une ou plusieurs tâches d’une exécution précédente sont toujours en attente. Pour plus d’informations, consultez [cette page](../../automating/using/scheduled-workflows-execution.md).

**Rubriques connexes :**

* [Cas pratique : création de diffusions à la date de création des profils](../../automating/using/workflow-creation-date-query.md)
* [Cas pratique : création d’une diffusion email tous les mardis](../../automating/using/workflow-weekly-offer.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Planificateur]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Indiquez la **[!UICONTROL Fréquence d&#39;exécution]** :

   * **[!UICONTROL Une seule fois]** : le workflow n&#39;est exécuté qu&#39;une seule fois.
   * **[!UICONTROL Plusieurs fois par jour]** : le workflow est exécuté de manières régulière plusieurs fois par jour.
   * **[!UICONTROL Quotidienne]** : le workflow est exécuté à une heure précise, une fois par jour.
   * **[!UICONTROL Hebdomadaire]** : le workflow est exécuté à un instant défini, une ou plusieurs fois par semaine.
   * **[!UICONTROL Mensuelle]** : le workflow est exécuté à un instant défini, une ou plusieurs fois par mois. Vous pouvez sélectionner les mois auxquels le workflow doit être exécuté. Vous pouvez également configurer des exécutions un jour de semaine spécifié du mois, comme le deuxième mardi du mois.
   * **[!UICONTROL Annuelle]** : le workflow est exécuté à un instant défini, une ou plusieurs fois par an.

1. Configurez les paramètres de l’exécution en fonction de vos besoins. Les options disponibles peuvent varier en fonction de la fréquence d’exécution sélectionnée (heure ou jours d’exécution, fréquence de répétition, etc.).

   >[!NOTE]
   >
   >Le champ **[!UICONTROL Fréquence des répétitions]** disponible pour les fréquences d’exécution quotidiennes et mensuelles permet d’espacer dans le temps les déclenchements du workflow. Par exemple, si vous sélectionnez une fréquence d&#39;exécution quotidienne et que la fréquence de répétition est paramétrée sur **2** (jours), le workflow sera déclenché tous les deux jours. La fréquence de répétition ne peut pas être inférieure à 10 minutes. Si la fréquence de répétition est paramétrée sur **0** (également valeur par défaut), cette option n’est pas prise en compte et le workflow s’exécute selon la fréquence d’exécution définie.

   Lorsque vous définissez la fréquence d’exécution sur **[!UICONTROL Plusieurs fois par jour]**, vous avez la possibilité de choisir entre exécuter le workflow à des moments spécifiques de la journée ou périodiquement tout au long de la journée.

+++ Découvrez comment configurer une fréquence d’exécution **[!UICONTROL « Plusieurs fois par jour »]**.

   * Pour exécuter le workflow plusieurs fois à des moments spécifiques de la journée, activez l’option **[!UICONTROL Heures spécifiques]** puis cliquez sur **[!UICONTROL Ajouter un élément]** pour spécifier l’heure d’exécution souhaitée. Ajoutez-en autant de fois que nécessaire pour répondre à vos besoins.

   * Pour exécuter le workflow de manière périodique tout au long de la journée, activez l’option **[!UICONTROL Périodique]** puis configurez la périodicité d’exécution :

      1. Dans le champ **[!UICONTROL Traitement répété selon la fréquence suivante (par exemple 2 h)]**, indiquez l’intervalle d’exécution du workflow (toutes les 30 minutes, toutes les 2 heures, par exemple).

         >[!NOTE]
         >
         >Cette option permet également de définir des fréquences de répétition quotidiennes, mensuelles ou annuelles. Dans ce cas, le workflow ne s’exécutera pas plusieurs fois par jour, mais selon la fréquence que vous avez définie dans ce champ.
         >
         > Si votre workflow ne nécessite pas plusieurs exécutions au cours d’une journée, mais doit plutôt s’exécuter tous les jours, tous les mois ou tous les ans, il est conseillé d’utiliser les options **[!UICONTROL Quotidienne]**, **[!UICONTROL Mensuelle]** ou **[!UICONTROL Annuelle]** disponibles dans la liste déroulante **[!UICONTROL Fréquence d’exécution]**.

      1. Dans le champ heure de **[!UICONTROL Début]**/**[!UICONTROL Fin]**, définissez l’heure à laquelle l’exécution du workflow doit commencer et se terminer.

         Si aucune heure de fin n’est définie, l’exécution se termine à 00 :00: 00 et la prochaine exécution démarre le lendemain à l’heure de début spécifiée.

      1. Dans le champ de date de **[!UICONTROL Début]**, sélectionnez la date de début de la première exécution.

   Dans l’exemple ci-dessous, l’activité est configurée pour exécuter le workflow toutes les 2 heures entre 8 h et 17 h, à partir du 1er mars.

   ![](assets/wkf_scheduler_day.png)

+++

1. Définissez l&#39;expiration de l&#39;exécution :

   * **[!UICONTROL Jamais]** : Le workflow sera exécuté selon la fréquence d&#39;exécution définie, sans limite dans le temps ni au niveau du nombre d&#39;itérations.
   * **[!UICONTROL Après un certain nombre d&#39;itérations]** : le workflow sera exécuté selon la fréquence d&#39;exécution définie, dans la limite de **X** itérations. Indiquez alors le **[!UICONTROL Nombre d&#39;itérations]**.
   * **[!UICONTROL A la date spécifiée]** : le workflow sera exécuté selon la fréquence d&#39;exécution définie, jusqu&#39;à une date précise. Indiquez alors la date limite d&#39;exécution.

1. Vérifiez le planning des dix prochaines exécutions de votre workflow en cliquant sur **[!UICONTROL Aperçu des prochaines exécutions]**.

1. Dans l&#39;onglet **[!UICONTROL Options d&#39;exécution]**, définissez le fuseau horaire du Planificateur dans le champ **[!UICONTROL Fuseau horaire.]**

   Pour plus d&#39;informations sur l&#39;envoi d&#39;une diffusion selon le fuseau horaire du destinataire, consultez cette [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) ou reportez-vous à cet [exemple](../../automating/using/recurring-push-notifications.md) de workflow récurrent.

1. Validez le paramétrage de l’activité et enregistrez le workflow.

## Exemple  {#example}

Dans l&#39;exemple suivant, l&#39;activité est paramétrée afin de faire démarrer le workflow toutes les deux semaines, le lundi matin à 7 h, pour une durée indéterminée.

![](assets/wkf_scheduler_example.png)
