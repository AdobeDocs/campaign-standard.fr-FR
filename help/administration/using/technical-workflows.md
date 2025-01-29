---
title: Workflows techniques
description: 'En savoir plus à propos des workflows techniques '
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: f87795ee2378a1e9e1b393c6cce002bcb70178b8
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 100%

---

# Workflows techniques{#technical-workflows}

Les workflows techniques sont livrés d&#39;usine avec Adobe Campaign. Les workflows techniques sont des opérations ou traitements programmés pour s&#39;exécuter périodiquement sur le serveur.

Ils permettent de réaliser les opérations de maintenance sur la base, remonter les informations de tracking sur les diffusions et mettre en place les traitements prévisionnels sur les diffusions.

Les administrateurs fonctionnels peuvent accéder aux workflows techniques depuis le menu **[!UICONTROL Administration > Paramétrage de l&#39;application > Workflows]**.

>[!NOTE]
>
>En tant qu&#39;administrateur fonctionnel, vous pouvez redémarrer les workflows techniques et les mettre en pause, et modifier leurs propriétés et leur structure.

![](assets/technical_workflows.png)

## Liste des workflows techniques {#list-of-technical-workflows}

Les workflows techniques sont utilisés pour gérer les processus techniques et d&#39;arrière-plan déclenchés automatiquement dans Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Libellé</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Description</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B Testing</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> Ce workflow analyse le tracking de chaque variante. A la fin de la période d'apprentissage du test A/B, il calcule automatiquement la variante gagnante. Par défaut, il se déclenche tous les jours.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturation</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Ce workflow transmet par e-mail le rapport d'activité du système à l'utilisateur 'billing'. Par défaut, il se déclenche tous les jours à 1H00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Copier des en-têtes à partir de modèles de diffusion</span> <br /> </td> 
   <td> <span class="uicontrol">smtpHeaderupdate</span> <br /> </td> 
   <td> Ce workflow copie les en-têtes SMTP définis pour les modèles de diffusion e-mail vers les diffusions enfant correspondantes qui ne sont pas des modèles. Seules les diffusions e-mail marketing sont récupérées par ce workflow. Les en-têtes SMTP ne sont pas copiés vers les diffusions transactionnelles et les diffusions de BAT. <br> Ce workflow n’est pas exécuté périodiquement. Il doit être démarré par la personne selon son utilisation. <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br> Si votre instance contient un volume élevé de diffusions, vous pouvez mettre à jour l’option NmsCleanup_DeliveryPurgeDelay dans les <strong>Paramètres de l’application</strong>. Si vous effectuez une modification dans les en-têtes SMTP d’un modèle, vous devez exécuter à nouveau le workflow après la modification afin que les en-têtes corrigés soient copiés vers les diffusions non modèles.<a href="data-retention.md#deliveries">En savoir plus</a>
<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Nettoyage de la base</span> <br /> </td> 
   <td> <span class="uicontrol">nettoyage</span> <br /> </td> 
   <td> Ce workflow est le workflow d'entretien de la base : il procède aux différents calculs des statistiques et traitements, et supprime les données obsolètes de la base de données selon le paramétrage défini. Par défaut, il se déclenche tous les jours à 4H00.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Importer une audience partagée</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Ce workflow synchronise les données des audiences Adobe Experience Cloud importées dans Adobe Campaign. Par défaut, il se déclenche toutes les heures.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Partage instantané des rapports</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Ce workflow démarre dès qu'un rapport devrait être envoyé. Il convertit votre rapport en fichier PDF puis l'envoie dans un e-mail aux destinataires ciblés.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Réconciliation des KPI avec Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Ce workflow récupère les KPI du service de rapports une fois par jour et les réconcilie avec les données Adobe Analytics. Il envoie ensuite la différence si nécessaire. Par défaut, il se déclenche tous les jours à 4.20H00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archivage local Message Center</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Ce workflow archive les événements temps réel vers une table d'historique. Par défaut, il se déclenche toutes les heures.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Agrégats du reporting</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Ce workflow met à jour les agrégats utilisés dans les rapports. Par défaut, il se déclenche tous les jours à 2H00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Partager les KPI avec Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Ce workflow envoie les données KPI toutes les 15 minutes depuis Adobe Campaign Standard vers Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Synchroniser avec Launch</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Ce workflow synchronise les propriétés mobiles de balise importées dans Adobe Campaign Standard. Il est lancé toutes les 15 minutes.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Récupération des logs de tracking</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Ce workflow synchronise les propriétés mobiles de balise importées dans Adobe Campaign Standard. Il est lancé toutes les 15 minutes.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Récupérer les logs de tracking</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> Ce workflow restaure les logs de tracking perdus. Notez que ce workflow technique est utilisé dans des contextes spécifiques et limité à une utilisation interne par Adobe. <br> Par défaut, il se déclenche toutes les 10 minutes.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Mettre à jour l'exécution des diffusions.</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> Ce workflow copie les broadlogs et les logs de tracking dans la base de données locale. Par défaut, il se déclenche toutes les 10 minutes.<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Mettre à jour les indicateurs de diffusion</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Ce workflow met à jour les indicateurs de performance clés (KPI) de la diffusion. Par défaut, il se déclenche toutes les heures.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mise à jour du statut des événements</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Ce workflow permet d'attribuer un statut à l'événement. Les statuts d'un événement sont les suivants :<br /> <strong>En attente</strong> : l'événement se trouve dans la file d'attente. Aucun modèle de message ne lui a encore été associé.<br /> <span class="uicontrol">En attente de diffusion : l'événement est dans la file d'attente, un modèle de message lui a été associé et il est en cours de traitement par la diffusion.</span><br /> <strong>Envoyé</strong> : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été envoyée.<br /> <strong>Ignoré par la diffusion</strong> : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a été ignorée.<br /> <strong>Erreur de diffusion</strong> : ce statut est copié depuis les logs de diffusion. Il signifie que la diffusion a échoué.<br /> <span class="uicontrol">Evénement non pris en charge : l'association de l'événement à un modèle de message a échoué. </span> L'événement ne sera pas retraité.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mise à jour pour la délivrabilité</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Ce workflow permet de créer la liste des règles de qualification des mails rebonds, ainsi que la liste des domaines et des MX dans la plate-forme. Ce workflow ne fonctionne que si le port HTTPS est ouvert. Par défaut, il se déclenche tous les jours à 2H00.<br /> </td> 
  </tr> 
 </tbody> 
</table>
