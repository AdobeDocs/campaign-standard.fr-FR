---
title: Dernière version
description: Cette page répertorie toutes les versions récentes d’Adobe Campaign Standard.
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
source-git-commit: 86302762a46a814ecc9b14a5fe1bfe1a4a4e0437

---


# Dernière version{#latest-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

## Version 20.3 - Mai 2020      {#release-20-3---may-2020}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>La loi thaïlandaise sur la protection des données personnelles (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La loi thaïlandaise sur la protection des données personnelles (PDPA) est la nouvelle loi sur la protection de la vie privée qui harmonise et modernise les exigences de protection des données en Thaïlande. Ce règlement s’applique aux clients  Adobe Campaign qui détiennent des données pour les sujets de données résidant dans ce pays.</p>
<p>En plus des fonctionnalités de confidentialité déjà disponibles dans  Adobe Campaign (y compris la gestion du consentement, les paramètres de rétention des données et les rôles utilisateur), nous profitons de l’occasion pour inclure des fonctionnalités supplémentaires afin de vous aider à vous préparer à l’application PDPA :</p>
<ul>
<li>Droit d'accès et droit de suppression : nous tirons parti des capacités qui ont été ajoutées au RMPC et à l'ACCP. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#righttoaccess">En savoir plus</a> </li>
<li><p>Lors de la création d’une demande de confidentialité, le type de réglementation PDPA a été ajouté dans le service principal de confidentialité. Cette méthode est celle que vous devez utiliser pour toutes les demandes d'accès et de suppression. L'utilisation de l'API et de l'interface de Campaign pour les demandes d'accès et de suppression est obsolète.  Consultez l'article <a href="../../rn/using/deprecated-features.md">Fonctionnalités obsolètes et supprimées</a>.</p></li>
</ul>
<p>Reportez-vous à la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">vidéo pratique</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API externe  (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Le API <strong></strong> externe  est en cours de transition de la version bêta à la version GA. Cette version apporte une flexibilité supplémentaire à l’analyseur du corps de réponse JSON. Vous pouvez maintenant :</p>
<ul>
<li>analysez un fichier JSON imbriqué avec une profondeur maximale de 10 niveaux. </li>
<li>analysez les propriétés sélectionnées sous forme de noeuds terminaux à partir d’un fichier JSON et aplatissez-les dans une seule ligne de tableau.</li>
<li>sélectionnez et utilisez un objet de tableau à partir d’un JSON sans avoir à nommer l’objet "data" ou le faire au niveau supérieur.</li>
</ul>
<p><strong>Attention :</strong> Les clients devront <strong>remplacer tous les d'API externes bêta par des</strong> d'API externes GA dans leur.  Les  qui utilisent la version bêta de l’API externe cesseront de fonctionner dans la version 20.3.</p>
<p>Pour plus d'informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vidéo de procédure</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Améliorations**

* Le nombre de caractères pouvant être utilisés dans le champ **Préfixe** pour [tester les messages à l’aide d’un](../../sending/using/testing-messages-using-target.md) ciblé est passé de 32 à 500 caractères.
* Le nombre maximal de  en temps réel pouvant être publiés sur une instance est passé de 350 à 2000. (CAMP-41608)

**Améliorations du Concepteur d’email**

* Le concepteur de courrier électronique peut désormais gérer un formatage HTML plus souple que le W3C strict. (CAMP-42529)
* Correction d’un problème lié aux images [](../../designing/using/links.md#inserting-a-link) cliquables afin d’empêcher l’affichage des liens en regard de l’image dans les blocs de contenu. (CAMP-41586)
* Correction d’un problème qui empêchait la redirection vers un lorsque l’URL [de](../../designing/using/links.md#about-tracked-urls) suivi avait un  ajouté dans le modèle. (CAMP-41537)
* Correction d’un problème de remplissage des boutons dans Outlook.
* Correction d’un problème en raison duquel les balises HTML s’affichaient en texte brut.
* La recherche par bloc de contenu affiche désormais les résultats de la recherche sur le serveur, ainsi que les résultats préchargés. (CAMP-41870)

**Autres changements**

* L&#39;interface de publication de ressource personnalisée a été améliorée avec des messages d&#39;erreur plus clairs.
* Les mappages de  non utilisés ont été supprimés de l’interface.
* Les rôles d’administrateur superflus ont été supprimés de l’interface.
* Les cases à cocher peuvent désormais être obligatoires dans un .
* Lors du téléchargement du fichier CSV d’un rapport dynamique, la limite de 200 lignes a été supprimée. Vous pouvez désormais inclure chaque ligne de votre rapport. (CAMP-40810)
* Ajout de la langue ES-US dans le des langues prêtes à l’emploi pour les courriels multilingues. (CAMP-42279)
* Les fichiers téléchargés avec un de  de fichiers de transfert seront désormais supprimés au bout de X jours, où X est déterminé par le champ **Historique en jours** sous le menu **Exécution** dans les propriétés du flux de travail. [En savoir plus](../../automating/using/executing-a-workflow.md#workflow-properties)

**Intégrations d’Experience Platform**

*  d’Adobe [Experience Platform](../../automating/using/aep-targeting-audiences.md) de la **Lecture de l’** dea été amélioré afin d’offrir de meilleures performances et une meilleure stabilité. En outre, les journaux de flux de travail ont été rendus plus clairs et plus détaillés concernant  tâches , ce qui facilite la surveillance et le dépannage lors de la lecture d’Adobe Experience Platform .

**Correctifs**

* Correction d’une erreur qui entraînait la création d’une ressource fantôme lors de la tâche de publication d’une ressource personnalisée.
* Correction d’un problème qui empêchait l’affichage de    si la ressource del’application était étendue avec une ressource personnalisée. (CAMP-41009)
* Correction d’un problème lié aux modèles de  prêts à l’emploi qui affichaient leur contenu en français lors de l’ouverture de l’éditeur. (CAMP-41639)
* Correction d’un problème dans les notifications Push avec un contenu dynamique qui pouvait empêcher l’affichage des émoticônes. (CAMP-40715)
* Correction d’un problème dans le **** qui pouvait entraîner l’affectation d’unincorrect à l’un des de complément sortants. (CAMP-41400)
* Correction d’une erreur qui empêchait la suppression des rapports planifiés. (CAMP-41302)
* Correction d’un problème qui provoquait des incohérences entre le  de  et le rapport Résumé **de l’** dede l’. (CAMP-41145)
* Correction d’un problème qui entraînait un chevauchement des caractères dans les rapports téléchargés.
* Correction d’un problème qui empêchait l’ d’un  de fonctionner pour la substitution de.
* Correction d’une erreur lors de la suppression de champs personnalisés d’une notification locale In-App.
* Correction d’un problème en raison duquel la fonction charIndex ne fonctionnait pas avec un de transfert **de** fin **ou de** fichier   dans un flux de travail.
* Correction d’un problème dans les  de qui pouvait se produire lors de l’utilisation d’un **de** de avec deux d’entrée, y compris des ressources de ayant un lien entre eux. (CAMP-42133)
* Correction d’un problème qui empêchait l’exécution d’un processus lors de l’utilisation de fonctions inconnues. (CAMP-41873)
* Correction d’un problème dans les  de qui pouvait se produire lors de la création de  de  à l’aide de plusieurs **de** desauvegarde avec un complément aux sortants. (CAMP-39992)
* Correction d’un problème en raison duquel les données étaient incohérentes lors de l’utilisation de la personnalisation dans les courriers électroniques transactionnels. (CAMP-41842)
* Correction de problèmes survenant lors de la suppression de champs personnalisés dans le de notification Push. (CAMP-37586)
* Correction d’une erreur qui empêchait les utilisateurs d’apporter des modifications aux rapports. (CAMP-42505)
