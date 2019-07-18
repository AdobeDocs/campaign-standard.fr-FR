---
title: Résolution des problèmes
seo-title: Résolution des problèmes
description: Résolution des problèmes
seo-description: Découvrez comment résoudre les problèmes liés au partage des ressources.
page-status-flag: jamais activé
uuid: 1 c 764 dd 8-e 09 f -4 e 8 e -9 ccd -88 ab 3 d 714284
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: intégration
content-type: référence
topic-tags: work-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c 28 e 1 d 90-8074-4127-a 6 fc-ed 39 d 69 cdb 19 cdb 19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Résolution des problèmes{#troubleshooting}

Lors de l'utilisation de l'intégration avec Audience Manager ou People core service, il est possible de rencontrer des erreurs.

Dans ce cas, vérifiez que les éléments suivants sont correctement configurés :

* **Comptes externes**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. Les serveurs S3 mentionnés doivent avoir été configurés pendant la mise en service.

   * **[!UICONTROL importSharedAudience]** : compte S3 dédié à l'importation d'audiences.
   * **[!UICONTROL exportSharedAudience]** : compte S3 dédié à l'exportation d'audiences.

* **Data sources partagées**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL La Priorité]** est utilisée lorsque plusieurs data sources sont définies. Elle décide quelle data source sera utilisée pour la mise en correspondance avec l'alias reçu dans l'ordre défini. **[!UICONTROL La priorité]** n'est nécessaire que pour l'implémentation des triggers.

   Vérifiez que la clé de réconciliation est correcte. C'est la valeur hachée/cryptée de ce champ qui est utilisée pour exporter et importer les audiences.

   En cas de hachage ou de cryptage de l'identifiant Declared ID, vérifiez que les mêmes paramètres/algorithmes de cryptage sont utilisés sur votre site Web.

   Un seul algorithme de cryptage est pris en charge : AES en mode CBC avec une taille de clé de 128, 192 ou 256 octets, avec un remplissage PKCS.

   Si l'algorithme de cryptage AES est sélectionné, les champs supplémentaires suivants doivent être correctement définis :

   * **Clé de cryptage** pour AES
   * **Cryptage IV** (vecteur d'initialisation) pour AES
   * **Canal** (Email/SMS/Autre) : ce champ permet de décrypter directement les adresses email et les numéros de SMS. Vérifiez que la clé de réconciliation correspond au paramètre du champ **Canal.** Si vous sélectionnez Autre, ce décryptage spécifique ne sera pas effectué et la clé de réconciliation sera utilisée pour réconcilier les données.
   Les audiences Experience Cloud peuvent ne pas être partagées parce que le workflow technique s'est arrêté ou est en pause. Accédez au workflow **[!UICONTROL Importer une audience partagée]** en cliquant directement sur l'option **Afficher l'audience partagée]dans votre Data source.[!UICONTROL **

Il est possible que certaines données soient manquantes lors du partage d'une audience via People core service ou lors de l'import d'une audience. Seuls les enregistrements dont l'identifiant ('Visitor ID' ou 'Declared ID') a pu être réconcilié avec la dimension des profils sont transférés. Les identifiants provenant des segments de People core service non reconnus par Adobe Campaign ne sont pas importés.
