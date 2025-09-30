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

En el ámbito del procesamiento de señales biomédicas, como las derivadas del electromiograma (EMG) y el electrocardiograma (ECG), resulta esencial limpiar las señales de artefactos y ruido para garantizar una interpretación fiable de los componentes fisiológicos verdaderos. Las señales reales captadas en el entorno clínico o experimental frecuentemente están contaminadas por interferencias como ruido de la línea eléctrica (50/60 Hz), deriva de la línea base (baseline wander), movimientos del sujeto o del electrodo, y contaminación cruzada entre señales fisiológicas (por ejemplo, que el ECG afecte al EMG) [1].

Para tratar estas perturbaciones se utilizan filtros digitales, entre los cuales los más comunes son los Filtros de Respuesta al Impulso Finito (FIR) y Filtros de Respuesta al Impulso Infinito (IIR). La elección entre ambos implica un compromiso entre varios parámetros: precisión en la respuesta en frecuencia, fase linealidad, complejidad computacional, estabilidad y distorsión de fase [2].

Los filtros FIR tienen la ventaja de ser inherentemente estables (no contienen retroalimentación interna) y pueden diseñarse con una fase lineal exacta, lo cual preserva la morfología de las señales (ondas P, QRS, T en ECG, o envolventes en EMG) [3]. Su desventaja es que requieren mayor longitud (más coeficientes) para lograr transiciones de banda nítidas, lo cual implica más cómputo y retardo [4].

Por su parte, los filtros IIR pueden lograr una respuesta de filtro más abrupta con menor orden (menos coeficientes), lo cual los hace más eficientes desde el punto de vista computacional y más adecuados para aplicaciones en tiempo real [5]. Sin embargo, al tener retroalimentación, pueden introducir distorsión de fase (no linealidad de fase) y potenciales problemas de estabilidad si no se diseñan cuidadosamente [5].

Cuando se trabaja con señales mixtas, por ejemplo, EMG contaminada por ECG, existen métodos dedicados para la separación de estas componentes superpuestas (gating, sustracción de plantilla, transformadas wavelet, filtrado adaptativo o separación de fuentes) [6]. En particular, en estudios comparativos de métodos de remoción de ECG de señales de EMG, se ha observado que los filtros de paso alto simples no logran eliminar completamente la interferencia sin afectar componentes de baja frecuencia del EMG, y otros métodos (por ejemplo, filtrado adaptativo o wavelets) pueden ofrecer un mejor equilibrio entre supresión de ruido y preservación de la señal deseada [6].

## 2. 🎯 Objetivos

### 2.1 Objetivo general

 - Conocer el manejo de Pyfda, tipos de fitros y aprender a diseñarlos e implementarlos para el procesamiento de señales biomédicas. 

### 2.2 Objetivos específicos
- Comparar el rendimiento de diferentes tipos de filtros en Pyfda, identificando las ventajas y desventajas de cada uno en el contexto de señales biomédicas.
- Investigar las funcionalidades de la biblioteca Pyfda para el diseño de filtros, enfocándose en su aplicación en el procesamiento de señales biomédicas.

## 3. 💻 Descripción de materiales

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
| Laptop |     Equipo con herramientas de software como Pyfda y Python para el filtrado de señales.   |  1  |

## 4. 📋 Metodología

1. Seleccionar las señales adquiridas en las últimas sesiones para trabajar.
2. Instalar el programa Pyfda en el entorno virtual de Anaconda.
3. Diseñar cuatro filtros por cada señal en Pyfda.
4. Exportar el filtro diseñado en formato .csv
5. En Python extraer los coeficiente al filtro para la creación de un sistema con una entrada y salida.
6. Graficar señal filtrada obtenida.
7. Realizar análisis de parámetros como SNR. 

## 5. 📊 Resultados 

### 5.1 Señales EMG

__5.1.1 Para la señal en reposo__

| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1.1 | Butterworth Notch | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/ButterworthNotch.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/ButterworthNotchPolos.png?raw=true) |
| 1.2 | Butterworth Pasabanda | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/ButterworthPasabanda.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/ButterworthPasabandaPolos.png?raw=true) |
| 2.1 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/Chebyshev1Notch.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/Chebyshev1NotchPolos.png?raw=true) |
| 2.2 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/Chebyshev1Pasabanda.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/Chebyshev1PasabandaPolos.png?raw=true) |
| 3.1 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/HammingNotch.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/HammingNotchPolos.png?raw=true) |
| 3.2 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/HammingPasabanda.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/HammingPasabandaPolos.png?raw=true) |
| 4.1 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/BlackmanNotch.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/BlackmanNotchPolos.png?raw=true) |
| 4.2 | ![diseño](ruta/a/imagen.png) | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/BlackmanPasabanda.png?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/pyfda%20EMG/BlackmanPasabandaPolos.png?raw=true) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ReposoBicepsCruda.png?raw=true) |
|Filtro anterior| ![Filtro anterior](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/PrefiltradoReposoBiceps.png?raw=true) |
|Filtro 1| ![Filtro 1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ReposoBicepsButterworth.png?raw=true) |
|Filtro 2| ![Filtro 2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ReposoBicepsChebyshev1.png?raw=true) |
|Filtro 3| ![Filtro 3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ReposoBicepsHamming.png?raw=true) |
|Filtro 4| ![Filtro 4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ReposoBicepsBlackman.png?raw=true) |

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
|Señal cruda| ![Señal Cruda](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/LentoBicepsCruda.png?raw=true) |
|Filtro anterior| ![Filtro anterior](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/PrefiltradoLentoBiceps.png?raw=true) |
|Filtro 1| ![Filtro 1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/LentoBicepsButterworth.png?raw=true) |
|Filtro 2| ![Filtro 2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/LentoBicepsChebyshev1.png?raw=true) |
|Filtro 3| ![Filtro 3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/LentoBicepsHamming.png?raw=true) |
|Filtro 4| ![Filtro 4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/LentoBicepsBlackman.png?raw=true) |

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
|Señal cruda| ![Señal Cruda](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ContraBicepsCruda.png?raw=true) |
|Filtro anterior| ![Filtro anterior](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/PrefiltradoContraBiceps.png?raw=true) |
|Filtro 1| ![Filtro 1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ContraBicepsButterworth.png?raw=true) |
|Filtro 2| ![Filtro 2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ContraBicepsChebyshev1.png?raw=true) |
|Filtro 3| ![Filtro 3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ContraBicepsHamming.png?raw=true) |
|Filtro 4| ![Filtro 4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20EMG/Se%C3%B1ales%20EMG/ContraBicepsBlackman.png?raw=true) |




### 5.2 Señales ECG

__5.2.1 Para la señal de primera derivada__ 
| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | Blackman | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F1_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F1_Zero.PNG?raw=true) |
| 2 | Butterworth | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F2_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F2_Zero.PNG?raw=true) |
| 3 | Chebyshev I | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F3_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F3_Zero.PNG?raw=true) |
| 4 | Hamming | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F4_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG1_F4_Zero.PNG?raw=true) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_crudo.PNG?raw=true) |
|Filtro anterior| ![Filtro anterior](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_FiltroAnt.PNG?raw=true) |
|Filtro 1| ![Filtro 1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_Filtro1.PNG?raw=true) |
|Filtro 2| ![Filtro 2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_Filtro2.PNG?raw=true) |
|Filtro 3| ![Filtro 3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_Filtro3.PNG?raw=true) |
|Filtro 4| ![Filtro 4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG1_Filtro4.PNG?raw=true) |

---
__5.2.2 Para la señal de respiración__ 
| N° filtro| Diseño |  H(f) | Diagrama de polos y ceros |
|:------:|:------:|:-----:|:-------------------------:|
| 1 | Equiripple | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F1_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F1_Zero.PNG?raw=true) |
| 2 | Bessel | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F2_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F2_Zero.PNG?raw=true) |
| 3 | Chebyshev II | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F3_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F3_Zero.PNG?raw=true) |
| 4 | Elliptic | ![H(f)](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F4_H(f).PNG?raw=true) | ![polos_ceros](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/pyfdaECG/ECG2_F4_Zero.PNG?raw=true) |


| Nombre | Gráfica |
|:------:|:------:|
|Señal cruda| ![Señal Cruda](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_crudo.PNG?raw=true) |
|Filtro anterior| ![Filtro anterior](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_FiltroAnt.PNG?raw=true) |
|Filtro 1| ![Filtro 1](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_Filtro1.PNG?raw=true) |
|Filtro 2| ![Filtro 2](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_Filtro2.PNG?raw=true) |
|Filtro 3| ![Filtro 3](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_Filtro3.PNG?raw=true) |
|Filtro 4| ![Filtro 4](https://github.com/RafaelPanez/GRUPO-01-ISB-2025-II/blob/main/Laboratorios/Laboratorio%206%20-%20Filtros%20FIR%20e%20IIR/Filtros%20ECG/Se%C3%B1ales%20ECG/ECG2_Filtro4.PNG?raw=true) |

## 6. 💭 Discusión y conclusiones

### 6.1 Acerca de los filtros para EMG

La señal electromiográfica (EMG) registra la actividad eléctrica de los músculos, pero durante su adquisición es vulnerable a la contaminación por distintas fuentes de ruido. Entre las más comunes están el generado por dispositivos electrónicos, la radiación electromagnética, los artefactos de movimiento, la interferencia de la red eléctrica, la inestabilidad en la descarga motora, la contaminación por electrocardiografía (ECG) y el crosstalk de músculos vecinos [7]. Estos factores enmascaran la señal y dificultan la interpretación de la actividad muscular, lo que reduce la precisión de los análisis y de los clasificadores de patrones.

Dentro de estas fuentes, los artefactos de movimiento son de los más relevantes, ya que aparecen en la interfaz piel–electrodo por desplazamiento de los sensores o cambios en la tensión de la piel. Estas perturbaciones generan oscilaciones de gran amplitud en frecuencias bajas, entre 1 y 20 Hz, que pueden igualar o superar la señal muscular [7], [8]. Para reducir este efecto, se fija un límite inferior de 20 Hz en el filtrado pasa-banda, lo que elimina el ruido de baja frecuencia y conserva la información útil, además de disminuir la inestabilidad asociada a la descarga de las unidades motoras [8].

En el extremo superior, se utiliza un límite de 450 Hz porque la mayor parte del contenido electromiográfico útil se encuentra por debajo de este valor. Por encima predominan el ruido electrónico, el térmico y la radiación electromagnética ambiental, todos los cuales reducen la relación señal–ruido [9]. De esta manera, el filtrado entre 20 y 450 Hz asegura que la señal procesada represente con fidelidad la actividad neuromuscular, sin la influencia de componentes de alta frecuencia que no aportan información fisiológica. Este criterio de filtrado se considera un estándar en la literatura por su efectividad en la adquisición de señales EMG comparables y confiables en estudios clínicos y experimentales [8], [9].

La interferencia de la red eléctrica es otra fuente crítica de ruido, que aparece como una oscilación sinusoidal en 50 o 60 Hz según la región geográfica. Su amplitud puede superar la de la señal muscular y enmascararla por completo, comprometiendo el análisis tanto temporal como espectral. Para eliminarla se emplean filtros notch, diseñados para atenuar específicamente esa frecuencia sin alterar de forma importante las bandas adyacentes de interés [8], [10].


__6.1.1 Para la señal en reposo__ 
---

La señal EMG en reposo del bíceps braquial se caracteriza por presentar únicamente actividad basal, reflejada en potenciales de unidad motora espontáneos de baja amplitud y ruido fisiológico de fondo. En esta condición, la señal útil es especialmente vulnerable a quedar enmascarada por interferencias externas, como el ruido de la red eléctrica (50/60 Hz) y artefactos de movimiento, lo que plantea un desafío en el filtrado digital [11].

El filtro Butterworth, con un orden de 11 en la banda de paso y 5 en la banda de rechazo, alcanzó un SNR de 29.53 dB. Su respuesta de magnitud plana en la banda de paso permitió preservar los potenciales espontáneos de baja amplitud característicos del reposo, minimizando la distorsión de amplitud. Aunque su fase no lineal podría inducir ligeras alteraciones temporales, en este contexto fisiológico dichas distorsiones son mínimas y no comprometen la detección de actividad basal [12].

El filtro Chebyshev Tipo I, configurado con un orden de 7 en la banda de paso y 4 en la banda de rechazo, logró el SNR más alto (33.93 dB). Este desempeño se debe a su mayor pendiente de atenuación, que permitió una supresión más eficiente del ruido de la red eléctrica. En reposo, donde las señales útiles son pequeñas y escasas, esta característica favorece la discriminación de potenciales fisiológicos frente a interferencias externas. Sin embargo, la no linealidad de fase introducida puede modificar levemente la sincronía temporal de descargas espontáneas, un aspecto relevante en estudios clínicos donde se evalúa la excitabilidad neuromuscular en reposo [13].

Por su parte, los filtros FIR con ventana Hamming y Blackman, de 195 coeficientes en la banda de paso y 1093 en la banda de rechazo, alcanzaron SNR de 24.81 dB y 25.26 dB respectivamente. Aunque su capacidad de supresión de ruido fue menor que la de los filtros IIR, su fase estrictamente lineal garantiza la preservación íntegra de la morfología temporal de la señal. Esta propiedad resulta crítica en reposo, ya que la interpretación clínica de descargas espontáneas o fibrilaciones depende de la forma de onda y no solo de la amplitud. Por tanto, a pesar de la menor atenuación de interferencias, los filtros FIR ofrecen una ventaja en estudios fisiológicos detallados de señales basales [14], [15].

__6.1.2 Para la señal en movimiento lento__ 
---
Durante la contracción muscular lenta, la señal EMG presenta un incremento progresivo de amplitud y mayor frecuencia de disparo de unidades motoras, con cierta superposición espectral que dificulta la discriminación de potenciales individuales. En este contexto, el filtrado digital debe equilibrar la supresión de ruido con la preservación de la dinámica temporal del reclutamiento muscular [11].

El filtro Butterworth, con un SNR de 24.50 dB, mantuvo su respuesta de magnitud plana en la banda de paso, lo que permitió preservar la amplitud creciente de las unidades motoras reclutadas de manera sostenida. No obstante, la fase no lineal introdujo distorsiones temporales que pueden afectar la identificación precisa de los momentos de disparo de cada unidad, un aspecto crítico para analizar la sincronización neuromuscular en contracciones lentas [12].
El filtro Chebyshev Tipo I alcanzó un SNR de 28.31 dB, mostrando mayor eficacia en la supresión de interferencias debido a su pendiente más pronunciada en la banda de rechazo. Esta característica favoreció la identificación de componentes de alta frecuencia generados por la coactivación de fibras rápidas, aunque las ondulaciones en la banda de paso alteraron levemente la amplitud de la señal. En un contexto de contracción lenta, esta distorsión puede sesgar la estimación de la contribución relativa de fibras musculares de diferentes tipos [13].

Los filtros FIR con ventana Hamming y Blackman, con SNR de 21.75 dB y 22.18 dB respectivamente, aseguraron una fase estrictamente lineal, lo que preservó con alta fidelidad la secuencia temporal de disparos. Esta propiedad resulta esencial en contracciones lentas, donde el interés principal radica en el análisis de la sincronía y el orden de reclutamiento. Sin embargo, la menor atenuación de ruidos residuales puede interferir en la detección de potenciales de baja amplitud correspondientes a unidades motoras de tipo lento [14], [15].

__6.1.3 Para la señal con fuerza en contra__ 
---
En la condición de contramovimiento, la señal EMG muestra un marcado incremento en amplitud y frecuencia de activación, producto del mayor reclutamiento de unidades motoras y de una mayor complejidad espectral asociada a la contracción contra resistencia. Esta condición demanda filtros capaces de preservar la potencia de las señales de alta amplitud y, al mismo tiempo, discriminar interferencias externas [11].
El filtro Butterworth, con un SNR de 23.37 dB, mantuvo una respuesta de magnitud plana en la banda de paso, lo que favoreció la conservación de los picos de gran amplitud generados por la contracción contra fuerza. Sin embargo, la fase no lineal introdujo distorsiones temporales que pueden dificultar la estimación precisa de la latencia entre el inicio de la contracción y la respuesta muscular, un aspecto importante en análisis biomecánicos [12].
El filtro Chebyshev Tipo I alcanzó un SNR de 27.29 dB, lo que refleja una mayor supresión de interferencias externas. Su pendiente más pronunciada en la banda de rechazo permitió aislar con mayor claridad los componentes útiles del EMG en condiciones de elevada actividad. No obstante, la distorsión de amplitud producida por las ondulaciones en la banda de paso puede alterar la representación relativa de la contribución de distintos grupos musculares, un factor relevante en contramovimientos de alta carga [13].

Los filtros FIR con ventana Hamming y Blackman, con SNR de 20.41 dB y 20.88 dB respectivamente, destacaron por su preservación de la fase lineal. Esto permitió mantener la secuencia temporal de la activación muscular incluso en presencia de contracciones complejas, lo que es crucial para estudiar patrones de coordinación intermuscular. Sin embargo, la menor capacidad de atenuación frente a ruidos de alta frecuencia limita su utilidad cuando el interés se centra en la depuración espectral más que en la forma temporal de la señal [14], [15].

En conjunto, los resultados muestran que el filtro Chebyshev Tipo I fue el que alcanzó los valores más altos de SNR en las tres condiciones evaluadas (33.93 dB en reposo, 28.31 dB en contracción lenta y 27.29 dB en contramovimiento), lo que evidencia su superioridad en la supresión de interferencias externas [9]. No obstante, en términos fisiológicos, la elección del mejor filtro depende de la naturaleza de la señal. En reposo, el Chebyshev se destaca por su capacidad de discriminar potenciales espontáneos de baja amplitud frente al ruido eléctrico; en contracción lenta, los filtros FIR resultan más apropiados cuando se requiere preservar con exactitud la secuencia temporal de reclutamiento; y en contramovimiento, el Butterworth asegura una adecuada conservación de los picos de gran amplitud. Así, considerando un equilibrio entre robustez en la atenuación de ruido y fidelidad en la morfología temporal, el filtro Chebyshev Tipo I puede considerarse el más eficiente en términos globales, mientras que los FIR constituyen la mejor opción cuando la prioridad es el análisis de la dinámica temporal fina [12], [15].

---
### 6.2 Acerca de los filtros para ECG

La señal proveniente de un electrocardiograma (ECG o EKG) indica información acerca de los movimientos del corazón y la intensidad de estos, siendo una de las herramientas más fiables para la detección de cardiopatías. Sin embargo, factores como  los artefactos de movimiento y la respiración generan  una componente de baja frecuencia que “desplaza” la línea de referencia de la señal. Puede oscilar lentamente, pero varía hasta 0.5 Hz o un poco más en casos de movimiento brusco [16]. Esa señal sin procesar a largo plazo nos puede hacer daño por medio de una mala interpretación de resultados, especialmente en segmentos como ST-T [17].

Entre las principales técnicas usadas para eliminar dicho componente es por medio de  un filtro pasa alta de bajo corte con fase lineal (FIR) para evitar distorsión de morfología [18]. Asimismo, se utilizan recursos como métodos de interpolación o ajuste a puntos del segmento isoeléctrico [17]. A partir de ello se generan diversos métodos combinados [19].

El ruido de alta frecuencia también es considerado como uno de los causantes de distorsión en la señal ECG. Este ocurre principalmente por ruido electrónico del mismo sistema, ruido de músculos cercanos o interferencia electromagnética. Afecta especialmente la onda QRS. Entre las principales herramientas se puede utilizar filtros pasabajos o wavelets para suavizar la señal [20].

Otro factor a considerar es la interferencia de red eléctrica, típicamente a 50 Hz o 60 Hz y sus armónicos. Esa interferencia puede superponerse con amplitud significativa a la señal ECG, y puede distorsionar los componentes clínicos si no se elimina correctamente. Luego, para poder eliminar dicha interferencia, es común el uso de filtros notch centrados en 50 Hz o 60 Hz para rechazar esa frecuencia estrecha. Es una de las técnicas más tradicionales. Asimismo, se utilizan sus variaciones que analizan amplitud y fase [20].


__6.1.1 Para la señal de primera derivada__ 
---

La señal de Primera Derivada se caracteriza por la presencia de componentes de baja frecuencia asociados a la línea isoeléctrica y ondas lentas (artefactos respiratorios o de movimiento), así como de interferencias externas como el ruido de la red eléctrica (50/60 Hz). Estas condiciones hacen que el diseño del filtrado digital sea crítico para preservar la morfología de las ondas P-QRS-T, evitando distorsiones en amplitud o fase que puedan afectar el diagnóstico clínico [21].

El Filtro FIR con ventana Blackman (pasaalta, orden 501) alcanzó un SNR de 26.73 dB. Su fase estrictamente lineal garantiza la preservación temporal de la morfología de las ondas del ECG, fundamental para la correcta interpretación de intervalos PR y QT. Sin embargo, su elevado orden implica mayor carga computacional, lo que puede ser una limitación en sistemas de monitoreo en tiempo real [22]. Los filtros FIR han sido ampliamente documentados por su capacidad para preservar la morfología y la fase de la señal, aunque su mayor orden resulta en un mayor costo computacional [23].

El Filtro IIR Butterworth pasabanda (orden 4) mostró un SNR de 21.31 dB. La respuesta de magnitud plana en la banda de paso permitió preservar las amplitudes de las ondas principales, con una atenuación adecuada de frecuencias no deseadas. Su baja complejidad lo hace atractivo para implementaciones embebidas, aunque la fase no lineal podría introducir pequeñas distorsiones temporales en la morfología del QRS [21]. El diseño de filtros IIR, como el Butterworth, es ideal cuando se busca una solución eficiente en términos computacionales, aunque las distorsiones de fase pueden ser un inconveniente [22].

Por su parte, el Filtro IIR Chebyshev Tipo I (orden 4) alcanzó un SNR de 19.88 dB, el menor entre los candidatos. Este desempeño se relaciona con el rizado en la banda de paso característico de esta aproximación, lo que puede introducir pequeñas variaciones en la amplitud de la señal ECG. No obstante, su mayor pendiente de atenuación asegura una mejor supresión de interferencias fuera de banda, siendo útil en entornos con alto nivel de ruido eléctrico [23].
Finalmente, el Filtro FIR con ventana Hamming (pasabanda, orden 301) obtuvo el mayor SNR de 27.03 dB. Aunque su orden es menor que el del FIR con ventana Blackman, logra un excelente compromiso entre eficiencia computacional y preservación de la morfología temporal. Su respuesta en fase estrictamente lineal lo convierte en la opción más confiable para estudios clínicos donde la precisión temporal (intervalos RR, ancho del QRS) es fundamental [24].
En conclusión, entre los filtros evaluados para ECG1, el FIR con ventana Hamming se presenta como la mejor alternativa, al ofrecer el mayor SNR y garantizar la conservación íntegra de la morfología de la señal, factor crítico para la interpretación clínica [10].

__6.2.2 Para la señal de respiración__ 
---
La señal de ECG2 (respiración) presenta un rango espectral más amplio, por lo que es fundamental aplicar filtros digitales que permitan eliminar artefactos de baja frecuencia (deriva de línea de base), interferencias de alta frecuencia y ruido de la red eléctrica, manteniendo la morfología de las ondas P-QRS-T. La adecuada selección del diseño de filtros asegura la preservación de la información clínica y mejora la relación señal-ruido (SNR) [25].
El Filtro Pasabanda Equiripple (orden 350) alcanzó un SNR de 12.04 dB. Su principal ventaja es la fase estrictamente lineal, que garantiza la preservación temporal de la morfología del ECG, aunque el costo computacional de su elevado orden puede ser una limitación en aplicaciones de monitoreo en tiempo real [25].

El Filtro Pasaalta Bessel (orden 4) obtuvo un SNR de 6.99 dB. Este tipo de filtro se caracteriza por su excelente respuesta en fase y mínima distorsión temporal, lo que favorece la correcta detección de intervalos PR y RR. Sin embargo, su baja atenuación en frecuencias cercanas a la banda de paso explica el bajo SNR alcanzado, limitando su capacidad de supresión de ruido de baja frecuencia [26].
El Filtro Pasaalta Chebyshev Tipo II (orden 5) logró un SNR de 7.08 dB. Aunque proporciona una atenuación más pronunciada fuera de la banda de paso, la presencia de rizado en la banda de rechazo puede introducir pequeñas variaciones en la estabilidad de la señal. Su desempeño en SNR es similar al Bessel, aunque con mayor capacidad de supresión de artefactos de baja frecuencia [27].

Finalmente, el Filtro Pasabaja Elíptico (orden 5) alcanzó un SNR negativo de –22.38 dB, lo que indica una degradación significativa de la calidad de la señal. A pesar de su alta selectividad y eficiencia en la atenuación de frecuencias superiores a 45 Hz, la distorsión introducida dentro de la banda útil compromete la morfología de las ondas ECG, haciéndolo inadecuado para aplicaciones clínicas [27].
En conclusión, entre los filtros evaluados para ECG2, el Equiripple pasabanda se presenta como la opción más adecuada, ya que ofrece un balance entre preservación de la morfología (fase lineal) y supresión de artefactos, a pesar de no alcanzar valores de SNR tan elevados como los vistos en ECG1 [25].


## 7. 📚 Referencias

[1] M. Boyer, L. Bouyer, J.-S. Roy y A. Campeau-Lecours, “Reducing Noise, Artifacts and Interference in Single-Channel EMG Signals: A Review,” Sensors, vol. 23, n.º 6, art. 2927, 2023, doi: 10.3390/s23062927.

[2] S. Sarpal, “Difference between IIR and FIR filters: a practical design guide,” Advanced Solutions Nederland (ASN). [En línea]. Disponible en: https://www.advsolned.com/difference-between-iir-and-fir-filters-a-practical-design-guide/

[3] C. Saxena, V. Upadhyaya, H. K. Gupta y A. Sharma, “Denoising of ECG Signals Using FIR & IIR Filter: A Performance Analysis,” en Proc. Int. Conf. on Emerging Trends in Expert Applications & Security (ICETEAS), Kalpa Publications in Engineering, vol. 2, pp. 51–58, 2018.

[4] S. Rani, A. Kaur y J. S. Ubhi, “Comparative study of FIR and IIR filters for the removal of Baseline noises from ECG signal,” International Journal of Computer Science and Information Technologies (IJCSIT), vol. 2, n.º 3, pp. 1105–1108, 2011.

[5] V. V. Reddy, M. Neelaveni, M. Sandeep, Sk. K. Ahmad y P. V. Krishna, “Comparison of FIR and IIR Filters Using ECG Signal with Different Sampling Frequencies,” International Research Journal of Modernization in Engineering, Technology and Science (IRJMETS), vol. 5, n.º 4, abril 2023, doi: 10.56726/IRJMETS35977.

[6] L. Xu, E. Peri, R. Vullings, C. Rabotti, J. P. Van Dijk y M. Mischi, “Comparative Review of the Algorithms for Removal of Electrocardiographic Interference from Trunk Electromyography,” Sensors, vol. 20, n.º 17, art. 4890, 2020, doi: 10.3390/s20174890.

[7] S. P. K. P. K. Zor, "A Review of ECG Signal Processing Methods," MDPI Sensors, vol. 16, no. 8, p. 1304, 2016. Disponible en:https://www.mdpi.com/1424-8220/16/8/1304.

[8] R. A. ., "Sensor-Based Systems for Real-Time Monitoring," MDPI Sensors, vol. 25, no. 13, p. 4004, 2025. Disponible en:https://www.mdpi.com/1424-8220/25/13/4004.

[9] T. K., "Signal Processing in Biomedical Applications," Journal of Electromyography and Kinesiology, vol. 54, p. 102440, 2020. Disponible en: : https://doi.org/10.1016/j.jelekin.2020.102440 

[10]  A. C. R. A. P. M. Z., "Rejection of Power Line Interference in EMG Signals Using a Notch Filter Initialized with Non-Zero States," Polish Academy of Sciences, 2025. Disponible en: https://www.par.pl/en/Yearbooks/2025/3-2025/Rejection-of-Power-Line-Interference-in-EMG-Signals-Using-a-Notch-Filter-Initialized-with-Non-Zero-States

[11] K. R. V. Shankar et al., "Design and Evaluation of ECG Signal Denoising Method Based on the Wavelet Transform," PMC, 2019. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC6412999/

[12] A. J. I. T. S. A. M. V. P. M. M., "A Comparative Study of Signal Processing Methods for ECG Denoising and Arrhythmia Detection," PMC, 2021. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC9599646/ 

[13] A. S. R. D. P. K., "Chebyshev Filter and Butterworth Filters: Comparison and Applications in Different Cases," ResearchGate, 2023. Disponible en: https://www.researchgate.net/publication/378435601_Chebyshev_filter_and_Butterworth_filters_Comparison_and_applications_in_different_cases 

[14] R. R. G. N. F. M. S. M. S., "ECG Signal Filtering Based on Digital Filter Design: An Overview," MDPI Sensors, vol. 24, no. 18, p. 5954, 2024. Disponible en: https://www.mdpi.com/1424-8220/24/18/5954  

[15] R. S. A. S. A. T. P., "Review and Analysis on Digital Filter Design in Digital Signal Processing," ResearchGate, 2023. Disponible en: https://www.researchgate.net/publication/388562991_Review_and_analysis_on_digital_filter_design_in_digital_signal_processing 

[16] "Baseline Wander," ScienceDirect. Disponible en: https://www.sciencedirect.com/topics/computer-science/baseline-wander.

[17] J. Kumar, N. S. V. R. Chandra, y S. R. R. R. P. Kumar, "ECG Signal Denoising: A Review of Methods," PMC, 2017. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC5361052/.

[18] K. C. J. Thomas, J. R. C. Saldanha, y A. J. R. Pinto, "Review on Filters for ECG Signal Denoising," PMC, 2019. Disponible en: https://pmc.ncbi.nlm.nih.gov/articles/PMC7494370/.

[19] R. P. Sharma, S. R. K. Yadav, y N. K. Singh, "A Hybrid Filtering Technique for ECG Signal Denoising," Biological Signal Processing and Control, vol. 64, pp. 102466, 2021. Disponible en: https://doi.org/10.1016/j.bspc.2021.102466.

[20] P. D. O’Brien, D. C. Carter, y D. J. Phillips, "A Novel Filter Design for ECG Signal Processing," Heliyon, vol. 10, no. 1, e26171, 2024. Disponible en: https://doi.org/10.1016/j.heliyon.2024.e26171.

[21] D. Gond, O. Dua, S. Raj, y S. Saxena, “A Statistical Comparison of FIR Kaiser Window and IIR Butterworth Filters in ECG Signal Pre‑Processing,” JETIR, vol. 11, no. 4, Apr. 2024.https://www.researchgate.net/publication/382219166_A_STATISTICAL_COMPARISON_OF_FIR_KAISER_WINDOW_AND_IIR_BUTTERWORTH_FILTERS_IN_ECG_SIGNAL_PRE-PROCESSING 

[22] H. Amhia, “Stability and Phase Response Analysis of Optimum IIR and FIR Filters,” Wiley, 2022. https://doi.org/10.1155/2022/9899899 

[23] K. – (o autor del estudio), “Comparison of FIR and IIR Filters for Audio Signal Noise Reduction,” 2023. 10.3390/s20051468 

[24] X. An et al., “Comparison of Motion Artefact Reduction Methods and the Use of Hamming Window in ECG Filtering,” PMC, 2020. https://www.researchgate.net/publication/372754570_Comparison_of_FIR_and_IIR_Filters_for_Audio_Signal_Noise_Reduction 

[25] S. M. Walke, S. S. Patil, y M. S. A. Khan, "A Comprehensive Approach to ECG Signal Enhancement Using Various Filtering Techniques," Nanotechnology Perceptions, vol. 20, no. S10, pp. 371–375, 2024.

[26] "Butterworth Filter," ScienceDirect, https://www.sciencedirect.com/topics/engineering/butterworth-filter 

[27] M. S. Chavan, R. A. Agarwala, y M. D. Uplane, "Comparative Study of Chebyshev I and Chebyshev II Filter Used for Noise Reduction in ECG Signal," International Journal of Circuits, Systems and Signal Processing, vol. 2, no. 1, pp. 1–17, 2008.

## 8. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |



















