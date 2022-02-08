---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 9ab2e49203315e4c31a1bc268cd17bd0351a5349
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 86%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

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
<p>Suite à la mise à jour de la version 2.17.0 d’Apache log4j en décembre 2021, afin de garantir que nos clients ne soient pas affectés par les effets involontaires potentiels d’une modification supplémentaire du système en dehors de notre calendrier de publication normal, nous avons effectué la mise à jour en interne et nous l’avons prête pour le déploiement avec cette version.</p>
</td> 
</tr> 
</tbody> 
</table>

**Correctifs de sécurité**

* Cette version comprend un nouveau mécanisme de signature dʼURL pour le suivi. Le mécanisme précédent a été désactivé afin dʼéviter quʼun problème ne bloque incorrectement certains liens de suivi signés et valides après avoir été modifiés par des outils de sécurité tiers. (CAMP-48983)
* Renforcez la sécurité pour accéder aux fichiers de configuration d’application et de serveur : La sécurité des API d’accès aux fichiers JavaScript est désormais limitée aux répertoires des environnements de test. (CAMP-49411)

**Améliorations**

* Amélioration du traitement des données de rapport afin d’éviter une surcharge du système. (CAMP-47578)
* Après lʼenvoi de vos messages in-app, vous pouvez désormais choisir de désactiver votre diffusion. Vous pouvez ainsi supprimer votre diffusion sans perdre aucune donnée de rapport. (CAMP-48469)
* Pour éviter tout problème, les utilisateurs ne peuvent plus utiliser le même nom pour une colonne de tableau personnalisée que celui utilisé pour la clé primaire automatique dans la base de données, `"<dataType><resourceName>Id"`. (CAMP-49358)

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
* Pour résoudre divers problèmes, le mécanisme de reprise a été amélioré pour les diffusions comprenant du contenu importé dʼune URL. (CAMP-48888)
* Correction d’un problème qui se produisait après la création d’un filtre dans une ressource personnalisée, puis son utilisation comme clé de réconciliation dans une page de destination. Si la ressource personnalisée était publiée à nouveau, le filtre était supprimé de la liste des clés de réconciliation disponibles pour la page de destination. (CAMP-49516)
* Correction d’un problème dans les pages de destination lors de l’utilisation de conditions dynamiques avec des cases à cocher. (CAMP-48604)
* Correction d’un problème qui se produisait dans une activité **Requête** lors de l’utilisation de la condition de filtre « En ou avant octobre ». Lorsque vous travailliez à partir dʼune instance réglée sur un fuseau horaire européen, le mois sélectionné pour le filtre affichait septembre au lieu dʼoctobre, en raison dʼun problème lors de la conversion du fuseau horaire. (CAMP-48602)
* Pour optimiser la délivrabilité, les emails sont désormais envoyés à l’aide d’un encodage 7 bits au lieu de 8 bits. Cela empêche les relais d’invalider la signature DKIM lors de la conversion de 8 à 7 bits. (CAMP-49016)
* Amélioration des performances lors de la duplication des audiences, afin d’éviter tout problème lors de l’utilisation de grandes audiences. (CAMP-49639)
* Correction d’un problème qui pouvait empêcher un filtre personnalisé dʼafficher les résultats corrects dans une activité **Requête**. (CAMP-49417)
* Correction dʼune erreur qui entraînait lʼaffichage dʼun message dʼerreur lors de lʼutilisation dʼun fragment dans une diffusion dont le nom contient une virgule. Ce problème a été résolu, des virgules peuvent désormais être utilisées dans les noms des fragments. (CAMP-49216)