# Guia 1 - Fórmula de Shannon-Hartley 

### Ejercicio 1
Calcular la capacidad de un canal con ancho de banda de __2MHz__ y relación S/N de __30dB__

**Solución**  
_Datos:_  

1. C = ?
2. B = 2MHz
3. S/N = 30 dB => Resolver con la Ecuación de `S/N [dB] = 10 * log_10 (S/N)`

_Entonces:_  

***De "3"***   
1. `x = S/N`
2. `30 = 10 * log x` => divido por 10 en ambos miembros
3. `3 = log x` => por definición de logaritmo `x = 10^3`
4. `x = 1000`

***De "2"***  
1. `B = 2x10^6`

***De "1"***
1. `C = B * log_2 (1 + S/N)`
2. `C = 2x10^6 * log_2 (1 + 1000)` => reemplazo los valores de las variables obtenidos en "2" y "3"
3. `C = 19934452,52 bps`
4. `C = 2 * log_2 (1 + 1000)` => Otra forma manteniendo las escalas ***ojo que lo dejo en mega***
5. `C = 19,93 Mbps`

___

### Ejercicio 2
Calcular la capacidad de un canal telefónico con relación señal/ruido de 50 dB

**Solución**  
_Datos:_
1. C = ?
2. B = 4000Hz = 4KHz => "valor obtenido de búsqueda en internet"
3. S/N = 50 dB

_Entonces:_

De "3"
1. `x = S/N`
2. `40 = 10 * log x` => divido por 10 en ambos miembros
3. `5 = log x` => por definición de logaritmo `x = 10^5`
4. `x = 100000`

De "1"  
1. `C = 4 * log_2 (1 + 100000)` => ***ojo que lo dejo en kilo***
2. `C = 66,43 Kbps`

___

### Ejercicio 3
En cierto canal se desea obtener una capacidad C = 300 kbps con un ancho de banda B = 100 kHz, 
siendo la densidad espectral de ruido No = 0,2 W/kHz. Calcular la potencia de señal S necesaria.

**Solución**  
_Datos:_  

1. C = 300 Kbps
2. B = 100 KHz
3. S/N = ?
4. Densidad Ruido = 0,2 W/KHz

_Entonces:_

De "4"  
1. `Z [W/KHz] = X [W] / Y [KHz]` => reemplazo por los datos del problema
2. `0,2 [W/KHz] = X[W] / 100 [KHz]` => paso el termino dividiendo al otro miembro multimplicando
3. `0,2 [W/KHz] * 100 [KHz] = X[W]` =>  simplifico unidades [KHz] y resuelvo la ecuación
4. `20 [W] = X [W]` => Por lo tanto se deduce que el ruido en el ancho de banda del canal es de __20W__

_Resuelvo la ecuación de Shannon_

1. `C = B * log_2 (1 + S/N)` => reemplazo por los datos del problema y el valor obtenido de "4"
2. `300 = 100 * log_2 (1 + S/20)` => divido por 100 en ambos miembros
3. `3 = log_2 (1 + S/20)` => por definición de logaritmo reformulo la ecuación
4. `2^3 = 1 + S/20`
5. `8 - 1 = S/20`
6. `7 * 20 = S`
7. `S = 140` => por lo tanto la potencia media de la señal debe ser de __140W__

___

### Ejercicio 4
Cierto canal de 4 kHz tiene una relación señal-ruido de 7. 

1. Obtener la relación señal-ruido de otro canal de 3 kHz que tenga la misma capacidad. 
2. Si ambos canales tienen igual densidad espectral de ruido, obtener la relación entre las respectivas potencias de señal. 

**Solución**  
_Datos:_

**Canal 1**    
- S1/N1 = 7
- B1 = 4 KHz
- C1 = ? Kbps

**Canal 2**  
- S2/N2 = ?
- C2 = C1 Kbps
- B2 = 3 KHz

__Entonces:__

Resuelvo la capcidad del canal 1  
1. `C1 = B1 * log_2 (1 + S/N)` => reemplazo las variables por los datos
1. `C1 = B1 * log_2 (1 + 7)` => opero dentro del paréntesis
2. `C1 = 4 * log_2 (8)` => resuelvo con calculadora
3. `C1 = 12` => capacidad del canal 1 __12Kbps__ 

Con la capacidad del canal 1 busco la relación señal/ruido del canal 2  

1. `C2 = B2 * log_2 (1 + S/N)` => reemplazo las variables por los datos
2. `12 = 3 * log_2 (1 + S/N)` => realizo cambio de variable __S/N = x__
3. `12 = 3 * log_2 (1 + x)` => divido en ambos miembros por 3
4. `4 = log_2 (1 + x)` => reformulo la ecuación por definición de logaritmo
5. `2^4 = 1 + x`
6. `16 - 1 = x`
7. `15 = x` => por lo tanto la relación señal/ruido del canal 2 es __15__


__Ecuaciones auxiliares__

`Rho Ruido [W/Hz] = potencia ruido [W] / ancho de banda del canal [Hz]`

_Entonces_  

Para las densidades de ruido tengo:

1. `Rho_N1 = Rho_N2 = Rho_N`
2. `Rho_N * B1 = N1`
3. `Rho_N * B2 = N2`

Para las relaciones señal/ruido tengo:

1. `S1/N1 = 7`
2. `S2/N2 = 15`

Reemplazo N1 y N2 por el despeje anterior, entonces:

1. `S1 / (Rho_N * B1) = 7` y `S2 / (Rho_N * B2) = 15` => despejo la variable Rho_N
2. `S1 / (7 * B1) = Rho_N` y `S2 / (15 * B2) = Rho_N` => como es un sistema de ecuaciones puedo resolver por el método de igualación
3. `S1 / (7 * B1) = S2 / (15 * B2)` => paso el termino __S2__ al denominador del miembro de la izquierda y __(7 * B1)__ al numerador del miembro de la derecha
4. `S1 / S2 = (7 * B1) / (15 * B2)` => como __B1__ y __B2__ son datos, reemplazo y resuelvo
5. `S1 / S2 = (7 * 4) / (15 * 3)`
6. `S1/S2 = 28/45` => por lo tanto la relación de potencias es `28/45 = ~0,62` 

___

### Ejercicio 5
En cierto canal se desea obtener una capacidad de 360 kbps con una potencia de señal de 900 W, 
siendo la densidad espectral de ruido igual a 5 W/kHz. Calcular el ancho de banda necesario, o 
justificar que esa capacidad es inalcanzable.

**Solución**  

_Datos:_

1. C = 360 Kbps
2. S = 900W
3. N = ?
4. B = ?
5. Rho_N = 5W/KHz

_Entonces:_  

De "5"  
1. `Rho_N = N/B` => N en función de B
2. `Rho_N * B = N`

De la ecuación de Shannon:  

1. `C = B * log_2 (1 + S/N)` => reemplazo con lo obtenido de "5" y los datos
2. `360 = B * log_2 (1 + 900/Rho_N * B)`
3. `360 / B = log_2 (1 + 900/Rho_N * B)`
4. `2^(360/B) = (1 + 900/Rho_N * B)` => hasta acá puedo llegar con las ecuaciones, puedo hacer un análisis de límites para entender el comportamiento.
5. `Lim B->inf. => 2^0 = 1 + 0 => 1 = 1`
6. `Lim B->0 => 2^inf = 1 + inf => inf. = inf.`
___

### Ejercicio 6
Calcular la relación señal a ruido en dB, para cierto canal cuya capacidad es de 400 kbps y su ancho 
de banda es de 40 kHz. 

**Solución**  

_Datos:_

1. C = 400 Kbps
2. B = 40 KHz
3. S/N = ?

De la ecuaciónn de Shannon:

1. `C = B * log_2 (1 + S/N)` => cambio de variable x = S/N
2. `400 = 40 * log_2 (1 + x)` => divido en ambos miembros por 40
3. `10 = log_2 (1 + x)` => por definición de logaritmo reformulo la ecuación
4. `2^10 = 1 + x` => paso el 1 al miembro de la izquierda restanto y acomodo la ecuación

5. `x = 2^10 - 1` => resuelvo 
6. `x = 1023` => retorno a las variables originales
7. `S/N = 1023`
8. `S/N [dB] = 10 log (1023)` => resuelvo por calculadora
9. `S/N = 30,09 dB` => por lo tanto la relación señal/ruido es de __30 dB__

___

### Ejercicio 7
Para un canal con BW=500KHz y S/N = 25dB, se pide: 
1. Calcular la relación señal a ruido, en veces 
2. Calcular la capacidad del canal 
3. Si la relación señal/ruido disminuye a la mitad ¿en qué proporción aumentará la capacidad del canal?

**Solución**

_Datos:_

1. C = ?
2. B = 500 KHz
3. S/N = 25 dB

De "3"

1. `S/N [dB] = 10 log (S/N)` => cambio de variable `x = S/N` y reemplazo con los datos.
2. `25 = 10 log (x)` => divido ambos miembros por 10
3. `2,5 = log (x)` => reformulo la ecuación por definición de logaritmo
4. `x = 10^2,5` => resuelvo con calculadora
5. `x = 316,23` 

De ecuación de Shannon

1. `C = B * log_2 (1 + S/N)` => reemplazo con los datos y valores obtenidos
2. `C = 500 * log_2 (1 + 316,22)` => resuelvo con calculadora **ojo que está en kilo**
3. `C = 4154,67 kbps` => muevo la coma 3 espacios a la derecha y lo represento en mega
4. `C = 4,15 Mbps` => capacidad del canal
5. `C = 500 * log_2 (1 + (316,22 / 2))` => señal/ruido a la mitad y resuelvo con calculadora
6. `C = 3656,94 Kbps` => muevo la coma 3 espacios a la izquierda para representarlo en mega
7. `C = 3,65 Mbps` => capacidad del canal con la relación señal/ruido a la mitad del planteo original

_Entonces:_

- 3,65 / 4,15 = ~0,879

Por lo tanto se deduce que reduciendo la relación señal/ruido a la mitad disminuye la capacidad del 
canal en un ~12%

___

# Guía 2 - Señales

## Ejercicio 1

- En la siguiente tabla, cada fila corresponde a una señal diferente. Completar las celdas vacías, sin olvidar unidades con sus múltiplos o submúltiplos más adecuados

`f = 1/T`  
`T = 1/f`  

|frecuencia  |periodo     |
|------------|------------|
|6.25 MHz    |**160ns**   |
|**500 KHz** |2 µs        |
|50 Hz       |**20 ms**   |
|**20MHz**   |50ns        |
|1.6 GHz     |**0.625ns** |

1. Dato 6.25 MHz
- `6.25 x10^6 = 1/T`
- `T = 1 / 6.25 x10^6`
- `T = 1.6x10^-7` <= _resultado_
- `T = 0.16 µs` <= _resultado llevado a submultiplo x10^-6_ 
- `T = 160ns` <= _resltado llevado a submiltiplo x10^-9_

2. Dato 2µs
- `2 µs = 1 / f`
- `2 x10^-6 = 1 / f`
- `f = 1 / 2 x10^-6`
- `f = 500000 Hz` <= _resultado_
- `f = 500 KHz` <= _divido resultado por 1000 para multiplo Kilo_ `500000 x10^-3`

3. Dato 50 Hz
- `T = 1 / 50`
- `T = 0.02 s` <= _resultado_
- `T = 20 ms` <= _mover el punto decimal 3 posiciones a la derecha para submultiplo mili_ `0.02 x10^3`

4. Dato 20 MHz
- `T = 1 / 20 x10^6`
- `T = 5x10^-8 s` <= _resultado_
- `T = 50ns` <= _submultiplo nano_

5. Dato 1.6 GHz
- `T = 1 / 1.6 x10^9`
- `T = 6.25x10-10 s` <= _resultado_
- `T = 0.625 ns` <= _submultiplo nano x10^^-9_
- `T = 625 ps`<= _submultiplo pico x10^-12_

___

## Ejercicio 2

- En la siguiente tabla, cada fila corresponde a una relación diferente entre potencias. Completar las celdas vacías recurriendo a valores prácticos (sin usar calculadora).

- Ecuaciones, logaritmos notables y propiedades.
- `db = 10 log (Ps/Pe)`
- `Ps: Potencia de Salida`
- `Pe: Potencia de Entrada`
- `log(2) = 0.3`
- `log(x*y) = log(x) + log(y)`
- `log(x/y) = log(x) - log(y)`

|  dB     |  Veces  |
|---------|---------|
|**26**   |400      |
|  17     |**50**   |
|**-13**  |0.05     |
|-33      |**X**    |
|**64**   |2500000  |

1. Dato 400 veces
- `db = 10 log (400)`
- `db = 10 log(2*2*100)`
- `db = 10 [log(2) + log(2) + log(100)]` <= _aplico propiedad del producto_
- `db = 10 (0.3 + 0.3 + 2)` <= _aplico logaritmos conocidos_ 
- `db = 10 x 2.6`
- `db = 26` <= _resultado_

2. Dato 17 dB
- `17 = 10 log(veces)` <= _descompongo el 17 para obtener elementos notables_
- `10 + 10 - 3 = 10 log(veces)`
- `10 + 10 - 3 = 10 [ log(x) + log(y) - log(z) ]`
- `10 + 10 - 3 = 10 [ log(x * (y/z)) ]` <= _por propiedad de logaritmos_ 
- `10 + 10 - 3 = 10 [ log(10 * (10/2)) ] ` <= _cuestionable operación ***REVISAR PROPIEDAD***_
- `50 veces` <= _resultado_

3. Dato 0.05 veces
- `db = 10 log(0.05)`
- `db = 10 log(1/2*10)`
- `db = 10 [log(1) - log(2*10)]`
- `db = 10 [log(1) - (log(2) + log(10))]`
- `db = 10 [0 - (0.3 + 1)]`
- `db = 10 * (-1.3)`
- `db = -13` <= _resultado_

4. Dato -33 dB
- `-33 = 10 log(veces)`
- `-10 - 10 - 10 - 3 = 10 [X]`
- `0.0005`

5. Dato 2500000 veces
- `db = 10 log(2500000)`
- `db = 10 log(2.5 * 10^6)`
- `db = 10 log((5*10^6) / 2)`
- `db = 10 [log(5) + log(10^6) - log(2)]`
- `db = 10 [log(10/2) + 6 log(10) - log(2)]`
- `db = 10 [log(10) - log(2) + 6 log (10) - log(2)]`
- `db = 10 [1 - 0.3 + 6*1 - 0.3]`
- `db = 10 [7 - 0.6]`
- `db = 10 * 6.4`
- `db = 64`

___

## Ejercicio 3

- En la siguiente tabla, cada fila corresponde a una señal de potencia diferente. Completar las celdas vacías, sin olvidar los múltiplos o submúltiplos más adecuados donde corresponda; recurrir a valores prácticos (sin usar calculadora).

- Ecuacions y elementos notables
- `dBm = 10 log(P/mW)`
- `P: potencia`
- `W: watt`

|dBm       |W         |
|----------|----------|
|27        |**X**     |
|**27**    |0.5W      |
|-6        |**X**     |
|**16**    |40mW      |
|63        |**X**     |


1. Dato 27dBm
- `27 = 10 log(miliwatts)`
- `10 + 10 + 10 - 3 = 10 log(watts)`
- `20 + 10 - 3 = 10 [log(A) + log(B) - log(C)]`
- `20 + 10 - 3 = 10 log((A * B) / C ))`
- `` ?:|

2. Dato 0.5W
- `dBm = 10 log(P/1mW)` => _0.5W * (1000mW / 1W) => 500mW_
- `dBm = 10 log(500mW/1mW)` => _simplifico unidades y reorganizo la expresion a valores notables_
- `dBm = 10 log(5*100)`
- `dBm = 10 [log(5) + log(100)]` => _reorganizo por propiedades de la suma de logaritmos_
- `dBm = 10 [log(10/2) + log(100)]` => _reorganizo nuevamente por propiedad de la resta de logaritmos_
- `dBm = 10 [log(10) - log(2) + log(100)]` => _aplico valores notables_
- `dBm = 10 (1 - 0.3 + 2)`
- `dBm = 10 * 2.7`
- `27 dBm` <= _resultado_

3. Dato -6 dBm
- `-3 dBm -3 dBm => 1 / 2 = 0.5 => 0.5 / 2 = 0.25 mW`
- `0.25 mW` <= _resultado_
- `250 µW` <= _aplico submultiplo_ 

4. Dato 40 mW
- `dBm = 10 log(40mW/1mW)` => _simplifico unidades y reorganizo la expresión a valores notables_
- `dBm = 10 log(2*2*10)` => _aplico propiedade de la suma de logaritmos_
- `dBm = 10 [2 log(2) + log(10)]`
- `dBm = 10 [2*0.3 + 1]`
- `dBm = 10 * (0.6 + 1)`
- `dBm = 10 * 1.6`
- `dBm = 16` <= _resultado_

5. Dato 63 dBm
- `63 dBm = (10 + 10 + 10 + 10 + 10 + 10 + 3) dBm`
- `10mW => 100 mW => 1 W => 10 W => 100 W => 1 KW => 2 KW`
- `2 KW`<= _resultado_
___ 

## Ejercicio 4 `?:|`

- Cierta señal cuya frecuencia fundamental es de 4 MHz tiene armónicos hasta 60 MHz y se aplica a la 
entrada de un filtro pasabajos ideal con frecuencia de corte de 25 MHz. Obtener las frecuencias de 
las sinusoides que aparecerán a la salida, y explicar qué característica de la señal se modifica al 
pasar por dicho filtro.


**Solución**
- Dado que su frecuencia fundamental es de 4MHz y tiene armónicos hasta los 60 MHz esta tiene sus 
armónicos en los múltiplos de 4 desde esa frecuencia
- `f0:4MHz`, `1:8MHz`, `2:12MHz`, `3:16MHz`, `4:20MHz`, `5:24MHz`, `6:26MHz`, `7:32MHz`, `8:36MHz`, 
`9:40MHz`, `10:44MHz`, `11:48MHz`, `12:52MHz`, `13:56MHz`, `14:60MHz`

- Al introducir un filtro pasabajos con frecuencia de corte de 25 MHz la señal se recortará en el 
5to armónico.
___

## Ejercicio 5

Dada una señal de T=10 nseg

1. ¿Cuál será la distancia que recorra en 5 períodos?
2. ¿Cuál será el tiempo insumido para recuperar una pantalla de CRM que necesita 10 consultas y 
espuestas, cuyo datacenter se encuentra en San Francisco (15000km)? 
3. ¿Cómo podría reducirse el tiempo calculado?

- Elementos utilizados
- `λ: longitud de onda`
- `v: velociad de propagación`
- `d: distancia`
- `v = 300000 km/s` => _pasaje a m/s => 300000 km/s * 1000 m/km => 300000000 m/s => `3x10^8` notación cientifica_

- Datos
- `T = 10 ns` => _pasaje a notación cientifica `10x10^-9`_
- `v = λ/T`

1. Resolución
- `v = λ/T`
- `vT = λ` => _reorganizo la ecuación_
- `λ = vT` => _reemplazo los valores_
- `λ = 3x10^8 * 10x10^-9` => _resuelvo con calculadora_
- `λ = 3m` => _solución para un período, unidad expresada en metros_

Distancia en 5 períodos
- `5T * (3m/1T)` => _relación longitud período_
- `15m` => _resultado_ 

2. Resolución
- `10 consultas`
- `15000 Km de distancia`
- `v = λ/T`
- `recorrido = 30000 Km` => _15000 Km de ida más 15000 Km de vuelta por consulta_
- `recorrido total = 10 recorrido = 10 * 30000 Km = 300000 Km` => _paso a unidad de metro_
- `recorrido total = 3x10^8 m`
- `tiempo total = recorrido total / velocidad` => _velocidad `v = λ/T` => `v = 3m / 10x10^-9 = 3x10^8 m/s`
- `tiempo total = 3x10^8 m / 3x10^8 m/s` => _se simplifica los factores y la unidad m dejando como unidad s, quedando dimensionalmente homogeneo_
- `tiempo total = 1s` 

3. Resolución
- `Los únicos valores modificables son la cantidad de consultas y la distancia.`
___

# Guía 3 - Modulación

## Ejercicio 1

- Cierta señal digital de 900 kbps tiene un ancho de banda de 2 MHz y se va a transmitir mediante
alguna técnica de modulación. En un diagrama de amplitudes y fases graficar todos los estados de la 
señal modulada si -en vez de la técnica anterior- se usa un modem PSK de 300 kbaud. 

**Solución**  
1. Calcular la cantidad de bits por baudio
2. Hacer un diagrama de aplitudes y fases

1. 900 Kbps / 300 Kbaudios = cantidad de bits/baudio = 3 bits
- Con 3 bits puedo transmitir 8 simbolos

2. Como se pide un digrama de amplitudes y fases lo divido en 2 amplitudes y cambio cada Pi/2 

![modulacion_ejercicio_1](https://github.com/leonardopardo/uade-ft-1c-2021-ejercicios/blob/main/src/modulacion_ejercicio_01.svg)

___

## Ejercicio 2

- El primer gráfico muestra una portadora (suponer senoidal); el segundo gráfico muestra una modulante 
triangular. Dibujar cuidadosamente en los otros gráficos el resultado de la modulación en FM y en AM.

**Solución**  

___

## Ejercicio 3

- Se transmite a 7.200 bps con un modem PSK de 2.400 baud. A partir de los cálculos que deban hacerse, 
graficar todos los estados de la señal modulada en un diagrama de amplitudes y fases, asignando además 
los bits que corresponden a cada estado. 

**Solución** 
- Al ser un modem PSK se asume una amplitud quedando el cambio por fase.

1. Calcular la cantidad de bits por baudio
- 7200 bps / 2400 baud = 3 bits

2. Graficar los estados en un diagrama de fases

- Gráfico

![modulacion_ejercicio_3](https://github.com/leonardopardo/uade-ft-1c-2021-ejercicios/blob/main/src/modulacion_ejercicio_03.svg)

___

## Ejercicio 4

- Se transmite a 12 Mbps con un modem QAM de 3 Mbaud con 2 amplitudes diferentes. A partir de los 
cálculos que deban hacerse, graficar todos los estados de la señal modulada en un diagrama de 
amplitudes y fases, con la mayor simetría posible.

**Solución**
1. Calcular cantidad de bits por baudio
- 12Mbps / 3Mbaud = 4 bits

2. Graficar en diagrama de amplitud y fase, tiene 2 amplitudes

___

## Ejercicio 5

- Estimar el ancho de banda de la señal modulada en cada uno de los dos ejercicios anteriores.

___

## Ejercicio 6

- Se transmite a 57600 bps con un modem de 9600 bauds. Graficar las constelaciones si:
    1. La modulación es QAM con 2 niveles de amplitud
    2. La modulación es PSK

1. Calcular cantidad de bits por baudio
- 57600 bps / 9600 bauds = 6 bits

- Graficar en QAM con dos amplitudes
- Graficar en PSK solo fases
___

# Guía 4 - Teoría de la Información y la Codificación

## Ejercicio 1

- Cada mensaje que emite cierta fuente de información meteorológica sobre Argentina -discreta y sin 
memoria- contiene la fecha, hora, lugar, y aspectos relevantes del estado climático actual (por 
ejemplo: "nublado, cálido y húmedo"). 
    1. ¿De qué depende la cantidad de información contenida en uno cualquiera de esos mensajes? 
    2. Ejemplificar un mensaje concreto de esta fuente, tal que contenga gran cantidad de información. 

**Respuesta**  
- `Depende de la probabilidad de ocurrencia`
- `1 de enero de 20XX 00:35 hs. CABA Nevando`
___

## Ejercicio 2

- Calcular la tasa de información de una señal que consta de 3 bits de sincronismo y 8 bits de 
información, considerando que el total del bloque se transmite en 10 microsegundos.

**Solución**  

- Se considera la entropia con 8 bits y el tiempo de bloque 10 microsegundos, donde ya está incluida la redundancia.
- `8/10x10^-6` <= _tiene unidades de `[bit]/[segundo]`_
- `8/10x10^-6` <= _resolver con calculadora_
- `800000 bits/segundo` <= _resultado_
- `800 Kbps` <= _acomodo a multiplo adecuado y ajusto la representación de la unidad_

___

## Ejercicio 3

- Se desea trasmitir una señal que consta de:
    - 1 bit de start
    - 15 bits de datos
    - 2 bits de redundancia
    - 2 bits de stop
Si cada bit tiene una duración de 100 nseg ¿cuál será la tasa de información?

**Solución**  
- Ya que en en la guía sobre el ejercicio anterior no se contemplaron los datos que no eran información, se toma la misma premisa para la solución de este ejercicio. Pero la duración no es del bloque entero como en el ejercicio 2 el cual ya tenía contemplado los bits de reduncia al alcarar que es la velocidad del bloque, por lo tanto debo calcular el tiempo total del bloque para el divisor.

- `15/(1+15+2+2)*100x10^-9` <= _esto tiene unidades de `[bit]/[bit]*([segundo]/[bit])`, resuelvo con calculadora_
- `75000000 bps` <= _ajusto a multiplo acorde_
- `7.5 Mbps` <= _resultado_
___

## Ejercicio 4

- Calcular la cantidad de bits de información y redundancia si se sabe que:
1. La tasa de información es 400 kbps
2. La duración de cada bit es 2 µseg 
3. La cantidad total de bits es 20

**Solución**
- `400 kbit/seg = x bit / (20 bit * 2x10^-6 seg/bit)` <= _limipio las unidades y paso el denominador de la derecha a la izquierda multiplicando_
- `400*(20*2x10^-6) = x` <= _resulvo con calculadora_
- `16 = x` <= _resultado_
- `16 bits de información` <= _respuesta final_
___

## Ejercicio 5

- Una fuente sin memoria tiene un alfabeto de 4 símbolos, siendo P(a) = 0,7; P(b) = 0,2 y P(c) = P(d)
1. Construir un código de Huffman para esta fuente, con alfabeto binario. 
2. Comprobar que se cumple la relación entre la entropía y la longitud media que predice la teoría.

**Solución**
- Calcular la probablidad de c y d
- `P(a) + P(b) + P(c) + P(d) = 1` <= _por teorema de probabilidad total, dado que P(c) = P(d), reemplazo por 2 P(c)_
- `P(a) + P(b) + 2P(c) = 1` <= _reemplazo por los datos_
- `0,7 + 0,2 + 2 P(c) = 1`
- `0,9 + 2 P(c) = 1`
- `2 P(c) = 1 - 0,9`
- `P(c) = 0,1 / 2`
- `P(c) = 0,05` <= _resultado_
- Dado que P(d) = P(c), entonces P(d) = 0,05
- Calculo de Hi, Pi * log_2(1/Pi)

![guia_4_ejercicio_05](https://github.com/leonardopardo/uade-ft-1c-2021-ejercicios/blob/main/src/guia_4_ejercicio_05.svg)

|Simbolo|Pi  |Hi  |Codigo|Li  |li  |
|-------|----|----|------|----|----|
|a      |0.7 |0.36|0     |1   |0,7 |
|b      |0.2 |0.46|10    |2   |0,4 |
|c      |0.05|0.22|110   |3   |0,15|
|d      |0.05|0.22|111   |3   |0,15|
|       |1   |1.26|-     |-   |1.4 |

- Eficiencia: `H/l * 100 = 1.26/1.4 * 100 = 90%`
- Redundancia: `(1-E) * 100 = (1 - 0.9) * 100 = 10%`
___

## Ejercicio 6

- Dada una fuente sin memoria que transmite 5 símbolos con las siguientes probabilidades: 
    - P (D) = 0,5  
    - P (C) = 0,25   
    - P (A) = 0,15  
    - P (B) = P (E)  

1. Encontrar el código de Huffman correspondiente 
2. Calcular la Entropia de la fuente, la longitud media del código, su eficiencia y redundancia.

**Solución**
1. Calcular el valor de las probabilidades B y E
- `P(A) + P(B) + P(C) + P(D) + P(E) = 1` <= _por teorema de la probabilidad total, dado que P(B) = P(E), reemplazo una de las variables por 2 veces la otra_
- `P(A) + P(C) + P(D) + 2P(E) = 1` <= _reemplazo por los valores numéricos_
- `0.15 + 0.25 + 0.5 + 2P(E) = 1`
- `0.9 + 2P(E) = 1`
- `2P(E) = 1 - 0.9`
- `P(E) = 0.1 / 2`
- `P(E) = 0.05` <= _resultados final_
- Por lo tanto P(E) y P(B) valen 0.05

2. Gráfico

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="381px" height="381px" viewBox="-0.5 -0.5 381 381" content="&lt;mxfile host=&quot;Electron&quot; modified=&quot;2021-04-26T00:34:25.155Z&quot; agent=&quot;5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/14.4.3 Chrome/87.0.4280.141 Electron/11.3.0 Safari/537.36&quot; etag=&quot;nW1AJnDpSF5GDW_3wy0Y&quot; version=&quot;14.4.3&quot; type=&quot;device&quot; pages=&quot;3&quot;&gt;&lt;diagram id=&quot;DXfBGZm6CotA9TYdEd3g&quot; name=&quot;modulación_4&quot;&gt;7VpbU+MgFP41fdThkjTJo1ZX9zazMz6oj9mENszS0KHUpv76JYZcgNatlzaa2Rcn50s4wHc+zgHsCE/mxZWIF9lPnhI2QiAtRvhihFAAxupvCWwqwANRBcwETSsItsANfSQaBBpd0ZQsjQ8l50zShQkmPM9JIg0sFoKvzc+mnJm9LuIZcYCbJGYuektTmVVoiIIWvyZ0ltU9w7Ge3zyuP9YzWWZxytcdCF+O8ERwLquneTEhrOSu5qVq92XH22ZgguRynwbg+9Xj9fR28QOciILmD5ffvsYnyK/cPMRspWesRys3NQUkT89KJpWV81yB55mcM2VB9ag6F5u7rnGvDFAbF4VhbWqroPKu83xfO1DPbZPSqFtUoyKpE612+hpa8pVIyDNz1lOWsZgR+a/vNJdXhM+JmoFqt25l4OvQZh0F1JggLJb0wRxurNU4a9w1PfziVE0EAb1wENB+NpZdu6imqVt1w2478k1HMLQcVTw4jtRDZ9ot9KSqlyhs/F4KA69RGPyvsB3CgMg/hV4AwzHygzH0sKm3yDsNfRRCHHgIh374SvVZbnxTi9YQfHRUae6T+xhTlaZU5Dqjktws4qfAr1WtM1UaLxdV+ZnSgqhOz6eUsQlnXLSi1t0RIUnxvMZcTegGobmYa7OjGFVhXck04DZ5GLS+lEP4xtW976r7KHkYj1+bhy1HdkQOnYYHHifvncplE99djg4cJ7daQgCdUKkEIs34LKXgf4iVcLbkoJjRWa7MRIWNKPy8TEdU7XfP9Is5TVO2K+EJvsrTMr11Kuab8llgFgQURk5Cw74rGugfKJ0FxyoJI4SnYUKSxImdevM79D3/nRi2SwaE0KEYblmX8GAVAwyOYwg/Gsf7lOXPzTEK3FRxXI73Kamfi2M7V/TPMR4cxxhaZ6DI75ljb3AcN5xuzF1GbxTvcwfyuSgOPpqKh7dzs1XcZI7eOA4djsGQDycosrZ19T8z+jqdwMgNQB3tQQYAmCugPpv3xT9yjy4ADngBhCb9Uc/yR+6pBoAByx8jq8huue49bgDc7TgccgCsS8X++Xe36nDI+R9al7EY9R0AtwDDIRcAewd0wPtZZba/hahu09sflODLvw==&lt;/diagram&gt;&lt;diagram id=&quot;Rgb2i4vwqOv7dDm6xw2h&quot; name=&quot;codigos_05&quot;&gt;7VpLc5swEP41PoZBiJePiZ00h7TTGXemTW8yyKAMRowsx3Z+faUgjIX8SuOYhPHFo11ghfbbb7Va3IOD6fIbQ0X6ncY46zl2vOzBYc9xQg+KX6lYlQq375aKhJG4VIFaMSIvWCltpZ2TGM+0GzmlGSeFroxonuOIazrEGF3ot01ops9aoAQbilGEMlP7m8Q8Vctyglp/j0mSVjMDv19emaLqZrWSWYpiuthQwdseHDBKeTmaLgc4k76r/PLs/CriCUX30zH74f+FT/E4vyqN3b3lkfUSGM75aU07pelnlM2Vv1DP8TMxy82YiVEiR8LuQLlrxleVY4V1gaEQbhYp4XhUoEheWYgoErqUTzMhATFEs6IEdkKWOJaKjCS5kCOxHMyEYkKybEAzKsbDnObSpnovzDheNoA84AWwhkaENKZTzNlKPKesuApMFc3QVvKijo3qlnQjLCodUtGYrA3XHhcD5fQ3AAANAMbbAXA6AgDwPxkCroFAtB0B2+sIBE74ySDwDAjijkPg2p8MgtBwLKPzPJaOGtrCEZTxlCY0R9kDpYVy6RPmfKW2fDTnVHe48A9b/ZHPW14lPipzr8JwqUmrtRRfy42/RkFo7ohcT3l9SfiGWSE9VjOKcW1UCpXNcnU4NmqFY1AUbqFzFuE996ntkSOW4H323O1RwXCGOHnWX+7kGDu+wTPbgF366AGNRRGos6dJFskJIsqsa3VhSuJY2rhheEZe0PjVnnR9QUnOX5fi3fS84T5SqRpQPVy/3kGYwr1ku7It34ZQI1y18R7teWX9p1zNhmkArNDXLAPbapihk8lMREUTvvWL/j+i/a3wjZSo2HMh8gcQ2WuVyIFBZLA1Er4ckfuHiOwGJ+Gta7muxtpa8fGsNdGLdtQ7W1D9kuUObBy71gHRVrkD4CVznjhzAufI1Bm0mjrNs0ZHUmcZ0vtzZ+DpNDxJLgWBBQPdrm0550qmwL0wuS0m74i4MzHZbNx05DQDdpwSayYHftBg3EmYLGa27L5mGIRW1XQ5A5fNdvR4V2m0ZQP/kqWR0+iHArft0shsBV0S6jsT6rGnypIArWVU82NEV2qjgw0iF+ilEThNaeRZ/UZ3qC6WzpBPL/2h1qjcLpPNjbQrtdHBDlEYhhrjqm/c766NbKuRIxxo+fBsXDa7RmhrcdSVnpHT+ET2cXWREOt/cZR41X+Fgbf/AA==&lt;/diagram&gt;&lt;diagram id=&quot;El05nHRYS2KDlFnGHKXv&quot; name=&quot;codigos_6&quot;&gt;7Vpbc6owEP41PrZDuImPXnqZMz1zLj0ztb50IomQFokTY9X++hMkgBCo1mmLMj6RXZKF7Lf7ZRNoGf3p6obBmf+TIhy0dA2tWsagpetAt01xiTTrWGN1jFjhMYJkp0xxT96wVGpSuyAIz3MdOaUBJ7O80qVhiF2e00HG6DLfbUKD/FNn0MOK4t6Fgap9IIj7sdbR25n+FhPPT54M7E58ZwqTznImcx8iutxSGVcto88o5XFruurjIHJe4pdfyBmt7aGOR92//4a90Y/u4s9FbOz6I0PSKTAc8oNNPzyN2k/uEF13nm8fIL+5e3l7kUO0VxgspL9gS7cD8ZTemImWF7VEpz6wpBP4OvGsMC9AFEJv6ROO72fQje4sRRwJnc+ngZCAaML5LEZ2QlYYRYqAeKGQXTEfzIRiQoKgTwMq2oOQhpFN+WKYcbwqILnDDSDFRgQ1plPM2VqMk1Z0Tc5ZxrNhS3mZRYcpVf5WYCQ6KOPRSy1nPhcN6fYPQAAUCMblEGiNgcA5Mgh0BQK3HAK9KRAA/cggMBQIUDkETUHAPDIATAUA3HAaSl1+LBDYCgSa6mokqhspSv8wughR5M2BJiTKuE89GsLgjtKZ9Psz5nwtazO44DSPinAiWw+j8ZdWIj5KcxthsMpJ61RC3ahCy15FaK5JNOn4/orwLbNCekyeKNqZ0UhIbMYTjmZ5ANTCU3TBXPyOj2Xwcsg8zHetymroMBxATl7zL/fpgdA+w14T7GadsOtqHQJKI+EOjsUuLc+sRSKN+JKIbVBX3pgShIJN3OA5eYPjjb3I9TNKQr6ZitVrWYP3CFfu0eTgjJ+2YaoO6EoivtAuTZCn4lja2+3S9O9oKlt2CyPoZDIX6BdhSl/ocOQsBbhxxepZAuhpLp6FAjKt6etaPDt75s6ZRQ9nUWdPFrV2pbvhmPZnJvzXZzg4l2J1RZNWHk3fsyYDlVfKI+Hk1mRQ4dcsS23QNvIkf+xZ6ihgwaqFuDFHOXphG5secNZ2oKmfqfKTqRIkX052caVTJ1cmhpu3f4lD+t2KxrLMXBom2B4vWQLjnKd15WlFPH1TTaMuk02paYxdedq2tHxNc/w7D5VV3cqqpjFFTeErbfq9qraipsSzX0mWoPFUae5JlaDWo/gk7hpY0+w8pbFM4+RqGvtc09SVqBVr7zfVNO3G1jT2rjx17I5+anmq/m6AyquapnwwAYUfPswvK2iEmP2UGAOW/dppXP0H&lt;/diagram&gt;&lt;/mxfile&gt;" style="background-color: rgb(255, 255, 255);"><defs/><g><ellipse cx="190" cy="350" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 350px; margin-left: 171px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">a<br />0,15</div></div></div></foreignObject><text x="190" y="354" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">a...</text></switch></g><ellipse cx="270" cy="350" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 350px; margin-left: 251px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">b<br />0,05</div></div></div></foreignObject><text x="270" y="354" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">b...</text></switch></g><ellipse cx="110" cy="350" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 350px; margin-left: 91px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">c<br />0,25</div></div></div></foreignObject><text x="110" y="354" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">c...</text></switch></g><ellipse cx="30" cy="350" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 350px; margin-left: 11px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">d<br />0,5</div></div></div></foreignObject><text x="30" y="354" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">d...</text></switch></g><ellipse cx="350" cy="350" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 350px; margin-left: 331px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">e<br />0,05</div></div></div></foreignObject><text x="350" y="354" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">e...</text></switch></g><path d="M 310 290 L 270 330" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 310px; margin-left: 290px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="290" y="313" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 310 290 L 350 330" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 300px; margin-left: 324px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="324" y="304" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="310" cy="270" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 270px; margin-left: 291px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">be<br />0,1</div></div></div></foreignObject><text x="310" y="274" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">be...</text></switch></g><path d="M 250 210 L 310 250" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 220px; margin-left: 270px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="270" y="223" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><path d="M 250 210 L 190 330" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 235px; margin-left: 241px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="241" y="238" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><ellipse cx="250" cy="190" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 190px; margin-left: 231px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">abe<br />0,25</div></div></div></foreignObject><text x="250" y="194" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">abe...</text></switch></g><path d="M 190 130 L 250 170" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 144px; margin-left: 209px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="209" y="147" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><path d="M 190 130 L 110 330" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 157px; margin-left: 183px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="183" y="160" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><ellipse cx="190" cy="110" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 110px; margin-left: 171px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">cabe<br />0,5</div></div></div></foreignObject><text x="190" y="114" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">cabe...</text></switch></g><path d="M 130 50 L 204.14 95.86" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 62px; margin-left: 147px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="147" y="65" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><path d="M 130 50 L 30 330" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 68px; margin-left: 123px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="123" y="71" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><ellipse cx="130" cy="30" rx="20" ry="20" fill="none" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 30px; margin-left: 111px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">dcabe<br />1</div></div></div></foreignObject><text x="130" y="34" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">dcabe...</text></switch></g></g><switch><g requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"/><a transform="translate(0,-5)" xlink:href="https://www.diagrams.net/doc/faq/svg-export-text-problems" target="_blank"><text text-anchor="middle" font-size="10px" x="50%" y="100%">Viewer does not support full SVG 1.1</text></a></switch></svg>

3. Tabla

|Simbolo|Pi  |Hi  |Codigo|Li  |li  |
|-------|----|----|------|----|----|
|a      |0.15|0.41|110   |3   |0,45|
|b      |0.05|0.22|1110  |4   |0,20|
|c      |0.25|0.50|10    |2   |0,50|
|d      |0.5 |0.50|0     |1   |0,50|
|e      |0.05|0.22|1111  |4   |0,20|
|       |1   |1.85|-     |-   |1.85|  

4. Calculo de Eficiencia y Redundancia
- E = H/l * 100 = 1 * 100 = 100%
- R = (1-E) * 100 = 0 * 100= 0%
___

## Ejercicio 7

- Una fuente sin memoria tiene un alfabeto de 6 símbolos, siendo P(a) = 0,6; P(b) = P(c) = P(d) = 0,1 ; P(e) = P(f) 
1. Calcular su entropía. 
2. Construir un código de Huffman para esta fuente, con alfabeto binario. 
3. Calcular la longitud media de este código. 
4. Calcular la eficiencia y la redundancia de este código.

**Solución**
1. Calcular la probabilidad de los simbolos faltantes y resolver el calculo de entropía
- `P(a) + P(b) + P(c) + P(d) + P(e) + P(f) = 1` <= _por teorema de probabilidad total, P(e) = P(f), entonces reemplazo por 2P(e)_
- `0.6 + 0.1 + 0.1 + 0.1 + 2P(e) = 1`
- `0.9 + 2P(e) = 1`
- `P(e) = (1 - 0.9) / 2`
- `P(e) = 0.05` <= _resultado, entonces P(e) = 0.05 y P(f) = 0.05_

2. Construir el código Huffman
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="461px" height="361px" viewBox="-0.5 -0.5 461 361" content="&lt;mxfile host=&quot;Electron&quot; modified=&quot;2021-04-28T18:27:34.752Z&quot; agent=&quot;5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/13.7.9 Chrome/85.0.4183.121 Electron/10.1.3 Safari/537.36&quot; etag=&quot;8wBobofBcTit62q7PH-E&quot; version=&quot;13.7.9&quot; type=&quot;device&quot;&gt;&lt;diagram id=&quot;NmMDTVviOJIlyTkP94RH&quot; name=&quot;Página-1&quot;&gt;7Vrdc6IwEP9rfKxDwpc81o/25qY3dzM+3LVvESLkBokTY9X+9RckyEeg9VoUdOxDJ7uYhf1tfrubQE8fLbaPDC2DH9TDYQ9q3ranj3sQ2kAT/2PFLlEMgJ4ofEa8RAUyxZS8YamU8/w18fCq8ENOacjJsqh0aRRhlxd0iDG6Kf5sTsPiXZfIx4pi6qJQ1f4mHg+kF9DO9N8w8YP0zsBykisLlP5YerIKkEc3OZU+6ekjRilPRovtCIcxdikuybyHmquHB2M44sdMsK0Fcc3R958v9PFxsB5PnJf7O2nlFYVr6TDqQSsUBoczJkZ+PNL6lnSB71JchG0RAiEMNwHheLpEbnxlIxaB0AV8EQoJiCFaLZO4zMkWi0cZyjtixvG21hVwAEgsLEwXmLOd+ImcYFgSU7mo9FTeZCEypCrIRSfVIbko/IPlDDcxkND9B4xQgXFWBSPoFoz6oGMw6gqMuApGzewWjsDoGI6GgqN3AcvxkCm7AqOpwOheAIy61jEYLQXG+SWwums1Ju2IcjhqCmKMriMvRmCsCRQo4wH1aYTCJ0qXEqu/mPOdbLTQmtMikgIctvsTz++bqfgsze2F8bYg7Q6Sdx+3W0KMaIQTzQOJXUyubwnPmRXSc3pHMc6MxkJqM/EOe0qHVgqhQICumYvfAU+2axwxH/OP1qq6JBgOESevxedoPsJqN1aRWwQcUylKpBsIevPB++xCaiHo+heDLqf+okQ8YdYVlMtZOTMkzy9n5Rv3sqFyJiobShxUDO3X4MGfzy9LW807Xat5oFTz4KDlZO2oNQ8rkAl/eQmbkPiRGLvCb8yEIkaFiN3ovbywIJ4X7jmPV+QNzfamYtos4+jvvTCHPXMc2xI0XyWMB82gbJdAdlSQ9QqQ4ckqon6m7HiVJRHAI9Oj3WZNhOpeRlPbnhiQJzTD4enoVMsfefIkJ2ddWT4m7yzfWrbdiXUBrALj0uOaL1amOwj7RcMQ9IHYN2R/etEmnc9X+CTFBRg3Dp+Bw0arHFY30lp1Y3t5HK4BNsdhSzcbJbE0Y/TTk+YzkLRia34jaeMkNVslqXpMA66l0NYAmy+0zXL0DJSseCVzo2TjlIStUlLdeYNrqZs1B20ZJQ3HbKbbhX3NriT3GUgK1canX9Hwtnp04hR39aD1c27nltm+kNmOPfQE7aa2CmZcSWZzPsxsVpoXutte1ETjRsKGSdgqB9XPLa6ku8h9X1XDwcHAubiOv6Ib7FYrUX5l3nonMVAQm2PPnSmoXdqLmPKrRWAfh/TJ3sSkLpSRRpcPdekbuQqkzWaQFmL2MWiSNLIvavXJPw==&lt;/diagram&gt;&lt;/mxfile&gt;" style="background-color: rgb(255, 255, 255);"><defs/><g><ellipse cx="430" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 411px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">a<br />0.6</div></div></div></foreignObject><text x="430" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">a...</text></switch></g><ellipse cx="350" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 331px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">b<br />0.1</div></div></div></foreignObject><text x="350" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">b...</text></switch></g><ellipse cx="110" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 91px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">e<br />0.05</div></div></div></foreignObject><text x="110" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">e...</text></switch></g><ellipse cx="190" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 171px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">d<br />0.1</div></div></div></foreignObject><text x="190" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">d...</text></switch></g><ellipse cx="270" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 251px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">c<br />0.1</div></div></div></foreignObject><text x="270" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">c...</text></switch></g><ellipse cx="30" cy="330" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 330px; margin-left: 11px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">f<br />0.05</div></div></div></foreignObject><text x="30" y="334" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">f...</text></switch></g><path d="M 70 270 L 30 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 290px; margin-left: 50px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="50" y="293" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 70 270 L 110 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 290px; margin-left: 90px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="90" y="293" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="70" cy="250" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 250px; margin-left: 51px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.1</div></div></div></foreignObject><text x="70" y="254" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.1</text></switch></g><rect x="20" y="240" width="30" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 250px; margin-left: 35px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">fe</div></div></div></foreignObject><text x="35" y="254" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">fe</text></switch></g><path d="M 160 150 L 70 230" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 190px; margin-left: 116px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">00</div></div></div></foreignObject><text x="116" y="193" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">00</text></switch></g><path d="M 160 150 L 190 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 191px; margin-left: 166px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">01</div></div></div></foreignObject><text x="166" y="194" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">01</text></switch></g><path d="M 160 150 L 270 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 190px; margin-left: 186px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">10</div></div></div></foreignObject><text x="186" y="193" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">10</text></switch></g><path d="M 160 150 L 350 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 190px; margin-left: 211px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">11</div></div></div></foreignObject><text x="211" y="193" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">11</text></switch></g><ellipse cx="160" cy="130" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 130px; margin-left: 141px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.4</div></div></div></foreignObject><text x="160" y="134" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.4</text></switch></g><path d="M 230 50 L 160 110" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 67px; margin-left: 212px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="212" y="70" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 230 50 L 430 310" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 65px; margin-left: 241px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="241" y="69" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="230" cy="30" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 30px; margin-left: 211px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">1</div></div></div></foreignObject><text x="230" y="34" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">1</text></switch></g><rect x="70" y="120" width="40" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 130px; margin-left: 90px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">fedcb</div></div></div></foreignObject><text x="90" y="134" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">fedcb</text></switch></g><rect x="130" y="20" width="50" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 30px; margin-left: 155px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">fedcba</div></div></div></foreignObject><text x="155" y="34" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">fedcba</text></switch></g></g><switch><g requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"/><a transform="translate(0,-5)" xlink:href="https://desk.draw.io/support/solutions/articles/16000042487" target="_blank"><text text-anchor="middle" font-size="10px" x="50%" y="100%">Viewer does not support full SVG 1.1</text></a></switch></svg>

3. Calcular la longitud media del código


|Simbolo|Pi   |Hi   |Código|Li|li |
|-------|-----|-----|------|--|---|
|a      |0.6  |0.44 |1     |1 |0.6|
|b      |0.1  |0.33 |011   |3 |0.3|
|c      |0.1  |0.33 |010   |3 |0.3|
|d      |0.1  |0.33 |001   |3 |0.3|
|e      |0.05 |0.21 |0001  |4 |0.2|
|f      |0.05 |0.21 |0000  |4 |0.2|
|       |1    |1.85 |------|--|1.9|


4. Calcular Eficiencia y Redundancia
- Eficiencia: H/l * 100 => `E = 1.85/1.9 = 0.973` => 97.3%
- Redundancia: (1 - E) * 100 => `1 - 0.973 = 0.027` => 2.7% 

___

## Ejercicio 8

- Una fuente sin memoria se codifica con un código bloque de L = 3 bits y su eficiencia es del 75%. 
    1. Determinar la entropía de la fuente y la redundancia. 
    2. ¿Cómo podría haberse conseguido una mejor eficiencia?

**Solución**
1. Entropía de la fuente y redundancia
- E * 100 = 75 => E = 0.75
- De la ecuación de eficiencia se desprende que:
- `0.75 = H / l` <= _reemplazo por los datos y despejo la incognita_
- `0.75*3 = H` <= _resuelvo con calculadora_
- `H = 2.25` <= _entropía de la fuente_
- `R = (1 - E)`
- `R = (1 - 0.75) = 0.25` <= _redundancia de la fuente_

2. Al utilizar código bloque todas las longitudes son iguales, entonces se podría mejorar pasando a un código compacto para reducir la longitud media.

___

## Ejercicio 9

- Hallar el código de Huffman para la siguiente fuente y determinar H, longitud media, E y R
    - P(A) = 0.13
    - P(B) = 0.19
    - P(C) = 0.08
    - P(D) = 0.05
    - P(E) = 0.22
    - P(F) = P(G) = P(H) 

**Solución**
1. Calcular probabilidades faltantes

- `P(A) + P(B) + P(C) + P(D) + P(E) + P(F) + P(G) + P(H) = 1` <= _por teorema de probabilidad total, P(F) = P(G) = P(H) lo reemplazo por 3P(F)_
- `P(A) + P(B) + P(C) + P(D) + P(E) + 3P(F) = 1` <= _reemplazo por sus valores_
- `0.13 + 0.19 + 0.08 + 0.05 + 0.22 + 3P(F) = 1` 
- `0.67 + 3P(F) = 1`
- `P(F) = (1-0.67) / 3`
- `P(F) = 0.11` <= _resultado, por lo tanto P(F) = P(G) = P(H) = 0.11_

2. Graficar el código Huffman
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" width="621px" height="561px" viewBox="-0.5 -0.5 621 561" content="&lt;mxfile host=&quot;Electron&quot; modified=&quot;2021-04-28T20:10:02.552Z&quot; agent=&quot;5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/13.7.9 Chrome/85.0.4183.121 Electron/10.1.3 Safari/537.36&quot; etag=&quot;o1iXVDLL9POvqS5kBmaS&quot; version=&quot;13.7.9&quot; type=&quot;device&quot; pages=&quot;2&quot;&gt;&lt;diagram id=&quot;NmMDTVviOJIlyTkP94RH&quot; name=&quot;Página-1&quot;&gt;7Vrdc6IwEP9rfKxDwpc81o/25qY3dzM+3LVvESLkBokTY9X+9RckyEeg9VoUdOxDJ7uYhf1tfrubQE8fLbaPDC2DH9TDYQ9q3ranj3sQ2kAT/2PFLlEMgJ4ofEa8RAUyxZS8YamU8/w18fCq8ENOacjJsqh0aRRhlxd0iDG6Kf5sTsPiXZfIx4pi6qJQ1f4mHg+kF9DO9N8w8YP0zsBykisLlP5YerIKkEc3OZU+6ekjRilPRovtCIcxdikuybyHmquHB2M44sdMsK0Fcc3R958v9PFxsB5PnJf7O2nlFYVr6TDqQSsUBoczJkZ+PNL6lnSB71JchG0RAiEMNwHheLpEbnxlIxaB0AV8EQoJiCFaLZO4zMkWi0cZyjtixvG21hVwAEgsLEwXmLOd+ImcYFgSU7mo9FTeZCEypCrIRSfVIbko/IPlDDcxkND9B4xQgXFWBSPoFoz6oGMw6gqMuApGzewWjsDoGI6GgqN3AcvxkCm7AqOpwOheAIy61jEYLQXG+SWwums1Ju2IcjhqCmKMriMvRmCsCRQo4wH1aYTCJ0qXEqu/mPOdbLTQmtMikgIctvsTz++bqfgsze2F8bYg7Q6Sdx+3W0KMaIQTzQOJXUyubwnPmRXSc3pHMc6MxkJqM/EOe0qHVgqhQICumYvfAU+2axwxH/OP1qq6JBgOESevxedoPsJqN1aRWwQcUylKpBsIevPB++xCaiHo+heDLqf+okQ8YdYVlMtZOTMkzy9n5Rv3sqFyJiobShxUDO3X4MGfzy9LW807Xat5oFTz4KDlZO2oNQ8rkAl/eQmbkPiRGLvCb8yEIkaFiN3ovbywIJ4X7jmPV+QNzfamYtos4+jvvTCHPXMc2xI0XyWMB82gbJdAdlSQ9QqQ4ckqon6m7HiVJRHAI9Oj3WZNhOpeRlPbnhiQJzTD4enoVMsfefIkJ2ddWT4m7yzfWrbdiXUBrALj0uOaL1amOwj7RcMQ9IHYN2R/etEmnc9X+CTFBRg3Dp+Bw0arHFY30lp1Y3t5HK4BNsdhSzcbJbE0Y/TTk+YzkLRia34jaeMkNVslqXpMA66l0NYAmy+0zXL0DJSseCVzo2TjlIStUlLdeYNrqZs1B20ZJQ3HbKbbhX3NriT3GUgK1canX9Hwtnp04hR39aD1c27nltm+kNmOPfQE7aa2CmZcSWZzPsxsVpoXutte1ETjRsKGSdgqB9XPLa6ku8h9X1XDwcHAubiOv6Ib7FYrUX5l3nonMVAQm2PPnSmoXdqLmPKrRWAfh/TJ3sSkLpSRRpcPdekbuQqkzWaQFmL2MWiSNLIvavXJPw==&lt;/diagram&gt;&lt;diagram id=&quot;YGNCn-TlKjC31DqxavB_&quot; name=&quot;Página-2&quot;&gt;7VxNk6o4FP01LrUgIYBLv7p70TP1pnox85a0RGUKiYXxif3rJzRBhETxjQoJ5aaLXCTAyT0n916S7sHJOnmNvc3qD+LjsAcMP+nBaQ8AFyL2NzUcMsMQ2ZlhGQd+ZjILw0fwhbnR4NZd4ONt6YeUkJAGm7JxTqIIz2nJ5sUx2Zd/tiBh+a4bb4kFw8fcC0Xr34FPV/y1gFPY33CwXOV3Nu1hdmbt5T/mb7JdeT7Zn5jgrAcnMSE0O1onExym2OW4LEb9SeD+mazG79u/+l8LOPvR72edvfzOJcdXiHFE79s1yLr+5YU7jtdrD9ghu8v4M2ZHy/TIGJj8Ebb0kOPKOmdDyBrj/Sqg+GPjzdMze+ZEzLai65C1THbobTfZuC6CBLNnGfNb4pjipDJGNS9oHlFn3orJGtP4wK7jvVgGHyjuqcjh7X0x7hY3rU6GPLd53NOWx54LNNkBB/Q3wIUCuFMZuAbSAFxXMWyRgO1Mhi0AGmBrW4qBawvgjqWqMNQAXGQrBq4jgDuSggs1ABeo5rmuAO6bvvOZapo7FMCdSOczVwNwTdVkIY+XT9B90dZ1IVANXUkc4LM8gTcjEqXwxWQX+SkwU4O1SExXZEkiL3wnZMMh/BdTeuBZjrejpAwwwyw+/JNeP0B58yfv7rsxTUqtw7Hlj9Jcp3gUZnkJ0nfMzicBPemWtX7md2THRadpI+8ze+H0Lf/HyDKkyC6e40u/y7M5L17iSx1CuavEOPRo8Kv8dHcfeEuMZQypK7x7nyzxLdMlDJYRO54zwHDMDClRApZajviJdeD74bfj4G3w5X1+95divyFBRL9fBY17aHqJaTzv5RcXj1c/TuAiBfvGACKXu/3VWPPufqTPX9C3cgFZLLZsxKtDc3yGG2gqCXqeNG2GpsNWaSpGxZJ5TkuanpG/gqZ5KYqT7UbKNkBSU5RUPdIVsxKWWKjtsERS+nnq3W16Z12pd6Yh95WGBE/MVI2uBCaoTvEQzMMyTsT+jaLXeJxia81bZTh4JoRtiIJiPcPoStBh11HQsixT+UDD0ZplWs+ObpvMRGItzOzK5OjUMRPayCpNjurz1BKFdAB1SAiqn4xbTwjOZL1PybtB8oZXSp55xlcaikYkJOqG5IHLHEyDEQTKkgdVl7y8SvPkafM8PTODNkRTceFJR3IGUPs9wTHQUHVimpKkbgAk6bpysUj1izSEbcciz+LkvTUun9hqNe5M/t5Q+iUp8HdE464pTZY/x6gfiuhdi9SapmfcqSGags6GIvXlS0d5Woqrv9lj67B4y1auKCJZUPhUuNsUzrlS4cx2l4WIEteVSORMgf1kWYjruLeJXCK94IGSJ9kP8ORpQzy1WuWpONl1JRQ5o38FT23XKBcv88HVZTEDENfeMQrosLcHVCKVY7u1HX/PsvC9FRBeu34VtFsXFj9ZdyRSgbV1YYRgWQHBbQL4eMmTfZzWiKfqcK7dvR1inbIjUQesXTTu2rCyhFL5QiW8arjUCzIqe1zb3soGxYUC04mAIwOBPs7jU6nbZqpnPhB6F5WQt2wReiiBHjwMevHj73Qy6ib21b0S0LrO7x8HvriT7+X1rZvgw8q3YJnnNwu+mCOOZ93EHtmqqY64VYSpTmd934SVpN4U8XcaxV9cUpLh31UGVFeiuOIAuPcZANYs/n9WFmcW/4QMzv4D&lt;/diagram&gt;&lt;/mxfile&gt;" style="background-color: rgb(255, 255, 255);"><defs/><g><ellipse cx="352" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 333px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">G<br />0.11</div></div></div></foreignObject><text x="352" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">G...</text></switch></g><ellipse cx="32" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 13px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">D<br />0.05</div></div></div></foreignObject><text x="32" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">D...</text></switch></g><ellipse cx="592" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 573px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">E<br />0.22</div></div></div></foreignObject><text x="592" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">E...</text></switch></g><ellipse cx="512" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 493px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">B<br />0.19</div></div></div></foreignObject><text x="512" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">B...</text></switch></g><ellipse cx="192" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 173px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">A<br />0.13</div></div></div></foreignObject><text x="192" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">A...</text></switch></g><ellipse cx="432" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 413px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">H<br />0.11</div></div></div></foreignObject><text x="432" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">H...</text></switch></g><ellipse cx="112" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 93px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">C<br />0.08</div></div></div></foreignObject><text x="112" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">C...</text></switch></g><ellipse cx="272" cy="532" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 532px; margin-left: 253px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">F<br />0.11</div></div></div></foreignObject><text x="272" y="536" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">F...</text></switch></g><path d="M 72 432 L 32 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 459px; margin-left: 60px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="60" y="462" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 72 432 L 112 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 461px; margin-left: 89px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="89" y="464" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="72" cy="412" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 412px; margin-left: 53px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.13</div></div></div></foreignObject><text x="72" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.13</text></switch></g><path d="M 352 432 L 272 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 450px; margin-left: 333px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">00</div></div></div></foreignObject><text x="333" y="454" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">00</text></switch></g><path d="M 352 432 L 352 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 455px; margin-left: 353px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">01</div></div></div></foreignObject><text x="353" y="458" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">01</text></switch></g><path d="M 352 432 L 432 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 458px; margin-left: 379px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">10</div></div></div></foreignObject><text x="379" y="461" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">10</text></switch></g><ellipse cx="352" cy="412" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 412px; margin-left: 333px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.33</div></div></div></foreignObject><text x="352" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.33</text></switch></g><path d="M 112 312 L 72 392" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 336px; margin-left: 104px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="104" y="339" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 112 312 L 192 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 342px; margin-left: 124px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="124" y="345" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="112" cy="292" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 292px; margin-left: 93px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.26</div></div></div></foreignObject><text x="112" y="296" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.26</text></switch></g><path d="M 552 432 L 512 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 453px; margin-left: 546px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="546" y="456" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 552 432 L 592 512" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 454px; margin-left: 563px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="563" y="457" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="552" cy="412" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 412px; margin-left: 533px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.41</div></div></div></foreignObject><text x="552" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.41</text></switch></g><path d="M 152 182 L 112 272" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 215px; margin-left: 139px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="139" y="218" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 152 182 L 352 392" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 218px; margin-left: 184px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="184" y="221" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="152" cy="162" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 162px; margin-left: 133px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">0.59</div></div></div></foreignObject><text x="152" y="166" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">0.59</text></switch></g><path d="M 192 52 L 152 142" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 74px; margin-left: 185px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">0</div></div></div></foreignObject><text x="185" y="77" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">0</text></switch></g><path d="M 206.17 46.12 L 552 392" fill="none" stroke="#000000" stroke-miterlimit="10" pointer-events="stroke"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 72px; margin-left: 228px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 11px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; background-color: #ffffff; white-space: nowrap; ">1</div></div></div></foreignObject><text x="228" y="75" fill="#000000" font-family="Helvetica" font-size="11px" text-anchor="middle">1</text></switch></g><ellipse cx="192" cy="32" rx="20" ry="20" fill="#ffffff" stroke="#000000" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 38px; height: 1px; padding-top: 32px; margin-left: 173px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: normal; word-wrap: normal; ">1</div></div></div></foreignObject><text x="192" y="36" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">1</text></switch></g><rect x="17" y="402" width="30" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 412px; margin-left: 32px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">DC</div></div></div></foreignObject><text x="32" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">DC</text></switch></g><rect x="52" y="282" width="40" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 292px; margin-left: 72px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">DCA</div></div></div></foreignObject><text x="72" y="296" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">DCA</text></switch></g><rect x="292" y="402" width="40" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 412px; margin-left: 312px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">FGH</div></div></div></foreignObject><text x="312" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">FGH</text></switch></g><rect x="497" y="402" width="30" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 412px; margin-left: 512px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">BE</div></div></div></foreignObject><text x="512" y="416" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">BE</text></switch></g><rect x="62" y="152" width="70" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 162px; margin-left: 97px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">DCAFGH</div></div></div></foreignObject><text x="97" y="166" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">DCAFGH</text></switch></g><rect x="92" y="22" width="80" height="20" fill="none" stroke="none" pointer-events="all"/><g transform="translate(-0.5 -0.5)"><switch><foreignObject style="overflow: visible; text-align: left;" pointer-events="none" width="100%" height="100%" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"><div xmlns="http://www.w3.org/1999/xhtml" style="display: flex; align-items: unsafe center; justify-content: unsafe center; width: 1px; height: 1px; padding-top: 32px; margin-left: 132px;"><div style="box-sizing: border-box; font-size: 0; text-align: center; "><div style="display: inline-block; font-size: 12px; font-family: Helvetica; color: #000000; line-height: 1.2; pointer-events: all; white-space: nowrap; ">DCAFGHBE</div></div></div></foreignObject><text x="132" y="36" fill="#000000" font-family="Helvetica" font-size="12px" text-anchor="middle">DCAFGHBE</text></switch></g></g><switch><g requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility"/><a transform="translate(0,-5)" xlink:href="https://desk.draw.io/support/solutions/articles/16000042487" target="_blank"><text text-anchor="middle" font-size="10px" x="50%" y="100%">Viewer does not support full SVG 1.1</text></a></switch></svg>
3. Hallar la entropía y longitud media

|Simbolo|Pi   |Hi    |Código|Li|li    |
|-------|-----|------|------|--|------|
|A------|0.13 |0.38  |001   |3 |0.39  |
|B------|0.19 |0.45  |10    |2 |0.38  |
|C------|0.08 |0.29  |0001  |4 |0.32  |
|D------|0.05 |0.22  |0000  |4 |0.20  |
|E------|0.22 |0.48  |11    |2 |0.44  |
|F------|0.11 |0.35  |0100  |4 |0.44  |
|G------|0.11 |0.35  |0101  |4 |0.44  |
|H------|0.11 |0.35  |0110  |4 |0.44  |
|       |1    |H=2.87|-     |- |l=3.05|

4. Eficiencia y Redundancia
- E = H/l => `E = 2.87/3.05 = 0.94` => 94%
- R = 1 - E => `R = 1 - 0.94 = 0.06` => 6% 

___

## Ejercicio 10

- Cierta fuente está compuesta de 6 símbolos que se transmiten con las siguientes probabilidades:
    - P(A) = 0.22
    - P(B) = 0.09
    - P(C) = 0.15
    - P(D) = 0.33 
    - P(E) = P(F)

1. Determinar la Entropía
2. Justificad si la fuente puede codificarse con un código binario de 2 bits. En caso contrario, indicar cuál es el número mínimo de bits.
3. Para el código binario resultante del punto b, calcular E y R. 

___

## Ejercicio 11

- Dada una fuente sin memoria con 32 símbolos equiprobables: 
1. Calcular la entropía de la fuente 
2. ¿Cuál es el significado del valor hallado en el punto anterior?
3. Si los símbolos no fueran equiprobables ¿la entropía sería mayor o menor?

___

## Ejercicio 12

- El proveedor de un novedoso sistema de compresión de archivos afirma que puede comprimir al 16% del tamaño original un texto extenso escrito en inglés sin perder información, es decir que se recupera -al descomprimir el archivo- exactamente el texto original; cada carácter del texto emplea 8 bit en el archivo original. Admitiendo que la entropía de la fuente que emite caracteres del inglés es de 1,6 bit por carácter, justificar -recurriendo al teorema pertinente- si esta pretensión es o no teóricamente posible. 
___

## Ejercicio 13

- Calcular la capacidad de un canal binario simétrico (BSC) cuya probabilidad de error de bit es p = 0,1.
___

# Digitalización de señales 

## Ejercicio 1
Una señal cuyo espectro se extiende hasta 800 kHz debe digitalizarse a 8 Mbps. Calcular el tamaño (en bit) de las muestras si se la muestreará a la mínima frecuencia teórica. 

___

## Ejercicio 2
Calcular la mínima velocidad teórica en Mbps para PCM de diez canales con cuantificación de 128 niveles, si cada señal analógica contiene frecuencias entre 0 y 2 MHz.

___

# Códigos para el control de errores 

## Ejercicio 1
En la siguiente tabla, cada fila corresponde a un código de características diferentes. Completar las celdas vacías.

***Cantidad máxima de bits simultaneamente errados que puede:***

|Distancia de Hamming|Detectar|Corregir|
|--------------------|--------|--------|
|1                   |--------|--------|
|2                   |--------|--------|
|3                   |--------|--------|
|4                   |--------|--------|
|5                   |--------|--------|
|7                   |--------|--------|
|10                  |--------|--------|
|--------------------|14      |--------|
|--------------------|--------|3       |
|--------------------|--------|4       |


___
 
## Ejercicio 2
En cierto sistema de comunicaciones se desea obtener en el receptor los datos correctos sin necesidad de solicitar retransmisión, si el ruido no altera más de 3 bit de cada palabra. 

1. Obtener la mínima distancia de Hamming de los códigos que cumplen con esta especificación. 
2. Justificar si se podría o no cumplir con esta especificación mediante algún código de Hamming. 
___

## Ejercicio 3
Calcular cuántos bits de paridad tendrá el código de Hamming adecuado para 8 bits de datos. Calcular con cuántos bits de datos será necesario agregar otro bit de paridad.
 
___

## Ejercicio 4
Se desea proteger los datos 111010 con un código de Hamming con bits de paridad tales que, en cada caso, la cantidad de unos sea impar (incluyendo al propio bit de paridad). Mostrar el procedimiento de codificación. 

___

## Ejercicio 5
Se recibe 1111010, que se ha transmitido usando el código de Hamming con bits de paridad tales que, en cada caso, la cantidad de unos debería ser impar (incluyendo al propio bit de paridad). Escribir los datos recuperados (sin bits de paridad) luego de la corrección de errores, mostrando el procedimiento de decodificación.

___

## Ejercicio 6
Dada una fuente que emite 4 símbolos, se desean trasmitir aplicando el código de Hamming: 
A= 0011 
B= 0101 
C= 1011 
D= 1110 
1.	Encuentre el código correspondiente para cada símbolo. 
2.	Si los símbolos tuvieran 7 bits ¿cuántos bits de paridad se necesitaría utilizar? 
3.	¿Tiene sentido usar Hamming en un canal con baja intensidad y probabilidad de ruido, como la Fibra Optica? Justificar.

___

## Ejercicio 7
Codificar, aplicando Hamming con paridad IMPAR, los siguientes símbolos
011010
001110
100101

___

## Ejercicio 8
Se transmiten los siguientes símbolos, ya codificados con Hamming:
0000101
0001100
0011001
Determinar si los mismos se encuentran bien codificados. En caso contrario, corregir el bit erróneo.

___

## Ejercicio 9
El siguiente conjunto de bits incluye un CRC que fue generado por el polinomio x4 + x + 1. Verificar si se ha recibido correctamente o con errores:  11010110111110

___

## Ejercicio 10
Un equipo receptor recibe el código 1011001101100 que fue codificado con CRC cuyo polinomio generador es X3 + X2 + 1. Determinar si se el código recibido es correcto o contiene errores.
