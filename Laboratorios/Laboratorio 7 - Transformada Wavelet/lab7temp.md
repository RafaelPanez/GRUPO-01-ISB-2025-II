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

![Intro](ruta/a/imagen.png) 

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
### 4.2 Filtro para EMG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| 1 | 1 | 1 | 1 |

### 4.3 Filtro para ECG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| 1 | 1 | 1 | 1 |

### 4.4 Filtro para EEG

| Nombre | Nivel | Umbral | Frecuencia |
|:---------:|:------------:|:------------:|:------------:|
| 1 | 1 | 1 | 1 |

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

En todas las señales biopotenciales (EMG, ECG y EEG) el proceso de filtrado es crucial para eliminar ruido proveniente de interferencias eléctricas, artefactos de movimiento y componentes de alta o baja frecuencia no fisiológicos, por lo que la elección del filtro debe equilibrar la atenuación del ruido con la preservación de las características relevantes del biopotencial [1D]. En este caso, los resultados muestran una mejora clara en la relación señal/ruido (SNR) y una reducción del error cuadrático medio (MSE), evidenciando un filtrado efectivo y una reconstrucción fiel de la señal original.

### 6.1 Señales EMG
---
|Comparación de señal cruda y filtrada - Reposo |
|:--------------------------------------------------:|
| ![C_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_comparacion.png?raw=true) |

En la condición de reposo, la señal filtrada (en rojo) evidencia una clara reducción de los picos aleatorios y del ruido de fondo, manteniendo el nivel basal cercano a cero. Esto coincide con el incremento del SNR observado (3.40 dB) y un MSE de 0.0001, lo que sugiere una eliminación eficaz del ruido térmico y eléctrico de baja amplitud.
Además, los filtros wavelet logran este equilibrio al suprimir las componentes de alta frecuencia sin distorsionar la envolvente fisiológica [2D].

|Comparación de señal cruda y filtrada - Lento |
|:--------------------------------------------------:|
| ![C_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_comparacion.png?raw=true) |

En la fase lenta, la señal filtrada resalta las regiones activas de contracción, evidenciando una mayor claridad en los pulsos musculares y una mejor diferenciación temporal entre las fases de reposo y activación. El MSE bajo (0.0003) y el SNR de 14.32 dB respaldan esta mejora. 

|Comparación de señal cruda y filtrada - Contracción |
|:--------------------------------------------------:|
| ![C_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_comparacion.png?raw=true) |

Finalmente, durante la contracción rápida, el filtrado conserva la densidad espectral entre 50 y 150 Hz, característica de la actividad mioeléctrica voluntaria [3D].


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


Por lo tanto, un filtrado pasa banda entre 0.5–45 Hz, complementado con un filtro Notch, es el más adecuado para preservar los componentes fisiológicos del ECG y eliminar tanto artefactos de movimiento como interferencias electromagnéticas [4D].
El análisis temporal demuestra que las características principales se mantienen alineadas entre la señal original y la filtrada, confirmando que la reconstrucción fue precisa y clínicamente útil [5D].

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

Estos resultados coinciden con lo reportado por Subha et al. (2020) y Wang & Liu (2022), quienes demostraron que los métodos basados en wavelet thresholding permiten eliminar artefactos no estacionarios en EEG sin comprometer las bandas cerebrales de interés. Los coeficientes de detalle muestran cómo las variaciones abruptas, típicas de artefactos o interferencias eléctricas, fueron suavizadas, lo que mejora la legibilidad temporal de los eventos neuronales [6D], [7D].


## 7. 📖 Conclusiones

## 8. 📚 Referencias

[1D] S. Yadav, S. K. Saha, R. Kar, and D. Mandal, “Optimized adaptive noise canceller for denoising cardiovascular signal using SOS algorithm,” Biomedical Signal Processing and Control, vol. 69, Art. no. 102830, Aug. 2021. doi: 10.1016/j.bspc.2021.102830

[2D] R. Merletti and D. Farina, Surface Electromyography: Physiology, Engineering, and Applications. Hoboken, NJ, USA: Wiley–IEEE Press, 2016. doi: 10.1002/9781119082934

[3D] R. H. Chowdhury, M. B. I. Reaz, M. A. B. M. Ali, A. A. A. Bakar, K. Chellappan, and T. G. Chang, “Surface electromyography signal processing and classification techniques,” Sensors, vol. 13, no. 9, pp. 12431–12466, 2013. doi: 10.3390/s130912431

[4D] S. Ozaydin and I. Ahmad, “Comparative performance analysis of filtering methods for removing baseline wander noise from an ECG signal,” Fluctuation and Noise Letters, vol. 23, no. 4, Art. no. 2350046, 2024. doi: 10.1142/S0219477524500469

[5D] Á. Fehér, "Denoising ECG signals by applying discrete wavelet transform," 2017 International Conference on Optimization of Electrical and Electronic Equipment (OPTIM) & 2017 Intl Aegean Conference on Electrical Machines and Power Electronics (ACEMP), Brasov, Romania, 2017, pp. 863-868, doi: 10.1109/OPTIM.2017.7975078.

[6D] L. Dezhi, M. Yujian, Z. Xintong and G. Xiaozhong, "Research on Feature Extraction and Classification of EEG Signals Based on Multitask Motor Imagination," 2020 International Conference on Robots & Intelligent System (ICRIS), Sanya, China, 2020, pp. 112-115, doi: 10.1109/ICRIS52159.2020.00036.

[7D] P. B. Patil and M. S. Chavan, "A wavelet based method for denoising of biomedical signal," International Conference on Pattern Recognition, Informatics and Medical Engineering (PRIME-2012), Salem, India, 2012, pp. 278-283, doi: 10.1109/ICPRIME.2012.6208358.



## 9. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |


