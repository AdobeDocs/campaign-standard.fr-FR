---
title: Réconcilier une audience de type fichier avec la base de données
description: Cet exemple montre comment utiliser l'activité Lecture d'audience pour réconcilier une audience créée directement à partir d'un import de fichier.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 100%

---


# Réconcilier une audience de type fichier avec la base de données {#example--reconcile-a-file-audience-with-the-database}

Cet exemple montre comment utiliser l&#39;activité **[!UICONTROL Lecture d&#39;audience]** pour réconcilier une audience créée directement à partir d&#39;un import de fichier.

Lors d&#39;un import de fichier, il est possible de sauvegarder son contenu directement dans une audience. Il s&#39;agit alors d&#39;une audience de type fichier et ses données ne sont liées à aucune ressource de base de données.

Le workflow d&#39;import se présente comme suit :

![](assets/readaudience_activity_example3.png)

* Une activité [Chargement de fichier](../../automating/using/load-file.md) télécharge un fichier contenant des données de profils extraites à l&#39;aide d&#39;un outil externe.

   Par exemple :

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* Une activité [Sauvegarde d&#39;audience](../../automating/using/save-audience.md) sauvegarde les données entrantes sous forme d&#39;audience. Comme les données n&#39;ont pas encore été réconciliées, l&#39;audience est une Audience Fichier et ses données ne sont pas encore reconnues en tant que données de profil.

Le workflow de réconciliation se présente comme suit :

![](assets/readaudience_activity_example2.png)

* L&#39;activité [Lecture d&#39;audience](../../automating/using/read-audience.md) télécharge l&#39;audience de type Fichier créée dans le workflow d&#39;import. Les données de l&#39;audience ne sont pas encore réconciliées avec la base de données Adobe Campaign.
* Via son onglet [Identification](../../automating/using/reconciliation.md), une activité **[!UICONTROL Réconciliation]** identifie les données entrantes comme étant des profils. Par exemple, en utilisant le champ **email** comme critère de réconciliation.
* Une activité [Mise à jour de données](../../automating/using/update-data.md) insère et met à jour la ressource profils de la base de données avec les données entrantes. Comme les données sont déjà identifiées comme des profils, vous pouvez sélectionner l&#39;option **[!UICONTROL En utilisant directement la dimension de ciblage]**, puis **[!UICONTROL Profils]** dans l&#39;onglet **[!UICONTROL Identification]** de l&#39;activité. Pour finir, ajoutez simplement la liste des champs à mettre à jour dans l&#39;onglet correspondant.
