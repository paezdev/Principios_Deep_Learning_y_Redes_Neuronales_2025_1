# Reconocimiento con Redes Neuronales — Actividades 1 y 2

## Descripción

Este repositorio corresponde al desarrollo progresivo de un proyecto de reconocimiento utilizando redes neuronales. Se documentan los experimentos y resultados de dos entregas principales:

- **Actividad 1:** Detección de fraudes financieros con un modelo básico de red neuronal.
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

## ✅ Actividad 1 — Detección de Fraudes Financieros con Red Neuronal

### Descripción

En esta actividad se desarrolla un modelo de red neuronal para detectar fraudes en transacciones con tarjetas de crédito. Se identifican variables relevantes (features) como monto, ubicación, hora, tipo de comercio, historial del cliente, entre otras, que alimentan el modelo.

El modelo es una red neuronal secuencial con una capa de entrada, dos capas ocultas con activación ReLU y una capa de salida con activación sigmoide, adecuada para clasificación binaria (fraude/no fraude).

### Variables de Entrada (Features)

1. Monto de la transacción (`transaction_amount`)
2. Ubicación del comercio vs. ubicación habitual del cliente (`merchant_location_distance`)
3. Hora de la transacción (`transaction_hour`)
4. Tipo de comercio (`merchant_type`)
5. Historial del cliente (`customer_transaction_count`)
6. Frecuencia de transacciones recientes (`transactions_last_24h`)
7. Tipo de tarjeta (`card_type`)
8. Dispositivo usado (`device_id`)
9. Dirección IP (`ip_location_match`)
10. País de origen (`country_match`)

### Proceso de Entrenamiento

- Se genera un conjunto de datos sintético con 10 características, con un desbalance de clases (95% legítimos, 5% fraudes).
- Se divide en conjuntos de entrenamiento y prueba.
- Se normalizan los datos para mejorar el desempeño.
- Arquitectura del modelo:
  - Capa de entrada con 10 neuronas.
  - Dos capas ocultas con 16 y 8 neuronas respectivamente, activación ReLU.
  - Capa de salida con 1 neurona y activación sigmoide.
- Optimización con Adam y función de pérdida `binary_crossentropy`.
- Entrenamiento durante 20 épocas con validación interna.

### Resultados

- Precisión final de entrenamiento: ~98.66%
- Precisión final de validación: ~99%
- La curva de precisión y pérdida muestra buen aprendizaje sin sobreajuste.
- Matriz de confusión:

|               | Predicho Legítimo | Predicho Fraude |
|---------------|-------------------|-----------------|
| Real Legítimo | 1897              | 3               |
| Real Fraude   | 33                | 67              |

- Reporte de clasificación:

| Clase   | Precisión | Recall | F1-score | Soporte |
|---------|-----------|--------|----------|---------|
| Legítimo| 0.98      | 1.00   | 0.99     | 1900    |
| Fraude  | 0.96      | 0.67   | 0.79     | 100     |
| **Accuracy global** |           |        | 0.98     | 2000    |

### Interpretación

- El modelo identifica correctamente la mayoría de transacciones legítimas (recall 1.00).
- Tiene margen de mejora en la detección de fraudes (recall 0.67), típico en problemas con clases desbalanceadas.
- La precisión para fraudes es alta (0.96), indicando que cuando predice fraude, suele acertar.
- El F1-score para fraudes (0.79) muestra un buen equilibrio, pero se recomienda mejorar la sensibilidad.

### Recomendaciones

1. Evaluar con un conjunto de prueba independiente para confirmar generalización.
2. Implementar *early stopping* para optimizar tiempo y recursos.
3. Guardar y documentar el modelo y sus hiperparámetros.
4. Monitorear desempeño en producción para detectar cambios en datos o entorno.
5. Explorar técnicas de regularización (dropout, L1/L2) y aumento de datos si se amplía el dataset.
6. Analizar errores para mejorar calidad de datos o arquitectura.
7. Actualizar el modelo periódicamente para mantener precisión y relevancia.

### Visualización de Resultados


Se incluyen gráficas de precisión y pérdida durante el entrenamiento y validación, que muestran la evolución positiva y estable del modelo.
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
- Comparación con resultados de la actividad 1 de ML

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