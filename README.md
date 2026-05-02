# Projet VPN WireGuard

## Objectif

Mettre en place un VPN afin de permettre une communication sécurisée entre un client et un serveur à l’aide d’un tunnel chiffré.

---

## Architecture

* 1 serveur VPN (machine virtuelle Ubuntu)
* 1 client (PC)
* Réseau privé VPN : 10.0.0.0/24

| Machine   | Rôle    | IP VPN   |
| --------- | ------- | -------- |
| VM Ubuntu | Serveur | 10.0.0.1 |
| PC        | Client  | 10.0.0.2 |

---

## Schéma

Voir le fichier `schema.png`

---

## Technologies utilisées

* WireGuard
* VMware
* Linux (Ubuntu)

---

## Fonctionnement

Le client se connecte au serveur VPN via un tunnel sécurisé utilisant WireGuard.

Chaque machine possède :

* une clé privée (secrète)
* une clé publique (échangée)

Le serveur écoute sur un port (51820) et accepte les connexions du client.

Une fois le tunnel établi, les deux machines peuvent communiquer comme si elles étaient sur le même réseau local.

---

## Mise en place

* Installation de WireGuard sur le serveur et le client
* Génération des clés publique/privée
* Configuration des fichiers `wg0.conf`
* Attribution des adresses IP VPN
* Ajout des peers (client ↔ serveur)
* Activation du tunnel VPN

---

## Tests réalisés

* Vérification du tunnel avec `wg`
* Ping du client vers le serveur :

  * `ping 10.0.0.1`
* Ping du serveur vers le client :

  * `ping 10.0.0.2`

Résultat : communication fonctionnelle via le VPN

---

## Problèmes rencontrés

* Mauvaise configuration de l’endpoint (adresse IP)
* Confusion entre clés publiques et privées
* Restrictions réseau de l’établissement (blocage UDP)

---

## Conclusion

Le VPN a été correctement mis en place et permet une communication sécurisée entre le client et le serveur.

Ce projet a permis de comprendre :

* le fonctionnement d’un VPN
* la gestion des clés de chiffrement
* la configuration réseau dans un environnement virtualisé

---

## Améliorations possibles

* Ajouter plusieurs clients
* Permettre la communication client ↔ client
* Automatiser le démarrage du VPN
* Déployer sur un serveur public