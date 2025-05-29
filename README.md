# Reconocimiento con Redes Neuronales — Actividades 1 y 2

## Descripción

Este repositorio corresponde al desarrollo progresivo de un proyecto de reconocimiento utilizando redes neuronales. Se documentan los experimentos y resultados de dos entregas principales:

- **Actividad 1:** Entrenamiento de un modelo básico (MLP) para clasificación de imágenes (MNIST).
- **Actividad 2:** Análisis de dos casos prácticos aplicando redes **CNN** para imágenes y **RNN** para texto.

> **Nota:** El repositorio continuará ampliándose con nuevas carpetas y notebooks conforme avancen las siguientes actividades del curso.

---

## 📁 Estructura del Proyecto

```
.
├── docs
│   ├── actividad 1
│   │   └── paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb - Colab.pdf
│   ├── actividad 2
│       └── Paez_Jean_EA_CNN_RNN.ipynb - Colab.pdf
├── src
│   └── notebook
│       ├── actividad 1
│       |   └── paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb
│       ├── actividad 2
│           └── Paez_Jean_EA_CNN_RNN.ipynb
├── .gitignore
└── README.md

```

---

## ✅ Actividad 1 — Modelo MLP (MNIST)

### Descripción

Se desarrolla y entrena un modelo básico de red neuronal multicapa (MLP) para clasificar imágenes del dataset MNIST. Se analiza el desempeño en función de precisión y pérdida.

### Resultados Principales

- **Precisión final de entrenamiento:** ~98.66%
- **Precisión final de validación:** ~98.81%
- **Pérdida final de entrenamiento:** ~0.05
- **Pérdida final de validación:** ~0.05

El modelo generaliza correctamente, sin señales de sobreajuste.

### Recomendaciones

- Evaluar con datos nuevos
- Aplicar *early stopping*
- Monitorear en producción
- Implementar regularización si se amplía el dataset

---

## 📊 Actividad 2 — Análisis con CNN y RNN

### Parte 1: RNN para Análisis de Sentimiento

Se estudia un caso donde una empresa quiere clasificar comentarios de usuarios en positivos o negativos. Se propone usar una **RNN (LSTM o GRU)** como solución. Incluye:

- Diagrama de arquitectura en Draw.io
- Identificación de desafíos técnicos
- Soluciones aplicables con embeddings y redes bidireccionales

### Parte 2: CNN para Clasificación MNIST

Se implementa una arquitectura **CNN** para el mismo problema de MNIST, obteniendo una mejora notable con respecto al modelo MLP.

- Capa convolucional + ReLU
- Capa de pooling
- Fully connected + Softmax
- Diagrama arquitectónico hecho en Draw.io

### Resultados

- **Precisión en validación:** 98.66%
- Gráficas de precisión por época
- Comparación con resultados de la actividad 1

---

## 🧠 Conclusión Final y Recomendaciones

CNN demostró ser más adecuada para imágenes, mientras que las RNN se ajustan mejor a datos secuenciales como texto. La selección correcta de arquitectura impacta directamente en el rendimiento.

**Recomendaciones:**
- Usar regularización y data augmentation en CNN
- Probar con datasets como CIFAR-10 o Fashion-MNIST
- Seguir documentando cada etapa en notebooks separados

---

## 🛠️ Requisitos

- Python 3.x
- TensorFlow / Keras
- Numpy, Matplotlib, Scikit-learn
- draw.io (para visualizar diagramas)

---

## ▶️ Ejecución

1. Clona este repositorio.
2. Accede a `actividad1/` o `actividad2/`.
3. Abre y ejecuta los notebooks correspondientes.
4. Analiza los resultados y gráficas generadas.

---

## 👤 Autor

Jean Carlos Páez Ramírez

---

> *El proyecto se encuentra en desarrollo continuo como parte del curso de Deep Learning y Redes Neuronales.*
```