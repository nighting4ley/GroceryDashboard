# GroceryDashboard

An end-to-end analytics case study examining United States grocery retail sales (2019–2023) trends, seasonal patterns, macroeconomic drivers, and holiday-driven demand spikes using **MySQL** and **Microsoft Power BI**.

---

## 📌 Project Overview

This project analyzes public datasets from the U.S. Department of Agriculture (USDA), US Census Bureau, Bureau of Economic Analysis (BEA), and Bureau of Labor Statistics (BLS) to evaluate consumer spending behaviors across 43 states and 11 distinct grocery categories. 

The goal of this case study is to assist supermarket logistics and supply chain planning by identifying sales cycles, demand surges, and geographic spending patterns from October 2019 to May 2023.

---

## 🗂️ Data Sources

* **USDA Economic Research Service (ERS) / Circana**: Weekly retail food sales scanner data (national totals, 54 subcategories, and state-level category data across 43 states).
* **US Census Bureau**: 
  * *Statistics of U.S. Businesses (SUSB) 2021*: Enterprise sizes, store establishments, employment, and payroll for NAICS `44511` (*Supermarkets and Other Grocery Retailers*).
  * *State Population Totals (2023)*.
* **US Bureau of Economic Analysis (BEA)**: Annual current-dollar state Gross Domestic Product (2019–2023).
* **US Bureau of Labor Statistics (BLS)**: Annual state unemployment rates (2019–2023).

---

## 🛠️ Tech Stack & Tools

* **Database Engine**: MySQL Server
* **ETL & Data Cleaning**: Microsoft Excel, Notepad++, SQL scripts
* **Data Visualization & Analytics**: Microsoft Power BI Desktop
* **Key Visuals Used**: Line charts, Treemaps, Stacked bar charts, Craydec Regression visuals

---

## ⚙️ ETL & Database Design

### Data Cleaning Highlights
* Normalized dates to the standard `YYYY-MM-DD` MySQL format.
* Handled missing/null values and stripped special formatting (currency symbols `$`, thousands separator commas `,`).
* Enforced case-matching during string replacements to avoid corrupting text fields (e.g., preventing `Arizona` from becoming `ArizoNULL`).
* Added auto-incrementing surrogate primary keys for relational mapping.

### Relational Schema (Key Tables)
* `national_food_sales` — Weekly national totals, dollar sales, and unit volume.
* `national_subcategory_sales` — Breakdown across 54 grocery subcategories.
* `state_category_sales` — State-level weekly sales across 11 major categories.
* `2021_susb_groceries_states` — Employment, payroll, and establishment sizes by state.
* `state_gdp`, `state_population`, `state_unemployment` — State-level macro metrics.

---

## 📊 Key Findings & Insights

* **Holiday Surges**: Significant spending spikes occur consistently the week prior to major holidays (Thanksgiving, Christmas, Easter, Valentine's Day).
* **Event Outliers**: A massive volume and dollar surge took place around **March 15, 2020** ("panic buying" phase following the COVID-19 national emergency declaration).
* **Seasonality**: Categories like *Beverages* and *Fruits & Vegetables* exhibit cyclical behavior, peaking in warm summer months and dipping in winter.
* **Top Spending Drivers**: Consumers spend the highest dollar amounts on *Commercially Prepared Items* (ready-to-eat meals, soups, frozen dinners) and *Meat/Proteins*, driven by high transaction volume and higher price-per-pound ratios.
* **State Demographics**: A strong positive linear correlation ($R^2 = 0.95$, $\text{Corr} = 0.97$) exists between state population and state GDP, with California, Texas, New York, and Florida driving the highest overall grocery employment and revenue.

---

## 🚀 Getting Started

### Prerequisites
* MySQL Server (8.0+) / MySQL Workbench
* Microsoft Power BI Desktop

### Setup & Installation
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/nighting4ley/GroceryDashboard.git](https://github.com/nighting4ley/GroceryDashboard.git)
   cd GroceryDashboard
   