---
title: Dernière version
description: Cette page détaille le contenu de la dernière version de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Dernière version{#latest-release}

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
* Vous pouvez désormais surveiller votre diffusion et effectuer le suivi des logs de tâches dans la nouvelle liste déroulante **Historique des tâches** du tableau de bord de vos messages. (CAMP-49840)
* Amélioration de la stabilité et de lʼintégrité de la base de données en réduisant le nombre de tuples inactifs, lorsquʼun grand nombre de messages sont envoyés sur tous les canaux au fil du temps. (CAMP-49755, CAMP-49792, CAMP-49849)
* Des améliorations ont été apportées à MTA (Mail Transfer Agent ) de Campaign, afin de garantir lʼactualisation automatique des connexions à la base de données en cas de panne ou de redémarrage de celle-ci. (CAMP-48063)


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


## Version 21.3 - Septembre 2021  {#release-21-3---sept-2021}

Les nouvelles fonctionnalités, améliorations et corrections incluses dans la dernière version de Campaign Standard sont répertoriées ci-dessous.

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
<p>La nouvelle fonctionnalité du journal d’audit capture, en temps réel, une liste complète d’actions et d’événements se produisant dans Adobe Campaign. Ceci comprend un accès en libre-service à un historique de données permettant de répondre à des questions, notamment :</p>
<ul>
<li>Qu’est-il advenu de ce workflow et qui l’a mis à jour pour la dernière fois ?</li>
<li>Qui a effectué les dernières modifications ?</li>
<li>Quel était l'état précédent ?</li>
</ul>
<p>Adobe Campaign effectue désormais un audit des actions de création, d’édition et de suppression pour les éléments suivants : workflows, options, ressources personnalisées. Les modifications de ces éléments sont également trackées.</p>
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

* La sécurité a été renforcée pour assurer une protection contre les attaques SSRF. (CAMP-47836)
* La liste des utilisateurs est désormais restreinte aux administrateurs. (CAMP-47260)
* Les variables d’environnement ne peuvent plus être utilisées dans le cadre de l’extension de paramètre dans une URL. (CAMP-47268)

**Améliorations**

* Lors de la création d’une diffusion récurrente dans un workflow, associée à un contenu Adobe Experience Manager, l’état de validation du contenu est désormais vérifié avant envoi.
* La limite de connexion à la base de données est maintenant alignée avec le package Campaign pour éviter les erreurs de connexion.
* Un nouveau contrôle de cohérence dans la publication des ressources personnalisées empêche les utilisateurs de dupliquer des index, ce qui entraîne l’échec de la publication. Un message d’erreur amélioré demande à l’utilisateur de renommer l’index, si nécessaire. [Apprenez-en davantage](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)   

**Autres changements**

* Les services Connecteur de données Adobe Experience Platform et Audience Destinations sont désormais obsolètes avec Campaign Standard. Si vous utilisez ces fonctionnalités, vous devez migrer vers les sources et destinations d’Adobe et adapter votre mise en œuvre. [Apprenez-en davantage](../../integrating/using/get-started-sources-destinations.md)   
* Les fonctionnalités obsolètes et supprimées sont répertoriées dans [cette page](deprecated-features.md).
* Une nouvelle fonction d&#39;agrégat &#39;StringAgg&#39; a été introduite pour concaténer les valeurs d&#39;une colonne de type chaîne. (CAMP-47077) [En savoir plus](../../automating/using/list-of-functions.md#aggregates)
* Le workflow technique **Mise à jour des indicateurs de diffusion** (updateDeliveryIndicators) a été amélioré pour optimiser les performances.
* Les modèles de messagerie In-App sont maintenant disponibles pour toutes les langues prises en charge dans Campaign Standard.
* Le délai de préparation des diffusions a été optimisé pour les messages transactionnels grâce à la réduction du nombre d’appels au serveur de tracking lors de l’analyse d’une diffusion.
* Un nouveau message d’alerte informe les utilisateurs d’un taux de rebond élevé.
* Amélioration des messages d’erreur et des avertissements des logs afin de faciliter le débogage lorsque la récupération des logs de tracking a échoué. (CAMP-48939, CAMP-47360)
* Vous pouvez maintenant entièrement personnaliser les URL, y compris le nom de domaine. [En savoir plus](../../designing/using/personalization.md#personalizing-urls)

**Correctifs**

* Correction d’une erreur de délai d’expiration lors de l’import de contenu d’e-mail depuis une URL. (CAMP-49054)
* Correction d’une erreur (-69) entraînée par la fin de la session lors de l’accès à une URL marquée d’un signet ou de l’actualisation d’une page à partir du navigateur. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correction d’un problème survenant lors de la synchronisation des règles de l’ancien serveur de délivrabilité avec le nouveau. (CAMP-48923)
* Correction d’un problème lors du chargement d’un modèle d’e-mail avec des balises HTML dans le Concepteur d’e-mail. (CAMP-48243)
* Correction d&#39;une erreur qui empêchait le chargement du contenu Adobe Experience Manager lors de la création de messages transactionnels avec le Concepteur d’e-mail. (CAMP-49075)
* Correction d’un problème dans l’interface : une marge intérieure trop importante était ajoutée entre la barre supérieure et le contenu.
* Correction d’un problème lié aux messages transactionnels qui entraînait une erreur de publication lors de l’utilisation de blocs de contenu Campaign dans le contenu Adobe Experience Manager. (CAMP-49233)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur en cas d’échec de l’authentification. L’utilisateur est maintenant redirigé vers la page de connexion.
* Correction d’un problème d’affichage des jetons qui empêchait les utilisateurs de modifier ou de partager un rapport.
* Correction d’un problème lors de la publication d’une ressource personnalisée à l’aide d’une expression de filtre avec des relations de table 1-n. (CAMP-48740)
* Correction d’un problème de mise en forme de date qui empêchait la récupération des dates de contact de diffusion dans les transitions de workflow. (CAMP-48871)
* Correction d’un problème qui empêchait l’extension des logs d’envoi lors de la création d’une dimension de profil personnalisé.
* Correction d’un problème qui entraînait l’échec des diffusions avec plusieurs variantes linguistiques. Désormais, si un utilisateur supprime la variante linguistique par défaut, une autre variante doit être définie comme variante par défaut avant de créer des copies de langue. (CAMP-48235)
* Correction d’un problème en raison duquel les messages e-mail affichaient des espaces supplémentaires dans Outlook si l’utilisateur avait sélectionné l’option **Afficher uniquement sur les appareils mobiles** lors de la conception du message. (CAMP-48902)
* Correction d’un problème en raison duquel la date de dernière exécution du champ de l’activité de requête incrémentale était absente de l’onglet **Données traitées** après l’exécution du workflow de requête incrémentale. (CAMP-48879)
* Correction d’un problème qui empêchait de définir correctement un code segment dynamique dans l’activité de workflow **Segmentation**. (CAMP-48727)
* Correction d&#39;une erreur qui se produisait de manière aléatoire lors de l&#39;enregistrement d&#39;un workflow après sa modification. (CAMP-48695)
* Correction d’un problème qui empêchait de publier des ressources personnalisées en raison du fait que le schéma de données d’un déclencheur restait inchangé même après la suppression de ce dernier. (CAMP-48523)
* Correction d’un problème qui empêchait le traitement des demandes de feedback loop, car le processus InMail n’était pas en mesure de récupérer les logs de diffusion à mettre à jour. (CAMP-48705)
* Correction d’un problème qui empêchait de définir correctement les options d’exclusion dans l’activité de workflow **Exclusion**.(CAMP-48355)
* Correction d’un problème qui se produisait lorsque les activités d’enrichissement des workflows impliquaient des abonnements ou des désabonnements à un service. Ce problème entraînait un blocage.
* Correction d’un problème qui empêchait l’exécution des workflows.
* Correction d’un problème qui empêchait les utilisateurs de renommer ou de supprimer des groupes de sécurité d’usine de l’interface utilisateur.
* Correction d’un problème qui empêchait les utilisateurs de supprimer un traitement de publication d’événement incomplet.
* Correction d’un problème en raison duquel le workflow de nettoyage de la base échouait avec une erreur. (CAMP-49097)
