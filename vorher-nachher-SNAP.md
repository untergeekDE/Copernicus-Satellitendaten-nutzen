## Vorher-Nachher-Bilder generieren

**Die Aufgabe:** Einen Vorher-Nachher-Vergleich für eine Region erstellen, z.B. um die Auswirkungen des Hitzesommers zu zeigen (oder die Folgen einer Katastrophe). 

![Vorher-Nachher Rhein-Main-Region](https://raw.githubusercontent.com/untergeekDE/Copernicus-Satellitendaten-nutzen/master/vorher-nachher-snapshot.PNG "Vorher-Nachher-Vergleich - contains Copernicus data")

*Eine Vorher-Nachher-Visualisierung des Rhein-Main-Gebiets mit zusätzlichen Vegetationsdaten [Link zur Live-Version](https://cdn.knightlab.com/libs/juxtapose/latest/embed/index.html?uid=ea327c8a-ad1c-11e8-9dba-0edaf8f81e27)*

Dafür nutzen wir Bilder des ["Sentinel-2"-Satelliten der ESA/EU](https://de.wikipedia.org/wiki/Sentinel-2), der seit 2016 Daten liefert. Seine Multispektral-Kamera liefert Bilder mit einer Auflösung von 10x10m pro Pixel (im sichtbaren Bereich; sonst z.T. etwas geringer). Die "Sentinel"-Daten kann man - wie alle des ["Copernicus"-Programms der EU](http://copernicus.eu/) - kostenlos nutzen, allerdings ist es etwas umständlich, an sie zu kommen. 

Dieses Tutorial hilft bei den ersten Schritten. 

### Schummeln: Zielgebiet und Datum finden

Das slowenische Startup Sinergise bietet einen Dienst an, auf dem man die Satellitenbilder ohne technischen Aufwand betrachten kann - den [Sentinel Hub Playground](https://apps.sentinel-hub.com/sentinel-playground/), die Demo des kommerziellen Angebots über API. Hier fangen wir an: 

1. Den [Sentinel Hub Playground](https://apps.sentinel-hub.com/sentinel-playground/) aufrufen.
1. Ein interessantes Zielgebiet aussuchen. (Wir bleiben erst einmal bei der Standardeinstellung: "Natural bands", das sichtbare Licht, so wie es unser Auge auch wahrnehmen würde.)
1. Für das Zielgebiet zwischen verschiedenen Aufnahmedaten hin- und herschalten - über das Kalender-Symbol. Es ist leider manchmal nicht ganz einfach, eine Aufnahme ohne Wolken zu finden - und dann sieht logischerweise auch der Satellit nichts. 
1. Die Daten für "vorher" und "nachher" notieren. 

### Die Satelliten-Daten suchen, ziehen, verarbeiten

1. Die [kostenlose Sentinel-Karten-Software SNAP](http://step.esa.int/main/download/) installieren (die gibt es für Windows, Mac und angeblich auch Linux)
1. Das Sentinel-Data-Hub ansteuern: https://scihub.copernicus.eu/ - Open Data Hub ansteuern und eigenes Konto anlegen.
1. Der möglicherweise schwierigste Schritt: Geeignete Daten finden. Dazu in den Einstellungen auswählen:
*Datumsbereich* - am besten ein ganzer Monat - Häkchen bei *"Mission: Sentinel-2"* (das ist der mit der Kamera), 
unter "Product Type" die Auswahl *"S2MSI1C"*. 
1. Feststellen, dass die ESA einen mit ihren Abkürzungen wahnsinnig machen kann [und das AKÜVERZ herunterladen](https://sentinels.copernicus.eu/documents/247904/383991/SUHET+Acronyms).
1. Damit kann man dann auch das "Product Type"-Kürzel entschlüsseln: **"S2..."=Sentinel-2-Satellit** 
(es gibt übrigens zwei davon, die sich abwechseln); **"...MSI..."=Multi-Spectral Instrument, also: Spektralkamera**, 
"...1C" steht für den **"Product Level"**, den Verarbeitungsgrad der Daten. Die 1C-Daten sind Kamerabild-Geodaten, 
an das Standard-Erdmodell WGS84 angepasst, die sich ohne Probleme in SNAP und auch in QGIS laden lassen - kurz: **Satellitenfotos**. 
1. Im Open Data Hub ein möglichst kleines Quadrat um Frankfurt (oder einen anderen Ort) ziehen und auf die "Suchen"-Lupe klicken. 
1. Einen Treffer auswählen, durch einen Klick auf das Augen-Symbol in der Vorschau prüfen und - 
falls interessant und wolkenfrei - herunterladen. ACHTUNG: Dateien sind jeweils zwischen 800MB und 1,2GB groß - 
man braucht Platz auf dem Laufwerk! Datei nach dem Download entpacken (am besten per Drag&Drop auf ein lokales Laufwerk). 
1. SNAP starten. *"File/Open Product"* anwählen, in den heruntergeladenen Daten-Ordner navigieren, die XML-Datei MTD_MSIL1C.xml 
(oder so) öffnen
1. In den "Product Explorer" gehen, den Ordner "Bands" anwählen - da stecken die eigentlichen Daten drin, sortiert nach 
"Bändern", also Frequenzspektren.
1. Machen wir zum Beispiel mal das Rotlicht-Bild der Kamera auf: Doppelklick auf B4.
1. Das Bild ist schwarzweiß - also Klick auf die "Colour Manipulation"-Toolbox, dann die Schwarzweiß-Skala in eine 
Rot-Skala ändern. 
1. Das Rot-Bild wieder schließen. Im Product Explorer das Wurzelverzeichnis anklicken, dann im Menü "Window"
den Punkt *"Open RGB Image Window"* auswählen. SNAP generiert jetzt aus den Bändern B2 (blau), B3 (grün) und B4 (rot) ein Farbfoto. Gegebenenfalls übers “Colour Manipulation” anpassen. 
1. Das gleiche jetzt auch noch mit einem zweiten Satellitenbild, das 14 Tage/3 Monate/1 Jahr vorher aufgenommen wurde. Je nachdem. 
1. Im Menü "View" ein Häkchen bei “Synchronise Image Views” setzen. 
Die geöffneten Bilder sind jetzt verknüpft - zoome ich in einem Bild an ein Gebiet heran, ist es automatisch auch
im anderen Fenster angewählt. 
1. Das nutzen wir jetzt: mit Lupe und Schiebe-Hand eins der Satellitenbilder zu was Interessantem zoomen 
(z.B. den Edersee oder den Flughafen). Hin- und Herklicken zwischen den Fenster-Tabs schaltet zwischen Vorher-Nachher hin und her. 
1. In beiden Fenstern nacheinander: Rechtsklick auf das Satellitenbild und *"Export View as Image"* auswählen.

### Bonuslevel: Vegetationskarte erstellen
1. Im Menü *"Optical"* den Unterpunkt *"Thematic Land Processing/Vegetation Radiometric Index/NDVI Processor"* aufrufen. Dieses Programm errechnet aus den Spektren im sichtbaren und nicht sichtbaren Licht einen Vegetations-Index für jedes Pixel. 
1. Das Tab *"Parameters"* anwählen und für *Resampling* "Highest Resolution" einstellen - da die Daten der Infrarotkamera nur mit einer 60x60m-Auflösung vorliegen, müssen erst Zwischenwerte für die fehlenden Pixel errechnet werden, um die Bilder übereinanderlegen zu können). Prozessor starten.
1. Prozessor-Fenster schließen, das neu erstellte Produkt im Explorer öffnen und das Band *"nvdi"* anzeigen lassen. 
1. Die Erklärung für den NDVI und den Unterschied zum TNDVI und GNDVI aus der SNAP-Hilfe ziehen. Wer Zeit hat: ein wenig wissenschaftliche Literatur über den NVDI googeln. 
1. Klüger geworden sein. :)
1. Colour Management öffnen - und den MERIS-Veg-Index laden (Braun- und Grüntöne).
1. Gesunde Vegetation hat einen Index von irgendwo zwischen 0,2 und 1,0 - je nach Bewuchs. Den untersten (braunen) Schieber im Colour-Management-Histogramm auf 0,3 schieben, dann anklicken und “None” auswählen - so werden nur Werte von 0,3 als grüne Pflanze angezeigt 
1. Wieder zum interessanten Punkt zoomen, A/B-Vergleich zum Ausgangsbild, Export der Vegetations-Karte über Rechtsklick als PNG. 
1. Import der Echtfarben- und der Vegetationskarte in den Photoshop, übereinanderlegen, NDVI-Index auf 70% Transparenz. 
 "GNDVI" und den Unterschied zum TNDVI und NDVI aus der SNAP-Hilfe ziehen. 

### Challenge mastered!
![Satellitenfoto Rhein-Main August 2018 - contains Copernicus data](https://raw.githubusercontent.com/untergeekDE/Copernicus-Satellitendaten-nutzen/master/ffm-2018-composite.png)
