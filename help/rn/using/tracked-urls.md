---
solution: Campaign Standard
product: campaign
title: Problème de signature des URL trackées
description: Problème de signature des URL trackées
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 59%

---


# Problème de signature des URL trackées {#tracked-urls}

Suite à des modifications récentes, les URL suivies envoyées par Campaign peuvent échouer. Certaines boîtes de réception peuvent être plus touchées que d&#39;autres, car certaines sociétés disposent d&#39;outils de sécurité spécifiques qui peuvent affecter les liens et modifier le mécanisme de signature d&#39;URL.

En conséquence, l’Adobe a décidé de désactiver le mécanisme de signature pour le suivi des liens. Cette procédure corrige tous les liens de suivi.

Veuillez noter que les liens de désinscription peuvent échouer comme tout autre lien, la fréquence est variable d&#39;hôte à hôte, mais inférieure à 1 %.

**Cela vous concerne-t-il ?**

Certains utilisateurs Campaign Standards sont affectés car le mécanisme de signature pour le suivi des liens dans les courriels a été introduit dans [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) - octobre 2020 - et est activé par défaut pour tous les clients.

**Comment effectuer la mise à jour ?**

Adobe travaillera avec vous pour mettre à jour votre configuration sous peu. Vous recevrez une notification par courrier électronique avec votre calendrier de mise à niveau.

**Quel est l&#39;impact ?**

La maintenance nécessite un temps d&#39;inactivité maximal de 25 minutes et pendant cette période, toutes les diffusions, les liens de tracking et les appels d&#39;API ne fonctionneront pas.

Une fois la mise à jour terminée, tous les liens fonctionnent comme prévu.

>[!NOTE]
>
>Pour toute question sur ces modifications, contactez l&#39;[Assistance clientèle d&#39;Adobe](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

