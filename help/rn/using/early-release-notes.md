---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 21.3 - Septembre 2021  {#release-21-3---sept-2021}


**Nouveautés**


<table> 
<thead> 
<tr> 
<th> <strong>Interface Experience Cloud unifiée</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La barre d’en-tête d’Adobe Campaign a été modifiée pour unifier et améliorer votre expérience sur tous les produits et services Experience Cloud. Ces modifications visent à faciliter votre expérience des produits et services, notamment :</p>
<ul>
<li>Basculement plus facile entre différentes entreprises ou vers une autre application.</li>
<li>Guide d'utilisateur amélioré - Avec l’intégration d’Experience League dans le produit, les résultats des recherches incluent également les résultats des forums de la communauté et davantage de contenu vidéo, ce qui permet d’accéder plus facilement à un plus large éventail de contenu pour tirer pleinement parti de l’application. Nous avons également ajouté un mécanisme de commentaires directement dans le menu Aide, ce qui facilite le signalement de problèmes ou le partage d’idées.</li>
<li>Notifications améliorées - La liste déroulante Notifications comporte désormais deux onglets : l’une pour vos propres notifications de produits, l’autre pour des annonces de produits plus globales.</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Journal d’audit</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La nouvelle fonctionnalité du journal d’audit capture, en temps réel, une liste complète d’actions et d’événements se produisant dans Adobe Campaign. Ceci comprend un accès en libre-service à un historique de données permettant de répondre à des questions, notamment :</p>
<ul>
<li>Qu’est-il advenu de ce workflow et qui l’a mis à jour pour la dernière fois ?</li>
<li>Qui a effectué les dernières modifications ?</li>
<li>Quel était l'état précédent ?</li>
</ul>
<p>Adobe Campaign effectue désormais un audit des actions de création, d’édition et de suppression pour les éléments suivants : workflows, options, ressources personnalisées. Les modifications de ces éléments sont également trackées.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Mode de diagnostic des workflows</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Vous pouvez désormais exécuter des workflows Campaign en mode de diagnostic. Ce mode consigne les informations afin de résoudre les problèmes d’exécution. L’ensemble du plan d’exécution est consigné si, par défaut, une requête de workflow prend plus d’une minute.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* Lors de la création d’une diffusion récurrente dans un workflow, associée à un contenu Adobe Experience Manager, l’état de validation du contenu est désormais vérifié avant envoi.
* La limite de connexion à la base de données est maintenant alignée avec le package Campaign pour éviter les erreurs de connexion.
* Ajout d’une vérification de cohérence lors de la création d’index dans les ressources personnalisées et amélioration des messages d’erreur.

**Correctifs**

* Correction d’une erreur de délai d’expiration lors de l’import de contenu d’e-mail depuis une URL. (CAMP-49054)
* Correction d’une erreur (-69) provoquée par la fin de la session lors de l’accès à une URL marquée d’un signet ou de l’actualisation d’une page à partir du navigateur. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correction d’un problème survenant lors de la synchronisation des règles de l’ancien serveur de délivrabilité avec le nouveau. (CAMP-48923)
* Correction d’un problème lors du chargement d’un modèle d’e-mail avec des balises HTML dans le Concepteur d’e-mail. (CAMP-48243)
