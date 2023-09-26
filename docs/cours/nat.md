# NAT Dynamique (Masquerade) version Cisco

Le NAT dynamique est une technique utilisée pour permettre à plusieurs dispositifs d'une réseau local (IP inside) de partager une seule adresse IP publique (IP outside) pour accéder à Internet ou d'autres réseaux externes.

**Éléments du NAT dynamique :**

1. **IP Inside (Adresse privée)** : L'adresse IP inside est l'adresse IP attribuée aux dispositifs du réseau local. Dans votre exemple, l'adresse IP inside est en 172.28.x.254/24. Ces adresses IP sont généralement privées et ne sont pas routables sur Internet.

2. **IP Outside (Adresse publique)** : L'adresse IP outside est l'adresse IP attribuée au routeur ou au pare-feu qui relie le réseau local au réseau externe, généralement Internet. Dans votre exemple, l'adresse IP outside est en 183.44.x.1/30. Cette adresse IP est publique et utilisée pour communiquer avec des ressources sur Internet.

3. **Table de traduction (Translation Table)** : La table de traduction est une table gérée par le routeur ou le pare-feu NAT qui associe les adresses IP inside aux adresses IP outside. Chaque fois qu'un dispositif du réseau local initie une connexion vers l'extérieur, une entrée est créée dans la table de traduction pour suivre la correspondance entre l'adresse IP inside et l'adresse IP outside.

4. **Port Mapping (Port Mapping)** : Dans le cas du NAT dynamique, les numéros de port sont également modifiés. Cela permet à plusieurs dispositifs à l'intérieur du réseau local d'utiliser la même adresse IP publique en attribuant un numéro de port unique à chaque connexion. Ainsi, le routeur peut rediriger le trafic vers le dispositif approprié en fonction du numéro de port.

**Configuration du NAT dynamique avec Cisco :**

Voici un exemple de configuration du NAT dynamique avec Cisco :

```bash
interface GigabitEthernet0/0
 ip address 183.44.x.1 255.255.255.252
 ip nat outside

interface GigabitEthernet0/1
 ip address 172.28.x.254 255.255.255.0
 ip nat inside

ip nat inside source list 1 interface GigabitEthernet0/0 overload

access-list 1 permit 172.28.x.0 0.0.0.255
```

Explications :

- La commande `ip nat outside` est appliquée à l'interface connectée à l'extérieur (GigabitEthernet0/0), tandis que `ip nat inside` est appliqué à l'interface connectée au réseau local (GigabitEthernet0/1).

- La commande `ip nat inside source list 1 interface GigabitEthernet0/0 overload` définit la règle de translation NAT dynamique. Elle indique que toutes les adresses IP du réseau local (définies dans l'access-list 1) seront traduites en utilisant l'adresse IP publique de l'interface GigabitEthernet0/0, avec la surcharge (overload) pour gérer plusieurs connexions simultanées en utilisant le mappage de ports.

- L'access-list 1 spécifie les adresses IP à l'intérieur du réseau local qui sont autorisées à être traduites.

Ainsi, avec cette configuration, les dispositifs du réseau local avec des adresses IP en 172.28.x.x pourront accéder à Internet en partageant l'adresse IP publique 183.44.x.1 grâce au NAT dynamique. Chaque connexion sortante se verra attribuer un numéro de port unique pour permettre la correspondance correcte entre les dispositifs internes et l'adresse IP publique.

## Verification du contenu de la table de NAT

Pour vérifier la table de translation NAT et la vider sur un routeur Cisco, vous pouvez utiliser les commandes suivantes :

Pour vérifier la table de translation NAT, utilisez la commande suivante :
```bash
show ip nat translations
```

Cette commande affichera une liste des entrées dans la table de translation NAT, montrant les adresses IP inside, les ports source, les adresses IP outside, les ports de destination, ainsi que le protocole utilisé.

Pour vider la table de translation NAT, utilisez la commande suivante :
```bash
clear ip nat translation *
```

Cette commande supprimera toutes les entrées de la table de translation NAT, réinitialisant ainsi les associations entre les adresses IP inside et outside. Assurez-vous d'utiliser cette commande avec précaution, car elle peut interrompre les connexions en cours.