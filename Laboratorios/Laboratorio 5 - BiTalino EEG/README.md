# LABORATORIO 5:  Uso de BiTalino para adquisición y análisis de señales EEG
---

## 1. Introducción

El electroencefalograma (EEG) es una técnica no invasiva que permite registrar la actividad eléctrica del cerebro mediante electrodos colocados en el cuero cabelludo [1]. Esta herramienta resulta fundamental en neurociencia y medicina clínica, ya que posibilita la evaluación de funciones cerebrales y el diagnóstico de distintos trastornos neurológicos [1]. Asimismo, el EEG facilita la monitorización continua de la actividad cerebral en pacientes críticos y la evaluación de la eficacia de tratamientos neurológicos, constituyéndose como un instrumento indispensable en investigación y entornos clínicos [2].

La generación de las señales EEG se produce principalmente en las neuronas piramidales de la corteza cerebral, ubicadas en las capas III y V [3-4]. Estas neuronas presentan una orientación perpendicular a la superficie cortical, lo que permite la formación de dipolos eléctricos detectables en el cuero cabelludo. La actividad registrada corresponde a la suma de los potenciales postsinápticos excitatorios e inhibitorios de grandes grupos de neuronas activadas de manera sincronizada [3]. Las oscilaciones resultantes se organizan en ritmos de alfa (8–13 Hz), beta (13–30 Hz), theta (4–8 Hz) y delta (0.5–4 Hz), cada uno asociado a distintos estados de conciencia y funciones cognitivas [3].

En cuanto a sus aplicaciones, el EEG constituye una herramienta esencial para el diagnóstico de epilepsia y la localización precisa de focos epilépticos, así como para estudios de sueño orientados a identificar trastornos como la narcolepsia [5]. De igual manera, la integración del EEG con técnicas de aprendizaje automático ha permitido el desarrollo de interfaces cerebro-computadora (BCI), lo que posibilita la comunicación y el control de dispositivos por parte de personas con discapacidades motoras [6].

**Figura 1.** Generación de señales EEG a partir de dipolos eléctricos formados por neuronas piramidales alineadas [4].

---
## 2. Objetivos

### 2.1 Objetivo general
—
Comprender el proceso de adquisición y procesamiento de señales de electroencefalograma (EEG) mediante su aplicación en el análisis de la actividad cerebral bajo diferentes condiciones experimentales.

### 2.2 Objetivos específicos
---

## 🛠️ 3. Instrumentos

|             Ítem              |                  Descripción                    |              Cantidad            |
|----------------------------|------------------------------------------------|:----------------------------------:|
|  BiTalino (r)evolution   |     Módulo de adquisición de señales biomédicas, incluye entradas para señales ECG, EMG, EEG y EDA.     |   1  |
| Cable para 3 electrodos |  Conector tripolar para la conexión de electrodos y el módulo de adquisición.     | 1 |
| Batería recargable LIPO 3.7V - 500mA |     Fuente de energía portátil para el  módulo BiTalino (r)evolution.         | 1 |
| Electrodos de superficie |  Sensores descartables para el registro de señales biomédicas.  |  3  |
| Laptop |     Equipo utilizado para la obtención de señales con el software OpenSignals (r)evolution  y procesamiento con Python.    |  1  |
| Ultracortex Mark IV (dry-electrode headset) |     Caso EEG abierto y modular diseñado para registrar actividad cerebral en aplicaciones de neurociencia, BCI y neurotecnología DIY    |  1  |

| ![imagen1](Imagenes/Figura2.1.PNG) | ![imagen2](Imagenes/fig3.png) | ![imagen3](Imagenes/casco.png) |
|:---------:|:---------:|:---------:|
| **(a)** | **(b)** | **(c)** |

**Figura 2**. Materiales utilizados para la realización del experimento. De izquierda a derecha: (a) BiTalino (r)evolution con batería (b) Laptop para adquisición de señales (c) Ultracortex Mark IV

## 📝 4. Marco teórico
---
### 4.1 Marco teórico
#### 4.1.1 Generación de la señal EEG
La EEG de superficie mide diferencias de potencial producidas por corrientes postsinápticas de poblaciones de **neuronas piramidales** orientadas de forma coherente en corteza. La señal registrada es resultado de **sumación espacial y temporal** atenuada por conducción de volumen (hueso, LCR, piel). Implica baja relación señal/ruido y alta sensibilidad a artefactos, de ahí la necesidad de **preprocesamiento explícito** y reportable.

#### 4.1.2 Bandas y reactividad alfa (EO vs EC)
Los ritmos clásicos incluyen δ (0.5–4 Hz), θ (4–7 Hz), **α (8–12 Hz)**, β (13–30 Hz) y γ (>30 Hz). En **reposo con ojos cerrados**, la **potencia alfa** aumenta de manera robusta, particularmente en regiones posteriores; al **abrir los ojos** o aumentar la carga atencional, esa potencia se **suprime**. Esta “reactividad alfa” se interpreta como un **mecanismo de gating sensorial** con modulación tálamo-cortical.

> _Inserta aquí un esquema de bandas EEG y la condición EO/EC._  
> `<!-- Figura A: Bandas EEG y reactividad alfa (EO vs EC) -->`

#### 4.1.3 Sistema 10–20, Fp1/Fp2 y artefactos oculares
El sistema **10–20** estandariza posiciones y facilita reproducibilidad. **Fp1** (frontal polar izquierdo) y **Fp2** (frontal polar derecho) están **muy próximos a los ojos**, por lo que captan con alta amplitud **parpadeos y movimientos oculares** (artefactos EOG). En frontal, los parpadeos pueden superar los **200 μV**, afectando potencias por canal y pudiendo generar **asimetrías aparentes** entre Fp1/Fp2 si difieren el patrón de parpadeo, la impedancia o la referencia. Por ello, es clave **marcar/gestionar** estos artefactos y documentar impedancias y referencia empleada.

> _Inserta aquí un mapa 10–20 resaltando Fp1/Fp2 y canales de referencia._  
> `<!-- Figura B: Mapa 10–20 (Fp1/Fp2) y referencia -->`

#### 4.1.4 Electrodos: húmedos vs secos
- **Húmedos (Ag/AgCl + gel)**: estándar clínico por **baja impedancia** y estabilidad; requieren preparación de piel y limpieza posregistro.  
- **Secos (multi-pin, gel-free)**: despliegue **rápido** y reutilizable (útiles con cascos tipo Ultracortex); hoy muestran **desempeño comparable** en ciertas tareas si el diseño es adecuado, aunque pueden ser más sensibles a movimiento y contacto en registros pasivos.

#### 4.1.5 Muestreo, referencia y filtrado
- **Muestreo**: elegir ≥**250–500 Hz** para cubrir con margen las bandas de interés y evitar aliasing; reportar siempre la **tasa**.  
- **Referencia**: promedio común, mastoides o A1/A2; documentar la elección porque altera amplitudes relativas por canal.  
- **Filtrado** (reportar tipo/orden/bandas):  
  - **Pasabanda** típico **0.5–40/80 Hz** para conservar bandas fisiológicas y suprimir offset/deriva.  
  - **Notch** a **50/60 Hz** para atenuar red eléctrica.  
  - Evitar **cortes altos agresivos** (p. ej., HPF >1 Hz en ERPs) sin justificar, porque **distorsionan amplitudes/latencias**.

> _Inserta aquí un diagrama simple del pipeline: bruto → filtrado → segmentación → PSD (Welch)._  
> `<!-- Figura C: Pipeline de preprocesamiento y análisis -->`

#### 4.1.6 Estimación espectral y métricas
Para cuantificar cambios EO/EC se recomienda la **PSD por Welch** (ventanado Hanning, 50% de solape) y calcular **potencia absoluta/relativa** por banda. En este protocolo, la métrica primaria es **potencia alfa (8–12 Hz)** en **EO vs EC** por canal (Fp1, Fp2). Métricas secundarias: conteo de parpadeos y potencia β durante tareas cognitivas.

> _Inserta aquí las figuras de PSD (EO vs EC) y barras de potencia alfa._  
> `<!-- Figura D: PSD por canal y condición -->`  
> `<!-- Figura E: Potencia alfa (EO vs EC) → efecto esperado: ↑α en EC -->`

---
### 4.2 Procedimiento experimental
#### Preparación del sujeto y del equipo
1. Explicar el procedimiento, retirar accesorios metálicos frontales y **limpiar piel** en sitios de registro.  
2. Verificar **batería/conexión** del sistema y crear el proyecto de adquisición (frecuencia de muestreo ≥**250–500 Hz**; mayor si analizarás >40 Hz) [10].

> **Inserta aquí** una foto del **montaje general** (casco/cintas y módulo de adquisición).  
> `<!-- Figura 1: Montaje de adquisición EEG -->`

#### Colocación de electrodos (10–20)
3. Ubicar **Fp1** y **Fp2** según 10–20. Colocar referencia (p. ej., mastoides o A1/A2) y tierra según tu hardware. Asegurar buen contacto y **baja impedancia** [6].

> **Inserta aquí** un **esquema 10–20** resaltando Fp1/Fp2.  
> `<!-- Figura 2: Mapa 10–20 con Fp1/Fp2 -->`

#### Protocolo de adquisición
4. **Reposo ojos abiertos (EO):** 2–3 min mirando un punto fijo, respiración normal.  
5. **Reposo ojos cerrados (EC):** 2–3 min, relajado, evitar movimientos.  
6. (Opcional) **Tarea cognitiva breve** (p. ej., restas seriadas) para observar cambios espectrales.  
7. **Marcado de eventos**: anotar cambios EO/EC, parpadeos voluntarios y eventos notables [1].

#### Preprocesamiento
8. **Revisión visual** y marcado de segmentos con artefactos obvios (movimientos, EMG facial). Los parpadeos impactan especialmente **Fp1/Fp2** [7].  
9. **Filtrado**: aplicar **pasabanda** ~**0.5–40 Hz** (o 0.5–80 Hz si requieres gamma baja) y **notch** a **50** (o **60**) Hz según tu red eléctrica. Reportar: tipo (FIR/IIR), orden y transitorio [3], [4], [5].  
10. (Opcional) **Re-referencia** (promedio común o referencia vinculada) si tu montaje lo permite [3].

#### Análisis cuantitativo
11. **Segmentación**: extraer **épocas** estables (p. ej., 4–8 s) en EO y EC, libres de artefacto [3].  
12. **PSD (Welch)** por canal (Fp1, Fp2): ventana 2–4 s, solape 50%, Hanning. Estimar **potencia en bandas**: delta (0.5–4), theta (4–7), **alfa (8–12)**, beta (13–30). Espera **↑alfa en EC** frente a EO [1], [2].  
13. **Comparaciones**:  
   - **EO vs EC**: diferencia o razón de potencia alfa por canal.  
   - **Fp1 vs Fp2**: comparar potencia en bandas; interpretar asimetrías considerando artefactos oculares y diferencias de contacto [7].

> **Inserta aquí** los **gráficos de PSD** (EO y EC) y, si quieres, **barras** de potencia alfa por condición y canal.  
> `<!-- Figura 3: PSD Fp1/Fp2 EO vs EC -->`  
> `<!-- Figura 4: Potencia alfa por condición (box/bar) -->`

## 6. Referencias
—
https://jamanetwork.com/journals/jamaneurology/article-abstract/581666 
https://pubmed.ncbi.nlm.nih.gov/19715175/
https://pubmed.ncbi.nlm.nih.gov/10576479/ 
https://publications.idiap.ch/downloads/reports/2007/uldry-idiap-com-07-04.pdf 
https://www.neurotherapeuticsjournal.org/article/S1878-7479(23)01188-1/fulltext 
https://pubmed.ncbi.nlm.nih.gov/39346532/ 

