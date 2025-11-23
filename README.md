# 🛒 User Behavior & A/A/B Testing Analysis

## 📌 Project Overview

This project is part of **Sprint 11** for a fictional food delivery startup. The primary goals are:

1. Analyze user behavior within the company’s mobile app using event logs.
2. Understand conversion drop-offs through a sales funnel.
3. Evaluate the results of an **A/A/B experiment** testing a new font style.

---

## 📂 Dataset

The dataset contains event logs from the mobile app:
- **File**: `logs_exp_us.csv`
- Each row represents a user action or event.
- Columns:
  - `EventName`: the event type
  - `DeviceIDHash`: anonymized user ID
  - `EventTimestamp`: time of the event (UNIX format)
  - `ExpId`: experiment group — 246 and 247 are control (A/A), 248 is test (B)

📎 Sample dataset available [here](sandbox:/mnt/data/logs_exp_us.csv)

---

## 🧪 Methodology

### Step 1: Data Cleaning
- Converted timestamps to datetime
- Filtered out incomplete logging periods (used data from **2019-07-29** onward)

### Step 2: Funnel Analysis
Events analyzed:
- `MainScreenAppear`
- `OffersScreenAppear`
- `CartScreenAppear`
- `PaymentScreenSuccessful`

We calculated:
- Number of users per step
- Conversion rates between each step

### Step 3: A/A Test (Validation)
- Compared control groups 246 and 247
- Verified statistical similarity using **Chi-squared tests**

### Step 4: A/B Test (Font Change)
- Compared group 248 (new font) with 246 and 247
- Tested if font change impacted user behavior

---

## 📊 Results

### 🛍 Funnel Conversion Rates
| Funnel Step              | Users  | Conversion from Previous Step |
|--------------------------|--------|-------------------------------|
| MainScreenAppear         | 7439   | —                             |
| OffersScreenAppear       | 4613   | 62%                           |
| CartScreenAppear         | 3749   | 81%                           |
| PaymentScreenSuccessful  | 3547   | 95%                           |

### 🔍 A/A Test Result
- No significant differences between control groups → ✅ Test setup is valid

### 🧪 A/B Test Result
- No significant differences between test and control groups
- Conclusion: **New font has no negative (or positive) effect**

---

## ✅ Conclusion

- The sales funnel is healthy, with most drop-off at the start (Offers screen)
- The experimental setup passed validation (A/A)
- The new font is safe to implement
- No user confusion or conversion loss was observed

---

## 💻 Tools Used

- Python
- Pandas
- Matplotlib
- SciPy (Chi-squared tests)
- Jupyter Notebook

---

## 📎 Author

Project built by Eric Moraes, part of a portfolio to demonstrate:
- Exploratory Data Analysis (EDA)
- A/B Testing Methodology
- Data Visualization & Interpretation
