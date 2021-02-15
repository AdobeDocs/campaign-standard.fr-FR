---
title: Configuration de l’application d’intégration Campaign-Dynamics
description: Découvrez comment configurer l'application d'intégration Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: ht
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: ht
source-wordcount: '808'
ht-degree: 100%

---


# Connexion des systèmes à l’application d’intégration

## Ajouter les informations d’identification à l’application d’intégration

L&#39;écran **[!UICONTROL Paramètres]** vous permet de spécifier les informations d&#39;identification de Microsoft Dynamics 365 et de l&#39;API Adobe. Vous pouvez également configurer les paramètres liés à l’instance SFTP Adobe Campaign

### Informations d&#39;identification Microsoft Dynamics 365

Les informations d&#39;identification Microsoft Dynamics 365 autorise l&#39;application d&#39;intégration à extraire vos données de Microsoft Dynamics 365. Vous devez d&#39;abord suivre les étapes affichées dans l&#39;écran [Configuration de Microsoft Dynamics 365 pour l’intégration de Campaign](../../integrating/using/d365-acs-configure-d365.md) afin de générer les valeurs qui seront collées dans cet écran. Les entrées décrites ci-dessous font référence à cet écran.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Id du client]** : découvrez comment référencer votre identifiant du client dans [cette section](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Secret client]** : découvrez comment générer votre secret client dans [cette section](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]** : découvrez comment trouver votre identifiant du tenant dans [cette section](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]** : l&#39;URL possède le format `https://&lt;nomserveur>.api.crm.dynamic.com/

### Informations d’identification API Adobe

Les informations d’identification Adobe Campaign sont générées à l’aide d’[Adobe I/O](https://www.adobe.io/). Vous devez accéder à l&#39;écran [Configurer Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) et suivre les instructions qui s&#39;y trouvent avant de pouvoir renseigner les entrées de cette section.

L&#39;image ci-dessous explique en détail le mapping entre Adobe I/O et les entrées de l&#39;écran des paramètres.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Clé privée* : le processus de définition de celle-ci débute en cliquant sur le bouton « Générer la paire de clés publique/privée ». Un fichier zip est alors créé. Vous devez le télécharger. Une fois téléchargé, décompressez le fichier, ce qui génère deux fichiers appelés certificate_pub.crt et private.key. Veillez à placer le fichier private.key à un endroit sécurisé et ne le partagez pas. Ouvrez le fichier private.key dans un éditeur de texte. Copiez la totalité de la valeur dans l’éditeur de texte (ctrl-A, ctrl-C sur PC, ou cmd-A, cmd-C sur Mac). Les lignes &quot;BEGIN PRIVATE KEY&quot; et &quot;END PRIVATE KEY&quot; doivent être incluses dans leur intégralité. Collez l’intégralité de ce texte multiligne dans l’entrée « Clé privée » de l’écran Paramètres.

* *URL* : cette valeur correspond au modèle https\://mc.adobe.io/&lt;nom-instance-campaign>. L’en-tête de l’application d’intégration comprend à la fois &quot;Org&quot; et &quot;Instance&quot;. La partie &quot;nom-instance-campaign&quot; de l’URL correspond simplement au nom trouvé dans cette valeur d’instance.

## Paramètres SFTP Adobe Campaign {#ac-smtp-settings}

Ces paramètres sont facultatifs. Vous devez les définir si vous prévoyez d’utiliser votre instance SFTP Adobe Campaign pour générer des logs à partir du connecteur. Cela s’avérera utile si vous rencontrez des problèmes lors de l’exécution de l’intégration et que vous devez résoudre les erreurs qui font que la sortie ne répond pas à vos attentes.

Vous pouvez aussi configurer le serveur SFTP si vous prévoyez d&#39;exécuter le workflow d&#39;opt-in/d’opt-out et qu&#39;il existe un flux de données entre Adobe Campaign et Microsoft Dynamics 365, soit **[!UICONTROL Unidirectionnel (Campaign vers Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectionnel]**.

>[!IMPORTANT]
>
>Vous êtes responsable des informations auxquelles vous accédez et téléchargez à partir des dossiers SFTP. Si les renseignements contiennent des données personnelles, vous êtes responsable de respecter les lois et règlements applicables en matière de protection de la vie privée. [En savoir plus](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Pour définir les paramètres SFTP Campaign pour l&#39;intégration de Microsoft Dynamics 365, accédez à la section suivante :

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

Vous devez spécifier les informations suivantes :

* **Hôte SFTP** : ce champ contient &lt;nom-instance-campaign>.campaign.adobe.com. L’en-tête de l’application d’intégration comprend à la fois l’**organisation** et l’**instance**. La partie &quot;nom-instance-campaign&quot; de l’URL correspond simplement au nom trouvé dans cette valeur d’instance.

* **Utilisateur SFTP** : si vous disposez de l’utilisateur SFTP, ajoutez-le ici. Sinon, consultez [cette section](#ac-control-panel-settings). Dans le cadre du processus, le nom d&#39;utilisateur s&#39;affiche.

* **Clé SFTP** : si vous disposez d’une clé SSH, ajoutez-la ici. Sinon, consultez [cette section](#ac-control-panel-settings).

* Les **plages IP** doivent être incluses dans votre configuration SFTP Adobe Campaign. Vous devrez les placer sur la liste autorisée pour que l’intégration utilise le point d&#39;entrée SFTP.

* L&#39;option **Voulez-vous exporter les logs vers votre SFTP Adobe Campaign ?** vous permet de déterminer si l’intégration génère des informations de connexion vers le point d&#39;entrée SFTP. Vous pouvez l&#39;utiliser pour faciliter le débogage si Adobe Campaign ou Microsoft Dynamics 365 n&#39;affiche pas les informations attendues.

## Configuration SFTP dans Adobe Campaign {#ac-control-panel-settings}

Découvrez la gestion SFTP avec le [Panneau de contrôle Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=fr) dans les sections suivantes :

* [À propos de la gestion SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=fr#sftp-management)

* [Gestion de l’espace de stockage SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=fr#installing-ssh-key)

* [Ajout de plages d’adresses IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=fr#sftp-management)

* [Gestion des clés](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=fr#sftp-management)

* [Connexion à votre serveur SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=fr#sftp-management)

Une fois la configuration terminée, connectez-vous au serveur SFTP avec la clé privée et créez le répertoire &quot;d365_loads/export&quot;.

[Consultez cette page](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=fr#sftp-management) pour plus d’informations sur le serveur SFTP Adobe Campaign Standard.
