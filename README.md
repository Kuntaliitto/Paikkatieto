# Paikkatieto
Paikkatietoon liittyvää materiaalia

## Asemakaavan kuvaustekniikka

Asemakaavan kuvaustekniikka (CC BY 4.0). Kuvaustekniikka pohjautuu MRL:n asemakaavan visualisointioppaaseen (Ympäristönministeriö, 2003).

- [QGISin tyylitiedosto, xml](asemakaavan_kuvaustekniikka/asemakaavan_kuvaustekniikka.xml) (16.6.2020 versio 1.1)
- [SLD-visualisointikirjasto](asemakaavan_kuvaustekniikka/SLD)

<img src="asemakaavan_kuvaustekniikka/testiaineisto_asemakaavan_tyylit.png" width="500"/>

Toteutus Gispo Oy, kevät 2020. 

### Ohjeet XML:n käyttöönottoon QGISissä

HUOM! Kuvaustekniikka on tehty uusimmalla [QGIS-versiolla](https://qgis.org/en/site/forusers/download.html) (3.10 tai uudempi). 
Vanhoilla versioilla tyyli ei toimi, sillä aiempiin versioihin nähden tyylien määrittelyyn tullut huomattavasti muutoksia QGISissä. 
Osa tyyleistä vaatii dataa taakseen, kuten esimerkiksi "korttelin numero" tai "rakennuksen julkisivun korkeus". Huomaathan, että tyylikirjasto on pohja, jonka avulla voi kehittää omaa kaavan tyylikirjastoa. 
Esimerkiksi kaikkia kaavakohteita, joita kunnassa on käytössä, ei välttämättä löydy  MRL:n oppaasta ja siten ei myöskään tästä tyylikirjastosta.

1. Lataa [asemakaavan kuvaustekniikan](asemakaavan_kuvaustekniikka/asemakaavan_kuvaustekniikka.xml) sisältävä XML-tiedosto tietokoneellesi ja avaa QGIS. 

2. Mene **Asetukset > Tyylien hallinta** niin saat auki **Tyylien hallinta -ikkunan**. Klikkaa ikkunan vasemmasta alakulmasta **Tuo/Vie > Import Item(s)** ja valitse tuotavaksi tiedostoksi lataamasi XML-tiedosto. 
Klikkaa **Valitse kaikki** ja sitten **Tuo** niin saat kuvaustekniikan QGISiin.

3. Käytä omaa aineistoa ja luokittele aineistosi QGISin **Kuvaustekniikka-paneelissa** (saat sen näkyviin menemällä **Näytä > Paneelit > Kuvaustekniikka**). 
Määrittele haluamallesi kohteille sopivat tyylit. Muista, että kuvaustekniikka koostuu polygoneista, viivoista ja pisteistä. Pistemäiset tyylit **eivät** näy polygoneille ja toisinpäin.

4. Joihikin kohteisiin tarvitaan dataa taustalle, joten voit määrittää ne datan avulla toimimaan oikein. 

### Ohjeet SLD-kuvaustekniikan käyttöönottoon GeoServer-ohjelmistossa

Asemakaavan kuvaustekniikassa on käytetty standardimuotoista SLD-kuvaustekniikkaa, joten sen pitäisi toimia kaikilla kyseistä standardia tukevilla ohjelmistoilla. 
Kuvaustyylejä on testattu GeoServerillä, ja ohessa on ohjeet tyylien käyttämiseen siinä. 

Tyylitiedostot on jaettu neljään eri tiedostoon kaavakohteen tyypin mukaisesti: kaavayksiköt, osa-alueet, viivamaiset kohteet sekä pistemäiset kohteet. 


1. Lataa asemakaavan kuvaustekniikan sisältävät SLD-tiedostot tietokoneellesi:

[SLD-visualisointikirjasto](asemakaavan_kuvaustekniikka/SLD)

2. Kokeile esim. GeoServer-ohjelmistolla. 

[SLD-kuvaustekniikan tarkempi kuvaus sekä ohjelmistot, joissa siihen tuki](https://en.wikipedia.org/wiki/Styled_Layer_Descriptor). 





