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
source-git-commit: 18d9b33e36db628ef1fc014e4abe6a4a7eef48b3

---


# Audience (nms:audience)

## Description de l’objet

<table>
               <tr>
                  <th>Nom</th>
                  <th>Libellé</th>
                  <th>Type (longueur)</th>
                  <th>Valeurs d'énumération</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Identifiant principal de la ressource</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aamMappingId</td>
                  <td>ID de mappage d’Audience Manager</td>
                  <td>string (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>AMC Data source</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>Aperçu de la population sélectionnée</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>Schéma de données</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectionLineNumber</td>
                  <td>Utiliser un numéro de ligne comme ID</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Count</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Date de comptage</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>Créé</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Créé par</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Description</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>doNotPersist</td>
                  <td>N’Historique pas cette tâche</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Erreurs avant abandon</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Expire le</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Entité géographique</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Audience d’Adobe Marketing Cloud</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Est une ressource externe</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logs</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Libellé</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Dernière modification</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifyBy (userBase)</td>
                  <td>Modification par</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>id</td>
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entité organisationnelle</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nomFichierRejet</td>
                  <td>Fichier de rejets</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Nom de l'audience partagée</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>source</td>
                  <td>Source</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>Identifiant de la source</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Audience</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>Type</td>
                  <td>énumération (chaîne) (100)</td>
                  <td>
                     <ul>
                        <li>Requête - Requête - Requête</li>
                        <li>Liste - liste - liste</li>
                        <li>Fichier - fichier - fichier</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>where</td>
                  <td>Définition de requête</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflow)</td>
                  <td>Workflow</td>
                  <td>link </td>
                  <td> </td>
               </tr>
            </table>

## Filtres

En filtrant la dimension (parFilteringResource)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>filterResource</td>
    <td>string</td>
    </tr>
</table>

Par nom ou étiquette (parTexte)

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

Par type (byType)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>type</td>
    <td>enumeration</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>string</td>
    </tr>
</table>