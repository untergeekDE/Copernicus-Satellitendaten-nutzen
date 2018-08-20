# Die Sentinel-Satelliten - eine Übersicht#

Derzeit (Stand: Sommer 2018) sind vier verschiedene Sentinel-Klassen in Betrieb: Sentinel-1, Sentinel-2, Sentinel-3 
und Sentinel-5P. Die ESA schießt aus Sicherheitsgründen und der besseren Abdeckung wegen in der Regel immer zwei
Satelliten einer Klasse ins All, zuletzt Sentinel-3B. Die beiden sind aus Nutzersicht wie ein Satellit, der häufiger
Daten liefert - und bessere. 

Die Satelliten 

Zum Verständnis der Original-ESA-Dokumentation ist das Abkürzungsverzeichnis sehr nützlich.

## Sentinel-1

##

Sentinel-1 ist ein Bodenradar. 
Es gibt zwei Sentinel-Satelliten, 1A (seit 2014) und 1B (seit April 2016). 
Der Satellit tastet den Boden in 250km breiten Streifen (swathes) ab; 
die Auflösung beträgt 5x20m. Außerdem tastet er im “Stripmap”-Modus einen 80km breiten 
Streifen mit einer Auflösung von 5x5m ab. Im “Extra Wide Swath”-Modus tastet er mit einer Auflösung von 20x40m ab. 

Anwendungsgebiete: Eis-Messung, Ölverschmutzung, Seewinde, Landveränderung

####Level-1-Produkte: 
##### SLC - Single-Look Complex
focused SAR data, geo-referenced using orbit and attitude data from the satellite, and provided in slant-range geometry. Slant range is the natural radar range observation coordinate, defined as the line-of-sight from the radar to each reflecting object. The products are in zero-Doppler orientation where each row of pixels represents points along a line perpendicular to the sub-satellite track.
##### GRD - Ground-Range Detection
products consist of focused SAR data that has been detected, multi-looked and projected to ground range using the Earth ellipsoid model WGS84. The ellipsoid projection of the GRD products is corrected using the terrain height specified in the product general annotation. The terrain height used varies in azimuth but is constant in range (but can be different for each IW/EW sub-swath).
####Level-2-Produkte:
##### OCN - Ocean
    Ocean Wind field (OWI)
    Ocean Swell spectra (OSW)
    Surface Radial Velocity (RVL)
Die Meeresdaten - mehr: https://sentinels.copernicus.eu/web/sentinel/user-guides/sentinel-1-sar/product-types-processing-levels/level-2

### Sentinel-2
Eine fliegende Kamera, die verschiedene Lichtspektren beobachtet - gerade die, die das menschliche Auge nicht sehen kann, und da
wird's interessant. ESA-Sprech: 
"SENTINEL-2 ist eine breitbandige, hochauflösende multispektrale Bildgebungs-Mission, die Copernicus Land Monitoring-Studien unterstützt, einschließlich der Überwachung von Vegetation, Boden und Wasser sowie der Beobachtung von Binnenwasserstraßen und Küstengebieten.
Das SENTINEL-2 Multispektral Instrument (MSI) wird 13 Spektralbänder erfassen: vier Bänder in 10 Metern, sechs Bänder in 20 Metern und drei Bänder in 60 Metern räumlicher Auflösung.
Die erhobenen Daten, Missionsabdeckung und hohe Wiederholungsfrequenz ermöglichen die Generierung von Geoinformationen auf lokaler, regionaler, nationaler und internationaler Ebene.
SENTINEL-2-Daten ergänzen bestehende Missionen, einschließlich LANDSAT (siehe Abbildung 1) und SPOT. Die Daten sind so konzipiert, dass sie von Nutzern geändert und angepasst werden können, die sich für Themenbereiche interessieren, wie:"
- Raumplanung
- Agrarumweltüberwachung
- Wasserüberwachung
- Überwachung von Wald und Vegetation
- Land Kohlenstoff, Überwachung natürlicher Ressourcen
- globale Ernteüberwachung

Die Daten umfassen:
- Bilddaten in Granulat oder Kacheln und das Produkt Area of ​​Interest (AOI) abdecken
- Vorschau-Daten, die einen Überblick über das Produkt für nachfolgende Bildsuche und Benutzerauswahl Zwecke bietet
- Zusatzdaten aus der Satellitentelemetrie
- Hilfsdateninformation, die die verwendeten Parameter beschreibt
- Qualitätsindikatordaten, die das Produkt in Bezug auf radiometrische, geometrische und Bildeigenschaften beschreiben.

####Level-2
##### BOA - Bottom of Atmosphere
Satellitenfotos. Eigentlich ein Kunstprodukt - das von der Sentinel-Toolbox (bzw. anderen "Prozessoren") aus den Level-1C-Produkten errechnet wird. https://sentinels.copernicus.eu/web/sentinel/user-guides/sentinel-2-msi/product-types/level-2a

### Sentinel-3

Sentinel-3 ist: 
- eine große Kamera
- ein Bodenradar
- ein fliegendes Thermometer. 

Oder, im ESA-Sprech: “SENTINEL-3 ist eine europäische Satellitenmission zur Erdbeobachtung, 
die entwickelt wurde, um GMES-Anwendungen in den Bereichen Ozean, Land, Atmosphäre, Notfall, Sicherheit und Kryosphäre zu unterstützen.”

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
####Level-2-Daten
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
