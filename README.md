# Paikkatieto
Paikkatietoon liittyvää materiaalia

## Asemakaavan kuvaustekniikka

Asemakaavan kuvaustekniikka (CC BY 4.0). Kuvaustekniikka pohjautuu MRL:n asemakaavan visualisointioppaaseen (Ympäristönministeriö, 2003).

- [QGISin tyylitiedosto, xml](asemakaavan_kuvaustekniikka/asemakaavan_kuvaustekniikka.xml) (28.5.2020 versio 1.1)
- [SLD-visualisointikirjasto](asemakaavan_kuvaustekniikka/SLD) (16.6.2020 versio 0.1)
- [SLD-kuvaustekniikan tarkempi kuvaus sekä ohjelmistot, joissa siihen tuki](https://en.wikipedia.org/wiki/Styled_Layer_Descriptor). 

<img src="asemakaavan_kuvaustekniikka/testiaineisto_asemakaavan_tyylit.png" width="500"/>

Toteutus Gispo Oy, kevät 2020. 

## Yleiskaavan kuvaustekniikka

Yleiskaavan kuvaustekniikka (CC BY 4.0). Kuvaustekniikka pohjautuu MRL:n Yleiskaavakaavamerkinnät ja -määräykset-oppaaseen (Ympäristönministeriö, 2003). 

- [XML-muodossa QGISin kuvaustyyli (versio 1.1, 21.8.2020)](yleiskaavan_kuvaustekniikka.xml)
- [SLD-kuvaustekniikka](SLD)

<img src="yleiskaavan_kuvaustekniikka/yleiskaava.png" width="500"/>

### Ohjeet XML:n käyttöönottoon QGISissä

HUOM! Kuvaustekniikat on tehty uusimmalla [QGIS-versiolla](https://qgis.org/en/site/forusers/download.html) (3.10 tai uudempi). 
Vanhoilla versioilla tyyli ei toimi, sillä aiempiin versioihin nähden tyylien määrittelyyn tullut huomattavasti muutoksia QGISissä. 
Osa tyyleistä vaatii dataa taakseen, kuten esimerkiksi "korttelin numero" tai "rakennuksen julkisivun korkeus". Huomaathan, että tyylikirjasto on pohja, jonka avulla voi kehittää omaa kaavan tyylikirjastoa. 
Esimerkiksi kaikkia kaavakohteita, joita kunnassa on käytössä, ei välttämättä löydy  MRL:n oppaasta ja siten ei myöskään tästä tyylikirjastosta.

1. Lataa [asemakaavan kuvaustekniikan](asemakaavan_kuvaustekniikka/asemakaavan_kuvaustekniikka.xml) tai [yleiskaavan kuvastenkiikan](yleiskaavan_kuvaustekniikka/yleiskaavan_kuvaustekniikka.xml) sisältävä XML-tiedosto tietokoneellesi ja avaa QGIS. 

2. Mene **Asetukset > Tyylien hallinta** niin saat auki **Tyylien hallinta -ikkunan**. Klikkaa ikkunan vasemmasta alakulmasta **Tuo/Vie > Import Item(s)** ja valitse tuotavaksi tiedostoksi lataamasi XML-tiedosto. 
Klikkaa **Valitse kaikki** ja sitten **Tuo** niin saat kuvaustekniikan QGISiin.

3. Käytä omaa aineistoa ja luokittele aineistosi QGISin **Kuvaustekniikka-paneelissa** (saat sen näkyviin menemällä **Näytä > Paneelit > Kuvaustekniikka**). 
Määrittele haluamallesi kohteille sopivat tyylit. Muista, että kuvaustekniikka koostuu polygoneista, viivoista ja pisteistä. Pistemäiset tyylit **eivät** näy polygoneille ja toisinpäin.

4. Joihikin kohteisiin tarvitaan dataa taustalle, joten voit määrittää ne datan avulla toimimaan oikein. 

### Ohjeet asemakaavan SLD-kuvaustekniikan käyttöönottoon GeoServer-ohjelmistossa

Asemakaavan kuvaustekniikassa on käytetty standardimuotoista SLD-kuvaustekniikkaa, joten sen pitäisi toimia kaikilla kyseistä standardia tukevilla ohjelmistoilla. 
Kuvaustyylejä on testattu GeoServerillä, ja ohessa on ohjeet tyylien käyttämiseen kyseisellä ohjelmistolla. Vastaavalla tavalla saat aki myös yleiskaavan kuvaustekniikan.

HUOM! Oletuksena on, että GeoServerille tuotujen tasojen ominaisuustiedoista löytyy sarake **ak_merk**, joka määrittää kaavakohteen tyypin  MRL:n oppaan numeroinnin mukaisesti, 
ja jonka perusteella kohteiden tyylit määräytyvät. Käytännössä myös osaan kaavakohteista liittyy datasta määräytyviä arvoja (esim. tontin numero, meluvallin desibeliarvo jne.). 
Yhteinäisten attribuutti-nimitysten puuttuessa, nämä merkinnät on toteutettu oppaan merkintöjä jäljittelevinä esimerkkimerkintöinä, joskin ohjeet datasta määräytyvien arvojen käyttöön löytyvät alla olevasta luvusta.     

1. Lataa asemakaavan kuvaustekniikan sisältävät [SLD-tiedostot](asemakaavan_kuvaustekniikka/SLD)
 tietokoneellesi. Tyylitiedostot on jaettu neljään eri tiedostoon kaavakohteen tyypin mukaisesti: 

- kaavayksiköt (MRL:n oppaan merkinnät 1-81), 
- osa-alueet (merkinnät 113-125, 127-128, 133-134, 136-138, 140-158, 161-162, 166-172, 174-183, 185-189) 
- viivamaiset kohteet (82-90, 126, 129-132, 135, 139, 159-160)
- pistemäiset kohteet (91-112, 163-165, 173, 184)

2. Kirjaudu GeoServerille. Oletuksena on, että visualisoitavat aineistot on jo sinne lisätty. Avaa päävalikon alta **Data**-valikosta kohta **Styles**. Tallenna GeoServerille uusi tyyli painamalla **Add New Style**. Aseta kohdan **Style Data** -kohdan alle perustiedot eli nimi tyylille (**Name**), mihin **Workspaceen** tyyli liitetään sekä varmista että kuvaustekniikan muotona (**format**) on SLD. Lataa koneelle tallentamasi tyylitiedosto kohdasta **Style Content** sekä **Choose File**. Tiedosto valittuasi muista myös painaa valintanapin oikealta puolelta **Upload...** (kts. kuva). **Validate**-napista voi tarkistaa ettei ladattu SLD sisällä virheitä sekä **Layer Preview** -välilehdeltä voi esikatsella tyyliä eri tasoilla. Paina **Submit** tallentaaksesi tyylin.

3. Ladatun tyylin voi asettaa oletustyyliksi halutulle tasolle **Publishing**-välilehdeltä ja laittamalla kyseiselle tasolle ruksin **Default**-kohtaan. Tämän valinnan voi tehdä myös **Data**-valikosta kohdasta **Layers** ja valitsemalla sieltä halutun tason **Publishing**-välilehdeltä kohdasta **Default Style** ladattu tyyli.

<img src="asemakaavan_kuvaustekniikka/geoserver_new_style_screenshot.PNG" width="500"/>

### Datan määrittämät visualisoinnit SLD:ssä

Kuten edellä on mainittu, osa kaavamerkinnöistä vaatii syötteen/inputin kaavakohteiden ominaisuustiedoista, ja tällaisten kohteiden kuvaustyylit on tehty MRL:n oppaan mukaisiksi esimerkinomaisiksi tyyleiksi, joissa kyseisten ominaisuuksien arvot ovat 123, ABC jne. SLD-tyylien rakenteessa tällaiset arvot liittyvät **Label**-tagiin, johon kyseinen oletusarvo on nyt siis asetettu. Kyseisen tagin sisälle on kuitenkin myös kirjoitettu koodia, jolla Label-tagiin voidaan lukea kohteiden ominaisuustiedoista tuleva arvo. Tähän tarkoitukseen on käytetty **PropertyName**-tagia ja sen saa käyttöön seuraavasti: 

- Koodi on oletuksena kommentoitu pois käytöstä (eli se on merkkien \<!-- ja \--> välissä). SLD-tiedostoa voi muokata kuten mitä tahansa tekstitiedostoa, eli avaa ensin kyseinen tiedosto esimerkiksi Notepad++-ohjelmalla tai GeoServerin Style Editoriin.

- Etsi tyylitiedostosta merkintä (eli siis **Rule**-tag), jonka arvojen haluat määrittyvän suoraan datasta. Merkinnät ovat tiedostossa numerojärjestyksessä ja esimerkiksi **Name**-tag **MRL_ak_100** tarkoittaa MRL:n oppaan asemakaavamerkintää numero 100. Name-tagia seuraava **Title**-tag kertoo tämän myös sanallisesti. 

- Etsi kyseisen merkinnän Label-tag ja editoi merkkien \<se:Label> ja \</se:Label> välissä olevaa koodia. Poista oletusarvo (123 tai vastaava) ja poista myös PropertyName-tagin ympärillä olevat kommenttimerkit, eli \<!-- ja \-->. Kirjoita merkkien \<ogc:PropertyName> ja \</ocg:PropertyName> väliin ominaisuustieto-tekstin tilalle se tason ominaisuustietosarakkeen nimi, josta arvon pitäisi määräytyä. Tallenna muutokset.






