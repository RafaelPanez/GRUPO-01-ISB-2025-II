# Lab 2 — Informe sobre la base de datos "Surface EMG during long-lasting ground walking of young able-bodied subject", según la metodología del CRISP-DM (2 primeras etapas)

## 🧭 Resumen de la problemática
Este trabajo plantea detectar tempranamente la fatiga muscular en futbolistas jóvenes a partir de señales sEMG de miembros inferiores. La motivación surge de la alta incidencia de lesiones musculares en divisiones formativas (≈27.13% del total; predominan contracturas ≈66.54%), con especial relevancia al final de partidos/entrenamientos cuando la fatiga está presente. Para una fase inicial robusta, se emplean bases de datos públicas (UCI, PhysioNet) que permiten validar el procesamiento/visualización antes de pasar a adquisiciones propias.

---

## 🎯 Objetivo del proyecto
- Formular un problema de clasificación (reposo / pre-fatiga / fatiga) usando sEMG de músculos relevantes para fútbol.
- Validar filtros, selección de canales y visualizaciones con **datasets de referencia**.
- Sentar bases para etapas posteriores: filtrado, normalización, análisis espectral y extracción de características.

---

## 📚 Bases de datos de referencia
- **EMG dataset in Lower Limb — UCI**
  - 22 sujetos (11 sanos, 11 con anormalidades de rodilla), 132 señales, ~15 s cada una.
  - sEMG bipolar convencional en tareas de marcha/extensión/flexión.
  - ➤ Útil para patrones básicos de activación, pero no incluye condiciones específicas de fatiga.

- **Individual differences in the neural strategies to control the lateral and medial head of the quadriceps during a mechanically constrained task (cuádriceps, HD-sEMG)**
  - 22 adultos (20–30 años), 1792 señales, 60 segundos por contracción, 2048 Hz.
  - Extensiones isométricas a 25% del torque máximo; enfoque en control neuromuscular.
  - ➤ Útil para explorar indicadores de fatiga; muestra reducida en algunas condiciones.

- **Surface EMG during long-lasting ground walking of young able-bodied subjects**
  - 31 adultos jóvenes, caminata, 2000 Hz, 60 s.
  - sEMG multicanal (vasto medial/lateral, etc.) con distintos niveles de esfuerzo.
  - ➤ Útil para observar variaciones asociadas a inicio de fatiga y simetrías.

> **Relevancia conjunta**: permiten probar y comparar estrategias de preprocesado y selección de canales en músculos clave (bíceps femoris, vasto medial, recto femoral, semitendinoso, gastrocnemio lateral, tibial anterior), alineados al gesto deportivo.

---

## 🧪 Notebook de ejemplo (PhysioNet, sujeto S2)
**Propósito**: cargar, identificar y visualizar **10 canales sEMG** (5 por pierna), separar por extremidad y graficar actividad cruda.

- **Datos**: 60 s, **fs = 2000 Hz**, 10 canales sEMG.
- **Selección de canales**: filtro por nombre que contiene `"semg"`.
- **Eje temporal**: `t = np.arange(0, 60, 1/fs)`.
- **Separación L/R**: 5 canales izquierda (**LT**), 5 canales derecha (**RT**).
- **Visualización**: subplots por músculo (TA, GL, RF, HAM, VL) para **comparar simetría y patrones**.

**Librerías empleadas**: `wfdb`, `matplotlib`.

---

## 🧰 Requisitos y ejecución rápida
```bash
# Entorno recomendado
python -m venv .venv && source .venv/bin/activate  # (Windows: .venv\Scripts\activate)

# Paquetes mínimos detectados
pip install wfdb matplotlib
```

## 🎓Aporte de los Integrantes

| Integrante | Contribución (%) |
|----------|:----------:|
| Salet Garcia   | 33.33%     |
| Dhiago Llanos  | 33.33%     |

| Rafael Panez   | 33.33%     |
