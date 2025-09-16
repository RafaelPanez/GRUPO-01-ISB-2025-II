# ❤️📈 LABORATORIO 4:  Uso de BiTalino para adquisición y análisis de señales ECG
---

## 📑 Índice

- [1. Introducción](#1-introducción)
- [2. Objetivos](#2-objetivos)
  - [2.1 Objetivo general](#21-objetivo-general)
  - [2.2 Objetivos específicos](#22-objetivos-específicos)
- [3. Descripción de materiales](#3-descripción-de-materiales)
- [4. Metodología](#4-metodología)
  - [4.1 Tipos de onda de la señal ECG](#41-tipos-de-onda-de-la-señal-ecg)
  - [4.2 Derivaciones del ECG](#42-derivaciones-del-ecg)
  - [4.3 Ejercicio aeróbico y anaeróbico](#43-ejercicio-aeróbico-y-anaeróbico)
  - [4.4 Selección del sujeto](#44-selección-del-sujeto)
  - [4.5 Configuración de electrodos](#45-configuración-de-electrodos)
  - [4.6 Procedimiento experimental](#46-procedimiento-experimental)
- [5. Resultados](#5-resultados)
  - [5.1 Repositorio de vídeos](#51-repositorio-de-vídeos)
  - [5.2 Gráficas obtenidas](#52-gráficas-obtenidas)
- [6. Referencias](#6-referencias)
- [Aporte de los integrantes](#aporte-de-los-integrantes)


## 📖 1. Introducción
---
Un electrocardiograma representa la actividad eléctrica producida por las contracciones del corazón por medio de una gráfica de voltaje versus tiempo [1-2]. Este procedimiento es no invasivo para el paciente, al cual se le colocan electrodos de superficie para el registro [2]. La principal aplicación del electrocardiograma radica en el análisis de la señal eléctrica obtenida para el diagnóstico de cardiopatías y su severidad [1]. Hasta el día de hoy se le considera una herramienta confiable en medicina y es de vital importancia contar con un equipo de ECG en cualquier parte del globo [1]. 

El principio para que los electrodos logren sensar la señal eléctrica es que esta se establece como un vector electromagnético. Al ocurrir un evento de despolarización y la corriente generada se acerca al electrodo, se obtiene una onda positiva en el ECG. Si ocurre repolarización y la corriente se aleja del electrodo, entonces también se registra una onda positiva. Caso contrario a alguno de los dos escenarios se genera una onda negativa [1].

A partir del ECG surgieron diversas aplicaciones, tales como el fundamento para clasificadores de arritmias, su uso con IA para diagnóstico y estimación de parámetros fisiológicos como la frecuencia respiratoria. Asimismo, existen diversos métodos de aplicación, los cuales varían con la posición de los electrodos y las variaciones en el proceso de filtrado, segmentación y extracción de la señal [3].



![Procesamiento ECG](Imagenes_lab4/Figura1.PNG)
**Figura 1.** Flujo de procesamiento de un ECG o también denominado EKG [3].


## 🎯 2. Objetivos
---

### 2.1 Objetivo general
---
Comprender el proceso de adquisición y procesamiento de señales de electrocardiograma (ECG) por medio de su aplicación en un análisis fisiológico con diversos estados de actividad física.

### 2.2 Objetivos específicos
---
- Adquirir señales biomédicas de electrocardiograma (ECG) a partir de un sujeto sometido a diferentes condiciones físicas: Descanso, contención de aire y actividad aeróbica.
- Configurar correctamente el módulo BiTalino con el uso de los puertos adecuados y conexión estable.
- Analizar las señales obtenidas por medio de OpenSignals (r)evolution y técnicas de procesamiento en Python para producir conclusiones relacionadas con procesos fisiológicos.

## 🛠️ 3. Descripción de materiales
---

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
|  BiTalino (r)evolution   |     Módulo de adquisición de señales biomédicas, incluye entradas para señales ECG, EMG, EEG y EDA.     |   1  |
| Cable para 3 electrodos |  Conector tripolar para la conexión de electrodos y el módulo de adquisición.     | 1 |
| Batería recargable LIPO 3.7V - 500mA |     Fuente de energía portátil para el  módulo BiTalino (r)evolution.         | 1 |
| Electrodos de superficie |  Sensores descartables para el registro de señales biomédicas.  |  3  |
| Laptop |     Equipo utilizado para la obtención de señales con el software OpenSignals (r)evolution  y procesamiento con Python.    |  1  |

| ![imagen1](Imagenes_lab4/Figura2.1.PNG)|![imagen2](Imagenes_lab4/Figura2.2.PNG)| ![imagen2.5](Imagenes_lab4/Figura2.3.PNG) |
|:---------:|:-------------------:|:----------------------:
|**(a)** | **(b)**  | **(c)** |

**Figura 2**. Materiales utilizados para la realización del experimento. De izquierda a derecha: (a) BiTalino (r)evolution con batería (b) Laptop para adquisición de señales (c) Cable conectado a electrodos.

## 📝 4. Metodología
---

### 📈 4.1 Tipos de onda de la señal ECG
---

- **Onda P:**  Obtenido a partir de la despolarización de la aurícula. Normalmente el voltaje producido por la onda es mayor o igual a 0.3 mV. Su periodo de duración es menor o igual a 120 ms. Al observar la derivación II siempre se tiene un valor positivo y en aVR siempre es negativo [2].
- **Onda R:**  Obtenido a partir del descenso del estímulo eléctrico por los ventrículos durante la despolarización. Es la onda más alta del ECG [1].
- **Onda S:** Obtenido a partir de la despolarización final de las fibras de Purkinje. No siempre se encuentra presente en el ECG [1].
- **Onda T:** Se obtiene a partir de la repolarización del ventrículo. Normalmente muestra un valor positivo en todas las derivaciones [2].
- **Complejo QRS:** Se obtiene a partir de la despolarización del ventrículo. Normalmente su período es de 60 a 120 ms. Su altura varía de acuerdo a la derivación [2].
- **Intervalo PR:** Se obtiene el periodo de duración cuando empieza la onda P hasta que inicia QRS. Normalmente su período es de 120 a 200 ms. [2].
- **Segmento ST:**  Se obtiene el periodo de duración cuando termina el complejo QRS hasta que inicia la onda T. Normalmente este dura entre 80 a 120 ms [1-2].
- **Intervalo QT:** Obtenido por medio del proceso del el inicio de la despolarización hasta el final de la repolarización de los ventrículos. Normalmente dura entre 400 a 440 ms [1].

![imagen3](Imagenes_lab4/Figura3.PNG)
**Figura 3.**  Forma característica de señal ECG [2].

### ❤️ 4.2 Derivaciones del ECG
---

El ECG tiene una configuración convencional que posee series derivaciones periféricas y seis derivaciones precordiales, haciendo un total de 12 derivaciones. Se incluye en las derivaciones periféricas a las derivaciones clásicas (I, II, III) y aumentadas (aVL, aVR y aVF). Estas están codificadas por colores para evitar una colocación incorrecta, siendo rojo a  brazo derecho, amarillo a brazo izquierdo, verde a pierna izquierda y negro a pierna derecha. Las derivaciones precordiales V1 a V6 se colocan en la superficie del tórax [1,4].

Su colocación es la siguiente:
- V1: Derecha del borde esternal [1]. 
- V2: Izquierda del borde esternal [1].
- V4: A la altura del quinto espacio intercostal en la línea medio-clavicular. Este debe colocarse anterior a V3 [1].
- V3: Entre V2 y V4 [1].
- V5: Entre V4 y V6 [1].
- V6: A la altura del quinto espacio intercostal en la línea medio-axilar [1].

![imagen4](Imagenes_lab4/Figura4.PNG)

**Figura 4.**  Las 12 derivaciones del ECG y todos las ubicaciones posibles en el cuerpo [4]. 

### 🏃‍♂️ 4.3 Ejercicio aeróbico y anaeróbico
---

Entre los tipos de ejercicio se encuentran dos grupos principales: ejercicios anaeróbicos y aeróbicos [5].

Los ejercicios anaeróbicos se caracterizan por utilizar procesos anaeróbicos como principal proceso para el consumo de energía en el cuerpo. Por lo tanto, influye en el aumento de la masa muscular y posee otros beneficios como el aumento de la masa ósea y así reducir el riesgo de osteoporosis [5].

Los ejercicios aeróbicos se caracterizan por utilizar el sistema aeróbico como principal proceso para el consumo de energía en el cuerpo. Por lo tanto, ocurre un gran consumo de oxígeno y por consiguiente el aumento de la frecuencia respiratoria y cardiaca. Entre los principales beneficios de los también denominados ejercicios de resistencia y cardiovasculares, se encuentra la mejora de la capacidad cardiorrespiratoria, prevención de enfermedades cardíacas y otras enfermedades como demencia y depresión [5]. 

### 👤 4.4 Selección del sujeto
---
Se seleccionó un voluntario sin historial de cardiopatías y en buen estado de salud, con el fin de poder obtener una señal ECG de una persona sana.

### ⚡ 4.5 Configuración de electrodos
---
Para este experimento se utilizará la configuración ilustrada en la Figura 5, en la cual se utilizan ambas muñecas como polos positivo y negativo, así como la cresta Ilíaca como punto neutro. Esta configuración ha mostrado ser adecuada para la obtención de parámetros como la frecuencia respiratoria y tener una amplitud adecuada para poder utilizar la señal para realizar un análisis de ECG. Sin embargo, es importante tener en cuenta que el procesamiento debe hacerse con un algoritmo adecuado [6-7]. 

![imagen5](Imagenes_lab4/Figura5.PNG)

**Figura 5.** Configuración de electrodos utilizados en este experimento.

### 🔬 4.6 Procedimiento experimental
---
1. **Limpieza de la zona y configuración del BiTalino:** Se limpia las zonas de la piel en la que se colocarán los electrodos con agua y jabón. Asimismo, se enciende el módulo y se coloca el cable para tres electrodos en la sección ECG. Se realiza conexión Bluetooth entre el BiTalino y la laptop. 

2. **Colocación de electrodos:** Se colocan los electrodos en la posición indicada en la Figura 5. Después de ello se los conecta al cable para tres electrodos. 

3. **Registro de la señal ECG:**
    - *Condición de reposo:* El voluntario se sentará en una posición cómoda y grabará sus señales ECG por 30 segundos. Al mismo tiempo se documentará la adquisición en formato de vídeo. Esta condición se realizará dos veces. 
    - *Condición de contener aire:* Al mismo tiempo se documentará la adquisición en formato de vídeo. Esta condición se realizará tres veces.
    - *Condición de actividad aeróbica:* Al mismo tiempo se documentará la adquisición en formato de vídeo. Esta condición se realizará una vez.

![imagen6](Imagenes_lab4/Figura6.PNG)

**Figura 6.** Registro de señal ECG.

## 📊 5. Resultados
---

### 🎥 5.1 Repositorio de vídeos
---
En esta sección encontrará todas las tomas de video de las señales utilizadas para el análisis requerido.

| Condición                      | Video 1 | Video 2 | Video 3 |
|:--------------------------------:|:---------:|:---------:|:---------:|
| Reposo                         | [▶️](https://youtube.com/shorts/nUOCGJeS2Zc?si=evrYjOI470gJ2ewU)     | [▶️](https://youtu.be/gqKORtb81b0?si=D-PNKI1Pz7ilzPA1)       | -       |
| Contención de aire  | [▶️](https://youtube.com/shorts/vPV-2XEB-_A?si=0fpbO1un5JqbYS5J)       | [▶️](https://youtu.be/YlQjrmEgMOU)      | [▶️](https://youtu.be/-MvJ0mhq688)      |
| Ejercicio Aeróbico | [▶️](https://youtu.be/UdIvIOF4wus)      |   -     |   -      |

### 📉 5.2 Gráficas obtenidas
---

**5.2.1 Gráficas del sujeto en reposo**

**Figura 7.** Primera adquisición de señal en condición de reposo: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

**Figura 8.** Segunda adquisición de señal en condición de reposo: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

**5.2.2 Gráficas del sujeto al contener aire**

**Figura 9.** Primera adquisición de señal del sujeto al contener aire: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

**Figura 10.** Segunda adquisición de señal del sujeto al contener aire: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

**Figura 11.** Tercera adquisición de señal del sujeto al contener aire: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

**5.2.3 Gráficas de actividad física aeróbica**

**Figura 12.** Adquisición de señal del sujeto al realizar actividad física aeróbica: Panel izquierdo muestra la señal cruda; panel derecho la señal preprocesada.

### 5.3 Interpretación de los resultados
---

**5.3.1 Interpretación de gráficas del sujeto en reposo**

**5.3.2 Interpretación de gráficas del sujeto al contener aire**

**5.3.3 Interpretación de gráficas de actividad física aeróbica**

**5.3.4 Interpretación conjunta**

## 📚 6. Referencias
---

1. Y. Sattar y L. Chhabra. “Electrocardiogram”. National Library of Medicine (NIH). Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.ncbi.nlm.nih.gov/books/NBK549803/ 
2. P. Madona, R. I. Basti y M. M. Zain, “PQRST wave detection on ECG signals”, Gac. Sanit., vol. 35, pp. S364—S369, 2021. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.gaceta.2021.10.052 
3. E. Merdjanovska y A. Rashkovska, “Comprehensive survey of computational ECG analysis: Databases, methods and applications”, Expert Syst. with Appl., p. 117206, abril de 2022. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.eswa.2022.117206 
4. “Electrocardiograma de 12 derivaciones: derivaciones y ejes”. Elsevier Connect. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.elsevier.com/es-es/connect/electrocardiograma-de-12-derivaciones-derivaciones-y-ejes 
5. “La diferencia entre ejercicio aeróbico y anaeróbico”. The European Food Information Council : Food facts for healthy choices | Eufic. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.eufic.org/es/vida-sana/articulo/la-diferencia-entre-ejercicio-aerobico-y-anaerobico 
6. D. Lapsa, M. Metshein, A. Krivošei, R. Janeliukstis, O. Märtens y A. Elsts, “Signal Acquisition and Algorithm Design for Bioimpedance-Based Heart Rate Estimation from the Wrist”, Appl. Sci., vol. 14, n.º 21, p. 9632, octubre de 2024. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.3390/app14219632 

7. J. Diven, R. Adair, J. Rowny, A. Birmingham y D. Jardine, “Evaluating the feasibility of upper arm ECG for cardiac monitoring”, Eur. Heart J., vol. 45, Supplement_1, octubre de 2024. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1093/eurheartj/ehae666.3426 

## 👥 Aporte de los integrantes
---
| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |

| Rafael Panez    | 33.33%           |



