---
title: Planification de la publication de Campaign Standard
description: Cette page répertorie les prochaines versions d’Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 184a878f7be573a6b45a3a2853c07029432392f0

---


# Planification des versions {#release-planning}

Adobe perfectionne constamment ses solutions en ajoutant de nouvelles fonctions, des améliorations et des correctifs.

Toutes les instances Adobe Campaign Standard sont mises à niveau à chaque nouvelle version. Aucune action n&#39;est requise pour la mise à niveau.

Les mises à niveau sont déployées en deux phases. En premier lieu, les instances de test sont mises à niveau pour permettre à nos clients de tester les nouvelles fonctionnalités et d&#39;adapter leur configuration si nécessaire. Ensuite, les instances de production sont mises à niveau.

Toutes les dates de publication sont sujettes à modification : nous vous recommandons de visiter cette page régulièrement pour vérifier les mises à jour.

Abonnez-vous pour [recevoir des notifications](https://www.adobe.com/subscription/priority-product-update.html) de mise à jour afin d’obtenir des détails sur les dernières versions d’Adobe Experience Cloud directement dans votre boîte de réception.

## Version 20.1.4 - Mise à jour de la version de février {#release-20-1-4---february-release-update}

Les mises à jour d’environnement se produisent par vagues, pendant les périodes indiquées ci-dessous. Des informations détaillées sur cette version sont disponibles dans les Notes [de](../../rn/using/release-notes.md)mise à jour. Si vous avez d’autres questions, contactez le service à la clientèle [Adobe](https://support.neolane.net/webApp/extranetLogin).

<table> 
 <thead> 
  <tr> 
   <th> Environnement<br /> </th> 
   <th> Dates <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Etape<br /> </td> 
   <td> 17-18 février 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> Production<br /> </td> 
   <td> 20 février au 5 mars 2020<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Questions et réponses {#questions-and-answers}

**Q : Quel est l&#39;impact ?**

A : Les modifications sont répertoriées dans les Notes [de](../../rn/using/release-notes.md)mise à jour, y compris les liens vers la documentation connexe. Adobe recommande également de consulter la page [Fonctions](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)obsolètes et supprimées. Ces pages sont disponibles pour la nouvelle version à la date de mise à niveau de l’environnement Stage.

**Q : Quel est le processus de validation ?**

A : À mesure que votre instance d’évaluation est mise à niveau, Adobe conseille de valider vos processus et les cas d’utilisation fonctionnent correctement avec cette nouvelle version et de signaler tout problème au service à la clientèle [](https://support.neolane.net/webApp/extranetLogin)Adobe.

**Q : Y aura-t-il accès à l’instance pendant le processus de mise à niveau ?**

A :Non. Lors de la mise à niveau de l’instance, il se peut que la base de données ne soit pas accessible pendant quelques minutes. Tous les processus redémarrent automatiquement.

**Q : Les messages continueront-ils à être envoyés ?**

A :Non. Les messages ne seront pas envoyés pendant quelques minutes. Dès que la mise à niveau est terminée, les processus sont automatiquement redémarrés.

**Q : Les processus continueront-ils à s’exécuter et à envoyer les livraisons ?**

A :Non. Lors de la mise à niveau de la version, le serveur de flux de travail et MTA sont arrêtés. Cela signifie que les processus ne s’exécuteront pas et que les livraisons ne seront pas envoyées pendant quelques minutes. Aucune action n’est requise : les processus redémarrent dès que l’instance est mise à niveau.

**Q : Le suivi des liens dans les messages fonctionnera-t-il toujours lors de la mise à niveau ?**

A : Oui, ils marcheront. Les nouveaux courriers électroniques ne peuvent pas être envoyés pendant la mise à niveau, mais les liens de suivi inclus dans les courriers électroniques déjà envoyés seront opérationnels.

**Q : Comment savoir si la mise à niveau est terminée ?**

A : Lors de la connexion à Campaign, une fenêtre contextuelle de notification de mise à jour s’affiche, avec la dernière version.

Pour toute autre question, contactez le service à la clientèle [Adobe](https://support.neolane.net/webApp/extranetLogin).