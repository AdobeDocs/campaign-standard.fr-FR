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
source-git-commit: 13ad7e616b51ae0fa0804db02f15120a636b7603

---


# Livraison (nms:delivery)

## Description de l’objet

<table>
               <tr>
                  <th>Nom</th>
                  <th>Libellé</th>
                  <th>Type (longueur)</th>
                  <th>Valeurs d'énumération</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Bon à tirer</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Identifiant principal de la ressource</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>A/B Testing</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advanced</td>
                  <td>Livraison avancée</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Paramètres avancés</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Contenu d’Adobe Experience Manager</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Message d'avertissement</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Type d'avertissement</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>attache</td>
                  <td>Fichiers joints</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>branding (brandingBase)</td>
                  <td>Marque</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Logs de diffusion </td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildingIn</td>
                  <td>Objet d’application intégré</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campaign</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Compte Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>commandes</td>
                  <td>Commandes</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contenu</td>
                  <td>Contenu</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Source du contenu</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaign - 0</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Type de ressource</td>
                  <td>string </td>
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
                  <td>deliveryMode</td>
                  <td>Mode de livraison</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Livraison en masse - en masse - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Description - descriptif - 2</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Externe - externe - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Routage</td>
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
                  <td>emailPreview</td>
                  <td>Aperçu du courrier électronique</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Exclus</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>exclusions</td>
                  <td>Exclusions appliquées</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>exécution</td>
                  <td>Paramètres d’exécution de remise</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Type d'exécution</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Unique - une fois - 0</li>
                        <li>Continu - continu - 1</li>
                        <li>Centre de messages - messageCenter - 2</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>ForecLogs</td>
                  <td>Journal des prévisions</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Entité géographique</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Ajout de fichiers joints</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icône</td>
                  <td>Icône</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Courrier électronique transactionnel - EmailLightning - 60</li>
                        <li>Télécopie - fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>Courrier électronique récurrent - emailRefresh - 30</li>
                        <li>Courrier direct - papier - 3</li>
                        <li>Téléphone - Téléphone - 2</li>
                        <li>Autre - autre - 120</li>
                        <li>SMS récurrents - smsRefresh - 31</li>
                        <li>Application mobile - pushNotification - 40</li>
                        <li>SMS transactionnels - smsLightning - 61</li>
                        <li>Courriel - Courriel - 0</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Est une ressource externe</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isMaster</td>
                  <td>Master</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Modèle</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>itérations</td>
                  <td>Diffusions</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>job</td>
                  <td>Traitement</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Logs</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpis</td>
                  <td>Indicateurs</td>
                  <td>item </td>
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
                  <td>logicalStatus</td>
                  <td>Statut de l'exécution</td>
                  <td>énumération (chaîne) (255)</td>
                  <td>
                     <ul>
                        <li>En cours - commencé - commencé</li>
                        <li>Edition - édition - édition</li>
                        <li>Terminé - terminé - terminé</li>
                        <li>Avertissement - avertissement</li>
                        <li>Erroné - erreur - erreur</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mailParameters</td>
                  <td>Paramètres d'en-tête Email</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Date</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mappage (deliveryMapping)</td>
                  <td>Mapping de ciblage</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Instance maître</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicateurs principaux</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Télécopie - fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>Courriel - Courriel - 0</li>
                        <li>Téléphone - Téléphone - 2</li>
                        <li>Courrier direct - papier - 3</li>
                        <li>Application mobile - pushNotification - 40</li>
                        <li>Autre - autre - 120</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
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
                  <td>offerManagement</td>
                  <td>Gestion des offres</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entité organisationnelle</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Diffusion parente</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priorité</td>
                  <td>Priorité de diffusion</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Elevé - élevé - 20</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programme</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>épreuves</td>
                  <td>Bons à tirer</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Aperçu de la notification push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Paramètres de PushNotification</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Rapports en temps réel</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Version de ressource</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Message du ruban</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>scénario</td>
                  <td>Paramètres de modèle de remise</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>planification</td>
                  <td>Planifier la diffusion</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Paramètres SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Aperçu du SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>état</td>
                  <td>Status</td>
                  <td>énumération (octet) </td>
                  <td>
                     <ul>
                        <li>Début en attente - startPending - 51</li>
                        <li>Prêt à être livré - prêt - 45</li>
                        <li>Nouvelle tentative en attente - réessayerEn attente - 61</li>
                        <li>Nouvelle tentative en cours - réessayerInProgress - 62</li>
                        <li>Échec - échec - 87</li>
                        <li>En cours - commencé - 55</li>
                        <li>Ciblage en attente - targetPrepPending - 11</li>
                        <li>Personnalisation en attente - messagePrepPending - 21</li>
                        <li>En pause - En pause - 75</li>
                        <li>Modification - édition - 0</li>
                        <li>Terminé - terminé - 95</li>
                        <li>Comptage en cours - targetSelection - 12</li>
                        <li>Message finalisé - messageReady - 25</li>
                        <li>Échec de la personnalisation ou du décompte - prepareError - 37</li>
                        <li>Arrêté - annulé - 85</li>
                        <li>Personnalisation en cours - messagePréparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                        <li>Arbitrage en cours - targetArbitrage - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>cibles</td>
                  <td>Cible de la diffusion</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Modèle de remise</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniature</td>
                  <td>Miniature de remise</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Diffusion</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>Paramètres du tracking</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Tracking</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>URL trackées</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>triggerMessage</td>
                  <td>Paramètres du message transactionnel</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>typologie (typologyBase)</td>
                  <td>Typologie</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Processus de ciblage</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Etat du workflow</td>
                  <td>énumération (chaîne) (255)</td>
                  <td>
                     <ul>
                        <li>En cours - commencé - commencé</li>
                        <li>Edition - édition - édition</li>
                        <li>Terminé - terminé - terminé</li>
                        <li>Avertissement - avertissement</li>
                        <li>Erroné - erreur - erreur</li>
                        <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
            </table>

## Filtres

Par type de canal (par canal)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>channel</td>
    <td>enumeration</td>
    </tr>
</table>

Par type d'exécution (byExecutionType)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>enumeration</td>
    </tr>
</table>

Par état logique (parLogicalStatus)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>état</td>
    <td>enumeration</td>
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
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Par période (par période)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Par période (parStartPeriod)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Par état de publication (parPublicationStatus)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>enumeration</td>
    </tr>
</table>

Par état (par état)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>état</td>
    <td>enumeration</td>
    </tr>
</table>

Messages de suivi (showFollowup)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>suivi</td>
    <td>boolean</td>
    </tr>
</table>

Inclure les livraisons avancées (avec Advanced)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>boolean</td>
    </tr>
</table>

Inclure les livraisons continues à partir d’une liste hétérogène (avec Continuous)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>withContinuous</td>
    <td>boolean</td>
    </tr>
</table>

Inclure des épreuves (avec FCP)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>boolean</td>
    </tr>
</table>

Planifiée pendant la période donnée (parPlanning)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Présente pendant une période donnée (parCalendar)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Afficher prêtes à l’emploi (showOob)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>oob</td>
    <td>boolean</td>
    </tr>
</table>