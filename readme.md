# Contextual Anomaly Detection in IoT Systems on Resource-Constrained Devices using TinyML

Code and data supporting the PhD thesis (compilation by publication) of Sahibzada Saadoon Hammad, Institute of New Imaging Technologies (INIT), Universitat Jaume I, Castelló de la Plana, Spain.

Each chapter folder corresponds to one peer-reviewed article and was originally developed as a standalone repository. They are consolidated here as a single point of reference.

## Repository structure

| Folder | Thesis chapter | Content |
|---|---|---|
| [`chapter2_slm/`](chapter2_slm/) | Chapter 2: State of the Art | Systematic Literature Mapping of TinyML-based anomaly detection in AIoT: search exports, cleaning, deduplication, screening, feature extraction and taxonomy/chart notebooks for the 94-study corpus |
| [`chapter4_tinyml_urban_noise/`](chapter4_tinyml_urban_noise/) | Chapter 4: TinyML Anomaly Detection on Urban Noise | LSTM autoencoder for point and collective anomaly detection in urban noise sensors, quantised to TensorFlow Lite and deployed on the ESP32 |
| [`chapter5_coi_anomaly_detection/`](chapter5_coi_anomaly_detection/) | Chapter 5: Communities of Interest for Anomaly Detection | Community of Interest (CoI) framework for temperature sensor networks: hyperparameter optimisation, final training and evaluation of BiLSTM, LSTM and MLP autoencoders (representative and global models) |

## Publications

| Chapter | Article | DOI |
|---|---|---|
| 2 | Trilles, S., Hammad, S. S., Iskandaryan, D. (2024). Anomaly detection based on Artificial Intelligence of Things: A Systematic Literature Mapping. *Internet of Things*, 25, 101063. | [10.1016/j.iot.2024.101063](https://doi.org/10.1016/j.iot.2024.101063) |
| 4 | Hammad, S. S., Iskandaryan, D., Trilles, S. (2023). An unsupervised TinyML approach applied to the detection of urban noise anomalies under the smart cities environment. *Internet of Things*, 23, 100848. | [10.1016/j.iot.2023.100848](https://doi.org/10.1016/j.iot.2023.100848) |
| 5 | Hammad, S. S., Ramos, F., Gould Carlson, M., Huerta Guijarro, J., Trilles, S. (2026). Community-based model sharing and generalisation: Anomaly detection in IoT temperature sensor networks. *Internet of Things*, 39, 102027. | [10.1016/j.iot.2026.102027](https://doi.org/10.1016/j.iot.2026.102027) |

## Data availability

| Chapter | Data | Source |
|---|---|---|
| 2 | Bibliographic exports, screening decisions and extracted features | Included in [`chapter2_slm/data/`](chapter2_slm/data/). Dataset of the published mapping: [10.5281/zenodo.8231242](https://doi.org/10.5281/zenodo.8231242) |
| 4 | Noise sensor data from Helsinki (mySMARTLife project) | Public, not redistributed here: [Helsinki Region Infoshare](https://hri.fi/data/en_GB/dataset/iot-meludataa-helsingista) |
| 5 | AVAMET meteorological station data | Restricted, not included. Access requires permission from the Associació Valenciana de Meteorologia "Josep Peinado" ([AVAMET](https://www.avamet.org/mxo-meteoxarxaonline.html)). Code archive: [10.5281/zenodo.18758344](https://doi.org/10.5281/zenodo.18758344) |
