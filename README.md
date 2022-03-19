# Vegova - delavnica Linux + Minecraft

## Virtualka

## Ukazna lupina

**Ukazna lupina** oz. *shell* je program, ki uporabniku omogoča osnovno delo, ki je lahko interaktivno ali neinteraktivno.

Poznamo 2 vrsti lupin:

- **ukazne lupine** - delo preko ukazne vrstice
  - *sh* - Bourneova lupina (ena prvih, 1977)
  - *csh* - C lupiona
  - ksh - Kornova lupina (v začetku 1980')
  - bash - Bourne-again lupina (1986)
  - command.com - DOS lupna
  - cmd.exe - Windows lupina
  - powershell - Nova Windows Lupina (temelji na .NET)
- **grafične lupine** - delo preko grafičnega uporabniškega vmesnika (GUI)
  - progman.exe (Windows 3.x)
  - explorer.exe (Windows NT itd.)
  - GNOME (GNU Network Object Model Environment)
  - KDE (K Desktop Environment)

TODO: Dodaj slike

### Ukazna vrstica

U ukazno vrstico izvajamo ukaze.

Ukazna vrstica se začne s **pozivnikom (prompt)**  `student@stroj:~>`, kjer `student` predstavlja ime uporabnika (ki je odprl lupino), `stroj` predstavlja ime naprave, `~` pa predstavlja pot, kjer se trenutno nahajamo.

TODO: Slika

Ukazne vrstice lahko avtomatično dopolnjujemo s pomočjo pritiskom tipke *Tab*.

Ukazna lupina shranjuje zgodovino izvedenih ukaznih vrstic:

- Po zgodovini se premikamo s tipkama *gor*/*dol*.
- Po zgodovini lahko iščemo s *Ctrl+R*.
- Uporabimo ukaz *histor* (npr. z `history -c` pobrišemo zgodovino ukazov).


Ostale pomembne tipke:

- *Ctrl+C* - ukinitev izvajanja ukaza
- *Ctrl+Z* - zaustavitev izvajanja ukaza
- *Ctrl+D* - konec vnosa podatkov

### Drevesna struktura datotek

### Ukaz: man

### Ukaz: pwd

### Ukaz: ls

### Ukaz: cd

### Ukaz: touch

### Ukaz: tree

### Ukaz: wget

### Okoljske spremenljivke


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
