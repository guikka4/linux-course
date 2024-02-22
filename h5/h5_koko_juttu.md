# Koko juttu - alusta alkaen!
Tämän viikon tehtävänä on asennella uusi, tyhjä virtuaalikone, joka alustetaan aiemmin kurssilla tehtyyn tapaan. Virtuaalikoneelle asennellaan web-palvelin sekä SSH-etähallintapalvelin. Webpalvelimelle luodaan uusi kotisivu. Lisäksi kirjautuminen automatisoidaan julkisella SSH-avaimella. Näiden toimien jälkeen tutkitaan domain-nimen tietoja 'host' ja 'dig' komennoilla. Vapaaehtoisena tehtävänä on asentaa Vagrant, jonka avulla on helppo ja nopea luoda uusia virtuaalikoneita. (Karvinen, T. 20214)

Työskentely alkaa kotioloissa, torstai-iltana 22.2.2024 klo 19:05.

## Käytössä oleva rauta
### Host OS
- Asus Tuf Gaming A15 FA506QM kannettava tietokone. Kone on tarkoitettu pelikäyttöön, ja on opiskeluolosuhteisiin ja tarkoitukseen nähden tehokas.
- Käyttöjärjestelmä: Windows 11 Home
- Prosessori: AMD Ryzen 7 5800H, 8 ydintä 3200GHz
- Muisti: 16 Gt
- Näytönohjain 6144Mt omalla muistilla
- Nettiyhteys taloyhtiön ethernet

### Guest OS
- päivitetään myöhemmin, kun uusi virtuaalikone on luotu
- 

## Uuden virtuaalikoneen asennus. 22.2.2024 19:10-20:25 suunnilleen 20 minuutin tauolla
- Aloitetaan asentamalla VirtualBoxiin uusi kone. Ohjeita joudun selaamaan https://terokarvinen.com/2021/install-debian-on-virtualbox/.
- Nimi määritetty, asennuksen sijainti asetettu
- ISO kuvake (virtuaalinen asennuslevy) bongattu edellisestä sijainnistaan. 64-bit versio Debianista
- käyttäjänimi ja äärettömän hyvä salasana keksitty
- 4096MB muistia ja 4 prosessoriyhdintä käyttöön
- 50Gt dynaamista kovalevytilaa luodaan (ei varaa tallennustilaa, ellei sille ole tarvetta) -> tässä kohtaa voisin valita kovalevytilan jaettuna aiemmin luodulta virtuaalikoneeltani, mutta luon uuden.
- Vielä uuden virtuaalikoneen settingseistä lyödään boottilevyke sisään (ISO tiedosto) ja menoksi
- Hiiri, näppäimistö ja netti toimii.
- Ajetaan installer työpöydältä ja seurataan ohjeita. Muistetaan hyvä salasana, sekä nimi, joka ei ole tunnistettavissa (se on näkyvillä)

### Komentorivin toimet - ensimmäiset askelet uudella käyttiksellä
- haetaan päivitykset 'sudo apt-get update'
- asennetaan päivitykset 'sudo apt-get -y dist-upgrade' (-y vastaa "yes" kaikkiin kysymyksiin asennuksista)
- asennetaan palomuuri 'sudo apt-get -y install ufw' ja laitetaan se päälle 'sudo ufw enable' --> näiden jälkeen boottaus


  
- resoluution säätämiseksi asennetaan vielä VMGuestBoxAdditions ja käytetään terminaalissa komentoa 'sudo bash VBoxLinuxAdditions.run'
- testaus vielä boottauksen jälkeen, että kaikki toimii



## 


## Lähteet
- Karvinen, T. 2021. Debianin asennus. https://terokarvinen.com/2021/install-debian-on-virtualbox/
- Karvinen, T. 2024. Tehtävänanto. https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/