# Vegova - delavnica Linux + Minecraft

## Virtualka

## Osnovni Linux ukazi

### Drevesna struktura datotek

### Ukaz: pwd

### Ukaz: ls

### Ukaz: cd

### Ukaz: touch

### Ukaz: tree

### Ukaz: wget

## Datoteke in pravice

### Ukaz: nano

### Pravice dostopa do datotek

### Ukaz: chown

### Ukaz: chmod

## Namestitev Jave


## Namestitev Minecraft strežnika

### Konfiguracija strežnika kot storitve: systemd

## Firewall

Dokumentacija:

- [Dokumentacija 1](https://help.ubuntu.com/community/UFW)

Privzeto ob namestitvi Ubuntu serverja ni nameščenega požarnega zidu, za to ga moramo namestiti sami.

Firewall oz. požarni zid je skupek programske opreme, ki skrbi za zaščito pri komunikaciji po omrežju. Ločuje dva odseka omrežij in med njima prepušča zgolj dovoljen promet, drug promet pa zavrne. V našem primeru ščiti aplikacije, ki tečejo na računalniku pred zunanjim nedovoljenim dosotopom.

Da zaščitimo naš strežnik bomo uporabili **ufw** (Uncomplicated firewall), saj omogoča enostaven konfiguracijski vmesnik. 

``` bash
# Namestitev
sudo apt install ufw

# Pregled statusa
sudo ufw status verbose
# icoming: promet od zunaj, ki dostopa do aplikacij
# routed: promet, ki potuje čez napravo do "drugih naprav" (naprava se obnaša kot usmerjevalnik)
# outgoing: promet, k ga ustvarjajo aplikacije na napravi, ko dostopajo do spleta

# Odpremo port za MineCraft server
sudo ufw allow 25565/tcp

# Primer: Omogoči tcp in udp
sudo ufw allow 53

# Primer: Omogoči promet določeni storitvi (/etc/services)
sudo ufw allow SERVICENAME

# Primer: Onemogoči promet
sudo ufw deny 53
sudo ufw deny 53/udp

# Pregled statusa
sudo ufw status verbose

# Omogoči požarni zid
sudo ufw enable
```

Konfiguracijske datoteke se nahajajo na `/etc/ufw`.
