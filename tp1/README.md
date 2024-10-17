# TP1 : Les premiers pas de bébé B1

## I. Récolte d'informations

### 🌞 Adresses IP de ta machine

#### Afficher l'adresse IP de la machine sur la carte réseau Wi-Fi :

```powershell
PS C:\Users\jawad> ipconfig
Carte réseau sans fil Wi-Fi :

   Adresse IPv4. . . . . . . . . . . . . .: 10.33.77.199
```

#### Afficher l'adresse IP de la machine sur la carte réseau Ethernet :

```powershell
PS C:\Users\jawad> ipconfig /all
Carte Ethernet Ethernet :

   Statut du média. . . . . . . . . . . . : Média déconnecté
   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Realtek PCIe GbE Family Controller
   Adresse physique . . . . . . . . . . . : 40-C2-BA-52-11-43
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
```

### 🌞 Si t'as un accès internet normal, d'autres infos sont forcément dispos...

#### Afficher l'adresse IP de la passerelle du réseau local :

```powershell
PS C:\Users\jawad> ipconfig
Carte réseau sans fil Wi-Fi :

   Passerelle par défaut. . . . . . . . . : 10.33.79.254
```

#### Afficher l'adresse IP du serveur DNS que le PC connaît :

```powershell
PS C:\Users\jawad> ipconfig
Carte réseau sans fil Wi-Fi :

   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8
                                       1.1.1.1
```

#### Afficher l'adresse IP du serveur DHCP que le PC connait :

```powershell
PS C:\Users\jawad> ipconfig
Carte réseau sans fil Wi-Fi :

   Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
```

### 🌟 BONUS

#### Déterminer si il y a un pare-feu actif sur la machine :

```powershell

```

## II. Utiliser le réseau

### 🌞 Envoie un ping vers...

#### Soi-même! :

```powershell
PS C:\Users\jawad> ping 10.33.77.199

Envoi d’une requête 'Ping'  10.33.77.199 avec 32 octets de données :
Réponse de 10.33.77.199 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.199 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.199 : octets=32 temps<1ms TTL=128
Réponse de 10.33.77.199 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 10.33.77.199:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
```

#### Vers l'adresse IP 127.0.0.1 :

```powershell
PS C:\Users\jawad> ping 127.0.0.1

Envoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
```

### 🌞 On continue avec ping. Envoie un ping vers...

#### La passerelle :

```powershell
PS C:\Users\jawad> ping 10.33.79.254

Envoi d’une requête 'Ping'  10.33.79.254 avec 32 octets de données :
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.
Délai d’attente de la demande dépassé.

Statistiques Ping pour 10.33.79.254:
    Paquets : envoyés = 4, reçus = 0, perdus = 4 (perte 100%),
```

#### Un(e) pote sur le réseau :

```powershell
PS C:\Users\jawad> ping 10.33.66.78

Envoi d’une requête 'Ping'  10.33.66.78 avec 32 octets de données :
Réponse de 10.33.66.78 : octets=32 temps=90 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=93 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=119 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=23 ms TTL=64

Statistiques Ping pour 10.33.66.78:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 23ms, Maximum = 119ms, Moyenne = 81ms
```

#### Un site internet :

```powershell
PS C:\Users\jawad> ping www.ynov.com

Envoi d’une requête 'ping' sur www.ynov.com [104.26.10.233] avec 32 octets de données :
Réponse de 104.26.10.233 : octets=32 temps=23 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=17 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=18 ms TTL=55
Réponse de 104.26.10.233 : octets=32 temps=16 ms TTL=55

Statistiques Ping pour 104.26.10.233:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 16ms, Maximum = 23ms, Moyenne = 18ms
```
### 🌞 Faire une requête DNS à la main

```powershell
PS C:\Users\jawad> nslookup www.thinkerview.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.thinkerview.com
Addresses:  2606:4700:3037::6815:4968
          2606:4700:3036::ac43:bda6
          188.114.97.7
          188.114.96.7
```

```powershell
PS C:\Users\jawad> nslookup www.wikileaks.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    wikileaks.org
Addresses:  80.81.248.21
          51.159.197.136
Aliases:  www.wikileaks.org
```

```powershell
PS C:\Users\jawad> nslookup www.torproject.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.torproject.org
Addresses:  2620:7:6002:0:466:39ff:fe32:e3dd
          2a01:4f9:c010:19eb::1
          2a01:4f8:fff0:4f:266:37ff:fe2c:5d19
          2620:7:6002:0:466:39ff:fe7f:1826
          2a01:4f8:fff0:4f:266:37ff:feae:3bbc
          95.216.163.36
          116.202.120.166
          204.8.99.144
          204.8.99.146
          116.202.120.165
```

## III. Sniffer le réseau

*Travail fait sur WireShark*

## IV. Network scanning et adresses IP

```powershell
PS C:\Users\jawad> ipconfig
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::949:b672:5dcb:8bd7%11
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.78.245
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . :
```