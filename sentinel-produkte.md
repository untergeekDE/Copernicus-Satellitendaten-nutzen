

# Die Sentinel-Satelliten - eine Übersicht #

Derzeit (Stand: Sommer 2018) sind vier verschiedene Sentinel-Klassen in Betrieb: Sentinel-1, Sentinel-2, Sentinel-3 
und Sentinel-5P. Die ESA schießt aus Sicherheitsgründen und der besseren Abdeckung wegen in der Regel immer zwei
Satelliten einer Klasse ins All, zuletzt Sentinel-3B. Die beiden sind aus Nutzersicht wie ein Satellit, der häufiger
Daten liefert - und bessere. 

Sentinel-2 ist der Satellit, der die derzeit hochauflösendsten offenen Daten liefert - für die optischen Bänder (also: für das, was unsere Augen sehen) mit einer Auflösung von 10m; ein Pixel im Bild entspricht also einer Fläche von 10x10m. 

## ESA verstehen

Ubedingt einen Blick in das [Abkürzungsverzeichnis](https://github.com/untergeekDE/Copernicus-Satellitendaten-nutzen/blob/master/SUHET%20Acronyms.pdf) werfen.

## Nutzungsbedingungen

vergleichbar einer CC-BY-Lizenz - weit gehende Verarbeitungs- und Nutzungsrechte unter korrekter Attribution: 

- Originaldaten: mit Copyright-Zeichen - so: **"©Copernicus data (year of reception)"** (Dann dürfen wir sie auch teilen.)
- Abgeleitete Werke: **"contains Copernicus data (year of reception)"**, für uns also: **"Basiert auf Copernicus-Satellitendaten (2016-2018)"**

[PDF mit den Bedingungen](https://scihub.copernicus.eu/twiki/pub/SciHubWebPortal/TermsConditions/TC_Sentinel_Data_31072014.pdf)

## Die Datensätze: Produkte

Die nützlichste ESA-Seite: https://scihub.copernicus.eu/userguide/

Die Satelliten haben meist mehrere Instrumente an Bord. Sie tasten die Erde in großen Streifen ab, während der Satellit sie überfliegt, und liefern verschiedene Datensätze - die so genannten **Produkte**. Diese Produkte gibt es in verschiedenen Verarbeitungszuständen ("Level")

### Produkt-"Level"

* Level 0: Sensor-Rohdaten (die Daten, so wie sie kommen - nicht oder nur wenig geeicht und entzerrt)
* Level 1: Korrigierte Geodaten, meist schon in Kartenform 
* Level 2: Errechnete Daten: etwa Wasser-Temperaturdaten, die aus Infrarotaufnahme und Umgebungsbedingungen erstellt werden

## Daten verwenden

### Geodaten nutzen 

Gute Einführung: https://github.com/PatrickStotz/mapping_101

### Tools

- Von der ESA: SNAP, die "Sentinel Application Platform". [Tutorial-Seite auf der "Science Toolbox Exploitation Platform" (STEP)](http://step.esa.int/main/doc/tutorials/snap-tutorials/).
- QGIS, ein Open-Source-Tool zur Visualisierung von Geodaten. [Hier ein Geodaten-Tutorial einer Consultingfirma](https://www.lutraconsulting.co.uk/blog/2017/11/02/working-with-climate-data-in-qgis/).
- [Benutzerhandbuch SENTINEL CODE-DE (PDF)](https://code-de.org/de/manuals/CD-UM-3301DE_Benutzerhandbuch_v1.1_online.pdf)
- [Die FAQ zur Web-API](https://software.ecmwf.int/wiki/display/WEBAPI/Web-API+FAQ) der ECMWF (s.o.)

### Daten laden

- wohl in der Regel im Datenformat NetCDF (ein Datenformat, das bei Meteorologen üblich ist)
- Die Dateien sind in der Regel mehrere GB groß
- Beim ECMWF gibt es auch aufgearbeitete Daten, u.a. Prognosen - allerdings kann man die nicht einfach herunterladen, sondern muss sich einen Downloader als Python-Skript zusammenklicken. Siehe unten: ECMWF
- In der Regel: Anmeldung erforderlich. 

### Tutorial

* [Schritt-für-Schritt-Anleitung für einen Vorher-Nachher-Vergleich](https://github.com/untergeekDE/Copernicus-Satellitendaten-nutzen/blob/master/vorher-nachher-SNAP.md)

Netterweise hat EUMETSAT Demo-Videos erstellt, die bei den ersten Schritten helfen - anhand des Beispiel-Produkts "Meerestemperatur-Daten": 

* [Video 1: SNAP nutzen](https://www.youtube.com/watch?v=l4oeRYj6_5U)
* [Video 2: Eine Seetemperatur-Karte erstellen](https://www.youtube.com/watch?reload=9&v=lKyUeN3uS0Q)

# Aufgearbeitete Daten

Partner nutzen, um Daten vorbereitet zu bekommen?

## Sentinel Hub

Ein slowenisches Startup namens Sinergise, das mit dem ["Sentinel Hub Playground](https://apps.sentinel-hub.com/sentinel-playground/) ein einfaches Tool zur Nutzung von (vor allem) Sentinel-2-Daten gebaut hat. 

## ECMWF

Unterbehörde der ESA in Großbritannien, die Wetterdaten - und im Katastrophenfall: Missionsdaten z.B. von Hafenanlagen und brennenden Wäldern - liefern soll. 

Die ECMWF tut interessante Dinge - und man kommt an viele Daten über eine API (bzw. über ein Python-Downloader-Skript, das man sich zusammenklicken muss.)

### Beispiele für Anwendungsfälle 

Im Sommer 2018 aus einer Präsentation des ECMWF beim Wissenschaftsjournalismus-Tag in Darmstadt herausgelauscht. 

- [Luftverschmutzungs-Prognosekarten des ECMWF (PDF)](https://www.ecmwf.int/sites/default/files/elibrary/2005/15822-air-quality-forecasting.pdf)
- [Eine Warn-App für Allergiker und Asthmatiker](https://atmosphere.copernicus.eu/pioneering-personalised-allergy-medicine)
- [Vorhersage-App für Wetter, Luftgüte (Ozon etc.), Luftdruck etc.](https://pflotsh.com/en/ecmwf.html)
- [Eine UV-Warnkarte (des australischen Cancer Council Victoria)](https://atmosphere.copernicus.eu/sunsmart)
- [Die Luftqualitäts-Vorhersage bei Euronews](https://de.euronews.com/wetter/copernicus-air-quality-index)


Viel Raum für praktische Erfahrungen!

Erstkontakt: die dortige Pressestelle. Ist zwar prinzipiell auch im Mindset "Wir liefern euch schöne bunte Bildchen"-Mindset unterwegs, kann aber im Prinzip schon mal was mit dem Wort Datenjournalismus anfangen. 

* [Die FAQ zur Web-API der ECMWF](https://software.ecmwf.int/wiki/display/WEBAPI/Web-API+FAQ)

# Die Satelliten und ihre Produkte

Die Level-0-Daten sind für uns nicht nutzbar, die Level-1-Daten müssen mit Vorsicht und Unterstützung von Fachleuten interpretiert werden. Daher werden wir in der Regel Level-2-Produkte nutzen.

Hier der Versuch einer Übersicht, was die Satelliten liefern und wozu man sie einsetzen könnte: 

## Sentinel-1
 
Sentinel-1 ist ein fliegendes Bodenradar. 

Es gibt zwei Sentinel-Satelliten, 1A (seit 2014) und 1B (seit April 2016). 
Der Satellit tastet den Boden in 250km breiten Streifen (swathes) ab; 
die Auflösung beträgt 5x20m. Außerdem tastet er im “Stripmap”-Modus einen 80km breiten 
Streifen mit einer Auflösung von 5x5m ab. Im “Extra Wide Swath”-Modus tastet er mit einer Auflösung von 20x40m ab. 

Anwendungsgebiete: Eis-Messung, Ölverschmutzung, Seewinde, Landveränderung.

### Produkte

#### Level 1: SLC - Single-Look Complex
ESA: "focused SAR (=Synthetic Aperture Radar) data, geo-referenced using orbit and attitude data from the satellite, and provided in slant-range geometry. Slant range is the natural radar range observation coordinate, defined as the line-of-sight from the radar to each reflecting object. The products are in zero-Doppler orientation where each row of pixels represents points along a line perpendicular to the sub-satellite track."

#### Level 1: GRD - Ground-Range Detection
ESA: "These products consist of focused SAR data that has been detected, multi-looked and projected to ground range using the Earth ellipsoid model WGS84. The ellipsoid projection of the GRD products is corrected using the terrain height specified in the product general annotation. The terrain height used varies in azimuth but is constant in range (but can be different for each IW/EW sub-swath)."

#### Level-2: OCN - Ocean
Die Meeresdaten - mehr: https://sentinels.copernicus.eu/web/sentinel/user-guides/sentinel-1-sar/product-types-processing-levels/level-2
- Ocean Wind field (OWI)
- Ocean Swell spectra (OSW)
- Surface Radial Velocity (RVL)

## Sentinel-2

Eine fliegende Kamera, die mit zwei Kamerasystemen verschiedene Lichtspektren beobachtet - gerade die, die das menschliche Auge nicht sehen kann, und da wird's interessant - weil man sie für Umweltanalyse einsetzen kann: Vegetation, Boden, Bodenschätze, Ernte, Wasser - ganz besonders auch Verkehr auf dem Wasser. 

Das SENTINEL-2 Multispektral Instrument (MSI) beobachtet 13 Spektralbänder erfassen, mit verschiedenen Auflösungen: vier Bänder in 10 Metern, sechs Bänder in 20 Metern und drei Bänder in 60 Metern räumlicher Auflösung.ildeigenschaften beschreiben.

#### Level-2: BOA - Bottom of Atmosphere

Satellitenfotos. Eigentlich ein Kunstprodukt - das von der Sentinel-Toolbox (bzw. anderen "Prozessoren") aus den Level-1C-Produkten errechnet wird, und in verschiedenen Layern einen Haufen Informationen enthält.

Leider sind die Details offenbar tief in der Dokumentation versteckt. 

Allgemeine ESA-Information: "Level-2A product provides orthorectified Bottom-Of-Atmosphere (BOA) reflectance, with sub-pixel multispectral registration. A Scene Classification map (cloud, cloud shadows, vegetation, soils/deserts, water, snow, etc.) is included in the product."

[ESA-Produktseite](https://sentinels.copernicus.eu/web/sentinel/user-guides/sentinel-2-msi/product-types/level-2a)

### Sentinel-3

Sentinel-3 ist: 
- eine große Kamera
- ein Bodenradar
- weil der Satellit auch aufs Infrarotspektrum schaut, ein fliegendes Thermometer. 

Wenn ich es richtig verstehe, wird der Satellit zwar vom ESOC geflogen und gemanaged, für die Meeresdaten (also alles, was OCLI und SLSTI über wasser liefern) ist irritierenderweise [EUMETSAT zuständig].(https://www.eumetsat.int/website/home/Copernicus/Sentinels/index.html)

Datensätze: 
- Wärmedaten, 
- Oberflächentemperatur
- Oberflächenprofil (Radar-Abtastung erkennt Berge, Täler, Gebäude?)
- Wassertemperatur
- Kameras, die Vegetationen erkennen

Sentinel-3 besteht aus 2 Systemen: 
- OLCI (Ocean Land Colour Instrument), einer Multiband-Kamera https://sentinels.copernicus.eu/web/sentinel/technical-guides/sentinel-3-olci/olci-instrument
- SLSTI (Sea and Land Surface Temperature Radiometer), einem Bodenradar https://sentinels.copernicus.eu/web/sentinel/technical-guides/sentinel-3-slstr/instrument/description

####Level-1-Daten

(tbd)
####Level-2-Daten

(tbd) 
##### 
#####
#####
#####

    SL_2_WCT gathers the results from the Sea Surface Temperature (SST) processing (see algorithms), i.e. SST (single and dual view, 2 and 3 channels). This product is an internal product and is not available to users.
    SL_2_WST gathers the results from L2P processing (see algorithms), i.e. the GHRSST like L2P SST.
    SL_2_LST gathers the results from Land Surface Temperature (LST) processing (see algorithms), i.e. the LST.
    SL_2_FRP gathers the results from Fire Radiative Power (FRP) processing (see algorithms), i.e. the FRP.
    SL_2_AOD gathers the results from Aerosol Optical Depth (AOD) processing (see algorithms), i.e. the AOD
    
    OLCI:
https://sentinels.copernicus.eu/web/sentinel/technical-guides/sentinel-3-olci/level-2/products-description

### Sentinel-5P
Misst Atmosphärengase und Aerosole; kann also Aussagen über die Luftqualität und über Atmosphärenbedingungen 
(Wolken!) liefern. “This means that a wide range of pollutants such as nitrogen dioxide, ozone, formaldehyde,
sulphur dioxide, methane and carbon monoxide can be imaged more accurately than ever before.
With a resolution as high as 7 km × 3.5 km, it has the potential to detect air pollution over individual cities.”

Datensätze:
Ausgewertete Daten über Atmosphärendaten - Level 2 (liegen mit 5 Tagen Verzögerung vor) 
- Methan
- Ozon
- SO2 Stickoxid

## Level-2-Produkte

# Sentinel-4

Luftgüte-, Atmosphären- und Klima-Sensoren (O3, Stickoxid)...

[Sentinel-4-Basisinfo der ESA](https://sentinel.esa.int/web/sentinel/missions/sentinel-4)

...muss noch ausgewertet werden. Ist der Satellit überhaupt schon in der Luft??? Zu fliegen scheint ihn EUMETSAT. 

# Sentinel-5

Ein hochauflösendes fliegendes Spektrometer. Soweit ich es sehe, noch nicht gestartet. 

[Sentinel-5-Basisinfo der ESA](https://sentinel.esa.int/web/sentinel/missions/sentinel-5)

# Sentinel-5P (Precursor)

Ein Satellit zur Atmosphären-Beobachtung; ein Radar zur Wolkenbeobachtung soll erlauben, Gebiete auszumaskieren, die von Wolken verdeckt sind. 2017 gestartet, geht erst jetzt allmählich in den Regelbetrieb. 

[Sentinel-5P-Basisinfo der ESA](https://sentinel.esa.int/web/sentinel/missions/sentinel-5p)

# Sentinel-6

Präzisions-Altimeter (Höhenmesser) zur Beobachtung der Meere: Erlaubt genaueste Messung der Meeresspiegel. Scheint noch nicht in Betrieb zu sein. 

[Sentinel-6-Basisinfo bei EUMETSAT](https://www.eumetsat.int/website/home/Satellites/FutureSatellites/CopernicusSatellites/Sentinel6JasonCS/index.html)
