---
title: Résoudre des problèmes d'intégration
description: Découvrez comment résoudre les problèmes liés au partage des ressources.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: ht
source-wordcount: '369'
ht-degree: 100%

---

# Résolution des problèmes{#troubleshooting}

Lors de l&#39;utilisation de l&#39;intégration avec Audience Manager ou People core service, il est possible de rencontrer des erreurs.

Dans ce cas, vérifiez que les éléments suivants sont correctement configurés :

* **Comptes externes**

   Dans **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Comptes externes]**, vérifiez que les comptes S3 externes ci-dessous sont correctement configurés. Les serveurs S3 mentionnés doivent avoir été configurés pendant l’approvisionnement.

   * **[!UICONTROL importSharedAudience]** : compte S3 dédié à l&#39;import d&#39;audiences.
   * **[!UICONTROL exportSharedAudience]** : compte S3 dédié à l&#39;export d&#39;audiences.

* **Data sources partagées**

   Dans **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Data sources partagées]**, vérifiez que la data source partagée est correctement définie.

   La **[!UICONTROL Priorité]** est utilisée lorsque plusieurs data sources sont définies. Elle décide quelle data source sera utilisée pour la mise en correspondance avec l&#39;alias reçu dans l&#39;ordre défini. La **[!UICONTROL Priorité]** n&#39;est nécessaire que pour l&#39;implémentation des Triggers.

   Vérifiez que la clé de réconciliation est correcte. C&#39;est la valeur hachée/chiffrée de ce champ qui est utilisée pour exporter et importer les audiences.

   En cas de hachage ou de chiffrement de l&#39;identifiant Declared ID, vérifiez que les mêmes paramètres/algorithmes de chiffrement sont utilisés sur votre site Web.

   Un seul algorithme de chiffrement est pris en charge : AES en mode CBC avec une taille de clé de 128, 192 ou 256 octets, avec un remplissage PKCS.

   Si l&#39;algorithme de chiffrement AES est sélectionné, les champs supplémentaires suivants doivent être correctement définis :

   * **Clé de chiffrement** pour AES
   * **Chiffrement IV** (vecteur d&#39;initialisation) pour AES
   * **Canal** (Email/SMS/Autre) : ce champ permet de déchiffrer directement les adresses e-mail et les numéros de SMS. Vérifiez que la clé de réconciliation correspond au paramètre du champ **Canal**. Si vous sélectionnez Autre, ce déchiffrement spécifique ne sera pas effectué et la clé de réconciliation sera utilisée pour réconcilier les données.

   Les audiences Experience Cloud peuvent ne pas être partagées parce que le workflow technique s&#39;est arrêté ou est en pause. Accédez au workflow **[!UICONTROL Importer une audience partagée]** en cliquant directement sur l&#39;option **[!UICONTROL Afficher l&#39;audience partagée]** dans votre Data source.

Il est possible que certaines données soient manquantes lors du partage d&#39;une audience via People core service ou lors de l&#39;import d&#39;une audience. Seuls les enregistrements dont l&#39;identifiant (&#39;Visitor ID&#39; ou &#39;Declared ID&#39;) a pu être réconcilié avec la dimension des profils sont transférés. Les identifiants provenant des segments de People core service non reconnus par Adobe Campaign ne sont pas importés.
