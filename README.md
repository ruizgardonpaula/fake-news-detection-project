# 📝 Fake News Detection: ML vs. Deep Learning (DistilBERT)

![Python](https://img.shields.io/badge/python-3.12-blue.svg)
![Transformers](https://img.shields.io/badge/lib-transformers-orange.svg)
![Accuracy](https://img.shields.io/badge/accuracy-99%25-green.svg)
![License](https://img.shields.io/badge/license-MIT-lightgrey.svg)

## 📌 Descripción del Proyecto
Este repositorio contiene un sistema avanzado de clasificación de noticias diseñado para combatir la desinformación. El proyecto compara dos enfoques tecnológicos distintos para la detección de *Fake News*:
1.  **Machine Learning Clásico:** Vectorización TF-IDF con Regresión Logística.
2.  **Deep Learning:** Fine-tuning del modelo Transformer **DistilBERT** (`distilbert-base-uncased`).

El sistema es capaz de identificar patrones lingüísticos sutiles y determinar la veracidad de un artículo periodístico con una **exactitud final del 99%**.

## 🚀 Características Principales
* **Mitigación de Data Leakage:** Implementación de limpieza avanzada con Regex para eliminar sesgos de agencias (como cabeceras de "Reuters") que suelen inflar artificialmente la precisión.
* **Pipeline Dual de Preprocesamiento:** * Limpieza estricta (lematización y remoción de stopwords) para el modelo estadístico.
    * Limpieza ligera (preservación de contexto) para el modelo Transformer.
* **Inferencia Interactiva:** Módulo integrado para predecir noticias externas en tiempo real.
* **Eficiencia Computacional:** Configuración optimizada para entrenamiento en GPUs comerciales o Google Colab (ajuste de batch size y acumulación de gradientes).

## 📊 Resultados y Comparativa

| Modelo | Accuracy | F1-Score | Ventaja Principal |
| :--- | :---: | :---: | :--- |
| **LogReg + TF-IDF** | 98% | 0.98 | Alta eficiencia en CPU / Baja latencia |
| **DistilBERT** | **99%** | **0.99** | Comprensión semántica y contextual profunda |

> **Análisis:** Mientras que el modelo clásico es excelente para detectar palabras clave, DistilBERT logra capturar matices en el tono narrativo y la estructura gramatical, reduciendo significativamente los falsos positivos.

## 🛠️ Tecnologías Utilizadas
* **Lenguaje:** Python 3.12
* **Bibliotecas NLP:** Hugging Face `transformers`, `datasets`, `evaluate`, NLTK, Scikit-learn.
* **Deep Learning:** PyTorch.
* **Entorno de ejecución:** Google Colab con aceleración por hardware (VRAM optimizada).
* **Dataset:** ISOT Fake News Dataset (University of Victoria).

## 📂 Estructura del Repositorio
```bash
├── notebooks/
│   └── Fake_News_Detection_Model.ipynb   # Código fuente completo y documentado
├── data/                                 # Directorio para archivos True.csv y Fake.csv
├── README.md                             # Documentación del proyecto
└── requirements.txt                      # Dependencias del entorno
