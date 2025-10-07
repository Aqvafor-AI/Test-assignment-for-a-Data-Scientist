# Test Assignment (S7): Sales Forecasting and Advertising Impact

📊 **Presentation with results:** [https://gamma.app/docs/-w0aksas0rq5lwvj?mode=doc](https://gamma.app/docs/-w0aksas0rq5lwvj?mode=doc)

---

The Jupyter notebook `Тестовое_задание_на_позицию_Data_Scientist.ipynb` solves a sales forecasting task with advertising effects using the provided CSV files.

## 📦 Data
Data are located under `data/` inside **`data.zip`** and include:
- `sales_train.csv` — historical sales by store and date;
- `advert_train.csv` — advertising activity in the training period;
- `advert_test.csv` — advertising schedule for the test period;
- `deploy_example.csv` — required submission format example.

## 🧰 Libraries
`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `statsmodels`, `zipfile`, `os` (and `google.colab.files` upload widget when running in Colab).

## 🔄 Workflow (as in the notebook)
1. Upload and unzip `data.zip` (Colab widget + `zipfile.ZipFile`).
2. Read CSVs and parse dates (`parse_dates=['date']`).
3. Convert to **long format**: `sales` and `advert_*` via `melt` → `date | store_id | value`.
4. Merge & clean: join on `store_id`, `date`; fill `advert` with zeros; drop missing `sales`.
5. Feature engineering: `year`, `month`, `day`, weekday dummies (`dow_*`).
6. Baseline visualization: weekly aggregation and plot “Total Weekly Sales”.
7. Models: **Linear Regression**, **Ridge**, **RandomForest**, **GradientBoosting**; time‑series CV (`TimeSeriesSplit`), train metrics `R²`/`RMSE`.
8. Test forecasting: build `test` from `advert_test` (melt, features, weekday dummies), predict and compare models on plots.
9. Export: pivot back to wide and save **`deploy_test_gb.csv`** (forecast from `GradientBoosting`).

## 📈 Advertising impact analysis (as in the notebook)
- `statsmodels` OLS on features (`advert`, calendar features, `dow_*`) with coefficient table and p‑values.  
- 95% CI errorbar plot for the `advert` coefficient.  
- **SARIMAX** with exogenous `advert` on weekly sums: `summary()` and diagnostics.

## 🗂️ Repository structure (actual)
```
├─ data/
│  └─ data.zip
│      ├─ sales_train.csv
│      ├─ advert_train.csv
│      ├─ advert_test.csv
│      └─ deploy_example.csv
│
├─ Тестовое_задание_на_позицию_Data_Scientist.ipynb
├─ S7.pdf
└─ README.md
```

## 📝 Output Data
- `deploy_test_gb.csv` — forecast saved from the notebook.
