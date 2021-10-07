---
title: Calendrier des versions de Campaign Standard
description: Cette page répertorie toutes les versions à venir d'Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '425'
ht-degree: 100%

---

# Calendrier des versions {#release-planning}

Adobe perfectionne constamment ses solutions en ajoutant de nouvelles fonctions, des améliorations et des correctifs.

Toutes les instances Adobe Campaign Standard sont mises à niveau à chaque nouvelle version. Aucune action n&#39;est requise pour la mise à niveau.

Les mises à niveau sont déployées en deux phases. En premier lieu, les instances de test sont mises à niveau pour permettre à nos clients de tester les nouvelles fonctionnalités et d&#39;adapter leur configuration si nécessaire. Ensuite, les instances de production sont mises à niveau.

Toutes les dates de publication peuvent faire l&#39;objet de modifications. Nous vous recommandons de consulter régulièrement cette page pour vérifier la présence de mises à jour.

## Version 21.3 - Version de septembre 2021 {#release-21-3-release}

Les mises à jour des environnements s&#39;effectuent par vagues, selon les dates indiquées ci-dessous. Les dates exactes sont communiquées par email à chaque client.

Vous trouverez des informations détaillées sur cette version dans les [Notes de mise à jour](../../rn/using/release-notes.md).

<table>
 <thead>
  <tr>
   <th> Environnement<br /> </th>
   <th> Dates <br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Préproduction<br /> </td>
   <td>7-8 septembre 2021<br /> </td>
  </tr>
  <tr>
   <td>Production<br /> </td>
   <td>14-21 septembre 2021<br /> </td>
  </tr>
 </tbody>
</table>

Pour toute question, contactez l&#39;[Assistance clientèle Adobe](https://helpx.adobe.com/fr/enterprise/using/support-for-experience-cloud.html).

## Questions et réponses {#questions-and-answers}

**Q : Quel est l&#39;impact ?**

R : Les modifications sont répertoriées dans les [Notes de mise à jour](../../rn/using/release-notes.md), qui comprennent des liens vers la documentation connexe. Adobe conseille également de consulter la page [Fonctionnalités obsolètes et supprimées](../../rn/using/deprecated-features.md). Ces pages seront actualisées avec les informations au sujet de la nouvelle version, à la date de la mise à niveau de l&#39;environnement de préproduction.

**Q : Quelle est la procédure de validation ?**

R : Lorsque l&#39;instance de préproduction est mise à niveau, Adobe recommande de valider les processus, de vérifier que les cas pratiques fonctionnent avec la nouvelle version et de signaler tout problème à l&#39;[Assistance clientèle Adobe](https://helpx.adobe.com/fr/enterprise/using/support-for-experience-cloud.html).

**Q : L&#39;instance sera-t-elle accessible pendant la mise à niveau ?**

R : Non. Lors de la mise à niveau de l&#39;instance, la base de données peut ne pas être accessible pendant plusieurs minutes. Tous les processus redémarrent automatiquement.

**Q : Les messages seront-ils toujours envoyés ?**

R : Non. Les messages ne seront pas envoyés pendant plusieurs minutes. Une fois la mise à niveau terminée, les processus seront automatiquement redémarrés.

**Q : Les workflows continueront-ils de s&#39;exécuter et d&#39;envoyer les diffusions ?**

R : Non. Pendant la mise à niveau de la version, le serveur de workflow et le MTA sont arrêtés. Les workflows ne fonctionneront plus et les diffusions ne seront plus envoyées pendant quelques minutes. Aucune action n&#39;est requise : les workflows redémarreront dès que l&#39;instance sera mise à niveau.

**Q : Les liens de tracking dans les messages fonctionneront-t-il toujours pendant la mise à niveau ?**

R : Oui. Il ne sera pas possible d&#39;envoyer de nouveaux emails pendant la mise à niveau, mais les liens de tracking inclus dans les messages déjà envoyés seront opérationnels.

**Q : Comment savoir quand la mise à niveau est terminée ?**

R : Lorsque vous vous connectez à Campaign, une fenêtre contextuelle de notification s&#39;affiche avec la dernière version.

Pour toute autre question, contactez l&#39;[Assistance clientèle Adobe](https://helpx.adobe.com/fr/enterprise/using/support-for-experience-cloud.html).
