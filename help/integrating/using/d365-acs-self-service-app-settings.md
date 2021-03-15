---
title: Configuration de l'application d'intégration Campaign-Dynamics
description: Découvrez comment configurer l'application d'intégration Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Intégration de Microsoft CRM
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 99%

---


# Connecter les systèmes à l&#39;application d&#39;intégration

## Ajouter des informations d&#39;identification à l&#39;application d&#39;intégration

L&#39;écran **[!UICONTROL Paramètres]** permet de spécifier les informations d&#39;identification de Microsoft Dynamics 365 et de l&#39;API Adobe. Vous pouvez également configurer des paramètres liés à l&#39;instance SFTP Adobe Campaign

### Informations d&#39;identification de Microsoft Dynamics 365

Les informations d&#39;identification de Microsoft Dynamics 365 autorisent l&#39;application d&#39;intégration à extraire vos données de Microsoft Dynamics 365.	Vous devez d&#39;abord suivre les étapes affichées dans l&#39;écran [Configuration de Microsoft Dynamics 365 pour l&#39;intégration de Campaign](../../integrating/using/d365-acs-configure-d365.md) afin de générer les valeurs qui seront collées dans cet écran. Les entrées décrites ci-après font référence à cet écran.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Id du client]** : découvrez comment référencer l&#39;identifiant du client dans [cette section](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Secret client]** : découvrez comment générer votre secret client dans [cette section](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]** : découvrez comment trouver votre identifiant du tenant dans [cette section](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]** : l&#39;URL possède le format `https://&lt;nomserveur>.api.crm.dynamic.com/

### Informations d&#39;identification de l&#39;API Adobe

Les informations d&#39;identification d&#39;Adobe Campaign sont générées à l&#39;aide d&#39;[Adobe I/O](https://www.adobe.io/). Vous devez accéder à l&#39;écran [Configuration d&#39;Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) et suivre les instructions qu&#39;il contient avant de pouvoir renseigner les entrées de cette section.

L&#39;image ci-après montre en détail le mapping entre Adobe I/O et les entrées de l&#39;écran des paramètres.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Clé privée* : la définition de celle-ci débute en cliquant sur le bouton « Générer la paire de clés publique/privée ». Un fichier zip est alors créé. Vous devez le télécharger. Une fois le fichier téléchargé, décompressez-le. Vous obtenez alors deux fichiers appelés certificate_pub.crt et private.key. Veillez à placer le fichier private.key à un endroit sécurisé et ne le partagez pas. Ouvrez le fichier private.key dans un éditeur de texte. Copiez la totalité de la valeur dans l&#39;éditeur de texte (ctrl-A, ctrl-C sur PC ou cmd-A, cmd-C sur Mac). Les lignes &quot;BEGIN PRIVATE KEY&quot; et &quot;END PRIVATE KEY&quot; doivent être incluses dans leur intégralité. Collez l&#39;intégralité de ce texte de plusieurs lignes dans l’entrée « Clé privée » de l’écran Paramètres.

* *URL* : cette valeur suit le modèle https\://mc.adobe.io/&lt;nom-instance-campaign>. L&#39;en-tête de l&#39;application d&#39;intégration comprend l&#39;Org et l&#39;Instance. La partie &quot;nom-instance-campaign&quot; de l&#39;URL correspond simplement au nom trouvé dans cette valeur d&#39;instance.

## Paramètres SFTP Adobe Campaign {#ac-smtp-settings}

Ces paramètres sont facultatifs. Vous devez les définir si vous prévoyez d&#39;utiliser votre instance SFTP Adobe Campaign pour générer des logs depuis le connecteur. Ces logs s&#39;avéreront utiles si vous rencontrez des problèmes lors de l&#39;exécution de l&#39;intégration et que vous devez résoudre les erreurs qui font que vous n&#39;obtenez pas les résultats escomptés.

Vous pouvez aussi configurer le serveur SFTP si vous prévoyez d&#39;exécuter le workflow d&#39;opt-in/opt-out et qu&#39;il existe un flux de données **[!UICONTROL Unidirectionnel (Campaign vers Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectionnel]** entre Adobe Campaign et Microsoft Dynamics 365.

>[!IMPORTANT]
>
>Vous êtes responsable des informations auxquelles vous accédez et que vous téléchargez à partir des dossiers SFTP. Si les informations contiennent des données personnelles, vous êtes tenu de respecter les lois et règlements applicables en matière de confidentialité. [En savoir plus](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Pour définir les paramètres SFTP Campaign pour l&#39;intégration de Microsoft Dynamics 365, accédez à la section suivante :

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

Vous devez spécifier les informations suivantes :

* **Hôte SFTP** : ce champ contient &lt;nom-instance-campaign>.campaign.adobe.com. L&#39;en-tête de l&#39;application d&#39;intégration comprend l&#39;**Org** et l’**Instance**. La partie &quot;nom-instance-campaign&quot; de l&#39;URL correspond simplement au nom trouvé dans cette valeur d&#39;instance.

* **Utilisateur SFTP** : si vous disposez d&#39;une clé SSH, ajoutez-la ici. Sinon, consultez [cette section](#ac-control-panel-settings). Dans le cadre du processus, le nom d&#39;utilisateur s&#39;affiche.

* **Clé SFTP** : si vous disposez d’une clé SSH, ajoutez-la ici. Sinon, consultez [cette section](#ac-control-panel-settings).

* Les **plages IP** doivent être incluses dans votre configuration SFTP Adobe Campaign. Vous devrez les placer dans la liste autorisée pour que l&#39;intégration puisse utiliser le point d&#39;entrée SFTP.	

* L&#39;option **Voulez-vous exporter les logs vers votre serveur SFTP Adobe Campaign ?** vous permet de déterminer si l&#39;intégration génère des informations de journalisation au point d&#39;entrée SFTP. Ces informations peuvent servir au débogage si Adobe Campaign ou Microsoft Dynamics 365 n&#39;affiche pas les informations attendues.

## Configuration de SFTP dans Adobe Campaign {#ac-control-panel-settings}

Découvrez la gestion SFTP avec le [Panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr) dans les sections suivantes :

* [À propos de la gestion SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=fr#sftp-management)

* [Gestion de l’espace de stockage SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=fr#installing-ssh-key)

* [Ajout de plages d&#39;adresses IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=fr#sftp-management)

* [Gestion des clés](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=fr#sftp-management)

* [Connexion à votre serveur SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=fr#sftp-management)

Une fois la configuration terminée, connectez-vous au serveur SFTP avec la clé privée et créez le répertoire &quot;d365_loads/export&quot;.

[Consultez cette page](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=fr#sftp-management) pour plus d&#39;informations sur le serveur SFTP Adobe Campaign Standard.
