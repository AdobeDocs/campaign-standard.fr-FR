---
title: Test des messages électroniques à l’aide de  ciblées
description: Découvrez comment tester les messages à l’aide d’ ciblées et d’adresses de substitution.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f0df05a08cc07b7c2a5b8e175177006360e7e7d

---


# Test des messages électroniques à l’aide de  ciblées {#testing-message-profiles}

## Présentation {#overview}

De plus, pour [tester les](../../audiences/using/managing-test-profiles.md), vous pouvez tester un message électronique en vous plaçant à la position de l’un des  ciblés. Cela vous permet d&#39;obtenir une représentation exacte du message que le recevra (champs personnalisés, informations dynamiques et personnalisées, y compris des données supplémentaires de la ...).

>[!NOTE]
>
> Cette fonctionnalité est disponible avec les messages électroniques uniquement.

Les étapes principales sont les suivantes :

1. Configurez votre message, puis lancez la phase de **préparation** .
1. **Sélectionnez un ou plusieurs** parmi les de ciblés par le message.
1. Associez à chaque une adresse **de** substitution à laquelle les seront envoyés.
1. (Facultatif) Pour chaque  de, définissez un **préfixe** à ajouter à la ligne d’objet du.
1. **** dans le concepteur de courrier électronique de la manière dont le message s’affichera pour l’ du.
1. Envoyez les.

Pour plus d&#39;informations sur le processus global, reportez-vous au didacticiel vidéo disponible [ici](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html).

>[!IMPORTANT]
>
>Cette fonctionnalité vous permet d&#39;envoyer  informations personnelles aux adresses électroniques externes. Gardez à l’esprit que l’exécution des demandes de confidentialité (RDPC et ACCP) dans Campaign Standard NE L’EXÉCUTERA PAS à l’externe.

## Sélection des  de et des adresses de substitution {#selecting-profiles}

Pour utiliser des  ciblées à des fins de test, vous devez d’abord les sélectionner, puis définir les adresses de substitution qui recevront les. Pour ce faire, vous pouvez [sélectionner des](#selecting-individual-profiles) de spécifiques parmi les  de ciblées ou [importer des](#importing-from-audience)à partir d’unexistant.

>[!NOTE]
>
>Vous pouvez sélectionner un maximum de 100  pour les tests.

### Sélection d’un individuel {#selecting-individual-profiles}

1. Dans le de messages, vérifiez que la préparation du message est réussie, puis cliquez sur le **[!UICONTROL Audience]** bloc.

   ![](assets/substitution_preparation.png)

1. Dans l’ **[!UICONTROL Profile substitutions]** onglet, cliquez sur le **[!UICONTROL Create element]** bouton pour sélectionner le à utiliser pour les tests.

   ![](assets/substitution_tab.png)

1. Cliquez sur le bouton de sélection du  pour afficher le de l’ del’ ciblée par le message.

   ![](assets/substitution_recipient_selection.png)

1. Sélectionnez le à utiliser pour le test, puis entrez dans le **[!UICONTROL Address]** champ l’adresse de substitution souhaitée, puis cliquez sur **[!UICONTROL Confirm]**. Tous les ciblant le  seront envoyés à cette adresse électronique, plutôt qu’à celle définie dans la base de données pour ce .

   Si vous souhaitez ajouter un préfixe spécifique à la ligne d’objet du , renseignez le **[!UICONTROL Subject line prefix]** champ.

   ![](assets/substitution_address.png)

   Le préfixe s’affiche comme suit :

   ![](assets/substitution_prefixsample.png)

1. Le  est ajouté au  de, avec son adresse de substitution et son préfixe associés. Répétez les étapes ci-dessus pour tous les  que vous souhaitez utiliser pour les tests, puis cliquez sur **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Si vous souhaitez envoyer un à plusieurs adresses de substitution pour une même  de, vous devez ajouter ce  autant de fois que nécessaire.

   Dans l’exemple ci-dessous, le basé sur le John Smith sera envoyé à deux adresses de substitution différentes :

   ![](assets/substitution_multiple_addresses.png)

1. Une fois que toutes les adresses de et de substitution sont définies, vous pouvez envoyer un pour tester le message. Pour ce faire, cliquez sur le **[!UICONTROL Test]** bouton, puis sélectionnez le type de test à effectuer.

   Notez que si aucun de test n’a été ajouté au du message, les options **[!UICONTROL Email rendering]** et **[!UICONTROL Proof + Email rendering]** ne sont pas disponibles.  For more information on proofs sending, refer to [this section](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Si vous apportez des modifications à votre message, veillez à relancer la préparation du message. Sinon, les modifications ne seront pas répercutées dans le.

### Importation de  à partir d’un  de {#importing-from-audience}

Campaign Standard vous permet d’importer un  dedeque vous pouvez utiliser pour les tests. Cela vous permet, par exemple, d’envoyer à une adresse de courriel unique un ensemble entier de messages ciblant différents  de.

De plus, si votre   est déjà configuré avec les colonnes d&#39;adresse et de préfixe, vous pourrez importer ces informations dans l&#39; **[!UICONTROL Profile substitutions]** onglet. Vous trouverez un exemple d’importation de   avec des adresses de substitution dans [cette section](#use-case).

>[!NOTE]
>
>Lors de l’importation d’un  , seuls les correspondant au **[!UICONTROL Profile substitutions]** de messages sont sélectionnés et ajoutés à l’onglet.

Pour importer des  à utiliser pour les tests à partir d’un  de, procédez comme suit :

1. Dans le de messages, vérifiez que la préparation du message a réussi, puis cliquez sur le **[!UICONTROL Audience]** bloc.

   ![](assets/substitution_preparation.png)

1. Dans l’ **[!UICONTROL Profile substitutions]** onglet, cliquez sur **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Sélectionnez le   à utiliser, puis saisissez l’adresse de substitution et le préfixe à utiliser pour les envoyés aude .

   ![](assets/substitution_audience_define.png)

   Si les adresses de substitution et/ou les préfixes à utiliser ont déjà été définis dans votre  , sélectionnez l’ **[!UICONTROL From Audience]** option, puis spécifiez la colonne à utiliser pour récupérer ces informations.

   ![](assets/substitution_fromaudience.png)

1. Cliquez sur le **[!UICONTROL Import]** bouton. Les  de l’  de l’correspondant au **[!UICONTROL Profile substitution]** message sont ajoutés à l’onglet, ainsi que les adresses et préfixes de substitution associés.

>[!NOTE]
>
>Si vous importez à nouveau le même  , avec des adresses et/ou des préfixes de substitution différents, le  sera ajouté aumême en plus de ceux de l’importation précédente.

![](assets/substitution_audience_added.png)

## Prévisualisation du message avec un ciblé

>[!NOTE]
>
>La  de est disponible avec le concepteur de courrier électronique uniquement.

Pour pouvoir des messages à l’aide de  de ciblées, veillez à ajouter ces **[!UICONTROL Profile substitution]** au [](#selecting-profiles)(voirDéfinition des et des adressesde substitution).

Si vous souhaitez utiliser des  de dans le message, vous devez les ajouter **avant** de lancer la préparation du message. Sinon, elles ne seront pas prises en compte dans le . Par conséquent, assurez-vous de relancer la préparation du message si une modification est apportée au  du.

Pour de messages à l’aide de la substitution de  de, procédez comme suit :

1. Dans le de messages, cliquez sur l’instantané de contenu pour ouvrir le message dans le concepteur de courrier électronique.

   ![](assets/substitution_preview_access.png)

1. Sélectionnez l’ **[!UICONTROL Preview]** onglet, puis cliquez sur **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Cliquez sur l’ **[!UICONTROL Profile Substitution]** onglet pour afficher les  de substitution qui ont été ajoutées à des fins de test.

   Sélectionnez le  à utiliser pour les  de, puis cliquez sur **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Un  du message s’affiche. Utilisez les flèches pour naviguer entre les  sélectionnés.

   ![](assets/substitution_preview.png)

## Utilisation :{#use-case}

Dans ce cas d’utilisation, nous souhaitons envoyer à un ensemble de spécifiques  un bulletin d’information personnalisé. Avant d’envoyer le bulletin d’information, nous voulons le  à l’aide de certains des  de ciblés, et envoyer des aux adresses électroniques internes définies dans un fichier externe.

Les étapes principales de ce cas d’utilisation sont les suivantes :

1. Créez le   à utiliser pour les tests.
1. Créez un flux de travail pour  l&#39; et envoyez la newsletter.
1. Configurez les  de substitution du message.
1. du message à l’aide d’un ciblé .
1. Envoyez des bons à tirer.

### Étape 1 : Créer le   à utiliser pour les tests

1. Préparez le fichier à importer pour créer le  de . Dans notre cas, il doit contenir l&#39;adresse de substitution à utiliser pour le, et un préfixe à ajouter à la ligne d&#39;objet .

   Dans cet exemple, l’adresse électronique &quot;oliver.vaughan@internal.com&quot; recevra un du message ciblant le avec l’adresse électronique &quot;john.doe@mail.com&quot;. Le préfixe &quot;JD&quot; sera ajouté à la ligne d’objet  du.

   ![](assets/substitution_uc1.png)

1. Créez le flux de travail pour créer un   à partir du fichier. Pour ce faire, ajoutez et configurez le   ci-dessous :

   * **[!UICONTROL Load file]**   : Importe le fichier CSV (pour plus d’informations sur ce  , reportez-vous à [cette section](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]**   : Associe les informations du fichier aux informations de la base de données. Dans cet exemple, nous utiliserons l&#39;adresse de courriel  du comme champ de rapprochement (pour plus d&#39;informations sur ce  de, reportez-vous à [cette section](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]**   : Crée un   basé sur le fichier importé (pour plus d’informations sur ce  de, reportez-vous à [cette section](../../automating/using/save-audience.md)).
   ![](assets/substitution_uc2.png)

1. Exécutez le flux de travail, puis accédez à l’ **[!UICONTROL Audiences]** onglet pour vérifier que le  de  a été créé avec les informations souhaitées.

   Dans cet exemple, le   est composé de trois. Chacun d’eux est lié à une adresse de courriel de substitution qui recevra le, avec un préfixe à utiliser dans la ligne d’objet  du.

   ![](assets/substitution_uc3.png)

### Étape 2 : Créez un flux de travail pour  l&#39; et envoyez le bulletin d&#39;information

1. Ajouter **[!UICONTROL Query]** et **[!UICONTROL Email delivery]** , puis configurez-les selon vos besoins (voir les sections [](../../automating/using/query.md)[](../../automating/using/email-delivery.md) etE-mail).

   ![](assets/substitution_uc4.png)

1. Exécutez le flux de travail et assurez-vous que la préparation du message est réussie.

### Étape 3 : Configuration de l’onglet de substitution des  du message

1. Open the **[!UICONTROL Email delivery]** activity. Dans le  du message, cliquez sur le **[!UICONTROL Audience]** bloc.

   ![](assets/substitution_uc5.png)

1. Sélectionnez l’ **[!UICONTROL Profile substitutions]** onglet, puis cliquez sur **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. Dans le **[!UICONTROL Audience]** champ, sélectionnez le   créé à partir du fichier.

   ![](assets/substitution_uc7.png)

1. Définissez l’adresse de substitution et le préfixe de ligne d’objet à utiliser lors de l’envoi des.

   Pour ce faire, sélectionnez l’ **[!UICONTROL From audience]** option, puis sélectionnez la colonne du   qui contient les informations.

   ![](assets/substitution_uc8.png)

1. Cliquez sur le **[!UICONTROL Import]** bouton. Les  de l’ de l’sont ajoutés au, avec leurs adresses de substitution associées et leurs préfixes de ligne d’objet.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >Dans notre cas, tous les  de la  sont visés par le **[!UICONTROL Query]** . Si l&#39;un de ces ne faisait pas partie de l&#39;de message, il ne serait pas ajouté à l&#39; de l&#39;.

### Étape 4 :  le message à l’aide d’un ciblé 

1. Dans le de messages, cliquez sur l’instantané de contenu pour ouvrir le message dans le concepteur de courrier électronique.

   ![](assets/substitution_uc10.png)

1. Sélectionnez l’ **[!UICONTROL Preview]** onglet, puis cliquez sur **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Cliquez sur l’ **[!UICONTROL Profile Substitution]** onglet pour afficher les  de substitution qui ont été ajoutées précédemment.

   Sélectionnez le  à utiliser pour les  de, puis cliquez sur **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Un  du message s’affiche. Utilisez les flèches pour naviguer entre les  sélectionnés.

   ![](assets/substitution_uc_previewprofile.png)

### Étape 5 : Envoyer des

1. Dans le  du message, cliquez sur le **[!UICONTROL Test]** bouton, puis confirmez.

   ![](assets/substitution_uc_sendproof.png)

1. Les sont envoyés selon ce qui a été configuré dans l’ **[!UICONTROL Profile substitutions]** onglet.

   ![](assets/substitution_uc_proofs.png)
