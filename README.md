# 🏦 Stock Pledge Financing Default Prediction & Risk Dashboard

## 📌 Business Context
In the banking and financial sector, predicting corporate client defaults on stock-pledged loans is critical for mitigating Non-Performing Loans (NPL) and maintaining institutional liquidity. 

This project tackles a highly imbalanced financial dataset to predict loan defaults. Rather than relying on a single black-box algorithm, this project presents a rigorous comparative analysis between traditional state-of-the-art tree-based models and modern Deep Learning architectures tailored for tabular data.

## 🚀 Key Highlights & Engineering Rigor
- Algorithm Showdown: Benchmarked LightGBM, XGBoost, and TabNet (Attention-based Deep Learning for Tabular Data) to find the optimal balance between speed, scalability, and predictive power.
- Enterprise Grade Reproducibility: Implemented a global seed_everything architecture across PyTorch, NumPy, and Python environments to ensure 100% deterministic and reproducible deep learning results.
- Business Centric Evaluation: Transitioned from standard AUC metrics to log loss optimization, prioritizing the confidence of probability predictions—a crucial factor for banking risk-scoring systems.
- Robust Preprocessing: Handled extreme financial outliers via median imputation and utilized standardization specifically optimized for Neural Network convergence.

## 🧰 Tech Stack
- Data Manipulation: pandas, numpy
- Machine Learning: scikit learn, LightGBM, XGBoost
- Deep Learning: PyTorch, pytorch-tabnet
- Visualization & BI : matplotlib, seaborn , Power BI, DAX 

## 📊 Model Performance & Evaluation

While all models achieved exceptional AUC scores in local validation, the final selection was strictly based on **Log Loss** to ensure the model outputs reliable probability scores for risk threshold tuning.

| Rank | Model | ROC-AUC Score | Log Loss | Conclusion |
| 🥇 | LightGBM | 1.0000 |  0.0034] | Best fit, highly efficient in handling noisy financial ratios with extreme leaf-wise gradient boosting. |
| 🥈 | XGBoost | 1.0000 | 0.0235 | Excellent, but slightly more conservative in probability confidence compared to LightGBM. |
| 🥉 | TabNet | 0.8923 | 0.3132  | Showed promise but required significantly larger datasets and extensive hyperparameter tuning to avoid overfitting. |

### Visual Insights

- **Confusion Matrices:** Demonstrates the models' precision in capturing True Positives (Actual Defaults) vs avoiding False Positives.
<img width="476" height="321" alt="image" src="https://github.com/user-attachments/assets/ce562dc8-8bd4-439e-81d1-dec0071bc907" />

<img width="470" height="323" alt="image" src="https://github.com/user-attachments/assets/1a3e2d71-3b61-4256-9fd9-dd3dd12e204d" />

<img width="465" height="321" alt="image" src="https://github.com/user-attachments/assets/89b721e9-77b7-46af-ba28-f3423cb6eb0c" />


- Learning Curves: Validation vs. Training Loss curves proving that the final models converged healthily without severe overfitting.

  <img width="500" height="322" alt="image" src="https://github.com/user-attachments/assets/c30ab0d6-3a10-4d19-a275-a44b17a5109c" />

  <img width="510" height="325" alt="image" src="https://github.com/user-attachments/assets/9e21ef75-2f2b-48f7-8818-070b1370c8be" />

  <img width="503" height="322" alt="image" src="https://github.com/user-attachments/assets/c32aab19-606f-49b8-9fa9-7acf357b0df5" />

## 📈 Interactive Power BI Risk Dashboard

To make the LightGBM predictions actionable for non technical stakeholders, the test set probability scores and feature importance weights were integrated into a two page Power BI report:

### 1. Overview Page
* **Portfolio KPI Cards:** Tracks total evaluated companies, baseline default count, and overall portfolio default rate.
* **Model Explainability:** Visualizes LightGBM feature importance so analysts can see which financial ratios drive default risk the most.
* **Company Risk Breakdown:** Displays individual stock codes alongside their predicted risk status.

<img width="1422" height="748" alt="image" src="https://github.com/user-attachments/assets/6d35d45d-3d3f-40b2-949c-60430f042eb4" />

### 2. Risk Simulation (Threshold Simulator)
* **Dynamic Risk Threshold Slicer:** Built using a disconnected Power BI *What-If Parameter* (`0.00` – `1.00`) paired with custom DAX measures (`CALCULATE`, `FILTER`, `SELECTEDVALUE`).
* **Real-Time Stress Testing:** Moving the threshold slider immediately recalculates the **Simulated Default Count**, **Simulated Default Rate**, and filters the high-risk company watchlist.
 * *At baseline threshold(`0.50`):* Flags **77 companies** (**20.48%** simulated default rate) as High Risk.
 * *Under stricter risk appetite (e.g., `0.30`):* Automatically expands the watchlist to capture borderline companies before default occurs.

<img width="1076" height="697" alt="image" src="https://github.com/user-attachments/assets/f540ccf2-6fbb-41cb-b491-10187756f107" />

💻 How to Reproduce
To run this pipeline locally and reproduce the exact results:

1. Clone this repository:
   ```bash
   git clone [https://github.com/](https://github.com/)[FarrellValentino]/[Stock Pledge Financing Default Prediction].git

2. Install the required dependecies:
     ```bash
     pip install -r requirements.txt
   
3. Run the notebook 

To explore the Power BI Dashboard :
Download and open `Stock Pledge Financing Risk Dashboard.pbix` using **Microsoft Power BI Desktop** to interact with the `Risk Threshold` slider
   
