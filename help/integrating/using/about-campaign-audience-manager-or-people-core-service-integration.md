---
title: A propos de l'intégration Campaign-Audience Manager ou People core service
description: Avec l'intégration d'Audience Manager/de People core service, vous pouvez partager des audiences ou des segments au sein des différentes solutions d'Adobe Experience Cloud.
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: ht
source-git-commit: 0062079addfbcd577faa1b16096f4588a05a8f78

---


# A propos de l&#39;intégration Campaign-Audience Manager ou People core service{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign vous permet d&#39;échanger et de partager des audiences/segments avec les autres applications d&#39;Adobe Experience Cloud. En intégrant **Adobe Campaign** à **People core service** (aussi appelé **Profiles &amp; Audiences core service**) ou Adobe Audience Manager, vous pouvez :

* importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d&#39;Adobe Experience Cloud. L&#39;import d&#39;audiences peut être réalisé depuis le menu **[!UICONTROL Audiences]**dans Adobe Campaign.
* exporter des audiences en tant qu&#39;audiences/segments partagés. Ces audiences peuvent être exploitées dans les différentes solutions d&#39;Adobe Experience Cloud que vous utilisez. L&#39;export d&#39;audiences peut être réalisé à la suite d&#39;un ciblage dans un workflow, à l&#39;aide de l&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]**.

L&#39;intégration prend en charge deux types d&#39;identifiants Adobe Experience Cloud :

* **Visitor ID** : ce type d&#39;identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des profils Adobe Campaign.
* **Declared ID** : ce type d&#39;identifiant permet de réconcilier tout type de données avec des profils Adobe Campaign. Cette intégration prend en charge les identifiants Declared ID standard, hachés et cryptés.

   Le cryptage permet de partager des données cryptées dans des sources de données (informations d&#39;identification personnelles, par exemple) à l&#39;aide de l&#39;identifiant Declared ID en spécifiant l&#39;algorithme de cryptage.

   Par exemple, grâce à la possibilité de décrypter des adresses email ou des numéros de SMS cryptés, vous pouvez également envoyer des messages déclenchés à vos utilisateurs même si leur profil n&#39;existe pas dans la base de données Adobe Campaign.

>[!CAUTION]
>
>L&#39;import d&#39;audiences dans Adobe Campaign peut être soumis à des restrictions légales en fonction des données échangées.

