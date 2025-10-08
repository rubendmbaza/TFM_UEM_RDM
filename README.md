# 🚀 TFM_UEM_RDM 
**Sistema de lectura de displays de 7 segmentos usando Gemma, EasyOCR y YOLOv11**  

## 📝 Nota importante  
El notebook de Colab no se visualiza correctamente en GitHub debido a un error con los widgets interactivos.  

### ▶️ Cómo usar:  
1. **Descarga** el notebook  
2. **Ábrelo** desde tu cuenta de Google Colab  
3. **Introduce** tu Token de HuggingFace cuando sea requerido (se encuentra comentado en el texto, por lo que la celda en sí no da error) 

## 🔄 Reentrenamiento personalizado  
Si deseas realizar el entrenamiento desde cero:  
1. Elimina las carpetas `yolo-...` después de ejecutar `!git clone`  
2. Sigue los pasos del notebook  

---

# 🚀 Sistema de Reconocimiento de Displays 7 Segmentos
Correspondiente al Notebook "trabajo_final_bueno.ipynb"

## 🔍 Descripción del Proyecto
Sistema comparativo de modelos de visión artificial para el reconocimiento preciso de dígitos en displays de 7 segmentos, implementado en Google Colab.

## 🛠 Modelos Implementados

### 🦉 **Google Paligemma 3b**
- Modelo multimodal (visión + lenguaje)
- Reconocimiento mediante prompts naturales
- Zero-shot learning

### 🔠 **EasyOCR**
- Pipeline clásico de dos etapas:
  1. Detección clásica sin Fine-Tunning
  2. Detección de caracteres con YOLO haciendo un reconocimiento OCR individual

### 🎯 **YOLOv11 (3 Versiones)**
| Versión          | Épocas | Tamaño Imagen | Pre-entrenamiento | 
|------------------|--------|---------------|-------------------|
| Básica           | 50     | 224px         | No                |
| Optimizada       | 50     | 224px         | Sí                |
| Avanzada         | 100    | 320px         | Sí                |

## 📊 Resultados Clave
Análisis comparativo en 20 imágenes de test:

| Modelo       | Precisión Absoluta| Precisión Relativa| Tiempo/Imagen | Hardware Requerido |
|--------------|-------------------|-------------------|---------------|--------------------|
| Paligemma    | 35%               | 66%               |0.32s          | GPU                |
| EasyOCR      | 0%                | 0%                |0.17s          | CPU                |
| YOLO Básico  | 40%               | 83.19%            |0.04s          | GPU                |
| YOLO Optimizado|   50%           |   90,27%          |0.05s          | GPU                |
|YOLO Avanzado | 60 %              |92.04%             |0.04s          | GPU                |

**Para hallar un análisis más complejo se puede consultar el excel "Comparativas.xlsx"**
