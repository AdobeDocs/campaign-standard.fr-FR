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
source-wordcount: '1072'
ht-degree: 43%

---

# Notes de mise à jour initiales {#new-release}

Cette page décrit les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 21.3 - Septembre 2021  {#release-21-3---sept-2021}

**Nouveautés**


<table> 
<thead> 
<tr> 
<th> <strong>Interface Experience Cloud unifiée</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La barre d’en-tête d’Adobe Campaign a été modifiée pour unifier et améliorer votre expérience sur tous les produits et services Experience Cloud. Ces modifications visent à faciliter votre expérience des produits et services, notamment :</p>
<ul>
<li>Basculement plus facile entre différentes entreprises ou vers une autre application.</li>
<li>Guide d'utilisateur amélioré - Avec l’intégration d’Experience League dans le produit, les résultats des recherches incluent également les résultats des forums de la communauté et davantage de contenu vidéo, ce qui permet d’accéder plus facilement à un plus large éventail de contenu pour tirer pleinement parti de l’application. Nous avons également ajouté un mécanisme de commentaires directement dans le menu Aide, ce qui facilite le signalement de problèmes ou le partage d’idées.</li>
<li>Notifications améliorées - La liste déroulante Notifications comporte désormais deux onglets : l’une pour vos propres notifications de produits, l’autre pour des annonces de produits plus globales.</li>
</ul>
<p>Pour plus d’informations, consultez la <a href="../../start/using/interface-description.md#top-bar">documentation détaillée</a>.
</p>
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
<p>La nouvelle fonctionnalité du journal d’audit capture, en temps réel, une liste complète d’actions et d’événements se produisant dans Adobe Campaign. Ceci comprend un accès en libre-service à un historique de données permettant de répondre à des questions, notamment :</p>
<ul>
<li>Qu’est-il advenu de ce workflow et qui l’a mis à jour pour la dernière fois ?</li>
<li>Qui a effectué les dernières modifications ?</li>
<li>Quel était l'état précédent ?</li>
</ul>
<p>Adobe Campaign effectue désormais un audit des actions de création, d’édition et de suppression pour les éléments suivants : workflows, options, ressources personnalisées. Les modifications de ces éléments sont également trackées.</p>
<p>Pour plus d'informations, consultez la <a href="../../administration/using/audit.md">documentation détaillée</a>.</p>
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
<p>Pour plus d’informations, consultez la <a href="../../automating/using/managing-execution-options.md">documentation détaillée</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Amélioration de la sécurité**

* La sécurité a été renforcée pour la protection contre les attaques SSRF. (CAMP-47836)
* La liste des utilisateurs est désormais réservée aux administrateurs. (CAMP-47260)
* Les variables d’environnement ne peuvent plus être utilisées dans le cadre de l’extension de paramètre dans une URL. (CAMP-47268)

**Améliorations**

* Lors de la création d’une diffusion récurrente dans un workflow, associée à un contenu Adobe Experience Manager, l’état de validation du contenu est désormais vérifié avant envoi.
* La limite de connexion à la base de données est maintenant alignée avec le package Campaign pour éviter les erreurs de connexion.
* Ajout d’une vérification de cohérence lors de la création d’index dans les ressources personnalisées et amélioration des messages d’erreur.

**Autres changements**

* Les services Connecteur de données Adobe Experience Platform et Audience Destinations sont désormais obsolètes avec Campaign Standard. Si vous utilisez ces fonctionnalités, vous devez migrer vers les sources et destinations d’Adobe et adapter votre mise en oeuvre. [Apprenez-en davantage](../../integrating/using/get-started-sources-destinations.md)
* Les fonctionnalités obsolètes et supprimées sont répertoriées dans [cette page](deprecated-features.md).
* Une nouvelle fonction d&#39;agrégat &#39;StringAgg&#39; a été introduite pour concaténer les valeurs d&#39;une colonne de type chaîne. (CAMP-47077)
* Le workflow technique **Mise à jour des indicateurs de diffusion** (updateDeliveryIndicators) a été amélioré pour de meilleures performances.
* Les modèles de messagerie in-app sont désormais disponibles pour toutes les langues prises en charge dans Campaign Standard.
* Le délai de préparation de la diffusion a été optimisé pour les messages transactionnels en réduisant le nombre d’appels au serveur de suivi lors de l’analyse de la diffusion.
* Un nouveau message d’alerte informe les utilisateurs d’un taux de rebond élevé.
* Amélioration des messages d’erreur et des avertissements de journal afin de faciliter le débogage lorsque la récupération des logs de tracking a échoué. (CAMP-48939, CAMP-47360)
* Vous pouvez désormais entièrement personnaliser les URL, y compris le nom de domaine. [En savoir plus](../../designing/using/personalization.md#personalizing-urls)

**Correctifs**

* Correction d’une erreur de délai d’expiration lors de l’import de contenu d’e-mail depuis une URL. (CAMP-49054)
* Correction d’une erreur (-69) provoquée par la fin d’une session lors de l’accès à une URL marquée d’un signet ou de l’actualisation d’une page à partir du navigateur. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correction d’un problème survenant lors de la synchronisation des règles de l’ancien serveur de délivrabilité avec le nouveau. (CAMP-48923)
* Correction d’un problème lors du chargement d’un modèle d’e-mail avec des balises HTML dans le Concepteur d’e-mail. (CAMP-48243)
* Correction d&#39;une erreur qui empêchait le chargement du contenu Adobe Experience Manager lors de la création de messages transactionnels avec le Concepteur d&#39;email. (CAMP-49075)
* Correction d’un problème dans l’interface en raison duquel une marge intérieure trop importante était ajoutée entre la barre supérieure et le contenu.
* Correction d’un problème lié aux messages transactionnels qui entraînait une erreur de publication lors de l’utilisation de blocs de contenu Campaign dans le contenu Adobe Experience Manager. (CAMP-49233)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur en cas d’échec de l’authentification. L’utilisateur est maintenant redirigé vers la page de connexion.
* Correction d’un problème d’affichage des jetons qui empêchait les utilisateurs de modifier ou de partager un rapport.
* Correction d’un problème lors de la publication d’une ressource personnalisée à l’aide d’une expression de filtre avec des relations de table 1-n. (CAMP-48740)
* Correction d’un problème de mise en forme de date qui empêchait la récupération des dates de contact de diffusion dans les transitions de workflow. (CAMP-48871)
* Correction d’un problème qui empêchait l’extension des envois lors de la création d’une dimension de profil personnalisé.
* Correction d’un problème qui entraînait l’échec des diffusions avec plusieurs variantes linguistiques. Désormais, si un utilisateur supprime la variante de langue par défaut, une autre variante de langue doit être définie comme variante par défaut avant de créer des copies de langue. (CAMP-48235)
* Correction d’un problème en raison duquel les messages électroniques affichaient des espaces blancs supplémentaires dans Outlook si l’utilisateur avait sélectionné l’option **Afficher uniquement sur les appareils mobiles** lors de la conception du message. (CAMP-48902)
* Correction d’un problème en raison duquel la date de dernière exécution du champ de l’activité de requête incrémentale était absente de l’onglet **Données traitées** après l’exécution du workflow de requête incrémentale. (CAMP-48879)
* Correction d’un problème qui vous empêchait de définir correctement un code segment dynamique dans l’activité de workflow **Segmentation** . (CAMP-48727)
* Correction d&#39;une erreur qui se produisait de manière aléatoire lors de l&#39;enregistrement d&#39;un workflow après son édition. (CAMP-48695)
* Correction d’un problème qui vous empêchait de publier des ressources personnalisées en raison du fait que le schéma de données d’un déclencheur restait inchangé même après la suppression du déclencheur. (CAMP-48523)
* Correction d’un problème qui empêchait le traitement des demandes de feedback loop, car le processus InMail n’était pas en mesure de récupérer les logs de diffusion à mettre à jour. (CAMP-48705)
* Correction d’un problème qui vous empêchait de définir correctement les options d’exclusion dans l’activité de workflow **Exclusion** .(CAMP-48355)
* Correction d’un problème qui se produisait lorsque les activités d’enrichissement dans les workflows impliquaient des abonnements ou des désabonnements à un service. Ce problème a entraîné un blocage.
* Correction d’un problème qui empêchait l’exécution des workflows.
* Correction d’un problème qui empêchait les utilisateurs de renommer ou de supprimer des groupes de sécurité d’usine de l’interface utilisateur.
* Correction d’un problème qui empêchait les utilisateurs de supprimer une tâche de publication d’événement incomplète.
* Correction d’un problème en raison duquel le workflow de nettoyage de la base échouait avec une erreur. (CAMP-49097)
