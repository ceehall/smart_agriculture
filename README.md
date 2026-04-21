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
## Conclusion

Six classification models were trained and evaluated: Logistic Regression, Decision Tree, K-Nearest Neighbors, Random Forest, Support Vector Machine, and Gradient Boosting. All models underwent hyperparameter tuning using Randomized Search with 5-fold cross-validation to identify optimal configurations.

After evaluation using accuracy scores, confusion matrices, and ROC-AUC scores, the **Gradient Boosting Classifier** consistently outperformed the other models across all metrics. It demonstrated the highest AUC score and the best balance between precision and recall — meaning it correctly identified crops that needed irrigation while minimising false alarms. The model was subsequently packaged into a scikit-learn Pipeline alongside One-Hot Encoding to ensure clean, reproducible predictions on new data.

Key findings from the analysis include:

- Environmental features — particularly moisture index (MOI), temperature, and humidity — were the strongest predictors of irrigation need.
- Soil type and seedling stage added meaningful signal, confirming that a one-size-fits-all irrigation schedule is insufficient across different crop conditions.
- The target variable required cleaning prior to modelling, as a value of `2` was incorrectly encoded and needed to be remapped to `0` to maintain binary classification integrity.
- Class distribution was inspected and found to be reasonably balanced, reducing the risk of model bias toward the majority class.

## Recommendation

Based on the findings of this project, the following recommendations are made:

**1. Deploy Gradient Boosting as the core prediction engine.**
The tuned Gradient Boosting model achieved the best performance and should be the model of choice for any production or pilot deployment. It is robust, handles complex feature interactions well, and generalises effectively to unseen data.

**2. Integrate the model into IoT-enabled irrigation systems.**
The model takes readily available sensor inputs — moisture, temperature, humidity — making it highly compatible with existing smart farming infrastructure. Embedding the model into an IoT pipeline would enable real-time, automated irrigation decisions without human intervention.

**3. Validate on local and regional farm data before full deployment.**
The current model was trained on a single dataset. Before scaling, it should be retested and potentially retrained on data collected from the specific farms or regions where it will be used, as soil types and climate conditions vary significantly by geography.

**4. Expand the feature set in future iterations.**
Incorporating additional variables such as rainfall forecasts, crop age, fertiliser application history, and historical yield data could further improve prediction accuracy and provide richer decision support.

**5. Monitor and retrain the model periodically.**
Environmental patterns shift with seasons and climate change. A model retraining schedule — quarterly or seasonally — should be established to ensure the system remains accurate over time.

**6. Build a simple farmer-facing dashboard.**
The technical model should be abstracted behind a simple interface — a mobile app or SMS alert system — that communicates recommendations in plain language (e.g., *"Irrigate your maize crop today"*), making the tool accessible to farmers regardless of technical literacy.


## 🙋 Authors

**GitHub Profiles**
(https://github.com/gideoncobbina)
(https://github.com/sandra620)
(https://github.com/Wesoamo-78)
(https://github.com/abissath)
(https://github.com/ceehall)

**LinkedIn Profiles**
(https://linkedin.com/in/gideon-cobbina)
(https://linkedin.com/in/sandraosei)
(https://linkedin.com/in/joycelyntigawoti)
(https://linkedin.com/in/michael-abissath)
(https://linkedin.com/in/cameron-harley)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

