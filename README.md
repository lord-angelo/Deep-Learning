# Deep Learning

Cuatro proyectos de redes neuronales desarrollados en la especialización de Ciencia de Datos (Duoc UC, 2025), desde redes densas hasta Transformers, con **TensorFlow/Keras**. Cada uno sigue el mismo método: un modelo base, variantes que cambian un hiperparámetro a la vez y una comparación con métricas.

| # | Proyecto | Tarea | Modelo | Resultado |
|---|---|---|---|---|
| 1 | [Feedforward · MNIST](01-feedforward-mnist/feedforward_mnist.ipynb) | Clasificación de dígitos escritos a mano | Red densa (MLP), comparación de optimizadores, batch size, épocas, tasa de aprendizaje y funciones de pérdida | **98,2 %** accuracy en validación (Adam, batch 64) |
| 2 | [CNN · Los Simpsons](02-cnn-simpsons/cnn_simpsons.ipynb) | Clasificación de imágenes de personajes | CNN de 4 bloques con BatchNormalization, Dropout progresivo y data augmentation; 5 arquitecturas comparadas | **97,4 %** accuracy en test (890 imágenes) |
| 3 | [RNN · El Quijote](03-rnn-quijote/lstm_quijote.ipynb) | Generación de texto carácter a carácter | LSTM; comparación de configuraciones y efecto de la temperatura al generar | Texto generado con estilo del Quijote |
| 4 | [Transformer · DailyDialog](04-transformer-dailydialog/transformer_dailydialog.ipynb) | Generación de respuestas en diálogos | Transformer encoder-decoder; evaluación con BLEU | Implementación completa y ajuste de hiperparámetros |

## Detalle

### 1. Feedforward · MNIST
Partiendo de un baseline, se probaron 9 variantes cambiando un solo hiperparámetro cada vez. El mejor resultado fue con **batch size 64**: 98,24 % de accuracy en validación, con curvas de entrenamiento y validación casi iguales (sin sobreajuste). El notebook [`carga_mejor_modelo`](01-feedforward-mnist/carga_mejor_modelo.ipynb) evalúa el modelo guardado con MNIST y con un dataset de dígitos hecho a mano.

### 2. CNN · Los Simpsons
Se compararon 5 arquitecturas. La ganadora (`modelo2c`) usa Dropout progresivo (0,10 → 0,25) en los bloques convolucionales, más BatchNormalization y data augmentation (flip, rotación, zoom). Logró **97,4 % de accuracy en test** con una brecha mínima entre entrenamiento y validación. El notebook [`carga_mejor_modelo`](02-cnn-simpsons/carga_mejor_modelo.ipynb) descarga el modelo entrenado y predice sobre imágenes nuevas.

### 3. RNN · El Quijote
Modelo de lenguaje basado en caracteres con LSTM, entrenado con el texto de *Don Quijote de la Mancha*. Se compararon configuraciones de unidades y entrenamiento, y se analizó cómo cambia el texto generado según la temperatura de muestreo.

### 4. Transformer · DailyDialog
Implementación de un Transformer para generar respuestas en conversaciones del dataset DailyDialog: tokenización, máscaras, entrenamiento y evaluación con BLEU sobre muestras generadas.

## Cómo ejecutarlos

Los notebooks están pensados para **Google Colab**: descargan sus datos al ejecutarse. Para correrlos localmente:

```bash
pip install -r requirements.txt
jupyter notebook
```

## Créditos

Trabajos realizados en equipo (Equipo 6) para la asignatura de Deep Learning de Duoc UC, sede Concepción. Desarrollo y documentación: Angelo López.
