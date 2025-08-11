# Intrusion Detection System (IDS) using XGBoost

## Project Overview

This repository contains a machine learning project for an **Intrusion Detection System (IDS)**. The system is designed to classify network sessions as either benign or malicious. The model is developed and validated using the `IDS.csv` dataset, which comprises a collection of network session logs with various features related to network activity.

---

## Dataset
The model is trained on a network session log dataset, `IDS.csv`, with a total of **9537 rows and 11 columns**. The dataset is structured for intrusion detection analysis, with the primary objective of classifying sessions as benign or malicious, as indicated by the binary target column `attack_detected`. The target column distribution shows a breakdown of **5273 benign sessions (0) and 4264 malicious sessions (1)**.

### Key Features
The dataset includes the following features:
* `session_id`: Unique identifier for each network session.
* `network_packet_size`: The number of network packets in the session.
* `protocol_type`: The network protocol used (e.g., TCP, UDP, ICMP).
* `login_attempts`: The number of login attempts during the session.
* `session_duration`: The duration of the session in seconds.
* `encryption_used`: The type of encryption applied (e.g., AES, DES, or None).
* `ip_reputation_score`: A score from 0 to 1 indicating the trustworthiness of the IP address.
* `failed_logins`: The number of failed login attempts.
* `browser_type`: The web browser used.
* `unusual_time_access`: A boolean (`0`/`1`) indicating if access occurred during abnormal hours.
* `attack_detected` (Target): A binary column where `1` indicates a malicious session and `0` indicates normal activity.

---

## Methodology and Model
The core of this IDS is an **XGBoost (Extreme Gradient Boosting)** classifier. The development process involved a comprehensive data exploration phase, followed by preprocessing steps such as **one-hot encoding for categorical features** and **scaling for numerical features**. The model's hyperparameters were tuned to achieve optimal performance.

### Performance Metrics
The model's performance was evaluated on a dedicated testing set, yielding the following results:
* **Accuracy:** 0.9984
* **Precision:** 0.9995
* **Recall:** 0.9961
* **F1 Score:** 0.9978

These metrics demonstrate the model's high effectiveness in accurately identifying malicious network sessions while maintaining a low rate of false positives and false negatives.

---

## Installation
To set up and run this project, you will need to install the required Python libraries. This can be done using `pip`:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
