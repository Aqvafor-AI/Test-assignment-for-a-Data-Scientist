# Data Scientist Test Task: Sales Forecasting and Advertising Impact

📊 **Presentation with results:** [https://gamma.app/docs/-w0aksas0rq5lwvj?mode=doc](https://gamma.app/docs/-w0aksas0rq5lwvj?mode=doc)

---

The Jupyter notebook `s7-data-scientist-test.ipynb` implements a solution for a **Data Scientist test assignment** focused on forecasting sales and analyzing the impact of advertising campaigns.

## 🎯 Objective
1. **Forecast sales** for the period **2017–2018**, using the known advertising schedule.  
2. **Analyze the impact** of advertising campaigns on store sales.

## 📦 Data
All source data is stored in the `data/` folder inside the **`data.zip`** archive.  
The archive includes:

| File | Description |
|------|--------------|
| `sales_train.csv` | Historical daily sales (2008–2017) |
| `advert_train.csv` | Advertising campaign schedule for the training period |
| `advert_test.csv` | Advertising schedule for the test period |
| `deploy_example.csv` | Example format of the required forecast file |

## 🧰 Libraries
- `pandas`, `numpy` — data processing  
- `matplotlib`, `seaborn` — visualization  
- `scikit-learn` — regression models and metrics  
- `statsmodels`, `xgboost`  — forecasting methods  
- `datetime` — time feature generation  

## 🧩 Workflow
1. **Data preprocessing** — read CSVs, merge sales and advertising data, create time features.  
2. **Advertising impact analysis** — visualize and compare sales during promo and non-promo periods.  
3. **Forecasting** — train and evaluate models (MAE, RMSE), generate forecast for 2017–2018.  
4. **Export results** — save final forecast as `deploy_test.csv` (same format as `deploy_example.csv`).  

## 📊 Results
- Conducted an analysis of how advertising affects sales.  
- Built a sales forecast for 2017–2018.  
- Prepared the final `deploy_test.csv` file.  
- All visuals and conclusions are available in the [presentation](https://gamma.app/docs/-w0aksas0rq5lwvj?mode=doc).  
