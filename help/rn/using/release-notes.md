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
source-git-commit: 14f764b92fef81c06551fb0f13b11b41e94095f0

---


# Dernière version{#latest-release}

[Calendrier des versions](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2019.md) | [Fonctionnalités obsolètes](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.1.4 - Février 2020    {#release-20-1-4---february-2020}

* Correction d’un problème lors de l’ouverture d’une activité Public **** lu sur des processus existants. (CAMP-41002)

## Version 20.1.3 - Février 2020    {#release-20-1-3---february-2020}

* Correction d’un problème de régression introduit dans la version 20.1 par CAMP-39273 pour les clients qui utilisaient la boucle. Le CAMP-39273 a été annulé.

## Version 20.1.2 - Février 2020    {#release-20-1-2---february-2020}

**Améliorations du Concepteur d&#39;email**

* Correction d’un problème en raison duquel un élément de balise HTML était ajouté dans un fragment obsolète lors de l’application de correctifs, puis de l’enregistrement du contenu. (CAMP-40685)
* Correction d’un problème en raison duquel un espace était ajouté lors de l’utilisation du contenu dynamique. (CAMP-40605)
* Correction d’un problème lors de la configuration d’un modèle de courrier électronique transactionnel. (CAMP-40604)

## Version 20.1 - Février 2020 {#release-20-1---february-2020}

**Nouveautés**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (version bêta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector est maintenant intégré avec Adobe Campaign Standard. Vous pouvez rendre vos données Campaign disponibles sur Adobe Experience Platform en mappant les données XTK (données ingérées dans Campaign) sur le modèle de données Adobe Experience Platform (XDM). </p>
    <p>Remarque : cette fonctionnalité n’est disponible que pour les clients hébergés sur Azure. For more information about this capability and conditions to activate it, refer to the <a href="../../administration/using/aep-about-data-connector.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">how-to video</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (version bêta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations permet de partager des segments d’Adobe Experience Platform avec Adobe Campaign.</p>
    <p>Remarque : cette fonctionnalité n’est disponible que pour les clients hébergés sur Azure. For more information about this capability and conditions to activate it, refer to the <a href="../../audiences/using/aep-about-audience-destinations-service.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">how-to video</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Améliorations**

* Disponibilité générale du MTA amélioré : les messages (y compris les messages transactionnels) sont maintenant envoyés par le MTA amélioré d’Adobe Campaign. Ce MTA est doté d’une version mise à niveau de l’infrastructure d’envoi qui permet d’améliorer la délivrabilité, le débit et la gestion des bounces. [En savoir plus](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* La gestion des fuseaux horaires a été améliorée. Vous pouvez maintenant définir un [fuseau horaire spécifique](../../automating/using/building-a-workflow.md) pour l’ensemble d’un workflow. Le fuseau horaire sélectionné s’applique à toutes les activités du workflow. Les informations sur le fuseau horaire, configurées pour l’opérateur ou le serveur, s’affichent maintenant dans l’interface (dans les logs et après avoir sélectionné un fuseau horaire). (CAMP-37672)

* Les API de Campaign Standard permettent maintenant d’effectuer une pagination lors de l’utilisation de tables volumineuses, en ajoutant le paramètre `_forcePagination=true` à votre URL d’appel. [En savoir plus](../../api/using/pagination.md)

* L’identifiant de log de diffusion (unique pour chaque log) est maintenant disponible dans les ressources des logs de diffusion et de tracking pour toutes les dimensions de ciblage. Vous pouvez ainsi identifier les logs d’envoi ou de tracking, par exemple lors d’un export. [En savoir plus](../../automating/using/exporting-logs.md)

**Améliorations du Concepteur d&#39;email**

* Ajout d’instructions de texte obligatoires manquantes lors de la création d’une audience.
* Correction d’un problème qui se produisait lorsqu’un utilisateur cliquait sur le bouton **Changer de contenu** dans l’assistant de l’ancien éditeur d’email.
* Correction d’un problème qui empêchait l’alignement des en-têtes avec le contenu du rapport Synthèse du service. (CAMP-38103)
* Correction d’un problème qui empêchait la suppression des variantes de contenu dynamique sans répercussion sur le reste de la ligne d’objet. (CAMP-40096)
* Correction d’un problème de test A/B lors de l’utilisation de la variante B sur la ligne d’objet. (CAMP-40327)
* Correction d’un problème qui empêchait d’effectuer un glisser-déposer des fichiers avec la fonctionnalité de chargement d’import de code HTML. (CAMP-39326)
* Correction d’un problème qui empêchait d’effectuer un copier-coller de texte à partir d’un éditeur de texte. (CAMP-39028)
* Correction d’un problème qui empêchait l’affichage des suggestions de mots. (CAMP-38970)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer des fragments. (ATU-2447)
* Correction d’un problème empêchant la duplication des structures dynamiques. (CAMP-38367)
* Correction d’un problème empêchant le contenu dynamique de conserver les conditions en cas de duplication. (CAMP-39051)

**Autres changements**

* Le filtre « Diffusions avec préparation en échec » prend maintenant en compte la date de création des diffusions plutôt que la date de dernière modification.
* Il n’est plus possible de modifier les entités organisationnelles du groupe de sécurité Administrateurs.
* Lors de la création d’un profil, le champ Entité organisationnelle doit maintenant être renseigné.
* Un trigger Experience Cloud ne peut maintenant être supprimé que si l’événement et le modèle transactionnel associés sont aussi supprimés.
* Adobe Creative SDK a été mis hors service. Elle est désormais obsolète dans Campaign Standard. See the [Deprecated and removed features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) page.


**Correctifs**

* Correction d’un problème lors de l’exécution d’une demande de suppression de confidentialité qui empêchait la suppression des données utilisateur dans les journaux d’exclusion. (CAMP-39003)
* Correction d’une erreur qui entraînait des problèmes d’accessibilité lors du redimensionnement du texte dans un élément de conteneur.
* Correction d’un problème qui empêchait les utilisateurs de fermer la fenêtre contextuelle Calendrier qui s’affichait lorsqu’ils pointaient sur des activités marketing.
* Fixed an issue in the **[!UICONTROL External API]** activity which displayed the **[!UICONTROL Confirm]** button even when no data was modified.
* Correction d’un problème lors de l’utilisation d’une activité **[!UICONTROL Union]** sur des requêtes avec des dimensions cibles différentes. Les données de transition n’affichaient que les enregistrements de la dimension de ciblage du jeu principal. (CAMP-36831)
* Fixed an issue that could lead to an error when using a **[!UICONTROL Reconciliation]** activity in specific contexts, for example with two inbound activities, one of them being an exclusion activity. (CAMP-37490)
* Correction de problèmes de performances possibles lors de la sélection et de la mise à jour des profils de test. (CAMP-37976)
* Correction d’un problème qui entraînait l’affichage de pages d’erreur lors d’un abonnement ou d’un désabonnement via les landing pages. (CAMP-37771)
* Correction d’un problème qui se produisait lors du téléchargement de contenu au format zip, comportant des fichiers PNG référencés dans le code HTML avec des extensions en majuscules. (CAMP-37913)
* Correction d’un problème qui empêchait l’envoi de messages In-app lors de l’ajout d’un profil de test à la diffusion.
* Correction d’une erreur liée à l’activité de workflow API externe qui échouait lorsqu’elle était liée à des activités d’enrichissement.
* Correction d’un problème susceptible d’entraîner l’affichage incorrect de l’état des messages SMS.
* Correction d’un problème lié aux ressources personnalisées qui entraînait l’apparition d’entrées en double pour différents points d’entrée d’API.
* Correction d’un problème qui empêchait la disponibilité des landing pages après publication. (CAMP-38695)
* Correction d’un bogue qui se produisait lors de l’affichage des données d’une transition Intersection provenant de deux ressources différentes. (CAMP-38974)
* Correction d’un problème qui entraînait une définition incorrecte de la valeur d’énumération dans un modèle de diffusion. (CAMP-38388)
* Correction d’une erreur lors de diffusions email en masse, qui entraînait l’affichage de l’état des diffusions En attente et de l’état Envoyé comme Terminé. (CAMP-35355)
* Correction d’une erreur qui affichait incorrectement le domaine de l’expéditeur dans les rapports dynamiques. (CAMP-33123)
* Correction d’un problème qui entraînait des incohérences dans le nombre de désabonnements dans les rapports dynamiques. (CAMP-39949)
* Correction d’un problème qui empêchait l’affichage des adresses dans l’écran Logs d’envoi lors de l’envoi de messages In-app.
* Correction d’un problème qui empêchait la mise à jour des logs d’envoi des SMS avec le nombre correct de bounces. (CAMP-38395)
* Correction d’une faille qui permettait aux appels de publication de l’abonnement à l’application de mettre à jour les jetons de notification Push. (CAMP-39273)
