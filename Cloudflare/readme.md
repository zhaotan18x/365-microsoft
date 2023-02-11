# Cloudflare

Cloudflare, Inc. on yhdysvaltalainen yritys, joka tarjoaa sisällönjakeluverkkoa, DDoS-suojausta ja muita pilvipalvelua. Verkkosivusto, joka on otettu käyttöön, ei itse jaa sisältöään, vaan Cloudflare toimii sille käänteisenä välityspalvelimena.

Cloudfrale toimii kuin välittäjänä asiakkaan ja palvelimen välillä käyttämällä käänteisellä välityspalvelinta verkkosivustojen peilausta ja välimuistia. Sen tarkoituksena on vähentää latenssia, kaistanleveyttä ja sivuston latausaikaa, kun käyttäjät vierailevat verkkosivua. Cloudflare tarjoaa suuria DNS (doman name system)- ja julkisia DNS-selvityspalveluita. Molempia tarjotaan yksityisyyden ja nopeuden ensisijaisina vaihtoehtoina Internet-palveluntarjoajan DNS-palvelimille. Esim. jos käy haku sivustolla 1.1.1.1 palveluun, joka tukee minkä tahansa laitteen.

Cloudfrale tarjoaa myös DDoS-suojausta, sähköpostien lajittelua, verkkosovellusten palomuuria ja uhkien estämistä. 

![Alt text](images/cloudflare-2.png)

* [Domain servers](#Domain-servers)
* [DNS servers](#DNS-servers)
* [dns palomuuri](#dns-palomuuri)
* [Nameserver](#Nameserver)
* [Proxy status](#Proxy-status)
* [muita ohjeita](#muita-ohjeita)

## Domain nimi

Yleinen domain luonti / muokkaus muu vastaava

![Alt text](images/cloudflare-1.png width="200")

## DNS servers

Verkkokäyttöiset sovellukset, kuten selaimet, käyttävät jotain nimeltä Stub Resolver vuorovaikutuksessa DNS:n kanssa. Kun sovellus tai selain on saanut verkkosivuston IP-osoitteen, he voivat käyttää sitä HTTP- tai HTTPS-protokollien avulla.

DNS:llä on neljä tyyppistä kategoria nimipalvelimia (nameserver), josta ovat <b>DNS oma ratkaiseja </b> (resolver) <b> root:in </b>, <b> TDL:n </b> (top-level domain) ja <b> virallinen </b>(authoritative) nimipalvelimet.  Nämä neljä tyyppiset kategoriat toimivat yhdessä harmoniassa suorittakseen tehtävän toiminnan määritettyihin toimialueen IP-osoitteen käyttäjäille/asiakkaalle.

![Alt text](images/cloudflare-8.PNG)

## DNS palomuuri

Cloudflare:n dns palomuuri välittää kaikkiin DNS kyselyihin nimipalveluihin, josta cloudflare globaalin reunaverkon kautta (global edge network). Toiminnassa se suojaa ylävirran (upstream) nimipalvelun, josta DDoS-hyökkäystä ja vähentää kuormitusta tallentamall DNS-vastausta välimuistiinsa.

DNS-palomuuri on tarkoitettu asiakkaille, joiden on nopeutettava ja suojattava  kokonaisia arvovaltaisia nimipalvelimia (authoritative nameservers), ja suorittaa täys tai osittaisen auktorisointia/arvovaltaisen/standardin DNS:n asiakkaille, jolloin on nopeuttava ja suojattava yksittäisiä vyöhykkeitä.

Myös etuja DNS-palomuurissa on organisaatiot voivat hallita täysin arvovaltaisia nimipalvelimia: DDos lieventämistä, korkea saatavuus, globaali jakelua, parannettujen suorituskykyä, kaistanleveyden säästöä, dns-välimuistia, määrittää pien ja suuren TTL ja jne.

![Alt text](images/cloudflare-firewall-1.png)

## Nameserver

Suom. nimipalvelin, joka viittaa DNS komponentiin, että tärkeä osuus nimitiloissa (namespace) ja Internetissä. Tärkein tehtävänä se on DNS-palvelimen kuin käännös joka tukee <b> domain nimit (verkkotunnus esim. sivusto.fi) </b> ja <b> host/isäntä </b> IP-osoitteen (93.47.123.4), toisena päänimeä tilaa Internetin, joka  käytetään tietokonejärjestelmien ja -resurssien tunnistamista japaikantamista Internetissä. 

Periaatteessa nimipalvelin (nameserver) viittaa DNS:ään (Domain name system), ja sitä voi käyttää myös kaikissa tietokoneohjelmissa, jotka toteuttavat verkkopalvelun (network service)  ja niitä voi vastata hakemistonpalvelua (directory service) ja kääntää usein  inhimilliseen merkitykselliseen tekstiin.

![Alt text](images/cloudflare-5.PNG)



## Proxy status

Organisaatiolla on aina oma työkalu väline, jossa suoriuttuu joko kommunikointi/viestintä tai muu tärkeä väline kuten selaimien chätti kanava, bloggit, dokumenttien säilytys tai muu sovellus, että näillä on tärkeät dokumentit/infot.  

<b> Proxy status </b> tarkoittaa liikenteen osoitteenmuutosta, josta julkisesti liikenöityy <b> IP-osoite </b> joko <ins> yksittyisellä </ins> tai <ins> julkisella </ins> osoitteella. Cloudflare käsittelee tietuen tulevia liikenteitä, että ottaa käyttöön palvelimille A, AAAA ja CNAME tietuet. 

![Alt text](images/cloudflare-6.png)

DNS proxied (oranssi pilvi päällä) tarkoittaa, että näytettään Cloudflare IP-osoiteta A.B.C.D & Näin joten pitäisi kulkea Cloudflare järjestelmän lävitse, mitä tekee sivustosta nopeamman, turvallisemman ja älykkäämän. Sitä käytettään parhaiten subdomain eli aliverkkontunnuksien / alidomainta (testi.domain.fi)

Harmaa pilvi eli DNS Only tarkoittaa ei kulje Cloudflare:n ylitse, mitä eroaa pilvi päällä vai ei? Sitä käytettään jotka liittyy muuta kuin verkkoliikennettä kuten organisaatio yksityiset salaiset asiat / dokumentointi mm. sähköposti, ftp, ja ssh, eli tietoliikenneverkon protokollat ja muut salaiset käyttöön ottot. FTP - file transfer protocol.

![Alt text](images/cloudflare-7.png)


## muita ohjeita:

DNS serveri tyyppit (4kpl): <br>
https://www.cloudflare.com/learning/dns/dns-server-types/ <br>
https://blog.cloudflare.com/cloudflare-dns-is-simple-fast-and-flexible/ <br><br>

Perus cloudflare dns recordien ja muu domain luonti (tyhjästä alkaen): <br>
https://www.namecheap.com/support/knowledgebase/article.aspx/9607/2210/how-to-set-up-dns-records-for-your-domain-in-cloudflare-account/














