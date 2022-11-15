---
title: Notes de mise à jour 2022
description: Cette page répertorie toutes les versions 2022 d’Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 8c722084-988d-47bd-98ad-9f5a422980a0
source-git-commit: 77c5baaf51b82ea001326f3f20c8ab183155f9e6
workflow-type: ht
source-wordcount: '1098'
ht-degree: 100%

---

# Notes de mise à jour 2022{#release-notes-2022}

## Version 22.2 - Juin 2022 {#june-2022}

**Améliorations**

* **Adobe Notification Service** - Campaign est fourni avec Adobe Notification Service, qui permet aux solutions Experience Cloud de tenir les utilisateurs d’Experience Cloud informés des activités qui leur sont importantes. À compter de la version 22.2, l’expérience utilisateur a été améliorée : les notifications sont hiérarchisées et les notifications générées par les produits sont séparées des annonces de statut d’Adobe. En complément, lorsque la notification fait référence à un workflow spécifique, vous pouvez désormais accéder directement au workflow correspondant à partir de l’e-mail ou de la notification intégrée au produit.  Pour plus d’informations sur les notifications d’Adobe Campaign, voir [Notifications Adobe Campaign](../../administration/using/sending-internal-notifications.md).

<!--
* **Optimization in Workflow startup** - Adobe has added a new capability which can tune the number of workflows that start around the same time. This would help prevent CPU spikes that could have led to service interruptions or downtime. Adobe would enable it after 22.2 release. There is no further action item on customer regarding the same.
-->

* **Accessibilité** - Adobe a apporté de nombreux correctifs d’accessibilité pour améliorer la facilité d’utilisation globale de l’application. Ces fonctionnalités sont actuellement accessibles à un nombre restreint d’utilisateurs initiaux. Elles seront déployées vers tous les clients dans les prochaines versions. Voici quelques exemples d’améliorations de l’accessibilité :

   * Assurance qu’il existe un indicateur de focus visible pour les éléments pouvant être ciblés sur chaque écran
   * Création de repères de page pour une navigation plus facile
   * Ajout du nom, du rôle, de la valeur et de l’état pour de nombreux contrôles
   * Correction des problèmes rencontrés avec l’ordre de focus dynamique sur les écrans principaux


**Correctifs**

* Correction d’un problème du workflow technique de facturation lié à une erreur de clé en double. (CAMP-51029)
* Ajout de la catégorie de navigateur Microsoft Edge manquante dans les rapports de tracking. Ils étaient auparavant catégorisés avec les ouvertures Microsoft Chrome. (CAMP-51165)
* Correction d’un problème lié aux demandes relatives au RGPD qui ne supprimaient pas les données des tables enfants. (CAMP-48276)
* Correction d’un problème dans le Concepteur d’e-mail en raison duquel la condition de visibilité d’un fragment n’était pas enregistrée, dans un modèle de message transactionnel. (CAMP-50338)
* Correction d’un problème dans les rapports de campagne en raison duquel la période n’était pas prise en compte. (CAMP-50991)
* Correction d&#39;une erreur qui provoquait l&#39;échec des e-mails planifiés : l&#39;analyse de la diffusion ne pouvait pas démarrer car la diffusion était toujours dans l&#39;état « Reprise en attente ». (CAMP-50302)
* Correction d’un problème dans le Concepteur d’e-mail lors de la prévisualisation d’un e-mail avec une substitution de profil. (CAMP-49312)
* Correction d’un problème lié à une valeur vide dans les énumérations personnalisées : lors de la création d&#39;une ressource personnalisée avec un champ qui est une énumération de texte et ne contient qu&#39;une seule valeur, cette valeur est maintenant définie par défaut, afin que vous puissiez créer une requête sur ce champ sous la forme d&#39;une requête simple. (CAMP-50606)


## Version 22.1 - Février 2022 {#feb-2022}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Mise à jour de sécurité pour les vulnérabilités d’Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache Log4j a corrigé les vulnérabilités signalées dans Apache Log4j version 2.17.1. Adobe Campaign Standard utilise Apache Log4j et cette version comprend la version la plus récente dʼApache Log4j, la version 2.17.1. </p>
</td> 
</tr> 
</tbody> 
</table>

**Correctifs de sécurité**

* Cette version comprend un nouveau mécanisme de signature dʼURL pour le suivi. Le mécanisme précédent a été désactivé afin dʼéviter quʼun problème ne bloque incorrectement certains liens de suivi signés et valides après avoir été modifiés par des outils de sécurité tiers. (CAMP-48983)

**Améliorations**

* Amélioration du traitement des données de rapport afin d’éviter une surcharge du système. (CAMP-47578)
* Après lʼenvoi de vos messages in-app, vous pouvez désormais choisir de désactiver votre diffusion. Vous pouvez ainsi supprimer votre diffusion sans perdre aucune donnée de rapport. (CAMP-48469)
* Pour éviter tout problème, les utilisateurs ne peuvent plus utiliser le même nom pour une colonne de tableau personnalisée que celui utilisé pour la clé primaire automatique dans la base de données, `"<dataType><resourceName>Id"`. (CAMP-49358)
* Vous pouvez désormais surveiller votre diffusion et effectuer le suivi des logs de tâches dans la nouvelle liste déroulante **Historique des tâches** du tableau de bord de vos messages. [En savoir plus](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Amélioration de la stabilité et de lʼintégrité de la base de données en réduisant le nombre de tuples inactifs, lorsquʼun grand nombre de messages sont envoyés sur tous les canaux au fil du temps. (CAMP-49755, CAMP-49792, CAMP-49849)
* Des améliorations ont été apportées à MTA (Mail Transfer Agent ) de Campaign, afin de garantir lʼactualisation automatique des connexions à la base de données en cas de panne ou de redémarrage de celle-ci. (CAMP-48063)
* La nouvelle option de tracking **Utiliser le pixel de tracking en haut de l&#39;e-mail** a été ajoutée aux propriétés de l&#39;e-mail. Elle vous permet de déplacer le pixel de tracking en haut de l&#39;e-mail plutôt qu&#39;en bas. (CAMP-49672)

**Correctifs**

* Correction d’un problème avec lʼoption **Envoyer le rapport maintenant** dans les rapports dynamiques : les tâches de génération de PDF échouaient avec les diffusions à plusieurs variantes. (CAMP-49120)
* Correction d’un problème qui empêchait les utilisateurs d’actualiser ou de dissocier le contenu Adobe Experience Manager (AEM) de leurs diffusions Adobe Campaign Standard lorsqu’un contenu dupliqué dans AEM partageait la même clé (cq:uuid). (CAMP-49161)
* Correction dʼune erreur lors de lʼaccès à une instance où les pages ne se chargeaient pas, les diffusions ne pouvaient pas être ouvertes ou les modifications en attente ne pouvaient pas être enregistrées. (CAMP-50195)
* Correction d’un problème en raison duquel les critères dʼalerte de diffusion ne pouvaient pas être ouverts si le champ **Filtre de diffusion** appliqué par ce critère n’était pas rempli. (CAMP-49093)
* Correction d’un problème lors de la modification du bouton **Secondaire** dans les diffusions in-app qui empêchait la prise en compte des modifications. (CAMP-50250)
* Correction dʼune erreur dans les instances japonaises qui empêchait les utilisateurs de choisir Plusieurs fois par jour comme **Fréquence dʼexécution** dans lʼactivité **Planificateur**. (CAMP-50247)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur lors de la sélection d’une heure dans une activité Planificateur dans une interface utilisateur japonaise. (CAMP-49289)
* Correction d’une erreur avec les rapports de notification push qui affichaient les notifications push ignorées comme **Ouverture** au lieu dʼ&#x200B;**Impression**. (CAMP-45980)
* Correction d’un problème qui pouvait entraîner des erreurs lors de l’ouverture d’un rapport. (CAMP-49222)
* Correction dʼun problème qui pouvait entraîner lʼéchec de la préparation de lʼe-mail après la suppression dʼun lien vers un contenu AEM. (CAMP-49877)
* Pour résoudre divers problèmes, le mécanisme de reprise a été amélioré pour les diffusions comprenant du contenu importé dʼune URL. [En savoir plus](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Correction d’un problème qui se produisait après la création d’un filtre dans une ressource personnalisée, puis son utilisation comme clé de réconciliation dans une page de destination. Si la ressource personnalisée était publiée à nouveau, le filtre était supprimé de la liste des clés de réconciliation disponibles pour la page de destination. (CAMP-49516)
* Correction d’un problème dans les pages de destination lors de l’utilisation de conditions dynamiques avec des cases à cocher. (CAMP-48604)
* Correction d’un problème qui se produisait dans une activité **Requête** lors de l’utilisation de la condition de filtre « En ou avant octobre ». Lorsque vous travailliez à partir dʼune instance réglée sur un fuseau horaire européen, le mois sélectionné pour le filtre affichait septembre au lieu dʼoctobre, en raison dʼun problème lors de la conversion du fuseau horaire. (CAMP-48602)
* Pour optimiser la délivrabilité, Adobe Campaign envoie désormais les e-mails à l’aide d’un encodage 7 bits au lieu de 8 bits. Cela empêche les relais intermédiaires dʼinvalider la signature DKIM, ce qui pourrait affecter lʼauthenticité des messages. (CAMP-49016)
* Amélioration des performances lors de la duplication des audiences, afin d’éviter tout problème lors de l’utilisation de grandes audiences. (CAMP-49639)
* Correction d’un problème qui pouvait empêcher un filtre personnalisé dʼafficher les résultats corrects dans une activité **Requête**. (CAMP-49417)
* Correction dʼune erreur qui entraînait lʼaffichage dʼun message dʼerreur lors de lʼutilisation dʼun fragment dans une diffusion dont le nom contient une virgule. Ce problème a été résolu, des virgules peuvent désormais être utilisées dans les noms des fragments. (CAMP-49216)
