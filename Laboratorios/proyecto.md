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

