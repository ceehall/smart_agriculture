# 🌾 Smart Agriculture — Crop Irrigation Classification

A machine learning project that predicts whether a crop requires irrigation based on environmental and soil conditions. Built using Python and scikit-learn on a dataset of 16,411 crop records.

---

## 📌 Problem Statement

Agriculture accounts for approximately 70% of global freshwater consumption, yet a significant portion of this water is lost to inefficient irrigation practices. Farmers often rely on intuition or fixed schedules to decide when to irrigate, without accounting for real-time environmental conditions such as soil moisture, temperature, and humidity. This leads to either over-irrigation — wasting water and increasing costs — or under-irrigation, which stunts crop growth and reduces yield.

This project addresses that gap by developing a machine learning classification model capable of predicting whether a crop requires irrigation based on measurable environmental and soil conditions. Using a dataset of 16,411 crop records spanning multiple soil types, seedling growth stages, and climate variables, the goal is to build a reliable, automated decision-support tool that can reduce water waste and improve crop outcomes in smart farming systems.

---


## 📊 Dataset

- **Records:** 16,411 crop samples (after deduplication)
- **Source:** `cropdata_updated.csv`

| Feature | Description |
|---|---|
| `crop_name` | Crop identifier (categorical) |
| `soil_type` | Type of soil (e.g., Black Soil, Red Soil) |
| `seedling_stage` | Growth stage of the crop (e.g., Germination) |
| `moi` | Moisture Index — soil moisture at time of collection |
| `temp` | Ambient temperature in °C |
| `humidity` | Relative humidity (%) |
| `result` | **Target** — 1 = irrigation needed, 0 = not needed |

---

## 🔁 Project Workflow

```
Load Data → Clean & EDA → Encode Features → Train/Test Split
    → Baseline Models → Hyperparameter Tuning → Evaluation → Pipeline
```

---

## 🧪 Models Trained

| Model | Tuned |
|---|---|
| Logistic Regression | ✅ |
| Decision Tree | ✅ |
| K-Nearest Neighbors | ✅ |
| Random Forest | ✅ |
| Gradient Boosting | ✅ |
| Support Vector Machine (SVM) | ✅ |

Hyperparameter tuning was performed using `RandomizedSearchCV` with 5-fold cross-validation.

---

## 📈 Evaluation Metrics

- Accuracy (train vs. test)
- Confusion Matrix
- ROC-AUC Score
- ROC Curve (all models plotted)

The **Gradient Boosting Classifier** was selected as the best-performing model and deployed via a scikit-learn `Pipeline`.

---

## 🗂️ Project Structure

```
├── Smart_Agriculture_Classification.ipynb   # Main notebook
├── cropdata_updated.csv                     # Dataset
└── README.md
```

---

## ⚙️ Requirements

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/your-username/smart-agriculture-classification.git
cd smart-agriculture-classification
jupyter notebook Smart_Agriculture_Classification.ipynb
```

> Make sure `cropdata_updated.csv` is in the same directory as the notebook.

---

## 💡 Potential Applications

- **Automated irrigation systems** — integrate with IoT sensors for real-time decisions
- **Agricultural research** — study how climate and soil affect crop growth stages
- **Smart farming dashboards** — alert farmers when irrigation thresholds are met

---

## 🙋 Author

**Your Name**
[GitHub](https://github.com/your-username) · [LinkedIn](https://linkedin.com/in/your-profile)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
