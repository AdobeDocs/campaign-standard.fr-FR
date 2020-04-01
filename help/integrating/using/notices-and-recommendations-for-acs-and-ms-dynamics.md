---
title: '"Utilisation de Campaign Standard et de Microsoft Dynamics 365 : Avis et recommandations"'
description: Découvrez les informations et les recommandations relatives à la manière de travailler avec Campaign Standard et Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 620be6615d162672948c3dccdae2752b8c999c47

---


# Utilisation de Campaign Standard et de Microsoft Dynamics 365 : Avis et recommandations

## Prise en charge de la région

Cette intégration est disponible dans les régions Amérique du Nord, EMEA et APAC.

Si vous vous trouvez dans les régions EMEA ou APAC, certaines de vos données seront traitées aux Etats-Unis dans le cadre de cette intégration. Voir à ce sujet [cette section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Source de vérité pour la synchronisation de contacts unidirectionnels

Pour la synchronisation des contacts et des entités personnalisées, cette intégration traite Dynamics 365 comme la source de vérité. Toute modification des attributs synchronisés doit être effectuée dans Microsoft Dynamics 365, et non  Adobe Campaign Standard. Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées dans Campaign pendant la synchronisation, car la synchronisation est dans une direction.  De plus, la synchronisation des contacts est conçue pour extraire tous les enregistrements de contacts, qu’ils soient marqués comme actifs ou inactifs dans Microsoft Dynamics 365.

## Gestion des requêtes de confidentialité

Cette intégration est conçue pour transférer les données utilisateur final (y compris, mais sans s&#39;y limiter, les informations personnelles, si elles sont contenues dans vos données utilisateur final), entre Microsoft Dynamics 365 et  Adobe Campaign Standard.  En tant que responsable du traitement des données, votre est tenu de se conformer aux lois et règlements en matière de confidentialité applicables à votre collecte et à votre utilisation des données personnelles.

Pour cette intégration, vous devez traiter chaque requête de sujet de données dans chaque système indépendamment afin que la modification soit répercutée dans les deux bases de données. La modification doit d&#39;abord être exécutée dans Microsoft Dynamics 365, puis dans  Adobe Campaign Standard. La seule exception à cette règle est qu’une demande de suppression liée à la confidentialité sera ajoutée à la file d’attente des outils de confidentialité dans Campaign Standard lorsqu’un contact est supprimé dans Dynamics 365.

Vous trouverez ci-dessous des liens pour vous aider à implémenter et/ou supprimer des requêtes liées à la confidentialité dans chaque système :

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Suppression de contacts

Comme Dynamics 365 est la source de la vérité, les suppressions de contacts dans Dynamics 365 seront répercutées dans Campaign.

Lorsqu’un contact est supprimé dans Dynamics 365, l’intégration met en file d’attente une demande de suppression liée à la confidentialité dans l’écran Campaign Demande/Outils de confidentialité.  Si vous avez désactivé le processus en deux étapes pour les demandes de suppression liées à la confidentialité, Campaign prendra soin de la suppression pour vous.

Cependant, si le processus en deux étapes est activé, vous devrez accéder à l’écran Demande/Outils de confidentialité, après l’exécution du de confidentialité, et confirmer si les enregistrements sont corrects pour être supprimés.  C&#39;est alors seulement que Campaign s&#39;occupera de la suppression.

Pour plus d&#39;informations, reportez-vous à la section [Comment exécuter des requêtes de suppression liées à la confidentialité dans  Adobe Campaign Standard](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Si le processus en deux étapes est activé pour les demandes de confidentialité dans Campaign, vos suppressions dans Dynamics 365 ne seront pas automatiquement répercutées dans Campaign.  Vous devrez accéder à l’écran de demande de confidentialité Campaign pour confirmer les suppressions.

>[!NOTE]
>
>Cette intégration crée une requête à l’aide de l’ID externe (c.-à-d. l’ID de contact Dynamics 365) comme identifiant d’enregistrement/de .

## Exclusion

En raison des différences dans les attributs d’exclusion entre Dynamics 365 et Campaign et des différences dans les besoins commerciaux de chaque client, le mappage d’exclusion a été laissé comme un exercice que le client doit terminer. Il est important de s’assurer que les exclusions sont correctement mises en correspondance entre les systèmes afin que les préférences d’exclusion de l’utilisateur final soient préservées et qu’il n’y ait pas de communication via un dont il s’est désabonné.

Sachez que seuls les attributs Campaign avec le préfixe &quot;blackList&quot; (par exemple, blackListEmail) ou l’attribut spécifique pour l’exclusion CCPA peuvent être utilisés dans les mappages d’exclusion.  Dans Dynamics 365, la plupart des champs d’exclusion ont le préfixe &quot;doNot&quot; ; toutefois, vous pouvez également utiliser les attributs personnalisés que vous avez créés à des fins d’exclusion si les types de données sont compatibles.

Lors de la mise en service de l’intégration, vous aurez la possibilité de spécifier la configuration d’exclusion dont vous avez besoin pour votre entreprise :

* Dynamics 365 est une source de vérité pour les exclusions : les attributs d&#39;exclusion seront synchronisés dans une direction de Dynamics 365 à Campaign Standard
* Campaign Standard est la source de vérité pour les exclusions : les attributs d&#39;exclusion seront synchronisés dans une direction, de Campaign Standard à Dynamics 365
* Dynamics 365 ET Campaign Standard sont les deux sources de vérité : les attributs d’exclusion seront synchronisés bidirectionnellement entre Campaign Standard et Dynamics 365

Suivez les instructions de post-mise en service du guide [utilisateur](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) Unifi pour mapper correctement ces valeurs.

La configuration d’exclusion bidirectionnelle utilise la logique pour déterminer la valeur à écrire sur les deux systèmes.  La logique compare les horodatages entre les deux systèmes (changement au niveau des enregistrements dans Dynamics 365, changement au niveau des attributs dans Campaign) afin de déterminer quel système prévaut.  Si Campaign contient l’horodatage le plus récent, la valeur Campaign prévaut.  Si Dynamics 365 contient l’horodatage le plus récent ou s’ils sont égaux, opt-out=TRUE gagne (en supposant que l’une des valeurs soit TRUE).

**Exclusion en vertu de la Loi sur la protection des consommateurs de la Californie (LPCC) et d’une loi semblable.**

La fonction de configuration d’exclusion bidirectionnelle n’est actuellement pas en mesure de soutenir la conformité à certaines exigences légales en vertu de l’ACFPC et/ou d’autres lois sur la confidentialité des données prêtes à l’emploi. Les clients qui doivent se conformer à l’ACCP ou à des exigences juridiques similaires relatives aux exclusions sont responsables de la mise en oeuvre de leur propre solution tierce pour effectuer des synchronisations bidirectionnelles.

>[!NOTE]
>
>Il est recommandé, si votre  ne requiert pas de prise en charge de l’exclusion bidirectionnelle, de sélectionner une option d’exclusion unidirectionnelle.

>[!NOTE]
>
>Veuillez consulter et, le cas échéant, mettre à jour les  par défaut et spécifiques dans  Adobe Campaign avant d&#39;effectuer des modifications ici pour vous assurer que ces modifications sont correctement appliquées à toutes les communications sortantes. Par exemple, veillez à ce que tous les mappages vers les préférences d’exclusion reflètent fidèlement les choix d’intention/de communication du et n’interrompent pas par inadvertance le de relation ou les  tels que les confirmations de commande client.

## Données Campaign existantes

Cette intégration synchronise les contacts et les entités personnalisées de Dynamics 365 vers Campaign. Campaign enregistrements créés en dehors de l’intégration (c.-à-d. non créés par la tâche de synchronisation) ne seront pas touchés par l’intégration, y compris les enregistrements Campaign existant au moment de la configuration de l’intégration.

Comme cette intégration utilise le **[!UICONTROL externalId]** champ de Campaign Standard pour synchroniser Campaign enregistrements d&#39; avec les enregistrements de contact Dynamics 365, ce champ de (**[!UICONTROL externalId]** ) doit être renseigné avec la dynamique 365 **[!UICONTROL contactId]** pour les enregistrements que vous souhaitez synchroniser à partir de Dynamics 365.  Les entités personnalisées devront également disposer de ce champ présent et renseigné correctement pour maintenir la synchronisation.  Gardez toutefois à l’esprit que Dynamics 365 sera toujours la source de la vérité et que les données Campaign de l’ peuvent être remplacées lorsque l’intégration détecte les mises à jour du côté de Dynamics 365.  D’autres étapes peuvent également être nécessaires pour activer l’intégration, selon votre déploiement existant ; il est donc recommandé de travailler en étroite collaboration avec votre contact technique Adobe.

>[!NOTE]
>
>En raison de la complexité des déploiements de clients existants, il est recommandé de travailler avec votre contact technique Adobe lors de la planification et de la configuration de l’intégration.
