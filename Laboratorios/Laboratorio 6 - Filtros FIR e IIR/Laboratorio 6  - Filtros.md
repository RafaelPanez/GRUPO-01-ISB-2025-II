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


## 6. 💭 Discusión

### 6.1 Acerca de los filtros para EMG

__6.1.1 Para la señal en reposo__ 
---
__6.1.2 Para la señal en movimiento lento__ 
---
__6.1.3 Para la señal con fuerza en contra__ 

### 6.2 Acerca de los filtros para ECG

__6.1.1 Para la señal de primera derivada__ 
---
__6.2.2 Para la señal de respiración__ 

## 7. 📖 Conclusiones


## 8. 📚 Referencias

## 9. 👥 Aporte de los integrantes

<div align="center">

| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |


