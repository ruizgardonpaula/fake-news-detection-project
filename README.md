# 🛡️ Fake News Detection: Machine Learning vs. Deep Learning (DistilBERT)

Este proyecto desarrolla un sistema de clasificación binaria para identificar noticias falsas con alta fidelidad, comparando la eficiencia de algoritmos estadísticos clásicos frente a arquitecturas modernas de **Transformers**. 

[![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)](https://www.python.org/)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Transformers-orange)](https://huggingface.co/docs/transformers/index)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red?logo=pytorch)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📌 Descripción General
El objetivo principal es combatir la desinformación mediante el procesamiento de lenguaje natural (NLP). El sistema analiza el contenido textual de noticias y detecta patrones de manipulación, comparando una línea base de **Machine Learning (TF-IDF + Regresión Logística)** contra un modelo de **Deep Learning (DistilBERT)**.

### Características Clave:
- **Detección de Data Leakage:** Implementación de limpieza con Regex para eliminar metadatos de agencias (ej. "Reuters") que sesgan el modelo.
- **Pipeline Dual:** Preprocesamiento adaptativo según el tipo de arquitectura utilizada.
- **Inferencia en tiempo real:** Módulo funcional para validar noticias externas.
- **Optimización de recursos:** Fine-tuning de DistilBERT configurado para ejecutarse en entornos con VRAM limitada.

---

## 📊 Comparativa de Rendimiento

| Métrica | ML Clásico (TF-IDF + LR) | Deep Learning (DistilBERT) |
| :--- | :---: | :---: |
| **Accuracy** | 98% | **99%** |
| **F1-Score (Fake)** | 0.99 | **0.99** |
| **Carga Computacional** | Muy Baja (CPU) | Alta (GPU Requerida) |
| **Comprensión Semántica** | Basada en términos | Contextual y gramatical |

---

## 📂 Estructura del Proyecto

```bash
fake-news-detection-project/
├── data/                       # Datasets originales (ISOT Dataset)
│   ├── Fake.zip
│   └── True.zip
├── docs/                       # Documentación técnica y académica
│   └── Memoria_Tecnica.pdf
├── notebooks/                  # Desarrollo experimental
│   └── fake_news_detector.ipynb
├── README.md                   # Documentación principal
└── requirements.txt            # Dependencias del entorno
```
---

## 🛠️ Instalación y Requisitos

1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/ruizgardonpaula/fake-news-detection-project.git
   cd fake-news-detection-project
   ```
2. **Instalar dependencias::** 
   ```bash
   pip install -r requirements.txt
   ```
3. **Uso:** Ejecuta el notebook notebooks/fake_news_detector.ipynb en Google Colab o Jupyter. Para el entrenamiento del modelo Transformer, se recomienda activar la aceleración por GPU.

---

## 🔬 Metodología

### 1. Preprocesamiento de Datos
* **ML Clásico:** Limpieza estricta, eliminación de *stopwords* y lematización mediante la librería `NLTK`.
* **DistilBERT:** Limpieza ligera para preservar la estructura sintáctica y el contexto semántico necesario para el mecanismo de atención del *Transformer*.

### 2. Fine-Tuning
Se realizó un ajuste fino del modelo `distilbert-base-uncased` durante **3 épocas**, utilizando un optimizador **AdamW** con una tasa de aprendizaje (learning rate) de $2 \times 10^{-5}$ y la implementación de técnicas de acumulación de gradientes para optimizar el consumo de memoria VRAM.

---

## ⚠️ Limitaciones y Consideraciones Éticas
* **Sesgo de Dataset:** El modelo ha sido entrenado con el ISOT Dataset (noticias políticas de 2017). El rendimiento podría variar al enfrentarse a noticias actuales o de sectores temáticos distintos (Salud, Clima, conflictos internacionales recientes, etc.).
* **Detección de IA:** La desinformación generada por Modelos de Lenguaje de Gran Escala (LLMs) actuales puede requerir técnicas adicionales de detección basadas en marcas de agua digitales o análisis de coherencia sintáctica avanzada.

---

## 👩‍💻 Autora
**Paula Ruiz Gardon** *Máster en Ciberseguridad e Inteligencia Artificial* [LinkedIn](https://linkedin.com/in/paularuizgardon) | [GitHub](https://github.com/ruizgardonpaula)

---
> *Este proyecto es parte del Trabajo de Fin de Módulo para **CEI - Escuela de Diseño y Marketing**.*
