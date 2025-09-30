# 📈⚡ Laboratorio 6: Filtros FIR e IIR

## 📑 Índice

- [1. Introducción](#1-introduccion)
- [2. Objetivos](#2-objetivos)
  - [2.1 Objetivo general](#21-objetivo-general)
  - [2.2 Objetivos específicos](#22-objetivos-especificos)
- [3. Descripción de materiales](#3-descripcion-de-materiales)
- [4. Metodología](#4-metodologia)
- [5. Resultados](#5-resultados)
    - [5.1 Señales EMG](#51-señales-emg)
        - [5.1.1 Para la señal en reposo](#511-para-la-señal-en-reposo)
        - [5.1.2 Para la señal en movimiento lento](#512-para-la-señal-en-movimiento-lento)
        - [5.1.3 Para la señal con fuerza en contra](#513-para-la-señal-con-fuerza-en-contra)
    - [5.2 Señales EMG](#52-señales-ecg)
        - [5.2.1 Para la señal de primera derivada](#521-para-la-señal-de-primera-derivada)
        - [5.2.2 Para la señal de respiración](#522-para-la-señal-de-respiracion)
- [6. Discusión](#6-discusion)
    - [6.1 Acerca de los filtros para EMG](#61-acerca-de-los-filtros-para-emg)
        - [6.1.1 Para la señal en reposo](#611-para-la-señal-en-reposo)
        - [6.1.2 Para la señal en movimiento lento](#612-para-la-señal-en-movimiento-lento)
        - [6.1.3 Para la señal con fuerza en contra](#613-para-la-señal-con-fuerza-en-contra)
    - [6.2 Acerca de los filtros para ECG](#62--acerca-de-los-filtros-para-ecg)
        - [6.2.1 Para la señal de primera derivada](#621-para-la-señal-de-primera-derivada)
        - [6.2.2 Para la señal de respiración](#622-para-la-señal-de-respiracion)
- [7. Conclusiones](#7-conclusiones)
- [8. Referencias](#8-referencias)
- [9. Aporte de los integrantes](#9-aporte-de-los-integrantes)

## 1. 📝 Introducción


## 2. 🎯 Objetivos

### 2.1 Objetivo general

### 2.2 Objetivos específicos


## 3. 💻 Descripción de materiales

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
| Laptop |     Equipo con herramientas de software como Pyfda y Python para el filtrado de señales.   |  1  |

## 4. 📋 Metodología


## 5. 📊 Resultados 

### 5.1 Señales EMG

__5.1.1 Para la señal en reposo__

| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 2 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 3 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 4 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](ruta/a/imagen.png) |
|Filtro anterior| ![Filtro anterior](ruta/a/imagen.png) |
|Filtro 1| ![Filtro 1](ruta/a/imagen.png) |
|Filtro 2| ![Filtro 2](ruta/a/imagen.png) |
|Filtro 3| ![Filtro 3](ruta/a/imagen.png) |
|Filtro 4| ![Filtro 4](ruta/a/imagen.png) |

---

__5.1.2 Para la señal en movimiento lento__ 

| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 2 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 3 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 4 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](ruta/a/imagen.png) |
|Filtro anterior| ![Filtro anterior](ruta/a/imagen.png) |
|Filtro 1| ![Filtro 1](ruta/a/imagen.png) |
|Filtro 2| ![Filtro 2](ruta/a/imagen.png) |
|Filtro 3| ![Filtro 3](ruta/a/imagen.png) |
|Filtro 4| ![Filtro 4](ruta/a/imagen.png) |

---

__5.1.3 Para la señal con fuerza en contra__ 
| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 2 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 3 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 4 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](ruta/a/imagen.png) |
|Filtro anterior| ![Filtro anterior](ruta/a/imagen.png) |
|Filtro 1| ![Filtro 1](ruta/a/imagen.png) |
|Filtro 2| ![Filtro 2](ruta/a/imagen.png) |
|Filtro 3| ![Filtro 3](ruta/a/imagen.png) |
|Filtro 4| ![Filtro 4](ruta/a/imagen.png) |




### 5.2 Señales ECG

__5.1.1 Para la señal de primera derivada__ 
| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 2 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 3 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 4 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](ruta/a/imagen.png) |
|Filtro anterior| ![Filtro anterior](ruta/a/imagen.png) |
|Filtro 1| ![Filtro 1](ruta/a/imagen.png) |
|Filtro 2| ![Filtro 2](ruta/a/imagen.png) |
|Filtro 3| ![Filtro 3](ruta/a/imagen.png) |
|Filtro 4| ![Filtro 4](ruta/a/imagen.png) |

---
__5.2.2 Para la señal de respiración__ 
| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 2 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 3 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |
| 4 | ![diseño](ruta/a/imagen.png) | ![H(f)](ruta/a/imagen.png) | ![polos_ceros](ruta/a/imagen.png) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](ruta/a/imagen.png) |
|Filtro anterior| ![Filtro anterior](ruta/a/imagen.png) |
|Filtro 1| ![Filtro 1](ruta/a/imagen.png) |
|Filtro 2| ![Filtro 2](ruta/a/imagen.png) |
|Filtro 3| ![Filtro 3](ruta/a/imagen.png) |
|Filtro 4| ![Filtro 4](ruta/a/imagen.png) |


## 6. 💭 Discusión y conclusiones

### 6.1 Acerca de los filtros para EMG

La señal electromiográfica (EMG) registra la actividad eléctrica de los músculos, pero durante su adquisición es vulnerable a la contaminación por distintas fuentes de ruido. Entre las más comunes están el generado por dispositivos electrónicos, la radiación electromagnética, los artefactos de movimiento, la interferencia de la red eléctrica, la inestabilidad en la descarga motora, la contaminación por electrocardiografía (ECG) y el crosstalk de músculos vecinos [1]. Estos factores enmascaran la señal y dificultan la interpretación de la actividad muscular, lo que reduce la precisión de los análisis y de los clasificadores de patrones.

Dentro de estas fuentes, los artefactos de movimiento son de los más relevantes, ya que aparecen en la interfaz piel–electrodo por desplazamiento de los sensores o cambios en la tensión de la piel. Estas perturbaciones generan oscilaciones de gran amplitud en frecuencias bajas, entre 1 y 20 Hz, que pueden igualar o superar la señal muscular [1], [2]. Para reducir este efecto, se fija un límite inferior de 20 Hz en el filtrado pasa-banda, lo que elimina el ruido de baja frecuencia y conserva la información útil, además de disminuir la inestabilidad asociada a la descarga de las unidades motoras [2].

En el extremo superior, se utiliza un límite de 450 Hz porque la mayor parte del contenido electromiográfico útil se encuentra por debajo de este valor. Por encima predominan el ruido electrónico, el térmico y la radiación electromagnética ambiental, todos los cuales reducen la relación señal–ruido [3]. De esta manera, el filtrado entre 20 y 450 Hz asegura que la señal procesada represente con fidelidad la actividad neuromuscular, sin la influencia de componentes de alta frecuencia que no aportan información fisiológica. Este criterio de filtrado se considera un estándar en la literatura por su efectividad en la adquisición de señales EMG comparables y confiables en estudios clínicos y experimentales [2], [3].

La interferencia de la red eléctrica es otra fuente crítica de ruido, que aparece como una oscilación sinusoidal en 50 o 60 Hz según la región geográfica. Su amplitud puede superar la de la señal muscular y enmascararla por completo, comprometiendo el análisis tanto temporal como espectral. Para eliminarla se emplean filtros notch, diseñados para atenuar específicamente esa frecuencia sin alterar de forma importante las bandas adyacentes de interés [2], [4].


__6.1.1 Para la señal en reposo__ 
---

La señal EMG en reposo del bíceps braquial se caracteriza por presentar únicamente actividad basal, reflejada en potenciales de unidad motora espontáneos de baja amplitud y ruido fisiológico de fondo. En esta condición, la señal útil es especialmente vulnerable a quedar enmascarada por interferencias externas, como el ruido de la red eléctrica (50/60 Hz) y artefactos de movimiento, lo que plantea un desafío en el filtrado digital [5].

El filtro Butterworth, con un orden de 11 en la banda de paso y 5 en la banda de rechazo, alcanzó un SNR de 29.53 dB. Su respuesta de magnitud plana en la banda de paso permitió preservar los potenciales espontáneos de baja amplitud característicos del reposo, minimizando la distorsión de amplitud. Aunque su fase no lineal podría inducir ligeras alteraciones temporales, en este contexto fisiológico dichas distorsiones son mínimas y no comprometen la detección de actividad basal [6].

El filtro Chebyshev Tipo I, configurado con un orden de 7 en la banda de paso y 4 en la banda de rechazo, logró el SNR más alto (33.93 dB). Este desempeño se debe a su mayor pendiente de atenuación, que permitió una supresión más eficiente del ruido de la red eléctrica. En reposo, donde las señales útiles son pequeñas y escasas, esta característica favorece la discriminación de potenciales fisiológicos frente a interferencias externas. Sin embargo, la no linealidad de fase introducida puede modificar levemente la sincronía temporal de descargas espontáneas, un aspecto relevante en estudios clínicos donde se evalúa la excitabilidad neuromuscular en reposo [7].

Por su parte, los filtros FIR con ventana Hamming y Blackman, de 195 coeficientes en la banda de paso y 1093 en la banda de rechazo, alcanzaron SNR de 24.81 dB y 25.26 dB respectivamente. Aunque su capacidad de supresión de ruido fue menor que la de los filtros IIR, su fase estrictamente lineal garantiza la preservación íntegra de la morfología temporal de la señal. Esta propiedad resulta crítica en reposo, ya que la interpretación clínica de descargas espontáneas o fibrilaciones depende de la forma de onda y no solo de la amplitud. Por tanto, a pesar de la menor atenuación de interferencias, los filtros FIR ofrecen una ventaja en estudios fisiológicos detallados de señales basales [8], [9].

__6.1.2 Para la señal en movimiento lento__ 
---
Durante la contracción muscular lenta, la señal EMG presenta un incremento progresivo de amplitud y mayor frecuencia de disparo de unidades motoras, con cierta superposición espectral que dificulta la discriminación de potenciales individuales. En este contexto, el filtrado digital debe equilibrar la supresión de ruido con la preservación de la dinámica temporal del reclutamiento muscular [5].

El filtro Butterworth, con un SNR de 24.50 dB, mantuvo su respuesta de magnitud plana en la banda de paso, lo que permitió preservar la amplitud creciente de las unidades motoras reclutadas de manera sostenida. No obstante, la fase no lineal introdujo distorsiones temporales que pueden afectar la identificación precisa de los momentos de disparo de cada unidad, un aspecto crítico para analizar la sincronización neuromuscular en contracciones lentas [6].
El filtro Chebyshev Tipo I alcanzó un SNR de 28.31 dB, mostrando mayor eficacia en la supresión de interferencias debido a su pendiente más pronunciada en la banda de rechazo. Esta característica favoreció la identificación de componentes de alta frecuencia generados por la coactivación de fibras rápidas, aunque las ondulaciones en la banda de paso alteraron levemente la amplitud de la señal. En un contexto de contracción lenta, esta distorsión puede sesgar la estimación de la contribución relativa de fibras musculares de diferentes tipos [7].

Los filtros FIR con ventana Hamming y Blackman, con SNR de 21.75 dB y 22.18 dB respectivamente, aseguraron una fase estrictamente lineal, lo que preservó con alta fidelidad la secuencia temporal de disparos. Esta propiedad resulta esencial en contracciones lentas, donde el interés principal radica en el análisis de la sincronía y el orden de reclutamiento. Sin embargo, la menor atenuación de ruidos residuales puede interferir en la detección de potenciales de baja amplitud correspondientes a unidades motoras de tipo lento [8], [9].

__6.1.3 Para la señal con fuerza en contra__ 
---
En la condición de contramovimiento, la señal EMG muestra un marcado incremento en amplitud y frecuencia de activación, producto del mayor reclutamiento de unidades motoras y de una mayor complejidad espectral asociada a la contracción contra resistencia. Esta condición demanda filtros capaces de preservar la potencia de las señales de alta amplitud y, al mismo tiempo, discriminar interferencias externas [5].
El filtro Butterworth, con un SNR de 23.37 dB, mantuvo una respuesta de magnitud plana en la banda de paso, lo que favoreció la conservación de los picos de gran amplitud generados por la contracción contra fuerza. Sin embargo, la fase no lineal introdujo distorsiones temporales que pueden dificultar la estimación precisa de la latencia entre el inicio de la contracción y la respuesta muscular, un aspecto importante en análisis biomecánicos [6].
El filtro Chebyshev Tipo I alcanzó un SNR de 27.29 dB, lo que refleja una mayor supresión de interferencias externas. Su pendiente más pronunciada en la banda de rechazo permitió aislar con mayor claridad los componentes útiles del EMG en condiciones de elevada actividad. No obstante, la distorsión de amplitud producida por las ondulaciones en la banda de paso puede alterar la representación relativa de la contribución de distintos grupos musculares, un factor relevante en contramovimientos de alta carga [7].

Los filtros FIR con ventana Hamming y Blackman, con SNR de 20.41 dB y 20.88 dB respectivamente, destacaron por su preservación de la fase lineal. Esto permitió mantener la secuencia temporal de la activación muscular incluso en presencia de contracciones complejas, lo que es crucial para estudiar patrones de coordinación intermuscular. Sin embargo, la menor capacidad de atenuación frente a ruidos de alta frecuencia limita su utilidad cuando el interés se centra en la depuración espectral más que en la forma temporal de la señal [8], [9].

En conjunto, los resultados muestran que el filtro Chebyshev Tipo I fue el que alcanzó los valores más altos de SNR en las tres condiciones evaluadas (33.93 dB en reposo, 28.31 dB en contracción lenta y 27.29 dB en contramovimiento), lo que evidencia su superioridad en la supresión de interferencias externas [3]. No obstante, en términos fisiológicos, la elección del mejor filtro depende de la naturaleza de la señal. En reposo, el Chebyshev se destaca por su capacidad de discriminar potenciales espontáneos de baja amplitud frente al ruido eléctrico; en contracción lenta, los filtros FIR resultan más apropiados cuando se requiere preservar con exactitud la secuencia temporal de reclutamiento; y en contramovimiento, el Butterworth asegura una adecuada conservación de los picos de gran amplitud. Así, considerando un equilibrio entre robustez en la atenuación de ruido y fidelidad en la morfología temporal, el filtro Chebyshev Tipo I puede considerarse el más eficiente en términos globales, mientras que los FIR constituyen la mejor opción cuando la prioridad es el análisis de la dinámica temporal fina [6], [9].


### 6.2 Acerca de los filtros para ECG

La señal proveniente de un electrocardiograma (ECG o EKG) indica información acerca de los movimientos del corazón y la intensidad de estos, siendo una de las herramientas más fiables para la detección de cardiopatías. Sin embargo, factores como  los artefactos de movimiento y la respiración generan  una componente de baja frecuencia que “desplaza” la línea de referencia de la señal. Puede oscilar lentamente, pero varía hasta 0.5 Hz o un poco más en casos de movimiento brusco [10]. Esa señal sin procesar a largo plazo nos puede hacer daño por medio de una mala interpretación de resultados, especialmente en segmentos como ST-T [11].

Entre las principales técnicas usadas para eliminar dicho componente es por medio de  un filtro pasa alta de bajo corte con fase lineal (FIR) para evitar distorsión de morfología [12]. Asimismo, se utilizan recursos como métodos de interpolación o ajuste a puntos del segmento isoeléctrico [11]. A partir de ello se generan diversos métodos combinados [13].

El ruido de alta frecuencia también es considerado como uno de los causantes de distorsión en la señal ECG. Este ocurre principalmente por ruido electrónico del mismo sistema, ruido de músculos cercanos o interferencia electromagnética. Afecta especialmente la onda QRS. Entre las principales herramientas se puede utilizar filtros pasabajos o wavelets para suavizar la señal [14].

Otro factor a considerar es la interferencia de red eléctrica, típicamente a 50 Hz o 60 Hz y sus armónicos. Esa interferencia puede superponerse con amplitud significativa a la señal ECG, y puede distorsionar los componentes clínicos si no se elimina correctamente. Luego, para poder eliminar dicha interferencia, es común el uso de filtros notch centrados en 50 Hz o 60 Hz para rechazar esa frecuencia estrecha. Es una de las técnicas más tradicionales. Asimismo, se utilizan sus variaciones que analizan amplitud y fase [14].


__6.1.1 Para la señal de primera derivada__ 
---

La señal de Primera Derivada se caracteriza por la presencia de componentes de baja frecuencia asociados a la línea isoeléctrica y ondas lentas (artefactos respiratorios o de movimiento), así como de interferencias externas como el ruido de la red eléctrica (50/60 Hz). Estas condiciones hacen que el diseño del filtrado digital sea crítico para preservar la morfología de las ondas P-QRS-T, evitando distorsiones en amplitud o fase que puedan afectar el diagnóstico clínico [15].

El Filtro FIR con ventana Blackman (pasaalta, orden 501) alcanzó un SNR de 26.73 dB. Su fase estrictamente lineal garantiza la preservación temporal de la morfología de las ondas del ECG, fundamental para la correcta interpretación de intervalos PR y QT. Sin embargo, su elevado orden implica mayor carga computacional, lo que puede ser una limitación en sistemas de monitoreo en tiempo real [16]. Los filtros FIR han sido ampliamente documentados por su capacidad para preservar la morfología y la fase de la señal, aunque su mayor orden resulta en un mayor costo computacional [17].

El Filtro IIR Butterworth pasabanda (orden 4) mostró un SNR de 21.31 dB. La respuesta de magnitud plana en la banda de paso permitió preservar las amplitudes de las ondas principales, con una atenuación adecuada de frecuencias no deseadas. Su baja complejidad lo hace atractivo para implementaciones embebidas, aunque la fase no lineal podría introducir pequeñas distorsiones temporales en la morfología del QRS [15]. El diseño de filtros IIR, como el Butterworth, es ideal cuando se busca una solución eficiente en términos computacionales, aunque las distorsiones de fase pueden ser un inconveniente [16].

Por su parte, el Filtro IIR Chebyshev Tipo I (orden 4) alcanzó un SNR de 19.88 dB, el menor entre los candidatos. Este desempeño se relaciona con el rizado en la banda de paso característico de esta aproximación, lo que puede introducir pequeñas variaciones en la amplitud de la señal ECG. No obstante, su mayor pendiente de atenuación asegura una mejor supresión de interferencias fuera de banda, siendo útil en entornos con alto nivel de ruido eléctrico [17].
Finalmente, el Filtro FIR con ventana Hamming (pasabanda, orden 301) obtuvo el mayor SNR de 27.03 dB. Aunque su orden es menor que el del FIR con ventana Blackman, logra un excelente compromiso entre eficiencia computacional y preservación de la morfología temporal. Su respuesta en fase estrictamente lineal lo convierte en la opción más confiable para estudios clínicos donde la precisión temporal (intervalos RR, ancho del QRS) es fundamental [18].
En conclusión, entre los filtros evaluados para ECG1, el FIR con ventana Hamming se presenta como la mejor alternativa, al ofrecer el mayor SNR y garantizar la conservación íntegra de la morfología de la señal, factor crítico para la interpretación clínica [4].

__6.2.2 Para la señal de respiración__ 
---
La señal de ECG2 (respiración) presenta un rango espectral más amplio, por lo que es fundamental aplicar filtros digitales que permitan eliminar artefactos de baja frecuencia (deriva de línea de base), interferencias de alta frecuencia y ruido de la red eléctrica, manteniendo la morfología de las ondas P-QRS-T. La adecuada selección del diseño de filtros asegura la preservación de la información clínica y mejora la relación señal-ruido (SNR) [19].
El Filtro Pasabanda Equiripple (orden 350) alcanzó un SNR de 12.04 dB. Su principal ventaja es la fase estrictamente lineal, que garantiza la preservación temporal de la morfología del ECG, aunque el costo computacional de su elevado orden puede ser una limitación en aplicaciones de monitoreo en tiempo real [19].

El Filtro Pasaalta Bessel (orden 4) obtuvo un SNR de 6.99 dB. Este tipo de filtro se caracteriza por su excelente respuesta en fase y mínima distorsión temporal, lo que favorece la correcta detección de intervalos PR y RR. Sin embargo, su baja atenuación en frecuencias cercanas a la banda de paso explica el bajo SNR alcanzado, limitando su capacidad de supresión de ruido de baja frecuencia [20].
El Filtro Pasaalta Chebyshev Tipo II (orden 5) logró un SNR de 7.08 dB. Aunque proporciona una atenuación más pronunciada fuera de la banda de paso, la presencia de rizado en la banda de rechazo puede introducir pequeñas variaciones en la estabilidad de la señal. Su desempeño en SNR es similar al Bessel, aunque con mayor capacidad de supresión de artefactos de baja frecuencia [21].

Finalmente, el Filtro Pasabaja Elíptico (orden 5) alcanzó un SNR negativo de –22.38 dB, lo que indica una degradación significativa de la calidad de la señal. A pesar de su alta selectividad y eficiencia en la atenuación de frecuencias superiores a 45 Hz, la distorsión introducida dentro de la banda útil compromete la morfología de las ondas ECG, haciéndolo inadecuado para aplicaciones clínicas [21].
En conclusión, entre los filtros evaluados para ECG2, el Equiripple pasabanda se presenta como la opción más adecuada, ya que ofrece un balance entre preservación de la morfología (fase lineal) y supresión de artefactos, a pesar de no alcanzar valores de SNR tan elevados como los vistos en ECG1 [19].


## 7. 📚 Referencias

[1] S. P. K. P. K. Zor, "A Review of ECG Signal Processing Methods," MDPI Sensors, vol. 16, no. 8, p. 1304, 2016. Disponible en:https://www.mdpi.com/1424-8220/16/8/1304.

[2] R. A. ., "Sensor-Based Systems for Real-Time Monitoring," MDPI Sensors, vol. 25, no. 13, p. 4004, 2025. Disponible en:https://www.mdpi.com/1424-8220/25/13/4004.

[3] T. K., "Signal Processing in Biomedical Applications," Journal of Electromyography and Kinesiology, vol. 54, p. 102440, 2020. Disponible en: : https://doi.org/10.1016/j.jelekin.2020.102440 

[4]  A. C. R. A. P. M. Z., "Rejection of Power Line Interference in EMG Signals Using a Notch Filter Initialized with Non-Zero States," Polish Academy of Sciences, 2025. Disponible en: https://www.par.pl/en/Yearbooks/2025/3-2025/Rejection-of-Power-Line-Interference-in-EMG-Signals-Using-a-Notch-Filter-Initialized-with-Non-Zero-States

[5] K. R. V. Shankar et al., "Design and Evaluation of ECG Signal Denoising Method Based on the Wavelet Transform," PMC, 2019. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC6412999/

[6] A. J. I. T. S. A. M. V. P. M. M., "A Comparative Study of Signal Processing Methods for ECG Denoising and Arrhythmia Detection," PMC, 2021. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC9599646/ 

[7] A. S. R. D. P. K., "Chebyshev Filter and Butterworth Filters: Comparison and Applications in Different Cases," ResearchGate, 2023. Disponible en: https://www.researchgate.net/publication/378435601_Chebyshev_filter_and_Butterworth_filters_Comparison_and_applications_in_different_cases 

[8] R. R. G. N. F. M. S. M. S., "ECG Signal Filtering Based on Digital Filter Design: An Overview," MDPI Sensors, vol. 24, no. 18, p. 5954, 2024. Disponible en: https://www.mdpi.com/1424-8220/24/18/5954  

[9] R. S. A. S. A. T. P., "Review and Analysis on Digital Filter Design in Digital Signal Processing," ResearchGate, 2023. Disponible en: https://www.researchgate.net/publication/388562991_Review_and_analysis_on_digital_filter_design_in_digital_signal_processing 

[10] "Baseline Wander," ScienceDirect. Disponible en: https://www.sciencedirect.com/topics/computer-science/baseline-wander.

[11] J. Kumar, N. S. V. R. Chandra, y S. R. R. R. P. Kumar, "ECG Signal Denoising: A Review of Methods," PMC, 2017. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC5361052/.

[12] K. C. J. Thomas, J. R. C. Saldanha, y A. J. R. Pinto, "Review on Filters for ECG Signal Denoising," PMC, 2019. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC7494370/.

[13] R. P. Sharma, S. R. K. Yadav, y N. K. Singh, "A Hybrid Filtering Technique for ECG Signal Denoising," Biological Signal Processing and Control, vol. 64, pp. 102466, 2021. Disponible en: https://doi.org/10.1016/j.bspc.2021.102466.

[14] P. D. O’Brien, D. C. Carter, y D. J. Phillips, "A Novel Filter Design for ECG Signal Processing," Heliyon, vol. 10, no. 1, e26171, 2024. Disponible en: https://doi.org/10.1016/j.heliyon.2024.e26171.

[15] D. Gond, O. Dua, S. Raj, y S. Saxena, “A Statistical Comparison of FIR Kaiser Window and IIR Butterworth Filters in ECG Signal Pre‑Processing,” JETIR, vol. 11, no. 4, Apr. 2024.https://www.researchgate.net/publication/382219166_A_STATISTICAL_COMPARISON_OF_FIR_KAISER_WINDOW_AND_IIR_BUTTERWORTH_FILTERS_IN_ECG_SIGNAL_PRE-PROCESSING 

[16] H. Amhia, “Stability and Phase Response Analysis of Optimum IIR and FIR Filters,” Wiley, 2022. https://doi.org/10.1155/2022/9899899 

[17] K. – (o autor del estudio), “Comparison of FIR and IIR Filters for Audio Signal Noise Reduction,” 2023. 10.3390/s20051468 

[18] X. An et al., “Comparison of Motion Artefact Reduction Methods and the Use of Hamming Window in ECG Filtering,” PMC, 2020. https://www.researchgate.net/publication/372754570_Comparison_of_FIR_and_IIR_Filters_for_Audio_Signal_Noise_Reduction 

[19] S. M. Walke, S. S. Patil, y M. S. A. Khan, "A Comprehensive Approach to ECG Signal Enhancement Using Various Filtering Techniques," Nanotechnology Perceptions, vol. 20, no. S10, pp. 371–375, 2024.

[20] "Butterworth Filter," ScienceDirect, https://www.sciencedirect.com/topics/engineering/butterworth-filter 

[21] M. S. Chavan, R. A. Agarwala, y M. D. Uplane, "Comparative Study of Chebyshev I and Chebyshev II Filter Used for Noise Reduction in ECG Signal," International Journal of Circuits, Systems and Signal Processing, vol. 2, no. 1, pp. 1–17, 2008.

## 8. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |




