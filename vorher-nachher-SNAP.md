## Vorher-Nachher-Bilder generieren

1. Die Sentinel-Karten-Software SNAP installieren (Installationsdatei liegt zum Kopieren im Software-Ordner; 
geht nur mit Admin-Rechten)
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
1. Im Menü "Optical" den Unterpunkt *"Thematic Land Processing/Vegetation Radiometric Index/GNDVI Processor"* aufrufen. 
Dieses Programm errechnet aus den Spektren im sichtbaren und nicht sichtbaren Licht einen Vegetations-Index für jedes Pixel. 
1. Bevor wir den Prozessor starten können, müssen wir auf dem *"Processing Parameters"*-Tab einen Resampling-Modus auswählen, 
der die Bilddaten vereinheitlicht - am besten *"Highest Resolution"*. Dann den Prozessor starten.
1. Wieder zum interessanten Punkt zoomenn (Edersee etc.), A/B-Vergleich zum Ausgangsbild, ggf. Export der Vegetations-Karte über Rechtsklick. 
1. Die Erklärung für den "GNDVI" und den Unterschied zum TNDVI und NDVI aus der SNAP-Hilfe ziehen. 
Klüger geworden sein. :) 
