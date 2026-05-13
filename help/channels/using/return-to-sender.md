---
title: Retour à l'expéditeur
description: Découvrez comment être informé d'une adresse incorrecte et l'exclure des prochaines communications.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
TQID: https://experienceleague.adobe.com/g-0yLI3-qYRfbF-gXuO8AtyCI3Qr5F7an5hqVzaQCE8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 227
ht-degree: 100%

---

# Retour à l&#39;expéditeur{#return-to-sender}

Les échanges de fichiers plats avec les opérateurs de services postaux intégrant les informations de retour à l&#39;expéditeur sont pris en charge. Les adresses postales correspondantes peuvent être ainsi exclues des communications futures. Cela vous permet également d’être averti d’une adresse incorrecte et d’interagir avec le client via d’autres canaux ou de l’encourager à mettre à jour son adresse postale.

Par exemple, un contact a déménagé sans vous indiquer sa nouvelle adresse postale. L’opérateur récupère la liste des adresses erronées et l’envoie à Adobe Campaign qui place automatiquement ces adresses dans la liste bloquée.

Pour permettre cette fonctionnalité, le modèle de diffusion courrier par défaut inclut l&#39;identifiant du log de diffusion au sein du contenu. Adobe Campaign peut ainsi synchroniser le profil et les données de diffusion avec les informations renvoyées par l&#39;opérateur.

![](assets/direct_mail_return_sender_1.png)

Un modèle d&#39;import est disponible sous **[!UICONTROL Adobe Campaign > Ressources > Modèles > Modèles d&#39;import > Mettre à jour les logs de diffusion et les mises en quarantaine Courrier]**. Dupliquez ce modèle de manière à créer le vôtre. Pour plus d&#39;informations sur l&#39;utilisation des modèles d&#39;import, voir [Utilisation des modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Une fois l&#39;import effectué, Adobe Campaign réalise automatiquement les actions suivantes :

* Les adresses incorrectes sont ajoutées à la liste bloquée au niveau du profil.
* Les principaux indicateurs de diffusion (KPI) sont mis à jour.
* Les logs de diffusion sont mis à jour.
