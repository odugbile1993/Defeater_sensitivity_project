# Beyond Fidelity: Defeater-Sensitivity in the Epistemic Evaluation of Post-Hoc AI Explanations

> A novel framework for evaluating whether AI explanations remain trustworthy when the evidence supporting predictions changes.

---

## 📖 Overview

Traditional Explainable Artificial Intelligence (XAI) evaluation focuses on descriptive metrics such as **fidelity**, **stability**, and **consistency**. While these metrics measure how accurately explanations reflect model behaviour, they do not assess whether explanations remain trustworthy when the evidential basis supporting predictions changes.

This repository accompanies the research paper:

**Beyond Fidelity: Defeater-Sensitivity in the Epistemic Evaluation of Post-Hoc AI Explanations**

The paper introduces **Defeater-Sensitivity**, a novel evaluation framework that measures the responsiveness of post-hoc explanations under controlled evidential perturbations.

---

## 🎯 Research Question

Most XAI methods answer:

> **Why did the model make this prediction?**

This research asks:

> **Does the explanation remain trustworthy when the evidence supporting the prediction changes?**

To answer this question, we introduce two new metrics:

* **Explanation Attribution Drift (EAD)**
* **Defeater-Sensitivity Index (DSI)**

---

## 🧠 Proposed Framework

The proposed framework evaluates explanation robustness through the following workflow:

1. Train a predictive model.
2. Generate baseline SHAP explanations.
3. Introduce controlled evidential perturbations.
4. Regenerate SHAP explanations.
5. Compute Explanation Attribution Drift (EAD).
6. Aggregate attribution drift into the Defeater-Sensitivity Index (DSI).

Unlike conventional XAI evaluation, the predictive model remains unchanged throughout the experiment, allowing explanation behaviour to be evaluated independently of model retraining.

---

## 📊 Dataset

**Give Me Some Credit**

* Total records: **104,805**
* Predictive features: **10**
* Target variable: **SeriousDlqin2yrs**
* Train/Test split: **80:20**
* Missing values handled using **median imputation**

---

## 🤖 Model

* Gradient Boosting Classifier
* TreeSHAP
* Scikit-learn
* SHAP
* Python

---

## 🧪 Experimental Scenarios

### Scenario A – Income Defeater

* MonthlyIncome reduced by **40%**
* Borrowers affected: **31,442**

### Scenario B – Debt Defeater

* DebtRatio increased by **40%**
* Borrowers affected: **31,442**

---

## 📈 Results

### Model Performance

| Metric    |      Value |
| --------- | ---------: |
| Accuracy  | **0.9384** |
| Precision | **0.6102** |
| Recall    | **0.1971** |
| F1-score  | **0.2980** |
| ROC-AUC   | **0.8661** |

### Defeater-Sensitivity Results

| Scenario        |          DSI |
| --------------- | -----------: |
| Income Defeater | **0.001817** |
| Debt Defeater   | **0.000772** |

The experiments demonstrate that different evidential perturbations produce different levels of explanation attribution drift, suggesting that explanation quality should be evaluated not only by descriptive agreement with model predictions but also by responsiveness to changing evidence.

---

## 📂 Repository Structure

```text
.
├── data/
│   └── Give Me Some Credit dataset
│
├── notebooks/
│   └── defeater_sensitivity.ipynb
│
├── figures/
│   ├── framework.png
│   ├── class_distribution.png
│   ├── baseline_shap_summary.png
│   ├── income_defeater.png
│   ├── debt_defeater.png
│   └── dsi_comparison.png
│
├── paper/
│   └── Beyond_Fidelity_Defeater_Sensitivity.pdf
│
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook
```

---

## 📚 Citation

If you use this work in your research, please cite:

```bibtex
@article{odugbile2026defeatersensitivity,
  title={Beyond Fidelity: Defeater-Sensitivity in the Epistemic Evaluation of Post-Hoc AI Explanations},
  author={Odugbile, Ayodele},
  year={2026},
  note={Submitted to the 10th International Conference on Interdisciplinary Research on Computer Science, Psychology and Education (ICICPE 2026)}
}
```

---

## 👤 Author

**Ayodele Odugbile**

Independent Researcher — Financial Machine Learning, Explainable AI, and Trustworthy AI

📍 Nigeria

---

## 🔮 Future Work

Future extensions of this research include:

* XGBoost
* Random Forest
* Neural Networks
* LIME
* Counterfactual Explanations
* Integrated Gradients
* Healthcare applications
* Fraud detection
* Financial risk modelling

---

## 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for details.
