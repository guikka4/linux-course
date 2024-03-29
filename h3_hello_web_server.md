# Hello Web Server
Työskentelyn kesto 18:11-20:20 2.2.2024. Työskentely tapahtuu perjantai-iltana kotioloissa, omalla kannettavalla tietokoneella. Vapaaehtoiset tehtävät jäävät tällä istumalla nyt tekemättä, palaan niihin uudella energialla paremmalla ajalla.

## Käytettävä tietokone
- Asus Tuf Gaming A15 FA506QM kannettava tietokone
- Käyttöjärjestelmä: Windows 11 Home
- Prosessori: AMD Ryzen 7 5800H, 8 ydintä 3200GHz
- Muisti: 16 Gt
- Näytönohjain NVIDIA GeForce RTX 3060 laptop, 6144Mt omalla muistilla
- Nettiyhteys tällä kertaa puhelimelta jaettu mobiilidatayhteys.

  ## Name-based Virtual Host Support
- IP-osoitepohjaisessa hostaamisessa yhteys isäntään määritellään IP-osoitteen perusteella. Jokainen isäntä tarvitsee oman IP-osoitteen.
- Nimipohjaisessa taas palvelin tarvitsee isännälle määritellyn nimen, jotta osaa ohjata käyttäjän oikeaan osoitteeseen.
- Nimipohjaisella isännöinnillä voidaan käyttää samaa IP-osoitetta monille sivustoille, jos palvelin konfiguroidaan ohjaamaan kävijä oikealle sivustolle nimen perusteella.
  
![Add file: Upload](h3_virtual_host_config.png)

- Paikallisesti voidaan luoda localhost-sivusto, jota testata ennen tuotantoon menoa.

## Weppipalvelimen testaus localhostilla

![Add file: Upload](h3_curl_localhost.png)

## Loki
Otin lokin less -N komennolla. Käytin apache2:n access.logia. Se ei kuitenkaan näyttänyt kuin 30.1. tapahtumia, eikä tuoreimpia, vaikka käynnistin selaimessakin localhostin. Joka tapauksessa, kuvakaappauksen rivit 1 ja 2 näyttävät, että sivusto vastaa normaalisti (HTTP/1.1 200). https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html. Rivissä 1 näkyy curl, ja rivissä 2 näkyy selaimen kautta ladattu sivu. ip-osoite on localhost-ip osoite.

![Add file: Upload](h3_access_log.png)

## Etusivu uusiksi
Ensin luodaan hattu.conf tiedosto sudoeditillä.

![Add file: Upload](h3_hattu_conf.png)

Sitten suljetaan käynnissä oleva webbipalvelin joka luotiin tunnilla komennolla a2dissite. Sen jälkeen sudo restarttia apachelle, ja vanha koira poistuu käytöstä. Kuitenkin apache heittää localhostilla vakioetusivunsa, vaikka sivusto ei näy sites-enabledissa. Enabloin myös uuden hattu sivuston ja potkin uudelleen apachen restartille.

![Add file: Upload](h3_dissite_koira.png)![Add file: Upload](h3_dissite_koira_restart.png)![Add file: Upload](h3_hattu_enabled.png)

Tämän jälkeen luon uuden kansion polulle, jonka konffitiedostoon kirjoitin.
Sitten vielä index.html filu sisään testiä koneeseen.

![Add file: Upload](h3_hattu_test1.png)
![Add file: Upload](h3_hattu_test2.png)

## HTML5 -sivu
Muokkasin hattu.comin html5 muotoon. Edellisestä HTML sivun tekemistä on aikaa, joten lunttaus oli paikallaan. https://terokarvinen.com/2012/short-html5-page/

![Add file: Upload](h3_html5.png)
![Add file: Upload](h3_html_firefox.png)

## Curl komennot
Curl komennoilla saadaan näkyville (esimerkissä curl localhost) -> tekstitietona webbisivu. curl -I näyttää sitten yksityiskohtaisemmat tiedot, ja otsakkeet luettavasta tiedosta.

![Add file: Upload](h3_curl_i.png)


### Päivitys
6.2.2024 klo 14. Rakenneltu html sivu uudelleen w3 validointityökalun avulla. Muokattu metatietoa sekä lisätty ääkköset. Validointi tuloksena antaa vielä herjan kieliasetuksesta, millä ei tässä kohtaa ole merkitystä.

![Add file: Upload](h3_html_paivitys.png)![Add file: Upload](h3_html_paivitys2.png)


## Lähteet
- https://httpd.apache.org/docs/2.4/vhosts/name-based.html
- https://terokarvinen.com/2012/short-html5-page/
- https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
- https://terokarvinen.com/2024/linux-palvelimet-2024-alkukevat/#h3-hello-web-server
- https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html
- https://validator.w3.org/
