
# Spyware Python - Client/Serveur

## Description
Ce projet est un spyware développé en Python. Il se compose de deux parties : un serveur et un client. Le client capture les frappes du clavier ainsi que les informations du presse-papiers et envoie régulièrement ces données au serveur via une connexion réseau. Le serveur reçoit les données, les enregistre sous forme de fichiers journaux et organise ces fichiers par client et par date.

## Fonctionnalités
### Serveur :
- Écoute les connexions entrantes des clients.
- Reçoit les données des frappes de clavier envoyées par les clients.
- Enregistre les données dans un dossier dédié à chaque client, organisé par date et heure.
- Permet de visualiser les fichiers reçus ou de les lire directement.

### Client :
- Capture les frappes de clavier à l'aide de `pynput`.
- Sauvegarde les informations du presse-papiers à chaque intervalle défini.
- Envoie les données capturées au serveur à intervalles réguliers.
- Nettoie les fichiers locaux après envoi.

## Installation
### Pré-requis
- Python 3
- Bibliothèques Python :
  - `socket`
  - `pynput`
  - `clipboard`
  - `argparse`
  - `os`

### Cloner le projet
```bash
git clone <lien_github>
cd spyware_python
```

### Installation des dépendances
Assurez-vous d'avoir les bibliothèques nécessaires installées :
```bash
pip install pynput clipboard
```

## Utilisation
### Serveur
Lancez le serveur avec l'option `-l` suivie du port d'écoute souhaité :
```bash
python3 serveur.py -l 4444
```
Autres options :
- `-r <folder/file.txt>` : Lire le contenu d'un fichier reçu.
- `-s` : Afficher la liste des fichiers reçus sur le serveur.

### Client
Modifiez les variables `ip_server` et `port` dans le fichier `client.py` pour correspondre à l'adresse IP et au port du serveur, puis lancez le client :
```bash
python3 client.py
```
Le client enverra automatiquement les données capturées au serveur toutes les 60 secondes (modifiable dans `time_interval`).

## Structure du projet
```
spyware_python/
│
├── server.py      # Serveur qui reçoit et enregistre les données des clients
├── client.py      # Client qui capture et envoie les frappes au serveur
├── README.md      # Fichier d'information
```

## Sécurité
**Attention :** Ce projet est à but éducatif uniquement. Son utilisation à des fins malveillantes est strictement interdite. Assurez-vous d'obtenir la permission avant d'installer ce type de programme sur une machine.

## Auteur
Projet développé par **Mohamed SAIDI** et **Ruben**.

## Licence
Ce projet est sous licence MIT.
