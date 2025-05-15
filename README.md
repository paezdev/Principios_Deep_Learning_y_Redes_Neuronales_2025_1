# Reconocimiento con Redes Neuronales — Actividad 1

## Descripción

Este repositorio corresponde a la **primera entrega** del proyecto de reconocimiento utilizando redes neuronales. En esta etapa inicial, se desarrolla y entrena un modelo básico, se analizan sus resultados y se establecen las bases para futuras implementaciones y mejoras.

> **Nota:** Este no es el trabajo final. El repositorio se irá ampliando con nuevas carpetas y notebooks para actividades posteriores (por ejemplo, `actividad2` para la implementación práctica, mejoras, pruebas adicionales, etc.).

## Estructura Actual

- `paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb`: Notebook principal de la primera actividad, donde se desarrolla el modelo, se entrena y se analizan los resultados.
- `image.png`: Imágenes de referencia o visualizaciones generadas durante el entrenamiento.

## Proceso de Entrenamiento

El modelo fue entrenado durante 20 épocas, mostrando una mejora constante en las métricas de precisión (*accuracy*) y pérdida (*loss*) tanto en los datos de entrenamiento como de validación. Se utilizaron técnicas estándar de preprocesamiento y validación para asegurar la robustez del modelo.

### Resultados Principales

- **Precisión final de entrenamiento:** ~98.66%
- **Precisión final de validación:** ~98.81%
- **Pérdida final de entrenamiento:** ~0.05
- **Pérdida final de validación:** ~0.05

Las curvas de accuracy y loss muestran un aprendizaje estable y sin señales de sobreajuste, lo que indica que el modelo generaliza correctamente a datos no vistos.

## Conclusiones

El modelo de red neuronal desarrollado en esta primera actividad demuestra un desempeño sobresaliente, alcanzando altos niveles de precisión y bajas pérdidas tanto en entrenamiento como en validación. La similitud entre las métricas de ambas fases indica que el modelo no presenta sobreajuste y es capaz de generalizar adecuadamente. Estos resultados validan la efectividad de la arquitectura y los hiperparámetros seleccionados para esta etapa inicial.

## Recomendaciones

1. **Evaluar con un conjunto de prueba independiente:**  
   Probar el modelo con datos completamente nuevos para confirmar su capacidad de generalización.

2. **Implementar early stopping:**  
   Utilizar esta técnica para optimizar el tiempo de entrenamiento y evitar épocas innecesarias.

3. **Guardar y documentar el modelo:**  
   Registrar la arquitectura y los hiperparámetros para facilitar futuras mejoras o reutilización.

4. **Monitorear el desempeño en producción:**  
   Supervisar el modelo si se implementa en un entorno real para detectar posibles degradaciones.

5. **Explorar técnicas de regularización si se amplía el dataset:**  
   Considerar dropout, regularización L1/L2 o aumento de datos si se observa sobreajuste en el futuro.

6. **Analizar los errores:**  
   Revisar los casos de fallo para identificar oportunidades de mejora.

7. **Actualizar el modelo periódicamente:**  
   Reentrenar el modelo si los datos cambian con el tiempo para mantener su precisión.

## Próximos Pasos

- Agregar nuevas carpetas y notebooks para la **Actividad 2** y siguientes, donde se implementarán mejoras, pruebas adicionales y aplicaciones prácticas del modelo.
- Documentar cada nueva etapa para mantener la trazabilidad y evolución del proyecto.

## Requisitos

- Python 3.x
- TensorFlow / Keras
- Numpy, Matplotlib, y otras librerías estándar de ciencia de datos

## Ejecución

1. Clona este repositorio.
2. Abre el notebook `paez_jean_reconocimiento_redes_neuronales(actividad1).ipynb`.
3. Ejecuta las celdas siguiendo el flujo del notebook.
4. Analiza los resultados y gráficas generadas.

## Autor

Jean Páez

---