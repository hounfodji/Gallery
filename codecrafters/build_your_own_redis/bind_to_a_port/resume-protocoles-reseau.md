# Les protocoles réseau et le modèle TCP/IP

## Introduction

Les protocoles réseau sont des ensembles de règles permettant aux appareils de communiquer entre eux sur un réseau. Le modèle TCP/IP est un cadre qui organise ces protocoles en 4 couches.

## Les 4 couches du modèle TCP/IP

### 1. Couche de liaison (Link Layer)

- **Rôle** : Transmission des données sur un support physique.
- **Exemples** :
  - Ethernet (câbles réseau)
  - Wi-Fi (connexion sans fil)
  - Bluetooth (connexion sans fil courte portée)

### 2. Couche Internet (Internet Layer)

- **Rôle** : Routage des données entre différents réseaux.
- **Protocoles principaux** :
  - IP (Internet Protocol) : Adressage et routage
  - ICMP : Diagnostic réseau (utilisé par la commande `ping`)
  - ARP : Mappage des adresses IP aux adresses MAC

### 3. Couche de transport (Transport Layer)

- **Rôle** : Assurer le transfert fiable des données entre appareils.
- **Protocoles principaux** :
  - TCP : Transfert fiable mais plus lent (ex : chargement de pages web)
  - UDP : Transfert rapide mais moins fiable (ex : streaming vidéo en direct)

### 4. Couche application (Application Layer)

- **Rôle** : Héberger les applications et services utilisés par les utilisateurs finaux.
- **Exemples** :
  - HTTP : Navigation web
  - SMTP : Envoi d'e-mails
  - FTP : Transfert de fichiers

## Exemples concrets

1. **Navigation web** :
   - Couche application : HTTP pour la requête web
   - Couche transport : TCP pour un transfert fiable
   - Couche Internet : IP pour le routage
   - Couche liaison : Wi-Fi ou Ethernet pour la transmission physique

2. **Appel vidéo** :
   - Couche application : Protocole propriétaire (ex : Zoom)
   - Couche transport : UDP pour la rapidité
   - Couche Internet : IP pour le routage
   - Couche liaison : Wi-Fi ou 4G/5G pour la transmission

3. **Envoi d'e-mail** :
   - Couche application : SMTP pour l'envoi
   - Couche transport : TCP pour la fiabilité
   - Couche Internet : IP pour le routage
   - Couche liaison : Fibre optique ou câble pour la transmission


# Le protocole TCP (Transmission Control Protocol)

## Introduction
TCP est un protocole réseau fiable qui fonctionne au-dessus du protocole IP (Internet Protocol), moins fiable.

## Fonctionnement de base

1. **Fragmentation des données** : Les données sont divisées en "paquets".
2. **Structure d'un paquet** : 
   - En-tête (avec adresses source et destination)
   - Section de données

## Comparaison avec IP

- IP est comme un service postal :
  - Les paquets peuvent se perdre
  - L'ordre d'arrivée n'est pas garanti

## Garanties offertes par TCP

1. **Livraison fiable** : 
   - Le récepteur accuse réception de chaque paquet
   - Retransmission en cas de perte

2. **Livraison ordonnée** :
   - Chaque paquet a un numéro de séquence
   - Le récepteur réordonne les paquets si nécessaire

## Connexions TCP

- **Orienté connexion** : Nécessite l'établissement d'une connexion
- **Rôles** : Un programme serveur, un programme client
- **Communication bidirectionnelle** : Une fois la connexion établie

## Identification d'une connexion TCP

Une connexion est identifiée par 4 éléments :
1. Adresse IP de destination
2. Numéro de port de destination
3. Adresse IP source
4. Numéro de port source

Exemple : Connexion à Google.com
- IP destination : x.x.x.x (serveur Google)
- Port destination : 443 (HTTPS)
- IP source : y.y.y.y (votre ordinateur)
- Port source : 26789 (nombre aléatoire)

## Établissement de connexion (Handshake TCP)

Processus en 3 étapes :
1. **SYN** : Le client envoie une demande de synchronisation
2. **SYN-ACK** : Le serveur répond et accuse réception
3. **ACK** : Le client confirme, la connexion est établie