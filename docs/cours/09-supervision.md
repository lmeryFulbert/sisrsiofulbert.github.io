# 09 - Supervision

## Introduction à la Supervision

A. Définition de la supervision

### II. A. Définition de la Supervision

La supervision désigne l'ensemble des processus, outils et méthodes utilisés pour surveiller et contrôler les éléments d'un système informatique ou d'un réseau. Son objectif principal est d'assurer la disponibilité, la performance et la fiabilité des composants du système, tout en anticipant et en résolvant les éventuels problèmes.

#### 1. Objectifs de la Supervision

La supervision vise plusieurs objectifs essentiels dans la gestion d'un réseau ou d'un système informatique :

- **Disponibilité :** S'assurer que les services et les ressources sont accessibles lorsque nécessaire, minimisant ainsi les temps d'indisponibilité.

- **Performance :** Mesurer et optimiser les performances des différents composants afin de garantir une utilisation efficiente des ressources.

- **Fiabilité :** Prévenir les pannes et les dysfonctionnements, assurant ainsi une exploitation continue et fiable du système.

- **Sécurité :** Identifier et réagir aux menaces potentielles, garantissant la sécurité des données et des communications.

#### 2. Composants sous Surveillance

La supervision englobe la surveillance de divers composants, parmi lesquels :

- **Matériel (Hardware) :** Suivi des performances des serveurs, routeurs, commutateurs, et autres équipements.

- **Logiciel (Software) :** Surveillance des applications, des bases de données, des systèmes d'exploitation pour détecter les erreurs et les défaillances.

- **Réseau :** Contrôle du trafic, de la bande passante, de la latence, et gestion des éléments réseau pour garantir un flux de données optimal.

- **Sécurité :** Détection des attaques, gestion des vulnérabilités, et contrôle des accès pour assurer la sécurité du système.

#### 3. Méthodes de Supervision

La supervision peut s'effectuer de manière proactive (supervision active) ou réactive (supervision passive). Les méthodes incluent la collecte de données, l'analyse des journaux, l'utilisation d'alertes, et la génération de rapports.

La mise en place d'une stratégie de supervision efficace permet non seulement d'améliorer la réactivité face aux incidents, mais également d'anticiper les problèmes potentiels, réduisant ainsi les temps d'arrêt et les impacts sur les utilisateurs.

## Protocole SNMP (Simple Network Management Protocol)

### Présentation générale de SNMP

Le **Simple Network Management Protocol (SNMP)** est un protocole **(UDP 161)** standard de gestion de réseau largement utilisé pour la supervision et la gestion des équipements réseau et des systèmes informatiques. Conçu pour être simple et efficace, SNMP permet la collecte d'informations et le contrôle d'appareils réseau, facilitant ainsi la surveillance proactive et la résolution des problèmes.

1. Architecture SNMP

**Agents SNMP :** Les agents SNMP sont des logiciels intégrés dans les équipements réseau (comme les routeurs, les commutateurs, les serveurs) chargés de collecter des informations sur les performances et l'état des dispositifs. Ces agents répondent aux requêtes SNMP et génèrent des "traps" en cas d'événements particuliers. Ils écoutent sur le port UDP 161 (ils s'agit donc d'un processus serveur).

**Gestionnaire SNMP :** Le gestionnaire SNMP est une application logicielle qui effectue des requêtes aux agents SNMP pour obtenir des informations sur les appareils supervisés. Il peut également envoyer des commandes pour configurer ou contrôler les dispositifs.
On le considère au niveau des flux comme le client.
Toutefois comme il centralise les réponses SNMP, on le considère comme le serveur de supervision.


2. Fonctionnement de SNMP

SNMP fonctionne sur la base d'un échange de messages entre le gestionnaire et les agents. Les messages SNMP, appelés Protocol Data Units (PDU), sont utilisés pour lire ou écrire des informations sur les appareils.

Les trois versions principales de SNMP sont :

**SNMPv1 :** La première version, offrant des fonctionnalités de base pour la surveillance. Elle utilise des communautés pour l'authentification.

**SNMPv2 :** Une version améliorée, introduisant des fonctionnalités telles que la capacité de définir des groupes de variables et des améliorations dans la gestion des erreurs.

**SNMPv3 :** La version la plus récente, intégrant des fonctionnalités de sécurité robustes, y compris l'authentification et le chiffrement, assurant ainsi une communication sécurisée entre les gestionnaires et les agents.

3. Avantages et Limitations de SNMP

**Avantages :**

- Universalité : SNMP est largement adopté, offrant une compatibilité étendue avec une variété d'équipements réseau et de systèmes.

- Simplicité : La simplicité de la conception de SNMP facilite son déploiement et son utilisation.

- Extensibilité : Il est possible d'étendre SNMP pour prendre en charge de nouveaux types d'équipements ou de variables grâce aux MIBs (Management Information Base).

**Limitations :**

Sécurité : Les versions plus anciennes de SNMP (v1 et v2) manquent de fonctionnalités de sécurité robustes. Cependant, SNMPv3 a remédié à ces lacunes en introduisant des mécanismes de sécurité plus avancés.

Complexité des MIBs : Les MIBs peuvent parfois être complexes, surtout dans les réseaux complexes, nécessitant une compréhension approfondie pour une configuration efficace

B. Structure de la MIB

La **MIB (Management Information Base)** est une structure hiérarchique qui organise les informations accessibles via SNMP. Elle est composée d'objets qui représentent des éléments spécifiques des équipements surveillés. Chaque objet a un identifiant unique appelé OID (Object Identifier). La MIB définit les variables que les gestionnaires peuvent interroger et modifier.

La MIB est organisée en différents groupes, chacun regroupant des objets liés à une fonction ou une caractéristique spécifique. Par exemple, la MIB-II est une partie standard de la MIB qui inclut des informations générales sur le système, l'interface réseau, et d'autres aspects communs.

Voici un exemple simplifié d'une partie de la MIB-II, qui est une MIB standard souvent utilisée pour superviser des appareils réseau. La MIB-II comprend plusieurs groupes, et nous allons explorer le groupe "System" pour illustrer quelques-uns de ses objets.

Groupe System de la MIB-II :

    sysDescr (1.3.6.1.2.1.1.1):
        Type : Chaîne de caractères
        Description : Une description du système, généralement fournie par le fabricant.

    sysObjectID (1.3.6.1.2.1.1.2):
        Type : Object Identifier
        Description : L'OID identifiant le type de système, permettant de déterminer le type d'équipement.

    sysUpTime (1.3.6.1.2.1.1.3):
        Type : Temps depuis le dernier redémarrage (en centièmes de secondes)
        Description : Temps écoulé depuis le dernier redémarrage du système.

    sysContact (1.3.6.1.2.1.1.4):
        Type : Chaîne de caractères
        Description : Information de contact pour l'administrateur du système.

    sysName (1.3.6.1.2.1.1.5):
        Type : Chaîne de caractères
        Description : Le nom de l'équipement.

    sysLocation (1.3.6.1.2.1.1.6):
        Type : Chaîne de caractères
        Description : L'emplacement physique du système.

    sysServices (1.3.6.1.2.1.1.7):
        Type : Entier
        Description : Indique quels services sont disponibles sur le système.

Chaque objet de la MIB est accessible via un identifiant unique (OID), et le gestionnaire SNMP peut interroger ces objets pour obtenir des informations sur le système. Par exemple, en interrogeant sysDescr, le gestionnaire pourrait recevoir une réponse avec une description détaillée du système.

#### Interaction SNMP

L'interaction entre le gestionnaire et l'agent s'effectue à travers des PDUs (Protocol Data Units) On peux utiliser snmpwalk sous linux pour tester le protocole snmp:

**Get Request :** Le gestionnaire envoie une requête demandant la valeur d'un objet spécifique dans la MIB de l'agent.

**Get Response :** L'agent répond avec la valeur de l'objet demandé.

**Set Request :** Le gestionnaire envoie une requête pour modifier la valeur d'un objet dans la MIB de l'agent.

**Trap :** L'agent peut également envoyer un "trap" (UDP 162) au gestionnaire pour signaler un événement, sans attendre une requête spécifique

IV. Supervision Active et Passive

A. Supervision Active

### IV. A. Supervision Active

La supervision active, également appelée monitoring actif, désigne une approche proactive dans laquelle le gestionnaire réseau génère délibérément des requêtes pour obtenir des informations sur les dispositifs surveillés. Cette méthode permet de mesurer en temps réel la performance, la disponibilité et d'autres paramètres clés des composants réseau. Voici une exploration plus approfondie de la supervision active :

#### 1. Méthodes de Supervision Active

La supervision active implique l'utilisation de différentes méthodes pour interroger les équipements réseau et collecter des données. Parmi les méthodes couramment utilisées, on trouve :

- **Ping (ICMP Echo) :** Envoi de paquets ICMP Echo Request aux appareils réseau pour vérifier leur disponibilité et mesurer les temps de réponse.

- **SNMP Polling :** Interrogation régulière des agents SNMP pour récupérer des informations sur les performances, la charge CPU, la mémoire, et d'autres paramètres.

- **Tests de bande passante :** Envoi de flux de données pour évaluer la bande passante disponible et détecter les goulots d'étranglement.

- **Test de connectivité :** Vérification de la connectivité entre les différents nœuds du réseau pour identifier les éventuels problèmes de routage.

#### 2. Avantages de la Supervision Active

- **Réactivité :** La supervision active permet une détection rapide des problèmes. Les gestionnaires peuvent recevoir des alertes immédiates lorsqu'une défaillance ou un problème de performance est détecté.

- **Collecte de données en temps réel :** Les mesures sont effectuées en temps réel, offrant une vue instantanée de l'état du réseau.

- **Analyse proactive :** L'analyse des tendances à partir des données collectées permet d'anticiper les problèmes potentiels et de prendre des mesures préventives.

- **Contrôle ciblé :** Les gestionnaires peuvent cibler spécifiquement des dispositifs, des interfaces ou des services pour une supervision plus précise.

#### 3. Outils de Supervision Active

Plusieurs outils de supervision active sont disponibles pour mettre en œuvre cette approche. Certains des outils les plus couramment utilisés incluent :

- **Nagios :** Utilisé pour surveiller la disponibilité, les ressources système, et les services.

- **PRTG :** Permet la surveillance en temps réel de la bande passante, des serveurs, des applications, etc.

- **Zabbix :** Offre une supervision complète avec la possibilité de configurer des déclencheurs et des alertes.

- **Wireshark :** Un outil d'analyse réseau qui peut être utilisé pour examiner le trafic en temps réel et diagnostiquer des problèmes.

#### 4. Exemple de Configuration

Un exemple simple de configuration de supervision active pourrait être la mise en place d'une sonde SNMP pour interroger périodiquement les dispositifs réseau et collecter des données sur la charge CPU, l'utilisation de la mémoire, et le trafic réseau.

```yaml
Device:
  - Name: RouteurA
    IP: 192.168.1.1
    SNMP:
      Community: public
      Metrics:
        - CPUUsage
        - MemoryUsage
        - NetworkTraffic
  - Name: SwitchB
    IP: 192.168.1.2
    SNMP:
      Community: public
      Metrics:
        - PortStatus
        - VLANStatus
```

##Exemple avec Nagios

IV. A. Supervision Active avec Nagios

Nagios est un puissant outil de supervision open source qui permet la surveillance active des ressources réseau. Voici un exemple simplifié de configuration pour superviser un routeur et un commutateur avec Nagios :

1. Configuration des Hôtes dans Nagios

La configuration des hôtes dans Nagios se fait généralement dans le fichier hosts.cfg. Voici un exemple :


```bash
# Fichier : /etc/nagios/objects/hosts.cfg

define host {
    use                 generic-host
    host_name           RouteurA
    alias               Routeur A - Description
    address             192.168.1.1
}

define host {
    use                 generic-host
    host_name           SwitchB
    alias               Switch B - Description
    address             192.168.1.2
}
```

Dans cet exemple, deux hôtes, "RouteurA" et "SwitchB", sont définis avec leurs adresses IP respectives.

2. Configuration des Services dans Nagios

La configuration des services spécifiques à surveiller se fait dans le fichier services.cfg. Voici un exemple :


```bash
# Fichier : /etc/nagios/objects/services.cfg

define service {
    use                 generic-service
    host_name           RouteurA
    service_description CPU Usage
    check_command       check_snmp!-C public -o hrProcessorLoad.1 -w 80 -c 90
}

define service {
    use                 generic-service
    host_name           RouteurA
    service_description Memory Usage
    check_command       check_snmp!-C public -o hrStorageUsed.1 -w 80% -c 90%
}

define service {
    use                 generic-service
    host_name           SwitchB
    service_description Port Status
    check_command       check_snmp!-C public -o ifOperStatus.1
}

define service {
    use                 generic-service
    host_name           SwitchB
    service_description VLAN Status
    check_command       check_snmp!-C public -o dot1qVlanStatus.1
}
```

Dans cet exemple, des services spécifiques tels que "CPU Usage" et "Memory Usage" pour le routeur, ainsi que "Port Status" et "VLAN Status" pour le commutateur, sont définis. Les commandes check_snmp permettent d'interroger les dispositifs via SNMP.

3. Commandes personnalisées

Nagios utilise des commandes pour effectuer des vérifications. Voici comment définir une commande pour interroger un dispositif via SNMP :

```bash
# Fichier : /etc/nagios/objects/commands.cfg

define command {
    command_name    check_snmp
    command_line    $USER1$/check_snmp -H $HOSTADDRESS$ $ARG1$
}
```

4. Résultat

Une fois que Nagios est configuré avec ces informations, il surveillera activement les services spécifiés et générera des alertes en cas de problème. Les seuils de déclenchement d'alertes (warning et critical) peuvent être ajustés en fonction des besoins spécifiques.

## Supervision Passive

La supervision passive, également connue sous le nom de monitoring passif, est une approche où les dispositifs réseau envoient activement des informations à un serveur de supervision sans qu'il ait à les interroger. Cela est généralement réalisé à l'aide de Traps SNMP. La supervision passive offre une visibilité en temps réel des événements sur le réseau sans avoir à effectuer des requêtes constantes. Voici un aperçu détaillé de la supervision passive :

### 1. Traps SNMP

- **Définition :** Un Trap SNMP est une notification instantanée qu'un agent SNMP envoie à un gestionnaire SNMP lorsqu'un événement prédéfini se produit. Les Traps peuvent signaler diverses conditions, telles que des pannes, des changements d'état, ou d'autres événements spécifiques.

- **Fonctionnement :** Lorsqu'un événement survient, l'agent SNMP génère un Trap et l'envoie au gestionnaire SNMP. Le gestionnaire réagit en conséquence, pouvant déclencher des alertes, des scripts, ou d'autres actions définies.

#### 2. Avantages de la Supervision Passive

- **Réactivité accrue :** Les Traps permettent une détection instantanée des événements, fournissant une réactivité accrue aux changements dans le réseau.

- **Réduction du trafic réseau :** Par rapport à la supervision active, la supervision passive génère moins de trafic réseau car les informations sont transmises uniquement lorsque des événements surviennent.

- **Visibilité en temps réel :** La supervision passive offre une visibilité immédiate sur les événements critiques, ce qui peut être crucial pour la résolution rapide des problèmes.

#### 3. Configuration des Traps SNMP

- **Au niveau de l'Agent SNMP :** La configuration des Traps SNMP se fait au niveau de l'agent SNMP sur chaque dispositif. Les événements spécifiques qui déclenchent l'envoi d'un Trap sont définis dans la configuration de l'agent.

- **Au niveau du Gestionnaire SNMP :** Le gestionnaire SNMP doit être configuré pour recevoir et interpréter les Traps. Cela implique la définition des actions à entreprendre lorsqu'un Trap spécifique est reçu.

#### 4. Exemple de Configuration

- **Configuration de l'Agent SNMP :** 

  Dans la configuration de l'agent sur un routeur, vous pourriez spécifier qu'un Trap doit être généré en cas de changement d'état d'une interface réseau.

  ```bash
  snmp-server enable traps
  snmp-server host 192.168.1.100 public SNMP-TRAP
  ```

  Dans cet exemple, le routeur envoie des Traps à l'adresse IP 192.168.1.100 avec la communauté SNMP "public" lorsqu'un événement défini survient.

- **Configuration du Gestionnaire SNMP :**

  Dans le gestionnaire SNMP (par exemple, avec un outil comme Nagios ou Centreon), vous devez configurer la réception des Traps SNMP et définir des règles pour gérer ces événements.

#### 5. Outils de Supervision Passive

Plusieurs outils de supervision passifs sont disponibles, certains construits au-dessus de protocoles comme SNMP, et d'autres utilisant des mécanismes spécifiques aux fournisseurs. Certains exemples incluent :

- **Nagios :** Peut être configuré pour recevoir et traiter des Traps SNMP.

- **Centreon :** Offre la gestion des Traps SNMP et une interface graphique conviviale pour définir des actions en réponse à des événements.

- **Zabbix :** Supporte la réception et le traitement des Traps SNMP.

La supervision passive, avec l'utilisation judicieuse des Traps SNMP, offre une approche puissante pour la détection et la gestion rapides des événements dans un réseau, permettant ainsi une résolution proactive des problèmes.