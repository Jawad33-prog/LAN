# Quelques pings
   
## 🌞 Prouvez que votre configuration est effective

```powershell 
PS C:\Users\jawad> Get-NetIPAddress -InterfaceAlias "Ethernet"

IPAddress         : fe80::91b3:9c27:fd9d:c7f9%16
InterfaceIndex    : 16
InterfaceAlias    : Ethernet
AddressFamily     : IPv6
Type              : Unicast
PrefixLength      : 64
PrefixOrigin      : WellKnown
SuffixOrigin      : Link
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore

IPAddress         : 10.1.1.1
InterfaceIndex    : 16
InterfaceAlias    : Ethernet
AddressFamily     : IPv4
Type              : Unicast
PrefixLength      : 24
PrefixOrigin      : Manual
SuffixOrigin      : Manual
AddressState      : Preferred
ValidLifetime     :
PreferredLifetime :
SkipAsSource      : False
PolicyStore       : ActiveStore
```

## 🌞 Tester que votre LAN + votre adressage IP est fonctionnel

```powershell
PS C:\Users\jawad> ping 10.1.1.2

Envoi d’une requête 'Ping'  10.1.1.2 avec 32 octets de données :
Réponse de 10.1.1.2 : octets=32 temps=4 ms TTL=128
Réponse de 10.1.1.2 : octets=32 temps=3 ms TTL=128
Réponse de 10.1.1.2 : octets=32 temps=5 ms TTL=128
Réponse de 10.1.1.2 : octets=32 temps=4 ms TTL=128

Statistiques Ping pour 10.1.1.2:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 3ms, Maximum = 5ms, Moyenne = 4ms
```

# Animal numérique

## 🌞 Sur le PC serveur

```powershell
PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> .\nc64.exe -l -p 9999
Bonjour
Bonjour

PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> .\nc64.exe 10.1.1.2 9998
Bonjour
Bonjour
```

## 🌞 Sur le PC serveur toujours

```powershell
PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> netstat -a -b -n
  TCP 10.1.1.1:30783  10.1.1.2:9998  ESTABLISHED  [nc64.exe]
```

## 🌞 Sur le PC client

```powershell
PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> .\nc.exe 10.1.1.2 9998
Yo!
Yo!
```

## 🌞 Echangez-vous des messages

```powershell
PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> .\nc64.exe -l -p 9999
Salut, comment vas-tu?
ça va et toi ?
```

## 🌞 Utilisez une commande qui permet de voir la connexion en cours

```powershell
PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> netstat 10.1.1.1:9999

Connexions actives

  Proto  Adresse locale         Adresse distante       État
  TCP    10.1.1.1:9999          AM:57328               ESTABLISHED

  PS C:\Users\jawad\Downloads\netcat-win32-1.11\netcat-1.11> netstat 10.1.1.2:9998

Connexions actives

  Proto  Adresse locale         Adresse distante       État
  TCP    10.1.1.1:30866         AM:9998                ESTABLISHED
```

# Autres services

Fonctionne pas... :(