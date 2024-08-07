---
title: Configuration du canal SMS
description: Apprenez les étapes de configuration des SMS, notamment le routage, le codage, les formats et les propriétés avancées.
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5ff1d636-eac7-4909-be16-4f4b439b19ff
source-git-commit: b023e07c337e3352b8d1e26254ce342e0d560a27
workflow-type: tm+mt
source-wordcount: '1706'
ht-degree: 100%

---

# Configuration du canal SMS{#configuring-sms-channel}

Pour envoyer des SMS, un ou plusieurs comptes externes doivent être configurés par un administrateur depuis le menu **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL SMS]** > **[!UICONTROL Comptes SMS]**.

Les étapes de création et de modification d&#39;un compte externe sont présentées dans la section [Comptes externes. ](../../administration/using/external-accounts.md) Vous trouverez ci-dessous les paramètres spécifiques aux comptes externes pour l&#39;envoi des SMS.

## Définition d&#39;un routage des SMS  {#defining-an-sms-routing}

>[!IMPORTANT]
>
>L’utilisation du même compte et du même mot de passe pour plusieurs comptes SMS externes peut entraîner des conflits et des chevauchements entre les comptes. Reportez-vous à la [page de résolution des problèmes de SMS](troubleshooting-sms.md#external-account-conflict).

Le compte externe **[!UICONTROL Routage des SMS par SMPP]** est fourni par défaut, mais il peut être utile d&#39;ajouter d&#39;autres comptes.

Si vous souhaitez utiliser le protocole SMPP, vous pouvez également créer un compte externe. Pour plus d&#39;informations sur le protocole et les paramètres SMS, consultez cette [note technique](../../administration/using/sms-protocol.md).

1. Créez un compte externe depuis **[!UICONTROL Administration > Paramétrage de l&#39;application > Comptes externes]**.
1. Définissez le type de compte sur **[!UICONTROL Routage]**, le canal sur **[!UICONTROL Mobile (SMS)]** et le mode de diffusion sur **[!UICONTROL Envoi en masse]**.

   ![](assets/sms_routing.png)

1. Définissez les paramètres de connexion.

   Pour renseigner les paramètres de connexion spécifiques à l&#39;envoi de SMS, adressez-vous à votre fournisseur de service SMS qui vous indiquera comment remplir les différents champs du compte externe.

   ![](assets/sms_connection.png)

   L&#39;option **[!UICONTROL Activer TLS par SMPP]** permet de chiffrer le trafic SMPP.

   **[!UICONTROL Activer les traces SMPP en mode verbeux dans le fichier de log]** permet de vider tout le trafic SMPP des fichiers journaux. Cette option doit être activée pour dépanner le connecteur et pour comparer le trafic affiché chez le fournisseur.

1. Contactez Adobe qui vous donnera la valeur à saisir dans le champ **[!UICONTROL Nom de l&#39;implémentation du SMSC]**, en fonction du fournisseur que vous aurez choisi.
1. Définissez les paramètres du canal SMPP. Pour plus d&#39;informations, consultez la section [Encodage et formats des SMS](#sms-encoding-and-formats).

   Activez l&#39;option **[!UICONTROL Stocker les MO entrants dans la base de données]** si vous souhaitez que tous les SMS entrants soient stockés dans la table SMS entrants. Pour plus d&#39;informations sur la façon de récupérer vos SMS entrants, reportez-vous à cette [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   L’option **[!UICONTROL Activer les mises à jour KPI en temps réel pendant le traitement du SR (rapport d’état)]** permet de mettre à jour les KPI **[!UICONTROL Délivrés]** et **[!UICONTROL Rebonds + erreurs]** en temps réel après l’envoi de votre diffusion. Ces KPI sont disponibles dans la fenêtre **[!UICONTROL Déploiement]** et sont directement recalculés en fonction du SR reçu du fournisseur.

   ![](assets/sms_connection_1.png)

1. Définissez les paramètres de **[!UICONTROL Débit et délais]**.

   Vous pouvez indiquer le débit maximum des messages sortants (&quot;MT&quot;, Mobile Terminated) en MT par seconde. Si vous indiquez « 0 » dans le champ correspondant, le débit ne sera pas limité.

   Les valeurs de tous les champs correspondant à des délais sont à renseigner en secondes.

1. Spécifiez les paramètres propres au SMSC si vous devez définir un mapping spécifique des chiffrements. Voir à ce sujet la section [Spécificités du SMSC](#smsc-specifics).

   Activez l&#39;option **[!UICONTROL Envoyer le numéro de téléphone complet (utiliser des caractères autres que des chiffres)]** si vous ne souhaitez pas respecter le protocole SMPP et transférer le préfixe **[!UICONTROL +]** sur le serveur du fournisseur SMS (SMS-C).

   Cependant, étant donné que certains fournisseurs requièrent l&#39;utilisation du préfixe **[!UICONTROL +]**, consultez votre propre fournisseur qui vous invitera à activer cette option si nécessaire.

1. Si besoin, définissez des réponses automatiques pour déclencher des actions selon le contenu de celles-ci. Voir à ce propos [cette section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Enregistrez la configuration du compte externe de routage des SMS.

Vous pouvez utiliser à présent votre nouveau routage pour envoyer des SMS avec Adobe Campaign.

## Encodage et formats des SMS  {#sms-encoding-and-formats}

### Encodage, longueur et translittération des SMS {#sms-encoding--length-and-transliteration}

Par défaut, le nombre de caractère d&#39;un SMS respecte la norme de téléphonie mobile GSM (Global System for Mobile Communications).

Les SMS utilisant l&#39;encodage GSM sont limités à 160 caractères, ou 153 caractères par SMS pour les messages envoyés en plusieurs parties.

>[!NOTE]
>
>Certains caractères comptent pour deux (accolades, crochets, symbole de l&#39;euro, etc.). La liste des caractères GSM disponibles est présentée dans la section [Table des caractères - Norme GSM](#table-of-characters---gsm-standard).

Vous pouvez si vous le souhaitez autoriser la translittération des caractères en cochant la case correspondante.

![](assets/sms_transliteration.png)

La translittération consiste à remplacer un caractère d&#39;un SMS par un autre lorsque ce caractère n&#39;est pas pris en charge par la norme GSM.

* Lorsque la translittération est **autorisée**, chaque caractère non pris en charge est remplacé par un caractère GSM lors de l&#39;envoi du message. Par exemple, la lettre &quot;ë&quot; est remplacée par &quot;e&quot;. Le message est alors légèrement altéré, mais la limite du nombre de caractères demeure identique.
* Lorsque la translittération **n&#39;est pas autorisée**, chaque message contenant des caractères non pris en charge est envoyé au format binaire (Unicode) : tous les caractères sont transmis tels quels. Or les SMS utilisant l&#39;encodage Unicode sont limités à 70 caractères (ou 67 caractères par SMS pour les messages envoyés en plusieurs parties). Si le nombre de caractères maximal est dépassé, plusieurs messages sont alors envoyés, ce qui peut générer des coûts supplémentaires.

>[!IMPORTANT]
>
>L&#39;insertion de champs de personnalisation dans le contenu du SMS peut introduire des caractères non pris en charge par l&#39;encodage GSM. Un exemple de contenu est proposé dans la section [Personnaliser un SMS](../../channels/using/personalizing-sms-messages.md).

Par défaut, la translittération des caractères est désactivée. Si vous souhaitez que tous les caractères de vos SMS soient conservés, pour ne pas altérer les noms propres par exemple, il est recommandé de ne pas activer cette option.

En revanche, si vos SMS contiennent beaucoup de caractères générant des messages Unicode, vous pouvez choisir d&#39;activer cette option afin de limiter le coût de vos envois.

### Tables des caractères - Norme GSM  {#table-of-characters---gsm-standard}

Cette section présente les caractères pris en charge par la norme GSM. Tout caractère inséré dans le corps du message autre que ceux mentionnés ci-dessous convertit le message complet en binaire (Unicode) et le limite donc à 70 caractères. Pour en savoir plus, consultez la section [Encodage, longueur et translittération des SMS](#sms-encoding--length-and-transliteration).

**Caractères simples**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> p<br /> </td> 
   <td> ¿<br /> </td> 
   <td> p<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> h<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> k<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> l<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> n<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> o<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP : espace (Space)

ESC : caractère d&#39;échappement (Escape)

LF : saut de ligne (Line Feed)

CR : retour chariot (Carriage Return)

**Caractères doubles**

^ { } [~] | €

### Spécificités des SMSC {#smsc-specifics}

>[!NOTE]
>
>Ces options permettent d&#39;adapter le connecteur à une utilisation avec un SMSC non standard (par exemple qui ne suit pas exactement les spécificités du protocole SMPP 3.4) ou avec des exigences d&#39;encodage spécifiques ; seuls les utilisateurs experts peuvent les configurer.

Lors de l&#39;envoi d&#39;un SMS, Adobe Campaign peut utiliser un ou plusieurs encodages de texte. Chaque encodage possède un jeu de caractères disponibles qui lui est propre, et le nombre de caractères qu&#39;il est possible de mettre dans un SMS dépend de l&#39;encodage.

Le champ **[!UICONTROL Data_coding]** permet à Adobe Campaign de signaler au SMSC l&#39;encodage utilisé.

>[!NOTE]
>
>Le mappage entre la valeur du **data_coding** et l’encodage réellement utilisé est standardisé. Cependant, certains SMSC possèdent une correspondance qui leur est propre : dans ce cas, votre administrateur **Adobe Campaign** doit déclarer cette correspondance. Consultez votre fournisseur pour en savoir plus.

La fonctionnalité **[!UICONTROL Définir un mapping spécifique des encodages]** vous permet de déclarer des **data_coding** et de forcer l&#39;encodage si besoin : pour ce faire, spécifiez un seul encodage dans le tableau.

**Configuration**

* Lorsque la fonctionnalité **[!UICONTROL Définir un mapping spécifique des encodages]** n&#39;est pas cochée, le connecteur a un comportement générique :

   * Il tente d&#39;utiliser l&#39;encodage GSM et lui affecte la valeur **data_coding = 0**.
   * Si l&#39;encodage GSM échoue, il utilise l&#39;encodage **UCS2** et lui affecte la valeur **data_coding = 8**.

  ![](assets/sms_data_coding.png)

* Lorsque la fonctionnalité **[!UICONTROL Définir un mapping spécifique des encodages]** est cochée, vous pouvez définir les encodages que vous souhaitez utiliser ainsi que les valeurs du champ **[!UICONTROL data_coding]** associées. Adobe Campaign tentera d&#39;utiliser le premier encodage de la liste, puis le suivant, si l&#39;encodage se révèle impossible.

  L&#39;ordre de déclaration est important : il est recommandé d&#39;ordonner la liste par ordre croissant **de coût**, afin de favoriser les encodages permettant de mettre le plus de caractères possible dans chaque SMS.

  Ne déclarez que les encodages que vous souhaitez utiliser. Si certains encodages fournis par le SMS-C ne correspondent pas à votre utilisation, ne les déclarez pas dans la liste.

  ![](assets/sms_data_coding1.png)

### Réponse automatique aux MO  {#automatic-reply-sent-to-the-mo}

Lorsqu’un profil répond à un SMS envoyé via Campaign, vous pouvez configurer les messages qui lui sont automatiquement renvoyés, ainsi que l’action à effectuer.

Pour plus d’informations, consultez [cette section](../../channels/using/managing-incoming-sms.md).

## Configuration des propriétés des SMS  {#configuring-sms-properties}

Cette section décrit la liste des paramètres propres aux SMS dans l&#39;écran des propriétés d&#39;une diffusion de type SMS ou d&#39;un modèle de SMS.

Les paramètres spécifiques à l&#39;envoi des SMS sont regroupés dans les sections **[!UICONTROL Envoi]** et **[!UICONTROL Paramètres avancés]**.

![](assets/sms_options.png)

Dans la section **[!UICONTROL Paramètres avancés]** :

* Le **[!UICONTROL Numéro court]** permet d&#39;ajouter un numéro court spécifique à votre diffusion. Les destinataires qui se sont désinscrits de ce numéro court spécifique seront automatiquement exclus pendant la préparation du message. Pour plus d&#39;informations sur la façon de configurer le numéro court, consultez [cette section](../../channels/using/managing-incoming-sms.md).

  >[!NOTE]
  >
  >Si le champ **[!UICONTROL Numéro court]** est laissé vide, la valeur du champ **[!UICONTROL Numéro court]** défini dans le compte externe sera utilisée.

Dans la section **[!UICONTROL Envoyer]** d&#39;un modèle SMS :

* L&#39;option **[!UICONTROL Nombre maximal de SMS par message]** vous permet de définir le nombre de SMS à utiliser pour envoyer un message. Si ce nombre est dépassé, le message ne sera pas envoyé.

  >[!IMPORTANT]
  >
  >Si vous avez inséré des champs de personnalisation ou du texte conditionnel dans le contenu de votre SMS, la longueur du message et donc le nombre de SMS peuvent varier d&#39;un destinataire à l&#39;autre. Pour en savoir plus, consultez la section [Personnaliser un SMS](../../channels/using/personalizing-sms-messages.md).

  ![](assets/sms_smpp_3.png)

* Le champ **[!UICONTROL Mode de transmission]** permet de déterminer la méthode de diffusion des messages par SMS :

   * **[!UICONTROL Enregistré sur le mobile]** : le message est stocké sur la carte SIM du téléphone du destinataire.
   * **[!UICONTROL Enregistré sur le terminal]** : le message est stocké dans la mémoire interne du téléphone.
   * **[!UICONTROL Flash]** : le message s&#39;affiche sur l&#39;écran du téléphone mobile du destinataire sous forme de notification, puis disparaît sans être enregistré.
