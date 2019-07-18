---
title: A propos de l'intégration Campaign-Audience Manager ou People core service
seo-title: A propos de l'intégration Campaign-Audience Manager ou People core service
description: A propos de l'intégration Campaign-Audience Manager ou People core service
seo-description: Avec l'intégration d'Audience Manager/de People core service, vous pouvez partager des audiences ou des segments au sein des différentes solutions d'Adobe Experience Cloud.
page-status-flag: jamais activé
uuid: 39 e 3 c 78 e-cccd -4823-afe 9-abc 7 f 8 aef 034
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: intégration
content-type: référence
topic-tags: work-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf 718329-f 181-46 f 7-80 a 2-b 525 a 8 dee 46 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# A propos de l'intégration Campaign-Audience Manager ou People core service{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign vous permet d'échanger et de partager des audiences/segments avec les autres applications d'Adobe Experience Cloud. En intégrant **Adobe Campaign** à **People core service** (aussi appelé **Profiles &amp; Audiences core service**) ou Adobe Audience Manager, vous pouvez :

* importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d'Adobe Experience Cloud. L'import d'audiences peut être réalisé depuis le menu **[!UICONTROL Audiences]dans Adobe Campaign.**
* exporter des audiences en tant qu'audiences/segments partagés. Ces audiences peuvent être exploitées dans les différentes solutions d'Adobe Experience Cloud que vous utilisez. L'export d'audiences peut être réalisé à la suite d'un ciblage dans un workflow, à l'aide de l'activité **[!UICONTROL Sauvegarde d'audience].**

L'intégration prend en charge deux types d'identifiants Adobe Experience Cloud :

* **Visitor ID** : ce type d'identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des profils Adobe Campaign.
* **Declared ID** : ce type d'identifiant permet de réconcilier tout type de données avec des profils Adobe Campaign. Cette intégration prend en charge les identifiants Declared ID standard, hachés et cryptés.

   Le cryptage permet de partager des données cryptées dans des sources de données (informations d'identification personnelles, par exemple) à l'aide de l'identifiant Declared ID en spécifiant l'algorithme de cryptage.

   Par exemple, grâce à la possibilité de décrypter des adresses email ou des numéros de SMS cryptés, vous pouvez également envoyer des messages déclenchés à vos utilisateurs même si leur profil n'existe pas dans la base de données Adobe Campaign.

>[!CAUTION]
>
>L'import d'audiences dans Adobe Campaign peut être soumis à des restrictions légales en fonction des données échangées.

