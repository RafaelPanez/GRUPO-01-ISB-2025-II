# Object Detection aplicado a Imágenes de ECG

## Índice

- [1. Teoría breve del tópico elegido](#1-teoria-breve-del-topico-elegido)
- [2. Papers que emplean el tópico y presentan resultados](#2-papers-que-emplean-el-topico-y-presentan-resultados)
- [3. Repositorio de GitHub relacionado con el tópico seleccionado](#3-repositorio-de-github-relacionado-con-el-topico-seleccionado)
- [4. Conclusiones](#4-conclusiones)


## 1. Teoría breve del tópico elegido

El Object Detection es una técnica de visión por computadora cuyo objetivo es identificar y localizar regiones relevantes dentro de una imagen. Mientras que en la electrocardiografía clásica la información se presenta como una señal 1D, en muchos entornos clínicos los ECG están disponibles únicamente como imágenes, ya sea por capturas de monitores, fotografías o documentos escaneados. Para analizar estos registros, la señal se trata como una imagen y los eventos fisiológicos del ECG se interpretan como “objetos”.

Un complejo QRS puede representarse mediante un rectángulo o bounding box que delimita su posición en la imagen. La misma lógica puede aplicarse para ondas P, ondas T, segmentos ST o diferentes tipos de latidos. La metodología consiste en transformar la señal 1D en una figura, normalizar su escala gráfica, procesarla mediante un modelo como YOLO y obtener coordenadas normalizadas que indican dónde ocurren los eventos.

Este enfoque es especialmente valioso en situaciones donde no existe acceso a la señal cruda. Permite digitalizar ECG impresos, automatizar el conteo de latidos, generar métricas básicas como frecuencia cardíaca, y habilitar aplicaciones clínicas portátiles y de bajo costo, incluso en contextos de telemedicina o triaje.

## 2. Papers que emplean el tópico y presentan resultados

A continuación se presentan dos trabajos representativos que aplican object detection o enfoques equivalentes sobre imágenes de ECG. Para cada uno se resumen el objetivo, metodología, resultados alcanzados y su relevancia para el estudio.

| Titulo | Objetivo | Metodología | Resultados | Relevancia |
|--------|----------|-------------|------------|------------|
| An Open-Source Python Framework and Synthetic ECG Image Datasets for Digitization, Lead Detection, and Segmentation. Rahimi et al., arXiv:2506.06315 (2025) | Proponer un framework completo para digitalización de ECG y detección de regiones mediante object detection. | Generación de imágenes sintéticas; anotaciones YOLO; entrenamiento de YOLOv5/YOLOv8 | Alto desempeño en detección de derivaciones con mAP superior al 95%; robusto ante distorsiones y ruido. | Fundamenta el uso de object detection en ECG y proporciona datasets listos para entrenamiento. |

|YOLO-ResTinyECG: A Lightweight ECG Image Object Detection Network. Li et al., Expert Systems With Applications (2025)| Desarrollar una variante ligera de YOLO optimizada para reconocimiento de latidos en imágenes ECG. |Conversión de ventanas de ECG en imágenes; arquitectura compacta; entrenamiento con MIT-BIH.|mAP superior al 90% y detección eficiente de latidos normales y ventriculares en tiempo real.|Demuestra la eficacia de YOLO en la detección de latidos directamente desde imágenes, validando su uso en laboratorios y dispositivos portátiles.|

**Tabla 1. Resumen de artículos científicos relevantes**

Ambos estudios coinciden en que el análisis de ECG mediante técnicas de detección en imágenes es una alternativa moderna, eficaz y compatible con procesamiento en tiempo real, incluso en hardware limitado. Los métodos evaluados se apoyan en arquitecturas ligeras y datos sintéticos o clínicos para alcanzar resultados competitivos.

## 3. Repositorio de GitHub relacionado con el tópico seleccionado

El repositorio más completo alineado con la temática es el framework oficial que acompaña el artículo de Rahimi et al. Incluye generación de imágenes, anotaciones en formato YOLO, máscaras de segmentación y notebooks de Python para replicar la metodología propuesta.

| Repositorio | URL | Contenido | Utilidad |
|-------------|-----|-----------|----------|
| ECG Image & Signal Dataset Framework | https://github.com/rezakarbasi/ecg-image-and-signal-dataset | Scripts para generar imágenes sintéticas de ECG; creación automática de bounding boxes; máscaras de segmentación; notebooks en Python para generar datasets y entrenar modelos. | Permite reproducir el proceso completo de digitalización y object detection aplicado a ECG. |

**Tabla 2. Repositorio relevante**

El notebook incluido muestra paso a paso cómo se construye una representación gráfica del ECG, cómo se simulan condiciones similares a un ECG en papel y cómo se generan las anotaciones en formato YOLO necesarias para entrenar detectores modernos. Este recurso constituye una base sólida para desarrollar tareas de detección y segmentación aplicadas a electrocardiogramas representados como imágenes.

## 4. Conclusiones

El análisis de ECG mediante object detection integra conceptos de la ingeniería biomédica y la visión computacional para abordar escenarios donde la señal solo está disponible en forma de imagen. Los artículos analizados demuestran que los modelos de detección basados en arquitecturas como YOLO pueden reconocer complejos QRS, derivaciones o tipos de latidos con alta precisión, incluso bajo ruido y distorsiones. El repositorio asociado proporciona herramientas prácticas que permiten implementar de manera inmediata este enfoque.