# Maailma kuulee

Tällä kertaa tutustun virtuaalipalvelimen vuokraamiseen, sekä web-palvelimen asennukseen sille. Tavoitteena on saada julkinen netissä näkyvä sivu aikaiseksi. Lisäksi sille on tarkoitus vuokrata nimi. Katsotaan mitä tulee, työskentely alkaa kotioloissa 11.2.2024 klo 22.45.

## Käytössä oleva rauta
### Host OS
- Asus Tuf Gaming A15 FA506QM kannettava tietokone
- Käyttöjärjestelmä: Windows 11 Home
- Prosessori: AMD Ryzen 7 5800H, 8 ydintä 3200GHz
- Muisti: 16 Gt
- Näytönohjain 6144Mt omalla muistilla
- Nettiyhteys taloyhtiön ethernet
### Guest OS- pyörii VirtualBoxin kautta
- Debian, 64-bit
- 4 prosessoriydintä
- 7981 Mt RAM

## Teoriasta käytäntöön
- Netistä voi vuokrata oman julkisen palvelimen. Nimenvuokraamalla voi osoittaa nimellä omaan palvelimeen
- Palvelin on syytä suojata palomuurilla hyökkäyksien hidastamiseksi
- Palvelimelle voidaan asentaa web-palvelin, tässä tapauksessa apache
- Palvelimen toimivuus varmistetaan päivittämällä kaikki palvelimen aplikaatiot
- (Lehto, S. 2022)
- Painokkaasti: Käytä aina pelkästään hyviä salasanoja! Salasanojen huonous johtaa helpommin tunkeutumisiin ja rikolliseen toimintaan
- Palvelimet, ja nimipalvelimet ovat kovasti kilpailtuja markkinoilla ja tarjolla on useita palveluntarjoajia
- SSH:lla otetaan etäyhteys vuokrattuun palvelimeen, omasta virtuaaliympäristöstä (tai raudalle asennetusta linuxista)
- Vuokrattu palvelin vaatii käyttäjien määrityksen
- Root-tunnus tulee sulkea
- Päivitykset, sekä palumuuri ovat ehdottomia. Palomuuriin tulee sallia SSH sekä paikallinen porttiyhteys, jotta palvelinta voidaan käyttää.
- (Karvinen, T. 2017)

## Virtuaalipalvelimen vuokraus
Tero Karvisen, sekä sekä edellisen oppitunnin perusteella päätin valita palveluntarjoajaksi materiaaleissakin löytyvän DigitanOceanin. Rekisteröinti sujuu aika mutkattomasti, mutta luottokortin lisäämisessä mainittu euron arvoinen liittymismaksu, sekä palvelun käyttötarkoituskysely ovat hieman häiritseviä. Enhän vielä ole ostanut mitään, kortiltani veloitetaan euro (vaikkakin lupauksen kera palauttaa katevaraus viikon sisällä). Joka tapauksessa, jatkan "Dropletien" kimppuun. Dropletit ovat älytön nimitys DigitalOceanille kutsua virtuaalikoneitaan. Virtual machine kuulostaisi verrattaen vaivalloiselta? Mutta, tämähän on vain markkinointikikka.

Valitsen virtuaalikoneeni sijainniksi EU-valtio Saksasta löytyvän Frankfurtin, käyttöjärjestelmäksi Debian 12, 64bit. Valitsen halvemmasta päästä olevan yhden prosessoriytimen, 25 gigan koneen. Mainiota! Tällä on hyvä lähteä eteenpäin. Sitten onkin aika valita root salasana, SSH määritellään myöhemmin. Mieleeni muistuu, että salasanan on oltava oikeasti vahva! Ja tottakai valitsen kaikki mahdolliset lisäpalvelut ja maksan itseni kipeäksi (en kai sentään). Muistan kuitenkin antaa hostnameksi simppelin nimen, jolla ei ole jäljitettävyyttä esimerkiksi käytettävään OS:ään. Sitten kliksuttelun jälkeen oma söötti droplettini onkin jo käynnissä. Siistiä!

## Lähteet
- Karvinen, T. 2017. First Steps on a New Virtual Private Server. https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/. Luettavissa 11.2.2024
- Lehto, S. 2022. Teoriasta käytäntöön pilvipalvelimen avulla (h4). https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/. Luettavissa 11.2.2024

