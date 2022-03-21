# Vegova - delavnica Linux + Minecraft

## Virtualka

Da si skrajšamo čas priprave je na voljo [Ubuntu Server 20.04](https://drive.google.com/file/d/1uXuYXMLVn9_eMHHl0PMdLa4Gml0fesxc/view?usp=sharing) VM slika, ki jo bomo uvozili v VirtualBox.

| 1. Odpri VirtualBox in pritisni na gumb **Import** |
|:--------------------------------------------------:|
| ![1. import appliance](https://user-images.githubusercontent.com/46302511/159177482-6b227359-f42c-4d56-9997-660c6caf7732.png) |
| 2. Pritisni na gumb za izbiro datoteke |
| ![2. open file selector](https://user-images.githubusercontent.com/46302511/159177541-c7562cfa-fb4a-4c95-a5b1-f83b0b78841b.png) |
| 3. Izberi prenešeno datoteko |
| ![3. select file](https://user-images.githubusercontent.com/46302511/159177561-a0bc37ee-7851-4f4b-901c-6db29e756c2d.png) |
| 4. Pritisni **Next** |
| ![4. press next](https://user-images.githubusercontent.com/46302511/159177613-d53d6d27-e549-4186-9ac0-0331652702bd.png)
| 5. Pusti privzete nastavitve in pritisni **Import** |
| ![5. import image](https://user-images.githubusercontent.com/46302511/159177702-aeeb66ee-b9e6-4d45-9653-6d7c66bfd51d.png) |
| 6. Počakaj da se VM slika uvozi |
| ![6. wait for import](https://user-images.githubusercontent.com/46302511/159177681-c19eb7f5-cfca-40a9-b5a1-29ede0abd907.png) |
| 7. Zaženi VM s pritiskom na gumb **Start** |
| ![7. start vm](https://user-images.githubusercontent.com/46302511/159177715-b69853b6-5c4f-47f6-9146-d084a9ed266d.png) |
| 8. Počakaj dokler ne prideš do prijavnega zaslona |
| ![8. wait till login screen](https://user-images.githubusercontent.com/46302511/159177727-a372e99a-7461-40fd-8fec-f2395b1f8c81.png) |

**Informacije o VM**
- Uporabniško ime: `vegovec`
- Geslo: `vegovec`

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

Ukazna vrstica se začne s **pozivnikom (prompt)**  `student@stroj:~>`, kjer `student` predstavlja ime uporabnika (ki je odprl lupino), `stroj` predstavlja ime naprave, `~` pa predstavlja pot, kjer se trenutno nahajamo (`~` je okrajšava za `/home/<ime-uporabnika>`).

**Pogosto za prikaz vnašanja ukaza v ukazno vrstico pred ukazom vidimo kar skrajšan prompt in sicer simbol `>` ali `$`.
Enako bo v tem dokumentu. Se pravi, če vidimo ukaz ki se začne s simbolom `>`, pomeni, da ga vnesemo v ukazno vrstico,
simbol `#` predstavlja komentar, besedilo brez simbola pa predstavlja odgovor, ki ga vrne ukaz.
Ko ukaz vnesemo v ukazno vrstico, simbola `>` ne napišemo, ta je tukaj le za ilustracijo primera.**

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

### Ukaz: `echo` ([dokumentacija](https://linux.die.net/man/1/echo))

Z ukazom `echo` izpišemo podane parametre na zaslon. Z stikali lahko spremenimo stil izpisa.

``` bash
# Primer izpisa besedila
> echo "Besedilo"

# Primer izpisa brez končnega prehoda v novo vrstico
> echo -n "Brez nove vrstice"
```

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
> man printf

# Izpis določenega poglavja dokumentacije
> man 2 intro

# Izpis vseh dokumentacij, ki so na voljo za ukaz
> man -a intro

# Iskanje ključne besede po vseh dokumentacijah
> man -k cd

# Izpis lokacije, kjer se nahaja dokumentacija
> man -w ls

# Prikaz dokumentacije s tem, da pri imenu upošteva velikost črk
> man -I printf
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

### Ukaz: `ls` ([dokumentacija](https://man7.org/linux/man-pages/man1/ls.1.html))

`ls` (list directory contents) je program za izpis datotek v trenutnem ali želenem direktoriju.
Če ga zaženemo brez argumentov bo izpisal vsebino trenutnega direktorija, če pa mu na konec dodamo še ime nekega direktorija, pa bo izpisal vsebino le-tega.
Ker pogosto o izpisanih datotekah želimo vedeti več kot le ime, `ls` ponuja veliko koristnih argumentov.

Primer le nekaterih:
- `-l` oz. `--long`: izpiše dodatne informacije o datotekah (npr. velikost, lastnike, čas spremembe, ...)
- `-h` oz. `--human-readable`: izpiše velikosti datotek na lepši način (npr. 1K, 2G, ...)
- `-a` oz. `--all`: izpiši tudi skrite datoteke (te, ki se začnejo s `.`)

``` bash
# Izpis vsebine mape v kateri se trenutno nahajamo
> ls

# Izpis vseh datotek z dodatnimi informacijimi napisanimi na lepši način
> ls -lah

# Izpis druge mape
> ls /etc
```

### Ukaz: `cd` ([dokumentacija](https://man7.org/linux/man-pages/man1/cd.1p.html), [primeri uporabe](https://www.tecmint.com/cd-command-in-linux/))

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
> cd /

# Premik v domačo mapo trenutnega uporabnika
> cd ~

# Premik eno mapo višje
> cd ..

# Premik v sosednjo mapo
> cd ../sosednjaMapa
```

Ker je ukaz ugrajen v samo lupino, se do njegove dokumentacije pride z ukazom `man builtins`.

### Ukaz: `touch` ([dokumentacija](https://man7.org/linux/man-pages/man1/touch.1.html))

`touch` se uporablja za ustvarjanje praznih datotek, tako kot lahko v grafičnem vmesniku z desnim klikom ustvarimo novo datoteko.

Primeri:

``` bash
# Ustvarimo datoteko
> touch datoteka1
```

### Ukaz: `tree` ([dokumentacija](https://linux.die.net/man/1/tree))

`tree` se uporablja kot alternativa programa `ls`, saj tudi izpiše seznam datotek, a na hierarhičen način z zamaknjenimi vrsticami glede na globino direktorija.

Primeri:

``` bash
# Preprost izpis
> tree mapa

# Izpis tudi skritih datotek/map
> tree -a mapa

# Izpis zgolj map
> tree -d mapa

# Izpis celotne (relativne) poti do datotek
> tree -f mapa

# Izpis brez zamikov in drevesne strukture
> tree -i mapa

# Izpis datotek in map, ki ustrezajo vzorcu
> tree -P vzorec mapa

# Izpis pravic poleg imen datotek in map
> tree -p mapa

# Izpis z velikostjo datotek
> tree -s mapa
> tree -h mapa # Bolj pregleden izpis

# Izpis do določene globine
> tree -L globina mapa
```

### Ukaz: `nano` ([dokumentacija](https://linux.die.net/man/1/nano), [bližnjice](https://www.nano-editor.org/dist/latest/cheatsheet.html))

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
> nano datoteka.txt
```

### Ukaz: `cat` ([dokumentacija - cat](https://man7.org/linux/man-pages/man1/cat.1.html), [dokumentacija - tac](https://man7.org/linux/man-pages/man1/tac.1.html))

Ukaz `cat` (concatenate) se uporablja za združitev vsebine datotek in izpis na standardni izhod.

Primeri;

``` bash
# Izpis vsebine datoteke
> cat datoteka.txt

# Izpis datoteke v obratnem vrstnem redu vrstic
> tac datoteka.txt
```

### Ukaz: `grep` ([dokumentacija](https://linux.die.net/man/1/grep))

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
> grep KljucnaBeseda datoteka.txt

# Kombinacija z ukazom cat
> cat datoteka.txt | grep KljucnaBeseda

# Iskanje vzorca v datiteju
> grep -E vzore+c datoteka.txt
```

### Ukaz: `sudo` ([dokumentacija](https://linux.die.net/man/8/sudo))

Z uporabo ukaza `sudo` lahko določen ukaz izvedemo kot, če bi ga izvedel drugi uporabnik ali pa superuser (root).

Primeri:

``` bash
# Poženemo ukaz kot administrator
> sudo cat datoteka.txt

# Poženemo ukaz kot drug uporabnik
> sudo -u user2 -g usergroup2 cat datoteka.txt
```

### Ukaz: `wget` ([dokumentacija](https://linux.die.net/man/1/wget))

Z ukazom `wget` lahko prenesemo datoteko iz spletnega ali FTP strežnika.

Primeri:

``` bash
# Prenos datoteke s spletnega strežnika
> wget https://example.org/File.txt

# Prenos, kjer določimo ime ciljne datoteke
> wget -O File.txt https://example.org/File.txt

# Izpis statusa prenosa
> wget --progress=bar https://example.org/File.txt

# Timeout
> wget --connect-timeout=10 https://example.org/File.txt
```

### Ukaz: `apt` ([dokumentacija](https://linux.die.net/man/8/apt-get))

Ukaz `apt` se uporablja za upravljanje programov na distribuciji Ubuntu (in nekaterih drugih).

Primeri:

```bash
# Preverjanje posodobitev
> sudo apt update

# Posodabljanje programov
> sudo apt upgrade

# Odstranjevanje odvečnih programov (sirot - orphans)
> sudo apt autoremove

# Iskanje programa
> apt search imeprograma

# Nameščanje programa
> sudo apt install imeprograma

# Odstranjevanje programa
> sudo apt remove imeprograma # Odstrani samo program
> sudo apt autoremove imeprograma # Odstrani program in sirote
> sudo apt purge imeprograma # Odstrani program in sistemske konfiguracijske datoteke

# Posodabljanje sistema (preveri za posodobitve, naredi popolno nadgradnjo in odstrani sirote)
> sudo apt update && sudo apt full-upgrade -y && sudo apt autoremove -y
```

Za vajo uporabimo zadnji primer, da posodobimo sistem in na koncu po potrebi ponovno zaženemo VM (ukaz `reboot`).

### Okoljske spremenljivke

Okoljske spremenljivke so podobne spremenljivkam v programskih jezikih, njihov namen je da na krajši način zapišemo neko informacijo.
Eno okoljsko spremenljivko smo že spoznali pri poglavju o `pwd`.
Za prikaz okoljske spremenljivke lahko uporabimo kar ukaz `echo`: `echo $PWD`, kar nam bo vrnilo pot do trenutnega direktorija.
Dve pogosti okoljski spremenljivki sta še `$HOME`, ki se razširi v `/home/<uporabniško ime>` in `$PATH`, ki vsebuje poti do vseh izvedljivih programov v sistemu.

Primer:
```bash
# Izpis spremenljivke
> echo $HOME
/home/vegovec

# Definiranje svoje spremenljivke
> ime=vsebina
> echo $ime
vsebina
```

## Datoteke in pravice

Pogosto želimo dostop do nekaterih datotek ali direktorijev omejiti na določene uporabnike.
Privzeto ima vsak uporabnik na Linux distribucijah dostop samo do svojih datotek, datotek drugih uporabnikov pa ne more videti.

Obstajajo tri vrste pravic: **bralne** (`r` - read), **pisalne** (`w` - write) in **izvajalne** (`x` - execte za datoteke, `d` za direktorije),
vsaki datoteki (ali direktoriju) pa lahko določimo te pravice za tri skupine uporabnikov:
***lastnik** (`u` - user), **skupina** (`g` - group) in **ostali** (`o` - others).

Če zaženemo ukaz `ls -lah` v nekem direktoriju bomo dobili nekaj takega:
```
erazemk@t540p ~> ls -lah
total 0
drwx------.  5 erazemk erazemk 160 mar 21 19:27 .
drwxrwxrwt. 25 root    root    580 mar 21 19:27 ..
-rw-r--r--.  1 erazemk erazemk   0 mar 21 19:27 datoteka1
-rw-r--r--.  1 erazemk erazemk   0 mar 21 19:27 datoteka2
-rwxr-xr-x.  1 erazemk erazemk   0 mar 21 19:27 datoteka3
drwxr-xr-x.  2 erazemk erazemk  40 mar 21 19:27 mapa1
drwxr-xr-x.  2 erazemk erazemk  40 mar 21 19:27 mapa2
drwxr-xr-x.  2 erazemk erazemk  40 mar 21 19:27 mapa3
```

Vidimo lahko, da ima vsaka datoteka kot prvi stolpec zaporedje znakov (npr. `-rw-r--r--.`).
Le-te si lahko predstavljamo kot stolpce v tabeli.

Poglejmo si za primer vrstico datoteke 1.

Znak 1 (`-`) pove, da datoteka ni direktorij (so pa direktoriji vse mape).

Znaki 2-4 (`rw-`) se nanašajo na lastnika (prvi `erazemk`) in povejo, da ima ta bralne (`r`) in pisalne (`w`), ne pa izvajalnih (`-`) pravic
(datoteko 3 pa lahko tudi izvaja).

Znaki 5-7 (`r--`) se nanašajo na skupino (drugi `erazemk`), in povejo, da lahko ta datoteko samo bere.

Znaki 8-10 (`r--`) se nanašajo na ostale uporabnike in povejo, da lahko tudi te datoteko samo berejo.

Znak 11 (`.`) je uporabljen za druge lastnosti, v katere se ne bomo spuščali.

Vidimo lahko, da imajo vse tri mape omogočeno izvajanje za vse tri skupine uporabnikov.
V Linux sistemih je odpiranje mape ekvivalentno izvajanju, zato moramo direktorijem nujno pustiti izvajalne pravice,
če jih želimo odpreti.

### Ukaz: `whoami` ([dokumentacija](https://linux.die.net/man/1/whoami))

Ukaz `whoami` uporabimo za izpis uporabniškega imena trenutnega uporabnika.

Primer:
```bash
> whoami
vegovec
```

### Ukaz: `chown` ([dokumentacija](https://linux.die.net/man/1/chown))

Ukaz `chown` se uporablja za spreminjanje lastništva datoteke ali direktorija.
Spremenimo lahko tako lastnika kot tudi skupino.

Primeri:
```bash
# Dodeljevanje lastništva datoteke imedatoteke uporabniku in skupini vegovec
> chown vegovec:vegovec imedatoteke

# Dodeljevanje lastništva direktorija in vseh poddirektorijev
> chown -R vegovec:vegovec direktorij
```

**TODO: /etc/passwd,/etc/shadow,/etc/group**

### Ukaz: `chmod` ([dokumentacija](https://linux.die.net/man/1/chmod))

Ukaz `chmod` se uporablja za spreminjanje pravic dostopa do datoteke ali direktorija.

Poleg določanja pravic z uporabo črk, lahko na krajši način določimo pravice za vse skupine uporabnikov za datoteko s števili.
Tako skrajšamo zapis na le tri števke, prva za lastnika, druga za skupino, tretja pa za ostale uporabnike.
Da izračunamo katere pravice bi dodelili datoteki moramo vrste pravic sešteti.
Branje je vredno 4, pisanje 2 in izvajanje 1.

Tako na primer za branje in pisanje dobimo število 6 (4 + 2), za branje, pisanje in izvajanje 7 (4 + 2 + 1),
za pisanje in izvajanje 3 (2 + 1) itd.

Da bi nastavili pravice za določene skupine uporabnikov to storimo tako, da jih zapišemo zaporedno: `644`.
To pomeni da bo lastnik lahko datoteko bral in vanjo pisal (`6`), skupina in ostali pa jo bojo lahko samo brali (`4`).

```bash
# Nastavi pravice izvajanja za lastnika datoteke
> chmod u+x imedatoteke # + pomeni dodaj, - pa odvzemi

# Odvzemi pravico izvajanja za skupino datoteke
> chmod g-x imedatoteke

# Nastavi pravice branja in pisanja datoteke lastniku in skupini, a samo branja ostalim
> chmod 644 imedatoteke

# Nastavi pravice izvajanja, branja in pisanja lastniku in skupini, a samo branja in izvajanja ostalim
> chmod 755 imedatoteke

# Nastavi pravice na direktoriju in vseh poddirektorijih
> chmod -R 755 mapa # <-- PAZI! - če direktorij nima pravice izvajanja, ga ne moremo odpreti
```

Privzeto imajo direktoriji pravice `755`, datoteke pa `644`.

## Namestitev Minecraft strežnika

1. Namestimo Javo: `sudo apt install -y openjdk-8-jre`
2. Ustvarimo novega uporabnika: `sudo useradd -m -r -d /opt/minecraft minecraft`
3. Premaknemo se v `/opt/minecraft`: `cd /opt/minecraft`
4. Obiščemo https://www.minecraft.net/en-us/download/server in prenesemo najnovejšo verzijo serverja (preko brskalnika ali pa z `wget`): `sudo wget https://launcher.mojang.com/v1/objects/c8f83c5655308435b3dcf03c06d9fe8740a77469/server.jar`
5. Zaženemo server: `java -Xmx1024M -Xms1024M -jar server.jar nogui`
6. Potrdimo strinjanje z EULA: `echo "eula=true" | tee eula.txt`
7. Server nastavimo na offline način

Ker želimo server avtomatsko pognati ob ponovnem zagonu moramo za to uporabiti `systemd` storitve.

### Konfiguracija strežnika kot storitve: systemd

Systemd (system daemon) je administratorsko orodje, ki skrbi za izvajanje storitev na večini Linux distribucij.
Storitve lahko zažene, ustavi ali ponovno zažene, ponuja pa še množico drugih možnosti.
Zaradi kompleksnosti sistema se vanj ne bomo spuščali.

Vedeti moramo le, da če želimo upravljati Minecraft strežnik s pomočjo Systemd (kar je koristno, ker se lahko avtomatsko zažene ko ponovno zaženemo VM), moramo zanj ustvariti konfiguracijsko datoteko, ki jo Systemd zna brati.

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

Ko datoteko shranimo, lahko s strežnikom upravljamo s sledečimi ukazi:

``` bash
# Omogočimo zagon strežnika ob vklopu naprave (naredimo ob namestitvi)
> sudo systemctl enable minecraft

# Zaženemo Minecraft strežnik
> sudo systemctl start minecraft

# Ustavimo Minecraft strežnik
> sudo systemctl stop minecraft
```

Če se želimo povezati na serverjevo konzolo zaženemo ukaz `screen -r minecraft`.
Ker ne želimo ustaviti serverja lahko iz konzole odidemo z ukazom: `Ctrl-a` + `d`.

## Požarni zid `ufw` ([dokumentacija](https://help.ubuntu.com/community/UFW))

Privzeto ob namestitvi Ubuntu serverja ni nameščenega požarnega zidu, za to ga moramo namestiti sami.

Firewall oz. požarni zid je skupek programske opreme, ki skrbi za zaščito pri komunikaciji po omrežju. Ločuje dva odseka omrežij in med njima prepušča zgolj dovoljen promet, drug promet pa zavrne. V našem primeru ščiti aplikacije, ki tečejo na računalniku pred zunanjim nedovoljenim dosotopom.

Da zaščitimo naš strežnik bomo uporabili **ufw** (Uncomplicated firewall), saj omogoča enostaven konfiguracijski vmesnik. 

``` bash
# Namestitev
> sudo apt install ufw

# Pregled statusa
> sudo ufw status verbose
# icoming: promet od zunaj, ki dostopa do aplikacij
# routed: promet, ki potuje čez napravo do "drugih naprav" (naprava se obnaša kot usmerjevalnik)
# outgoing: promet, k ga ustvarjajo aplikacije na napravi, ko dostopajo do spleta

# Odpremo port za MineCraft server
> sudo ufw allow 25565/tcp

# Primer: Omogoči tcp in udp
> sudo ufw allow 53

# Primer: Omogoči promet določeni storitvi (/etc/services)
> sudo ufw allow SERVICENAME

# Primer: Onemogoči promet
> sudo ufw deny 53
> sudo ufw deny 53/udp

# Pregled statusa
> sudo ufw status verbose

# Omogoči požarni zid
> sudo ufw enable
```

Konfiguracijske datoteke se nahajajo na `/etc/ufw`.

## Povezovanje na Minecraft server

Ker smo server nastavili na offline način, se lahko nanj povežemo tudi brez plačljivega Minecraft računa, kar bomo storili s pomočjo aplikacije [TLauncher](https://tlauncher.org/en/).

| 1. Obišči [TLauncher spletno stran](https://tlauncher.org/en/), prenesi aplikacijo in jo zaženi |
|:-----------------------------------------------------------------------------------------------:|
| ![Screenshot from 2022-03-21 18-32-52](https://user-images.githubusercontent.com/46302511/159335389-ddc09e64-f641-4ada-ad21-f6b003ef1049.png) |
| ![Screenshot from 2022-03-21 18-33-06](https://user-images.githubusercontent.com/46302511/159335431-5276e02f-879f-4e56-8a97-152c0ad925ff.png) |
| 2. Vpiši želeno uporabniško ime (ni važno katero) in pritisni na gumb **Install** |
| ![Screenshot from 2022-03-21 18-34-07](https://user-images.githubusercontent.com/46302511/159335558-77c7ebff-9d97-4fb3-bd67-3f32f7027c45.png) |

Ko se bo Minecraft uspešno prenesel se bo avtomatsko zagnal, od tam naprej pa se verjetno že znate povezati na server.
