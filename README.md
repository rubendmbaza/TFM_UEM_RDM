# 🚀 TFM UEM - Digitalización de Displays de 7 Segmentos

[![Python](https://img.shields.io/badge/Python-3.10-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?&logo=PyTorch&logoColor=white)](https://pytorch.org/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-00FFFF.svg?&logo=YOLO&logoColor=darkblue)](https://github.com/ultralytics/ultralytics)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Models-yellow)](https://huggingface.co/)

> **Estudio comparativo de modelos de IA (PaLI-Gemma, EasyOCR y YOLOv8) para el reconocimiento de dígitos en displays de 7 segmentos en entornos industriales.**

---

## 📝 Nota Importante

El notebook de Colab no se visualiza correctamente en la interfaz de GitHub debido a un error de renderizado con los widgets interactivos.

### ▶️ Cómo Ejecutar el Proyecto
1.  **Descargar el Notebook**: Haz clic en `TFM_Ruben_Diaz_Molina.ipynb` y luego en el botón "Download".
2.  **Abrir en Google Colab**: Ve a [colab.research.google.com](https://colab.research.google.com) y selecciona `Archivo > Subir cuaderno` para abrir el archivo que has descargado.
3.  **Autenticación**: Introduce tu Token de Hugging Face cuando la celda correspondiente lo solicite para poder descargar el modelo PaLI-Gemma.

---

## 🛠️ Modelos Evaluados

Este proyecto implementa y compara tres enfoques distintos de visión artificial:

### 1. Google PaLI-Gemma 3B
- **Tipo**: Modelo Multimodal (Visión + Lenguaje).
- **Método**: Realiza el reconocimiento mediante *prompts* en lenguaje natural (ej: "¿qué número ves?"). No requiere entrenamiento específico (*zero-shot learning*).

### 2. EasyOCR
- **Tipo**: Pipeline de Reconocimiento Óptico de Caracteres (OCR).
- **Método**: Utiliza un sistema de dos etapas para detectar y luego reconocer texto. Se evalúa su rendimiento "de serie" sin *fine-tuning*.

### 3. YOLOv8
- **Tipo**: Detector de Objetos.
- **Método**: Trata cada dígito (`0-9`) y el punto (`.`) como un objeto independiente que debe ser localizado y clasificado. Se han evaluado tres configuraciones:

| Versión | Épocas | Tamaño Imagen | Pre-entrenamiento |
|:--- |:---:|:---:|:---:|
| **Básica** | 50 | 224x224 px | No |
| **Optimizada** | 50 | 224x224 px | Sí (COCO) |
| **Avanzada** | 100 | 320x320 px | Sí (COCO) |

---

## 🎯 Métricas de Precisión

Los resultados detallados de kas tablas de precisión se encuentran en el archivo `Tablas de Precisión.xlsx`. El análisis se basa en tres métricas clave:

-   **Precisión Absoluta**: La métrica más estricta. La predicción debe ser una coincidencia exacta con el valor real, incluyendo todos los dígitos y el punto decimal.
-   **Precisión Numérica**: Una métrica más flexible que considera un acierto si los dígitos son correctos, ignorando errores en el punto decimal.
-   **Precisión Relativa**: Un análisis granular a nivel de carácter que mide la fiabilidad del modelo con un sistema de puntuación (`+1` por acierto, `0` por omisión, `-1` por error).

---

## 🔄 Reentrenamiento Personalizado
Si deseas realizar el entrenamiento de los modelos YOLOv8 desde cero:
1.  Abre el notebook en Google Colab y ejecuta la primera casilla.
2.  Elimina el archivo de imágenes preselccionadas para test que se ecuentra en `imagenes > selected_images.npy`
3.  En las celdas de entrenamiento de YOLO, el código comprueba si la carpeta de resultados (`yolo-...-runs`) ya existe.
4.  Para forzar un nuevo entrenamiento, simplemente elimina la carpeta correspondiente antes de ejecutar la celda.
