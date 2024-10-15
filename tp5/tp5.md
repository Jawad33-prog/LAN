# I. Setup

## ☀️ Uniquement avec des commandes, prouvez-que :

*vous avez bien configuré les adresses IP demandées (un ip a suffit hein)*

```powershell
[jawad@localhost ~]$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:d2:9c:1d brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.11/24 brd 10.5.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fed2:9c1d/64 scope link
       valid_lft forever preferred_lft forever
```

```powershell
[jawad@localhost ~]$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:d2:9c:1d brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.12/24 brd 10.5.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fed2:9c1d/64 scope link dadfailed tentative
       valid_lft forever preferred_lft forever
```

```powershell
[jawad@localhost ~]$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:d2:9c:1d brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 86369sec preferred_lft 86369sec
    inet6 fe80::a00:27ff:fed2:9c1d/64 scope link
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:04:17:5e brd ff:ff:ff:ff:ff:ff
    inet 10.5.1.254/24 brd 10.5.1.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe04:175e/64 scope link
       valid_lft forever preferred_lft forever
```

*vous avez bien configuré les hostnames demandés*

```powershell
[jawad@localhost ~]$ sudo hostnamectl set-hostname client1
[jawad@localhost ~]$ sudo hostnamectl
 Static hostname: client1
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: e6c810eee35249dfb8d60fc495d8b5d0
         Boot ID: 877cf719e0474b36bca860e7930db047
  Virtualization: oracle
Operating System: Rocky Linux 9.4 (Blue Onyx)
     CPE OS Name: cpe:/o:rocky:rocky:9::baseos
          Kernel: Linux 5.14.0-427.13.1.el9_4.x86_64
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Firmware Version: VirtualBox
```

```powershell
[jawad@localhost ~]$ sudo hostnamectl set-hostname client2
[jawad@localhost ~]$ sudo hostnamectl
 Static hostname: client2
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: e6c810eee35249dfb8d60fc495d8b5d0
         Boot ID: b66ecd70df79496a95a4071391534591
  Virtualization: oracle
Operating System: Rocky Linux 9.4 (Blue Onyx)
     CPE OS Name: cpe:/o:rocky:rocky:9::baseos
          Kernel: Linux 5.14.0-427.13.1.el9_4.x86_64
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Firmware Version: VirtualBox
```

```powershell
[jawad@localhost ~]$ sudo hostnamectl set-hostname routeur
[jawad@localhost ~]$ sudo hostnamectl
 Static hostname: routeur
       Icon name: computer-vm
         Chassis: vm 🖴
      Machine ID: e6c810eee35249dfb8d60fc495d8b5d0
         Boot ID: 3b6b61d9a4ff4deaa531c2f5d6865bb3
  Virtualization: oracle
Operating System: Rocky Linux 9.4 (Blue Onyx)
     CPE OS Name: cpe:/o:rocky:rocky:9::baseos
          Kernel: Linux 5.14.0-427.13.1.el9_4.x86_64
    Architecture: x86-64
 Hardware Vendor: innotek GmbH
  Hardware Model: VirtualBox
Firmware Version: VirtualBox
```

*tout le monde peut se ping au sein du réseau 10.5.1.0/24*

Depuis client1 :

```powershell
[jawad@localhost ~]$ ping 10.5.1.12
PING 10.5.1.12 (10.5.1.12) 56(84) bytes of data.
64 bytes from 10.5.1.12: icmp_seq=1 ttl=64 time=6.44 ms
...

[jawad@localhost ~]$ ping 10.5.1.254
PING 10.5.1.254 (10.5.1.254) 56(84) bytes of data.
64 bytes from 10.5.1.254: icmp_seq=1 ttl=64 time=2.26 ms
...
```

Depuis client2 :

```powershell
[jawad@localhost ~]$ ping 10.5.1.11
PING 10.5.1.11 (10.5.1.11) 56(84) bytes of data.
64 bytes from 10.5.1.11: icmp_seq=1 ttl=64 time=4.44 ms
...

[jawad@localhost ~]$ ping 10.5.1.254
PING 10.5.1.254 (10.5.1.254) 56(84) bytes of data.
64 bytes from 10.5.1.254: icmp_seq=1 ttl=64 time=4.61 ms
...
```

Depuis routeur :

```powershell
[jawad@localhost ~]$ ping 10.5.1.12
PING 10.5.1.12 (10.5.1.12) 56(84) bytes of data.
64 bytes from 10.5.1.12: icmp_seq=1 ttl=64 time=13.1 ms
...

[jawad@localhost ~]$ ping 10.5.1.11
PING 10.5.1.11 (10.5.1.11) 56(84) bytes of data.
64 bytes from 10.5.1.11: icmp_seq=1 ttl=64 time=26.6 ms
...
```

# II. Accès internet pour tous

## ☀️ Déjà, prouvez que le routeur a un accès internet

```powershell
[jawad@localhost ~]$ ping ynov.com
PING ynov.com (104.26.10.233) 56(84) bytes of data.
64 bytes from 104.26.10.233 (104.26.10.233): icmp_seq=1 ttl=52 time=31.0 ms
...
```

## ☀️ Prouvez que les clients ont un accès internet

Depuis client1 :

```powershell
[jawad@client1 ~]$ ping www.ynov.com
PING www.ynov.com (172.67.74.226) 56(84) bytes of data.
64 bytes from 172.67.74.226 (172.67.74.226): icmp_seq=1 ttl=51 time=35.7 ms
...
```

Depuis client2 :

```powershell
[jawad@localhost ~]$ ping www.ynov.com
PING www.ynov.com (172.67.74.226) 56(84) bytes of data.
64 bytes from 172.67.74.226 (172.67.74.226): icmp_seq=1 ttl=51 time=29.7 ms
...
```

## ☀️ Montrez-moi le contenu final du fichier de configuration de l'interface réseau

```powershell
[jawad@client2 ~]$ cat /etc/sysconfig/network-scripts/ifcfg-enp0s3
DEVICE=enp0s3
NAME=client2.tp5.b1

ONBOOT=yes
BOOTPROTO=static

IPADDR=10.5.1.12
NETMASK=255.255.255.0
GATEWAY=10.5.1.254
DNS1=1.1.1.1
```

# III. Serveur SSH

## ☀️ Sur routeur.tp5.b1, déterminer sur quel port écoute le serveur SSH

```powershell
[jawad@localhost ~]$ sudo ss -tlnp | grep sshd
[sudo] password for jawad:
LISTEN 0      128          0.0.0.0:22        0.0.0.0:*    users:(("sshd",pid=700,fd=3))
LISTEN 0      128             [::]:22           [::]:*    users:(("sshd",pid=700,fd=4))
```

## ☀️ Sur routeur.tp5.b1, vérifier que ce port est bien ouvert

```powershell
[jawad@localhost ~]$ sudo firewall-cmd --list-all | grep services
  services: cockpit dhcpv6-client ssh
```

```powershell
[jawad@localhost ~]$ cat /etc/services | grep ssh
ssh             22/tcp                          # The Secure Shell (SSH) Protocol
ssh             22/udp                          # The Secure Shell (SSH) Protocol
x11-ssh-offset  6010/tcp                        # SSH X11 forwarding offset
ssh             22/sctp                 # SSH
sshell          614/tcp                 # SSLshell
sshell          614/udp                 #       SSLshell
netconf-ssh     830/tcp                 # NETCONF over SSH
netconf-ssh     830/udp                 # NETCONF over SSH
sdo-ssh         3897/tcp                # Simple Distributed Objects over SSH
sdo-ssh         3897/udp                # Simple Distributed Objects over SSH
netconf-ch-ssh  4334/tcp                # NETCONF Call Home (SSH)
snmpssh         5161/tcp                # SNMP over SSH Transport Model
snmpssh-trap    5162/tcp                # SNMP Notification over SSH Transport Model
tl1-ssh         6252/tcp                # TL1 over SSH
tl1-ssh         6252/udp                # TL1 over SSH
ssh-mgmt        17235/tcp               # SSH Tectia Manager
ssh-mgmt        17235/udp               # SSH Tectia Manager
```

# IV. Serveur DHCP

## ☀️ Installez et configurez un serveur DHCP sur la machine routeur.tp5.b1

```powershell
[jawad@localhost ~]$ sudo dnf install dhcp-server
Last metadata expiration check: 0:09:52 ago on Tue 15 Oct 2024 05:30:58 PM CEST.
Package dhcp-server-12:4.4.2-19.b1.el9.x86_64 is already installed.
Dependencies resolved.
Nothing to do.
Complete!
```

```powershell
sudo nano /etc/dhcp/dhcpd.conf

#
# DHCP Server Configuration file.
#   see /usr/share/doc/dhcp-server/dhcpd.conf.example
#   see dhcpd.conf(5) man page
#
option domain-name "tp5.b1";              
option domain-name-servers 8.8.8.8;       

subnet 10.5.1.0 netmask 255.255.255.0 {    
    range 10.5.1.20 10.5.1.100;          
    option routers 10.5.1.254;       
    option subnet-mask 255.255.255.0;     
    option broadcast-address 10.5.1.255;   
}
```