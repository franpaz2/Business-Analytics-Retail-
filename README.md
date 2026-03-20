# Retail Business Analytics
**Market Entry Strategy & Data-Driven Business Model for a Specialty Coffee Shop**

![R](https://img.shields.io/badge/R-276DC3?style=for-the-badge&logo=r&logoColor=white)
![Data Storytelling](https://img.shields.io/badge/Data_Storytelling-4B0082?style=for-the-badge)
![Data Engineering](https://img.shields.io/badge/Data_Wrangling-F24E1E?style=for-the-badge)
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-0048C0?style=for-the-badge)

> **Retail Business Analytics** is a comprehensive market intelligence project designed to validate the commercial viability of a coffee shop in Torrevieja. It combines a robust data engineering pipeline (ETL in R) with deep business analysis to transform raw demographic and mobility data into actionable operational and financial decisions.

---

## The Business Challenge
The retail and hospitality sector experiences a high failure rate during the first year due to intuition-based decision-making. The challenge consisted of evaluating a small commercial space (25m2 usable) with a maximum capacity of 15 people. The goal was to maximize profitability per square meter by defining the optimal target audience, peak conversion time slots, and product strategy based on real demographic evolution and competitor analysis.

---

## Technical Architecture & Data Processing (Data Wrangling)

To ensure the accuracy of the commercial conclusions, a structured data pipeline was developed in the R Markdown environment, processing multiple raw data sources (.csv).

### 1. Tech Stack
* **Language:** R
* **Data Manipulation & ETL:** `dplyr`, `readr`
* **Time Series:** `lubridate`
* **Advanced Visualization:** `ggplot2`

### 2. ETL Pipeline & Data Cleaning
* **Regex & Type Casting:** Algorithmic cleaning of European formats (removal of thousands separators using `gsub`) and strict conversion of text strings into continuous numerical variables to enable statistical calculation.
* **Time Series Processing:** Destructuring nested temporal fields (e.g., "2023M01") by extracting substrings to instantiate independent `year` and `month` variables.
* **Data Enrichment (Joins):** Crossing spatial and demographic sub-tables (using `merge()`) to consolidate population volumes with parametric spending metrics by nationality.

### 3. Feature Engineering & Dimensional Modeling
* **Seasonality Normalization:** Calculation of the seasonality rate by normalizing the monthly tourist weight against the total annual sum.
* **Synthetic Business KPIs:** Design of new cascaded derived variables (`dplyr` pipeline), highlighting the predictive calculation of *Total Impact* (population multiplied by average spending crossed between tourists and local residents).
* **Multidimensional EDA:** Programming high-density charts in `ggplot2` mapping 4 simultaneous mathematical dimensions in the competitor analysis: Distance to the venue (X-Axis), Rating (Y-Axis), Review Volume (Size), and Average Ticket (Continuous color gradient).

---

## Key Insights & Actionable Strategy

Crossing demographic data and the Feature Engineering pipeline revealed the following strategic axes:

### 1. Segmentation & Target Audience
* **Sociodemographic Shift:** The percentage of the Spanish population has decreased to 47.9%, while the Ukrainian and Northern European population has experienced a critical increase. 
* **Omnichannel Strategy:** Mandatory implementation of digital menus (QR) in Spanish, English, Russian, and Ukrainian.

### 2. Operational Optimization by Time Slots
* **07:30 – 10:00 (35% of spending):** Traffic dominated by local workers. Requires an operational model focused on speed and a *Take Away* format to mitigate capacity limitations.
* **10:00 – 13:00 (30% of spending):** Dominated by foreign residents oriented towards prolonged consumption (*Brunch*).
* **Product Adaptation:** Alignment of the offering with detected trends (gluten-free, vegan products, and plant-based milks), adjusting the average ticket to the sustained growth of the municipality's per capita income.

---

## How to Reproduce the Analysis

1. Clone the repository:
```bash
git clone [https://github.com/tu-usuario/retail-business-analytics.git](https://github.com/tu-usuario/retail-business-analytics.git)
cd retail-business-analytics
```
2. Install dependencies (R Console):
```R
install.packages(c("dplyr", "ggplot2", "readr", "lubridate"))
```
3. Run the `limpieza_graficas.Rmd` notebook to compile the data pipeline and generate the final analytical document.

*Analysis and Data Engineering co-developed by the Iceberg Datum ecosystem.*
