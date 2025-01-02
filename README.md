# Intrusion Detection System

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Data Collection and Preprocessing](#data-collection-and-preprocessing)
- [Modeling Approach](#modeling-approach)
- [Usage](#usage)
- [Results](#results)
- [Contributors](#contributors)
- [References](#references)

---

## Introduction
Intrusion Detection System (IDS) is a machine learning-based solution to combat cybersecurity threats posed by **Domain Generation Algorithms (DGAs)**. DGAs are widely used by malware to generate domain names, enabling communication with command and control servers. 

This project focuses on enhancing the detection of malicious DGAs in real-time network traffic by analyzing **48 features** derived from domain names, including lexical and statistical attributes such as entropy, pronounceability, and character frequencies.

---

## Features
- Real-time DNS traffic analysis using **Scapy**.
- Feature extraction of domain names including character-based and n-gram-based features.
- Classification of domain names using **Random Forest** and **Decision Tree** algorithms.
- Model trained on **Alexa's top 1-million domains** for benign data and **360 DGA** for malicious domains.

---

## Technologies Used
- **Programming Language**: Python
- **Libraries**: 
  - `Scapy` (for DNS traffic sniffing)
  - `NumPy` (for numerical operations)
  - `pandas` (for data manipulation)
  - `joblib` (for model persistence)
- **Algorithms**:
  - Decision Tree (CART algorithm)
  - Random Forest (ensemble learning)

---

## Data Collection and Preprocessing
### Data Sources:
- Benign domains: Alexa's top 1-million domains
- Malicious domains: 360 DGA NetLab Open Project

### Preprocessing Steps:
1. **Feature Extraction**: 
   - Extracted **48 features** based on character frequency, entropy, n-grams, and masked domain strings.
   - Example: `google.com` → Features include number of vowels, consonants, entropy, and n-gram statistics.
2. **Label Assignment**: 
   - `1` for malicious domains.
   - `0` for benign domains.

---

## Modeling Approach
### Decision Tree
- Binary tree construction using CART algorithm.
- Features split based on Gini impurity.

### Random Forest
- Combines multiple decision trees using **bagging**.
- Ensures diversity through bootstrap sampling and random feature selection.

### Training:
- Number of Trees: 20
- Max Depth: 10
- Features: 48
- Dataset split: 80% training, 20% testing.

---

## Usage
### Requirements:
- Python 3.x
- Required Libraries: `numpy`, `pandas`, `scikit-learn`, `scapy`, `joblib`

### Steps:
1. Clone this repository:
   ```bash
   git clone https://github.com/AiyyappanMR/Intrusion-Detection-System.git
   cd Intrusion-Detection-System
