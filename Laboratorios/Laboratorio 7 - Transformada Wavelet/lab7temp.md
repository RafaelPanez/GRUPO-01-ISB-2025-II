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

### 6.1 Señales EMG
---
|Comparación de señal cruda y filtrada - Reposo |
|:--------------------------------------------------:|
| ![C_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Reposo_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Lento |
|:--------------------------------------------------:|
| ![C_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Lento_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Contracción |
|:--------------------------------------------------:|
| ![C_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EMG/Contra_comparacion.png?raw=true) |

texto

### 6.2 Señales ECG
---
|Comparación de señal cruda y filtrada - Reposo |
|:--------------------------------------------------:|
| ![C_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Reposo_comparacion.png?raw=true) |

texto
|Comparación de señal cruda y filtrada - Respirar |
|:--------------------------------------------------:|
| ![C_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/Respirar_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Primera Derivada |
|:--------------------------------------------------:|
| ![C_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/PrimeraDeri_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Segunda Derivada |
|:--------------------------------------------------:|
| ![C_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ECG/SegundaDeri_comparacion.png?raw=true) |

texto

### 6.3 Señales EEG
---
|Comparación de señal cruda y filtrada - Parpadeo |
|:--------------------------------------------------:|
| ![C_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Parpadeo_comparacion.png?raw=true) |

texto
|Comparación de señal cruda y filtrada - Musica |
|:--------------------------------------------------:|
| ![C_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Musica_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Resta |
|:--------------------------------------------------:|
| ![C_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Resta_comparacion.png?raw=true) |

texto

|Comparación de señal cruda y filtrada - Copilado |
|:--------------------------------------------------:|
| ![C_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/EEG/Copilado_comparacion.png?raw=true) |

texto

## 7. 📖 Conclusiones

## 8. 📚 Referencias

## 9. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |


