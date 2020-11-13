---
title: Calcul des indicateurs
description: Comprenez les résultats de vos rapports grâce à la liste des formules de chaque mesure.
page-status-flag: never-activated
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '732'
ht-degree: 100%

---


# Calcul des indicateurs{#indicator-calculation}

>[!NOTE]
>
>Pour mieux traiter et gérer les volumes élevés et les analyses en temps réel, les rapports dynamiques utilisent des agrégations approximatives pour des estimations de comptage distinct. Les agrégations approximatives offrent une utilisation de mémoire limitée et sont souvent plus rapides que les calculs exacts.

Les tableaux ci-dessous contiennent la liste des indicateurs utilisés dans les différents rapports et leur formule de calcul en fonction du type de diffusion.

## Diffusion Email {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Libellé</strong> <br /> </th> 
   <th> <strong>Nom du champ</strong> <br /> </th> 
   <th> <strong>Formule de calcul de l'indicateur</strong> <br /> </th> 
   <th> <strong>Commentaires</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Compte désactivé<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Sur la liste bloquée<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux sur la liste bloquée<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Bounces + Erreurs<br /> </td> 
   <td> @Bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux Bounces + Erreurs<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clics<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 ou 10 ou 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose uniquement sur la mesure Délivrés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de délivrabilité<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Hard bounces<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de hard bounce<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Domaine invalide<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Boîte pleine<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Page miroir<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose uniquement sur la mesure Délivrés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de page miroir<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non connecté<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux d'ouverture<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose uniquement sur la mesure Délivrés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantaine<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de mise en quarantaine<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr>
  <tr> 
   <td> Rejetés<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de rejet<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> @envoyé<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Soft bounces<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de soft bounces<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose sur la mesure Envoyés (Délivrés + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics uniques<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Les clics uniques sont calculés à l'aide des concepts de ThetaSketch. Pour plus d’informations à ce propos, consultez cet <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemple</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures uniques<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inatteignable <br /> </td> 
   <td> @Inatteignable<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Désabonnement<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Taux de désabonnement<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> Le dénominateur pour le calcul du taux repose uniquement sur la mesure Délivrés.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utilisateur inconnu<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Diffusion Notification push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Libellé</strong> <br /> </th> 
   <th> <strong>Nom du champ</strong> <br /> </th> 
   <th> <strong>Formule de calcul de l'indicateur</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> @envoyé<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de délivrabilité<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux Bounces + Erreurs<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux d'ouverture<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Ouvertures uniques<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> Les ouvertures uniques sont calculées à l'aide des concepts ThetaSketch de RecipientIds uniques. Pour plus d’informations à ce propos, consultez cet <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemple</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions uniques<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics uniques<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Les clics uniques sont calculés à l'aide des concepts de ThetaSketch. Pour plus d’informations à ce propos, consultez cet <a href="https://docs.adobe.com/content/help/fr-FR/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">exemple </a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Diffusion In-App {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Libellé</strong> <br /> </th> 
   <th> <strong>Nom du champ</strong> <br /> </th> 
   <th> <strong>Formule de calcul de l'indicateur</strong> <br /> </th> 
   <th> <strong>Commentaires</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Traités/envoyés<br /> </td> 
   <td> @envoyé<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivrés<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivered)<br /> </td> 
   <td> delivered=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressions<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) ou @count(status=button 1 click + button 2 click + dismissals)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressions uniques<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Pour le modèle <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Campaign (inAppProfile)</span>, utilisateur = Identifiant du destinataire.<br /> Pour les modèles <span class="uicontrol">Cibler tous les utilisateurs d'une application mobile (inAppBroadcast)</span> et <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Mobile (inApp)</span>, utilisateur = Identifiant MC ou équivalent qui représente une combinaison unique d'utilisateur, d'application mobile et d'appareil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics In-App <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clics In-App uniques<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> Pour le modèle <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Campaign (inAppProfile)</span>, utilisateur = Identifiant du destinataire.<br /> Pour les modèles <span class="uicontrol">Cibler tous les utilisateurs d'une application mobile (inAppBroadcast)</span> et <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Mobile (inApp)</span>, utilisateur = Identifiant MC ou équivalent qui représente une combinaison unique d'utilisateur, d'application mobile et d'appareil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de clics In-App<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total des clics sur le bouton 1 ou le bouton 2/total des impressions x 100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejet In-App<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rejets In-App uniques<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Pour le modèle <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Campaign (inAppProfile)</span>, utilisateur = Identifiant du destinataire.<br /> Pour les modèles <span class="uicontrol">Cibler tous les utilisateurs d'une application mobile (inAppBroadcast)</span> et <span class="uicontrol">Cibler les utilisateurs en fonction de leur profil Mobile (inApp)</span>, utilisateur = Identifiant MC ou équivalent qui représente une combinaison unique d'utilisateur, d'application mobile et d'appareil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Taux de rejet In-App<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total fermetures/total impressions x 100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

