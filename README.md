# VPNCegepLinux
En premier lieu, je tiens à dire que ma méthode a seulement été testé sur Arch Linux pour l'instant alors certaines particularités peuvent s'appliquer à d'autres distributions. 

Dans tous les cas, si vous avez un problème avec quoi que ce soit, contactez-moi sur mon Teams de l'école et je pourrai essayer de vous aider. William Boulanger (1987690)

## Installation

Je ne crois pas avoir à rien expliquer ici, car si vous utilisez Linux, vous savez déjà installer un package. Tout de même...

Arch Linux :
```
sudo pacman -S strongswan
```
Debian :
```
sudo apt install strongswan
```
Si vous utilisez une autre distribution, référez-vous à la documentation officielle : https://docs.strongswan.org/docs/5.9/install/install.html

## Configuration
**1. Copier les fichiers se situant dans le dossier etc de ce repository dans /etc**

**2. Ouvrir les deux fichiers dans un éditeur de texte et remplacer tou ce qui est entre trois accolades par vos informations appropriées**

Par exemple, {{{ton matricule du cégep}}} deviendra `1234567` si cela est votre matricule du cégep.

En ce qui concerne `{{{ton subnet local}}}`, l'information peut être trouvée à l'aide des commandes `ipconfig` ou `ip addr show`.

Il suffit de repérer le NIC utilisé pour se connecter à internet et de noter son adresse IP. Par exemple, si l'adresse IP utilisé est 10.0.0.160/24, il fautra utiliser 10.0.0.0/24. On peut ignorer le 160, car il est en dehors du subnet (24 = 255.255.255.0).

## Utilisation

* Utiliser la commande `sudo ipsec restart` afin de partir le daemon

* Utilires la commande `sudo ipsec up fortiGate` afin de se connecter au VPN

Si tout fonnctionne, cela est clairement indiqué dans l'output de la dernière commande.

