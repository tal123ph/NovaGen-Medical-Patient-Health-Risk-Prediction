# 🏥 NovaGen Medical — Patient Health Risk Prediction

A machine learning project for **NovaGen Research Labs**, built to predict patient health risk (`Target`: high-risk vs. low-risk) from lifestyle and clinical features. Multiple classification models are trained and compared, with **Recall** prioritized as the key evaluation metric — since in a medical risk-screening context, failing to flag a genuinely high-risk patient (a false negative) is far more costly than a false alarm.

## 📊 Dataset

`novagen_dataset.csv` — 9,549 patient records with 22 features, including:

- **Vitals & clinical measures:** Age, BMI, Blood Pressure, Cholesterol, Glucose Level, Heart Rate
- **Lifestyle factors:** Sleep Hours, Exercise Hours, Water Intake, Stress Level, Smoking, Alcohol, Diet, Physical Activity
- **Health background:** Medical History, Allergies, Mental Health
- **Encoded categorical features:** Diet Type (Vegan/Vegetarian), Blood Group (A/B/AB/O)
- **Target:** Binary health risk label (fairly balanced — ~52% / 48% split)

## 📁 Project Structure

```
novagen-medical-risk-prediction/
│
├── novagen.ipynb            # Main modeling notebook
├── novagen2.ipynb           # Refined/alternate version of the pipeline
├── novagen_dataset.csv      # Patient dataset
└── README.md
```

## 🚀 Approach

1. **Data preparation** — train/test split with stratification to preserve target class balance, feature scaling with `StandardScaler`
2. **Baseline model** — Logistic Regression with L2 regularization
3. **Model comparison** — several classifiers trained and evaluated on the same split:
   - Logistic Regression (regularized)
   - K-Nearest Neighbors
   - Random Forest (ensemble)
   - Gradient Boosting (ensemble)
   - Voting Classifier (combining Logistic Regression, KNN, and Random Forest)
4. **Evaluation** — Accuracy, Recall, and classification reports compared across all models, with **Recall used as the primary decision metric** given the medical-risk context

## 📈 Results

| Model                | Recall |
|-----------------------|:------:|
| Logistic Regression   | 82.8%  |
| KNN                    | 88.3%  |
| Random Forest          | 95.8–96.1%  |
| Gradient Boosting      | 94.9–95.9%  |
| Voting Classifier      | 92–93%  |

**Random Forest emerged as the best-performing model**, achieving the highest recall — making it the recommended classifier for flagging high-risk patients in this dataset.

## 🛠️ Tech Stack

- **Python 3**
- **scikit-learn** — model training, preprocessing, and evaluation
- **Pandas / NumPy** — data handling
- **Matplotlib** — visualization
- **Jupyter Notebook**

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/tal123ph/novagen-medical-risk-prediction.git
   cd novagen-medical-risk-prediction
   ```

2. Install the required libraries:
   ```bash
   pip install pandas numpy scikit-learn matplotlib jupyter
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

4. Open `novagen.ipynb` and run the cells top to bottom.

## 🎯 Purpose

This project simulates a real-world healthcare screening scenario: comparing multiple classification algorithms not just on raw accuracy, but on the metric that actually matters for patient safety — recall. It reflects practical model-selection thinking for a high-stakes classification problem, and is part of my applied ML portfolio as an aspiring **AI Engineer / Data Scientist**.

## 👤 Author

**Muhammad Talha**
Data Analytics Student | Aspiring AI Engineer & Data Scientist
- GitHub: [@tal123ph](https://github.com/tal123ph)
- LinkedIn: [muhammad-talha12b](https://www.linkedin.com/in/muhammad-talha12b)

## 📄 License

This project is open source and available for learning purposes.
