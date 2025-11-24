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
- [8. Referencias](#8-referencias)

## 🔍 1. Introducción

La señal del electrocardiograma (ECG) es de gran relevancia clínica, principalmente debido a la detección de anomalías cardiovasculares por medio de la morfología de sus ondas P,QRS y T, las cuales indican el patrón que sigue el corazón para su movimiento [1,2]. Es por ello que el avance en el campo de procesamiento de señales en ECG es de vital importancia, en la cual se incluye el diseño y mejora de algoritmos de identificación de ondas P, QRS y T, entre otras características temporales y morfológicas [1,2].

El principal objetivo de este campo es el diseño de algoritmos robustos que logren delinear con precisión los inicios, picos y finales de cada onda en cada latido [3]. A partir de ello, se podrán entrenar modelos de sistema de clasificación, los cuales serán capaces de distinguir patrones normales de los correspondientes a distintas clases patológicas [3]. El procesamiento previo se integra con el análisis de características morfológicas para completar el ciclo de reconocimiento automático [3].

<div align="center">

![img](Lab10/img.png)

</div>

## 🎯 2. Objetivos

### 2.1 Objetivo general

- Reconocer las ondas P, QRS y T de una señal EKG proveniente de una de las diecisiete clases del dataset del artículo “Novel methodology of cardiac health recognition based on ECG signals and evolutionary-neural system”

### 2.2 Objetivos específicos
- Importar las líbrerías de Python adecuadas para la detección de ondas en señales EKG.
- Aplicar filtros de distintos tipos para preparar la señal para el algoritmo de detección de ondas en señales EKG.
- Complementar la detección de ondas en señales con el cálculo de parámetros elementales de la señal EKG. 

## ⚙️💻 3. Metodología

1. Se importan las librerías correspondientes. Se descargó neurokit2, numpy, scipy.signal, matplotlib.pyplot, pickle y pywt. 
2. Se carga dataset del formato pickle. Se selecciona el **canal 1** de la **clase NSR** y se grafica señal cruda. 
3. Se realiza la detección de ondas ECG:

- **Ondas P**: Se emplearán dos métodos de detección. El primero consiste en la detección de picos de la onda P por medio de diversos filtros y umbrales sin necesidad de contar previamente con la ubicación de los picos R (detect_pwaves_only()). Por otro lado, el segundo método utiliza la función ecg_process de NeuroKit2. Para la estimación de parámetros, también se emplearon dos métodos. El primero parte de la detección de detect_pwaves_only() y filtros wavelet, además de las fórmulas para hallar los estadísticos. El segundo parte de NeuroKit2, especialmente de nk.ecg_process.
- **Ondas R**: Se emplearán dos métodos de detección. El primero consiste en una mezcla de promediado móvil y umbrales, para luego aplicar la función detect_qrs_rpeaks. Para el cálculo de parámetros se trabajó sobre este método usando la función rr_intervals_ms. En el segundo método, ya sea para detección o estimación, se aplica la librería NeuroKit2.
- **Ondas QRS**: Tanto en el proceso de detección y estimación de parámetros se aplicarán las funciones ofrecidas por la librería NeuroKit2.
- **Ondas T**: Tanto en el proceso de detección y estimación de parámetros se aplicarán las funciones ofrecidas por la librería NeuroKit2. 

## 📊 4. Resultados

<div align="center">

### 4.1 Señal cruda

![Cruda]()

### 4.2 Análisis de onda P

| Nombre | detect_pwaves_only()  | NeuroKit2 |
|------------|-------------|----------------|
| Detección P |  ![P1](Lab10/deteccionP1.png) | ![P2](Lab10/deteccionP2.png) |
| Duración promedio | 116.6 ms | 89.63 ms |
| Amplitud promedio | 0.022 mV |  0.044 mV |
| Dispersión | 31.81 ms | 27.78 ms |

### 4.3 Análisis de onda R

| Nombre | detect_qrs_rpeaks | NeuroKit2 |
|------------|-------------|----------------|
| Detección R | ![R1](Lab10/deteccionR1.png) | ![R2](Lab10/deteccion.png) |
| Aproximación BPM | ![bpm1](Lab10/bpm.png) | ![bpm2](Lab10/bpm2.png) |

| Nombre | rr_intervals_ms | NeuroKit2 |
|------------|-------------|----------------|
| Duración promedio | 555.39 ms | 628.57  ms |
| BPM promedio | 121.4 bpm | 95.98 bpm |

### 4.4 Análisis de segmento QRS

| Nombre | NeuroKit2 |
|------------|-------------|
| Detección QRS | ![QRS](Lab10/QRS.png) |
| Duración promedio | 78.17 ms |
| Amplitud promedio | 1.941 mV |
| Duración QRS mínima | 72.22 ms | 
| Duración QRS máxima | 83.33 ms |
| N° latidos analizados | 14 |

### 4.5 Análisis de onda T

| Nombre | NeuroKit2 |
|------------|-------------|
| Detección ondas T | ![T](Lab10/deteccionT.png) |
| Duración promedio | 167.06 ms |
| Amplitud promedio | 0.039 mV |
| TpTe promedio | 80.36 ms | 

</div>

## 🧠 5. Discusión

## 📌 6. Conclusiones

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




