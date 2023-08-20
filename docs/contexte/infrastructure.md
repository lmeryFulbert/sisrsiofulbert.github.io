# Infrastrucure

## Dossier technique de l’infrastructure du réseau *SportLudique*

## Lycée Fulbert Chartres 2023-2024

## Table des matières

[Dossier technique de l’infrastructure du réseau *SportLudique*
[1](#dossier-technique-de-linfrastructure-du-réseau-sportludique)](#dossier-technique-de-linfrastructure-du-réseau-sportludique)

[Lycée Fulbert Chartres 2020-2021
[1](#lycée-fulbert-chartres-2023-2024)](#lycée-fulbert-chartres-2023-2024)

[Introduction : [2](#introduction)](#introduction)

[Rappel du contexte : [2](#rappel-du-contexte)](#rappel-du-contexte)

[Présentation Générale de l’infrastructure :
[2](#présentation-générale-de-linfrastructure)](#présentation-générale-de-linfrastructure)

[L’Infrastructure réseau du lycée Fulbert simulant le réseau
SportLudique
[3](#linfrastructure-réseau-du-lycée-fulbert-simulant-le-réseau-sportludique)](#linfrastructure-réseau-du-lycée-fulbert-simulant-le-réseau-sportludique)

[Etape préalable pour travailler sur le contexte SportLudique
[3](#etape-préalable-pour-travailler-sur-le-contexte-sportludique)](#etape-préalable-pour-travailler-sur-le-contexte-sportludique)

[Préfixe à utiliser dans les noms des VM sur la ferme
[4](#préfixe-à-utiliser-dans-les-noms-des-vm-sur-la-ferme)](#préfixe-à-utiliser-dans-les-noms-des-vm-sur-la-ferme)

[Login et password à utiliser
[4](#login-et-password-à-utiliser)](#login-et-password-à-utiliser)

[Les machines virtuelles à créer et à héberger sur la ferme de serveur
sur chaque site (donc dans chaque VLAN d’îlot) :
[4](#les-machines-virtuelles-à-créer-et-à-héberger-sur-la-ferme-de-serveur-sur-chaque-site-donc-dans-chaque-vlan-dîlot)](#les-machines-virtuelles-à-créer-et-à-héberger-sur-la-ferme-de-serveur-sur-chaque-site-donc-dans-chaque-vlan-dîlot)

[L’Infrastructure réseau
[6](#linfrastructure-réseau)](#linfrastructure-réseau)

[Plan d’adressage IP [6](#plan-dadressage-ip)](#plan-dadressage-ip)

[Les éléments du réseau
[6](#les-éléments-du-réseau)](#les-éléments-du-réseau)

[Infrastructure SportLudique (au siège à chartres)
[7](#infrastructure-sportludique-au-siège-à-chartres)](#infrastructure-sportludique-au-siège-à-chartres)

[Abonnements Internet pour chaque site
[7](#abonnements-internet-pour-chaque-site)](#abonnements-internet-pour-chaque-site)

[Abonnement Fibre : [7](#abonnement-fibre)](#abonnement-fibre)

[Accès Internet et DMZ
[8](#accès-internet-et-dmz)](#accès-internet-et-dmz)

[Messagerie Electronique
[8](#messagerie-electronique)](#messagerie-electronique)

[Réseau WIFI [8](#réseau-wifi)](#réseau-wifi)

[Supervision de réseau, Maintenance et déploiement
[9](#supervision-de-réseau-maintenance-et-déploiement)](#supervision-de-réseau-maintenance-et-déploiement)

[ANNEXE 1 - Schéma de l’infrastructure DE CHAQUE SITE
[10](#_Toc50622457)](#_Toc50622457)

[ANNEXE 2 - PLAN D’ADRESSAGE IP
[11](#annexe-2---plan-dadressage-ip)](#annexe-2---plan-dadressage-ip)

[ANNEXE 2 - PLAN D’ADRESSAGE IP des serveurs (suite)
[13](#annexe-2---plan-dadressage-ip-des-serveurs-suite)](#annexe-2---plan-dadressage-ip-des-serveurs-suite)

[Serveurs publiques (Internet simulé) et serveurs hébergés dans DMZ
[13](#serveurs-publiques-internet-simulé-et-serveurs-hébergés-dans-dmz)](#serveurs-publiques-internet-simulé-et-serveurs-hébergés-dans-dmz)

[ANNEXE 3 - Plan de brassage.
[14](#annexe-3---plan-de-brassage.)](#annexe-3---plan-de-brassage.)

[ANNEXE 4 - Identifiants & mots de passe
[15](#annexe-4---identifiants-mots-de-passe)](#annexe-4---identifiants-mots-de-passe)

[Annexe 5 - Infrastructure Publique simulée dans le labo du lycée
Fulbert
[16](#annexe-5---infrastructure-publique-simulée-dans-le-labo-du-lycée-fulbert)](#annexe-5---infrastructure-publique-simulée-dans-le-labo-du-lycée-fulbert)

[Annexe 5 bis [17](#annexe-5-bis)](#annexe-5-bis)

[Adressage IP publique des sites
[17](#adressage-ip-publique-des-sites)](#adressage-ip-publique-des-sites)

[Routeurs simulant internet dans l’infrastructure du lycée Fulbert
[17](#routeurs-simulant-internet-dans-linfrastructure-du-lycée-fulbert)](#routeurs-simulant-internet-dans-linfrastructure-du-lycée-fulbert)

[Annexe 6 [18](#annexe-6)](#annexe-6)

[Model [19](#model)](#model)

[SPEC [19](#spec)](#spec)

[Features [19](#features)](#features)

## Introduction :

Les Projets Personnels Encadrés (PPE) seront développés autour du
contexte *SportLudique*. Cet environnement permettra à l’étudiant de
réaliser un ensemble de projets autour de différentes situations
professionnelles (les missions) et acquérir ainsi les compétences en
conformité avec le référentiel.

## Rappel du contexte :

*SportLudique* est une société basée sur 4 sites distants chartres,
tours, Orléans et Châteauroux. Elle est spécialisée dans la conception
et la production d’articles de sports non conventionnels.

L’infrastructure informatique et réseau est prise en charge par le
département "Solution d’Infrastructure Système et Réseau" (SISR) qui se
charge de l’exploitation de l’ensemble des équipements du parc ainsi que
de la réalisation des projets informatiques.

La DSI délègue les taches techniques de réalisation, déploiement,
maintenance et support à son prestataire maître d’œuvre autour d’un
contrat de service dans lequel il assure la maîtrise d’ouvrage.

## Présentation Générale de l’infrastructure :

L’infrastructure (schéma Annexe 1) est découpée en 3 parties comprenant
le siège ainsi que les différents sites distants et le réseau d’accès à
Internet. La DSI est responsable de l’administration de
l’infrastructure, de la fourniture de services et de la sécurisation des
données en déléguant ces tâches à son prestataire homologué qui est le
maître d’œuvre pour la réalisation des opérations d’administration du
système d’information de *SportLudique*.

Le service Informatique de *SportLudique* est mandaté pour l’exécution
de tous les projets qui concernent le parc informatique de l’entreprise
et agit comme prestataire au travers de contrats de service vis-à-vis
des différents sites distants. Chaque site dispose d’une infrastructure
avec un domaine &lt;nomville&gt;.sportludique.fr . Un serveur d’annuaire
Active Directory et son contrôleur de domaine assure la gestion et
l’administration du réseau.

Le nom de domaine *sportludique.fr* a été réservé auprès de l’AFNIC et
le bureau d’enregistrement (registar) gérant ce nom de domaine est
nordnet (en réalité il est géré par l’enseignant M MERY).

## 

WHOIS

Le nom de domaine "**sportludique.fr**" est déjà déposé.

 Résultat de votre recherche

-   **Nom de domaine :** sportludique.fr

-   **État :** Actif (consulter aussi le [**site
    > web **](http://www.lyceefulbert.fr/))

-   **DNSSEC :** inactif

-   **Bureau d'enregistrement
    > :** [**NORDNET**](http://www.afnic.fr/fr/produits-et-services/services/whois/)

-   **Date de création : **29 mai 2012 17:37

-   **Date d'expiration : **29 mai 2016 17:37

-   **Serveurs de noms (DNS)**

    -   ***Serveur n° 1: **ns2.lerelaisinternet.com*

    -   ***Serveur n° 2: **ns1.lerelaisinternet.com*

##  L’Infrastructure réseau du lycée Fulbert simulant le réseau SportLudique

L’infrastructure comporte plusieurs périmètres de sécurité. Les services
de *SportLudique* sont organisés en VLAN de niveau 1.

Les machines hôtes utilisables par les étudiants sont câblées via des
prises Ethernet murale de labo dont le numéro est pair (2-4-6-8). Ces
prises sont ensuite brassées sur le Switch SISR2 sur leur port respectif
(2-4-6-8) dans le vlan1 par défaut qu’on vous demande de ne pas modifier
sur ces ports. (Pour revenir facilement dans une configuration classique
pour l’apprentissage et la connectivité au domaine SIO.Fulbert)

Le Switch SISR2 est relié à autre baie par l’intermédiaire du Switch HP
par défaut sur un port associé au VLAN 217 (VLAN par défaut des
deuxièmes années SISR).

![](medias/infrastructure/image1.emf)

### Etape préalable pour travailler sur le contexte SportLudique

Brancher le Swtich SISR2 sur le port du VLAN correspondant à votre îlot
pour isoler celle-ci du réseau habituel, et ne plus être impacté par
l’agent relai DHCP configuré sur le VLAN 217.

Le VLAN 200 est le VLAN Labo pour toute la promotion des deuxièmes
années SISR. Le VLAN 210 est le VLAN Labo de l’ îlot 1. Le 220 celui de
l’ îlot 2 etc…

![](medias/infrastructure/image2.emf)

Chaque site Chartres, Tours, Orléans et Châteauroux correspond à un îlot
et possède donc son propre VLAN isolé du reste du réseau du Labo du
lycée Fulbert.

Penser à enlever les postes du domaine SIO.fulbert en les mettant dans
en groupe de travail WORKGROUP (réseau poste à poste) puis les attacher
au domaine local du site sur lequel vous êtes mandaté. Évidement
celui-ci doit être mis en place sur la ferme de serveur dans le VLAN
correspondant.

### Préfixe à utiliser dans les noms des VM sur la ferme

<table>
<colgroup>
<col style="width: 44%" />
<col style="width: 55%" />
</colgroup>
<thead>
<tr class="header">
<th>Chartres</th>
<th>CHA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tours</td>
<td>TRS</td>
</tr>
<tr class="even">
<td>Orléans</td>
<td>ORL</td>
</tr>
<tr class="odd">
<td>Châteauroux</td>
<td>CHX</td>
</tr>
</tbody>
</table>

### Login et password à utiliser

<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Microsoft Windows</p>
<p>Serveur</p>
<p>Stations</p></th>
<th><p>administrateur / Azerty1234</p>
<p>nomuser / nomuser (géré dans l’annuaire AD)</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Distribution linux</td>
<td><p>root / Azerty1234</p>
<p>compte utilisateur : dsi / Azerty1234</p></td>
</tr>
<tr class="even">
<td><p>Switch / Routeurs</p>
<p>Mode privilégié (enable)</p></td>
<td><p>admin / Azerty1234</p>
<p>Azerty1234</p></td>
</tr>
</tbody>
</table>

### Les machines virtuelles à créer et à héberger sur la ferme de serveur sur chaque site (donc dans chaque VLAN d’îlot) :

#### Un contrôleur de domaine principal

VM Windows Server (Minimum 2008R2) Active Directory/DNS/DHCP

\- Rôles :

-   Contrôleur de domaine AD-DC

-   DNS

-   DHCP

-Configuration :

-   Nom de la machine : &lt;*prefixe*&gt;-AD-

-   OS : Windows 2008 Server R2 64 bits minimum

-   Login : Administrateur

-   Mot de passe : Azerty1234

**  
**

#### Un serveur de déploiement d’image de stations de travail

\- Au choix parmi les solutions suivantes à documenter :

-   ServeurMicrosoft WDS

-   Serveur FOG

-   Serveur CloneZilla

#### Un logiciel d’inventaire et de helpdesk opensource et de télédeploiement de logiciel

**Linux FusionInventory/GLPI**

-   Serveur d’inventaire (FusionInventory), gestionnaire de parc
    informatique (GLPI)

-   Application WEB, gestionnaire de ressources et des tickets
    d’incidents

-   Télé déploiement possible avec FOG ou GLPI

#### Un serveur Proxy filtrant (implémentation au choix après études des possibilités)

-   Nom de la machine : PROXY

<!-- -->

-   Proxy cache sous Squid - Proxy filtrant :SquidGuard

-   Avec authentification transparente et traçabilité des accès dans un
    serveur de Log

#### Un serveur de Log

-   Centralisation des logs sur un serveur SYSLOL avec gestion des
    sauvegardes

#### Un serveur de supervision (implémentation au choix après études des possibilités)

\- Nom de la machine :

\- Rôles du serveur : Supervision des équipements réseau (routeurs,
commutateurs, point d’accès sans fils)

\- Configurations :

-   OS : Eyes Of Network, Centreon, PRTG ….A étudier

#### Services Web

Serveurs hébergés dans la DMZ de chaque site à isoler sur un VLAN dédié
à créer sur votre switch. Le switch CISCO sera alors raccordé à un port
TRUNCK 802.1 géré par votre enseignant sur le switch HP

On montera chaque service de la DMZ dans l’une ou l’autre des
technologies à savoir Windows et Linux.

-   Serveur http hébergeant de nombreux sites web à savoir dans le cas
    du site de chartres:

    -   [www.chartres.sportludique.fr](http://www.chartres.sportludique.fr)

    -   intranet.chartres.sportludique.fr

    -   extranet.chartres.sportludique.fr

-   Serveur SFTP, en téléchargement de documents mis en ligne

## L’Infrastructure réseau 

La structure générale du réseau comprend :

> \- Les sous réseaux des sites distants
>
> \- Les sous réseaux des départements
>
> \- Le réseau Backbone
>
> \- Le réseau WIFI
>
> \- La DMZ de chaque site géographique
>
> \- Le réseau d’accès à Internet

Le réseau *sportLudique* héberge tous les serveurs dans une baie de
serveurs installée dans le service Informatique du département Réseau.
Les serveurs hébergent les applications de gestion et de supervision du
parc informatique.

Le réseau mobile WIFI permet de servir les postes nomades du personnel
des différents sites. Ce réseau doit être assez souple et adaptable pour
fournir un accès à Internet au public externe sans toutefois
compromettre la sécurité du SI. Le schéma de l’infrastructure générale
est donné en Annexe 1.

### Plan d’adressage IP 

Le réseau général est construit autour de l’adresse 172.16.0.0 avec un
masque de 16 bits. Ceci permet de couvrir l’ensemble du plan d’adressage
de l’entreprise mais aussi pour les évolutions. L’administrateur vous
demande de réfléchir aux découpages en sous réseau pour sécuriser les
différents services de chaque site. Le plan d’adressage IP **192.168.x.0
/28 est attribué à la DMZ de chaque site.**

Les tableaux en Annexe à compléter contiennent le plan d’adressage IP de
l’ensemble du réseau. Ce plan d’adressage tient compte d’une
exploitation des adresses IP en mode dynamique par 2 serveurs DHCP.

Un bloc d’adresse est réservé pour les équipements en adressage fixe et
ceci pour chaque sous réseaux. Des règles d’ingénierie ont été définies
et imposent de placer les plages d’adresses fixes sur les adresses les
plus hautes de chaque sous réseau.

Ce tableau est présenté en ANNEXE 2.

### Les éléments du réseau

Ce réseau regroupe les fonctions suivantes :

> \- Une structure de VLAN de niveau 3 est utilisée pour la
> structuration des réseaux WIFI. Cette structure permet de limiter les
> domaines de diffusion. Les VLANs de *sportludique* sont organisés
> selon une structure hiérarchique par département.
>
> \- Un VLAN de gestion permet d’accéder aux équipements de réseau via
> les postes Administrateur du service Informatique du département
> réseau. La gestion des équipements permet d’assurer la maintenance,
> les mises à jour des configurations ou des IOS et les opérations
> ponctuelles de surveillance et de test du réseau.
>
> \- Le routage des VLAN utilise la technique des sous interfaces VLAN
> et l’encapsulation 802.1Q implémentés dans les switch et routeurs.
>
> \- Un connexion Haut débit assure une liaison à l’Internet. Chaque
> site est connecté via à routeur au réseau publique via un prestataire
> (géré par votre professeur qui vous donnera en temps utile les
> adresses IP publiques utilisables).
>
> \- Chaque site dispose d’une connexion de secours de type xDSL fournie
> par un second FAI afin d’assurer une haute disponibilité de l’accès
> Internet. On réfléchira à une solution pour rendre les services web
> offerts par chaque site hautement disponible eux aussi.
>
> \- les serveurs DHCP et serveurs de nom DNS assurent la gestion des
> machines. Le service DHCP est installé sur 2 serveurs physiquement
> séparés pour assurer la tolérance aux pannes.
>
> \- Un routeur filtrant assure les fonctions de pare feu entre le LAN,
> la DMZ et l’internet (WAN), la distribution pfsense basée sur BSD sera
> privilégiée pour cette tâche. Ce point névralgique devra être
> hautement disponible lui aussi au moins sur le site physique de
> chartres.

### Infrastructure SportLudique (au siège à chartres)

L’entreprise comporte 6 services (6 VLANs minimum) dont le département
réseau qui renferme le service Informatique. Ce service assure la
gestion et administration du réseau et du parc informatique.

Les ressources informatiques (serveurs, bases de données, systèmes de
supervision…) sont situées dans une baie de serveurs.

Parmi ces serveurs on trouve les 2 serveurs DHCP en redondance à chaud
et le serveur Proxy qui se charge des requêtes http des personnels de
l’entreprise

Les salles ressources au rez de chaussée du bâtiment offrent des accès
aux équipements multimédia, vidéo, téléphones IP, imprimantes et
ordinateurs pour les utilisateurs externes tel que des clients ou des
fournisseurs.

Ces salles sont regroupées dans le n<sup>ième</sup> VLAN intégré dans le
réseau.

### Abonnements Internet pour chaque site

Un abonnement FAI haut débit Fibre est géré par un routeur CISCO qui
supporte le trafic principal. Un abonnement FAI ADSL de secours devra
être mis en place chargé de prendre le relais en cas de panne de
l’abonnement du routeur primaire. Lorsque le lien primaire retrouve un
état opérationnel il reprend la gestion du trafic (Protocole
propriétaire Cisco HSRP).

Les 2 abonnements Internet sont souscris avec les opérateurs Orange et
SFR qui délivrent un contrat de service Pro Fibre 100Mb/s avec une SLA
GTR 4heures pour l’abonnement principal Fibre et un contrat bas débit
ASDL GTR 48Heures pour l’abonnement de secours.

<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 20%" />
<col style="width: 17%" />
<col style="width: 19%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><strong>Chartres</strong></th>
<th><strong>Tours</strong></th>
<th><strong>Orléans</strong></th>
<th><strong>Chateauroux</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Abonnement <strong>ADSL </strong>:</p>
<h3 id="abonnement-fibre">Abonnement Fibre : </h3></td>
<td><p>183.44.128.2 /30</p>
<p>221.87.28.1 /30</p></td>
<td><p>183.44.137.2 /30</p>
<p>221.87.37.1 /30</p></td>
<td><p>183.44.145.2 /30</p>
<p>221.87.45.1 /30</p></td>
<td><p>183.44.136.2 /30</p>
<p>221.87.36.1 /30</p></td>
</tr>
</tbody>
</table>

### Accès Internet et DMZ

Cette partie représente le périmètre de sécurité pour l’accès à
Internet. Une zone DMZ est intégrée dans le routeur pare-feu qui
règlemente les échanges l’accès à Internet. Ce routeur assure la gestion
du sous réseau DMZ qui renferme les services WEB et FTP, la fonction de
pare feu et l’interconnexion au réseau privé et Internet. Son
implémentation sera créée avec une VM connecté aux différents VLANS du
lycée Fulbert pour isoler les flux et simuler un véritable routeur
dédié.

Les 2 services SFTP et WEB de la DMZ sont intégrés dans une VM dans une
machine Windows ou linux pour héberger le site WEB de chaque site. Ces
services sont accessibles depuis l’Internet (simulé dans le labo) et le
réseau interne sous certaines conditions.

Le périmètre de sécurité est représenté par les fonctions suivantes :

> \- Pare Feu entre le réseau interne, la DMZ et Internet avec
> sécurisation par des règles de contrôle d’accès. Ces règles sont
> définies ci-dessous.
>
> \- Haute disponibilité sur l’accès à Internet assuré par 2 routeurs en
> HSRP avec fonction NAT/PAT. Une fonction port forwarding permet de
> rediriger les requêtes provenant de l’Internet (du routeur principal
> fibre) vers les ressources accessibles de l’association (http, FTP…).
>
> \- Pour compléter le périmètre de sécurité, un serveur Proxy WEB
> (Proxy squid) réglemente l’accès à Internet pour l’ensemble des
> utilisateurs internes de chaque site en les traçant excepté pour les
> postes d’administration du service Informatique.

**Règles de contrôle d’accès :**

> 1/ Seuls les requêtes du serveur Proxy peut accéder à Internet.
>
> 2/ Les Internautes peuvent accéder à la DMZ mais pas au réseau privé.
>
> 3/ Les sous réseaux de *SportLudique* peuvent accéder aux ressources
> de la DMZ.
>
> 4/ Les postes nomades du réseau Wifi ¨Visiteurs¨ n’ont accès qu’à
> Internet. Les postes du réseau Wifi ¨Employés¨ peuvent accéder au
> réseau Interne et à Internet.
>
> 5/ Le trafic ICMP est autorisé pour les postes du service
> Informatique.
>
> 6/ Le trafic ICMP provenant de l’Internet est interdit.

### Messagerie Electronique

Un serveur de messagerie sera aussi disponible sur chaque site. Le nom
de domaine sportludique.fr étant réservé, les adresses auront la forme
[utilisateur@&lt;ville&gt;.sportludique.fr](mailto:utilisateur@%3cville%3e.sportludique.fr)

Les utilisateurs devront pouvoir consulter leur messagerie du réseau
internet et du réseau publique. Des échanges seront évidemment possibles
entre chaque site géographique.

### Réseau WIFI

Pour cette maquette le réseau WIFI interne couvre la surface occupée
dans le bâtiment Hall d’accueil et l’espace extérieur qui couvrira les
zones utilisées pour les journées évènementielles porte ouverte. Ce
point d’accès contrôle 2 réseaux radios identifiés par un SSID.

Un SSID ¨Visiteurs¨ permet de fournit une connectivité Internet au
public externe à l’association dans le cadre de leur visite dans les
locaux ou lors d’activités événementielles type journées portes ouvertes
qui accueille du public ou des invités. Ce réseau offre une connectivité
ouverte non sécurisée à Internet. L’identification du réseau est
diffusée.

Un SSID ¨Employés¨ fournit au personnel interne munis de postes
portables l’accessibilité Internet et vers le réseau privé. Pour ce SSID
on utilise la sécurisation WPA et une authentification WPA2-Entreprise.
Pour ce réseau, le cryptage AES est utilisé et le SSID de réseau n’est
pas diffusée. L’authentification sera assurée via le contrôleur de
domaine ActiveDirectory et une stratégie d’accès au réseau sera
différente en fonction des groupes utilisateurs. Un test sera fait avec
une authentification par certificats électroniques.

Ces 2 réseaux sont séparés par des VLAN de niveau 3 et une règle sur le
routeur PRF permet d’éviter que les visiteurs puissent accéder au réseau
interne privé.

### Supervision de réseau, Maintenance et déploiement

En cas de panne l’analyse de problème réseau s’effectue via l’outil
d’analyse de trame Wireshark qui permettra de vérifier les anomalies de
fonctionnement du réseau pour la validation, les tests ou la mise en
service mais aussi le dépannage de situation en cas de blocage.

Une fonction de port mirroring sur les commutateurs Cisco permet
d’analyser les trafics sur les liens stratégiques

Un service d’administration à distance utilisant le protocole SSH
version 2 permet une prise de contrôle à distance des équipements
routeurs et commutateurs du réseau en mode sécurisé. L’application SSH
sera installée sur les équipements de réseau. Ce protocole utilise le
mode de chiffrement à clés asymétriques RSA (longueur de clé 1024).

Les équipements de réseau sont accessibles en SNMP pour permettre
l’exploitation du réseau par le logiciel de superivision (Centreon ou
autre solution compatible avec le protocole SNMP). On utilise la
communauté ¨spludique¨ pour les relations agent/serveur avec droits en
lecture. On utilisera les traps ou notifications snmp définies par Cisco
pour surveiller le fonctionnement du protocole HSRP sur les liaisons
internet, les ruptures de liens et les pannes et redémarrages des
équipements.

Le superviseur est dédié à la supervision des équipements de réseau
(commutateurs, routeurs, passerelles, Points d’accès).

L’outil de gestion de parc et gestion d’incidents GLPI permet d’assurer
le suivi et la gestion des postes et serveurs informatiques. Un service
de télé déploiement de logiciel devra être mis en place dans chaque site
par les équipes techniques.

## ANNEXE 1 - Schéma de l’infrastructure DE CHAQUE SITE

![](medias/infrastructure/image3.emf)

## ANNEXE 2 - PLAN D’ADRESSAGE IP

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 18%" />
<col style="width: 18%" />
<col style="width: 18%" />
<col style="width: 18%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><strong>Site de</strong></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>LAN global</strong></td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Nombre d'hotes</td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Nombre de serveurs</td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td>Adresse réseau</td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td>Masque</td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td colspan="3"><strong>Plan adressage sous réseau (VLAN)</strong></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><strong>VLAN service + ID ferme de serveur</strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
</tr>
<tr class="odd">
<td>Nombre d'hôtes</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>Masque CIDR</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>Masque décimal</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>Adresse du réseau</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>Adresse de diffusion</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>Plage fixe</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>Plage DHCP principal</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>Plage DHCP secondaire</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>Passerelle</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>relai DHCP (oui / non)</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 18%" />
<col style="width: 18%" />
<col style="width: 18%" />
<col style="width: 18%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Routeur Pare Feu</strong></th>
<th></th>
<th></th>
<th></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Vlan Transport VLAN ID</strong></td>
<td><strong> Interface eth0</strong></td>
<td><strong> Interface eth1</strong></td>
<td><strong> Interface eth2</strong></td>
<td><strong> Interface eth3</strong></td>
</tr>
<tr class="even">
<td><strong>vers service</strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
<td><strong> </strong></td>
</tr>
<tr class="odd">
<td>Adresse</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>Masque</td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><strong>Routeurs FAI</strong></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><strong> </strong></td>
<td><strong> Interface eth0 (publique)</strong></td>
<td><strong> Interface eth1 (privée)</strong></td>
<td><strong> Interface virtuelle</strong></td>
</tr>
<tr class="even">
<td rowspan="4">R1</td>
<td>VLAN</td>
<td>100</td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>adresse</td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>masque</td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><strong>Passerelle</strong></td>
<td colspan="3"> </td>
</tr>
<tr class="even">
<td rowspan="4">R2</td>
<td>VLAN</td>
<td>200</td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td>adresse</td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td>masque</td>
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><strong>Passerelle</strong></td>
<td colspan="3"> </td>
</tr>
</tbody>
</table>

## ANNEXE 2 - PLAN D’ADRESSAGE IP des serveurs (suite)

<table style="width:100%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 9%" />
<col style="width: 9%" />
<col style="width: 11%" />
<col style="width: 10%" />
<col style="width: 10%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 2%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th></th>
<th></th>
<th></th>
<th></th>
<th></th>
<th></th>
<th></th>
<th colspan="2"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td colspan="2"></td>
</tr>
<tr class="even">
<td><strong>Nom</strong></td>
<td><strong>VM sur la ferme</strong></td>
<td><strong>VLAN (étiquette réseau)</strong></td>
<td><strong>Adresse IP et masque CIDR</strong></td>
<td><strong>Masque (notation décimale</strong></td>
<td><strong>Passerelle</strong></td>
<td><strong>login</strong></td>
<td><strong>password</strong></td>
<td><strong>OS</strong></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

### Serveurs publiques (Internet simulé) et serveurs hébergés dans DMZ

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 9%" />
<col style="width: 10%" />
<col style="width: 12%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 12%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Nom</strong></th>
<th><strong>VM sur la ferme</strong></th>
<th><strong>VLAN (étiquette réseau)</strong></th>
<th><strong>Adresse IP et masque CIDR</strong></th>
<th><strong>Masque (notation décimale</strong></th>
<th><strong>Passerelle</strong></th>
<th><strong>login</strong></th>
<th><strong>password</strong></th>
<th><strong>OS</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Registar DNS</td>
<td> </td>
<td>200</td>
<td>121.283.90.205 / 29</td>
<td>255.255.255.248</td>
<td>121.283.90.206</td>
<td> </td>
<td> </td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td> </td>
<td></td>
</tr>
</tbody>
</table>

## ANNEXE 3 - Plan de brassage. 

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 11%" />
<col style="width: 16%" />
<col style="width: 1%" />
<col style="width: 17%" />
<col style="width: 17%" />
<col style="width: 17%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>SW1 2960-24</strong></td>
<td><strong>Ports</strong></td>
<td><strong>VLAN</strong></td>
<td></td>
<td><strong><br />
SW1 2960-24</strong></td>
<td><strong>Ports</strong></td>
<td><strong>VLAN</strong></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/1</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/1</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/2</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/2</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/3</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/3</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/4</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/4</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/5</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/5</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/6</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/6</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/7</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/7</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/8</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/8</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/9</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/9</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/10</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/10</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/11</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/11</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/12</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/12</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/13</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/13</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/14</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/14</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/15</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/15</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/16</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/16</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/17</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/17</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/18</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/18</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/19</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/19</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/20</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/20</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/21</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/21</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/22</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/22</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Fa0/23</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/23</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Fa0/23</td>
<td></td>
<td></td>
<td></td>
<td>Fa0/23</td>
<td></td>
</tr>
<tr class="even">
<td></td>
<td>Gi0/1</td>
<td></td>
<td></td>
<td></td>
<td>Gi0/1</td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td>Gi0/2</td>
<td></td>
<td></td>
<td><strong><br />
</strong></td>
<td>Gi0/2</td>
<td></td>
</tr>
</tbody>
</table>

## ANNEXE 4 - Identifiants & mots de passe 

**Tables des noms DNS**

## Annexe 5 - Infrastructure Publique simulée dans le labo du lycée Fulbert

![](medias/infrastructure/image4.emf)

##  Annexe 5 bis

### Adressage IP publique des sites

<table style="width:100%;">
<colgroup>
<col style="width: 8%" />
<col style="width: 13%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>VLAN ID</strong></th>
<th><strong>Routeur FAI</strong></th>
<th><strong>interface publique</strong></th>
<th><strong>Chartres</strong></th>
<th><strong>Orléans</strong></th>
<th><strong>Tours</strong></th>
<th><strong>Chateauroux</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="3">100</td>
<td rowspan="3">R1</td>
<td>adresse IP</td>
<td>221.87.1<strong>28</strong>.2 /30</td>
<td>221.87.1<strong>45</strong>.2 /30</td>
<td>221.87.1<strong>37</strong>.2 /30</td>
<td>221.87.1<strong>36</strong>.2 /30</td>
</tr>
<tr class="even">
<td>masque</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
</tr>
<tr class="odd">
<td>passerelle</td>
<td>221.87.128.1</td>
<td>221.87.145.1</td>
<td>221.87.137.1</td>
<td>221.87.136.1</td>
</tr>
<tr class="even">
<td rowspan="3">200</td>
<td rowspan="3">R2</td>
<td>adresse IP</td>
<td>183.44.<strong>28</strong>.1 /30</td>
<td>183.44.<strong>45</strong>.1 /30</td>
<td>183.44.<strong>37</strong>.1 /30</td>
<td>183.44.<strong>36</strong>.1 /30</td>
</tr>
<tr class="odd">
<td>masque</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
<td>255.255.255.252</td>
</tr>
<tr class="even">
<td>passerelle</td>
<td>183.44.28.2</td>
<td>183.44.45.2</td>
<td>183.44.37.2</td>
<td>183.44.36.2</td>
</tr>
</tbody>
</table>

### Routeurs simulant internet dans l’infrastructure du lycée Fulbert

<table style="width:100%;">
<colgroup>
<col style="width: 8%" />
<col style="width: 13%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
<col style="width: 15%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>VLAN ID</strong></th>
<th><strong>Routeur internet</strong></th>
<th><strong>interface</strong></th>
<th><strong>IP</strong></th>
<th><strong>Masque</strong></th>
<th><strong>Réseau</strong></th>
<th><strong>Broadcast</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td rowspan="6">100</td>
<td rowspan="6">R1</td>
<td>chartres</td>
<td>221.87.<strong>128</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>221.87.128.0</td>
<td>221.87.128.3</td>
</tr>
<tr class="even">
<td>orléans</td>
<td>221.87.<strong>145</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>221.87.145.0</td>
<td>221.87.145.3</td>
</tr>
<tr class="odd">
<td>tours</td>
<td>221.87.<strong>137</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>221.87.137.0</td>
<td>221.87.137.3</td>
</tr>
<tr class="even">
<td>chateauroux</td>
<td>221.87.<strong>136</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>221.87.136.0</td>
<td>221.87.136.3</td>
</tr>
<tr class="odd">
<td>reste du monde</td>
<td>121.183.90.<strong>201</strong> / 29</td>
<td>255.255.255.248</td>
<td>121.183.90.200</td>
<td>121.183.90.207</td>
</tr>
<tr class="even">
<td>PASSERELLE</td>
<td colspan="4">121.183.90.<strong>206</strong></td>
</tr>
<tr class="odd">
<td rowspan="9">200</td>
<td rowspan="6">R2</td>
<td>chartres</td>
<td>183.44.<strong>28</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>183.44.28.0</td>
<td>183.44.28.3</td>
</tr>
<tr class="even">
<td>orléans</td>
<td>183.44.<strong>45</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>183.44.45.0</td>
<td>183.44.45.3</td>
</tr>
<tr class="odd">
<td>tours</td>
<td>183.44.<strong>37</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>183.44.37.0</td>
<td>183.44.37.3</td>
</tr>
<tr class="even">
<td>chateauroux</td>
<td>183.44.<strong>36</strong>.1 /30</td>
<td>255.255.255.252</td>
<td>183.44.36.0</td>
<td>183.44.36.3</td>
</tr>
<tr class="odd">
<td>reste du monde</td>
<td>121.183.90.<strong>202</strong> / 29</td>
<td>255.255.255.248</td>
<td>121.183.90.200</td>
<td>121.183.90.207</td>
</tr>
<tr class="even">
<td>PASSERELLE</td>
<td colspan="4">121.183.90.<strong>206</strong></td>
</tr>
<tr class="odd">
<td rowspan="3">RSportFulbert</td>
<td>Vers Internet simulé</td>
<td>121.183.90.206 / 29</td>
<td>255.255.255.248</td>
<td>121.183.90.200</td>
<td>121.183.90.207</td>
</tr>
<tr class="even">
<td>Vers Fulbert</td>
<td>10.200.255.1 /16</td>
<td>255.255.0.0</td>
<td>10.200.0.0</td>
<td>10.200.255.255</td>
</tr>
<tr class="odd">
<td>PASSERELLE</td>
<td>10.200.255.254</td>
<td colspan="3">Commentaire NAT réseau 128.183.90.200 --&gt;
10.200.255.1</td>
</tr>
</tbody>
</table>

## Annexe 6

**Les équipements de réseau**

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 72%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>DLINK 3200 AP</strong></th>
<th><blockquote>
<p><img src="medias/infrastructure/image5.png"
style="width:2.73958in;height:1.54167in"
alt="1%20DWL3200APB281600x1600" /></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Désignation</strong></td>
<td><blockquote>
<p><strong>Point d’Accès WIFI</strong></p>
</blockquote></td>
</tr>
<tr class="even">
<td><strong>Caractéristiques matériels</strong></td>
<td><ul>
<li><p>Boîtier solide en métal certifié Plenum</p></li>
<li><p>Technologie Power over Ethernet (PoE) 802.3af intégrée</p></li>
<li><p>Deux antennes à gain élevé amovibles</p></li>
<li><p>Base PoE (Power over Ethernet) fournie</p></li>
<li><p>Supports de verrouillage inclus</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Mode de fonctionnement</strong></td>
<td><ul>
<li><p>AP</p></li>
<li><p>WDS</p></li>
<li><p>AP + WDS</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Connectivité haute performance</strong></td>
<td><ul>
<li><p>Débits sans fil conformes à la norme 802.11g</p></li>
<li><p>Débits de transfert de données sans fil pouvant atteindre 54
Mbps*</p></li>
<li><p>Débit sans fil de 108 Mbps avec la technologie 108G
D-Link*</p></li>
<li><p>*Le débit maximal du signal sans fil est basé sur les
spécifications de la norme IEEE 802.11g. Dans la réalité, sa valeur
pourra varier. En effet, les conditions réseau et les facteurs
environnementaux peuvent restreindre le débit réel des données.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Sécurité</strong></td>
<td><ul>
<li><p>Chiffrement des données WEP 64/128/152 bits</p></li>
<li><p>WPA Personal/WPA Enterprise</p></li>
<li><p>WPA2 Personal/WPA2 Enterprise</p></li>
<li><p>Authentification utilisateur 802.1x</p></li>
<li><p>AES</p></li>
<li><p>SSID multiples 802.1Q/segmentation réseau</p></li>
<li><p>Filtrage des adresses MAC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Administration</strong></td>
<td><ul>
<li><p>Logiciel AP Manager</p></li>
<li><p>Navigateur Web (HTTP)</p></li>
<li><p>Telnet</p></li>
<li><p>SNMP v.3</p></li>
</ul></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 36%" />
<col style="width: 63%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Routeur Cisco</strong></th>
<th><blockquote>
<p><img src="medias/infrastructure/image6.png"
style="width:3.97917in;height:1.86458in" /></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2"><h3 id="model">Model</h3>
<p><strong>Brand</strong> CISCO <strong>Series</strong> 1900
<strong>Model</strong> CISCO1921/K9</p>
<h3 id="spec">SPEC</h3>
<p><strong>Speed</strong> 10/100/1000Mbps LAN <strong>Ports</strong> 2 x
10/100/1000Mbps</p>
<p><strong>VPN</strong> IPSec, PPTP, L2TP</p>
<h3 id="features">Features</h3>
<blockquote>
<p><strong>Interfaces/Ports:</strong><br />
2 x RJ-45 10/100/1000Base-T Network LAN<br />
1 x RJ-45 Auxiliary Management<br />
1 x RJ-45 Console Management<br />
1 x Type A USB 2.0 USB<br />
1 x Type B USB Management</p>
<p><strong>I/O Expansions:</strong><br />
Number of Expansion Slots: 2<br />
Expansion Slots: (2 Total) HWIC</p>
<p><strong>Management:</strong><br />
SNMP RMON Syslog NetFlow TR-069 IEEE 802.1p QoS<br />
IEEE 802.1q VLAN Web Based Management Cisco Configuration
Professional<br />
<br />
CiscoWorks LMS CiscoWorks NCM Cisco Security Manager<br />
Cisco Unified Provisioning Manager Cisco License Manager Cisco
Configuration Engine</p>
<p><strong>Memory:</strong><br />
<br />
Standard Memory: 512 MB<br />
Maximum Memory: 512 MB<br />
Memory Technology: DRAM<br />
Flash Memory: 256 MB<br />
The Cisco 1921 builds on the best-in-class offering of the Cisco 1841
Integrated Services Routers.<br />
All Cisco 1900 Series Integrated Services Routers offer embedded
hardware encryption acceleration, optional firewall, intrusion
prevention, and advanced security services.<br />
In addition, the platforms support the industry's widest range of wired
and wireless connectivity options such as Serial, T1/E1, xDSL, Gigabit
Ethernet, and third-generation (3G) wireless.</p>
</blockquote></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 75%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Switch CISCO 2960<br />
- 48 ports</strong></th>
<th><blockquote>
<p><img src="medias/infrastructure/image7.jpeg"
style="width:4.9375in;height:0.91667in" alt="C2960-24TC-S" /></p>
</blockquote></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td colspan="2"><table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><table style="width:100%;">
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Description du produit</th>
<th></th>
<th>Cisco Catalyst 2960-24TC-S - commutateur - 24 ports - Géré -
Montable sur rack</th>
</tr>
</thead>
<tbody>
</tbody>
</table></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de périphérique</th>
<th></th>
<th>Commutateur - 24 ports - Géré</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de châssis</th>
<th></th>
<th>Montable sur rack 1U</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Interfaces</th>
<th></th>
<th>Fast Ethernet</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr class="header">
<th>Ports</th>
<th></th>
<th>24 x 10/100 + 2 x SFP Gigabit combiné</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Performances</th>
<th></th>
<th>Capacité de commutation : 16 Gbps ? Performances de transfert
(taille de paquet 64 octets) : 6,5 Gbps</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Taille de la table d'adresses MAC</th>
<th></th>
<th>8 000 entrées</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole de gestion à distance</th>
<th></th>
<th>SNMP 1, SNMP 2, RMON 1, RMON 2, Telnet, SNMP 3, SNMP 2c, HTTP,
HTTPS, TFTP, SSH-2</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 35%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Caractéristiques</th>
<th></th>
<th>Layer 2 switching, auto-détection par dispositif, compatible DHCP,
auto-négociation, prise en charge du réseau local (LAN) virtuel,
auto-uplink (MDI/MDI-X auto), IGMP snooping, prise en charge de Syslog,
prise en charge DiffServ, contrôle de la tempête de Broadcast, Multicast
Storm Control, Unicast Storm Control, prise en charge du protocole RSTP
(Rapid Spanning Tree Protocol), prise en charge du protocole Multiple
Spanning Tree Protocol (MSTP), assistance Dynamic Trunking Protocol
(DTP), assistance Port Aggregation Protocol (PAgP), qualité de service
(QDS), Link Aggregation Control Protocol (LACP), Port Security,
notification de l'adresse MAC</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Conformité aux normes</th>
<th></th>
<th>IEEE 802.3, IEEE 802.3u, IEEE 802.3z, IEEE 802.1D, IEEE 802.1Q, IEEE
802.3ab, IEEE 802.1p, IEEE 802.3x, IEEE 802.3ad (LACP), IEEE 802.1w,
IEEE 802.1x, IEEE 802.1s, IEEE 802.3ah, IEEE 802.1ab (LLDP)</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 35%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Alimentation</th>
<th></th>
<th>CA 120/230 V ( 50/60 Hz )</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 35%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Dimensions (LxPxH)</th>
<th></th>
<th>44.5 cm x 23.6 cm x 4.4 cm</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="even">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr class="header">
<th>Poids</th>
<th></th>
<th>3.65 kg</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
<tr class="odd">
<td><table>
<colgroup>
<col style="width: 34%" />
<col style="width: 6%" />
<col style="width: 58%" />
</colgroup>
<thead>
<tr class="header">
<th>Garantie du fabricant</th>
<th></th>
<th>Garantie limitée à vie</th>
</tr>
</thead>
<tbody>
</tbody>
</table></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>
