# Infrastructure

## Objectifs à atteindre

L'objectif avant les vacances de la Toussaint est de mettre en place l'ensemble de l'architecture physique et logique pour faciliter le travail et la mise en œuvre de divers services. Notre infrastructure repose sur un réseau local (LAN) composé de plusieurs VLAN, notamment des VLAN utilisateur, ainsi qu'au moins un VLAN dédié à l'hébergement des serveurs.

Le routage entre les VLAN sera assuré par un commutateur de niveau 3 positionné au cœur du réseau. Cela garantira une communication efficace entre les différents segments du réseau.

Dans le contexte de services accessibles publiquement, nous devons les isoler dans une zone démilitarisée (DMZ) pour renforcer la sécurité. Pour ce faire, deux groupes de travail collaboreront avec deux pare-feux autonomes, à savoir un pare-feu physique Stormshield et un pare-feu virtuel pfsense déployé en tant que machine virtuelle.

De plus, deux autres groupes travailleront exclusivement avec un seul pare-feu physique Stormshield, ce qui permettra de cloisonner leurs activités et de garantir une sécurité adéquate.

Pour héberger les données nécessaires aux serveurs de la DMZ publique, nous mettrons en place une DMZ privée, assurant ainsi une isolation appropriée des informations sensibles.

Un point essentiel de notre conception est le contrôle de tous les flux par les pare-feux. Cela garantira une sécurité renforcée en examinant et en autorisant uniquement les communications nécessaires.

Concernant l'architecture DNS, nous adopterons les bonnes pratiques en séparant les rôles de résolveur et de serveur DNS ayant autorité. Cette approche optimise la gestion des requêtes DNS en distinguant clairement les responsabilités de chaque composant, assurant ainsi une mise en œuvre robuste et sécurisée du service DNS.

