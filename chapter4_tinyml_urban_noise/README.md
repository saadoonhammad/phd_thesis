# Chapter 4: TinyML Anomaly Detection on Urban Noise Sensors

Unsupervised anomaly detection in an IoT urban noise sensor network using a Long Short-Term Memory (LSTM) autoencoder, quantised to TensorFlow Lite and deployed on an ESP32-S3 microcontroller.

## Notebooks

One notebook per sensor, with the same pipeline in each:

| Notebook | Sensor |
|---|---|
| `187_LSTM_Anomalies_Paper.ipynb` | TA120-T246187 |
| `189_LSTM_Anomalies_Paper.ipynb` | TA120-T246189 |

1. Data loading and cleaning: sensor selection, duplicate removal, incomplete days, null values
2. Exploratory data analysis: hourly, daily and monthly noise patterns
3. Data preparation: train/test split, scaling, sequence generation
4. LSTM autoencoder training on normal data
5. Anomaly detection through reconstruction error (point and collective anomalies)
6. Evaluation: confusion matrix, precision, recall
7. Conversion to TensorFlow Lite, full-integer quantisation and C array export (`xxd`) for the microcontroller
8. Model size comparison (Keras, TensorFlow Lite, quantised TensorFlow Lite)

## Results

Deployment performance on the target microcontroller (Table 4.5 of the thesis):

| Metric | TA120-T246187 | TA120-T246189 |
|---|---|---|
| Average inference time | 4 ms | 4 ms |
| Power consumption | 0.1333 W ± 0.015 | 0.1448 W ± 0.039 |
| Flash occupancy | 800.63 KB | 800.63 KB |
| RAM occupancy | 102.62 KB | 112.71 KB |
| Heap memory (during inference) | 528 bytes | 744 bytes |

## Data

Noise sensor data from Helsinki, collected as part of the mySMARTLife EU project and publicly available from Helsinki Region Infoshare: https://hri.fi/data/en_GB/dataset/iot-meludataa-helsingista

The data are not redistributed in this repository.

## Publication

Hammad, S. S., Iskandaryan, D., Trilles, S. (2023). An unsupervised TinyML approach applied to the detection of urban noise anomalies under the smart cities environment. *Internet of Things*, 23, 100848. https://doi.org/10.1016/j.iot.2023.100848
