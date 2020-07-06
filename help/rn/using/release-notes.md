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
translation-type: ht
source-git-commit: 04bc32a9abb2939823f18165e1fe46d9f2315cce
workflow-type: ht
source-wordcount: '1054'
ht-degree: 100%

---


# Dernière version{#latest-release}

[Calendrier des versions](../../rn/using/release-planning.md) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2020.md) | [Fonctionnalités obsolètes](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Version de juin du nouveau panneau de contrôle** avec surveillance des profils actifs, audit de délivrabilité des sous-domaines et gestion des clés GPG. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html).

## Version 20.3 - Mai 2020 {#release-20-3---may-2020}

**Nouveautés**

<table> 
<thead> 
<tr> 
<th> <strong>Loi thaïlandaise sur la protection des données personnelles (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La loi thaïlandaise sur la protection des données personnelles (PDPA) est la nouvelle loi sur la protection de la vie privée qui harmonise et modernise les exigences en matière de protection des données de la Thaïlande. Ce règlement s’applique aux clients Adobe Campaign qui détiennent des données pour des titulaires de données résidant dans ce pays.</p>
<p>Outre les fonctionnalités de confidentialité déjà disponibles dans Adobe Campaign (notamment la gestion du consentement, les paramètres de conservation des données et les rôles utilisateur), nous profitons de l’occasion pour inclure d’autres fonctionnalités afin de faciliter votre préparation au PDPA :</p>
<ul>
<li>Droit d'accès et droit de suppression : nous tirons parti des capacités qui ont été ajoutées pour le RGPD et le CCPA. <a href="https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#righttoaccess">En savoir plus</a> </li>
<li><p>Lors de la création d’une demande d'accès à des informations personnelles, le type de réglementation PDPA a été ajouté à Privacy Core Service. Cette méthode est celle que vous devez utiliser pour toutes les demandes d'accès et de suppression. L'utilisation de l'API et de l'interface de Campaign pour les demandes d'accès et de suppression est obsolète.  Consultez l'article <a href="../../rn/using/deprecated-features.md">Fonctionnalités obsolètes et supprimées</a>.</p></li>
</ul>
<p>Reportez-vous à la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">vidéo pratique</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Activité API externe (DG)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>L’activité <strong>API externe</strong> est en cours de transition de la version bêta vers la version DG (disponibilité générale). Cette version apporte une flexibilité supplémentaire à l’analyseur du corps de réponse JSON. Vous pouvez maintenant :</p>
<ul>
<li>analyser un JSON imbriqué avec une profondeur maximale de 10 niveaux ; </li>
<li>analyser les propriétés sélectionnées sous forme de nœuds feuilles à partir d’un JSON et les aplatir en une seule ligne de tableau ;</li>
<li>sélectionner et utiliser un objet de tableau à partir d’un JSON sans avoir à nommer l’objet « data » ou le mettre au niveau supérieur.</li>
</ul>
<p><strong>Attention :</strong> les clients devront <strong>remplacer toutes les activités API externes bêta</strong> par des activités API externes DG dans leurs workflows.  Les workflows qui utilisent la version bêta de l’API externe cesseront de fonctionner dans la version 20.3.</p>
<p>Pour plus d'informations, consultez la <a href="../../automating/using/external-api.md">documentation détaillée</a> et la <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">vidéo de procédure</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

![](assets/do-not-localize/cp-icon.png) **Version de mai du nouveau panneau de contrôle** avec renouvellement de certificat pour les sous-domaines CNAME. [En savoir plus](https://docs.adobe.com/content/help/fr-FR/control-panel/using/release-notes.html).

**Améliorations**

* Le nombre de caractères pouvant être utilisés dans le champ **Préfixe** pour [tester les messages à l’aide de profils ciblés](../../sending/using/testing-messages-using-target.md) est passé de 32 à 500 caractères.
* Le nombre maximal d’événements en temps réel pouvant être publiés sur une instance est passé de 350 à 2 000. (CAMP-41608)
* La synchronisation entre Adobe Launch et Campaign Standard a été améliorée grâce à l’utilisation du workflow technique syncWithLaunch. Ce workflow permet l’import automatique de toutes les propriétés mobiles d’Adobe Launch dans Adobe Campaign Standard. Pour plus d’informations, consultez [cette page](../../administration/using/technical-workflows.md).

   Vous devrez envoyer une demande à l’Assistance client d’Adobe (directement ou par l’intermédiaire de votre contact Adobe) pour que le workflow technique syncWithLaunch soit activé dans votre instance Campaign. (CAMP-40082)

**Améliorations du Concepteur d’email**

* Le Concepteur d’email peut maintenant gérer une mise en forme HTML plus flexible que le W3C strict. (CAMP-42529)
* Correction d’un problème lié aux [images cliquables](../../designing/using/links.md#inserting-a-link) afin d’empêcher l’affichage des liens en regard de l’image dans les blocs de contenu. (CAMP-41586)
* Correction d’un problème qui empêchait la redirection vers une landing page lorsqu’une catégorie de l’[URL trackée](../../designing/using/links.md#about-tracked-urls) était ajoutée dans le modèle. (CAMP-41537)
* Correction d’un problème lié aux marges intérieures des boutons dans Outlook.
* Correction d’un problème en raison duquel les balises HTML s’affichaient sous la forme de texte brut.
* La recherche des blocs de contenu affiche maintenant les résultats de la recherche sur le serveur, ainsi que les résultats préchargés. (CAMP-41870)

**Autres changements**

* L’interface de publication des ressources personnalisées a été améliorée. Elle propose maintenant des messages d’erreur plus clairs.
* Les mappings de diffusion inutilisés ont été supprimés de l’interface.
* Les rôles d’administrateur inutiles ont été supprimés de l’interface.
* Les cases à cocher peuvent maintenant être obligatoires dans une landing page.
* Lors du téléchargement du fichier CSV d’un rapport dynamique, la limite de 200 lignes a été supprimée. Vous pouvez maintenant inclure chaque ligne de votre rapport. (CAMP-40810)
* Ajout de la langue ES-US dans la liste des langues d’usine pour les emails multilingues. (CAMP-42279)
* Les fichiers téléchargés avec une activité de transfert de fichier seront désormais supprimés au bout de X jours, où X est déterminé par le champ **Jours d’historique** sous le menu **Exécution** dans les propriétés du workflow. [En savoir plus](../../automating/using/managing-execution-options.md)

**Intégrations d’Experience Platform**

*  L’activation des [audiences Experience Platform](../../automating/using/aep-targeting-audiences.md) d’Adobe depuis l’activité **Lecture d’audience** a été améliorée afin d’offrir des performances optimisées et une meilleure stabilité. En outre, les logs des workflows ont été rendus plus clairs et plus détaillés en ce qui concerne les traitements d’activation, ce qui facilite le monitoring et la résolution des problèmes lors de la lecture des audiences d’Adobe Experience Platform.

**Correctifs**

* Correction d’une erreur qui entraînait la création d’une ressource fantôme lors du traitement de publication d’une ressource personnalisée.
* Correction d’un problème qui empêchait l’affichage de l’historique marketing des profils si la ressource de profil était étendue avec une ressource personnalisée. (CAMP-41009)
* Correction d’un problème lié aux modèles de landing page d’usine qui affichaient leur contenu en français lors de l’ouverture de l’éditeur. (CAMP-41639)
* Correction d’un problème lié aux notifications push avec un contenu dynamique qui pouvait empêcher l’affichage des emojis. (CAMP-40715)
* Correction d’un problème dans l’activité de **Déduplication** qui pouvait entraîner l’affectation d’un code segment incorrect à l’une des transitions de complémentaire sortantes. (CAMP-41400)
* Correction d’une erreur qui empêchait la suppression des rapports planifiés. (CAMP-41302)
* Correction d’un problème qui entraînait des incohérences entre le tableau de bord des diffusions et le rapport **Synthèse des diffusions**. (CAMP-41145)
* Correction d’un problème qui entraînait un chevauchement des caractères dans les rapports téléchargés.
* Correction d’un problème qui empêchait l’aperçu d’une diffusion de fonctionner pour la substitution des bons à tirer.
* Correction d’une erreur lors de la suppression de champs personnalisés d’une notification locale In-App.
* Correction d’un problème qui empêchait la fonction charIndex de fonctionner avec une activité de **Fin** ou de **Transfert de fichier** dans un workflow.
* Correction d’un problème lié aux workflows qui pouvait se produire lors de l’utilisation d’une activité d’**Enrichissement** avec deux activités d’entrée incluant des ressources cibles ayant un lien entre elles. (CAMP-42133)
* Correction d’un problème qui empêchait l’exécution d’un workflow lors de l’utilisation de fonctions inconnues. (CAMP-41873)
* Correction d’un problème lié aux workflows qui pouvait se produire lors de la création d’audiences à l’aide de plusieurs activités de **Sauvegarde d’audience** avec des transitions de complémentaire sortantes. (CAMP-39992)
* Correction d’un problème qui entraînait des incohérences dans les données lors de l’utilisation de la personnalisation dans les emails transactionnels. (CAMP-41842)
* Correction de problèmes qui se produisaient lors de la suppression de champs personnalisés dans les diffusions de notifications push. (CAMP-37586)
* Correction d’une erreur qui empêchait les utilisateurs d’apporter des modifications aux rapports. (CAMP-42505)
