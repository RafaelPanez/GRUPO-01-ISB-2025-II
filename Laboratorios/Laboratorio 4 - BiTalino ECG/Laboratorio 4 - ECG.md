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
  - [5.3 Interpretación de resultados](#53-interpretación-de-resultados)  
    - [5.3.1 Interpretación de gráficas del sujeto en reposo](#531-interpretación-de-gráficas-del-sujeto-en-reposo)  
    - [5.3.2 Interpretación de gráficas del sujeto al contener aire](#532-interpretación-de-gráficas-del-sujeto-al-contener-aire)  
    - [5.3.3 Interpretación de gráficas de actividad física aeróbica](#533-interpretación-de-gráficas-de-actividad-física-aeróbica)  
    - [5.3.4 Interpretación conjunta](#534-interpretación-conjunta)  
- [6. Conclusiones](#6-conclusiones)  
- [7. Referencias](#7-referencias)  
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

| ![imagen1](Imagenes_lab4/Figura2.1.PNG)|![imagen2](Imagenes_lab4/Figura2.2.PNG)|![imagen2.5](Imagenes_lab4/Figura2.3.PNG) |
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

| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/ReposoECG_ORIGINAL_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/ReposoECG_ORIGINAL_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/ReposoECG_ORIGINAL_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/ReposoECG_ORIGINAL_canal2_freq_filt.png) |

**Figura 7.** Adquisición de señales en condición de reposo: Panel izquierdo muestra las señales crudas; panel derecho las señales preprocesadas.

**5.2.2 Gráficas del sujeto al contener aire**
| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/RESPIRARECG1_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/RESPIRARECG1_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/RESPIRARECG1_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/RESPIRARECG1_canal2_freq_filt.png) |

**Figura 8.** Primera adquisición de señal del sujeto al contener aire: Panel izquierdo muestran las señales crudas; panel derecho las señales preprocesadas.

| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/RESPIRAECG2_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/RESPIRAECG2_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/RESPIRAECG2_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/RESPIRAECG2_canal2_freq_filt.png) |

**Figura 9.** Segunda adquisición de señal del sujeto al contener aire: Panel izquierdo muestran las señales crudas; panel derecho las señales preprocesadas.

| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/RESPIRAECG3_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/RESPIRAECG3_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/RESPIRAECG3_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/RESPIRAECG3_canal2_freq_filt.png) |

**Figura 10.** Tercera adquisición de señal del sujeto al contener aire: Panel izquierdo muestran las señales crudas; panel derecho las señales preprocesadas.

Cabe resaltar que se escogió un fragmento (20s-25s) para poder visualizar de mejor forma la señal. En todo caso, se adjuntan las gráficas procesadas en todo su dominio (tiempo).

| Señales filtradas en su totalidad |
|-----------------------|
| ![Reposo crudo](Imagenes_lab4/outputs/filtered/time/RESPIRARECG1_canal2_time_filt.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/filtered/time/RESPIRAECG2_canal2_time_filt.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/filtered/time/RESPIRAECG3_canal2_time_filt.png) |

**Figura 11.** Tres adquisiones procesadas de la señal cuando el sujeto contiene el aire.

**5.2.3 Gráficas de actividad física aeróbica**

| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/PrimeraDerivada_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/PrimeraDerivada_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/PrimeraDerivada_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/PrimeraDerivada_canal2_freq_filt.png) |

**Figura 12.** Adquisición de señal (primera derivada) del sujeto al realizar actividad física aeróbica: Panel izquierdo muestran las señales crudas; panel derecho las señales preprocesadas.

| Señal cruda | Señal filtrada |
|-------------|----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/raw/time/SegundaDerivada_canal2_time_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/time/SegundaDerivada_canal2_time_filt_crop.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/raw/freq/SegundaDerivada_canal2_freq_raw.png) | ![Reposo filtrado](Imagenes_lab4/outputs/filtered/freq/SegundaDerivada_canal2_freq_filt.png) |

**Figura 13.** Adquisición de señal (segunda derivada) del sujeto al realizar actividad física aeróbica: Panel izquierdo muestran las señales crudas; panel derecho las señales preprocesadas.

**5.2.4 Gráficas de pipeline**
| Señal con picos R | Datos obtenidos |
|-------------------|-----------------|
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/ReposoECG_ORIGINAL_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/ReposoECG_ORIGINAL_canal2_summary.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/RESPIRARECG1_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/RESPIRARECG1_canal2_summary.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/RESPIRAECG2_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/RESPIRAECG2_canal2_summary.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/RESPIRAECG3_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/RESPIRAECG3_canal2_summary.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/PrimeraDerivada_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/PrimeraDerivada_canal2_summary.png) |
| ![Reposo crudo](Imagenes_lab4/outputs/pipeline/SegundaDerivada_canal2_time_filt_crop_peaks.png) | ![Datos](Imagenes_lab4/outputs/pipeline/SegundaDerivada_canal2_summary.png) |

### 5.3 Interpretación de los resultados
---

**5.3.1 Interpretación de gráficas del sujeto en reposo**
En adultos sanos, la frecuencia cardíaca (FC) en reposo se sitúa típicamente entre 60 y 100 lpm, con predominio del tono vagal y una variabilidad de la frecuencia cardíaca (HRV) caracterizada por oscilaciones de origen parasimpático [8]. En los registros obtenidos, la FC media aparece notoriamente elevada y la HRV excesivamente amplia para un estado basal. Este comportamiento difícilmente representa una condición fisiológica real, ya que una HRV tan grande en reposo se asocia más a errores de detección que a modulaciones autonómicas auténticas. Desde la metodología, la causa más probable corresponde a dobles conteos de ondas R/T o artefactos de movimiento, fenómenos ampliamente descritos en la literatura de procesamiento de ECG y HRV [8]. Por ello, resulta esencial ajustar la detección mediante tres estrategias clásicas: (i) inclusión de un período refractario mínimo que evite falsos positivos, (ii) inversión de polaridad cuando los complejos R son negativos, y (iii) filtrado selectivo en la banda 5–15 Hz únicamente para la etapa de detección del QRS. Tras estas correcciones, la gráfica debería mostrar un ritmo sinusal estable, con HRV de amplitud moderada atribuible al control vagal, y un espectro de potencia en el dominio de la frecuencia dominado por bajas frecuencias, como corresponde a sujetos en reposo [8].

**5.3.2 Interpretación de gráficas del sujeto al contener aire**
Durante la apnea voluntaria, se activa el denominado reflejo de inmersión, que combina bradicardia, vasoconstricción periférica y redistribución del flujo sanguíneo hacia órganos vitales, mecanismos mediados por activación parasimpática y estimulación de quimiorreceptores en condiciones de hipoxia/hipercapnia [9]. La literatura también describe una breve taquicardia anticipatoria al inicio, así como otra de recuperación al término de la maniobra [10]. En contraste, las gráficas obtenidas muestran una FC elevada durante todo el segmento, sin evidencia de la caída progresiva típica. Este hallazgo sugiere dos posibilidades: primero, que existan errores de detección derivados de morfologías atípicas, ruido o sobredetección de picos, lo que distorsiona el registro; segundo, que el sujeto haya realizado maniobras preparatorias como hiperventilación o Valsalva, que inducen una taquicardia inicial prolongada y dificultan observar la bradicardia característica. En términos gráficos, se esperaría una curva descendente de FC y un aumento en la variabilidad de intervalos RR conforme avanza la apnea, patrón ampliamente documentado en estudios fisiológicos sobre apnea voluntaria [9], [10].

**5.3.3 Interpretación de gráficas de actividad física aeróbica**
Durante el ejercicio aeróbico, la respuesta fisiológica es más consistente con lo descrito en la literatura: incremento sostenido de la FC y reducción progresiva de HRV, reflejando la retirada vagal y el predominio simpático [11]. La magnitud de la reducción de HRV se relaciona directamente con la intensidad del esfuerzo y se mantiene mientras persista la carga. Estudios recientes sugieren que el análisis conjunto de FC y HRV permite identificar los umbrales ventilatorios, situando el primer umbral (VT1) alrededor de 140 lpm y el segundo (VT2) en torno a 165 lpm en adultos entrenados [12]. En las gráficas analizadas, la FC supera con frecuencia los 165 lpm y la HRV se encuentra prácticamente suprimida, lo que indica trabajo en intensidades cercanas o superiores al VT2. Este patrón concuerda con lo descrito en la literatura: tramos con FC muy elevada acompañados de intervalos RR más uniformes, lo que se traduce en trazados lineales y compactos en los gráficos de HRV [11], [12]. De este modo, los resultados refuerzan la utilidad de las gráficas para identificar no solo tendencias de esfuerzo, sino también umbrales fisiológicos relevantes.

**5.3.4 Interpretación conjunta**
* Reposo: las gráficas reflejan una sobrestimación de la FC y HRV, atribuible a errores de detección; corregido el procesamiento, se esperaría una FC normal (60–100 lpm) con modulación vagal evidente [8].
* Contención de aire: la literatura describe bradicardia/modulación autonómica durante la apnea; el patrón de taquicardia sostenida observado sugiere artefacto de detección o fase no puramente apneica en los segmentos analizados [9], [10].
* Ejercicio aeróbico: se confirma el comportamiento canónico ↑FC y ↓HRV con la intensidad, coherente con estudios recientes que cuantifican la disminución de HRV durante el esfuerzo y su relación con VT1/VT2 [11], [12].
## 📌 6. Conclusiones
---
Los resultados del laboratorio demostraron que la frecuencia cardíaca (FC) y la variabilidad de la frecuencia cardíaca (HRV) constituyen parámetros útiles para evaluar la modulación autonómica bajo diferentes condiciones fisiológicas. En reposo se espera un predominio vagal con HRV moderada [8], durante la apnea un patrón de bradicardia asociado al reflejo de inmersión [9], [10], y en el ejercicio aeróbico un incremento sostenido de FC junto con la reducción de HRV por predominio simpático [11], [12]. Sin embargo, los registros mostraron discrepancias atribuibles a errores de detección, lo cual evidencia la importancia de la calidad en la adquisición y el procesamiento de las señales.

El análisis permitió identificar que en las condiciones de reposo y apnea existieron limitaciones técnicas, principalmente sobredetección de complejos QRS y artefactos de movimiento, que llevaron a sobreestimaciones de FC y HRV. Dichos problemas metodológicos son ampliamente descritos en la literatura de procesamiento de señales [8] y subrayan la necesidad de utilizar algoritmos robustos con periodos refractarios, inversión de polaridad y filtrado selectivo para obtener resultados confiables en la práctica experimental.

En contraste, los registros durante el ejercicio aeróbico reflejaron con mayor fidelidad la fisiología esperada: aumento progresivo de la FC y disminución notable de la HRV. Este comportamiento coincide con estudios recientes que relacionan la dinámica de la HRV con los umbrales ventilatorios (VT1 ~140 lpm y VT2 ~165 lpm), validando el uso de estas métricas para cuantificar la intensidad del esfuerzo [11], [12]. Así, la experiencia confirmó que el ejercicio es la condición más consistente para validar experimentalmente los métodos de análisis aplicados.

En conjunto, la práctica permitió concluir que el análisis de señales cardíacas es una herramienta no invasiva con alto potencial para el estudio de la fisiología humana y sus adaptaciones al esfuerzo, pero su aplicabilidad depende de un procesamiento riguroso y de la reducción de errores técnicos. Por lo tanto, se resalta la necesidad de mejorar los algoritmos de detección de picos y de aplicar controles más estrictos en la adquisición de datos, a fin de incrementar la validez de las interpretaciones en estudios futuros de carácter biomédico y deportivo [8]–[12].

## 📚 7. Referencias
---

1. Y. Sattar y L. Chhabra. “Electrocardiogram”. National Library of Medicine (NIH). Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.ncbi.nlm.nih.gov/books/NBK549803/ 
2. P. Madona, R. I. Basti y M. M. Zain, “PQRST wave detection on ECG signals”, Gac. Sanit., vol. 35, pp. S364—S369, 2021. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.gaceta.2021.10.052 
3. E. Merdjanovska y A. Rashkovska, “Comprehensive survey of computational ECG analysis: Databases, methods and applications”, Expert Syst. with Appl., p. 117206, abril de 2022. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.eswa.2022.117206 
4. “Electrocardiograma de 12 derivaciones: derivaciones y ejes”. Elsevier Connect. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.elsevier.com/es-es/connect/electrocardiograma-de-12-derivaciones-derivaciones-y-ejes 
5. “La diferencia entre ejercicio aeróbico y anaeróbico”. The European Food Information Council : Food facts for healthy choices | Eufic. Accedido el 15 de septiembre de 2025. [En línea]. Disponible: https://www.eufic.org/es/vida-sana/articulo/la-diferencia-entre-ejercicio-aerobico-y-anaerobico 
6. D. Lapsa, M. Metshein, A. Krivošei, R. Janeliukstis, O. Märtens y A. Elsts, “Signal Acquisition and Algorithm Design for Bioimpedance-Based Heart Rate Estimation from the Wrist”, Appl. Sci., vol. 14, n.º 21, p. 9632, octubre de 2024. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.3390/app14219632 

7. J. Diven, R. Adair, J. Rowny, A. Birmingham y D. Jardine, “Evaluating the feasibility of upper arm ECG for cardiac monitoring”, Eur. Heart J., vol. 45, Supplement_1, octubre de 2024. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1093/eurheartj/ehae666.3426
8. Mayo Clinic Staff, “What’s a normal resting heart rate?” Mayo Clinic, 2022. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://www.mayoclinic.org/healthy-lifestyle/fitness/expert-answers/heart-rate/faq-20057979 
9. M. Marlinge et al., “Blood Adenosine Increase During Apnea in Spearfishermen Reinforces the Efficiency of the Cardiovascular Component of the Diving Reflex,” Frontiers in Physiology, vol. 12, 2021. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.3389/fphys.2021.743154
10. S. Laborde, M. Allen, and U. Borges, “Effects of Voluntary Slow Breathing on Heart Rate and Heart Rate Variability: A Systematic Review and Meta-analysis,” Neuroscience & Biobehavioral Reviews, vol. 138, 104711, 2022. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1016/j.neubiorev.2022.104711
11. D. Mongin, H. Hannink, P. Abry, and O. Barnabé, “Decrease of heart rate variability during exercise,” PLOS ONE, vol. 17, no. 9, e0273981, 2022. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.1371/journal.pone.0273981
12. B. Rogers, M. Schaffarczyk, and T. Gronwald, “Improved Estimation of Exercise Intensity Thresholds by Combining Dual Non-Invasive Biomarker Concepts: Correlation Properties of Heart Rate Variability and Respiratory Frequency,” Sensors, vol. 23, no. 4, 1973, 2023. Accedido el 16 de septiembre de 2025. [En línea]. Disponible: https://doi.org/10.3390/s23041973 

## 👥 Aporte de los integrantes
---
| Integrante      | Contribución (%) |
|-----------------|:------------------:|
| Salet Garcia    | 33.33%           |
| Dhiago Llanos   | 33.33%           |
| Rafael Panez    | 33.33%           |























