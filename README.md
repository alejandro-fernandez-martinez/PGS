# Portable Ground Station - 📡 PGS 🛰️

## Objetivo

Creación de una estación terrestre para la conexión con [satélites](https://www.amsat-ea.org/sat%C3%A9lites-activos/), permitiendo recibir y enviar información en función de las posibilidades que ofrezcan los mismos.

v0.1 - Recibir [satélite Es'hail-2/QO-100](https://amsat-dl.org/en/eshail-2-amsat-phase-4-a/) 

## Material necesario

### Radio definida por software ([SDR] (https://www.rtl-sdr.com))

* #### Hardware
https://sdr-es.com/eleccion-sdr/
* #### Software
https://www.sdrpp.org/

### Antenas

* Parabólicas: + info https://axessnet.com/la-antena-satelital-de-comunicaciones-como-funciona-y-cuales-son-sus-tipos/


## Notas con información para futuro
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

## Decodificar señales
WXtoIMG (Weather Satellite Decoder?)


## Enlaces de interés
* https://www.mdpi.com/2673-4001/5/1/12
