# Procédure d’installation

## 1. Installation

Installer WireGuard sur chaque machine :

```
sudo apt install wireguard
```

## 2. Génération des clés

```
wg genkey | tee privatekey | wg pubkey > publickey
```

## 3. Configuration

Créer le fichier `wg0.conf` sur chaque machine avec :

* adresse IP VPN
* clés
* configuration des peers

## 4. Activation

```
sudo wg-quick up wg0
```

## 5. Vérification

```
sudo wg
ip a
ping 10.0.0.X
```

## 6. Configuration serveur

Activer le routage :

```
echo 1 | sudo tee /proc/sys/net/ipv4/ip_forward
```
