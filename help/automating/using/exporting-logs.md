---
title: Export des logs
description: Qu'elles concernent les diffusions ou les abonnements, les données de log peuvent être exportées par le biais d'un workflow simple.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
TQID: https://experienceleague.adobe.com/Xu174CF9RsD4nhFs6KBm0TzsHFnuiBJgnHgK6-r5cI0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 649
ht-degree: 100%

---

# Export des logs{#exporting-logs}

Qu&#39;elles concernent les diffusions ou les abonnements, les données de log peuvent être exportées par le biais d&#39;un workflow simple. Vous pouvez ainsi analyser les résultats de vos campagnes dans vos outils de reporting ou de Business Intelligence.

>[!CAUTION]
>
>Seuls les [administrateurs](../../administration/using/users-management.md#functional-administrators) fonctionnels, avec un rôle d’**[!UICONTROL administration]** et un accès aux entités **Toutes**, peuvent accéder aux logs d’envoi, aux logs de messages, aux logs de tracking, aux logs d’exclusion ou aux logs d’abonnement. Un utilisateur autre qu’administrateur peut cibler ces logs mais en commençant par une table liée (profils, diffusion).

Grâce à une **[!UICONTROL Requête incrémentale]** qui récupère uniquement les nouveaux logs à chaque exécution du workflow et une activité **[!UICONTROL Extraction de fichier]** simple qui permet de définir les colonnes de sortie, vous pouvez obtenir un fichier au format et avec les données désirés. Utilisez ensuite une activité **[!UICONTROL Transfert de fichier]** pour récupérer le fichier final. Chaque exécution du workflow est planifiée par un **[!UICONTROL Planificateur]**.

L&#39;opération d&#39;export des logs peut être effectuée par les utilisateurs standard. En revanche, seul l&#39;administrateur fonctionnel peut gérer les ressources privées suivantes : broadlogs, tracking, exclus, logs d&#39;abonnement et logs d&#39;historique des abonnements dans l&#39;onglet **Profils**.

1. Créez un workflow, comme expliqué dans [cette section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Ajoutez une activité **[!UICONTROL Planificateur]** et définissez-la selon vos besoins. Vous trouverez ci-dessous un exemple d&#39;exécution mensuelle.

   ![](assets/export_logs_scheduler.png)

1. Ajoutez une activité **[!UICONTROL Requête incrémentale]** et configurez-la afin de sélectionner les logs dont vous avez besoin. Pour sélectionner par exemple tous les broadlogs (logs de diffusion des profils) mis à jour ou nouveaux, procédez comme suit :

   * Dans l&#39;onglet **[!UICONTROL Propriétés]**, remplacez la ressource cible par **Logs de diffusion** (broadLogRcp).

     ![](assets/export_logs_query_properties.png)

   * Dans l&#39;onglet **[!UICONTROL Cible]**, définissez une condition afin de récupérer tous les logs de diffusion qui correspondent aux diffusions envoyées en 2016 ou après. Pour plus d&#39;informations à ce sujet, voir la section [Edition de requêtes](../../automating/using/editing-queries.md#creating-queries).

     ![](assets/export_logs_query_target.png)

   * Dans l&#39;onglet **[!UICONTROL Données traitées]**, sélectionnez **[!UICONTROL Utiliser un champ de date]** et le champ **lastModified**. Pendant les prochaines exécutions du workflow, seuls les logs qui auront été modifiés ou créés après la dernière exécution seront récupérés.

     ![](assets/export_logs_query_processeddata.png)

     Après la première exécution du workflow, vous pouvez voir dans cet onglet la date de dernière exécution qui sera utilisée pour la prochaine exécution. Cette date est automatiquement mise à jour à chaque exécution du workflow. Vous avez toujours la possibilité de remplacer cette valeur en en saisissant une autre qui répond à vos besoins.

1. Ajoutez une activité **[!UICONTROL Extraction de fichier]** qui permettra d&#39;exporter les données interrogées vers un fichier :

   * Dans l&#39;onglet **[!UICONTROL Extraction]**, indiquez le nom du fichier.

     Si vous sélectionnez l&#39;option **[!UICONTROL Ajoutez la date et l&#39;heure au nom du fichier.]**, ce nom sera automatiquement renseigné avec la date d&#39;exportation pour s&#39;assurer que tous les fichiers extraits sont uniques. Sélectionnez les colonnes que vous souhaitez exporter dans votre fichier. Ici, vous pouvez sélectionner des données de ressources associées, telles que des informations de diffusion ou de profil.

     >[!NOTE]
     >
     >Pour exporter un identifiant unique pour chaque log, sélectionnez l&#39;élément **[!UICONTROL Identifiant du log de diffusion]**.

     Pour organiser le fichier final, vous pouvez appliquer un tri, selon la date du log, par exemple, comme l&#39;illustre l&#39;exemple ci-après.

     ![](assets/export_logs_extractfile_extraction.png)

   * Dans l&#39;onglet **[!UICONTROL Structure du fichier]**, définissez le format du fichier de sortie selon vos besoins.

     Cochez l&#39;option **[!UICONTROL Exporter les libellés plutôt que les valeurs internes des énumérations]** si vous exportez des valeurs d&#39;énumération. Cette option permet de récupérer des libellés plus courts qui sont compréhensibles à la place d&#39;identifiants.

1. Ajoutez une activité **[!UICONTROL Transfert de fichier]** et configurez-la pour transférer le fichier nouvellement créé du serveur Adobe Campaign vers un autre emplacement où vous pourrez accéder au fichier (un serveur SFTP, par exemple).

   * Dans l’onglet **[!UICONTROL Général]**, sélectionnez **[!UICONTROL Chargement de fichier]** puisque l’objectif est d’envoyer le fichier d’Adobe Campaign vers un autre serveur.
   * Dans l&#39;onglet **[!UICONTROL Protocole]**, indiquez les paramètres de transfert et sélectionnez le [compte externe](../../administration/using/external-accounts.md#creating-an-external-account) à utiliser.

1. Ajoutez une activité **[!UICONTROL Fin]** pour vous assurer que le workflow se termine correctement et enregistrez ce dernier.

   ![](assets/export_logs_example_workflow.png)

Vous pouvez exécuter à présent le workflow et récupérer le fichier de sortie sur le serveur externe.

**Rubrique connexe :**

[Workflows](../../automating/using/get-started-workflows.md)
