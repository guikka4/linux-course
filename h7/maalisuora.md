# Maalisuoralla !
Tällä viikolla on varsinainen viimeinen viikkotehtävä. Tehtävä sisältää 
- a) käännöksen "Hei maailma"
- b) Kaikilla käyttäjillä ajettavissa oleva komento 
- c) Vanhan labraharjoituksen rakaiseminen soveltuvin osin 
- d) Uuden virtuaalikoneen asennuksen ja päivittämisen sekä palomuurin asennuksen
- (Karvinen, T. 2024)

## Käytössä oleva rauta
### Host OS
- Asus Tuf Gaming A15 FA506QM kannettava tietokone. Kone on tarkoitettu pelikäyttöön, ja on opiskeluolosuhteisiin ja tarkoitukseen nähden tehokas.
- Käyttöjärjestelmä: Windows 11 Home
- Prosessori: AMD Ryzen 7 5800H, 8 ydintä 3200GHz
- Muisti: 16 Gt
- Näytönohjain 6144Mt omalla muistilla
- Nettiyhteys taloyhtiön ethernet

### Guest OS
- Debian bookworm - VirtualBoxin kautta asennettu
- RAM 4096MB
- 4 Prosessoriydintä
- Kovalevy 50GB

# Työskentely 9.3.2024 klo 10:15-11:30
## a) Hei, maailma pythonilla
- `micro hello.py` -> loin tämän nimisen tiedoston kotihakemistooni. Kuvakaappauksessa lopputulos

- `#!/usr/bin/python3`
- `print("Hello, world!")`

![Add file: Update](h7_helloworld.png) ![Add file: Upload](h7-hello2.png)

## b) Ajettava komento kaikille käyttäjille. Käytän shelli scriptiä esimerkkiin
- `micro test1.sh` -> tiedosto kotihakemistoon. Scritpi sisältää kuvakaappauksen komennot
- `#!/usr/bin/bash` -> mahdollistaa scriptin ajon mistä tahansa
- `pwd` -> näyttää tämänhetkisen hakemistopolun
- `ls`-> listaa hakemistokansion sisällön
- `whoami` -> näyttää käyttäjän
- `hostname` -> näyttää tietokoneen nimen
- `date --iso=min` -> näyttää pvm ja kellonajan
- `cat test1.sh` -> tulostaa test1.sh tiedoston sisällön komentoriville

![Add file: Update](h7-test1sh.png)

- `bash test1.sh` -> koklaillaan ensin hakemistossa miten toimii. Toimii

![Add file: Update](h7-bashtesti1.png)

- `chmod ugo+x test1.sh` -> annetaan ajo-oikeus kaikille käyttäjille
- `sudo cp test1.sh` /usr/local/bin/` -> tiedoston siirto kansioon, josta se on ajettavissa kaikkialta
- `ls /usr/local/bin` -> tsekataan että siellä se on

![Add file: Update](h7-local.png)

- `./test1.sh` -> testataan vielä että scripti toimii. Toimii
- `test1.sh` -> kokeillaan vielä muulla hakemistopolulla, tässä tapauksessa rootissa. Toimii

![Add file: Update](h7-test2sh.png)

## d) Uuden virtuaalikoneen asennus labraa varten 9.3.2024 12:00-
- 64-bit debian bookworm
- 6gb RAM
- 4 prosessoriydintä
- 40gb kovalevytilaa
- äärettömän hyvät salasanat
- Näppis, hiiri ja netti toimii joten työpöydältä Debianin asennus seuraavaksi
- Kieleksi amerikan englanti, käyttöalueeksi Suomi ja näppäpimistö suomalaiseksi
- Nimi ja muut tiedot sekä älytön salasana
- -> install ja odotellaan hetki
- guest additions asennus jotta resoluutio skaalautuu ja näyttö on nätimpi.
- Devices->VBox kuvake -> Terminaaliin `cd /media/*/VBox*` -> `sudo bash VBoxLinuxAdditions.run` -> Restarttia ja kaikki toimii
- (Karvinen, T. 2021)

### Virtuaalikone käyttökuntoon labraa varten
- `sudo apt-get update` -> päivitysten haku
- `sudo apt-get -y dist-upgrade` -> päivitysten asennus
- `sudo apt-get -y install ufw` -> palomuurin asennus
- `sudo ufw enable`-> palomuuri päälle -> `Firewall is active and enabled on system startup`

## c) Vanhan labraharjoituksen teko. Tällä haavaa suuria aikatauluhaasteita. Toivon, että ehdin tekemään ennen arvioitavaa loppuharjoitusta!

## Lähteet
- Karvinen, T. 2021. Virtuaalikoneen asennus. https://terokarvinen.com/2021/install-debian-on-virtualbox/
- Karvinen, T. 2024. Tehvtävänanto. https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/#h7-maalisuora
