---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 8bc0b1186e177b6937c1ae72c1f8763c480b12a9
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 10%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 22.1 - Février 2022               {#feb-2022}


**Nouveautés**


<table> 
<thead> 
<tr> 
<th> <strong>Mise à jour de sécurité pour les vulnérabilités de la sécurité d’Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j a corrigé les vulnérabilités signalées dans la version Apache log4j v2.17.1. Adobe Campaign Standard utilise Apache log4j et dans cette version, il comprend le dernier log4j Apache v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Correctifs de sécurité**

* Nouveau mécanisme de signature d’URL pour le suivi inclus dans cette version. Le mécanisme précédent avait été désactivé pour empêcher un problème qui provoquait le blocage incorrect de certains liens de suivi signés valides après avoir été modifiés par des outils de sécurité tiers. (CAMP-48983)

**Améliorations**

* Amélioration du traitement des données de rapport afin d’éviter un surchargement du système. (CAMP-47578)
* Après l&#39;envoi de vos messages In-App, vous pouvez désormais choisir de désactiver votre diffusion. Vous pouvez ainsi supprimer votre diffusion sans perdre de données de reporting. (CAMP-48469)
* Pour éviter tout problème, les utilisateurs ne peuvent plus utiliser le même nom pour une colonne de table personnalisée que celui utilisé pour la clé Principal automatique dans la base de données, `"<dataType><resourceName>Id"`. (CAMP-49358)
* Vous pouvez désormais surveiller votre diffusion et suivre les logs des traitements avec la nouvelle **Historique des tâches** du tableau de bord de vos messages. (CAMP-49840)

**Correctifs**

* Correction d’un problème lié à la fonction **Envoyer le rapport maintenant** dans les rapports dynamiques : les traitements de génération de PDF ont échoué avec les diffusions, y compris les multivariantes. (CAMP-49120)
* Correction d’un problème qui empêchait les utilisateurs d’actualiser ou de dissocier le contenu Adobe Experience Manager (AEM) de leurs diffusions Adobe Campaign Standard lorsqu’un contenu dupliqué dans AEM partageait la même clé (cq:uuid). (CAMP-49161)
* Correction d&#39;une erreur lors de l&#39;accès à une instance où les pages ne se chargeaient pas, où les diffusions ne pouvaient pas être ouvertes ou les modifications en attente ne pouvaient pas être enregistrées. (CAMP-50195)
* Correction d’un problème qui empêchait l’ouverture des critères des alertes de diffusion si le champ **Filtre de diffusion** appliqué par ce critère n’a pas été rempli. (CAMP-49093)
* Correction d’un problème lors de la modification de la variable **Secondaire** dans les diffusions In-App qui ont empêché la prise en compte des modifications. (CAMP-50250)
* Correction d&#39;une erreur dans les instances japonaises qui empêchait les utilisateurs de choisir plusieurs fois par jour comme **Fréquence d&#39;exécution** dans le **Planificateur** activité. (CAMP-50247)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur lors de la sélection d’une heure dans une activité Planificateur dans une interface utilisateur japonaise. (CAMP-49289)
* Correction d’une erreur liée aux rapports de notification push qui affichait des notifications push ignorées comme **Ouvrir** au lieu de **Impression**. (CAMP-45980)
* Correction d’un problème qui entraînait des erreurs lors de l’ouverture d’un rapport. (CAMP-49222)
* Correction d’un problème qui entraînait l’échec de la préparation de l’email après la suppression d’un lien vers AEM contenu. (CAMP-49877)
* Pour résoudre divers problèmes, le mécanisme de reprise a été amélioré pour les diffusions, y compris le contenu importé à partir d&#39;une URL. (CAMP-48888)
* Correction d’un problème qui se produisait après la création d’un nouveau filtre dans une ressource personnalisée, puis son utilisation comme clé de réconciliation dans une landing page. Si la ressource personnalisée a de nouveau été publiée, le filtre a été supprimé de la liste des clés de réconciliation disponibles pour la landing page. (CAMP-49516)
* Correction d’un problème dans les landing pages lors de l’utilisation de conditions dynamiques avec des cases à cocher. (CAMP-48604)
* Correction d’un problème qui se produisait dans une **Requête** activité lors de l’utilisation de la condition de filtre &quot;En cours ou avant octobre&quot;. Lorsque vous travaillez à partir d’une instance définie sur un fuseau horaire européen, le mois sélectionné pour le filtre affichait septembre au lieu d’octobre, en raison d’un problème lors de la conversion du fuseau horaire. (CAMP-48602)
* Pour optimiser la délivrabilité, Adobe Campaign envoie désormais les emails à l’aide d’un encodage 7 bits au lieu de 8 bits. Cela empêche les relais intermédiaires d&#39;invalider la signature DKIM, ce qui pourrait affecter l&#39;authenticité des messages. (CAMP-49016)
* Les performances lors de la duplication d’audiences ont été améliorées afin d’éviter tout problème lors de l’utilisation d’audiences volumineuses. (CAMP-49639)
* Correction d’un problème qui empêchait l’affichage des résultats corrects par un filtre personnalisé dans une **Requête** activité. (CAMP-49417)
* Correction d&#39;une erreur qui affichait un message d&#39;erreur lors de l&#39;utilisation d&#39;un fragment dans une diffusion dont le nom comportait une virgule. Le problème a été résolu, des virgules peuvent désormais être utilisées dans les noms des fragments. (CAMP-49216)