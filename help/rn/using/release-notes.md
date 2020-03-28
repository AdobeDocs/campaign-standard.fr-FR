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
source-git-commit: c4500832b87e986cdbbbf72b9b8c0591f64f7da8

---


# Dernière version{#latest-release}

[Calendrier des versions](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Versions du panneau de contrôle](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Mises à jour de la documentation](../../rn/using/documentation-updates.md) | [Notes de mise à jour précédentes](../../rn/using/release-notes-2019.md) | [Fonctionnalités obsolètes](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.2 - Mars 2020     {#release-20-2---march-2020}

**Nouveautés**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Intégration d'objets blob Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Le connecteur de Azure Blob  peut désormais être utilisé pour importer ou exporter des données vers les  à l'aide d'un de flux de travail de fichier <strong>de</strong> transfert. </p>
    <p>Pour plus d'informations, consultez la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentation détaillée</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Test par courrier électronique à l’aide d’un ciblé</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Outre le  de test, vous pouvez maintenant tester vos courriels sur des  ciblées réelles. Cela vous permet d’obtenir une représentation exacte du message que le recevra : champs personnalisés, informations dynamiques et personnalisées, y compris les données supplémentaires des , etc. </p>
    <p>For more information, refer to the <a href="../../sending/using/testing-messages-using-target.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">tutorial video</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>De nouvelles fonctionnalités seront disponibles dans Campaign Panneau de configuration en avril, notamment la gestion des enregistrements Google TXT, la surveillance de l’espace de base de données et les alertes par courrier électronique. Pour en savoir plus sur ces fonctionnalités, consultez la Note [de mise à jour du Panneau de](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)configuration.

**Améliorations**

* L&#39;expérience utilisateur de la messagerie transactionnelle a été améliorée et la cohérence de l&#39;interface a été améliorée. [En savoir plus](../../channels/using/about-transactional-messaging.md)
* Campaign Standard vous permet désormais d’envoyer des pour tester les  à l’aide de données supplémentaires provenant de l’ de l’analyse.
* Les garde-fous pour le d&#39;API externe  ont été mis à jour. [En savoir plus](../../automating/using/external-api.md)

**Améliorations du Concepteur d&#39;email**

* Correction d’un problème affectant l’échappement lorsque vous cliquiez plusieurs fois sur une image personnalisée.
* Correction d’un problème lors de la duplication de composants de texte dynamique, en raison duquel la mauvaise ligne était dupliquée. (CAMP-41249)
* Correction d’un problème de remplissage dans Outlook lors de la définition du remplissage au niveau du tableau et non au niveau div.
* Correction d’un problème en raison duquel la largeur d’une image était modifiée lors du passage en mode HTML. (CAMP-41116)
* Correction d’un problème qui empêchait l’accessibilité du composant de médias sociaux lors de la fourniture d’un texte alternatif aux icônes. (CAMP-41345)
* Correction d’un problème en raison duquel les balises visibles `<br>` s’affichaient lors de l’utilisation du copier-coller dans le concepteur de courrier électronique.
* Correction d’un problème en raison duquel les balises HTML s’affichaient dans le courrier électronique après le passage du contenu HTML au texte ordinaire. (CAMP-41138)
* Correction d’un problème empêchant le rendu des boutons avec une seule bordure définie.
* Correction d’un problème de retrait HTML en raison duquel le pied de page des courriers électroniques se déplaçait vers la gauche dans Microsoft Outlook. (CAMP-40987)
* Correction d’un problème en raison duquel  ciblage d’un attribut de collection défini en HTML était copié dans le contenu en texte brut lors du passage en mode texte brut. (CAMP-40365)
* Correction d’un problème qui empêchait l’insertion de liens sur un segment de texte sélectionné. (CAMP-41406)
* Correction d’un problème en raison duquel la date était modifiée lors de la sélection d’un fuseau horaire dans l’éditeur de  du. (CAMP-38277)

**Autres changements**

* La réconciliation des **IPC avec le flux de travaux prêt à l’emploi d’Adobe Analytics** s’exécute désormais jusqu’à la date actuelle au lieu de s’exécuter pendant une seule journée.
* Le MCPNS ne prend pas en charge l’ajout d’APNS et d’APNS-SANDBOX en tant que plateformes dans une application. Une fois le certificat ajouté avec succès dans  Adobe Campaign Standard, vous ne pouvez plus modifier vos paramètres depuis qu’une seule plateforme APNS (production ou sandbox) peut être ajoutée à l’application MCPNS.

**Intégrations de plateformes d’expérience**

>[!NOTE]
>
>Les fonctionnalités d’Adobe Experience Platform dans Campaign Standard sont actuellement en version bêta, qui peuvent faire l’objet de fréquentes mises à jour sans préavis. Reportez-vous à la documentation détaillée : Connecteur [de données de la plateforme](../../administration/using/aep-about-data-connector.md)d’expérience, [ destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Dans les journaux de processus, toutes les 10 minutes, Campaign affiche désormais le nombre d’enregistrements déjà traités par la tâche en cours d’exécution.
* Correction d’un problème qui pouvait se produire lors de l’importation d’un Adobe Experience Platform qui avait été supprimé de la base de données.
* Correction d’un problème dans les journaux de flux de travail, en raison duquel un résultat incorrect pouvait s’afficher pour le nombre total d’enregistrements importés.

**Correctifs**

* Correction d’un problème lié au  de flux de travail **de** qui pouvait se produire lors de l’ajout d’espaces dans le champ **Alias** qui créait ensuite un nouvel élément de ligne. (CAMP-39229)
* Correction d’un problème en raison duquel chaque de test pouvait être ciblé lors de l’envoi d’un message de.
* Correction d’un problème survenant après l’annulation de la publication et la suppression d’une configuration de  de. [En savoir plus](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Correction d’un problème en raison duquel le bouton **Enregistrer** disparaissait lors des modifications apportées au  du.
* Correction d’un problème lors de la suppression manuelle d’une demande de confidentialité Campaign après son traitement, qui empêchait la suppression des données associées à la demande même après le nettoyage.
* Correction d’un problème qui pouvait se produire lors de la prévisualisation ou de l’envoi de messages contenant des caractères spéciaux d’Adobe Experience Manager.
* Correction d’un problème qui pouvait se produire dans les  de lors de l’exécution d’un  de avec plusieurs entrants.