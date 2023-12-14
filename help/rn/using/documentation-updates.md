---
title: Mises à jour de la documentation
description: Découvrez l’ensemble des mises à jour les plus récentes de la documentation d’Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '7280'
ht-degree: 99%

---

# Mises à jour de la documentation{#documentation-updates}

Outre les [Notes de mise à jour](../../rn/using/release-notes.md) Adobe Campaign, cette page répertorie toutes les nouvelles mises à jour de la documentation d&#39;Adobe Campaign Standard.

## Décembre 2023 {#doc-updates-dec-2023}

Certaines modifications importantes apportées au service Android FCM (Firebase Cloud Messaging) seront publiées en 2024 et auront une incidence sur votre mise en œuvre d’Adobe Campaign. En savoir plus dans [cette technote](../../administration/using/push-technote.md).

## Version 23.2 - Automne/hiver 2023 {#release-23-2}

* Les notes de mise à jour de la version automne/hiver 2023 de Campaign Standard 23.2 ont été publiées. [En savoir plus](release-notes.md)

* JWT (JSON Web Tokens) est actuellement en cours d’obsolescence et est remplacé par OAuth. La transition sera progressivement effectuée dans les prochaines versions de Campaign et la documentation sera modifiée pour refléter ces mises à jour.

## Octobre 2023 {#doc-updates-oct-2023}

* La nouvelle interface utilisateur des Triggers d’Experience Cloud est désormais disponible. Elle offre une expérience intuitive de gestion des comportements des consommateurs et des consommatrices et de personnalisation des expériences client. [En savoir plus](https://experienceleague.adobe.com/docs/experience-cloud/triggers/overview.html?lang=fr){target="_blank"}.

* Une note sur l’utilisation de profils de test de type Piège combinés à des règles de filtrage ou de fatigue a été ajoutée. [En savoir plus](../../sending/using/using-traps.md)

## Version 23.1 - Printemps/été 2023 {#release-23-1}

Les notes de mise à jour de la version printemps/été 2023 de Campaign Standard 23.1 ont été publiées. [En savoir plus](release-notes.md)

## Novembre 2022 {#doc-updates-november-2022}

Une note a été ajoutée pour vous recommander d’éviter les espaces vides dans le champ d’identifiant des diffusions. [En savoir plus](../../channels/using/creating-an-email.md)

Des informations ont été ajoutées dans la page d’activité de workflow **[!UICONTROL Extraire le fichier]** dans le but d’extraire des données dans un fichier CSV avec un codage spécifique. [En savoir plus](../../automating/using/extract-file.md)

## Version 22.3 - Automne/hiver 2022 {#release-22-3}

Les notes de mise à jour de la version automne/hiver 2022 de Campaign Standard 22.3 ont été publiées. [En savoir plus](release-notes.md)

<!--Data retention periods have been updated to reflect changes coming with 22.3 release. [Read more](../../administration/using/data-retention.md)-->


## Version 22.2 - Juin 2022 {#release-22-2}

**Améliorations incluses dans la version**

**Adobe Notification Service** - Campaign est fourni avec Adobe Notification Service, qui permet aux solutions Experience Cloud de tenir les utilisateurs d’Experience Cloud informés des activités qui leur sont importantes. [En savoir plus](../../administration/using/sending-internal-notifications.md).

**Autres modifications**

Les intégrations avec le Connecteur d’Adobe Experience Platform et le service Audience Destinations sont désormais obsolètes. [En savoir plus](deprecated-features.md)

L&#39;utilisation du mode test SMTP a été détaillée. [En savoir plus](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## Mars 2022 {#doc-updates-march-2022}

Une note a été fournie pour indiquer que l’envoi de BAT à l’aide de la substitution de profil ajoutera des enregistrements aux journaux des profils sélectionnés. [En savoir plus](../../sending/using/testing-messages-using-target.md)

## Version 22.1 - Février 2022 {#release-22-1}

**Améliorations incluses dans la version**

Amélioration du mécanisme de reprise pour les diffusions, y compris le contenu importé à partir d’une URL. [En savoir plus](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

Mise à jour du niveau d’accès des options de contrôle de l’audit : les options antérieures d’activation/désactivation du [Journal d’audit](../../administration/using/audit.md) n’étaient pas accessibles aux [administrateurs fonctionnels](../../administration/using/users-management.md#functional-administrators). Grâce à cette modification, le niveau d’accès à l’audit est modifié pour fournir un contrôle aux administrateurs fonctionnels. [En savoir plus](../../administration/using/audit.md#enable-disable-audit)

Le nouveau menu déroulant **Historique des tâches** a été ajouté au tableau de bord des messages. [En savoir plus](../../sending/using/monitoring-a-delivery.md)

**Autres changements**

Ajout d’une note d’avertissement concernant les mots-clés qui déclenchent des réponses automatiques des SMS : ils ne doivent contenir que des caractères alphanumériques. [En savoir plus](../../channels/using/managing-incoming-sms.md)

Ajout d’une note à la section E-mail du test A/B : si la population totale est inférieure à 50 000, chaque variante doit représenter au moins 10 % de la population totale. Sinon, les journaux afficheront un avertissement. [En savoir plus](../../channels/using/designing-an-a-b-test-email.md)

Mise à jour de la description de l’option **[!UICONTROL Effacer les fichiers sources après le transfert]** dans l’activité **Transfert de fichier**, y compris un rappel pour surveiller manuellement la taille du contenu archivé dans le répertoire SFTP au cas où l’option n’est pas sélectionnée. [En savoir plus](../../automating/using/transfer-file.md)

Mise à jour de la totalité des liens obsolètes dans les sections **Confidentialité**. [En savoir plus](../../start/using/privacy.md)

Ajout d’un lien direct vers la documentation du Panneau de contrôle Campaign dans la table des matières de la documentation de Campaign Standard.

## Version 21.3 - Septembre 2021  {#release-21-3---september-2021}

**Nouvelles fonctionnalités de cette version**

Interface Experience Cloud améliorée et unifiée – [En savoir plus](../../start/using/interface-description.md#top-bar)

Nouvelle fonctionnalité Journal d’audit – [En savoir plus](../../administration/using/audit.md)

Mode de diagnostic des workflows – [En savoir plus](../../automating/using/managing-execution-options.md)

**Autres mises à jour de la documentation accompagnant cette version**

Une nouvelle section a été ajoutée sur la façon de supprimer une adresse de la liste de quarantaine. [En savoir plus](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

La section **Quarantaine et liste bloquée** a été clarifiée. [En savoir plus](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## Juillet 2021 {#doc-updates-july-2021}

Une nouvelle section a été ajoutée pour décrire comment permettre aux utilisateurs de s’abonner ou de se désabonner de plusieurs services à partir d’une seule landing page. [En savoir plus](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

La section **Gestion des données de formulaire de landing page** a été mise à jour et simplifiée. [En savoir plus](../../channels/using/managing-landing-page-form-data.md)

## Version 21.2 - Juin 2021 {#release-21-2---june-2021}

**Nouvelles fonctionnalités de cette version**

Validation des landing pages : vous pouvez désormais ajouter une option d&#39;accord obligatoire à vos landing pages. [En savoir plus](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

La section **Taille de l&#39;e-mail** a été mise à jour avec des informations sur la taille maximale d&#39;un e-mail, qui est désormais définie sur 100 Mo par défaut. [En savoir plus](../../sending/using/design-and-personalize.md#email-size)

**Autres mises à jour de la documentation accompagnant cette version**

Des informations ont été ajoutées sur la modification du mapping de ciblage dans une notification push transactionnelle. [En savoir plus](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## Mai 2021 {#doc-updates-may-2021}

La section de rapport **Profils actifs** a été mise à jour. [En savoir plus](../../audiences/using/active-profiles.md)

La page **Calendrier des versions** a été mise à jour avec de nouvelles dates. [En savoir plus](../../rn/using/release-planning.md)


## Avril 2021 {#doc-updates-april-2021}

Une nouvelle section consacrée à la manière d&#39;utiliser les sources et destinations Adobe Experience Platform pour partager des données entre Campaign Standard et Real-time Customer Data Platform (RTCDP) a été ajoutée. [En savoir plus](../../integrating/using/get-started-sources-destinations.md)

## Mars 2021 {#doc-updates-march-2021}

Nouvelle page **Options d&#39;aide et d&#39;assistance**. [En savoir plus](../../support.md)

La section qui répertorie les étapes clés concernant l&#39;envoi d&#39;un message a été enrichie d&#39;informations et de références supplémentaires. [En savoir plus](../../channels/using/key-steps-to-send-a-message.md)

Des informations ont été ajoutées pour indiquer que, lors de la sélection d&#39;une audience dans une requête, sa définition est copiée et non référencée. [En savoir plus](../../audiences/using/selecting-an-audience-in-a-message.md)

Les informations relatives au service Audience Destinations et au connecteur de données Adobe Experience Platform ont été regroupées dans une nouvelle section.

Désormais, la source de données **d&#39;ID déclarés** peut également être utilisée avec l&#39;intégration de People Core Service. Des informations ont été ajoutées à la documentation sur l’intégration de Campaign-Audience Manager ou People Core Service. [En savoir plus](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Des informations ont été ajoutées au sujet de l&#39;implémentation du tracking local pour les applications mobiles. [En savoir plus](../../administration/using/local-tracking.md)

La section [Délivrabilité](../../sending/using/about-deliverability.md) a été mise à jour et inclut désormais des liens vers le nouveau [Guide des bonnes pratiques relatives à la délivrabilité d&#39;Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr). Toutes les informations génériques relatives à la délivrabilité qui peuvent s&#39;appliquer à diverses solutions d&#39;Adobe ont été déplacées vers l&#39;[annexe du guide des bonnes pratiques](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=fr#additional-resources).

## Version 21.1 - Février 2021               {#release-21-1---february-2021}

**Nouvelles fonctionnalités de cette version**

Service de retour d&#39;e-mail – [En savoir plus](../../sending/using/confirming-the-send.md#message-indicators)

Améliorations de l&#39;intégration d&#39;Adobe Experience Manager - [En savoir plus](../../integrating/using/creating-multilingual-email-aem.md)

Interface Experience Cloud unifiée – [En savoir plus](../../start/using/interface-description.md#top-bar)

**Autres mises à jour de la documentation accompagnant cette version**

Des informations ont été ajoutées sur la façon de rechercher un profil en fonction de l&#39;email, du prénom, du nom ou de tout champ personnalisé. [En savoir plus](../../audiences/using/integrated-customer-profile.md)

Des informations ont été ajoutées sur la nouvelle fonction GetOption qui vous permet de renvoyer la valeur d&#39;une fonction spécifiée lors de l&#39;appel d&#39;un workflow avec des paramètres externes. [En savoir plus](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

Des informations ont été ajoutées sur la nouvelle variable de sortie **[!UICONTROL filesCount]** disponible après l&#39;utilisation d&#39;une activité **[!UICONTROL Transfert de fichier]**. [En savoir plus](../../automating/using/transfer-file.md#output-variables)

La section **Configuration du canal email** a été mise à jour afin de clarifier les derniers paramètres de messagerie applicables. Certains anciens paramètres encore utilisés pour certains clients sont répertoriés en bas de la page. [En savoir plus](../../administration/using/configuring-email-channel.md)

Des informations ont été ajoutées sur la manière de s&#39;assurer qu&#39;un workflow planifié n&#39;est pas replanifié tant qu&#39;une ou plusieurs tâche(s) d&#39;une exécution précédente sont encore en attente. [En savoir plus](../../automating/using/scheduled-workflows-execution.md)

## Décembre 2020 {#doc-updates-december-2020}

La fonctionnalité d&#39;**optimisation prédictive de l&#39;objet** est désormais obsolète. [En savoir plus](../../rn/using/deprecated-features.md)

La section **Prise en main de la messagerie transactionnelle** comprend désormais des [schémas améliorés](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) pour une meilleure compréhension du processus.

Un cas pratique de bout en bout est désormais disponible pour illustrer le processus de mise en œuvre de la messagerie transactionnelle. [En savoir plus](../../channels/using/transactional-messaging-use-case.md)

La section **Confidentialité** a été déplacée [ici](../../start/using/privacy.md).

Une nouvelle page **Accessibilité** est disponible : elle présente la prise en charge de l’accessibilité dans l’espace de travail Adobe Campaign Standard. [En savoir plus](../../start/using/accessibility.md)

Une note d&#39;avertissement a été ajoutée, indiquant que, pour des performances optimales, le nombre de messages transactionnels publiés doit rester inférieur à 100. [En savoir plus](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

La page des paramètres et protocoles du connecteur SMS a été déplacée [ici](../../administration/using/sms-protocol.md).

La section **Utilisation des listes de produits dans un message transactionnel** a été déplacée [ici](../../designing/using/using-product-listings.md).

## Novembre 2020 {#doc-updates-november-2020}

La section **Données personnelles et personnes concernées** a été mise à jour avec un scénario d&#39;utilisation afin d&#39;illustrer comment les différents acteurs impliqués interagissent en matière de confidentialité. [En savoir plus](../../start/using/privacy.md#use-case-scenario)

Une nouvelle section énumérant les questions fréquentes relatives à la protection des données personnelles a été ajoutée. [En savoir plus](../../start/using/privacy-faq.md)

La section **Confidentialité** a été déplacée et enrichie de deux nouvelles pages : [Gestion de la confidentialité](../../start/using/privacy-management.md) et [Gestion des demandes d&#39;accès à des informations personnelles](../../start/using/privacy-requests.md).

La section **Messagerie transactionnelle** a été réorganisée et regroupée en un seul emplacement pour une navigation améliorée. [En savoir plus](../../channels/using/getting-started-with-transactional-msg.md)

Des informations ont été ajoutées dans la section Connecteur de données Adobe Experience Platform sur l&#39;erreur de validation du mapping de données liée à la gestion de la confidentialité et sur la manière de la résoudre.

## Version 20.4 - Octobre 2020        {#release-20-4---october-2020}

**Nouvelles fonctionnalités de cette version**

Populations témoins – [En savoir plus](../../sending/using/control-group.md)

API externe (prise en charge OAuth).  [En savoir plus](../../automating/using/external-api.md)

Intégration de l&#39;IA dédiée au parcours.  [En savoir plus](../../sending/using/predictive.md)

**Autres mises à jour de la documentation accompagnant cette version**

La section relative à l&#39;appel d&#39;un workflow avec des paramètres externes a été enrichie de nouvelles fonctions disponibles dans l&#39;éditeur d&#39;expression. [En savoir plus](../../automating/using/customizing-workflow-external-parameters.md)

Une recommandation a été ajoutée aux meilleures pratiques des workflows concernant le nombre d&#39;activités à utiliser par workflow. [En savoir plus](../../automating/using/best-practices-workflows.md#number-activities)

Ajout d&#39;une section sur les bonnes pratiques relatives aux diffusions. [En savoir plus](../../sending/using/delivery-best-practices.md)

Une section a été ajoutée pour décrire les nouveaux filtres qui permettent de rechercher les configurations des événements en fonction de leur statut et de la dernière réception d&#39;un événement. [En savoir plus](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## Septembre 2020 {#doc-updates-september-2020}

La section relative aux **messages transactionnels Événement** a été réorganisée et clarifiée. [En savoir plus](../../channels/using/editing-transactional-message.md)

Une note d&#39;avertissement a été ajoutée pour avertir les utilisateurs des limitations d&#39;autorisations liées à l&#39;accès au journal. [En savoir plus](../../administration/using/users-management.md)

Une nouvelle section a été ajoutée pour détailler le processus de création d&#39;une nouvelle marque. [En savoir plus](../../administration/using/branding.md#creating-a-brand)

La nouvelle intégration Campaign Standard - Microsoft Dynamics 365 est désormais disponible – [En savoir plus](../../integrating/using/d365-acs-get-started.md)

Des informations sur les sources anonymes ont été ajoutées dans le rapport Profils actifs. [En savoir plus](../../audiences/using/active-profiles.md)

## Août 2020 {#doc-updates-august-2020}

Une nouvelle section mise à jour concernant la prise en main de la messagerie transactionnelle est disponible. [En savoir plus](../../channels/using/getting-started-with-transactional-msg.md)

La variable **Limites des messages transactionnels** section déplacée [here](../../channels/using/transactional-messaging-limitations.md).

La section **Préparation de l&#39;envoi** a été déplacée [ici](../../sending/using/preparing-the-send.md).

## Juillet 2020 {#doc-updates-july-2020}

Une nouvelle section a été ajoutée avec des directives relatives à la surveillance Campaign Standard. [En savoir plus](../../administration/using/monitoring-guidelines.md)

La section Limites et mécanismes de sécurisation de l&#39;API externe a été mise à jour. [En savoir plus](../../automating/using/external-api.md#guardrails)

La page Vue d’ensemble de la gestion de la protection des données a été mise à jour pour inclure des informations relatives aux réglementations PDPA (Personal Data Protection Act) thaïlandaise et LGPD (Lei Geral de Proteção de Dados) brésilienne. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

Le guide Canal mobile a été réorganisé et amélioré. Un nouveau guide Configuration des canaux mobiles a été ajouté avec la documentation technique sur la configuration mobile. [En savoir plus](../../administration/using/push-tracking.md)

La page Gestion de la confidentialité dans Campaign Standard a été mise à jour, avec notamment des clarifications sur la façon de gérer les demandes d&#39;accès aux informations personnelles par le biais de l&#39;intégration de Privacy Core Service. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

Nouvelles fonctionnalités d&#39;e-mails optimisées par l&#39;IA : optimisation du temps d&#39;envoi et scores de profil. [En savoir plus](../../sending/using/predictive.md)

## Juin 2020 {#doc-updates-june-2020}

Les cas d&#39;utilisation des workflows ont été mis à jour et réorganisés en sections thématiques. [En savoir plus](../../automating/using/about-workflow-use-cases.md)

Des cas d&#39;utilisation ont été ajoutés pour [chiffrer](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt) et [déchiffrer](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt) des données à l&#39;aide du Panneau de contrôle et des workflows Campaign.

Les références à l&#39;ancien site web d&#39;assistance ont été remplacées par la nouvelle URL. [En savoir plus](../../support.md)

La configuration de compte Litmus personnalisé a été supprimée de la fonctionnalité d&#39;Inbox rendering. [En savoir plus](../../sending/using/email-rendering.md)

L’intégration Campaign Standard - Microsoft Dynamics 365 n’est actuellement pas disponible. Un nouveau connecteur est en cours de développement et sera prochainement disponible. Les pages d&#39;aide connexes ont été supprimées. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

## Mai 2020 {#doc-updates-may-2020}

La page de présentation de Campaign Standard a été enrichie et réorganisée en thèmes. [En savoir plus](../../start/using/about-campaign-standard.md)

La section Paramètres du canal email a été clarifiée avec des informations supplémentaires sur les champs de masques autorisés et l&#39;identifiant des rapports de diffusion. [En savoir plus](../../administration/using/configuring-email-channel.md)

La section Configuration d&#39;une application mobile à l&#39;aide des SDK Adobe Experience Platform est désormais disponible dans la documentation de base avec des informations supplémentaires concernant la synchronisation de l&#39;application mobile AEPSDK depuis le workflow technique de Launch. [En savoir plus](../../administration/using/configuring-a-mobile-application.md)

## Version 20.3 - Mai 2020                {#release-20-3---may-2020}

**Nouvelles fonctionnalités de cette version**

La loi thaïlandaise sur la protection des données personnelles (PDPA).  [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html)

Activité API externe (GA).  [En savoir plus](../../automating/using/external-api.md)

**Autres mises à jour de la documentation accompagnant cette version**

Des informations ont été ajoutées sur le champ **[!UICONTROL Jours d&#39;historique]** dans les propriétés de workflow, qui incluent désormais les fichiers téléchargés par l&#39;activité **[!UICONTROL Transfert de fichier]**. [En savoir plus](../../automating/using/managing-execution-options.md)

Des informations ont été ajoutées dans la section de substitution de profil concernant la limite de 500 caractères du préfixe de ligne d&#39;objet. [En savoir plus](../../sending/using/testing-messages-using-target.md)

Une nouvelle section consacrée à la protection des informations personnelles et au consentement a été ajoutée à la documentation de base. [En savoir plus](../../start/using/privacy.md)

Un cas d’utilisation a été ajouté pour vous permettre de convertir les e-mails de l’ancien éditeur dans le concepteur d’e-mail – [En savoir plus](../../designing/using/converting-emails-from-legacy-editor.md)

Une section de questions fréquentes a été ajoutée au sujet du concepteur d’e-mail – [En savoir plus](../../designing/using/faq-email-designer.md)

## Avril 2020 {#doc-updates-april-2020}

L&#39;intégration de Microsoft Dynamics 365 avec la documentation d’Adobe Campaign Standard est désormais disponible dans la documentation principale. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

Des ressources supplémentaires ont été ajoutées à la page d&#39;accueil de la documentation. [En savoir plus](../../campaign-standard-home.md)

Des informations sur le service d’identité Experience Cloud (ECID) ont été ajoutées à la documentation du connecteur Adobe Experience Platform.

La section Messages transactionnels a été améliorée avec des informations sur l&#39;accès aux derniers événements transactionnels et des captures d&#39;écran mises à jour. [En savoir plus](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

Les typologies et la documentation des règles de typologie ont été améliorées et mises à jour avec des informations supplémentaires sur les règles de typologie natives. [En savoir plus](../../sending/using/about-typology-rules.md)

Des informations ont été ajoutées sur l&#39;action **[!UICONTROL Listage de fichiers]** de l&#39;activité **[!UICONTROL Transfert de fichier]**. [En savoir plus](../../automating/using/transfer-file.md)

La documentation sur les reprises après un échec temporaire de diffusion a été mise à jour avec plus de détails sur la manière dont les reprises sont gérées une fois mises à niveau vers le MTA amélioré. [En savoir plus](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

La section Supprimer un message transactionnel a été améliorée et clarifiée. [En savoir plus](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

La section **Aperçu des diffusions** a été mise à jour avec des exemples de diffusions mobiles. [En savoir plus](../../sending/using/previewing-messages.md)

Des bonnes pratiques ont été ajoutées en ce qui concerne les messages transactionnels et la suppression d&#39;événements en temps réel inutilisés. [En savoir plus](../../channels/using/configuring-transactional-event.md#creating-an-event)

La section Configuration du canal Email a été mise à jour afin d&#39;apporter des éclaircissements sur tous les paramètres de messagerie qui sont désormais gérés par le MTA amélioré. [En savoir plus](../../administration/using/configuring-email-channel.md)

La section Messages transactionnels a été mise à jour avec des informations supplémentaires sur les droits nécessaires pour modifier les configurations des événements et sur la manière d&#39;enrichir les collections dans les messages transactionnels. [En savoir plus](../../channels/using/configuring-transactional-event.md).

## Version 20.2 - Avril 2020                {#release-20-2---april-2020}

**Nouvelles fonctionnalités de cette version**

Intégration de Blob Azure.  [En savoir plus](../../administration/using/external-accounts.md#microsoft-azure-external-account)

Test d&#39;e-mails à l&#39;aide de profils ciblés – [En savoir plus](../../sending/using/testing-messages-using-target.md)

**Autres mises à jour de la documentation accompagnant cette version**

Ajout d&#39;une limite au rendu des messages In-App. [En savoir plus](../../channels/using/customizing-an-in-app-message.md)

Ajout d&#39;informations sur l&#39;utilisation des agrégats dans une activité **[!UICONTROL Requête]**. [En savoir plus](../../automating/using/query.md#adding-an-aggregate)

Ajout d&#39;une limite avec MCPNS lors de la configuration d&#39;une application mobile. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html)

Ajout d&#39;une nouvelle section sur les instructions de configuration au guide Administration. Déplacement de la section relative aux navigateurs et aux systèmes d&#39;exploitation compatibles du Guide de prise en main vers cette section. Ajout également d’une note technique sur les points d’entrée réseau Campaign Standard à cette section. [En savoir plus](../../administration/using/about-configuration-guidelines.md)

Disponibilité d&#39;une nouvelle section décrivant comment supprimer une configuration d&#39;événement. [En savoir plus](../../channels/using/publishing-transactional-event.md#deleting-an-event)

Mise à jour des sections sur les messages transactionnels pour prendre en compte les mises à jour et améliorations de l&#39;interface utilisateur. [En savoir plus](../../channels/using/getting-started-with-transactional-msg.md)

Mise à jour des informations relatives aux mécanismes de sécurisation pour l&#39;activité API externe. [En savoir plus](../../automating/using/external-api.md)

## Mars 2020 {#doc-updates-march-2020}

Ajout à la documentation principale d’informations plus détaillées sur le MTA amélioré, notamment en ce qui concerne les règles de gestion des e-mails et la qualification des e-mails rejetés. [En savoir plus](../../administration/using/configuring-email-channel.md#email-processing-rules)

Déplacement et mise à jour de la section consacrée à l&#39;archivage avec e-mail Cci. [En savoir plus](../../sending/using/archiving.md)

Mise à jour de la documentation sur la configuration d&#39;une application mobile et des pages connexes pour prendre en compte l&#39;obsolescence du SDK V4. [En savoir plus](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html)

Mise à jour et amélioration de la documentation sur l’intégration Adobe Campaign Standard/Adobe Experience Manager –  [En savoir plus](../../integrating/using/configure-experience-manager.md)

Mise à jour de la documentation sur le concepteur d’e-mail de Campaign et des pages connexes pour prendre en compte l&#39;obsolescence du [!DNL Adobe Creative SDK]. [En savoir plus](../../rn/using/deprecated-features.md)

Disponibilité d’une nouvelle section consacrée aux bonnes pratiques relatives au modèle de données Campaign Standard –  [En savoir plus](../../developing/using/data-model-best-practices.md)

Ajout d&#39;informations sur le droit natif **[!UICONTROL Workflow]**. [En savoir plus](../../administration/using/list-of-roles.md)

Ajout d&#39;informations au **[!UICONTROL champ Jours d&#39;historique]** disponible dans les propriétés du workflow. [En savoir plus](../../automating/using/about-workflow-execution.md)

## Version 20.1 - Février 2020               {#release-20-1---february-2020}

**Nouvelles fonctionnalités de cette version**

Adobe Experience Platform Data Connector (version bêta)

Audience Destinations (version bêta)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour de la documentation relative à la gestion de la confidentialité avec des informations sur la création du champ d&#39;opt-out du CCPA pour les ressources de profil personnalisées. [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html)

Réorganisation et amélioration des notes de mise à jour. [En savoir plus](../../rn/using/release-notes.md)

Ajout d&#39;informations relatives au groupe de sécurité Administrateurs, indiquant que l&#39;entité organisationnelle **[!UICONTROL Tous (tous)]** lui est affectée et ne peut pas être modifiée. [En savoir plus](../../administration/using/managing-groups-and-users.md)

Ajout d&#39;informations sur la définition d&#39;un fuseau horaire spécifique à utiliser par défaut dans un workflow. [En savoir plus](../../automating/using/building-a-workflow.md)

Ajout d&#39;informations dans le guide Utilisation des API concernant le nouveau paramètre **_forcePagination=true**, qui permet d&#39;effectuer une pagination sur des tables volumineuses. [En savoir plus](../../api/using/pagination.md)

Ajout d&#39;une nouvelle section décrivant les avertissements pouvant être affichés dans un tableau de bord de messages. [En savoir plus](../../channels/using/message-dashboard.md#warnings)

Disponibilité de la documentation relative au MTA amélioré d’Adobe Campaign, qui décrit l’infrastructure d’envoi mise à niveau afin d’améliorer la délivrabilité, le débit et la gestion des rebonds. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/campaign-enhanced-mta.html)

Ajout de notes pour indiquer que les URL du serveur d&#39;applications et du serveur de pages miroir doivent être sécurisées pour que les aperçus des landing pages et des pages miroir s&#39;affichent dans l&#39;interface utilisateur de Campaign. [En savoir plus](../../administration/using/branding.md#configuring-and-using-brands)

Mise à jour de la section sur l&#39;export des logs pour indiquer la disponibilité de l&#39;identifiant de log de diffusion dans les ressources des logs de diffusion et de tracking, ce qui permet d&#39;exporter un identifiant unique pour chaque log. [En savoir plus](../../automating/using/exporting-logs.md)

## Janvier 2020 {#doc-updates-january-2020}

La documentation relative à la délivrabilité a été mise à jour avec une nouvelle section concernant la certification IP. <!--[Read more](../../sending/using/ip-certification.md)-->

Disponibilité d&#39;une nouvelle section décrivant la création d&#39;un workflow de diffusion cross-canal. [En savoir plus](../../automating/using/workflow-cross-channel-delivery.md)

Mise à jour de la section Calcul des indicateurs pour les rapports dynamiques. [En savoir plus](../../reporting/using/indicator-calculation.md)

Ajout d&#39;une nouvelle page sur les directives générales relatives aux diffusions mobiles dans Adobe Campaign Standard. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-mobile.html)

Mise à jour de la documentation relative à l’utilisation de Campaign et d’Experience Manager avec une nouvelle section de **conseils sur l’utilisation de l’intégration Campaign-Experience Manager** –  [En savoir plus](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

Amélioration de la page d&#39;accueil de la documentation des API avec des redirections vers les différentes rubriques. [En savoir plus](../../api/using/get-started-apis.md)

## Nov. - Déc. 2019 {#doc-updates-december-2019}

La documentation du compte externe Configuration S3 a été mise à jour. [En savoir plus](../../administration/using/external-accounts.md#amazon-s3-external-account)

La section Concevoir un contenu d&#39;e-mail a été réorganisée. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

Le guide de prise en main de la délivrabilité a été intégré à la documentation de base et mis à jour. [En savoir plus](../../sending/using/about-deliverability.md)

Le guide de prise en main sur l&#39;export/import des ressources personnalisées a été intégré dans la documentation principale. [En savoir plus](../../automating/using/exporting-importing-custom-resources.md)

Ajout d’un nouveau cas pratique, décrivant comment créer une population témoin à l’aide d’un workflow dans Campaign Standard.

Les informations relatives aux propriétés des pages de destination ont été déplacées dans une section dédiée. [En savoir plus](../../channels/using/configuring-landing-page.md)

La documentation du Panneau de contrôle a été intégrée au nouvel ensemble de documentation collaborative. [En savoir plus](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr)

Le tableau de **calcul des indicateurs** a été mis à jour. [En savoir plus](../../reporting/using/indicator-calculation.md)

Le jeu de documentation des API a été intégré à la documentation de Campaign Standard.[En savoir plus](../../api/using/get-started-apis.md)

La section de prise en main de la création d&#39;un email personnalisé a été déplacée et mise à jour. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-get-started-with-emails.html)

Mise à jour du guide de prise en main des bonnes pratiques de diffusion. [En savoir plus](../../sending/using/delivery-best-practices.md)

Le datamodel a été intégré à la documentation de Campaign Standard. [En savoir plus](../../developing/using/datamodel-audience.md)

Le nouveau point d’entrée d’API **/customResources** a été ajouté à la documentation de l’API. [En savoir plus](../../api/using/interacting-with-custom-resources.md)

## Version 19.4 - Octobre 2019        {#release-19-4---october-2019}

**Nouvelles fonctionnalités de cette version**

California Consumer Privacy Act (CCPA) – [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/acs-privacy.html#ccpa)

Intégration de Microsoft Dynamics 365 (GA) – [En savoir plus](../../integrating/using/d365-acs-get-started.md)

**Autres mises à jour de la documentation accompagnant cette version**

La liste des messages d’erreur d’Adobe Campaign a été mise à jour. [En savoir plus](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html)

Amélioration et enrichissement du guide de prise en main du RGPD. Il s&#39;agit maintenant d&#39;une documentation sur la gestion de la vie privée, incluant le RGPD et la CCPA. [En savoir plus](https://helpx.adobe.com/content/help/fr/campaign/kb/campaign-privacy.html)

Ajout d&#39;un nouveau graphique présentant le processus de publication des messages transactionnels. [En savoir plus](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

Le guide de prise en main des bonnes pratiques de diffusion a été déplacé et mis à jour. [En savoir plus](../../sending/using/delivery-best-practices.md)

Ajout d&#39;une nouvelle section. Elle fournit un aperçu des différentes méthodes qui vous permettent d&#39;enrichir la base de données Campaign Standard. [En savoir plus](../../audiences/using/enriching-campaign-database.md)

Une nouvelle section décrivant l&#39;association du style au concepteur d’e-mails a été ajoutée. [En savoir plus](../../designing/using/styles.md#about-styling-links)

Des informations relatives à la confidentialité ont été ajoutées à la documentation des API. [Cliquez ici](../../api/using/creating-a-privacy-request.md)

## Sept. - Oct. 2019 {#doc-updates-october-2019}

Ajout d&#39;une nouvelle section relative aux paramètres de Campaign Standard. [En savoir plus](../../administration/using/about-campaign-standard-settings.md)

Ajout d&#39;une nouvelle section décrivant comment envoyer un email de confirmation personnalisé automatique aux profils qui s&#39;abonnent à un service spécifique. [En savoir plus](../../audiences/using/confirming-subscription-to-a-service.md)

La section Messagerie transactionnelle a été modifiée en fonction des dernières mises à jour de l&#39;interface utilisateur, y compris l&#39;édition du contenu avec le concepteur d’e-mails. [En savoir plus](../../channels/using/editing-transactional-message.md)

Réorganisation du chapitre sur les landing pages. Il a également été enrichi d&#39;une nouvelle section décrivant les étapes de configuration d&#39;une landing page. [En savoir plus](../../channels/using/getting-started-with-landing-pages.md)

Une nouvelle section a été ajoutée dans la section des notifications push sur la création et la mise à jour des informations de profil en fonction des données d&#39;abonnement aux applications mobiles. [En savoir plus](../../channels/using/updating-profile-with-mobile-app-data.md)

Un nouvel exemple a été ajouté pour montrer comment envoyer un email contenant des données supplémentaires extraites d&#39;une activité de chargement de fichier. [En savoir plus](../../automating/using/sending-email-enriched-fields.md)

Une nouvelle section sur l&#39;utilisation des pièges a été ajoutée. [En savoir plus](../../sending/using/using-traps.md)

Une note sur l&#39;option **Launch_URL_Campaign** a été ajoutée à la page sur la configuration d&#39;une application mobile à l&#39;aide des SDK Adobe Experience Platform. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html)

Réorganisation du guide du concepteur d’e-mails. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

## Août 2019 {#doc-updates-august-2019}

Ajout d&#39;une section comportant des cas pratiques sur les workflows axés sur les requêtes. [En savoir plus](../../automating/using/workflow-created-query-with-complement.md)

Ajout d&#39;une procédure dans la section de dépannage des workflows. Celle-ci aborde la manière d&#39;afficher les requêtes SQL dans l&#39;onglet Log. [En savoir plus](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

Ajout d’un article d’aide comportant des informations relatives aux sous-domaines et à la gestion des certificats dans le Panneau de contrôle –  [En savoir plus](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=fr)

Mise à jour de la section décrivant les modèles et les fragments de contenu. [En savoir plus](../../designing/using/using-reusable-content.md#content-templates)

Ajout d&#39;une section décrivant comment enregistrer un contenu d&#39;email en tant que modèle dans le concepteur d’e-mails. [En savoir plus](../../designing/using/using-reusable-content.md#saving-content-as-template)

## Version 19.3 - Juillet 2019                {#release-19-3---july-2019}

**Nouvelles fonctionnalités de cette version**

Activité API externe (version bêta publique) – [En savoir plus](../../automating/using/external-api.md)

Rapport sur le segment de workflow – [En savoir plus](../../reporting/using/creating-a-report-workflow-segment.md)

**Autres mises à jour de la documentation accompagnant cette version**

Disponibilité du Guide de mise en œuvre de Campaign Standard –[En savoir plus](https://helpx.adobe.com/fr/campaign/kb/campaign-standard-implementation-guide.html)

Création d&#39;un ensemble de nouveaux articles d&#39;aide sur l&#39;implémentation et l&#39;utilisation du connecteur Microsoft Dynamics 365. Cette fonctionnalité est actuellement en disponibilité limitée. [En savoir plus](../../integrating/using/d365-acs-get-started.md)

Ajout d&#39;une note à la section [Appeler un workflow avec des paramètres](../../automating/using/calling-a-workflow-with-external-parameters.md) concernant la préparation d&#39;une diffusion et la période d&#39;agrégation.

Des informations ont été ajoutées sur la personnalisation du libellé d’une diffusion avec des variables d’événements qui ont été déclarées dans l’activité de signal externe du workflow. [En savoir plus](../../automating/using/external-signal.md)

Ajout d’une section présentant comment créer un utilisateur dans Adobe Campaign Standard –  [En savoir plus](../../administration/using/users-management.md)

Disponibilité d&#39;un nouvel article comprenant des conseils pour simplifier les campagnes marketing, notamment des liens vers la documentation du produit et des vidéos de tutoriel. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/simplify-campaign-management.html)

Ajout d&#39;une section de résolution des problèmes pour les rapports dynamiques. [En savoir plus](../../reporting/using/troubleshooting.md)

Ajout d&#39;un diagramme expliquant comment les différents modèles In-App gèrent les informations personnelles. [En savoir plus](../../channels/using/preparing-and-sending-an-in-app-message.md)

Mise à jour de la section sur l&#39;enregistrement du contenu d&#39;un email en tant que fragment dans le concepteur d’e-mails. [En savoir plus](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

Ajout d’un avertissement sur l’impact des espaces blancs supplémentaires sur la mise en page du contenu d’un email. [En savoir plus](../../designing/using/personalization.md#creating-custom-content-blocks)

Ajout d&#39;une section sur les mises à jour recommandées du concepteur d’e-mails. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

Ajout d&#39;une section sur les bonnes pratiques relatives aux workflows. [En savoir plus](../../automating/using/best-practices-workflows.md)

Mise à jour de la liste des messages d&#39;erreur de Standard et Campaign Classic. [En savoir plus](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=fr)

Ajout d&#39;un avertissement à la documentation des ressources personnalisées. Il est recommandé d&#39;utiliser 30 caractères maximum pour les identifiants des ressources personnalisées. Cette recommandation s&#39;applique également aux champs de ressources personnalisées, aux clés, aux index et aux liens. [En savoir plus](../../developing/using/creating-or-extending-the-resource.md)

## Juin - Juillet 2019 {#doc-updates-2019}

Ajout d&#39;une page sur les limites des landing pages. [En savoir plus](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

Ajout d&#39;un cas pratique sur la façon d&#39;appeler un profil à l&#39;aide d&#39;une clé d&#39;identification composite. [En savoir plus](../../developing/using/uc-calling-resource-id-key.md)

Ajout d&#39;une recommandation concernant l&#39;utilisation des diffusions récurrentes sans période d&#39;agrégation lors de l&#39;appel d&#39;un workflow avec des paramètres. [En savoir plus](../../automating/using/calling-a-workflow-with-external-parameters.md)

Mise à jour de la liste des messages d&#39;erreur de Standard et Campaign Classic. [En savoir plus](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=fr)

Ajout d&#39;un avertissement à la documentation des ressources personnalisées. Il est recommandé d&#39;utiliser 30 caractères maximum pour les identifiants des ressources personnalisées. Cette recommandation s&#39;applique également aux champs de ressources personnalisées, aux clés, aux index et aux liens. [En savoir plus](../../developing/using/creating-or-extending-the-resource.md)

## Version 19.2 - Mai 2019  {#release-19-2---may-2019}

**Nouvelles fonctionnalités de cette version**

Panneau de contrôle – [En savoir plus](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr)

Notifications locales – [En savoir plus](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

Améliorations apportées aux workflows : ajout d&#39;une payload à l&#39;activité de signal externe – [En savoir plus](../../automating/using/calling-a-workflow-with-external-parameters.md)

Améliorations apportées aux landing pages : Google reCAPTCHA – [En savoir plus](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour de l&#39;article sur la délégation de nom de domaine. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/domain-name-delegation.html)

Publication d&#39;un nouvel article sur le calendrier des versions pour communiquer les dates des prochaines versions. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-release-planning.html)

Mise à jour des liens d&#39;aide contextuelle directement accessibles depuis Adobe Campaign.

Cette [page](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=fr) devient la page officielle des vidéos d’Adobe Campaign Standard.

Ajout d&#39;une section sur la rétention des données comprenant les valeurs de rétention par défaut pour les tables standards. [En savoir plus](../../administration/using/data-retention.md)

Ajout d&#39;une section sur les mises à jour et les opérations de maintenance. [En savoir plus](../../administration/using/updates-and-maintenance-operations.md)

Ajout d&#39;informations sur la nouvelle option de tri de l&#39;activité **Transfert de fichier**. [En savoir plus](../../automating/using/transfer-file.md)

Mise à jour de la [documentation sur les API REST](../../api/using/get-started-apis.md) :

* Ajout d’une nouvelle section comportant des informations génériques sur les raisons d’utiliser les API REST Campaign Standard
* Mise à disposition d&#39;un ensemble de requêtes d&#39;API préconçues, représentant des cas pratiques courants
* Ajout d&#39;une section sur la gestion des entités organisationnelles
* Ajout d&#39;informations sur la création d&#39;un service
* Ajout d&#39;informations sur l&#39;appel d&#39;un workflow avec des paramètres

Ajout d&#39;informations sur la nouvelle activité **Test**. [En savoir plus](../../automating/using/test.md)

Mise à jour du guide sur l&#39;automatisation avec des liens vers les activités de workflow associées. [En savoir plus](../../automating/using/workflow-interface.md#palette)

Mise à jour de la section Calcul des indicateurs pour les rapports dynamiques. [En savoir plus](../../reporting/using/indicator-calculation.md)

Ajout d&#39;un tableau sur la compatibilité des rapports dynamiques pour mieux comprendre la compatibilité entre les dimensions et les mesures. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

Mise à jour de la liste des fonctions pour les workflows. [En savoir plus](../../automating/using/list-of-functions.md)

Réorganisation et étoffement du chapitre Conception du contenu avec une nouvelle section décrivant de façon claire les différentes méthodes de conception d&#39;un email en utilisant des contenus existants dans le concepteur d’e-mails. [En savoir plus](../../designing/using/using-existing-content.md)

Ajout d&#39;une section sur l&#39;enregistrement du contenu d&#39;un email en tant que fragment dans le concepteur d’e-mails. [En savoir plus](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

Mise à jour de la section sur la gestion des liens avec des informations supplémentaires sur la gestion des URL trackées dans le concepteur d’e-mails. [En savoir plus](../../designing/using/links.md#inserting-a-link)

Ajout d&#39;une section pour décrire le processus spécifique à la reprise des messages transactionnels. [En savoir plus](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

Clarification et mise à jour de la section sur la publication d&#39;une ressource avec l&#39;extension d&#39;API avec les dernières modifications apportées à l&#39;interface utilisateur. [En savoir plus](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

Attribution d&#39;un nouveau nom à la section Archivage des emails et réorganisation de celle-ci. [En savoir plus](../../sending/using/archiving.md)

Mise à jour de la section Créer un email pour prendre en compte les dernières modifications apportées à l&#39;interface. [En savoir plus](../../channels/using/creating-an-email.md)

Mise à jour de l&#39;article [Protocole et paramètres du connecteur SMS](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html) de la base de connaissances avec l&#39;option ajoutée au compte externe SMS afin de limiter le nombre d&#39;instances MTA autorisées pour la connexion au fournisseur SMPP.

Enrichissement et réorganisation du guide de démarrage. [En savoir plus](../../start/using/about-campaign-standard.md)

Mise à jour de la page Fonctionnalités obsolètes et supprimées. [En savoir plus](../../rn/using/deprecated-features.md)

Mise à jour et restructuration de la section sur l&#39;intégration de Dreamweaver. [En savoir plus](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## Version 19.1 - Février 2019               {#release-19-1---february-2019}

**Nouvelles fonctionnalités de cette version**

Améliorations du reporting du canal push – [En savoir plus](../../reporting/using/push-notification-report.md)

Intégration de Launch pour les applications mobiles – [En savoir plus](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

Messagerie In-App mobile – [En savoir plus](../../channels/using/about-in-app-messaging.md)

Améliorations des workflows – En savoir plus [ici](../../automating/using/workflow-interface.md#duplicating-workflow-activities) et [ici](../../automating/using/load-file.md#configuration)

**Autres mises à jour de la documentation accompagnant cette version**

Ajout au chapitre Editer un contenu d&#39;email de la nouvelle expérience d&#39;intégration pour la création de contenu d&#39;email et d&#39;autres améliorations apportées au concepteur d’e-mails. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

Ajout d&#39;une section sur les limites des messages transactionnels. [En savoir plus](../../channels/using/transactional-messaging-limitations.md)

Ajout d’une section comparant les différentes options de création d’email dans Adobe Campaign –  [En savoir plus](../../designing/using/using-integrations.md#email-design-options-comparison)

La section Créer des blocs de contenu personnalisés a été étoffée avec des détails sur les dimensions de ciblage. [En savoir plus](../../designing/using/personalization.md#creating-custom-content-blocks)

Ajout d&#39;un avertissement indiquant que le concepteur d’e-mails ne prend pas en charge Internet Explorer 11. [En savoir plus](../../administration/using/about-configuration-guidelines.md)

Ajout d&#39;avertissements à la section Supprimer une ressource concernant la réinitialisation. [En savoir plus](../../developing/using/deleting-a-resource.md)

Mise à jour du chapitre sur l&#39;ajout ou l&#39;extension d&#39;une ressource. [En savoir plus](../../developing/using/creating-or-extending-the-resource.md)

Ajout d&#39;un cas pratique sur l&#39;extension de la ressource personnalisée de profils. [En savoir plus](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

Ajout d&#39;informations sur la liaison de ressources personnalisées. [En savoir plus](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

Ajout d&#39;une technote sur l&#39;affichage d&#39;une image d&#39;une notification push Adobe Campaign Standard. [En savoir plus](../../administration/using/image-push-notification.md)

Ajout d&#39;une technote sur la mise en œuvre du tracking des notifications push. [En savoir plus](../../administration/using/push-tracking.md)

Mise à jour de la liste des messages d&#39;erreur de Standard et Campaign Classic. [En savoir plus](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=fr)

Mise à jour de la documentation sur l&#39;intégration Triggers - Campaign. [En savoir plus](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Mise à jour des liens d&#39;aide contextuelle disponibles directement dans Adobe Campaign.

Ajout d&#39;une note sur l&#39;ajout d&#39;un horodatage au nom du fichier contenant les enregistrements rejetés. [En savoir plus](../../automating/using/load-file.md#configuration)

Ajout d&#39;informations lors de l&#39;import de champs composés de colonnes de longueur fixe. [En savoir plus](../../automating/using/load-file.md#configuration)

Ajout d&#39;informations sur l&#39;option permettant de conserver les enregistrements rejetés dans un fichier. Cette option permet maintenant d&#39;appliquer une phase de post-traitement au fichier contenant les enregistrements rejetés. [En savoir plus](../../automating/using/load-file.md#configuration)

Ajout d&#39;une section sur la duplication des activités de workflow grâce à des opérations de copier-coller. [En savoir plus](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

Ajout d&#39;informations sur la nouvelle option des activités Requête ([en savoir plus](../../automating/using/query-samples.md)) et Segmentation ([en savoir plus](../../automating/using/segmentation.md)). Celle-ci permet d&#39;ajouter une transition sortante après l&#39;activité si aucune donnée n&#39;est récupérée.

Ajout d&#39;informations à la section sur l&#39;activité Mise à jour de données. Ces informations concernent le nouveau champ Taille du lot qui permet de définir la taille maximale du lot des données à charger. [En savoir plus](../../automating/using/update-data.md#configuration)

Ajout d&#39;informations à la section sur l&#39;activité Extraction de fichier. Ces informations concernent la nouvelle option permettant de désactiver le processus de génération de fichier si la transition sortante est vide. [En savoir plus](../../automating/using/extract-file.md#configuration)

## Version 19.0 - Janvier 2019               {#release-19-0---january-2019}

**Nouvelles fonctionnalités de cette version**

Disponibilité générale du concepteur d’e-mails – [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

Listes de produits dans les emails transactionnels – [En savoir plus](../../designing/using/using-product-listings.md)

Vue mobile dans le concepteur d’e-mails – [En savoir plus](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

Améliorations de la Messagerie In-App (version bêta) – [En savoir plus](../../channels/using/about-in-app-messaging.md)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour du guide Conception de contenu pour prendre en compte la disponibilité générale du concepteur d’e-mails et l&#39;obsolescence de l&#39;éditeur de contenu d&#39;email. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

Mise à jour de la documentation [In-App](../../channels/using/about-in-app-messaging.md) et [Notification push](../../channels/using/about-push-notifications.md).

Ajout d&#39;informations supplémentaires sur les différents types d&#39;audiences dans Adobe Campaign. [En savoir plus](../../audiences/using/about-audiences.md)

Mise à jour du chapitre Utilisateurs et sécurité pour prendre en compte l&#39;obsolescence des entités géographiques. [En savoir plus](../../administration/using/organizational-units.md)

Ajout d&#39;informations sur la nouvelle option de l&#39;activité de chargement de données permettant d&#39;appliquer une étape de post-traitement au fichier contenant les enregistrements rejetés (ex. compression au format zip). [En savoir plus](../../automating/using/load-file.md)

Ajout d&#39;informations sur le nouveau champ de l&#39;activité Mise à jour de données permettant de configurer la taille maximale des mises à jour pour les données à télécharger. [En savoir plus](../../automating/using/update-data.md)

Mise à jour de la documentation [Importer du contenu depuis une URL](../../designing/using/using-existing-content.md#importing-content-from-a-url) avec des informations relatives au concepteur d’e-mails.

Ajout de Microsoft Edge (dernière version) à la liste des navigateurs compatibles pour les ordinateurs. [En savoir plus](../../administration/using/about-configuration-guidelines.md)

Ajout d&#39;informations sur la nouvelle option de l&#39;activité Extraction de fichier qui empêche la génération d&#39;un fichier si la transition entrante est vide. [En savoir plus](../../automating/using/extract-file.md)

Déplacement vers cet [emplacement](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html) de la section Configuration d&#39;une application mobile à l&#39;aide du SDK V4.

Déplacement vers cet [emplacement](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdk.html) de la section Configuration d&#39;une application mobile à l&#39;aide des SDK Adobe Experience Platform.

Mise à jour des vidéos et déplacement vers cet [emplacement](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=fr).

Mise à jour de la section Type des utilisateurs. [En savoir plus](../../administration/using/users-management.md)

## Version 18.9 - Septembre 2018  {#release-18-9---september-2018}

**Nouvelles fonctionnalités de cette version**

Messagerie in-app (version bêta) – [En savoir plus](../../channels/using/about-in-app-messaging.md)

Intégration avec Adobe Launch pour les applications mobiles (version bêta) – [En savoir plus](../../sending/using/managing-typologies.md)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour du guide de notification Push avec les changements de l&#39;interface. [En savoir plus](../../channels/using/about-push-notifications.md)

Ajout d&#39;informations sur la suppression d&#39;une audience. [En savoir plus](../../audiences/using/creating-audiences.md#deleting-audiences)

Mise à jour de la section de rapport natif des notifications Push. [En savoir plus](../../reporting/using/push-notification-report.md)

## Version 18.7 - Juillet 2018   {#release-18-7---july-2018}

**Nouvelles fonctionnalités de cette version**

[Drapeau Haute priorité](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android) et [filtre de typologie](../../sending/using/managing-typologies.md) pour les abonnés de l&#39;application mobile.

Import de contenu automatisé à partir d&#39;une URL au moment de la préparation. [En savoir plus](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**Autres mises à jour de la documentation accompagnant cette version**

Ajout d&#39;une nouvelle technote sur les paramètres et le protocole du connecteur SMS. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/sms-connector-protocol-and-settings.html)

Mise à jour de la documentation sur l&#39;intégration d&#39;Experience Manager avec Adobe Campaign. [En savoir plus](../../reporting/using/creating-a-custom-profile-dimension.md)

Entière réorganisation du guide &quot;Conception du contenu&quot;, notamment pour présenter les deux éditeurs permettant de concevoir le contenu des emails. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

Découvrez comment rendre les contenus externes entièrement éditables avec Creative SDK en créant des fragments à partir des emails existants. [En savoir plus](../../designing/using/designing-from-scratch.md)

La liste des attributs HTML permettant une conformité totale avec Creative Designer est maintenant disponible dans cette [section](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

Ajout d&#39;informations sur la langue par défaut d&#39;un modèle multilingue. [En savoir plus](../../channels/using/multilingual-messages-template.md)

Le guide Utilisateurs &amp; sécurité a été mis à jour pour refléter le fait que l’entité géographique soit devenue obsolète pour les nouvelles instances de Campaign Standard, ainsi que pour les instances existantes sans entité géographique créée, à partir de la version 18.7 – [En savoir plus](../../rn/using/deprecated-features.md)

## Version 18.6 - Juin 2018  {#release-18-6---june-2018}

**Nouvelles fonctionnalités de cette version**

Mise à jour de la documentation sur les API avec des informations sur l&#39;API **History**. Ajout d&#39;un cas pratique permettant de récupérer la page miroir pour une diffusion envoyée à un profil. [En savoir plus](../../api/using/interacting-with-marketing-history.md)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour et réorganisation de la documentation sur l&#39;intégration Triggers - Campaign. [En savoir plus](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Ajout d&#39;un cas pratique détaillé permettant de créer une dimension de profil personnalisée. [En savoir plus](../../reporting/using/creating-a-custom-profile-dimension.md)

Réorganisation de la documentation Utilisation de Campaign et Audience Manager ou People core service. [En savoir plus](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Mise à jour de la définition du rôle Préparer les diffusions. [En savoir plus](../../administration/using/list-of-roles.md)

Ajout d&#39;un exemple dans la section d&#39;activité de requête indiquant comment cibler des profils ayant cliqué sur un lien spécifique dans une diffusion. [En savoir plus](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

Ajout d&#39;une section dans la documentation sur les API relative aux **filtres personnalisés**. [En savoir plus](../../api/using/filtering.md)

## Version 18.5 - Mai 2018  {#release-18-5---may-2018}

**Nouvelles fonctionnalités de cette version**

RGPD : intégration avec Core Service. [En savoir plus](../../start/using/privacy-management.md)

Améliorations des notifications push. retours détaillés de la diffusion.  [En savoir plus](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

Extension des logs de diffusion.  [En savoir plus](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

Rapports dynamiques avec les données de profil personnalisées.  [En savoir plus](../../channels/using/creating-a-multilingual-push-notification.md)

**Autres mises à jour de la documentation accompagnant cette version**

Ajout de la liste de mesures Campaign disponible dans Analytics. [En savoir plus](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Ajout d&#39;informations sur le sous-menu Licences dans le menu Administration. [En savoir plus](../../administration/using/licenses.md)

Ajout d&#39;informations sur la manière d&#39;utiliser les champs personnalisés dans une notification push. [En savoir plus](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

Mise à jour du guide étape par étape dédié aux bonnes pratiques de diffusion. [En savoir plus](../../sending/using/delivery-best-practices.md)

Ajout des informations sur les types de logs de tracking. [En savoir plus](../../sending/using/tracking-messages.md#tracking-logs)

La section relative à l&#39;activité Requête a été mise à jour avec des exemples de requêtes. [En savoir plus](../../automating/using/query.md#query-samples)

La section dédiée au placement sur liste bloquée a été renommée « Comprendre les processus d’opt-in et d’opt-out (inscription et désinscription) ». Celle-ci a été mise à jour avec des informations concernant la manière de gérer le processus d’opt-in à des canaux spécifiques, et de configurer des landing pages pour gérer les processus d’opt-in et d’opt-out. [En savoir plus](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Découvrez les bonnes pratiques relatives à l’utilisation de serveurs SFTP hébergés Adobe – [En savoir plus](../../administration/using/external-accounts.md#sftp-external-account)

La liste des solutions/core services Analytics pris en charge en vue de l&#39;intégration avec Triggers a été mise à jour. [En savoir plus](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

Certaines pages de la documentation consacrée à l&#39;éditeur de contenu ont été fusionnées pour offrir un aperçu plus complet des différentes actions disponibles. [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

## Version 18.3 - Mars 2018   {#release-18-3---march-2018}

**Nouvelles fonctionnalités de cette version**

Règlement général sur la protection des données de l&#39;UE (RGPD) – [En savoir plus](../../start/using/privacy.md)

Creative Designer pour les emails – [En savoir plus](../../designing/using/designing-content-in-adobe-campaign.md)

Diffusions de notifications push multilingues – [En savoir plus](../../channels/using/creating-a-multilingual-push-notification.md)

Utilisation des ressources personnalisées dans les messages transactionnels – [En savoir plus](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**Autres mises à jour de la documentation accompagnant cette version**

L&#39;API RGPD regroupe des informations qui permettent le traitement automatique des demandes RGPD. [En savoir plus](../../api/using/creating-a-privacy-request.md)

Ajout d&#39;informations sur la configuration des landing pages pour offrir aux destinataires la possibilité d&#39;être placés sur liste bloquée. [En savoir plus](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

Réorganisation de la section [Configuration des messages transactionnels](../../channels/using/configuring-transactional-event.md) et ajout d&#39;un [cas pratique détaillé](../../channels/using/transactional-messaging-use-case.md).

Ajout d&#39;une note technique permettant d&#39;apprendre comment générer un fichier CSV multilingue à utiliser pour les notifications push. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-generate-csv-multilingual-push.html)

Ajout d&#39;informations sur le modèle d&#39;import **Mettre à jour les logs de diffusion et les mises en quarantaine Courrier**. [En savoir plus](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

Mise à jour de la liste des workflows techniques. [En savoir plus](../../administration/using/technical-workflows.md)

Mise à jour de la section relative à l&#39;activité Planificateur. [En savoir plus](../../automating/using/scheduler.md)

Mise à jour de la liste des ressources d&#39;aide concernant l&#39;intégration des solutions Campaign et Adobe. [En savoir plus](../../integrating/using/get-started-campaign-integrations.md)

Mise à jour de l’aide contextuelle intégrée à Campaign Standard.

## Version 18.2 - Février 2018   {#release-18-2---february-2018}

**Nouvelles fonctionnalités de cette version**

Abonnement : abonnez ou désabonnez une liste de profils à plusieurs services – [En savoir plus](../../automating/using/subscription-services.md)

Activité d’enrichissement : enrichissez les données en fonction des transitions précédentes – [En savoir plus](../../automating/using/enrichment.md)

**Autres mises à jour de la documentation accompagnant cette version**

Modification de la plupart des URL des intégrations des solutions Adobe avec Campaign. Vérifiez vos signets. [En savoir plus](../../integrating/using/get-started-campaign-integrations.md)

Datamodel v1 est maintenant disponible avec la structure SQL pour les ressources natives - [En savoir plus](../../developing/using/datamodel-introduction.md)

Ajout d&#39;informations sur la préparation d&#39;un message dans une diffusion – [En savoir plus](../../sending/using/preparing-the-send.md)

Les notes de mise à jour ont été réorganisées sur plusieurs pages afin d&#39;obtenir une vue plus globale des différentes versions.

Mise à jour de la section **[!UICONTROL Utilisation des typologies]** pour une meilleure visibilité. [En savoir plus](../../sending/using/about-typology-rules.md)

Disponibilité d&#39;une nouvelle option permettant d&#39;optimiser les performances lors de la définition de nombreuses données additionnelles dans une **[!UICONTROL requête]**. [En savoir plus](../../automating/using/query-samples.md)

Mise à jour de l&#39;exemple d&#39;import de profil avec quelques conseils pour que les profils soient prêts à recevoir des courriers. [En savoir plus](../../automating/using/about-data-import-and-export.md)

Nouvelle activité disponible dans les workflows : l&#39;activité **[!UICONTROL Enrichissement]**. [En savoir plus](../../automating/using/enrichment.md)

Mise à jour de la section sur l&#39;activité **[!UICONTROL Services d&#39;abonnements]** afin qu&#39;elle comporte d&#39;autres cas pratiques, notamment l&#39;utilisation d&#39;un seul fichier pour mettre à jour les abonnements à plusieurs services. [En savoir plus](../../automating/using/subscription-services.md)

Ajout d&#39;un cas pratique détaillé sur la préparation d&#39;une diffusion. [En savoir plus](../../sending/using/preparing-the-send.md)

Suppression de la section comprenant la liste des autorisations. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf) (PDF).

Ajout d&#39;un cas pratique détaillé sur l&#39;utilisation des réponses automatiques des SMS. [En savoir plus](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

Ajout d&#39;informations sur l&#39;envoi d&#39;une diffusion en fonction des fuseaux horaires des utilisateurs dans un workflow récurrent. [En savoir plus](../../automating/using/recurring-push-notifications.md)

Réorganisation de la section **[!UICONTROL Personnaliser une notification push]** avec des cas pratiques détaillés. [En savoir plus](../../channels/using/customizing-a-push-notification.md)

Nouvelle section consacrée à la gestion des listes bloquées. [En savoir plus](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Mises à jour des informations sur les diffusions en échec et les mises en quarantaine. [En savoir plus](../../sending/using/monitoring-a-delivery.md)

Nouvelles sections consacrées aux [mappings de ciblage](../../administration/using/target-mappings-in-campaign.md) et aux [dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).

## Version 18.1 - Janvier 2018   {#release-18-1---january-2018}

**Nouvelles fonctionnalités de cette version**

Reporting pour la gestion de la fatigue – [En savoir plus](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

Partage des rapports – [En savoir plus](../../reporting/using/reporting-interface.md#share-tab)

Améliorations des notifications push – En savoir plus [ici](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) et [ici](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)

Diffusions optimisées avec les fuseaux horaires – [En savoir plus](../../automating/using/scheduler.md)

Déclenchement de l&#39;activité Signal via l&#39;API – [En savoir plus](../../api/using/triggering-a-signal-activity.md)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour de la section sur la création de service. [En savoir plus](../../audiences/using/creating-a-service.md)

Ajout de cas pratiques pour une meilleure compréhension des entités et des groupes de sécurité. [En savoir plus](../../administration/using/organizational-units.md)

Amélioration des définitions et des calculs des dimensions, mesures et segments dans les rapports dynamiques. [En savoir plus](../../reporting/using/list-of-components-.md)

Ajout d&#39;informations sur la récupération des SMS entrants à l&#39;aide d&#39;un workflow. [En savoir plus](../../administration/using/configuring-sms-channel.md)

Ajout d&#39;informations sur les Paramètres d&#39;historisation de l&#39;activité Transfert de fichier. [En savoir plus](../../automating/using/transfer-file.md)

Mise à jour des instructions pour configurer l’intégration avec Audience Manager ou People core service – [En savoir plus](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## Version 17.10 - Octobre 2017   {#release-17-10---october-2017}

**Nouvelles fonctionnalités de cette version**

Gestion de la fatigue – [En savoir plus](../../sending/using/fatigue-rules.md)

Création de contenu : import depuis une URL – [En savoir plus](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**Autres mises à jour de la documentation accompagnant cette version**

Mise à jour de l&#39;exemple de test A/B. [En savoir plus](../../channels/using/designing-an-a-b-test-email.md)

Nouvelle technote sur la façon de créer ou de mettre à jour les données de profil lorsqu&#39;une application mobile envoie des données de collecte PII. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/acs-updating-profile-based-on-subscription.html)

Ajout d&#39;une section sur les nouvelles fonctionnalités de suivi d&#39;export. [En savoir plus](../../administration/using/auditing-export-logs.md)

Ajout de précisions sur l&#39;export de package natif. [En savoir plus](../../automating/using/managing-packages.md)

Mise à jour de la définition et des exemples de compte externe. [En savoir plus](../../administration/using/external-accounts.md)

Mise à jour de nombreuses captures d&#39;écran pour refléter les modifications apportées aux catégories du requêteur.

Déplacement et réorganisation de la section [Alertes de diffusion](../../sending/using/receiving-alerts-when-failures-happen.md).

Clarification de la section &#39;Ressources personnalisées&#39; avec une procédure plus détaillée pour [définir des filtres](../../developing/using/configuring-filter-definition.md).

Mise à jour et clarification de la [technote](https://helpx.adobe.com/fr/campaign/kb/integrate-mobile-sdk.html) sur l’intégration du SDK Mobile Adobe Experience Cloud avec une application mobile pour recevoir des notifications push Adobe Campaign Standard.

Ajout d&#39;une technote expliquant la structure de la payload reçue dans une application mobile. [En savoir plus](../../administration/using/push-payload.md)

Mise à jour de la [section](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html) sur la configuration du canal des notifications push avec de nouvelles données de payload à ajouter en fonction du système d&#39;exploitation lors de la définition des postbacks dans l&#39;interface Adobe Mobile Services.

Mise à jour de la documentation sur les SMS avec l&#39;ajout d&#39;une clarification à la section [Réponses automatiques des SMS](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

Nouvelle section consacrée à la gestion des workflows via l&#39;API. [En savoir plus](../../api/using/controlling-a-workflow.md)

Nouvelle section consacrée aux clés primaires et à l&#39;utilisation d&#39;un identifiant d&#39;entreprise comme clé dans l&#39;API. [En savoir plus](../../api/using/get-started-apis.md)

Ajout d&#39;informations sur le filtrage simple et multiple dans l&#39;API. [En savoir plus](../../api/using/filtering.md)

## Version 17.9 - Septembre 2017  {#release-17-9---september-2017}

**Nouvelles fonctionnalités de cette version**

Bibliothèque de modèles d&#39;e-mail – [En savoir plus](../../designing/using/using-reusable-content.md#content-templates)

Rapports dynamiques avec les données de profil – [En savoir plus](../../reporting/using/about-dynamic-reports.md)

Amélioration de l&#39;abonnement en masse – [En savoir plus](../../automating/using/subscription-services.md)

**Autres mises à jour de la documentation accompagnant cette version**

Liste détaillée de tous les composants disponibles dans les rapports dynamiques et modifications apportées aux formules. [En savoir plus](../../reporting/using/list-of-components-.md)

Liste détaillée des KPI partagés avec Adobe Analytics – [En savoir plus](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Vidéo Nouveau rapport dynamique. 

Ajout de recommandations relatives au compte S3. [En savoir plus](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

Mise à jour de la section sur les différents types d&#39;utilisateurs. [En savoir plus](../../administration/using/users-management.md)

Mise à jour de la section sur la personnalisation des images sources. [En savoir plus](../../designing/using/personalization.md#personalizing-an-image-source)

Ajout d&#39;une documentation sur le rapport des profils actifs. [En savoir plus](../../audiences/using/active-profiles.md)

La documentation sur les [alertes de diffusion](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons) a été mise à jour avec une section sur la résolution des problèmes qui donne quelques conseils sur les actions que vous pouvez entreprendre à la réception des alertes.

Disponibilité d’un nouveau guide de prise en main : il présente certaines des bonnes pratiques que vous pouvez appliquer pour la diffusion de vos communications avec Adobe Campaign, depuis la création et le ciblage jusqu’à l’envoi et le suivi – [En savoir plus](../../sending/using/delivery-best-practices.md)

Mise à jour de la documentation sur les messages de relance avec un cas pratique plus détaillé. [En savoir plus](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

Ajout d&#39;une documentation sur l&#39;identifiant ACS. [En savoir plus](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Ajout de nouvelles fonctions de hachage et de chiffrement avec des exemples. [En savoir plus](../../automating/using/list-of-functions.md)

Mise à jour de la section sur l&#39;activité de workflow Transfert de fichier. [En savoir plus](../../automating/using/transfer-file.md)

Ajout d&#39;informations sur l&#39;option Demander une confirmation avant l&#39;envoi des messages de l&#39;activité de workflow Diffusion email. [En savoir plus](../../automating/using/email-delivery.md)

## Version 17.7 - Juillet 2017   {#release-17-7---july-2017}

**Nouvelles fonctionnalités de cette version**

Diffusions multilingues (Email et SMS) – [En savoir plus](../../channels/using/creating-a-multilingual-email.md)

Notifications Adobe Campaign – [En savoir plus](../../administration/using/sending-internal-notifications.md)

Alertes sur les diffusions – [En savoir plus](../../sending/using/receiving-alerts-when-failures-happen.md)

Identifiant Declared ID chiffré dans les sources de données – [En savoir plus](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Partage des KPI de Campaign vers Analytics – [En savoir plus](../../integrating/using/about-campaign-analytics-integration.md)

Canal courrier : Retour à l&#39;expéditeur – [En savoir plus](../../channels/using/return-to-sender.md)

**Autres mises à jour de la documentation accompagnant cette version**

Les guides de prise en main et les vidéos ont été regroupés au sein d&#39;une section spécifique.

La documentation sur le rendu des emails a été mise à jour. [En savoir plus](../../sending/using/email-rendering.md)

Le tableau de calcul des indicateurs de rapports a été mis à jour. [En savoir plus](../../reporting/using/indicator-calculation.md)

La documentation sur le reporting a été mise à jour avec quatre nouvelles mesures. [En savoir plus](../../reporting/using/list-of-components-.md)

Documentation ajoutée sur la génération d&#39;ID uniques pour les profils. [En savoir plus](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Le mécanisme de double opt-in est maintenant documenté via une procédure complète. [En savoir plus](../../channels/using/setting-up-a-double-opt-in-process.md)

La section présentant la liste des rôles a été mise à jour. [En savoir plus](../../administration/using/list-of-roles.md)

## Version 17.5 - Mai 2017   {#release-17-5---may-2017}

**Nouvelles fonctionnalités de cette version**

Courrier – [En savoir plus](../../channels/using/about-direct-mail.md)

E-mail Cci – [En savoir plus](../../sending/using/archiving.md)

**Autres mises à jour de la documentation accompagnant cette version**

Le guide &quot;Deliveries&quot; (Diffusions) a été réorganisé et renommé &quot;Channels&quot; (Canaux). [En savoir plus](../../channels/using/get-started-communication-channels.md)

Plusieurs captures d&#39;écran ont été mises à jour afin de refléter les modifications de l&#39;interface.

Une nouvelle technote est disponible : &quot;Intégration du SDK Adobe Mobile à votre application mobile&quot;. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/integrate-mobile-sdk.html)

Les instructions relatives à la configuration du service People core service ou à l&#39;intégration d&#39;Audience Manager à Adobe Campaign ont été ajoutées. [En savoir plus](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

Tableau des autorisations corrigé afin de clarifier la fonction de certains rôles. [En savoir plus](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

Mise à jour des liens d&#39;aide contextuelle disponibles directement dans Adobe Campaign.

## Version 17.4 - Avril 2017   {#release-17-4---april-2017}

**Nouvelles fonctionnalités de cette version**

Amélioration des fonctionnalités d&#39;édition d&#39;image avec le SDK Creative – [En savoir plus](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

Notifications push transactionnelles – [En savoir plus](../../channels/using/transactional-push-notifications.md)

Notifications push récurrentes – [En savoir plus](../../automating/using/push-notification-delivery.md)

Connecteur Amazon Simple Storage Service (S3) – [En savoir plus](../../administration/using/external-accounts.md)

Intégration de Dreamweaver disponible – [En savoir plus](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=fr)

**Autres mises à jour de la documentation accompagnant cette version**

Section ajoutée sur les différents types d’utilisateurs Adobe Campaign. [En savoir plus](../../administration/using/users-management.md)

Le guide des workflows a été réorganisé et étoffé. Trouvez facilement comment [créer](../../automating/using/building-a-workflow.md) et [exécuter](../../automating/using/about-workflow-execution.md) un workflow, comment [cibler](../../automating/using/about-targeting-activities.md) et [gérer](../../automating/using/about-targeting-activities.md#enriching-data) vos données, comment [importer et exporter](../../automating/using/about-data-import-and-export.md) des données et comment utiliser les données de workflow afin de mettre à jour la base de données ou d&#39;envoyer des diffusions.

Le calcul d&#39;indicateur de rapport est à présent disponible pour les rapports dynamiques. Il comprend une description détaillée et une formule de calcul. [En savoir plus](../../reporting/using/indicator-calculation.md)

Nouvelle section dédiée à la configuration d’Abobe Mobile Services pour permettre l’utilisation des notifications push et des données de point ciblés dans Adobe Campaign. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html)

Mise à jour des sections sur la configuration et l&#39;implémentation des applications mobiles, avec des procédures plus détaillées pour configurer et envoyer des notifications push. [En savoir plus](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html)

Mise à jour de la section concernant l&#39;utilisation d&#39;images dans Campaign. [En savoir plus](../../designing/using/images.md#setting-up-image-properties)

Mise à jour de la partie intégration avec Adobe Analytics pour Mobile (point ciblé), y compris les étapes de configuration et le cas pratique. [En savoir plus](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## Version 17.2 - Mars 2017   {#release-17-2---march-2017}

**Nouvelles fonctionnalités de cette version**

Rapports dynamiques – [En savoir plus](../../reporting/using/about-dynamic-reports.md)

Intégration avec Dreamweaver (Labs) – [En savoir plus](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=fr)

Optimisation manuelle de l&#39;heure d&#39;envoi – [En savoir plus](../../sending/using/optimizing-the-sending-time.md)

Notifications push : améliorations – [En savoir plus](../../channels/using/about-push-notifications.md)

Workflows : nouvelle activité Signal – [En savoir plus](../../automating/using/external-signal.md)

Workflows : nouvelle activité Lecture d&#39;audience – [En savoir plus](../../automating/using/read-audience.md)

Données de points ciblés – [En savoir plus](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

Ressources liées dans les API REST – [En savoir plus](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**Autres mises à jour de la documentation accompagnant cette version**

Intégration de Triggers : ajout de deux cas pratiques. [En savoir plus](../../integrating/using/abandonment-triggers-use-cases.md)

Nous avons repensé la documentation sur l&#39;API destinée aux développeurs avec de nouvelles informations et de nouveaux fragments de code pour une meilleure expérience utilisateur. [En savoir plus](../../api/using/get-started-apis.md)

Découvrez des exemples des nouvelles activités de workflow [Lecture d&#39;audience](../../automating/using/read-audience.md) et [Signal externe](../../automating/using/external-signal.md).

## Version 17.1 - Janvier 2017  {#release-17-1---january-2017}

**Nouvelles fonctionnalités de cette version**

Export des logs pour un reporting externe – [En savoir plus](../../automating/using/exporting-logs.md)

API des messages transactionnels – [En savoir plus](../../api/using/get-started-apis.md)

Capacités marketing des messages transactionnels - [En savoir plus](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**Autres mises à jour de la documentation accompagnant cette version**

Activité de workflow Requête incrémentale : nouveau mode incrémental – [En savoir plus](../../automating/using/incremental-query.md)

Mise à jour de l&#39;activité de workflow Planificateur – [En savoir plus](../../automating/using/scheduler.md)

Changement d&#39;URL : Assets core service – [En savoir plus](../../integrating/using/working-with-campaign-and-assets-core-service.md)

Changement d&#39;URL : People core service – [En savoir plus](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Réorganisation du guide Profils et audiences. [En savoir plus](../../audiences/using/get-started-profiles-and-audiences.md)
