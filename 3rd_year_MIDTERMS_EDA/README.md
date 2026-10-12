# DS311: Exploratory Data Analysis — Midterm Lab Exam & PIT Dataset
## Group 4: Environment and Nature | Subcategory: Inland Water Resources

### Primary Selected Dataset: Wastewater Generation and Treatment

This directory hosts the primary curated dataset for the **DS311 Performance Innovative Task (PIT: Data Poster)** and **Midterm Lab Exam Report** at USTP.

---

### Available Files
1. **`Wastewater generation and treatment.csv`**: Raw UN Statistics Division dataset exported from Kaggle (`ruchi798/global-environmental-indicators`).
2. **`Wastewater_generation_and_treatment_clean.csv`**: Pre-sanitized version with missing value tokens (`…`, `..`) parsed to `NaN`, clean snake_case column headers, and explicit numeric casting.
3. **`Wastewater generation and treatment.xlsx`**: Raw Excel format.

---

### Project Metadata
* **Poster Title:** `Analysing the growth of Municipal Wastewater Generation and its Burden on Urban Treatment Infrastructure`
* **Domain:** Group 4 — Environment and Nature
* **Business Question:**  
  > *"As municipal wastewater generation grows due to rapid urban expansion, does urban treatment plant capacity expand at parity, or does an escalating 70% infrastructure deficit emerge that justifies private capital expenditure (CAPEX) and Public-Private Partnerships (PPPs) in wastewater utility facilities?"*
* **The Two Numerical Variables (Strictly 2 for Bivariate Analysis):**
  * **Independent Variable ($X$):** `total_wastewater_generated_1k_m3_day` ($1,000\text{ m}^3/\text{day}$)
  * **Dependent Variable ($Y$):** `urban_wastewater_treated_1k_m3_day` ($1,000\text{ m}^3/\text{day}$)

---

### Key Empirical Metrics
* **Sample Size:** $N = 24$ complete reporting pairs (79 countries reporting in the table).
* **Pearson Correlation ($r$):** $0.9058$ ($p = 1.15 \times 10^{-9}$, $R^2 = 82.04\%$)
* **Spearman Rank Correlation ($\rho$):** $0.8887$ ($p = 6.63 \times 10^{-9}$)
* **OLS Regression Fit:**
  $$\text{urban\_treated} = 338.49 + 0.2964 \times \text{total\_generated}$$
* **Core Discovery:** The slope of $0.2964$ proves that for every $1,000\text{ m}^3$ of wastewater generated, **only $\approx 296\text{ m}^3$ is treated in urban facilities**, leaving a **$\approx 70\%$ untreated/unmanaged infrastructure deficit gap**.

---

### Direct Google Colab One-Liner

To load this dataset directly inside Google Colab without manual file uploading:

```python
import pandas as pd

# Option 1: Load pre-cleaned version (Recommended)
url_clean = "https://raw.githubusercontent.com/Troge-dev/datasets/main/3rd_year_MIDTERMS_EDA/Wastewater_generation_and_treatment_clean.csv"
df = pd.read_csv(url_clean)

# Option 2: Load raw UN version
url_raw = "https://raw.githubusercontent.com/Troge-dev/datasets/main/3rd_year_MIDTERMS_EDA/Wastewater%20generation%20and%20treatment.csv"
df_raw = pd.read_csv(url_raw, na_values=['…', '...', '..', '', ' '])

print("Shape:", df.shape)
df.head()
```
