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
### 2.2 Objetivos específicos

## 3. 💻 Descripción de materiales

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
| Laptop |    texto   |  1  |

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
| Reposo | ![Cruda_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGCrudo.png?raw=true) | ![Filtro_1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGWavelet.png?raw=true) | MSE: / SNR: |
| Lento | ![Cruda_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/LentoEMGCrudo.png?raw=true) | ![Filtro_2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/LentoEMGWavelet.png?raw=true) | MSE: / SNR: |
| Contracción | ![Cruda_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ContraEMGCrudo.png?raw=true) | ![Filtro_3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ContraEMGWavelet.png?raw=true) | MSE: / SNR: |

__Adicional: Gráficos de frecuencia__

| Nombre  | Gráfico de frecuencias | Espectrograma | 
|:---------:|:------------:|:------------:|
| Reposo | ![f_1](ruta/a/imagen.png) | ![E_1](ruta/a/imagen.png) |
| Lento | ![f_2](ruta/a/imagen.png) | ![E_2](ruta/a/imagen.png) | 
| Contra | ![f_3](ruta/a/imagen.png) | ![E_3](ruta/a/imagen.png) |


### 5.2 Señales ECG
---

| Nombre  | Señal Cruda  | Señal Filtrada | Párametros obtenidos |
|:---------:|:------------:|:------------:|:------------:|
| Reposo | ![Cruda_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGCrudo.png?raw=true) | ![Filtro_1C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ReposoECGWavelet.png?raw=true) | MSE: / SNR: |
| Respirar | ![Cruda_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RespirarECGCrudo.png?raw=true) | ![Filtro_2C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RespirarECGWavelet.png?raw=true) | MSE: / SNR: |
| Primera Derivada | ![Cruda_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/PrimeraDerivadaECGCrudo.png?raw=true) | ![Filtro_3C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/PrimeraDerivadaECGWavelet.png?raw=true) | MSE: / SNR: |
| Segunda Derivada | ![Cruda_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/SegundaDerivadaECGCrudo.png?raw=true) | ![Filtro_4C](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/SegundaDerivadaECGWavelet.png?raw=true) | MSE: / SNR: |

__Adicional: Gráficos de frecuencia__

| Nombre  | Gráfico de frecuencias | Espectrograma | 
|:---------:|:------------:|:------------:|
| Señal 1 | ![f_1C](ruta/a/imagen.png) | ![E_1C](ruta/a/imagen.png) |
| Señal 2 | ![f_2C](ruta/a/imagen.png) | ![E_2C](ruta/a/imagen.png) | 
| Señal 3 | ![f_3C](ruta/a/imagen.png) | ![E_3C](ruta/a/imagen.png) |
| Señal 4 | ![f_4C](ruta/a/imagen.png) | ![E_4C](ruta/a/imagen.png) |


### 5.3 Señales EEG
---

| Nombre  | Señal Cruda  | Señal Filtrada | Párametros obtenidos |
|:---------:|:------------:|:------------:|:------------:|
| Parpadeo | ![Cruda_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ParpadeoEEGCrudo.png?raw=true) | ![Filtro_1E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/ParpadeoEEGWavelet.png?raw=true) | MSE: / SNR: |
| Musica | ![Cruda_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/MusicaEEGCrudo.png?raw=true) | ![Filtro_2E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/MusicaEEGWavelet.png?raw=true) | MSE: / SNR: |
| Resta | ![Cruda_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RestaEEGCrudo.png?raw=true) | ![Filtro_3E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/RestaEEGWavelet.png?raw=true) | MSE: / SNR: |
| Copilado | ![Cruda_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/Copilado1EEGCrudo.png?raw=true) | ![Filtro_4E](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%207%20-%20Transformada%20Wavelet/Imagenes/Copilado1EEGWavelet.png?raw=true) | MSE: / SNR: |

__Adicional: Gráficos de frecuencia__

| Nombre  | Gráfico de frecuencias | Espectrograma | 
|:---------:|:------------:|:------------:|
| Señal 1 | ![f_E1](ruta/a/imagen.png) | ![E_1E](ruta/a/imagen.png) |
| Señal 2 | ![f_2E](ruta/a/imagen.png) | ![E_2E](ruta/a/imagen.png) | 
| Señal 3 | ![f_3E](ruta/a/imagen.png) | ![E_3E](ruta/a/imagen.png) |
| Señal 4 | ![f_4E](ruta/a/imagen.png) | ![E_4E](ruta/a/imagen.png) |

## 6. 💭 Discusión

### 6.1 Señales EMG
---
|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_1](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre)  |
|:--------------------------------------------------:|
| ![C_2](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_3](ruta/a/imagen.png) |

texto

### 6.2 Señales ECG
---
|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_1C](ruta/a/imagen.png) |

texto
|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_2C](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_3C](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_4C](ruta/a/imagen.png) |

texto

### 6.3 Señales EEG
---
|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_1E](ruta/a/imagen.png) |

texto
|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_2E](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_3E](ruta/a/imagen.png) |

texto

|Comparación de señal cruda y filtrada - Señal (nombre) |
|:--------------------------------------------------:|
| ![C_4E](ruta/a/imagen.png) |

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


