---
title: Dernière version
description: Cette page répertorie toutes les versions récentes d'Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8b02b81ef27c8415bc5bcce41178dfbfc90670cf

---


# Dernière version{#latest-release}

[Calendrier des versions](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2019.md) | [Fonctionnalités obsolètes](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.1.2 - Février 2020 {#release-20-1-2---february-2020}

**Améliorations du Concepteur d&#39;email**

Correction d’un problème en raison duquel un élément de balise HTML était ajouté dans un fragment obsolète lors de l’application de correctifs, puis de l’enregistrement du contenu. (CAMP-40685) Correction d’un problème qui entraînait l’ajout d’un espace lors de l’utilisation de contenu dynamique. (CAMP-40605) Correction d’un problème lors de la configuration d’un modèle de courrier électronique transactionnel. (CAMP-40604)

## Version 20.1 - Février 2020 {#release-20-1---february-2020}

**Nouveautés**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Connecteur de données Adobe Experience Platform (bêta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le connecteur de données Adobe Experience Platform est désormais intégré à Adobe Campaign Standard. Vous pouvez rendre vos données de campagne disponibles sur Adobe Experience Platform en mappant les données XTK (données assimilées dans Campaign) au modèle de données de la plateforme Adobe Experience Platform (XDM). </p>
    <p>Notez que cette fonctionnalité n'est disponible que pour les clients hébergés sur Azure. Pour plus d’informations sur cette fonctionnalité et les conditions d’activation, reportez-vous à la documentation <a href="../../administration/using/aep-about-data-connector.md"></a> détaillée et à la vidéo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html"></a>comment l’activer.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Destinations d’audience (bêta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Destinations d’audience vous permet de partager des segments d’Adobe Experience Platform vers Adobe Campaign.</p>
    <p>Notez que cette fonctionnalité n'est disponible que pour les clients hébergés sur Azure. Pour plus d’informations sur cette fonctionnalité et les conditions d’activation, reportez-vous à la documentation <a href="../../audiences/using/aep-about-audience-destinations-service.md"></a> détaillée et à la vidéo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html"></a>comment l’activer. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Disponibilité mondiale de l&#39;accord de libre-échange amélioré : les messages (y compris les messages transactionnels) sont désormais envoyés par la MTA améliorée d’Adobe Campaign, qui fournit une infrastructure d’envoi améliorée permettant une meilleure délivrabilité, un débit et une gestion des rebonds améliorés. [En savoir plus](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* La gestion du fuseau horaire a été améliorée. Vous pouvez désormais définir un fuseau horaire [spécifique](../../automating/using/building-a-workflow.md) pour l’ensemble d’un processus. Le fuseau horaire sélectionné s’applique à toutes les activités du processus. Les informations sur le fuseau horaire configuré pour l’opérateur ou le serveur s’affichent désormais dans l’interface (dans les journaux et après avoir sélectionné un fuseau horaire). (CAMP-37672)

* Les API de Campaign Standard vous permettent désormais d’effectuer une pagination lors de l’utilisation de tableaux volumineux, en ajoutant le `_forcePagination=true` paramètre à votre URL d’appel. [En savoir plus](../../api/using/pagination.md)

* L’ID du journal de diffusion (qui est un identifiant unique pour chaque journal) est désormais disponible dans les ressources des journaux de diffusion et des journaux de suivi pour toutes les dimensions de ciblage. Cela permet d’identifier l’envoi ou le suivi des journaux lors de l’exportation, par exemple. [En savoir plus](../../automating/using/exporting-logs.md)

**Améliorations du Concepteur d&#39;email**

* Ajout d’instructions de texte obligatoire manquantes lors de la création d’une audience.
* Correction d’un problème en cliquant sur le bouton **Modifier le contenu** dans l’assistant de l’éditeur de courrier électronique hérité.
* Correction d’un problème qui empêchait l’alignement des en-têtes avec le contenu du rapport Résumé du service. (CAMP-38103)
* Correction d’un problème qui empêchait la suppression des variantes de contenu dynamique sans affecter le reste de la ligne d’objet. (CAMP-40096)
* Correction d’un problème de test A/B lors de l’utilisation de la variante B sur la ligne d’objet. (CAMP-40327)
* Correction d’un problème en raison duquel vous ne pouviez pas faire glisser et déposer des fichiers lors de l’utilisation de la fonction d’importation de code HTML de téléchargement. (CAMP-39326)
* Correction d’un problème qui empêchait la copie et le collage de texte à partir d’un éditeur de texte. (CAMP-39028)
* Correction d’un problème qui empêchait l’affichage des suggestions de mots. (CAMP-38970)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer des fragments. (ATU-2447)

**Autres changements**

* Le filtre &quot;Livraisons avec échec de la préparation&quot; prend désormais en compte la date de création des livraisons plutôt que la date de dernière modification.
* L’unité organisationnelle du groupe de sécurité Administrateurs ne peut plus être modifiée.
* Lors de la création d’un profil, le champ Unité organisationnelle doit maintenant être rempli.
* Déclencheur Experience Cloud ne peut désormais être supprimé que si l’événement et le modèle transactionnel qui y sont liés sont supprimés.

**Correctifs**

* Correction d’un problème lors de l’exécution d’une demande de suppression de confidentialité qui empêchait la suppression des données utilisateur dans les journaux d’exclusion. (CAMP-39003)
* Correction d’un problème qui provoquait des problèmes d’accessibilité lors du redimensionnement du texte dans un élément de conteneur.
* Correction d’un problème qui empêchait les utilisateurs de fermer la fenêtre contextuelle Calendrier qui s’affichait lors du survol dans les activités marketing.
* Correction d’un problème dans l’ **[!UICONTROL External API]** activité qui affichait le **[!UICONTROL Confirm]** bouton même lorsqu’aucune donnée n’était modifiée.
* Correction d’un problème lors de l’utilisation d’une **[!UICONTROL Union]** activité sur des requêtes avec des dimensions cibles différentes. Les données de transition n’affichaient que les enregistrements de la dimension de ciblage du jeu principal. (CAMP-36831)
* Correction d’un problème susceptible d’entraîner une erreur lors de l’utilisation d’une **[!UICONTROL Reconciliation]** activité dans des contextes spécifiques, par exemple avec deux activités entrantes, l’une étant une activité d’exclusion. (CAMP-37490)
* Correction de problèmes de performances qui pouvaient survenir lors de la sélection et de la mise à jour des profils de test. (CAMP-37976)
* Correction d’un problème en raison duquel les pages d’erreur pouvaient s’afficher lors de l’abonnement ou du désabonnement via les pages d’entrée. (CAMP-37771)
* Correction d’un problème survenant lors du téléchargement de contenu au format zip, avec des fichiers PNG référencés dans le code HTML avec leur extension en majuscules. (CAMP-37913)
* Correction d’un problème qui empêchait l’envoi de messages in-app lors de l’ajout d’un profil de test à la diffusion.
* Correction d’une erreur avec l’activité de flux de travaux API externe qui échouait lorsqu’elle était liée à des activités d’enrichissement.
* Correction d’un problème en raison duquel l’état des messages SMS pouvait s’afficher incorrectement.
* Correction d’un problème lié aux ressources personnalisées en raison duquel les entrées en double apparaissaient sous différents points de fin d’API.
* Correction d’un problème qui empêchait la disponibilité des pages d’entrée après publication. (CAMP-38695)
* Correction d’un bogue qui se produisait lors de l’affichage des données d’une transition Intersection provenant de deux ressources différentes. (CAMP-38974)
* Correction d’un problème en raison duquel la valeur d’énumération dans un modèle de remise était incorrectement définie. (CAMP-38388)
* Correction d’une erreur en raison de laquelle les diffusions en vrac par courrier électronique affichaient l’état des remises comme En attente et l’état Envoyé comme Terminé. (CAMP-35355)
* Correction d’une erreur qui affichait incorrectement le domaine de l’expéditeur dans les rapports dynamiques. (CAMP-33123)
* Correction d’un problème qui provoquait des incohérences dans le nombre d’annulation d’abonnement dans les rapports dynamiques. (CAMP-39949)
* Correction d’un problème qui empêchait l’affichage des adresses dans l’écran Envoi des journaux lors de l’envoi de messages in-app.
* Correction d’un problème qui empêchait la mise à jour des journaux d’envoi SMS avec le nombre correct de rebonds. (CAMP-38395)
