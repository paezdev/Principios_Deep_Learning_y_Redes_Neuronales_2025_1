# Principios de Deep Learning y Redes Neuronales — Actividades 1, 2, 3 y 4

## Descripción

Este repositorio corresponde al desarrollo progresivo de un proyecto de reconocimiento utilizando redes neuronales. Se documentan los experimentos y resultados de cuatro entregas principales:

- **Actividad 1:** Detección de fraudes financieros con un modelo básico de red neuronal.
- **Actividad 2:** Análisis de dos casos prácticos aplicando redes **CNN** para imágenes y **RNN** para texto.
- **Actividad 3:** Implementación básica de una RNN para análisis de sentimiento de texto.
- **Actividad 4:** Mejora de un modelo LSTM bidireccional con embeddings FastText, optimización de hiperparámetros con Keras Tuner, regularización y exportación para producción.

---

## 📁 Estructura del Proyecto

```
.
├── docs
│   ├── actividad 1
│   │   └── paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb - Colab.pdf
│   ├── actividad 2
│   │   └── Paez_Jean_EA_CNN_RNN.ipynb - Colab.pdf
│   ├── actividad 3
│   │   └── Paez_JeanCarlos_Evidencia3_RNN.ipynb - Colab.pdf
│   ├── actividad 4
│   │   └── páez_ramírez_jean_carlos_ consideraciones éticas y legales.pdf
│   │   
├── src
│   └── notebook
│       ├── actividad 1
│       │   └── paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb
│       ├── actividad 2
│       │   └── Paez_Jean_EA_CNN_RNN.ipynb
│       ├── actividad 3
│       │   └── Paez_JeanCarlos_Evidencia3_RNN.ipynb
│       └── actividad 4
│           ├── Paez_Jean_EA4_Codigo.py
│           └── modelo_mejorado_lstm_fasttext.keras
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

## 📝 Actividad 3 — Implementación Básica de RNN para Análisis de Sentimiento

### Descripción

En esta actividad se implementa una red neuronal recurrente básica (RNN) utilizando TensorFlow/Keras, enfocada en el análisis de sentimiento de comentarios de productos. El objetivo es clasificar los comentarios en positivos o negativos, siguiendo los lineamientos de la evidencia de aprendizaje.

El modelo construido incluye:
- Una capa de embedding para la representación vectorial de las palabras.
- Una capa SimpleRNN para el procesamiento secuencial de los datos.
- Una capa densa final con activación sigmoide para la clasificación binaria.

El conjunto de datos utilizado es reducido y simulado, lo que permite demostrar el funcionamiento general del modelo, aunque limita su capacidad de generalización.

### Proceso de Entrenamiento

- Preprocesamiento de los comentarios mediante tokenización y padding.
- Definición de la arquitectura secuencial con las capas mencionadas.
- Compilación del modelo con optimizador Adam y función de pérdida `binary_crossentropy`.
- Entrenamiento durante 10 épocas.
- Evaluación del modelo con nuevos comentarios no vistos.

### Resultados

- Precisión de entrenamiento alcanzó hasta 0.80 en la última época.
- La función de pérdida disminuyó progresivamente, indicando aprendizaje.
- Las predicciones para nuevos comentarios estuvieron cercanas a 0.5, reflejando la limitación del modelo por el tamaño del dataset y la presencia de frases nuevas.

### Conclusiones y Recomendaciones

- El modelo cumple con el objetivo académico de implementar y entender una RNN básica para análisis de sentimientos.
- Para mejorar el rendimiento, se recomienda:
  1. Ampliar el conjunto de datos con ejemplos reales y variados.
  2. Explorar arquitecturas más avanzadas como LSTM o GRU.
  3. Realizar un preprocesamiento más exhaustivo del texto (eliminación de stopwords, normalización, embeddings preentrenados).
  4. Ajustar hiperparámetros y aumentar el número de épocas si se dispone de más datos.

---

## 🧠 Actividad 4 — Mejora de Modelo LSTM con FastText y Optimización

### Descripción

En esta actividad se mejora un modelo de análisis de sentimiento utilizando una red neuronal recurrente bidireccional (LSTM) con embeddings preentrenados FastText. Se optimizan hiperparámetros mediante Keras Tuner, se aplican técnicas de regularización como dropout y batch normalization, y se exporta el modelo para producción.

Se incluyen análisis detallados de resultados, visualizaciones, pruebas con frases personalizadas y consideraciones éticas sobre transparencia, equidad y privacidad.

### Implementación

- Modelo bidireccional LSTM con embeddings FastText (300 dimensiones).
- Optimización de hiperparámetros: tasa de aprendizaje, tamaño de lote, número de épocas, dropout, unidades LSTM, etc.
- Regularización con dropout y batch normalization para evitar sobreajuste.
- Uso de Keras Tuner para búsqueda automática de hiperparámetros.
- Exportación del modelo entrenado para uso en producción.
- Funciones para preprocesamiento, predicción personalizada y evaluación.

### Resultados

- Precisión en validación superior al 80%.
- Buen balance entre precisión y recall, con análisis detallado de matriz de confusión.
- Visualizaciones de curvas de aprendizaje y matriz de confusión.
- Pruebas con frases personalizadas que muestran capacidad de clasificación en textos reales.
- Identificación de limitaciones y recomendaciones para mejorar.

### Consideraciones Éticas y Legales

- **Transparencia:** Documentación clara del modelo, métricas y decisiones.
- **Equidad:** Balanceo de clases y análisis para evitar sesgos.
- **Privacidad:** Uso responsable de datos, anonimización y cumplimiento normativo.

### Recomendaciones

1. Aumento y diversificación de datos para mejorar la generalización.
2. Ajuste fino de hiperparámetros y arquitectura para optimizar desempeño.
3. Implementación de modelos ensemble para mayor robustez.
4. Manejo de neutralidad y ambigüedad en texto para clasificaciones más precisas.
5. Evaluación continua y monitoreo en producción para mantener efectividad.

---

## 🛠️ Requisitos

- Python 3.x
- TensorFlow / Keras
- Numpy, Matplotlib, Scikit-learn
- Keras Tuner
- FastText embeddings (archivo `cc.es.300.vec`)
- draw.io (para diagramas)

---

## ▶️ Ejecución

1. Clona este repositorio.
2. Accede a la carpeta correspondiente a la actividad que deseas ejecutar (`actividad1/`, `actividad2/`, `actividad3/`, `actividad4/`).
3. Abre y ejecuta los notebooks o scripts correspondientes.
4. Analiza los resultados y gráficas generadas.

---

## 👤 Autor

Jean Carlos Páez Ramírez