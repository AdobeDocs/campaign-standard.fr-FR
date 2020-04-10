---
title: Calendrier des versions de Campaign Standard
description: Cette page répertorie toutes les versions à venir d’Adobe Campaign Standard.
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
source-git-commit: a71af00e606d78c4ff8b39da1b9f032c0dcf0fc6

---


# Calendrier des versions {#release-planning}

Adobe perfectionne constamment ses solutions en ajoutant de nouvelles fonctions, des améliorations et des correctifs.

Toutes les instances Adobe Campaign Standard sont mises à niveau à chaque nouvelle version. Aucune action n&#39;est requise pour la mise à niveau.

Les mises à niveau sont déployées en deux phases. En premier lieu, les instances de test sont mises à niveau pour permettre à nos clients de tester les nouvelles fonctionnalités et d&#39;adapter leur configuration si nécessaire. Ensuite, les instances de production sont mises à niveau.

Toutes les dates de publication peuvent faire l’objet de modifications. Nous vous recommandons de consulter régulièrement cette page pour vérifier la présence de mises à jour.

**NOUVEAU !** Abonnez-vous à [Campaign Standard notifications](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) de mise à jour pour obtenir des détails sur les prochaines versions directement dans votre boîte de réception.

## Version 20.3.1 - Version de mai {#release-20-3-may-release}

Les mises à jour des environnements s’effectuent par vagues, selon les dates indiquées ci-dessous. Vous trouverez des informations détaillées sur cette version dans les [Notes de mise à jour](../../rn/using/release-notes.md). Pour toute question, contactez l’[Assistance clientèle Adobe](https://support.neolane.net/webApp/extranetLogin).

<table> 
 <thead> 
  <tr> 
   <th> Environnement<br /> </th> 
   <th> Dates <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Préproduction<br /> </td> 
   <td> April 27 - 28, 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> Production<br /> </td> 
   <td> 4-11 mai 2020<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Questions et réponses {#questions-and-answers}

**Q : Quel est l’impact ?**

R : Les modifications sont répertoriées dans les [Notes de mise à jour](../../rn/using/release-notes.md), qui comprennent des liens vers la documentation connexe. Adobe conseille également de consulter la page [Fonctionnalités obsolètes et supprimées](https://helpx.adobe.com/fr/campaign/kb/acs-deprecated-and-removed-features.html). Ces pages seront actualisées avec les informations au sujet de la nouvelle version, à la date de la mise à niveau de l’environnement de préproduction.

**Q : Quelle est la procédure de validation ?**

R : Lorsque l’instance de préproduction est mise à niveau, Adobe recommande de valider les processus, de vérifier que les cas pratiques fonctionnent avec la nouvelle version et de signaler tout problème à l’[Assistance clientèle Adobe](https://support.neolane.net/webApp/extranetLogin).

**Q : L’instance sera-t-elle accessible pendant la mise à niveau ?**

R : Non. Lors de la mise à niveau de l’instance, la base de données peut ne pas être accessible pendant plusieurs minutes. Tous les processus redémarrent automatiquement.

**Q : Les messages seront-ils toujours envoyés ?**

R : Non. Les messages ne seront pas envoyés pendant plusieurs minutes. Une fois la mise à niveau terminée, les processus seront automatiquement redémarrés.

**Q : Les workflows continueront-ils de s’exécuter et d’envoyer les diffusions ?**

R : Non. Pendant la mise à niveau de la version, le serveur de workflow et le MTA sont arrêtés. Les workflows ne fonctionneront plus et les diffusions ne seront plus envoyées pendant quelques minutes. Aucune action n’est requise : les workflows redémarreront dès que l’instance sera mise à niveau.

**Q : Les liens de tracking dans les messages fonctionneront-t-il toujours pendant la mise à niveau ?**

R : Oui. Il ne sera pas possible d’envoyer de nouveaux emails pendant la mise à niveau, mais les liens de tracking inclus dans les messages déjà envoyés seront opérationnels.

**Q : Comment savoir quand la mise à niveau est terminée ?**

R : Lorsque vous vous connectez à Campaign, une fenêtre contextuelle de notification s’affiche avec la dernière version.

Pour toute autre question, contactez l’[Assistance clientèle Adobe](https://support.neolane.net/webApp/extranetLogin).