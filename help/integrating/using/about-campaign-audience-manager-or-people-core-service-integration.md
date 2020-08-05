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
translation-type: tm+mt
source-git-commit: 1e790f550f6eb84954f199caeda88a8fd90dfd85
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 52%

---


# A propos de l&#39;intégration Campaign-Audience Manager ou People core service{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Selon les données échangées, l&#39;importation d&#39;audiences en Adobe Campaign peut être soumise à des restrictions légales.

Adobe Campaign vous permet d&#39;échanger et de partager des audiences/segments avec les autres applications d&#39;Adobe Experience Cloud. En intégrant **Adobe Campaign** à **People core service** (aussi appelé **Profiles &amp; Audiences core service**) ou Adobe Audience Manager, vous pouvez :

* importer dans Adobe Campaign des audiences/segments provenant de différentes solutions d&#39;Adobe Experience Cloud. L&#39;import d&#39;audiences peut être réalisé depuis le menu **[!UICONTROL Audiences]** dans Adobe Campaign.
* exporter des audiences en tant qu&#39;audiences/segments partagés. Ces audiences peuvent être exploitées dans les différentes solutions d&#39;Adobe Experience Cloud que vous utilisez. L&#39;export d&#39;audiences peut être réalisé à la suite d&#39;un ciblage dans un workflow, à l&#39;aide de l&#39;activité **[!UICONTROL Sauvegarde d&#39;audience]**.

L&#39;intégration prend en charge deux types d&#39;identifiants Adobe Experience Cloud :

* **Visitor ID** : ce type d&#39;identifiant permet de réconcilier des visiteurs Adobe Experience Cloud avec des profils Adobe Campaign. Dès qu’une connexion est activée via l’Adobe IMS, le service d’identification des Visiteurs de Marketing Cloud est activé, ce qui remplace le cookie permanent utilisé par Adobe Campaign. Vous pouvez ainsi identifier un visiteur, puis le lier à un profil.
   <br>Un ID de visiteur est lié à un profil dès que le profil clique dans un courrier électronique envoyé via Adobe Campaign :
   * Si le profil dispose déjà d’un ID de visiteur, les données du navigateur du profil permettent à Adobe Campaign de récupérer et de lier automatiquement le profil à l’ID de visiteur.
   * Si aucun ID de visiteur n’est trouvé, un nouvel ID est créé. Cet ID de visiteur est stocké dans les logs de tracking de profil.

   L&#39;identifiant sera ensuite reconnu par les autres applications Adobe Marketing Cloud partageant le même CNAME.

* **ID**déclaré : ce type d’ID vous permet de concilier tout type de données avec les éléments de la base de données Adobe Campaign. Il est représenté en Adobe Campaign en tant que clé de réconciliation prédéfinie. Lors de l’échange de données, les identifiants de base de données Adobe Campaign sont hachés. Ces identifiants hachés sont ensuite comparés aux identifiants hachés de l’audience Adobe Marketing Cloud impliquée dans l’importation ou l’exportation.
   <br>Cette intégration prend en charge les identifiants Declared ID standard, hachés et cryptés.

   >[!CAUTION]
   >
   >L’ID déclaré ne fonctionne qu’avec Adobe Audience Manager. L&#39;ID déclaré ne fonctionnera pas sans lui.

   Le cryptage permet de partager des données cryptées dans des sources de données (informations d&#39;identification personnelles, par exemple) à l&#39;aide de l&#39;identifiant Declared ID en spécifiant l&#39;algorithme de cryptage.

   Par exemple, grâce à la possibilité de décrypter des adresses email ou des numéros de SMS cryptés, vous pouvez également envoyer des messages déclenchés à vos utilisateurs même si leur profil n&#39;existe pas dans la base de données Adobe Campaign.

Le diagramme suivant décrit le fonctionnement de cette intégration. Ici, AAM signifie Adobe Audience Manager et ACS pour Adobe Campaign Standard.

![](assets/aam_diagram.png)