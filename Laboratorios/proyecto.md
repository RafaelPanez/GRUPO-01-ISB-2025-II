# 📊 Proyecto del Curso
## 📝Título tentativo del proyecto
Sistema de detección temprana de fatiga muscular en futbolistas jóvenes mediante el análisis de señales electromiográficas.
## ⚠️ Problemática a abordar
La falta de monitoreo de la fatiga deja a los jóvenes futbolistas expuestos a lesiones que podrían prevenirse al detectar a tiempo el cansancio excesivo.
## 📚 Justificación de la problemática  
La fatiga muscular no detectada a tiempo es un factor contribuyente en las frecuentes lesiones que sufren los jóvenes futbolistas. De hecho, las distensiones musculares constituyen una proporción importante de las lesiones totales en el fútbol juvenil; por ejemplo, en divisiones formativas se ha reportado que 27,13% de todas las lesiones son de tipo muscular, siendo las contracturas la forma más común con un 66.54% [1]. Gran parte de estas lesiones musculares ocurren en situaciones de fatiga: las sobrecargas de isquiotibiales (una de las lesiones musculares más típicas, que representa alrededor del 12% de todas las lesiones en futbolistas) y cuadríceps suelen producirse hacia el final de los partidos o entrenamientos [2].

Por un lado, forzar el músculo fatigado incrementa el riesgo de desgarros y distensiones que resultan en dolor, pérdida de movilidad y necesidad de interrupción del entrenamiento. Por otro lado, la reincidencia de lesiones musculares es alta si no se da un tiempo de recuperación adecuado, lo que puede iniciar un ciclo de lesión-crónica si el deportista vuelve a jugar sin haberse recuperado completamente [3].

Aunque existen directrices médicas y deportivas que respaldan la necesidad de mejorar la prevención de fatiga en futbolistas jóvenes (guías de medicina deportiva, calendarios con fechas preestablecidas, entre otros) mediante buenas prácticas como acondicionamiento físico progresivo, equipamiento protector, técnica correcta y respeto por los periodos de recuperación muscular [4]; estas normas preventivas muchas veces no se implementan plenamente en el deporte formativo en países como Perú. Asimismo, un análisis reciente sobre el fútbol profesional en Perú reportó que la incidencia de lesiones durante los partidos se mantuvo similar entre la temporada regular 2023 y la temporada desarrollada en pandemia (2020), la incidencia de lesiones incrementó (de 25.6 a 28,5) así como también el número total de lesiones registradas (de 228 a 313) [5].

En consecuencia, cada lesión no evitada representa días de incapacidad física, costos médicos y, en el caso de futbolistas jóvenes, posibles retrasos en su formación académica [6]. Por lo tanto, la falta de preparación física adecuada y las limitaciones en la recuperación aumentan significativamente la severidad e impacto de las lesiones musculares, reforzando así la necesidad de implementar sistemas de prevención de fatiga accesibles para el contexto deportivo peruano.
## 💡 Motivación
Reconocer cuándo los músculos inferiores están propensos a la fatiga muscular en futbolistas jóvenes del Perú llenará un vacío de conocimiento y permitirá fundamentar mejoras en las políticas deportivas del fútbol nacional. Asimismo, aunque existe un estudio previo que relaciona el síndrome de Burnout (estado de agotamiento físico, mental y emocional por estrés) con la frecuencia de lesiones deportivas en futbolistas jóvenes del Perú [7], lo cierto es que no se encontraron datos medibles  ni cuantificables que permitan obtener información vital sobre el estado y funcionalidad de los músculos inferiores involucrados en este deporte. Por ende, este proyecto resalta la necesidad de establecer protocolos de detección temprana de fatiga en futbolistas jóvenes del Perú.
## 🎯 Objetivos a alcanzar  
### 🎓 Objetivo general
Diseñar y validar un sistema basado en electromiografía (EMG) que permita detectar la aparición de fatiga en músculos inferiores de futbolistas jóvenes.
### 🧭Objetivos específicos
- Seleccionar los músculos (isquiotibiales, en particular bíceps femoris y semitendinosus, y de apoyo cuadríceps como vastus medialis y rectus femoris) para evaluar patrones de fatiga mediante EMG.

- Adquirir señales EMG  siguiendo un protocolo de ejercicios repetitivos (sprints cortos, contracciones isométricas, entre otros) para inducir estados de reposo, pre-fatiga y fatiga.

- Procesar y filtrar las señales EMG con técnicas digitales (filtros Butterworth y notch) para la eliminación de ruidos.

- Desarrollar un algoritmo de clasificación en MATLAB/Python para discriminar entre estados de reposo, pre-fatiga y fatiga.

- Comparar señales propias con bases de datos (bíceps femoris, vastus medialis, rectus femoris, semitendinosus, hamstrings) para validar la consistencia de los patrones de fatiga.
## 🛠️Herramientas a utilizar
### Hardware
- Sensor BITalino (sensor de EMG) con electrodos de superficie.

- Computadora con interfaz de adquisición de BITalino.
### Software
- MATLAB (Signal Processing Toolbox, Classification Learner).

- Entorno de programación Python.
## 🗄️ Base de Datos
| **Título** | **Resumen** |
|------------|-------------|
| EMG dataset in Lower Limb - from UC Irvine | Base de datos de biceps femoris, vastus medialis, rectus femoris y semitendinosus [8]. |
| Individual differences in the neural strategies to control the lateral and medial head of the quadriceps during a mechanically constrained task | Base de datos de vastus lateralis (VL) y vastus medialis (VM) [9]. |
| Surface electromyographic signals collected during long-lasting ground walking of young able-bodied subjects | Base de datos de gastrocnemius lateralis (GL), tibialis anterior (TA), rectus femoris (RF), hamstrings (Ham), y vastus lateralis [10]. |
## 🔎Estado del Arte
### Producto 
#### Papers
| **Imagen** | **Título** | **Resumen** |
|---------------------------|------------|-------------|
| 📄 | Sensitivity to change of quadriceps and hamstrings muscle wearable electromyography outcomes during a professional soccer match | El trabajo explora el uso de la EMG textil en partidos de fútbol profesional, enfocándose en cuádriceps e isquiotibiales. Se encontró que esta técnica permite detectar cambios entre el primer y segundo tiempo, mostrando su utilidad para monitorear la carga neuromuscular, optimizar el rendimiento y reducir el riesgo de lesiones [11]. |
| 📄 | Influence of Fatigue on the Rapid Hamstring/Quadriceps Force Capacity in Soccer Players | Este estudio, realizado en 17 futbolistas profesionales, evidenció que la fatiga disminuye la capacidad de generar fuerza rápida (RTD) y de activar los músculos en los primeros 100 ms de la contracción, destacando estos parámetros como más relevantes que las variaciones en los índices H/Q para comprender el riesgo de lesión [12]. |
| 📄 | Scheduling Concurrent Training 48 versus 72 h after Simulated Match Play: Effects on Neuromuscular Function and Fatigue | Este estudio analizó la función neuromuscular, la fatiga y las respuestas de dolor muscular al entrenamiento concurrente realizado 48 h (MD+2) y 72 h (MD+3) después de un partido en deportes de equipo de campo, considerando la influencia de la programación del microciclo competitivo [13]. |

#### Productos Comerciales
| Imagen | Título | Información |
|--------|--------|-------------|
| ![Myocene](https://www.myocene.com/us/wp-content/uploads/2021/09/myocene-device.jpg) | Myocene | El dispositivo permite evaluar la fatigabilidad muscular de los atletas en el campo, facilitando un mejor monitoreo de la fatiga para optimizar el rendimiento mediante entrenamientos adecuados y reducir el riesgo de sobreentrenamiento y lesiones [14]. |
| ![Trigno Lite System](https://delsys.com/wp-content/uploads/2021/06/Trigno-Lite-System-Overview.png) | Trigno Lite System | Sistema que combina sensores de grado de investigación con la facilidad de uso de una laptop o tableta, permitiendo obtener datos de EMG y movimiento de alta calidad con mínima configuración. Incluye herramientas de software avanzadas para la interpretación de las señales [15]. |
| ![Myontec MBody MShorts3 EMG](https://www.mindtecstore.com/media/image/product/139/lg/myontec-mbody-3-smart-shorts.jpg) | Myontec MBody MShorts3 EMG | Prenda deportiva inteligente que, junto con el monitor EMG MCell3, permite registrar datos de entrenamiento de los músculos del muslo, cuádriceps y glúteos. Incluye sensores de movimiento en la cadera (IMU) y análisis mediante aplicación móvil [16]. |
