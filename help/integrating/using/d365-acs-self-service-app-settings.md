---
title: Configuration de l’application d’intégration Campaign-Dynamics
description: Découvrez comment configurer l'application d'intégration Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 3%

---


# Connexion des systèmes à l’application d’intégration

## Ajouter les informations d’identification à l’application d’intégration

L&#39;écran **[!UICONTROL Paramètres]** vous permet de spécifier les informations d&#39;identification de Microsoft Dynamics 365 et de l&#39;API d&#39;Adobe. Vous pouvez également configurer les paramètres liés à l’instance SFTP Adobe Campaign.

### Informations d&#39;identification Microsoft Dynamics 365

Les informations d&#39;identification Microsoft Dynamics 365 permettent à l&#39;application d&#39;intégration d&#39;extraire vos données de Microsoft Dynamics 365.  Vous devez d&#39;abord suivre les étapes de l&#39;écran [Configurer l&#39;intégration Microsoft Dynamics 365 pour Campaign](../../integrating/using/d365-acs-configure-d365.md) afin de générer les valeurs qui seront collées dans cet écran. Les entrées décrites ci-dessous font référence à cet écran.

![](assets/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL ID]** client : Découvrez comment référencer votre ID de client dans  [cette section](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Secret]** client : Découvrez comment générer votre clé secrète client dans  [cette section](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]** : Découvrez comment trouver votre identifiant locataire dans  [cette section](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]** : L&#39;URL aura le format `https://&lt;servername>.api.crm.dynamic.com/

### Informations d’identification de l’API Adobe

Les informations d’identification Adobe Campaign sont générées à l’aide de [Adobe I/O](https://www.adobe.io/). Vous devrez visiter l&#39;écran [Configurer Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) et suivre les instructions qui s&#39;y trouvent avant de pouvoir remplir les entrées de cette section.

L&#39;image suivante explique en détail le mappage entre Adobe I/O et les entrées d&#39;écran des paramètres.

![](assets/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Clé* privée : le processus de définition de ces débuts en cliquant sur le bouton &quot;Générer la paire de clés publique/privée&quot;. Vous allez créer un fichier zip que vous devez télécharger. Une fois téléchargé, décompressez le fichier, ce qui génère deux fichiers nommés certificate_pub.crt et private.key. Veillez à placer private.key dans un emplacement sécurisé et ne le partagez pas. Ouvrez le fichier private.key dans un éditeur de texte. Copiez la totalité de la valeur dans l’éditeur de texte (ctrl-A, ctrl-C sur un PC, ou cmd-A, cmd-C sur un Mac). Cela devrait inclure les lignes &quot;BEGIN PRIVATE KEY&quot; et &quot;END PRIVATE KEY&quot; dans leur intégralité. Collez tout ce texte multiligne dans la saisie &quot;Clé privée&quot; de l’écran Paramètres.

* *URL* : Cette valeur correspond au modèle https\://mc.adobe.io/&lt;campaign-instance-name>. L’en-tête de l’application d’intégration comprend à la fois &quot;Org&quot; et &quot;Instance&quot;. La partie &quot;campaign-instance-name&quot; de l’URL correspond simplement au nom trouvé dans cette valeur d’instance.

## Paramètres SFTP Adobe Campaign {#ac-smtp-settings}

Ces paramètres sont facultatifs. Vous devez les définir si vous prévoyez d’utiliser votre instance Adobe Campaign SFTP pour générer des journaux à partir du connecteur. Cela s’avérera utile si vous rencontrez des problèmes lors de l’exécution de l’intégration et que vous devez déboguer les raisons pour lesquelles la sortie ne répond pas à vos attentes.

L&#39;autre raison de configurer le serveur SFTP est que vous prévoyez d&#39;exécuter le processus d&#39;inclusion/exclusion et qu&#39;il y a un flux de données entre Adobe Campaign et Microsoft Dynamics 365, soit **[!UICONTROL Unidirectionnel (Campaign à Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectionnel]**.

>[!IMPORTANT]
>
>Vous êtes responsable des informations que vous accédez et téléchargez à partir des dossiers SFTP. Si les renseignements contiennent des données personnelles, vous êtes responsable de respecter les lois et règlements en vigueur sur la protection des renseignements personnels. [En savoir plus](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Pour définir les paramètres SFTP Campaign pour l&#39;intégration Microsoft Dynamics 365, accédez à la section suivante :

![](assets/d365-to-acs-ui-page-workflows-settings-sftp.png)

Vous devez spécifier :

* **Hôte** SFTP : ce champ contient  &lt;campaign-instance-name>.campaign.adobe.com. L’en-tête de l’application d’intégration comprend à la fois l’**organisation** et l’**instance**. La partie &quot;campaign-instance-name&quot; de l’URL correspond simplement au nom trouvé dans cette valeur d’instance.

* **Utilisateur** SFTP : Si vous disposez de l’utilisateur SFTP, ajoutez-le ici. Sinon, reportez-vous à [cette section](#ac-control-panel-settings). Dans le cadre du processus, le nom d&#39;utilisateur s&#39;affiche.

* **Clé** SFTP : Si vous avez une clé SSH, ajoutez-la ici. Sinon, reportez-vous à [cette section](#ac-control-panel-settings).

* Les **plages IP** doivent être incluses dans votre configuration SFTP Adobe Campaign. Il faudra les placer sur la liste autorisée pour que l’intégration utilise le point de terminaison SFTP.

* Le **Voulez-vous exporter les journaux vers votre SFTP Adobe Campaign ?** vous permet de déterminer si l’intégration génère des informations de journalisation vers le point de terminaison SFTP. Vous pouvez l&#39;utiliser pour faciliter le débogage si Adobe Campaign ou Microsoft Dynamics 365 n&#39;affiche pas les informations attendues.

## Configuration SFTP en Adobe Campaign {#ac-control-panel-settings}

Découvrez la gestion SFTP avec [Panneau de Contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr) dans les sections suivantes :

* [À propos de la gestion SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [Gestion de l’espace de stockage SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Ajouter des plages d’adresses IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Gérer les clés](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Connexion à votre serveur SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Une fois la configuration terminée, connectez-vous au serveur SFTP avec la clé privée et créez le répertoire &quot;d365_loads/export&quot;.

[Consultez cette ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=fr#sftp-management) page pour plus d’informations sur le serveur Adobe Campaign Standard SFTP.
