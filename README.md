# Portable Ground Station - 📡 PGS 🛰️

v0.0.0 - Fase documental

## Objetivo

Creación de una estación terrestre para la conexión con satélites, permitiendo recibir y enviar información en función de las posibilidades que ofrezcan los mismos.

## Proyectos de redes receptoras

| Red de Estaciones Receptoras | [TinyGS](https://tinygs.com/) | [SatNOGS](https://satnogs.org/) |
| ------------- | ------------- | ------------- |
| Tipo de servicio | Recepción datos del satélite | Recepción datos del satélite | Conexión limitada a Internet vía satélite |
| Limitaciones del servicio | Autoconfigurado al satélite más cercano | Asignación manual de los próximos pases | Capacidad Máx. de descarga de 200MB/día |
| Satélites emisores| [Listado oficial](https://tinygs.com/satellites)  | [Listado oficial](https://db.satnogs.org/satellites/)  
| Rango Frecuencias Recibidas | 137, 433, 868-915, 2400  | [Múltiples rangos](https://db.satnogs.org/stats)  |
| Modos de Transmisión Recibidos | LoRa | [Múltiples modulaciones](https://db.satnogs.org/stats)  |

- Nota: + Info TinyGS https://www.youtube.com/watch?v=6_csJlAhj-U

## Listado de satélites

* ### [Othernet](https://othernet.is/)
Conexión limitada a internet vía satélite: datos metereológicos, noticias, Wikipedia, radio y APRS Radio data. Capacidad máxima de descarga de 200 MB/día. TIene hardware propio: Othernet Dreamcatcher y LNB.

| Nombre | COSPAR ID | Frecuencias | Órbita |
| ------------- | ------------- | ------------- | ------------- |
| SES-2 | 2011-049A | ------------- |Geoestacionario | Othernet América del Norte |
| Astra 3B | 2010-021A | ------------- |Geoestacionario | Othernet Europa |


* ### Meteorológicos

| Nombre | COSPAR ID | Frecuencias | Órbita |
| ------------- | ------------- | ------------- | ------------- |
| NOAA 15 | 1998-030A | Señal APT: 137,620 MHz | ------------- |
| NOAA 18 | 2005-018A | Señal APT: 137,9125 MHz | ------------- |
| NOAA 19 | 2009-005A | Señal APT: 137,100 MHz | ------------- |

* ### De radioaficionados
| Nombre | Canal FM | Transpondedor Lineal (SSB / CW)
| ------------- | ------------- |------------- |
| AO-27 | SI¿frecuencias? |------------- |
|SO-50 (SaudiSat-1C)| SI¿frecuencias? |------------- |
|AO-92| |------------- |Si ?¿frecuencias, modulaciones? |


En función de la modulación:
Canal FM: utilizan la modulación de frecuencia para la transmisión/recepción de señales. Simplex/Duplex (transmisión/recepción en diferentes frecuencias). Voz.
Transpondedor Lineal (SSB / CW): pueden manejar múltples señales simultáneamente en bandas estrechas de frecuencias. Modulación de banda lateral única. Voz alta calidad y datos baja velocidad.
    Single Side Band - SSB
    Continuous Wave - CW
Modos Digitales: permiten varias técnicas de modulación y codificación digital. Modos como BPSK (Phase Shift Keying), QPSK, y otros.Permiten la transmisión de datos, correo electrónico (a través de servicios como PACSAT), y otros modos digitales como APRS (Automatic Packet Reporting System).

[AMSAT](https://www.amsat-ea.org/informaci%C3%B3n/) - Satélites de radioaficionados
+ info: https://www.amsat-ea.org/sat%C3%A9lites-activos/
+ info: https://amsat.org/status/
+ https://www.amsat.org/status/

## Localización y seguimiento de satélites

* ### Software de seguimiento de satélites
[Gpredict](https://oz9aec.dk/gpredict/)

* ### Archivos TLE (Two-Line Element)
Representan parámetros keplerianos, los cuales describen la órbita de un satélite alrededor de la Tierra.
Ejemplo:
```
ISS (ZARYA)
1 25544U 98067A   20067.54791667  .00016717  00000-0  10270-3 0  9003
2 25544  51.6442  69.6564 0007241  3.8045 356.3187 15.49101164213792
```
Línea 1:

    Número de línea (1): Siempre será 1 para la primera línea.
    Número de catálogo del satélite (25544): Identificador único del satélite.
    Código de clasificación (U): U = Unclassified (No clasificado).
    Número de lanzamiento y fragmento (98067A): Año de lanzamiento (98 para 1998), número de lanzamiento (067) y fragmento del lanzamiento (A).
    Época (20067.54791667): Año y día del año con decimales (2020, día 67.54791667).
    Derivada del medio movimiento (0.00016717): Cambio en la tasa de movimiento medio.
    Segunda derivada del medio movimiento (00000-0): Cambio en la tasa de la primera derivada.
    *Coeficiente de arrastre b (10270-3)**: Coeficiente que representa el efecto del arrastre atmosférico.
    Ephemeris type (0): Tipo de efemérides (generalmente 0).
    Número de elemento (9003): Número de identificación de este conjunto de elementos.

Línea 2:

    Número de línea (2): Siempre será 2 para la segunda línea.
    Número de catálogo del satélite (25544): Mismo que en la primera línea.
    Inclinación orbital (51.6442): Inclinación de la órbita en grados.
    Ascensión recta del nodo ascendente (69.6564): Ángulo del nodo ascendente en grados.
    Excentricidad (0007241): Excentricidad de la órbita (decimal sin punto, debe interpretarse como 0.0007241).
    Argumento del perigeo (3.8045): Ángulo del perigeo en grados.
    Anomalía media (356.3187): Ángulo de la anomalía media en grados.
    Movimiento medio (15.49101164): Número de revoluciones por día.
    Número de revolución (213792): Número de revoluciones completas desde el lanzamiento.

Fuentes de archivos TLE:
https://www.celestrak.com/

Generar tus propios archivos TLE personalizados:
https://github.com/albertomn86/TLEGenerator
https://sdr-es.com/generar-archivo-TLE/

* ### Modelo matemático SGP4 (Simplified General Pertubations 4)
Se usa para predecir las posiciones y velocidades de satélites en órbita terrestre baja (LEO). Desarrollado por NORAD en la década de 1980, es una mejora de los anteriores como SGP, SGP2 y SGP3. Usa los parámetros de los TLE para calcular la posición del satélite en cualquier momento posterior a la época dada.

## Radio definida por software (SDR)

* ### Hardware
https://sdr-es.com/eleccion-sdr/
* ### Software
https://www.sdrpp.org/

## Antenas

* Parabólicas: + info https://axessnet.com/la-antena-satelital-de-comunicaciones-como-funciona-y-cuales-son-sus-tipos/

## Decodificar señales
WXtoIMG (Weather Satellite Decoder?)

## (en contrucción)
* Othernet: Servicio de acceso a determinada información de Internet desde satélites geoestacionarios: Datos 
  * Bibliografía:
    * https://github.com/Othernet-Project/Dreamcatcher
    * https://github.com/McOrts/OTHERNET_GroundStation
    * https://www.youtube.com/watch?v=8H49Vyqkftg
    * https://www.youtube.com/watch?v=KPsQn06TM4M
    * https://www.youtube.com/watch?v=0F57ARpZFig
    * https://www.rtl-sdr.com/outernet-dreamcatcher-setup-with-ads-b-dump1090-and-piaware-tutorial/

* NOAA
  * Satélites:
    * NOAA 15 - COSPAR ID: 1998-030A - Señal APT: 137,620 MHz
    * NOAA 18 - COSPAR ID: 2005-018A - Señal APT: 137,9125 MHz
    * NOAA 19 - COSPAR ID: 2009-005A - Señal APT: 137,100 MHz
  * Hardware necesario
    * Antena cuadrifilar
      * (Alternativa) Antena v-dipolo de 77M-1GHz (aprox. 1m)
    * (Opcional) Filtro de paso de banda de sierra de 137 MHz (SAW_137,5 MHz) y amplificador de bajo ruido (LNA)
    * RTL-SDR
  * Software necesario
    * Sofware seguimiento satélites
    * Software generación imagenes?
      * WXtoImg - https://wxtoimgrestored.xyz/downloads/ 
    * Software para SDR
      * SdrSharp - https://airspy.com/download/ 
  * Bibliografía:
    * https://www.youtube.com/watch?v=L6SJ9ZFXSc4

## Enlaces de interés
* https://www.rtl-sdr.com/
* https://sdr-es.com/
* https://www.amsat-ea.org/
* https://www.mdpi.com/2673-4001/5/1/12
