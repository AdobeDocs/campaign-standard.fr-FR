---
title: Statuts des ressources
description: Découvrez les différents statuts des ressources en fonction de leur état de publication.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Statuts des ressources{#resource-statuses}

En fonction de leur publication ou de l’état  du , les ressources peuvent avoir des états différents.

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**Publication :**

* **En création** : la ressource vient d&#39;être créée ou bien la ressource a été réinitialisée. Pour créer les tables de base de données ainsi que les API correspondantes, la ressource doit être republiée. Si une ressource est en cours de réécriture, elle devient automatiquement inactive après l’étape de publication.
* **En attente d&#39;initialisation** : la ressource a été réinitialisée. Le processus de réinitialisation interviendra lors de la prochaine publication. La réinitialisation est irrévocable. Plusieurs messages d’avertissement s’affichent pour informer l’utilisateur, à la fois lors d’une nouvelle rédaction et lors de la préparation de la publication.

   Pour plus d&#39;informations sur la réinitialisation, voir la section [Supprimer une ressource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >The **[!UICONTROL Cancel re-draft]** option is available when the resource that you want to re-draft still contains links through other resources with the &quot;Published&quot; status. Cette option permet de rétablir le processus de « réinitialisation ». Les statuts d&#39;origine des ressources personnalisées sont alors rétablis.

* **Publiée** : la ressource a été publiée. Si la ressource est modifiée après la date de la dernière modification, un message s’affiche pour vous inviter à republier la ressource afin de prendre en compte les dernières modifications.

Le **[!UICONTROL Do not publish latest modifications]** champ empêche la prise en compte des modifications dans les publications futures.

Ce champ est configurable dans la définition de la ressource personnalisée.
