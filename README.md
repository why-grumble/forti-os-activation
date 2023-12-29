# Activation de Forti OS

Ce document va vous permettre d'activer Forti OS et de pouvoir utiliser le pare-feu sans limites.
Vous aurez besoin de Python pour générer la licence.

## Téléchargement

Télécharger la VM de Fortigate depuis le site de support (**Version 7.2.6 ou précédente**) :
https://support.fortinet.com/Download/VMImages.aspx

## Configuration Fortigate

Importer la VM sur votre hyperviseur
Par défaut le compte est admin sans mot de passe
(Le clavier es en QWERTY je vous conseil de définir 12345 comme mot de passe pour le moment)
Pour configurer le port WAN et permettre un accès web exécuté ces commandes

```bash
config system interface
edit port1
set mode dhcp
set allowaccess http https ssh
get
```
Vous pouvez maintenant vous connectez à l’interface web avec son ip

## Licence

Script provenant de : https://github.com/rrrrrrri/fos-license-gen

Utiliser votre compte admin et il va vous être demandé une licence
A ce moment-là on va utiliser le script main.py
```bash
python3 main.py
```
Il va générer un fichier Licence.lic, il ne reste plus qu’à l’importer dans la section prévue et le pare-feu va redémarrer.
