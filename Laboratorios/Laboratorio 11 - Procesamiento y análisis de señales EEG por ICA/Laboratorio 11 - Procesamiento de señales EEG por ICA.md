# 🧠📈 LABORATORIO 11: Procesamiento y análisis de señales ECG por ICA

## 🧾 Índice

- [1. Introducción](#1-introducción)
- [2. Objetivos](#2-objetivos)
  - [2.1 Objetivo general](#21-objetivo-general)
  - [2.2 Objetivos específicos](#22-objetivos-específicos)
- [3. Metodología](#3-descripción-de-materiales)
- [4. Resultados](#4-metodología)
- [5. Discusión ](#5-discusión)
- [6. Conclusiones](#6-conclusiones)
- [7. Referencias](#7-referencias)
- [Aporte de los integrantes](#aporte-de-los-integrantes)


## 📖 1. Introducción
En el análisis de señales electroencefalográficas (EEG), la extracción fiable de actividad neuronal útil depende de una secuencia de preprocesamientos: filtrado de ruido, evaluación del potencia espectral en bandas estándar (Delta, Theta, Alpha, Beta, Gamma) y análisis de los componentes temporoespaciales subyacentes [1-2]. En este marco, la técnica del análisis de componentes independientes (ICA) surge como un método clave para separar las fuentes mezcladas que contribuyen a los canales del EEG registrados en el cuero cabelludo [1-2]. ICA tiene como premisa que las señales observadas son combinaciones lineales de fuentes estadísticamente independientes, y por tanto busca estimar una matriz de desmezcla que revele dichas fuentes latentes [1-2].

Su relevancia en el análisis del EEG radica en dos dimensiones complementarias: 
* Facilita la eliminación de artefactos (como parpadeos, movimientos oculares, actividad muscular) que corrompen la estimación de la potencia en bandas o la localización de fuentes neurales; por ejemplo, estudios recientes muestran que ICA mejora la calidad de los componentes extraídos en entornos móviles y con artefactos de movimiento [3-4].
* Al obtener dichas fuentes “independientes”, permite avanzar hacia un análisis de conectividad o de carácter fuente (en lugar de canal), abriendo la puerta a interpretaciones fisiológicas más finas [3-4].

A la hora de calcular la potencia de las bandas (Delta, Theta, Alpha, Beta, Gamma) y graficar su distribución, el empleo de ICA puede proveer una señal más limpia y segmentada, reduciendo la contaminación cruzada entre bandas y proporcionando una mejor base para interpretar los patrones de potencia por banda en cada paciente [3-4].


## 🎯 2. Objetivos
---

### 2.1 Objetivo general
Procesar señales EEG registradas con un sistema Neurocortex de 8 canales, que permita la eliminación eficaz de artefactos mediante Análisis de Componentes Independientes (ICA). 

### 2.2 Objetivos específicos
- Implementar una etapa de preprocesamiento estructurada que incluya filtrado, normalización y re-referenciación de los canales EEG, optimizando la calidad de la señal para la posterior aplicación del ICA.

- Aplicar el análisis de componentes independientes para identificar y remover artefactos fisiológicos y de movimiento.

## 🛠️ 3. Metodología

Se cargó el archivo proveniente del Neurocortex, y el programa leyó los ocho canales registrados. Con esos datos se creó un arreglo en MNE usando la frecuencia de muestreo del equipo. Luego, se asignó el montaje estándar y se mapearon los electrodos a sus posiciones más cercanas, permitiendo análisis y visualización topográfica. Los canales se definieron como tipo EEG, marcando como misc aquellos auxiliares no cerebrales.

Durante el preprocesamiento, se aplicó una re-referenciación, adecuada para registros de ocho canales. Posteriormente, se realizó un filtrado para eliminar derivas lentas y para conservar la actividad cortical relevante, incluyendo un filtro notch a 60 Hz para suprimir interferencias eléctricas. Las señales se normalizaron mediante z-score por canal con el fin de facilitar comparaciones y análisis posteriores.

Se inspeccionó la señal para detectar canales saturados o con alta varianza. Asimismo, se incluyó en la inspección la identificación de componentes asociados a parpadeos, actividad muscular y movimientos. Dicho conjunto de componentes se eliminó durante la aplicación del ICA, por lo que se obtiene una señal limpia. 


## 🔍 4. Resultados 

| **Etapa del procesamiento** | **Descripción** | **Figura** |
|-----------------------------|----------------------------------|-------------------|
| **Canal 0** | Muestra una distribución negativa en la región frontal y positiva en la zona occipital, con una señal periódica y estable. El espectro revela picos claros en 50 Hz y 100 Hz, con baja varianza y sin pérdida de segmentos | ![C0](figuras/C0.png) |
| **Canal 1** | Evidencia un patrón negativo en las áreas posteriores y positivo en el vértex. La señal presenta deflexiones lentas de baja amplitud y un espectro similar al anterior, con picos eléctricos definidos | ![C1](figuras/C1.png) |
| **Canal 2** | Destaca por una fuerte positividad frontal y central, acompañada de oscilaciones regulares y de baja amplitud. El espectro mantiene picos en 50 Hz y 100 Hz con mínima dispersión de varianza | ![C2](figuras/C2.png) |
| **Canal 3** | Presenta predominio positivo en regiones frontales y temporales, con zonas negativas occipitales. La actividad temporal es suave y de baja frecuencia, mostrando la misma estructura espectral repetitiva y baja varianza | ![C3](figuras/C3.png) |
| **Canal 4** | Mantiene una topografía positiva en las zonas anteriores y laterales, con negatividad leve posterior. La señal es estable, de amplitud reducida, y el espectro vuelve a concentrarse en las bandas de 50 Hz y 100 Hz, sin segmentos descartados | ![C4](figuras/C4.png) |
| **Canal 5** | Muestra polaridad invertida respecto a los anteriores, con áreas negativas en la parte inferior derecha y positivas en el frente. Se observa un pequeño evento transitorio alrededor del tiempo cero y un comportamiento general estable | ![C5](figuras/C5.png) |
| **Canal 6** | Exhibe negatividad en regiones occipitotemporales derechas y positividad central. La señal presenta deflexiones leves y consistentes, con el mismo perfil espectral y varianza baja | ![C6](figuras/C6.png) |
| **Canal 7** | Posee un patrón simétrico con alternancia de zonas positivas y negativas, de amplitud muy reducida. El espectro está dominado nuevamente por los picos en 50 Hz y su armónico, y la varianza permanece estable sin valores extremos | ![C7](figuras/C7.png) |

## 💬 5. Discusión



## 📝 6. Conclusiones

- 
- 
- 

## 📚 7. Referencias
[1] A. Tharwat, “Independent component analysis: An introduction”, Appl. Comput. Inform., ahead-of-print, ahead-of-print, agosto de 2020. Accedido el 5 de noviembre de 2025. [En línea]. DOI: https://doi.org/10.1016/j.aci.2018.08.006

[2] “Independent Component Analysis with Functional Neuroscience Data Analysis”, J. Biomed. Phys. Eng., vol. 13, n.º 2, abril de 2023. Accedido el 5 de noviembre de 2025. [En línea]. DOI: https://doi.org/10.31661/jbpe.v0i0.2111-1436 

[3] I. Atti, P. Belardinelli, R. J. Ilmoniemi y J. Metsomaa, “Measuring the accuracy of ICA-based artifact removal from TMS-evoked potentials”, Brain Stimul., vol. 17, n.º 1, pp. 10–18, enero de 2024. Accedido el 5 de noviembre de 2025. [En línea]. DOI: https://doi.org/10.1016/j.brs.2023.12.001

[4] C. B. Gonsisko, D. P. Ferris y R. J. Downey, “iCanClean Improves Independent Component Analysis of Mobile Brain Imaging with EEG”, Sensors, vol. 23, n.º 2, p. 928, enero de 2023. Accedido el 5 de noviembre de 2025. [En línea]. DOI: https://doi.org/10.3390/s23020928

## 👥 Aporte de los integrantes
| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |
