# Edge-BMS: Lightweight AI-based Battery Management System

## Overview
This project presents a lightweight AI-based Battery Management System (Edge-BMS) designed for real-time State of Charge (SoC) estimation on embedded hardware.

The goal of this research is to reduce cloud dependency and enable real-time battery monitoring and control directly on edge devices.

The system integrates deep learning-based SoC prediction with an embedded microcontroller platform (STM32) to perform inference and support battery cell balancing.

---

## Key Features
- Lightweight deep learning model for SoC prediction
- Edge AI deployment on STM32 microcontroller
- Real-time battery monitoring
- Integration with battery cell balancing control
- Designed for low-power embedded environments

---

## System Pipeline
1. Battery data acquisition (voltage, current, temperature)
2. Data preprocessing and normalization
3. Deep learning model training
4. Model export (.h5)
5. Embedded AI deployment on STM32
6. Real-time SoC estimation
7. Battery cell balancing control

---

## AI Models Compared
Three models were evaluated for SoC prediction.

- Conv1D + MLP
- GRU + MLP
- LSTM + MLP

The Conv1D + MLP model achieved the best balance between accuracy and computational efficiency, making it suitable for edge deployment.

---

## Model Performance

Conv1D + MLP  
RMSE: 0.0375  
MAE: 0.0286  
MAPE: 9.38%

GRU + MLP  
RMSE: 0.0536  
MAE: 0.0409  
MAPE: 13.70%

LSTM  
RMSE: 0.0418  
MAE: 0.0294  
MAPE: 9.53%

The Conv1D + MLP model was selected for deployment due to its lower error and smaller parameter size.

---

## Embedded Deployment

Target Hardware  
STM32 NUCLEO-G431RB

The trained deep learning model was deployed on the STM32 microcontroller for edge inference.

The embedded system performs:
- real-time battery state monitoring
- AI inference for SoC prediction
- control signals for battery cell balancing circuits

---

## Cell Balancing System

The system includes a capacitor shuttle-based cell balancing circuit.

Characteristics:
- energy transfer between battery cells
- MOSFET-based switching control
- MCU GPIO control

This approach improves energy efficiency compared to passive balancing methods.

---

## Repository Structure

Edge-BMS
│
├ model
│   └ soc_prediction_model.h5
│
├ stm32
│   └ embedded inference code
│
├ paper
│   └ research paper
│
└ README.md

---

## Technologies Used

Python  
TensorFlow / Keras  
Deep Learning (Conv1D, GRU, LSTM)  
Embedded AI  
STM32 Microcontroller  
Battery Management System

---

## Future Work

- Integration of SoH prediction models
- Optimization of embedded inference performance
- Full real-time battery management system implementation
- Advanced cell balancing strategies

---

## Authors

Yongjun Jang  
Sooyeon Kim  
Ihyun Noh
