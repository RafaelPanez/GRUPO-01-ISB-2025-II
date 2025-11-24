# 📉💓 Laboratorio 10: Procesamiento de señales EKG

##  Índice

- [1. Introducción](#1-introduccion)
- [2. Objetivos](#2-objetivos)
  - [2.1 Objetivo general](#21-objetivo-general)
  - [2.2 Objetivos específicos](#22-objetivos-especificos)
- [3. Metodología](#3-metodologia)
- [4. Resultados](#4-resultados)
  - [4.1 Señal Cruda](#41-señal-cruda)
  - [4.2 Análisis de onda P](#42-analisis-de-onda-p)
  - [4.3 Análisis de onda R](#43-analisis-de-onda-r)
  - [4.4 Análisis de segmento QRS](#44-analisis-de-segmento-qrs)
  - [4.5 Análisis de segmento T](#45-analisis-de-segmento-t)
- [5. Discusión](#5-discusion)
- [6. Conclusiones](#6-conclusiones)
- [7. Referencias](#7-referencias)
- [8. Aporte de los integrantes](#8-aporte)

## 🔍 1. Introducción

La señal del electrocardiograma (ECG) es de gran relevancia clínica, principalmente debido a la detección de anomalías cardiovasculares por medio de la morfología de sus ondas P,QRS y T, las cuales indican el patrón que sigue el corazón para su movimiento [1,2]. Es por ello que el avance en el campo de procesamiento de señales en ECG es de vital importancia, en la cual se incluye el diseño y mejora de algoritmos de identificación de ondas P, QRS y T, entre otras características temporales y morfológicas [1,2].

El principal objetivo de este campo es el diseño de algoritmos robustos que logren delinear con precisión los inicios, picos y finales de cada onda en cada latido [3]. A partir de ello, se podrán entrenar modelos de sistema de clasificación, los cuales serán capaces de distinguir patrones normales de los correspondientes a distintas clases patológicas [3]. El procesamiento previo se integra con el análisis de características morfológicas para completar el ciclo de reconocimiento automático [3].

<div align="center">

![img](Lab10/img.PNG)

</div>

## 🎯 2. Objetivos

### 2.1 Objetivo general

- Reconocer las ondas P, QRS y T de una señal EKG proveniente de una de las diecisiete clases del dataset del artículo “Novel methodology of cardiac health recognition based on ECG signals and evolutionary-neural system”

### 2.2 Objetivos específicos
- Importar las líbrerías de Python adecuadas para la detección de ondas en señales EKG.
- Aplicar filtros de distintos tipos para preparar la señal para el algoritmo de detección de ondas en señales EKG.
- Complementar la detección de ondas en señales con el cálculo de parámetros elementales de la señal EKG. 

## ⚙️💻 3. Metodología

El procesamiento se estructuró de manera que cada etapa respondiera a una necesidad específica del análisis ECG: eliminación de ruido, estabilización de la línea isoeléctrica, y posterior delineación de ondas P, QRS y T mediante algoritmos complementarios. A continuación, se describe el flujo metodológico y la lógica detrás de cada elección.

### 3.1. Importación de librerías y carga del dataset.
Se utilizaron numpy y scipy.signal para manipulación numérica y filtrado, matplotlib para visualización, pywt para transformada wavelet y neurokit2 como referencia validada para la detección de ondas. El dataset se cargó en formato pickle y se seleccionó el canal 1 de la clase NSR, lo que permitió trabajar con una señal de ritmo sinusal limpio y con buena relación señal-ruido, adecuada para comparar algoritmos.

### 3.2. Preprocesamiento de la señal.
La señal cruda mostró ruido de alta frecuencia y pequeñas variaciones de la línea base propias del dataset. Para mitigarlo, se aplicaron filtros de banda estrecha centrados en el rango fisiológico del ECG. En particular: Un filtrado básico 0.5–40 Hz (o similar según función), que atenúa ruido muscular y movimientos respiratorios.

En el caso específico de la onda P, se emplearon wavelets para realzar estructuras de baja amplitud. El uso de pywt permitió resaltar componentes entre 5–15 Hz, banda donde la P es más distinguible pese a su morfología pequeña y variable.

### 3.3. Detección de ondas P mediante dos enfoques.
Se compararon dos metodologías distintas:

* Método manual (detect_pwaves_only()): combinó filtrado, realce wavelet y umbrales adaptativos. Este enfoque no depende de la posición del R-peak, lo que permite evaluar el desempeño ante señales donde QRS no es necesariamente confiable. La contrapartida es su mayor sensibilidad al ruido y su tendencia a sobreestimar la duración.

* Método NeuroKit2: utiliza una cadena integrada de preprocesamiento, detección de R-peaks y alineamiento basado en ventanas fisiológicas, lo que produce estimaciones más estables. Se empleó la función ecg_process, que genera automáticamente los índices de inicio, pico y final de la onda P.

### 3.4. Detección de ondas R y cálculo de frecuencia cardiaca.
Para la onda R se emplearon también dos métodos:

* Método manual (promediado móvil + umbrales + detect_qrs_rpeaks): el promediado móvil reduce fluctuaciones rápidas, facilitando que los umbrales detecten picos prominentes. Posteriormente, se aplicó detect_qrs_rpeaks() para refinar la detección. El cálculo del RR se realizó mediante la función rr_intervals_ms.

* Método NeuroKit2: la detección automática de R-peaks utiliza heurísticas robustas inspiradas en Pan-Tompkins, con corrección de falsos positivos y ajuste de ventanas. Esto permitió obtener una frecuencia cardíaca más estable y fisiológicamente coherente.

### 3.5. Detección del complejo QRS.
Se utilizó exclusivamente NeuroKit2 para este segmento debido a que su delineación integrada (puntos Q, R y S) es más confiable que los métodos manuales, especialmente para señales sin patología evidente. El algoritmo corrige desplazamientos de índices y asegura que cada latido tenga marcados los tres componentes, lo cual es crucial para calcular duración y amplitud.

### 3.6. Detección y análisis de la onda T.
La onda T fue analizada mediante el pipeline de NeuroKit2, que identifica automáticamente sus puntos clave considerando la localización del complejo QRS previo. Este procedimiento permite evaluar duración, amplitud y el intervalo Tp-Te, métrica de repolarización ventricular asociada al riesgo arrítmico.

## 📊 4. Resultados

<div align="center">

### 4.1 Señal cruda

![Cruda](Lab10/crudo.PNG)

### 4.2 Análisis de onda P

| Nombre | detect_pwaves_only()  | NeuroKit2 |
|------------|-------------|----------------|
| Detección P |  ![P1](Lab10/deteccionP1.PNG) | ![P2](Lab10/deteccionP2.PNG) |
| Duración promedio | 116.6 ms | 89.63 ms |
| Amplitud promedio | 0.022 mV |  0.044 mV |
| Dispersión | 31.81 ms | 27.78 ms |

### 4.3 Análisis de onda R

| Nombre | detect_qrs_rpeaks | NeuroKit2 |
|------------|-------------|----------------|
| Detección R | ![R1](Lab10/deteccionR1.PNG) | ![R2](Lab10/deteccionR2.PNG) |
| Aproximación BPM | ![bpm1](Lab10/bpm.PNG) | ![bpm2](Lab10/bpm2.PNG) |

| Nombre | rr_intervals_ms | NeuroKit2 |
|------------|-------------|----------------|
| Duración promedio | 555.39 ms | 628.57  ms |
| BPM promedio | 121.4 bpm | 95.98 bpm |

### 4.4 Análisis de segmento QRS

| Nombre | NeuroKit2 |
|------------|-------------|
| Detección QRS | ![QRS](Lab10/QRS.PNG) |
| Duración promedio | 78.17 ms |
| Amplitud promedio | 1.941 mV |
| Duración QRS mínima | 72.22 ms | 
| Duración QRS máxima | 83.33 ms |
| N° latidos analizados | 14 |

### 4.5 Análisis de onda T

| Nombre | NeuroKit2 |
|------------|-------------|
| Detección ondas T | ![T](Lab10/deteccionT.PNG) |
| Duración promedio | 167.06 ms |
| Amplitud promedio | 0.039 mV |
| TpTe promedio | 80.36 ms | 

</div>

## 🧠 5. Discusión

Los resultados muestran diferencias claras entre los métodos propios y las funciones de NeuroKit2, y esas discrepancias ayudan a entender tanto las limitaciones técnicas como la sensibilidad de cada enfoque. En la onda P, el método detect_pwaves_only() produjo duraciones mayores y amplitudes menores que NeuroKit2. Esto tiene sentido: al apoyarse en filtros y wavelets sin referencia directa al complejo QRS, el algoritmo propio es más vulnerable al ruido de baja amplitud y tiende a “ensanchar” la detección, mientras que NeuroKit2 utiliza un pipeline optimizado que incorpora alineamiento respecto a los R-peaks, lo que reduce solapamientos y mejora la estimación temporal en ondas pequeñas. La dispersión menor obtenida con NeuroKit2 también sugiere mayor estabilidad interlatido.

En la onda R, ambos métodos identificaron correctamente los picos, aunque la variabilidad en la frecuencia cardíaca obtenida con el algoritmo propio es mayor y muestra valores atípicos. Esto ocurre porque el cálculo mediante promediado móvil + umbrales es sensible a pequeños errores en la posición del R-peak; basta desplazar un índice por unos milisegundos para alterar de manera drástica un RR interval. NeuroKit2, en cambio, incorpora correcciones post-detección y un filtrado más robusto, lo cual se refleja en un BPM más fisiológico y estable.

Para el complejo QRS, NeuroKit2 mostró duraciones en el rango normal (aprox. 72–83 ms) y amplitudes coherentes (~1.9 mV). La estabilidad en estos parámetros sugiere que la señal seleccionada del dataset NSR tiene buena calidad y que el algoritmo de delineación de Q, R y S está funcionando de manera consistente. Finalmente, en la onda T, la detección resultó uniforme y con métricas fisiológicamente plausibles: duración promedio de 167 ms y Tp-Te alrededor de 80 ms, valores típicos en ritmos sinusales normales sin repolarización patológica. En conjunto, los resultados confirman que NeuroKit2 ofrece segmentaciones más regulares, mientras que los métodos manuales permiten entender mejor la lógica detrás de la detección, pero sacrifican precisión cuando la amplitud es baja o el ruido relativo es alto.


## 📌 6. Conclusiones

El análisis permitió identificar con éxito las ondas P, QRS, R y T de una señal ECG correspondiente al ritmo sinusal normal (NSR). Los métodos implementados manualmente cumplieron su función educativa al evidenciar cómo filtros, wavelets y umbrales pueden generar detectores funcionales, aunque más sensibles al ruido y a la variabilidad entre latidos. En contraste, NeuroKit2 proporcionó mediciones más estables y fisiológicamente coherentes, reflejando la ventaja de algoritmos optimizados que integran correlaciones entre ondas y correcciones post-procesamiento.

A nivel morfológico, los parámetros obtenidos (duración de P ~90–116 ms, QRS ~78 ms, T ~167 ms, BPM ~96–121) se encuentran dentro de los rangos esperados para un sujeto con ritmo sinusal, lo cual valida tanto la calidad de la señal utilizada como la eficacia de los algoritmos aplicados. La diferencia en los valores de BPM entre métodos evidencia la importancia de una buena detección de R-peaks para evitar errores acumulativos en RR y frecuencia cardíaca.

En conjunto, el laboratorio demuestra que la detección automática de ondas ECG exige un preprocesamiento adecuado y algoritmos robustos, especialmente cuando se trabaja con ondas de baja amplitud como la P. Asimismo, confirma que herramientas como NeuroKit2 pueden servir como referencia para validar métodos propios y para la futura implementación de clasificadores o sistemas automáticos de análisis cardíaco.


## 📚🔗 7. Referencias

[1] A. Zyout, H. Alquran, W. A. Mustafa y A. M. Alqudah, “Advanced Time-Frequency Methods for ECG Waves Recognition”, Diagnostics, vol. 13, n.º 2, p. 308, enero de 2023. Accedido el 24 de noviembre de 2025. [En línea]. Disponible: https://doi.org/10.3390/diagnostics13020308

[2] R. Costa, T. Winkert, A. Manhães y J. P. Teixeira, “QRS Peaks, P and T Waves Identification in ECG”, Procedia Comput. Sci., vol. 181, pp. 957–964, 2021. Accedido el 24 de noviembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.procs.2021.01.252  

[3] H. Dogan y R. O. Dogan, “A Comprehensive Review of Computer-based Techniques for R-Peaks/QRS Complex Detection in ECG Signal”, Arch. Comput. Methods Eng., abril de 2023. Accedido el 24 de noviembre de 2025. [En línea]. Disponible: https://doi.org/10.1007/s11831-023-09916-x 

## 🗂️ 8. Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |













