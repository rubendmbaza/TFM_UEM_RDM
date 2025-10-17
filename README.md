🚀 TFM_UEM_RDM 
Sistema de lectura de displays de 7 segmentos usando Gemma, EasyOCR y YOLOv8  

📝 Nota importante  
El notebook de Colab no se visualiza correctamente en GitHub debido a un error con los widgets interactivos.  

▶️ Cómo usar:  
Descarga el notebook.

Ábrelo desde tu cuenta de Google Colab.

Introduce tu Token de HuggingFace cuando sea requerido (se encuentra comentado en el texto, por lo que la celda en sí no da error).

🔄 Reentrenamiento personalizado  
Si deseas realizar el entrenamiento desde cero:  

Elimina las carpetas yolo-...-runs después de ejecutar !git clone.

Sigue los pasos del notebook.

🚀 Sistema de Reconocimiento de Displays 7 Segmentos
Correspondiente al Notebook "TFM_Ruben_Diaz_Molina.ipynb"

🔍 Descripción del Proyecto
Sistema comparativo de modelos de visión artificial para el reconocimiento preciso de dígitos en displays de 7 segmentos, implementado en Google Colab.

🛠 Modelos Implementados
###  Google Paligemma 3b

Modelo multimodal (visión + lenguaje)

Reconocimiento mediante prompts naturales

Zero-shot learning

###  EasyOCR

Pipeline clásico de dos etapas:
  1. Detección de texto sin Fine-Tuning.
  2. Análisis del rendimiento con recortes guiados por YOLO para aislar el reconocimiento.

###  YOLOv8 (3 Versiones)
| Versión          | Épocas | Tamaño Imagen | Pre-entrenamiento | 
|------------------|--------|---------------|-------------------|
| Básica           | 50     | 224px         | No                |
| Optimizada       | 50     | 224px         | Sí                |
| Avanzada         | 100    | 320px         | Sí                |

🎯 Métricas de Precisión
Los resultados detallados y las tablas comparativas se encuentran en el archivo Tablas de precisión.xlsx. El análisis se basa en tres métricas:

Precisión Absoluta: La métrica más estricta. La predicción debe ser una coincidencia exacta con el valor real, incluyendo todos los dígitos y el punto decimal en su posición correcta.

Precisión Numérica: Una métrica más flexible. La predicción es correcta si los dígitos numéricos coinciden, ignorando errores u omisiones en el punto decimal.

Precisión Relativa: Un análisis a nivel de carácter individual para una evaluación granular. Se usa un sistema de puntuación para medir la fiabilidad del modelo: +1 por acierto, 0 por omisión y -1 por error.

