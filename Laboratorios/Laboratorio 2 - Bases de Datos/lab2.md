# ⚽Etapa 1: Comprensión del negocio (Business Understanding)

## ❓1.1 Pregunta central del proyecto
La pregunta que guía este trabajo es:

**¿Podemos detectar tempranamente la fatiga muscular en futbolistas jóvenes mediante el análisis de señales EMG de músculos inferiores?**

Este planteamiento transforma el objetivo general en un problema claro de clasificación de estados musculares a partir de bioseñales. No se trata únicamente de “analizar EMG”, sino de **reconocer patrones en las señales que permitan distinguir entre reposo, pre-fatiga y fatiga**.

## 📊1.2 Contexto y relevancia
En el fútbol juvenil, las lesiones musculares constituyen un problema recurrente y de gran impacto. Se ha reportado que el 27,13% de todas las lesiones en divisiones formativas son de tipo muscular, siendo las contracturas las más comunes (66,54%) [1]. Dentro de estas, las sobrecargas de isquiotibiales y cuadríceps representan alrededor del 12% de todas las lesiones, y ocurren con mayor frecuencia hacia el final de partidos o entrenamientos, cuando la fatiga está presente [2].

El riesgo no es solo inmediato: forzar un músculo fatigado aumenta la probabilidad de desgarros y distensiones que obligan al jugador a detener entrenamientos, y la reincidencia de lesiones es alta si no se otorga un tiempo de recuperación adecuado [3]. En consecuencia, cada lesión no prevenida implica días de incapacidad, costos médicos adicionales y, en el caso de jóvenes futbolistas, retrasos en su formación deportiva y académica [6].

## 🌍1.3 Motivación e impacto
En el contexto peruano, las medidas preventivas recomendadas en guías internacionales (acondicionamiento progresivo, periodos de recuperación adecuados, equipamiento protector) no siempre se implementan de manera efectiva en categorías juveniles. Esto refuerza la necesidad de contar con **sistemas accesibles de monitoreo y predetección de fatiga**, capaces de integrarse a la práctica deportiva y contribuir a reducir la incidencia de lesiones.

Un sistema de este tipo no solo llenaría un vacío de conocimiento, sino que también fundamentaría mejoras en políticas deportivas y estrategias de prevención, generando un impacto positivo tanto en la salud de los atletas como en su rendimiento y proyección.

## 💾1.4 Rol de las bases de datos de referencia
Aunque en etapas posteriores se planea adquirir señales EMG propias, resulta necesario iniciar con **bases de datos públicas de referencia** (e.g., UCI, PhysioNet). Estas contienen registros de músculos clave en el fútbol, como bíceps femoris, vastus medialis, rectus femoris, semitendinosus, gastrocnemius lateralis y tibialis anterior. 

Trabajar con estas bases en la etapa inicial permite:
- Validar los algoritmos de procesamiento (filtros digitales, eliminación de ruido).  
- Identificar patrones consistentes de fatiga ya documentados en la literatura.  
- Asegurar que las metodologías sean confiables antes de aplicarlas en datos propios.

De este modo, la fase de **Comprensión del negocio** establece con claridad el **qué** (detectar fatiga muscular en futbolistas jóvenes), el **por qué** (alta incidencia de lesiones musculares y limitaciones en prevención en el Perú) y el **cómo inicial** (usar bases de datos de referencia para validar algoritmos de procesamiento y clasificación).


# 🧩Etapa 2: Comprensión de los datos (Data Understanding)
## 📑2.1 Estructura general de las bases de datos

En las siguientes tablas se detallan las características generales de cada base, como número de sujetos, estructura y condiciones de adquisición de las señales.

| **Base de datos**                                                                                         | **Número de sujetos** | **Población objetivo**                              | **Número de señales registradas** | **Duración total de los registros**     | **Tipo de registro**          |
|------------------------------------------------------------------------------------------------------------|------------------------|------------------------------------------------------|------------------------------------|-----------------------------------------|-------------------------------|
| EMG dataset in Lower Limb - from UC Irvine                                                                 | 22                     | 11 adultos sanos y 11 con anormalidades en la rodilla | 132                                | ~15 segundos                             | sEMG bipolar convencional     |
| Individual differences in the neural strategies to control the lateral and medial head of the quadriceps…  | 22                     | Adultos sanos entre 20 y 30 años                     | 1792                               | 60 segundos por contracción              | HD-sEMG                       |
| Surface electromyographic signals collected during long-lasting ground walking of young able-bodied subjects | 31                     | Adultos jóvenes entre 20 y 30 años                   | 31                                 | 60 segundos                             | sEMG multicanal               |

| **Base de datos**                                                                                         | **Tareas / movimientos realizados**                                                        | **Formato de archivo** | **Frecuencia de muestreo** | **Resolución de adquisición** | **Repeticiones por sujeto**          |
|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|-------------------------|-----------------------------|--------------------------------|--------------------------------------|
| EMG dataset in Lower Limb - from UC Irvine                                                                 | Marcha, extensión de la pierna desde posición sentada y flexión de la pierna hacia arriba   | .log y .txt             | 1000 Hz                     | 14 bits                        | 3–5                                  |
| Individual differences in the neural strategies to control the lateral and medial head of the quadriceps…  | Extensiones isométricas de rodilla al 25% del torque máximo                                | .mat                    | 2048 Hz                     | 12 bits                        | 2 (para 6 sujetos, el resto solo 1) |
| Surface electromyographic signals collected during long-lasting ground walking of young able-bodied subjects | Caminata                                                                                   | .dat y .hea             | 2000 Hz                     | 12 bits                        | 1                                    |
## 🔎2.2 Relevancia para el proyecto

### 🦵2.2.1 EMG dataset in Lower Limb - from UC Irvine

El dataset posee señales de músculos relevantes para el fútbol, tales como bíceps femoral, vasto medial, recto femoral y semitendinoso. Asimismo, estas han sido tomadas con acciones relacionadas al deporte, con actividades como sentado, parado y marcha. No obstante, la base de datos no incluye condiciones específicas de fatiga. Se puede utilizar como referencia inicial, la identificación de patrones musculares básicos y la validación preliminar de algoritmos. 

### 🧠2.2.2  Individual differences in the neural strategies to control the lateral and medial head of the quadriceps during a mechanically constrained task

El dataset se centra en el estudio de contracciones isométricas con distintas formas de activación muscular, lo cual se puede asociar a la fatiga muscular y lo hace relevante para el proyecto. Dado que analiza el cuádriceps, está relacionado estrechamente con el rendimiento de los futbolistas. Sin embargo, la muestra de la base de datos es reducida. Su uso permite validar métodos de análisis de señales y explorar patrones de control neuromuscular.

 
### 🏃‍♂️2.2.3 Surface electromyographic signals collected during long-lasting ground walking of young able-bodied subjects

El dataset presenta músculos como el vasto medio y vasto lateral, los cuales son importantes para la disciplina deportiva estudiada. Adicionalmente, se trabajó la obtención de las señales con distintos niveles de esfuerzo, lo que permite estudiar variaciones asociadas al inicio de fatiga. La cantidad de sujetos que participaron hace que la muestra alcance a ser considerable. La diversidad de las señales la convierten en una referencia adaptable al objetivo de análisis de fatiga muscular en deporte.
