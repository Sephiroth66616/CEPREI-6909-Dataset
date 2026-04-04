# CEPREI-6909 Industrial Dataset for Cross-Domain Fault Diagnosis

[![Status](https://img.shields.io/badge/Status-Under%20Review-orange.svg)]()
[![Dataset](https://img.shields.io/badge/Dataset-CEPREI--6909-blue.svg)]()

> **⚠️ IMPORTANT NOTICE:**
> This repository serves as the official data hub for the **CEPREI-6909 Industrial Dataset**, introduced in the paper **"Causal Prototype Variational Information Bottleneck Framework for Cross-Domain Fault Diagnosis"**. 
> 
> **The paper is currently under peer review. To comply with the review policies and protect unpublished work, the dataset download links are temporarily withheld.** 
> 
> **🎉 The complete CEPREI-6909 dataset will be made fully public and freely accessible to the research community immediately upon the acceptance of the paper.** 

---

## 📖 Introduction
In practical industrial applications, rotating machinery often operates under non-stationary conditions (e.g., varying speeds and loads), leading to severe domain shifts and spurious correlations in monitoring data. 

To validate models against these complex challenges, we introduce the **CEPREI-6909 Industrial Dataset**, collected from a customized mechanical fault simulation platform at the China Electronic Product Reliability and Environmental Testing Research Institute (CEPREI). This dataset is specifically designed to evaluate Artificial Intelligence-based fault diagnosis methods under extreme compound working condition shifts and natural class imbalance scenarios.

---

## 🗄️ About the CEPREI-6909 Dataset

### ⚙️ Testbed Configuration
The experimental platform integrates:
- A variable frequency drive motor & coupling
- A Type-6909 deep groove ball bearing
- A non-linear hydraulic loading system to simulate the dynamic characteristics of realistic industrial transmission chains.

### 📊 Data Acquisition Specifications
- **Sampling Rate:** 10 kHz
- **Sample Duration:** 0.768 seconds per sample
- **Sensor:** Accelerometers

### 🏷️ Fault Modes and Physical Parameters
The dataset encompasses 1 healthy state and 6 complex fault states, including wire-cutting damage on races and structural cage fractures.

| Label | Fault Type | Location | Dimension / Severity |
| :---: | :--- | :--- | :--- |
| **0** | Normal | - | - |
| **1** | Groove | Inner Race | 0.4 mm |
| **2** | Groove | Inner Race | 0.6 mm (Severe) |
| **3** | Groove | Outer Race | 0.4 mm |
| **4** | Groove | Outer Race | 0.6 mm (Severe) |
| **5** | Pitting | Rolling Element | 0.4 mm |
| **6** | Fracture | Cage | Structural Fracture |

### 🌪️ Variable Operating Conditions
To construct severe domain shift scenarios, data acquisition followed a full-factorial experimental design spanning extreme speeds and heavy loads.

| Dataset Label | Radial Load Setting (N) | Rotational Speed Setting (rpm) | Total Conditions |
| :---: | :--- | :--- | :---: |
| **0, 1, 2, 3, 4, 5** | 320, 420, 820, 1220, 1620, 2020 | 300, 600, 900, 1200, 1500, 1800, 2100, 2400, 2700, 3000 | 60 |
| **6** *(Cage Fracture)* | 320 * | 300, 600, 900, 1200, 1500, 1800, 2100, 2400, 2700, 3000 | 10 |

*\*Note: Due to the high risk of catastrophic cage disintegration and safety hazards under heavy loads, Label 6 was safely restricted to the 320 N base load. This authentic physical constraint naturally provides an ideal testbed for evaluating diagnostic model robustness under severe **class imbalance** and **missing target labels** across domain transfers.*

## 🚀 Recommended Cross-Domain Evaluation Tasks
Researchers utilizing this dataset are encouraged to construct the following challenging transfer tasks:
1. **Single-Variable Shift:** Cross-speed (e.g., 300-1500 rpm $\leftrightarrow$ 1800-3000 rpm) and Cross-load (e.g., Light $\leftrightarrow$ Heavy).
2. **Compound Shift:** Simultaneous drastic changes in both speed and load (e.g., Low-speed Light-load $\to$ High-speed Heavy-load).
3. **Partial Domain Adaptation:** Evaluating model stability when the target domain structurally lacks specific fault modes (e.g., Label 6 under heavy loads).

---

## ✉️ Contact
If you have any questions regarding the dataset specifications or require early access for validation purposes, please feel free to open an issue or contact the authors.

*Download links and detailed data loading instructions will be updated here soon.*
