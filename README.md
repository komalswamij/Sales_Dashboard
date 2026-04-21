# 📊 Business Sales Performance Dashboard

> Interactive Business Sales Performance Dashboard built on 1,500 Indian retail transactions across 19 states. 8 dynamic charts, KPI cards, cross-filtering, dark/light mode, key insights & business recommendations. Built with Python (data prep) + HTML/CSS/JavaScript + Chart.js.

<div align="center">

[![Live Demo](https://img.shields.io/badge/🔗%20Live%20Demo-Visit%20Dashboard-blue?style=for-the-badge)](https://yourusername.github.io/sales-dashboard)
[![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-222?style=for-the-badge&logo=github)](https://yourusername.github.io/sales-dashboard)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

![Dashboard Preview](preview.png)

---

## 📌 Table of Contents

- [Problem Statement](#-problem-statement)
- [Live Demo](#-live-demo)
- [Dataset](#-dataset)
- [Data Preparation](#-data-preparation)
- [Dashboard Features](#-dashboard-features)
- [KPI Metrics](#-kpi-metrics)
- [Charts & Visualisations](#-charts--visualisations)
- [Key Insights](#-key-insights)
- [Business Recommendations](#-business-recommendations)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [How to Run Locally](#-how-to-run-locally)
- [License](#-license)

---

## 🎯 Problem Statement

A multi-category retail business operating across **19 Indian states** was experiencing **inconsistent profitability** despite rising order volumes. The company sells across three categories — Electronics, Clothing, and Furniture — through five payment channels, but lacked a unified view of which products, regions, and customers were actually driving sustainable margin.

Without this visibility, leadership could not:
- Distinguish high-revenue-but-low-margin products from true profit contributors
- Allocate marketing budgets effectively across regions
- Rationalise the product catalogue by removing loss-making SKUs
- Prioritise geographic expansion based on real performance data

This dashboard provides a **360-degree performance view** across all dimensions — enabling data-driven decisions at every level of the organisation.

---

## 🔗 Live Demo

👉 **[View the Live Dashboard](https://yourusername.github.io/sales-dashboard)**

Features to try:
- Toggle **Dark / Light mode** using the button in the top-right corner
- Apply **filters** by Month, Category, State, or Payment Mode — all 8 charts update instantly
- **Hover** over any chart element for detailed tooltips
- Scroll down to read the written **Key Insights** and **Business Recommendations**

---

## 📂 Dataset

| File | Rows | Columns | Description |
|------|------|---------|-------------|
| `Orders.csv` | 500 | 5 | Order ID, Order Date, Customer Name, State, City |
| `Details.csv` | 1,500 | 7 | Order ID, Amount, Profit, Quantity, Category, Sub-Category, Payment Mode |

- **Merged on:** `Order ID`
- **Final dataset:** 1,500 enriched line items across 500 unique orders
- **Time period:** Full Year 2018
- **Geography:** 19 Indian states, multiple cities

---

## 🧹 Data Preparation

All data preparation was done in Python before building the dashboard.

### Cleaning Steps
```python
# 1. Handled missing values across both files
# 2. Removed duplicate records
# 3. Standardised state names (e.g. stripped trailing spaces from "Kerala ")
# 4. Parsed Order Date strings to datetime objects
# 5. Merged Orders + Details on Order ID (1:many join)
```

### Derived Fields Created
```python
# Temporal fields from Order Date
Month       = dt.month                         # 1–12
MonthName   = dt.strftime('%b')                # Jan, Feb ... Dec
Quarter     = f'Q{(dt.month - 1) // 3 + 1}'  # Q1, Q2, Q3, Q4
Year        = dt.year                          # 2018

# Business metrics
AOV              = Total Revenue / Total Orders
Profit Margin(%) = (Total Profit / Total Revenue) × 100
```

---

## ✨ Dashboard Features

| Feature | Details |
|---------|---------|
| 🎛️ **Dynamic Filters** | Month · Category · State · Payment Mode — all visuals update in real time |
| 🔄 **Cross-filtering** | Every chart responds to every filter combination simultaneously |
| 🌙 **Dark / Light Mode** | Full theme switch including chart palettes, backgrounds, and typography |
| 💬 **Hover Tooltips** | Formatted ₹ values on every data point across all charts |
| 📝 **Problem Statement** | Business context panel for stakeholder alignment |
| 💡 **Key Insights** | 6 colour-coded, evidence-backed written findings |
| 📋 **Recommendations** | 6 prioritised strategic actions with implementation tags |
| ♻️ **Reset Filters** | One-click return to full dataset view |
| 📱 **Responsive Layout** | Adapts cleanly across screen sizes |
| ⚡ **Zero Dependencies** | Single HTML file — no backend, no database, no build step |

---

## 📈 KPI Metrics

| Metric | Full Year 2018 |
|--------|---------------|
| 💰 Total Revenue | ₹4,37,771 |
| 📊 Total Profit | ₹36,963 |
| 🛒 Total Orders | 500 |
| 📦 Total Qty Sold | 5,615 units |
| 🎯 Average Order Value | ₹875.54 |
| 📉 Profit Margin | 8.44% |

---

## 📊 Charts & Visualisations

| # | Chart | Type | Description |
|---|-------|------|-------------|
| 1 | Monthly Revenue & Profit Trend | Bar + Line (combo) | Revenue bars vs profit/loss line across 12 months |
| 2 | Revenue by Category | Grouped Bar | Electronics vs Clothing vs Furniture — revenue & profit |
| 3 | Payment Mode Mix | Doughnut | Revenue share across COD, Credit Card, UPI, EMI, Debit Card |
| 4 | Quarterly Performance | Grouped Bar | Q1–Q4 revenue and profit comparison |
| 5 | Sub-category Performance | Horizontal Bar | Top 10 sub-categories by revenue — loss-makers in red |
| 6 | Top 10 Customers | Ranked List | Customer revenue ranking with proportional bar indicators |
| 7 | State-wise Revenue & Profit | Grouped Bar | Top 10 states — profit/loss colour-coded |

**Colour convention:**
- 🔵 Blue → Revenue
- 🟢 Green → Profit
- 🔴 Red → Loss

---

## 🔍 Key Insights

| # | Insight | Impact |
|---|---------|--------|
| 1 | **Q3 (Jul–Sep) is a net-loss quarter** — -₹1,469 profit despite ₹71.7K revenue | High |
| 2 | **Printers deliver 14.5% margin** — nearly 2× the 8.4% company average | High |
| 3 | **COD = 35% of revenue** across 684 transactions — raises return risk & delays cash flow | Medium |
| 4 | **Maharashtra + MP = 43% of total revenue** — critical geographic concentration risk | High |
| 5 | **Clothing = 63% of units sold** but Skirt, Leggings & Kurti are loss-making | Medium |
| 6 | **Top 10 customers = ~15% of revenue** — customer concentration risk | Medium |

---

## 💼 Business Recommendations

| # | Recommendation | Priority |
|---|---------------|----------|
| 1 | **Rationalise loss-making SKUs** — reprice or discontinue Skirt, Leggings, Kurti, Electronic Games, Furnishings | 🔴 High |
| 2 | **Stimulate Q3 demand** — monsoon Clothing campaigns, back-to-school Electronics bundles in Jun–Aug | 🟡 Medium |
| 3 | **Shift payment mix to digital** — incentivise Credit Card/UPI with cashback to reduce COD | 🟡 Medium |
| 4 | **Scale Printers aggressively** — add accessories, ink bundles, B2B channel for offices & schools | 🟢 Strategic |
| 5 | **Launch key account retention programme** — protect ₹65K+ top-customer revenue with loyalty tiers | 🟡 Medium |
| 6 | **Diversify geographically** — target Kerala, Tamil Nadu, Karnataka, Punjab to cut concentration from 43% to <30% | 🟢 Strategic |

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Data Preparation | Python 3 · `csv` · `datetime` · `collections` |
| Frontend Structure | HTML5 · Semantic markup |
| Styling | CSS3 · CSS Variables · Dark/Light theming |
| Interactivity | Vanilla JavaScript (ES6+) |
| Charts | [Chart.js 4.4.1](https://www.chartjs.org/) |
| Hosting | GitHub Pages |
| Architecture | Single-file · Zero build step · No backend |

---

## 📁 Project Structure

```
sales-dashboard/
│
├── index.html          ← Complete dashboard (single self-contained file)
├── Orders.csv          ← Raw orders data (500 rows)
├── Details.csv         ← Raw transaction details (1,500 rows)
├── README.md           ← This file
└── preview.png         ← Dashboard screenshot for README
```

---

## 🚀 How to Run Locally

No installations, no servers, no dependencies.

```bash
# Step 1 — Clone the repository
git clone https://github.com/yourusername/sales-dashboard.git

# Step 2 — Navigate into the folder
cd sales-dashboard

# Step 3 — Open in your browser
# On Mac:
open index.html

# On Windows:
start index.html

# On Linux:
xdg-open index.html
```

Or simply **double-click** `index.html` in your file explorer.

🔗 Prefer not to clone? Visit the **[live version on GitHub Pages](https://yourusername.github.io/sales-dashboard)** directly.

---

## 📸 Screenshots

| Light Mode | Dark Mode |
|-----------|----------|
| ![Light Mode](preview-light.png) | ![Dark Mode](preview-dark.png) |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome.

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — free to use, modify, and distribute.
See the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**[Your Name]**
- LinkedIn: [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
- GitHub: [@yourusername](https://github.com/yourusername)
- Live Dashboard: [yourusername.github.io/sales-dashboard](https://yourusername.github.io/sales-dashboard)

---

<div align="center">

⭐ **If you found this project useful, please give it a star — it helps others discover it!** ⭐

</div>
