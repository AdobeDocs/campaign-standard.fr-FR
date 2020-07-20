---
title: Répartition par domaine (Breakdown by domains)
description: Grâce au rapport d'usine Répartition par domaine (Breakdown by domains), découvrez les données de performance de vos diffusions selon chaque domaine de votre client.
page-status-flag: never-activated
uuid: 75a64c81-325b-422f-b6ef-deb06eec7f7b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 2ce174f9-5d7d-48b9-9235-6bf3e238ff37
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

---


# Répartition par domaine (Breakdown by domains){#breakdown-by-domains}

Ce rapport contient les données de performance pour chaque domaine représenté dans l&#39;audience pour une diffusion email. S&#39;il s&#39;agit d&#39;un rapport de campagne ou de programme, les données de performance sont disponibles pour des audiences multiples. Ces données vous permettent d&#39;analyser le comportement de chaque domaine par rapport à des événements spécifiques. Par exemple, affichage des liens, URL en liste bloquée, etc.

![](assets/delivery_reports_6.png)

Le tableau **Broadcast statistics** contient les données disponibles liées aux erreurs possibles rencontrées pour chaque domaine, telles que :

* **Traités/envoyés** : nombre d&#39;emails envoyés.
* **Délivrés** : nombre d&#39;emails délivrés.
* **Bounces + erreurs** : nombre d&#39;emails qui n&#39;ont pas pu être livrés.
* **Hard bounce** : nombre total d&#39;erreurs permanentes, telles qu&#39;une adresse email incorrecte.
* **Soft bounce** : nombre total d&#39;erreurs temporaires, telles qu&#39;une boîte de réception pleine.

Le deuxième tableau, **Statistiques de tracking**, contient les données disponibles concernant la réactivité des destinataires par rapport à la diffusion, telles que :

* **Délivrés** : nombre d&#39;emails délivrés
* **Ouverture** : nombre d&#39;ouvertures d&#39;un message dans une diffusion.
* **Clic** : nombre de clics sur un contenu dans une diffusion.
* **Désabonnés** : nombre de clics sur le lien de désinscription.
* **Page miroir** : nombre de clics sur le lien de la page miroir.
* **Placé sur la liste bloquée** : nombre de destinataires ayant déclaré un email comme étant un spam ou un courrier indésirable (voir la section [Gestion de la liste bloquée dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).

