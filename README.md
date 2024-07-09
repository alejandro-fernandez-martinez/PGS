# Portable Ground Station - 📡 PGS 🛰️

v0.0.0 - Fase documental

## Objetivo

Creación de una estación terrestre para la conexión con satélites, permitiendo recibir y enviar información en función de las posibilidades que ofrezcan los mismos.

## Material (en contrucción)
* Software seguimiento satélites: https://oz9aec.dk/gpredict/
* Antena: rotador, pc control, antena
* SDR: ¿? (https://sdr-es.com/eleccion-sdr/)
* Software SDR: https://www.sdrpp.org/ (https://sdr-es.com/instalacion-sdrpp/)
* Software decodificador: ¿?

## Información sobre Redes (en contrucción)
* Othernet: Servicio de acceso a determinada información de Internet desde satélites geoestacionarios: Datos metereológicos, noticias, Wikipedia, radio y APRS Radio data. Límite de descarga diario: 200 MB. Comunicación unidireccional.
  * Satélites:
    * SES-2 - COSPAR ID: 2011-049A
    * Astra 3B - COSPAR ID: 2010-021A
  * Hardware necesario
    * Othernet Dreamcatcher
    * LNB
  * Software necesario
    * Software seguimiento de satélites 
  * Bibliografía:
    * https://github.com/Othernet-Project/Dreamcatcher
    * https://github.com/McOrts/OTHERNET_GroundStation
    * https://www.youtube.com/watch?v=8H49Vyqkftg
    * https://www.youtube.com/watch?v=KPsQn06TM4M
    * https://www.youtube.com/watch?v=0F57ARpZFig
    * https://www.rtl-sdr.com/outernet-dreamcatcher-setup-with-ads-b-dump1090-and-piaware-tutorial/

* SatNOGS - https://satnogs.org

* TintGS - https://tinygs.com/

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
