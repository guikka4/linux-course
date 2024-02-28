# DJ Ango - Django!!

## Tiivistelmät

### Django 4 Instant Customer Database Tutorial (Karvinen, T. 2021)
- env - virtuaalinen kehitysympäristö, jota käytetään web-kehityksessä
- env:n kanssa ei käytetä sudoa, eikä pip-asennuksia tehdä ilman env:ä!
- djangon asennuksen kanssa tällä tavalla varmistuttava, että tosiaan ei ole typoja "django":ssa


### Deploy Django 4 - Production Install (Karvinen, T. 2021)
- Asennus muistuttaa hyvin pitkälti aiemmin kurssilla tehtyä Name Based Virtual Hostia, conffitiedosto on hieman erilainen
- Kun asennetaan djangoa, luodaan ensin env.
- Djangon ohjelmoinnit ovat projekteja, jokainen ominaan
- Python on tässä tapauksessa eräänlainen mooodi, jota käytetään Apachen sisällä

# Työskentely alkaa 28.2.2024 klo 16.45

## Käytössä oleva rauta
### Host OS
- Asus Tuf Gaming A15 FA506QM kannettava tietokone. Kone on tarkoitettu pelikäyttöön, ja on opiskeluolosuhteisiin ja tarkoitukseen nähden tehokas.
- Käyttöjärjestelmä: Windows 11 Home
- Prosessori: AMD Ryzen 7 5800H, 8 ydintä 3200GHz
- Muisti: 16 Gt
- Näytönohjain 6144Mt omalla muistilla
- Nettiyhteys mobiilidata

### Guest OS
- Debian bookworm - VirtualBoxin kautta asennettu
- RAM 4096MB
- 4 Prosessoriydintä
- Kovalevy 50GB

## VirtualEnv
- `sudo apt-get update` -> haetaan päivitykset
- `sudo apt-get -y install virtualenv` -> asennetaan virtualenv kehitysympäristöksi
- `mkdir django /home/user/` hakemistoon -> uusi kansio djangoprojekteille
- `virtualenv --system-site-packages -p python3 env/` -> luo env/ kansion ylle määritellylle polulle. Komento `system-site-packages` antaa ladata paketteja pythonia varten virtuaaliympäristön ulkopuolelta
- `source env/bin/activate` -> aktivoi virtuaaliympäristön. Prompti vaihtuu (env) alkuiseksi.
- `which pip` -> palauttaa `/home/pasih/django/env/bin/pip`, eli virtuaaliympäristössä ollaan
- `micro requirements.txt` -> "django" kirjoitetaan tähän tiedostoon. Siltä asennetaan kohta itse django. Tarkistetaan `cat requirements.txt`. Palauttaa oikein kirjoitetun "django":n joten asennetaan
![Add file: Upload](h6-django-asennus.png)
- `pip install -r requirements.txt` -> django asennus
- `django-admin --version` -> näyttää mikä django versio on latautunut. Eli django 5
![Add file: Upload](h6-django-version.png)
- 

## Lähteet
- Karvinen, T. 2022. https://terokarvinen.com/2022/deploy-django/
- Karvinen, T. 2022. https://terokarvinen.com/2022/django-instant-crm-tutorial/
- Karvinen, T. 2024. Tehtävänanto. https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/#h6-dj-ango
