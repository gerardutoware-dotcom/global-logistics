# Global Logistics Optimization & Carbon Audit
**Data Analytics Portfolio Project**

## Project Overview
This project provides an end-to-end audit of a national logistics network consisting of 5,000+ fulfillment records. By integrating geospatial data engineering with financial modeling, I identified that **28.5% of total orders** are currently fulfilled via "Critical Inefficiency" lanes (cross-country routes exceeding 2,500km). 

The goal of this project was to quantify the financial "leakage" and carbon impact of sub-optimal routing and provide data-driven recommendations for inventory rebalancing.

---

## The Tech Stack
* **SQL (BigQuery):** Data cleaning, joining disparate warehouse/customer tables, and schema optimization.
* **Python (Google Colab):** Implementation of the **Haversine Formula** to calculate great-circle distances between geographic coordinates.
* **Tableau:** Advanced geospatial visualization, Spider-Map generation, and **LOD (Level of Detail) Expressions** for operational KPIs.

---

## Methodology: Geospatial Modeling
To classify shipping efficiency, I calculated the distance between Warehouse ($Lat_1, Lon_1$) and Customer ($Lat_2, Lon_2$) using the Haversine formula:

$$d = 2r \arcsin\left(\sqrt{\sin^2\left(\frac{\phi_2 - \phi_1}{2}\right) + \cos(\phi_1) \cos(\phi_2) \sin^2\left(\frac{\lambda_2 - \lambda_1}{2}\right)}\right)$$

**Efficiency Tiers:**
- **Optimized:** < 1,000 km (Regional fulfillment)
- **Sub-Optimal:** 1,000 km - 2,500 km (Inter-regional)
- **Critical Inefficiency:** > 2,500 km (Cross-country)

---

## Key Insights & Business Impact
* **Operational Risk:** Found that **28.5%** of the network operates in the "Critical" tier, indicating a severe inventory-to-demand mismatch.
* **Financial Leakage:** Identified **£21,677** in annual avoidable shipping premiums.
* **Sustainability:** Quantified **36.67** metric tons of avoidable $CO_2$ emissions directly tied to inefficient routing.

---

## Strategic Recommendation
The analysis suggests that by relocating high-velocity SKUs to a mid-west 3rd-party logistics (3PL) partner, the company can reduce "Critical" shipping lanes by **15-20%**, significantly lowering both fulfillment costs and the corporate carbon footprint.
