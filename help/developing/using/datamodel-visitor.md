---
title: DataModel
description: En savoir plus sur le modèle de données
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# Visiteur (nms:visitor)

## Description de l’objet

    &lt;table&gt;
    &lt;tr&gt;
    &lt;th&gt;Name&lt;/th&gt;
    &lt;th&gt;Label&lt;/th&gt;
    &lt;th&gt;Type (length)&lt;/th&gt;
    &lt;th&gt;Valeurs d'énumération&lt;/th&gt;
    &lt;/tr&gt;
    &lt;tr&gt;&lt;td&gt;PKey&lt;/td&gt;&lt;td&gt;Identifiant de ressource principale&lt;/td&gt;&lt;td&gt;string &lt;/td&gt;&lt;td&gt;&lt;&lt;td&gt;&lt;&lt;td&gt;&lt; /tr&gt;&lt;tr&gt;&lt;tr&gt;commentaire&lt;/td&gt;&lt;/td&gt;commentaire du référent&lt;/td&gt;chaîne (255)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;créé&lt;/td&gt;&lt;/td&gt;créé&lt;/td&gt;date &lt;/td&gt;&lt;td&gt; &lt;/tr&gt;&lt;/td&gt;&lt;tr&gt;&lt;tr&gt;&lt;td&gt;createdBy (userBase)&lt;/td&gt;&lt;td&gt;Créé par&lt;/td&gt;lien &lt;/td&gt;&lt;/td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;tr&gt;livraison (remise)&lt;/td&gt;&lt;/td&gt;livraison&lt;/td&gt;lien&lt;/td&gt;lien &lt;/td&gt;&lt;td&gt;&lt;/td&gt; &lt;tr&gt;&lt;tr&gt;&lt;td&gt;deliveryId&lt;/td&gt;&lt;td&gt;ID de la dernière remise&lt;/td&gt;&lt;td&gt;entier &lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;desc&lt;/td&gt;&lt;td&gt;Description&lt;/td&gt;chaîne (512)&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt; /tr&gt;&lt;tr&gt;&lt;tr&gt;courriel&lt;/td&gt;&lt;td&gt;courriel&lt;/td&gt;chaîne&lt;/td&gt;de (128)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;externalId&lt;/td&gt;&lt;td&gt;External ID&lt;/td&gt;&lt;td&gt;chaîne (64)&lt;/td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&lt;/td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&lt;/td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt; &lt;tr&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;firstName&lt;/td&gt;&lt;td&gt;Prénom&lt;/td&gt;chaîne (30)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;td&gt;forwardUrl&lt;/td&gt;&lt;td&gt;chaîne (255/2005)&lt; td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;tr&gt;geoUnit(geoUnitBase)&lt;/td&gt;&lt;td&gt;Unité géographique&lt;/td&gt;&lt;td&gt;lien &lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;lastModified&lt;/td&gt;&lt;td&gt;&lt;td&gt;Dernière modification&lt;/td&gt;&gt;td&gt;date &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;nom&lt;/td&gt;&lt;td&gt;nom&lt;/td&gt;nom&lt;/td&gt;chaîne (50)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;modifiéPar (userBase)&lt;/td&gt;&lt;td&gt;modifié par&lt; /td&gt;&lt;td&gt;link&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;orgUnit (orgUnitBase)&lt;/td&gt;unité d'organisation&lt;/td&gt;&lt;td&gt;link &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;origine&lt;/td&gt;d'origine&lt;/td&gt;&lt;td&gt;origine&lt; td&gt;Recensement de la&lt;td&gt;énumération (octet) &lt;/td&gt;&lt;td&gt;&lt;ul&gt;non défini - non défini - 0&lt;/li&gt;&lt;li&gt;VALEUR INVALIDE - __Invalid_value__ - __Invalid_value_&lt;/li&gt;&lt;/ul&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;destinataire(td&gt;destinataire)&lt;/td&gt;&lt;td&gt;Profil identifié&lt;/td&gt;&lt;td&gt;lien&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;nom du destinataire&lt;/td&gt;&lt;td&gt;identifiant de profil&lt;/td&gt;&lt;td&gt;entier &lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;courriel référent&lt;/td&gt;td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&gt;&lt;td&gt;&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&lt;td&gt;&gt; Adresse électronique du référent&lt;/td&gt;chaîne&lt;td&gt;de (128)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;referrerFirstName&lt;/td&gt;&lt;td&gt;prénom du référent&lt;/td&gt;chaîne(30)&lt;/td&gt;&lt;td&gt; &lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&lt;tr&gt;&gt; &lt;referrerId&lt;/td&gt;&lt;td&gt;Identifiant référent&lt;/td&gt;&lt;td&gt;entier &lt;/td&gt;&lt;/td&gt;&lt;/tr&gt;&lt;tr&gt;&lt;td&gt;referrerLastName&lt;/td&gt;&lt;td&gt;Nom référent&lt;/td&gt;&lt;td&gt;chaîne (50)&lt;/td&gt;&lt;td&gt;&lt;/td&gt;&gt;&lt;tr&gt;&lt;td&gt;referrerRcp (destinataire)&lt;/td&gt;&lt;/td&gt;référent&lt;/td&gt;lien&lt;/td&gt;&lt;/td&gt;&lt;td&gt;&lt;/tr&gt;&lt;tr&gt;titre&lt;/td&gt;titre&lt;/td&gt;étiquette&lt;/td&gt;&lt;td&gt;chaîne (255)&lt;/td&gt;&lt;td&gt; &lt;&lt;td&gt;&lt;/td&gt;/tr&gt;&lt;/table&gt;
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    

## Filtres

Par nom, prénom ou adresse électronique (parTexte)</p>

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>texte</td>
        <td>string</td>
        </tr>
    </table>