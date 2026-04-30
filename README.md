# Projet VPN WireGuard

## Objectif

Mettre en place un VPN afin de permettre la communication sécurisée entre plusieurs machines virtuelles.

## Architecture

* 1 serveur VPN
* 2 clients (VM)
* Réseau privé : 10.0.0.0/24

## Schéma

Voir le fichier `schema.png`

## Technologies utilisées

* WireGuard
* VMware
* Linux (Debian / Ubuntu)

## Fonctionnement

Les clients se connectent au serveur VPN via un tunnel sécurisé.
Chaque machine possède une adresse IP privée et des clés de chiffrement.
Le serveur permet la communication entre les clients.

## Configuration

* Création des clés publique/privée
* Configuration des fichiers `wg0.conf`
* Attribution des IP VPN
* Définition des règles `AllowedIPs`
* Activation du routage (IP forwarding)

## Problème rencontré

Le ping entre les clients ne fonctionne pas dans l’environnement de l’école.

Cause probable :

* Blocage des ports UDP
* Restrictions réseau empêchant le trafic VPN

## Conclusion

Le VPN est correctement configuré mais limité par l’environnement réseau.
Dans un environnement non restreint, la communication entre clients fonctionnerait.
