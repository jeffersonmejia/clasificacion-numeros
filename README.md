# Clasificacion de Digitos Manuscritos mediante Red Neuronal Convolucional

## Indice

1. [Resumen](#1-resumen)
2. [Instalacion](#2-instalacion)

---

## 1. Resumen

Este proyecto implementa una red neuronal convolucional (CNN) para la clasificacion de digitos manuscritos del dataset **MNIST**. El modelo fue entrenado con **60.000 imagenes** de entrenamiento y validado con **10.000 imagenes** de prueba, todas con resolucion de **28 x 28 pixeles** en escala de grises.

La arquitectura de la red consta de dos capas convolucionales (32 y 64 filtros) con agrupamiento maximo (*MaxPooling*), una capa de abandono (*Dropout*) con tasa de 0,5, y dos capas densas completamente conectadas de 100 y 10 neuronas respectivamente. Se aplicaron tecnicas de aumento de datos —rotaciones de hasta 30 grados, desplazamientos horizontales y verticales de hasta 25 %, y factores de acercamiento entre 0,5 y 1,5— para mejorar la capacidad de generalizacion del modelo.

El modelo alcanzo una precision del **98,7 %** sobre el conjunto de prueba tras 60 epocas de entrenamiento con el optimizador Adam y funcion de perdida entropia cruzada categorica. Posteriormente, se exporto a formato **TensorFlow.js** para su despliegue en una aplicacion web interactiva que permite al usuario dibujar o subir un digito y obtener su clasificacion en tiempo real.

**Autor:** Jefferson Mejia

---

## 2. Instalacion

### Requisitos

- Python 3.10 o superior
- Google Colab (para el entrenamiento) o entorno local con TensorFlow 2.x
- Navegador web moderno (para la aplicacion web)

### Entrenamiento del modelo

1. Abrir el cuaderno `P3Modelo_Numero_MejiaJefferson.ipynb` en Google Colab o en un entorno local con Jupyter.
2. Ejecutar todas las celdas en orden secuencial. El cuaderno descargara automaticamente el dataset MNIST, construira, entrenara y exportara el modelo.
3. Al finalizar, se generara el modelo en formato TensorFlow.js dentro de la carpeta `modelo/`.

### Aplicacion web

1. Clonar el repositorio:

   ```bash
   git clone https://github.com/<usuario>/P3modelo_numeros_MejiaJefferson.git
   cd P3modelo_numeros_MejiaJefferson
   ```

2. Abrir el archivo `index.html` directamente en un navegador web. No se requiere servidor local ni instalacion adicional, ya que TensorFlow.js se carga mediante CDN.

3. Dibujar un digito (0-9) en el lienzo o subir una imagen y presionar **Clasificar**.

### Estructura del proyecto

```
P3modelo_numeros_MejiaJefferson/
├── index.html                              # Aplicacion web interactiva
├── P3Modelo_Numero_MejiaJefferson.ipynb    # Cuaderno de entrenamiento
└── modelo/
    ├── model.json                          # Arquitectura del modelo (TF.js)
    └── group1-shard1of1.bin                # Pesos del modelo (TF.js)
```
