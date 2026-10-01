# 🐼 Pandas Assignment

A Jupyter Notebook covering core **NumPy** and **Pandas** concepts: output prediction, code debugging, edge cases, and a real-world data-cleaning scenario.

**Name:** Ganta Tejaswini
**Roll No:** 238T1A0541
**Notebook:** [`Tejaswini_pandas1.ipynb`](./Tejaswini_pandas1.ipynb)

---

## 📚 Contents

### Section A – Output Prediction
Predicting the output of short code snippets and explaining the result.

| Q | Topic | Key concept |
|---|-------|-------------|
| 1 | Array operations & vectorization | NumPy array vs. Pandas Series (element-wise multiplication, index) |
| 2 | Boolean filtering | `df[df['Marks'] >= 65]` |
| 3 | Descriptive statistics | `mean()`, `max()`, `median()` |
| 4 | Group-wise analysis | `groupby()` with `mean()` |
| 5 | Positive correlation | `Series.corr()` |
| 6 | Negative correlation | Meaning of the sign of the correlation coefficient |

### Section B – Code Correction
Finding and fixing bugs in given code.

| Q | Topic | Fix |
|---|-------|-----|
| 1 | CSV reading | Remove `header=None` so the header row is not read as data |
| 2 | Data analysis | Use `sort_values('Salary', ascending=False)` for the top 5 salaries |
| 3 | Cleaning data | Assign `fillna()` result back to the column |
| 4 | Correlation | Use `df['Hours'].corr(df['Marks'])` instead of the wrong `df.corr(...)` call |

### Section C – Edge Cases
- **Broadcasting:** adding arrays of shape `(3, 1)` and `(1, 3)` gives a `(3, 3)` result.
- **CSV edge cases:** quoted commas, missing values, and mixed date formats, and how incorrect parsing affects a DataFrame.
- **Salary outlier:** why the median represents a typical salary better than the mean when an extreme value is present.

### Section D – Scenario: Student Assessment Data Cleaning
A step-by-step cleaning pipeline on a messy student assessment dataset:

1. Load and inspect the data (`head()`, `info()`, `isnull().sum()`)
2. Standardize department names (`IT`, `it`, `I.T.` → `IT`; `finance` → `Finance`)
3. Remove exact duplicate records (`drop_duplicates()`)
4. Convert `Marks` to numeric (handles `"88 marks"`, `"Absent"`, `"NA"`, blanks) using `pd.to_numeric(..., errors="coerce")`
5. Investigate missing marks (absent vs. not entered)
6. Flag marks outside the valid range 0–100 (e.g. `105`)
7. Report the cleaned DataFrame and a summary

**Cleaning summary**

| Metric | Result |
|--------|--------|
| Records removed | 1 (duplicate of `S102`) |
| Missing marks remaining | 4 |
| Invalid marks identified | 1 (`105`) |

---

## 🛠️ Concepts & Functions Used

`pd.Series` · `pd.DataFrame` · `np.array` · boolean indexing · `groupby()` · `mean()` · `median()` · `max()` · `corr()` · `sort_values()` · `head()` · `fillna()` · `replace()` · `drop_duplicates()` · `to_numeric()` · `isnull()` · `read_csv()` · NumPy broadcasting

---

## ▶️ How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/Tejaswini0541/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. Install the requirements
   ```bash
   pip install numpy pandas jupyter
   ```
3. Launch the notebook
   ```bash
   jupyter notebook Tejaswini_pandas1.ipynb
   ```

> **Note:** Section D reads `student_assessment_dirty.csv`. Place this file in the same folder as the notebook before running those cells.

---

## 🧰 Tech Stack

- Python 3
- Pandas
- NumPy
- Jupyter Notebook

---

## 📁 File Structure

```text
<your-repo-name>/
├── Tejaswini_pandas1.ipynb        # Main notebook (Sections A–D)
├── student_assessment_dirty.csv   # Dataset used in Section D
└── README.md                      # Project documentation
```
