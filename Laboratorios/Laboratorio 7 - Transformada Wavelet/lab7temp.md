# 🌊⚙️ Laboratorio 7: Transformada Wavelet

## Índice
- [1. Introducción](#1-introduccion)
- [2. Objetivos](#2-objetivos)
  - [2.1 Objetivo general](#21-objetivo-general)
  - [2.2 Objetivos específicos](#22-objetivos-especificos)
- [3. Descripción de materiales](#3-descripcion-de-materiales)
- [4. Metodología y diseño del filtro](#4-metodologia-y-diseño-del-filtro)
- [5. Resultados](#5-resultados)
    - [5.1 Señales EMG](#51-señales-emg)
    - [5.2 Señales ECG](#52-señales-ecg)
    - [5.3 Señales EEG](#52-señales-eeg)
- [6. Discusión](#6-discusion)
    - [6.1 Señales EMG](#51-señales-emg)
    - [6.2 Señales ECG](#52-señales-ecg)
    - [6.3 Señales EEG](#52-señales-eeg)
- [7. Conclusiones](#7-conclusiones)
- [8. Referencias](#8-referencias)
- [9. Aporte de los integrantes](#9-aporte-de-los-integrantes)

## 1.  📝 Introducción

La transformada wavelet es eficiente para el análisis de funciones de onda pequeña, siendo cada día más utilizada en aplicaciones biomédicas [1]. Esta proviene a partir de una función del mismo nombre, cuyas características son poseer media cero y una normalización correcta [1]. La principal ventaja que esta herramienta posee es el uso de ventanas de duración variable, las cuales permiten que se pueda analizar señales con un rango de frecuencias más amplio y variable [1-2].

En cuanto a su aplicación en EMG, la transformada wavelet es capaz de ayudar al preprocesamiento del sEMG y a la eliminación del ruido presencial en la señal, lo cual es importante dada la probabilidad de contaminación que esta señal tiene [3]. Asimismo, se ha innovado en su ejecución y hay métodos de filtrado a partir de este en el cual se aplica técnicas como multicapa y separación de fuentes (Fast-ICA) [3]. 

Por otro lado, en cuanto al EEG, existen estudios recientes en los que se ha desarrollado transformadas wavelet como expansiones redundantes racionales que permiten una mejor representación del contenido frecuencial del EEG para la clasificación de imaginaria motriz [4]. Es decir, la simulación previa a una acción del individuo [4].

Finalmente, en el análisis de ECG, la transformada se ha tomado en cuenta en aspectos como detección de picos R, segmentación de ondas P, QRS, T, eliminación de ruido y compresión de señales [2]. Esto es debido a su capacidad de captar transitorios o  partes agudas de la señal como el complejo QRS. Adicionalmente, la literatura destaca su utilidad en la limpieza de señales y detección automática de anomalías [2].

Es por ello la importancia de realizar pruebas de filtrado con la transformada wavelet y su posterior análisis, como se encontrará en está sección del repositorio. En la Figura 1 se puede observar las fórmulas de la transformada continua y discreta de wavelet. 

|**Figura 1.** a) Transformada wavelet continua. b) Transformada wavelet discreta.|
|------------------------------------------------|
|<div align="center"><img src="https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/be889a9626b379f157d887ff030f638e5035fc0a/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/fig1.PNG" width="500"/></div> |


## 2.  🎯 Objetivos

### 2.1 Objetivo general

- Aplicar la transformada wavelet para el procesamiento de diferentes tipos de señales biomédicas (EMG, ECG, EEG).

### 2.2 Objetivos específicos

- Profundizar conocimientos acerca de la transformada wavelet y sus parámetros.
- Utilizar herramientas como Python para la aplicación de la transformada Wavelet.

## 3. 💻 Descripción de materiales

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
| Laptop |   Laptop con aplicación Python y múltiples librerías (pandas, matplotlib, numpy, scipy).    |  1  |

## 4. 📋 Metodología y diseño de filtro

### 4.1 Pasos 

1. Seleccionar las señales adquiridas y organizarlas en una carpeta.
2. Instalar el programa Python en el entorno virtual de Anaconda.
3. Utilizar Visual Studio Code para la programación en Python con un código iterativo para archivos. 
4. Graficar espectros de frecuencia y resultados de filtración obtenidos.
6. Obtener mediciones como SNR y MSE.
7. Analizar y discutir resultados. 

### 4.2 Filtro para EMG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| Symlets | 5 | Universal Hard | 1000 Hz |

De acuerdo a literatura reciente, el uso de filtros de la familia Symlets ya ha sido utilizado para el filtrado y mejora de las señales EMG. 

Por ejemplo, de acuerdo al estudio “Discrete wavelet transform based processing of embroidered textile-electrode electromyography (2024)”, se obtuvieron mejores cifras de SNR, RMSE y porcentaje de distorsión con el uso de filtros Symlets de nivel 4 y con umbral fuerte sobre señales sEMG [5]. Por lo tanto, se demuestra que la combinación es aplicable para eliminar ruidos indeseados en la señal y al mismo tiempo mantener el balance ante la posible pérdida de información muscular. 

Por otro lado, según el artículo “An improved wavelet threshold denoising approach for surface electromyography signal”, se indica que el umbral hard es aplicado principalmente para la preservación de picos musculares [6]. No obstante, se recomiendan ajustes en los coeficientes independientes y elegir correctamente el método de umbralización adecuado para evitar distorsiones o eliminación de coeficientes menores en las señales procesadas [6]. 

En el presente trabajo se utilizará Symlets de nivel 5 para observar si todavía se cumple el balance entre definición de picos de la señal EMG y la pérdida de información. 


### 4.3 Filtro para ECG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| Daubechies 4 | 5 | Heursure Soft | 1000 Hz |

Al revisar diversos estudios, se consideró los parámetros indicados en la tabla para realizar el filtrado de las señales ECG. 

De acuerdo al estudio “An efficient ECG signals denoising technique based on the on the combination of particle swarm optimisation and wavelet transform” se emplea una mezcla de filtro Daubechies 4 con enjambre de partículas complejo (PSO) para quitar ruidos externos al ECG, con la cual se obtienen resultados positivos [7].

Asimismo, en  “Selection of Wavelet and Thresholding Rule for Denoising the ECG Signals”  se indica que la familia de filtros Daubechies se ha usado comúnmente para denoising, y que las técnicas de umbralización suave son preferibles frente a técnicas duras cuando el objetivo es evitar discontinuidades abruptas [8]. Ello es adecuado para una señal ECG, dado que su morfología consiste en picos continuos de diversa amplitud [8].

Luego, en “A Study of Chosen an Optimum Type of Wavelet Filter for De-Noising an ECG signal” , los autores comparan diferentes familias de wavelet y métodos de umbralización para distintos niveles [9]. Ello ha sido con el fin de seleccionar la combinación que mejor preserve la morfología del ECG y se obtenga un buen SNR. Al final del artículo se concluye que combinar familias de wavelets suaves con reglas de umbral adaptables como Heursure Soft ofrecen el mejor equilibrio [9].

En el presente trabajo se utilizará Daubechies de nivel 5 para obtener una separación de detalles adecuada y se puedan conservar tanto frecuencias altas como bajas. 

### 4.4 Filtro para EEG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| Coiflets | 5 | Universal Soft | 1000 Hz |

Al revisar diversos estudios, se encontró que la familia de filtros wavelet se encuentra entre las familias más utilizadas al aplicar filtros wavelet en EEG. 

Según “Source Localization of EEG Brainwaves Activities via Mother Wavelets Families for SWT Decomposition”, el uso de wavelets Coiflet mejora la preservación de patrones neuronales relevantes al proporcionar una separación de varias frecuencias [10]. Por lo tanto, separa eficazmente las bandas delta, theta, alfa, beta y gamma sin pérdida de resolución, lo cual es muy importante en señales de múltiples frecuencias como EEG [10].

En cuanto a la umbralización, la regla universal suave con la que es aplicada atenúa progresivamente los coeficientes de baja magnitud de manera no abrupta, por lo que ayuda a preservar la información que tiene EEG, el cual, como el ECG, su morfología tiene varios picos en un amplio rango de frecuencias [11].  Ello ha sido encontrado en estudios como  “HAPPILEE: HAPPE In Low Electrode Electroencephalography, a standardized pre-processing software for lower density recordings”, donde combinaciones como wavelet denoising y reconstrucción adaptativa mejora la detectabilidad de fuentes neuronales  [11].

Así como en los casos anteriores, se utilizará el filtro en el nivel 5 para obtener la mayor separación de componentes posible. 


## 5. 📊 Resultados 

### 5.1 Señales EMG
---

| Nombre  | Señal Cruda  | Señal Filtrada | Párametros obtenidos |
|:---------:|:------------:|:------------:|:------------:|
| Reposo | ![Cruda_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGCrudo.png?raw=true) | ![Filtro_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGWavelet.png?raw=true) | MSE: 0.0001 / SNR: 3.40 dB |
| Lento | ![Cruda_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/LentoEMGCrudo.png?raw=true) | ![Filtro_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/LentoEMGWavelet.png?raw=true) | MSE: 0.0003 / SNR: 14.32 dB |
| Contracción | ![Cruda_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ContraEMGCrudo.png?raw=true) | ![Filtro_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ContraEMGWavelet.png?raw=true) | MSE: 0.0006 / SNR: 12.85 dB |

__Adicional 1: Gráficos de frecuencia__

| Nombre  | Señal en frecuencia | Espectrograma |
|:---------:|:------------:|:------------:|
| Reposo | ![f_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_frecuencias.png?raw=true) | ![E_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_espectro.png?raw=true) |
| Lento | ![f_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_frecuencias.png?raw=true) | ![E_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_espectro.png?raw=true) |
| Contra | ![f_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_frecuencias.png?raw=true) | ![E_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_espectro.png?raw=true) |

__Adicional 2: Coeficientes de detalle__

| Reposo  | Lento | Contra |
|:-------:|:----:|:-------:|
| ![CF_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_cf.png?raw=true) | ![CF_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_cf.png?raw=true) | ![CF_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_cf.png?raw=true) | 

### 5.2 Señales ECG
---

| Nombre  | Señal Cruda  | Señal Filtrada | Párametros obtenidos |
|:---------:|:------------:|:------------:|:------------:|
| Reposo | ![Cruda_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGCrudo.png?raw=true) | ![Filtro_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGWavelet.png?raw=true) | MSE: 0.0001 / SNR: 17.84 dB |
| Respirar | ![Cruda_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RespirarECGCrudo.png?raw=true) | ![Filtro_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RespirarECGWavelet.png?raw=true) | MSE: 0.0001 / SNR: 13.93 dB |
| Primera Derivada | ![Cruda_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/PrimeraDerivadaECGCrudo.png?raw=true) | ![Filtro_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/PrimeraDerivadaECGWavelet.png?raw=true) | MSE: 0.0000 / SNR: 22.20 dB |
| Segunda Derivada | ![Cruda_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/SegundaDerivadaECGCrudo.png?raw=true) | ![Filtro_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/SegundaDerivadaECGWavelet.png?raw=true) | MSE: 0.0001 / SNR: 16.51 dB |

__Adicional 1: Gráficos de frecuencia__

| Nombre  | Señal en frecuencia | Espectrograma |
|:---------:|:------------:|:------------:|
| Reposo | ![f_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Reposo_frecuencias.png?raw=true) | ![E_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Reposo_espectro.png?raw=true) |
| Respirar | ![f_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Respirar_frecuencias.png?raw=true) | ![E_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Respirar_espectro.png?raw=true) | 
| Primera Derivada | ![f_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/PrimeraDeri_frecuencias.png?raw=true) | ![E_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/PrimeraDeri_espectro.png?raw=true) |
| Segunda Derivada | ![f_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/SegundaDeri_frecuencias.png?raw=true) | ![E_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/SegundaDeri_espectro.png?raw=true) |

__Adicional 2: Coeficientes de detalle__

| Reposo  | Respirar | Primera Derivada| Segunda Derivada |
|:-------:|:----:|:-------:|:-------:|
| ![CF_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Reposo_cf.png?raw=true) | ![CF_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Respirar_cf.png?raw=true) | ![CF_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/PrimeraDeri_cf.png?raw=true) | ![CF_4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/SegundaDeri_cf.png?raw=true) | 


### 5.3 Señales EEG
---

| Nombre  | Señal Cruda  | Señal Filtrada | Párametros obtenidos |
|:---------:|:------------:|:------------:|:------------:|
| Parpadeo | ![Cruda_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ParpadeoEEGCrudo.png?raw=true) | ![Filtro_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ParpadeoEEGWavelet.png?raw=true) | MSE: 0.1231 / SNR: 32.20 dB |
| Musica | ![Cruda_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/MusicaEEGCrudo.png?raw=true) | ![Filtro_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/MusicaEEGWavelet.png?raw=true) | MSE: 0.1157 / SNR: 33.27 dB |
| Resta | ![Cruda_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RestaEEGCrudo.png?raw=true) | ![Filtro_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RestaEEGWavelet.png?raw=true) | MSE: 0.0930 / SNR: 33.74 dB |
| Copilado | ![Cruda_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/Copilado1EEGCrudo.png?raw=true) | ![Filtro_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/Copilado1EEGWavelet.png?raw=true) | MSE: 0.1419 / SNR: 22.76 dB |

__Adicional 1: Gráficos de frecuencia__

| Nombre  | Señal en frecuencia | Espectrograma |
|:---------:|:------------:|:------------:|
| Parpadeo | ![f_E1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Parpadeo_frecuencias.png?raw=true) | ![E_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Parpadeo_espectro.png?raw=true) |
| Musica | ![f_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Musica_frecuencias.png?raw=true) | ![E_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Musica_espectro.png?raw=true) | 
| Resta | ![f_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Resta_frecuencias.png?raw=true) | ![E_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Resta_espectro.png?raw=true) |
| Copilado | ![f_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Copilado_frecuencias.png?raw=true) | ![E_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Copilado_espectro.png?raw=true) |

__Adicional 2: Coeficientes de detalle__

| Parpadeo | Musica | Resta | Copilado |
|:-------:|:----:|:-------:|:-------:|
| ![CF_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Parpadeo_cf.png?raw=true) | ![CF_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Musica_cf.png?raw=true) | ![CF_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Resta_cf.png?raw=true) | ![CF_4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Copilado_cf.png?raw=true) | 

## 6. 💭 Discusión

En todas las señales biopotenciales (EMG, ECG y EEG) el proceso de filtrado es crucial para eliminar ruido proveniente de interferencias eléctricas, artefactos de movimiento y componentes de alta o baja frecuencia no fisiológicos, por lo que la elección del filtro debe equilibrar la atenuación del ruido con la preservación de las características relevantes del biopotencial [12]. En este caso, los resultados muestran una mejora clara en la relación señal/ruido (SNR) y una reducción del error cuadrático medio (MSE), evidenciando un filtrado efectivo y una reconstrucción fiel de la señal original.

### 6.1 Señales EMG
---
|Comparación de señal cruda y filtrada - Reposo |
|:--------------------------------------------------:|
| ![C_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_comparacion.png?raw=true) |

En la condición de reposo, la señal filtrada (en rojo) evidencia una clara reducción de los picos aleatorios y del ruido de fondo, manteniendo el nivel basal cercano a cero. Esto coincide con el incremento del SNR observado (3.40 dB) y un MSE de 0.0001, lo que sugiere una eliminación eficaz del ruido térmico y eléctrico de baja amplitud.
Además, los filtros wavelet logran este equilibrio al suprimir las componentes de alta frecuencia sin distorsionar la envolvente fisiológica [13].

|Comparación de señal cruda y filtrada - Lento |
|:--------------------------------------------------:|
| ![C_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_comparacion.png?raw=true) |

En la fase lenta, la señal filtrada resalta las regiones activas de contracción, evidenciando una mayor claridad en los pulsos musculares y una mejor diferenciación temporal entre las fases de reposo y activación. El MSE bajo (0.0003) y el SNR de 14.32 dB respaldan esta mejora. 

|Comparación de señal cruda y filtrada - Contracción |
|:--------------------------------------------------:|
| ![C_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_comparacion.png?raw=true) |

Finalmente, durante la contracción rápida, el filtrado conserva la densidad espectral entre 50 y 150 Hz, característica de la actividad mioeléctrica voluntaria [14].


Los espectrogramas y coeficientes de detalle refuerzan esta observación, mostrando un desplazamiento de energía hacia las frecuencias medias tras el filtrado, lo que refleja una correcta eliminación de artefactos de movimiento y de la red eléctrica (60 Hz). Por tanto, el método aplicado resultó óptimo para conservar la información muscular relevante y mejorar la interpretabilidad temporal y espectral de la señal.

### 6.2 Señales ECG
---
|Comparación de señal cruda y filtrada - Reposo |
|:--------------------------------------------------:|
| ![C_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Reposo_comparacion.png?raw=true) |

Las señales ECG presentan una morfología bien preservada después del proceso de filtrado. En la condición de reposo, el filtrado tipo Notch (centrado en 60 Hz) eliminó eficazmente la interferencia de la red eléctrica, realzando los complejos QRS sin distorsionar las ondas P y T. El aumento del SNR hasta 17.84 dB y la baja pérdida de energía (MSE = 0.0001) evidencian un desempeño adecuado.

|Comparación de señal cruda y filtrada - Respirar |
|:--------------------------------------------------:|
| ![C_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Respirar_comparacion.png?raw=true) |

Durante la condición respirar, el ruido por artefacto de movimiento se reduce notablemente, permitiendo distinguir los latidos incluso en presencia de variaciones respiratorias.

|Comparación de señal cruda y filtrada - Primera Derivada |
|:--------------------------------------------------:|
| ![C_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/PrimeraDeri_comparacion.png?raw=true) |

|Comparación de señal cruda y filtrada - Segunda Derivada |
|:--------------------------------------------------:|
| ![C_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/SegundaDeri_comparacion.png?raw=true) |

En las condiciones de primera y segunda derivada, las señales filtradas mantienen la periodicidad de los ciclos cardíacos con una ligera atenuación del nivel de base, sin afectar la morfología del complejo QRS.


Por lo tanto, un filtrado pasa banda entre 0.5–45 Hz, complementado con un filtro Notch, es el más adecuado para preservar los componentes fisiológicos del ECG y eliminar tanto artefactos de movimiento como interferencias electromagnéticas [15].
El análisis temporal demuestra que las características principales se mantienen alineadas entre la señal original y la filtrada, confirmando que la reconstrucción fue precisa y clínicamente útil [16].

### 6.3 Señales EEG
---
|Comparación de señal cruda y filtrada - Parpadeo |
|:--------------------------------------------------:|
| ![C_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Parpadeo_comparacion.png?raw=true) |

|Comparación de señal cruda y filtrada - Musica |
|:--------------------------------------------------:|
| ![C_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Musica_comparacion.png?raw=true) |

En las señales EEG se observa que el filtrado logró conservar los patrones neuronales relevantes, reduciendo a la vez artefactos por parpadeo, movimiento y ruido de alta frecuencia.
Durante la condición de parpadeo, las componentes de baja frecuencia asociadas a los movimientos oculares fueron atenuadas, mientras que en la condición de música la señal filtrada resalta las variaciones rítmicas de mediana frecuencia (8–30 Hz), correspondientes a las bandas alfa y beta.

|Comparación de señal cruda y filtrada - Resta |
|:--------------------------------------------------:|
| ![C_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Resta_comparacion.png?raw=true) |

|Comparación de señal cruda y filtrada - Copilado |
|:--------------------------------------------------:|
| ![C_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Copilado_comparacion.png?raw=true) |

En la condición de resta sucesiva (trabajo mental), la señal se mantiene estable con amplitudes coherentes (entre ±10 μV), mientras que durante la tarea cognitiva (copilado) se aprecia un aumento en la densidad espectral media, lo cual es consistente con un mayor reclutamiento cortical.


El filtrado wavelet empleado redujo el ruido sin eliminar las oscilaciones lentas fisiológicas, aumentando el SNR hasta 33 dB y manteniendo una reconstrucción fiel de la señal original (MSE ≈ 0.1).

Estos resultados coinciden con lo reportado por Subha et al. (2020) y Wang & Liu (2022), quienes demostraron que los métodos basados en wavelet thresholding permiten eliminar artefactos no estacionarios en EEG sin comprometer las bandas cerebrales de interés. Los coeficientes de detalle muestran cómo las variaciones abruptas, típicas de artefactos o interferencias eléctricas, fueron suavizadas, lo que mejora la legibilidad temporal de los eventos neuronales [17], [18].


## 7. 📖 Conclusiones

Se concluye que la transformada wavelet fue adecuada para EMG, ECG y EEG, dado que aumentó el SNR y redujo el MSE sin sacrificar la morfología fisiológica, lo que valida su uso como etapa de preprocesamiento frente a ruido no estacionario y artefactos de movimiento. La reconstrucción temporal y espectral fue coherente con los fenómenos esperados en cada biopotencial.

Para EMG, el filtro Symlets (nivel 5, umbral hard, 1000 Hz) atenuó el ruido manteniendo picos mioeléctricos y la energía principal en ~50–150 Hz. Se observó limpieza en reposo (MSE≈1e-4; SNR≈3.4 dB) y mejora notable durante contracciones (SNR≈14.3 dB en lento y ≈12.9 dB en rápida), sin aplanar la envolvente ni eliminar transitorios útiles.

En ECG, Daubechies-4 (nivel 5, heursure soft, 1000 Hz) combinado con notch de red preservó con fidelidad las ondas P-QRS-T, redujo baseline wander e interferencia de 60 Hz y elevó el SNR (≈17.8 dB en reposo; ≈22.2 dB en primera derivada) con MSE muy bajo (≈0–1e-4). La periodicidad y el alineamiento de complejos se mantuvieron, sosteniendo la utilidad clínica de la señal filtrada.

Finalmente, el filtro Coiflets (nivel 5, soft, 1000 Hz) para EEG disminuyó artefactos oculares y de alta frecuencia, preservando bandas alfa-beta (8–30 Hz). Se mantuvieron SNR altos (≈22–34 dB) con MSE moderado y una reconstrucción que respeta las variaciones por estado (reposo, música, tareas cognitivas).

## 8. 📚 Referencias

[1] M. G. M. Milani, P. E. Abas, and L. C. De Silva, “A critical review of heart sound signals segmentation algorithms,” Smart Health, Art. no. 100283, Apr. 2022. doi: 10.1016/j.smhl.2022.100283

[2] S. B. Shuvo et al., “Application of wavelet transformation and artificial intelligence techniques in healthcare: A systemic review,” WIREs Data Mining and Knowledge Discovery, vol. 15, no. 2, Mar. 2025, Art. no. e70007. doi: 10.1002/widm.70007

[3] W. Lu, D. Gong, X. Xue, and L. Gao, “Improved multi-layer wavelet transform and blind source separation based ECG artifacts removal algorithm from the sEMG signal: In the case of upper limbs,” Frontiers in Bioengineering and Biotechnology, vol. 12, May 2024, Art. 1367929. doi: 10.3389/fbioe.2024.1367929

[4] H. R. Al Ghayab, Y. Li, M. Diykh, A. Sahi, S. Abdulla, and A. R. Alkhuwaylide, “EEG based over-complete rational dilation wavelet transform coupled with autoregressive for motor imagery classification,” Expert Systems with Applications, Jan. 2025, Art. no. 126433. doi: 10.1016/j.eswa.2025.126433

[5] B. B. Etana et al., “Discrete wavelet transform based processing of embroidered textile-electrode electromyography signal acquired with load and pressure effect,” Journal of Industrial Textiles, vol. 54, Jan. 2024. doi: 10.1177/15280837241232449

[6] C. Ouyang, L. Cai, B. Liu, and T. Zhang, “An improved wavelet threshold denoising approach for surface electromyography signal,” EURASIP Journal on Advances in Signal Processing, vol. 2023, no. 1, Oct. 2023. doi: 10.1186/s13634-023-01066-3

[7] A. Azzouz et al., “An efficient ECG signals denoising technique based on the combination of particle swarm optimisation and wavelet transform,” Heliyon, Feb. 2024, Art. no. e26171. doi: 10.1016/j.heliyon.2024.e26171

[8] L. Devnath, “Selection of wavelet and thresholding rule for denoising the ECG signals,” ResearchGate, 2015. doi: 10.13140/RG.2.1.1137.6243

[9] A. S. Ahmed, K. S. Rijab, and S. A. Alagha, “A study of chosen an optimum type of wavelet filter for de-noising an ECG signal,” International Journal of Current Engineering and Technology, vol. 10, no. 05, pp. 749–756, Oct. 2020. doi: 10.14741/ijcet/v.10.5.9

[10] T. Frikha et al., “Source localization of EEG brainwaves activities via mother wavelets families for SWT decomposition,” Journal of Healthcare Engineering, vol. 2021, pp. 1–11, Apr. 2021, Art. ID 9938646. doi: 10.1155/2021/9938646

[11] K. Lopez, “HAPPILEE: HAPPE in low electrode electroencephalography, a standardized pre-processing software for lower density recordings,” NeuroImage, vol. 260, 2022, Art. no. 119390. doi: 10.1016/j.neuroimage.2022.119390

[12] S. Yadav, S. K. Saha, R. Kar, and D. Mandal, “Optimized adaptive noise canceller for denoising cardiovascular signal using SOS algorithm,” Biomedical Signal Processing and Control, vol. 69, Art. no. 102830, Aug. 2021. doi: 10.1016/j.bspc.2021.102830

[13] R. Merletti and D. Farina, Surface Electromyography: Physiology, Engineering, and Applications. Hoboken, NJ, USA: Wiley–IEEE Press, 2016. doi: 10.1002/9781119082934

[14] R. H. Chowdhury, M. B. I. Reaz, M. A. B. M. Ali, A. A. A. Bakar, K. Chellappan, and T. G. Chang, “Surface electromyography signal processing and classification techniques,” Sensors, vol. 13, no. 9, pp. 12431–12466, 2013. doi: 10.3390/s130912431

[15] S. Ozaydin and I. Ahmad, “Comparative performance analysis of filtering methods for removing baseline wander noise from an ECG signal,” Fluctuation and Noise Letters, vol. 23, no. 4, Art. no. 2350046, 2024. doi: 10.1142/S0219477524500469

[16] Á. Fehér, "Denoising ECG signals by applying discrete wavelet transform," 2017 International Conference on Optimization of Electrical and Electronic Equipment (OPTIM) & 2017 Intl Aegean Conference on Electrical Machines and Power Electronics (ACEMP), Brasov, Romania, 2017, pp. 863-868, doi: 10.1109/OPTIM.2017.7975078.

[17] L. Dezhi, M. Yujian, Z. Xintong and G. Xiaozhong, "Research on Feature Extraction and Classification of EEG Signals Based on Multitask Motor Imagination," 2020 International Conference on Robots & Intelligent System (ICRIS), Sanya, China, 2020, pp. 112-115, doi: 10.1109/ICRIS52159.2020.00036.

[18] P. B. Patil and M. S. Chavan, "A wavelet based method for denoising of biomedical signal," International Conference on Pattern Recognition, Informatics and Medical Engineering (PRIME-2012), Salem, India, 2012, pp. 278-283, doi: 10.1109/ICPRIME.2012.6208358.



## 9. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |


