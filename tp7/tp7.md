# Serveur Web

## 🌞 Lister les ports en écoute sur la machine

```powershell
[jawad@web ~]$ sudo ss -ltnp | grep 80
LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("nginx",pid=11344,fd=6),("nginx",pid=11343,fd=6))
LISTEN 0      511             [::]:80           [::]:*    users:(("nginx",pid=11344,fd=7),("nginx",pid=11343,fd=7))
```

## 🌞 Ouvrir le port dans le firewall de la machine

```powershell
[jawad@web ~]$ sudo firewall-cmd --permanent --add-port=80/tcp
success
[jawad@web ~]$ sudo firewall-cmd --reload
success
```

## 🌞 Vérifier que ça a pris effet

```powershell
[jawad@client1 ~]$ ping sitedefou.tp7.b1
PING sitedefou.tp7.b1 (10.7.1.11) 56(84) bytes of data.
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=1 ttl=64 time=2.05 ms
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=2 ttl=64 time=2.13 ms
...
```