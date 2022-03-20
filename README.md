# Vegova - delavnica Linux + Minecraft

## Virtualka

- OS: [Ubuntu Server 20.04 (OVA format)](https://drive.google.com/file/d/1uXuYXMLVn9_eMHHl0PMdLa4Gml0fesxc/view?usp=sharing)

**TODO: Slike za namestitev (+omrežna nastavitev virtualk, da bodo lahko dostopali do njih potem)**

## Ukazna lupina

**Ukazna lupina** oz. *shell* je program, ki uporabniku omogoča osnovno delo, ki je lahko interaktivno ali neinteraktivno.

Poznamo 2 vrsti lupin:

- **ukazne lupine** - delo preko ukazne vrstice
  - `sh` - Bourneova lupina (ena prvih, 1977)
  - `csh` - C lupina
  - `ksh` - Kornova lupina (v začetku 1980')
  - `bash` - Bourne-again lupina (1986)
  - `command.com` - DOS lupna
  - `cmd.exe` - Windows lupina
  - `powershell` - Nova Windows Lupina (temelji na .NET)
- **grafične lupine** - delo preko grafičnega uporabniškega vmesnika (GUI)
  - `progman.exe` (Windows 3.x)
  - `explorer.exe` (Windows NT itd.)
  - GNOME (GNU Network Object Model Environment)
  - KDE (K Desktop Environment)

| **Bash** |
|:--------:|
| ![bash](https://user-images.githubusercontent.com/46302511/159131636-ba74ebb0-8a4d-4fda-b158-55115e43b2ae.png) |

| **Fish** |
|:--------:|
| ![fish](https://user-images.githubusercontent.com/46302511/159131733-56fd9d63-61cc-4c6f-be1a-1ac2ef3c32aa.png) |

| **CMD** |
|:-------:|
| ![cmd](https://user-images.githubusercontent.com/46302511/159131670-01d53e5f-ca8d-4554-9af5-f5e1b44e8d8b.png) |

| **Powershell** |
|:--------------:|
| ![powershell](https://user-images.githubusercontent.com/46302511/159131704-e3f6419f-1e3d-4c3c-a8cd-ab9591c6a02b.png) |

| **Explorer** |
|:------------:|
| ![explorer](https://user-images.githubusercontent.com/46302511/159131711-40b4fbb9-4a56-4252-8ac1-a16463a4e0a6.png) |

| **GNOME** |
|:---------:|
| ![gnome](https://user-images.githubusercontent.com/46302511/159131717-0b34e4b3-937f-4326-867b-86742515198a.png) |

### Ukazna vrstica

V ukazno vrstico vnašamo ukaze, ki se nato izvedejo.

Ukazna vrstica se začne s **pozivnikom (prompt)**  `student@stroj:~>`, kjer `student` predstavlja ime uporabnika (ki je odprl lupino), `stroj` predstavlja ime naprave, `~` pa predstavlja pot, kjer se trenutno nahajamo. (`~` je okrajšava za `/home/<ime-uporabnika>`)

Ukazne vrstice lahko avtomatično dopolnjujemo s pomočjo pritiskom tipke *Tab*.

Ukazna lupina shranjuje zgodovino izvedenih ukaznih vrstic:
- po zgodovini se premikamo s tipkama *gor*/*dol*,
- po zgodovini lahko iščemo s *Ctrl+R*,
- uporabimo ukaz *history* (npr. z `history -c` pobrišemo zgodovino ukazov),
- pri lupinah, ki niso `bash` so ukazi lahko drugačni.

Ostale pomembne tipke:
- *Ctrl+C* - ukinitev izvajanja ukaza
- *Ctrl+Z* - zaustavitev izvajanja ukaza
- *Ctrl+D* - konec vnosa podatkov

| Primer dopolnjevanja besedila vrstice |
|:-------------------------------------:|
| ![GNOME Terminal - ukazna vrstica](https://user-images.githubusercontent.com/46302511/159132155-d3ec4bd6-f8f1-46fc-bdcd-e83c7724199b.png) |

### Ukaz: `echo`

Z ukazom `echo` izpišemo podane parametre na zaslon. Z stikali lahko spremenimo stil izpisa.

``` bash
# Primer izpisa besedila
echo "Besedilo"

# Primer izpisa brez končnega prehoda v novo vrstico
echo -n "Brez nove vrstice"
```

Dokumentacija:

- [Dokumentacija za ukaz](https://linux.die.net/man/1/echo)

### Ukaz: `man`

Eden izmed bolj uporabnih programov, ki pride privzeto na vseh Linux distribucijah je `man`, kar je okrajšava za **manual** oz. navodila.
Le-ta lahko prikaže navodila (skoraj) vsakega programa, ki je nameščen na sistemu, pa tudi navodila za uporabo C knjižnic in drugih funkcij, ki jih Linux ponuja.

Za začetek lahko pogledamo navodila za uporabo kar `man` programa samega, in sicer z ukazom `man man`.

Poglavja:

- *name* - ime ukaza z enovrstičnim opisom
- *synopsis* - formalni zapis kako pognazi ukaz, katere parametre lahko podamo
- *description* - opis ukaza
- *options* - parametri, ki jih lahko podamo ukazu
- *exit status* - pomeni posameznih izhodnih vrednosti (0 = OK, kar je različno od 0 pomeni, da je prišlo do napake)
- *return value* - če dokumentacija opisuje metodo knjižnice, je tu opisana vrednost, ki jo metoda vrne
- *errors* - opisuje napake, ki so lahko vrnjene preko spremenljivke *errno*
- *environment* - opis okoljskih spremenljivk, ki vplivajo na delovanje programa
- *files* - datoteke in mape, kjer se program in konfiguracijske datoteke nahajajo
- *versions* - različice 
- *notes* - dodatni zapiski
- *bugs* - znani hrošči
- *examples* - pogosti primeri uporabe
- *authors* - avtorji programa
- *see also* - povezave do dokumentacij drugih programov

Primeri ukazov:

``` bash
# Izpis doumentacije za ukaz printf
man printf

# Izpis določenega poglavja dokumentacije
man 2 intro

# Izpis vseh dokumentacij, ki so na voljo za ukaz
man -a intro

# Iskanje ključne besede po vseh dokumentacijah
man -k cd

# Izpis lokacije, kjer se nahaja dokumentacija
man -w ls

# Prikaz dokumentacije s tem, da pri imenu upošteva velikost črk
man -I printf

```

![man man](https://user-images.githubusercontent.com/46302511/159133118-7cbe39ee-5e4f-449a-a303-0b500819a214.png)

Za izhod iz programa pritisnemo na tipko **q** (piše tudi levo spodaj).

Če ne vemo točno kateri program želimo, lahko uporabimo argument za iskanje: `-k` (npr. `man -k git`)

Dodatna dokumentacija:

- [Primeri](https://www.geeksforgeeks.org/man-command-in-linux-with-examples/)
- [Primeri](https://www.howtogeek.com/663440/how-to-use-linuxs-man-command-hidden-secrets-and-basics/)

### Drevesna struktura datotek

Iz Windowsa smo navajeni poti kot je `C:\Users\Uporabik\Documents`, pri Linuxu je stvar podobna (npr. `/home/uporabnik/Documents` v tem primeru).

![Drevesna struktura datotek](https://user-images.githubusercontent.com/46302511/159132426-8f21d6ba-837c-46f9-8536-6a5aa040757b.png)

Ker se želimo bolje naučiti uporabljati Linux, si bomo o Linux drevesni strukturi prebrali kar iz prej omenjenega `man` in sicer z ukazom `man hier`.
Najpomembnejši direktoriji so `/`, `/bin`, `/boot`, `/dev`, `/etc`, `/home`, `/lib`, `/media`, `/proc` in `/root`:

|   Pot  |                        Opis                       |
|:------:|:-------------------------------------------------:|
|    /   |                Korenski direktorij                |
|  /bin  |                Izvršljivi programi                |
|  /boot |              Datoteke za *bootloader*             |
|  /dev  | Poti za priklopljene naprave (diski, kamere, ...) |
|  /etc  |              Konfiguracijske datoteke             |
|  /home |                Uporabniške datoteke               |
|  /lib  |                Sistemske knjižnice                |
| /media |        USB ključki in druge zunanje naprave       |
|  /proc |               Informacije o sistemu               |
|  /root |             Datoteke uporabnika `root`            |

### Ukaz: `pwd`

`pwd` (print working directory) je program, za izpis poti trenutnega direktorija.
Večina lupin podpira uporabo spremenljivke `$PWD`, ki vrne isto pot, a brez izvajanja zunanjega programa.

``` bash
# Primer: Poženemo ukaz pwd
student@stroj:~/delavnice2022$ pwd
/home/student/delavnice2022

# Primer: Izpišemo vsebino okoljske spremenljivke PWD
student@stroj:~/delavnice2022$ echo $PWD
/home/student/delavnice2022
```

### Ukaz: `ls`

`ls` (list directory contents) je program za izpis datotek v trenutnem ali želenem direktoriju.
Če ga zaženemo brez argumentov bo izpisal vsebino trenutnega direktorija, če pa mu na konec dodamo še ime nekega direktorija, pa bo izpisal vsebino le-tega.
Ker pogosto o izpisanih datotekah želimo vedeti več kot le ime, `ls` ponuja veliko koristnih argumentov.

Primer le nekaterih:
- `-l` oz. `--long`: izpiše dodatne informacije o datotekah (npr. velikost, lastnike, čas spremembe, ...)
- `-h` oz. `--human-readable`: izpiše velikosti datotek na lepši način (npr. 1K, 2G, ...)
- `-a` oz. `--all`: izpiši tudi skrite datoteke (te, ki se začnejo s `.`)

``` bash
# Izpis vsebine mape v kateri se trenutno nahajamo
ls

# Izpis vseh datotek z dodatnimi informacijimi napisanimi na lepši način
ls -lah

# Izpis druge mape
ls /etc
```

Dokumentacija:

- [Dokumentacija ukaza](https://man7.org/linux/man-pages/man1/ls.1.html)

### Ukaz: `cd`

`cd` (change directory) se uporablja za premik med mapami, tako kot se v grafičnem vmesniku premaknemo v mapo z dvojnim klikom.

Posebne okrajšave poti:

- `-` - prejšna mapa v kateri smo bili
- `..` - nadrejena mapa (ena mapa višje v drevesu)
- `--` - mapa v kateri smo uporabili ukaz `cd -`
- `~` - domača mapa uporabnika (ponavadi `/home/uporabnik`)
- `.` - trenutna mapa

Pri ukazu lahko podamo dva tipa poti:

- **relativno** - Pot podamo od trenutne mape (kot če bi namesto `.` dodali pot, ki jo izpiše ukaz `pwd`) npr. `cd ./podmapaTrenutneMape`.
- **absolutno** - Podamo celotno pod od korenskega direktorija (`/`) npr. `/home/uporabnik`.

V kolikor ne vemo celotne poti, si lahko pomagamo s *tabulatorjem*, ki nam  bo pokazal možnosti za dokončanje poti.


Primeri:

``` bash
# Premik v korensko mapo
cd /

# Premik v domačo mapo trenutnega uporabnika
cd ~

# Premik eno mapo višje
cd ..

# Premik v sosednjo mapo
cd ../sosednjaMapa
```

Ker je ukaz ugrajen v samo lupino, se do njegove dokumentacije pride z ukazom `man builtins`.

Dokumentacija:

- [Dokumentacija ukaza](https://man7.org/linux/man-pages/man1/cd.1p.html)
- [Primeri uporabe ukaza](https://www.tecmint.com/cd-command-in-linux/)

### Ukaz: `touch`

`touch` se uporablja za ustvarjanje praznih datotek, tako kot lahko v grafičnem vmesniku z desnim klikom ustvarimo novo datoteko.

Primeri:

``` bash
# Ustvarimo datoteko
touch datoteka1
```

Dokumentacija:

- [Dokumentacija](https://man7.org/linux/man-pages/man1/touch.1.html)

### Ukaz: `tree`

`tree` se uporablja kot alternativa programa `ls`, saj tudi izpiše seznam datotek, a na hierarhičen način z zamaknjenimi vrsticami glede na globino direktorija.

Primeri:

``` bash
# Preprost izpis
tree mapa

# Izpis tudi skritih datotek/map
tree -a mapa

# Izpis zgolj map
tree -d mapa

# Izpis celotne (relativne) poti do datotek
tree -f mapa

# Izpis brez zamikov in drevesne strukture
tree -i mapa

# Izpis datotek in map, ki ustrezajo vzorcu
tree -P vzorec mapa

# Izpis pravic poleg imen datotek in map
tree -p mapa

# Izpis z velikostjo datotek
tree -s mapa
tree -h mapa # Bolj pregleden izpis

# Izpis do določene globine
tree -L globina mapa
```

Dokumentacija:

- [Dokumentacija 1](https://linux.die.net/man/1/tree)

### Ukaz: `nano`

Ukaz `nano` uporabimo, da uredimo vsebino tekstovne datoteke v terminalu.

Bližnjice:

- *CTRL+S* - Shrani trenutno datoteko
- *CTRL+O* - Shrani kot
- *CTRL-X* - Izhod
- *CTRL+K* - Cut
- *CTRL+U* - Paste
- *ALT+U* - Undo
- *ALT+E* - Redo

Primeri:

``` bash
# Uredimo vsebino datoteke
nano datoteka.txt
```

Dokumentacija:

- [Dokumentacija](https://linux.die.net/man/1/nano)
- [Bližnjice](https://www.nano-editor.org/dist/latest/cheatsheet.html)

### Ukaz: `cat`

Ukaz `cat` (concatenate) se uporablja za združitev vsebine datotek in izpis na standardni izhod.

Primeri;

``` bash
# Izpis vsebine datoteke
cat datoteka.txt

# Izpis datoteke v obratnem vrstnem redu vrstic
tac datoteka.txt
```

Dokumentacija:

- [Dokumentacija cat](https://man7.org/linux/man-pages/man1/cat.1.html)
- [Dokumentacija tac](https://man7.org/linux/man-pages/man1/tac.1.html)

### Ukaz: `grep`

Z ukazom `grep` izpišemo vrstice v datoteki, ki se ujemajo v našem vzorcu. Velikokrat ga uporabimo v kombinaciji z drugimi ukazi, kjer iščemo po standardnem vhodu namesto po datoteki.

Operatorji za ponovitev, ki se uporabljajo pri definiciji vzorca:

- `?` - predhodni element je opcijski in se ponovi največ enkrat
- `*` - predhodni element se lahko pojavi mnogokrat, lahko tudi ničkrat
- `+` - predhodni element se pojavi vsaj enkrat
- `{n}` - predhodni element se pojavi natanko n-krat
- `{n,}` - predhodni element se pojavi vsaj n-krat
- `{,m}` - predhodni element se pojavi največ m-krat
- `{n,m}` - predhodni element se pojavi vsaj n-krat in ne več kot m-krat

Definicije množice znakov:

- `[abcd]` - množica, ki vsebuje znake a, b, c in d
- `[a-z]` - množica, ki vsebuje znake "od a do z"

Primeri:

``` bash
# Iskanje vrstic v datoteki, ki vsebujejo ključno besedo
grep KljucnaBeseda datoteka.txt

# Kombinacija z ukazom cat
cat datoteka.txt | grep KljucnaBeseda

# Iskanje vzorca v datiteju
grep -E vzore+c datoteka.txt
```

Dokumentacija:

- [Dokumentacija](https://linux.die.net/man/1/grep)

### Ukaz: `sudo`

Z uporabo ukaza `sudo` lahko določen ukaz izvedemo kot, če bi ga izvedel drugi uporabnik ali pa superuser (root).

Primeri:

``` bash
# Poženemo ukaz kot administrator
sudo cat datoteka.txt

# Poženemo ukaz kot drug uporabnik
sudo -u user2 -g usergroup2 cat datoteka.txt
```

Dokumentacija:

- [Dokumentacija](https://linux.die.net/man/8/sudo)

### Ukaz: `wget`

**TODO: Opis + primer**

### Ukaz: `apt`

**TODO: Opis + primer (cache search, install, remove, purge, update, upgrade)**

### Okoljske spremenljivke

**TODO: Opis in seznam pogosto uporabljenih okoljski spremenljiv, primer definicije svojih**

## Datoteke in pravice

**TODO: Opis (user,group, others), pravice (r,w,x)**

### Ukaz: `whoami`

**TODO: Opis + primer**

### Ukaz: `chown`

**TODO: Opis + primer + /etc/passwd,/etc/shadow,/etc/group**

### Ukaz: `chmod`

**TODO: Opis + primer**

## Namestitev Minecraft strežnika

1. Namestimo Javo: `sudo apt install -y openjdk-8-jre`
2. Ustvarimo novega uporabnika: `sudo useradd -m -r -d /opt/minecraft minecraft`
3. Premaknemo se v `/opt/minecraft`: `cd /opt/minecraft`
4. Obiščemo https://www.minecraft.net/en-us/download/server in prenesemo najnovejšo verzijo serverja (preko brskalnika ali pa z `wget`): `sudo wget https://launcher.mojang.com/v1/objects/c8f83c5655308435b3dcf03c06d9fe8740a77469/server.jar`
5. Zaženemo server: `java -Xmx1024M -Xms1024M -jar server.jar nogui`
6. Potrdimo strinjanje z EULA: `echo "eula=true" | tee eula.txt`

Ker želimo server avtomatsko pognati ob ponovnem zagonu moramo za to uporabiti `systemd` storitve.

### Konfiguracija strežnika kot storitve: systemd

**TODO: Dodaj splošen info o systemd**

Ustvarimo datoteko `minecraft.service`: `sudo nano /etc/systemd/system/minecraft.service`

Vanjo zapišemo sledeče:
```conf
[Unit]
Description=Minecraft Server
After=network.target

[Service]
WorkingDirectory=/opt/minecraft
User=minecraft
Group=minecraft
Restart=always
ExecStart=/usr/bin/screen -dmS minecraft /usr/bin/java -Xmx1024M -Xms1024M -jar server.jar nogui
ExecStop=/usr/bin/screen -S minecraft -p 0 -X stuff "`printf \"stop\r\"`"

[Install]
WantedBy=multi-user.target
```

S strežnikom upravljamo s sledečimi ukazi:

``` bash
# Omogočimo zagon strežnika ob vklopu naprave (naredimo ob namestitvi)
sudo systemctl enable minecraft

# Zaženemo Minecraft strežnik
sudo systemctl start minecraft

# Ustavimo Minecraft strežnik
sudo systemctl stop minecraft
```

Če se želimo povezati na serverjevo konzolo zaženemo ukaz `screen -r minecraft`.
Ker ne želimo ustaviti serverja lahko iz konzole odidemo z ukazom: `Ctrl-a` + `d`.

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
