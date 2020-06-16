# Paikkatieto
Paikkatietoon liittyvää materiaalia

## Asemakaavan kuvaustekniikka

Asemakaavan kuvaustekniikka (CC BY 4.0)
- [QGISin tyylitiedosto, xml](asemakaavan_kuvaustekniikka/asemakaavan_kuvaustekniikka.xml) (16.6.2020 versio 1.1)
- [SLD-visualisointikirjasto](asemakaavan_kuvaustekniikka/SLD)

<img src="asemakaavan_kuvaustekniikka/testiaineisto_asemakaavan_tyylit.png" width="500"/>

Toteutus Gispo Oy, kevät 2020. 

### Ohjeet XML:n käyttöönottoon QGISissä

HUOM! Kuvaustekniikka on tehty uusimmalla [QGIS-versiolla](https://qgis.org/en/site/forusers/download.html) (3.10 tai uudempi). 
Vanhoilla versioilla tyyli ei toimi, sillä aiempiin versioihin nähden tyylien määrittelyyn tullut huomattavasti muutoksia QGISissä. 
Osa tyyleistä vaatii dataa taakseen, kuten esimerkiksi "korttelin numero" tai "rakennuksen julkisivun korkeus". 

1. Lataa XML-muotoinen tyylikirjasto koneellesi ja avaa QGIS. Kohdasta **Asetukset > Tyylien hallinta** avautuvassa paneelissa voit importoida (tuoda) 
XML-tyylin QGISiin. Valitse kaikki ja Tuo tiedot. 

2. Käytä omaa aineistoa ja luokittele aineistosi QGISin Tason tyylit-kohdassa. Määrittele haluamallesi kohteille sopivat tyylit. 
Muista, että tyylikirjasto koostuu polygoneista, viivoista ja pisteistä. Pistemäiset tyylit *eivät* näy polygoneille ja toisinpäin. 

3. Joihikin kohteisiin tarvitaan dataa taustalle, joten voit määrittää ne datan avulla toimimaan oikein. 

4. Huomaathan, että tyylikirjasto on pohja, jonka avulla voi kehittää omaa kaavan tyylikirjastoa. 
Esimerkiksi kaikkia kaavakohteita, joita kunnassa on käytössä, ei välttämättä löydy  MRL:n oppaasta ja siten ei myöskään tästä tyylikirjastosta.

### SLD 

[SLD-kuvaustekniikan tarkempi kuvaus sekä ohjelmistot, joissa siihen tuki](https://en.wikipedia.org/wiki/Styled_Layer_Descriptor). 

Kokeile esim. GeoServer-ohjelmistolla. 



