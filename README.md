# NumPy-and-synthetic-sales-data-project
# Numpyproj.ipynb

Hi — this notebook is something I put together to play with NumPy and synthetic sales data. It creates a small, reproducible retail dataset for January 2026 (200 orders) and walks through a bunch of simple analyses: totals, filters, basic aggregations, and a few toy feature transforms. I wrote it to be easy to follow if you want to learn how to do quick analytics with structured NumPy arrays.

What you'll find in the notebook
- Data generation (200 rows) with a fixed seed so the results repeat:
  - order_id: integer
  - product_id: integer (100–120)
  - category: "Electronics", "Apparel", or "Grocery"
  - quantity: 1–10
  - price_per_unit: category-dependent (Electronics highest, Grocery lowest)
  - discount: one of [0, 0.05, 0.1, 0.15, 0.2]
  - date: random days in January 2026 (string YYYY-MM-DD)
  - store_id: 1–5

- Example analyses and transformations included:
  - Accessing fields and slicing (e.g., first 10 quantities)
  - total_price = quantity * price_per_unit
  - final_price = total_price * (1 - discount)
  - Counts and totals per category (orders, total quantity)
  - Max / min sale per category
  - Filtering: high-value orders, category + price filters
  - Average discount per category
  - Revenue per store and top revenue dates
  - Top products by total quantity sold
  - Cumulative revenue over time (after sorting by date)
  - Simple feature work: min-max price normalization, discount capping
  - Revenue bucketing (Low / Medium / High) and a conditional bonus example

Quick run notes
- This was run with NumPy and a standard Jupyter kernel (Python 3.11 in my environment).
- I used np.random.seed(42) so the numbers you see in the notebook are reproducible.

Some example results from the run in the notebook
- Average order value (final_price mean): ~9194.339
- Discounted orders: 157
- Top revenue dates (top 3): 2026-01-15, 2026-01-21, 2026-01-12
- Example store revenues:
  - Store 1: 294,276.60
  - Store 2: 465,002.10
  - Store 3: 460,859.35
  - Store 4: 234,531.00
  - Store 5: 384,198.75

Requirements
- Python 3.7+ (I used 3.11)
- NumPy
- Jupyter Notebook or JupyterLab

Install with pip if needed:
```
pip install numpy jupyterlab
```
(Optional) If you want to convert the structured NumPy array to a CSV or use DataFrame operations:
```
pip install pandas
```

How to run
1. Open the notebook (Numpyproj.ipynb) in Jupyter:
   - jupyter notebook Numpyproj.ipynb
   - or jupyter lab
2. Run the cells from top to bottom. The notebook builds the synthetic dataset and then runs the examples; nothing external is required.

Save or export the data
- To save as CSV (via pandas):
```python
import pandas as pd
df = pd.DataFrame(sales_data)   # sales_data is the structured NumPy array
df.to_csv("sales_data.csv", index=False)
```
- Save the NumPy array directly:
```python
np.save("sales_data.npy", sales_data)
```

Ideas to extend this notebook
- Convert the structured array to a pandas DataFrame to use groupby and easier plotting
- Add plots (Matplotlib, Seaborn, or Plotly): daily revenue, revenue by category/store, discount histograms
- Use datetime objects (numpy datetime64 or pandas timestamps) and aggregate by week
- Simulate returns or cancellations and compute net revenue
- Build a small Streamlit dashboard to explore the data interactively


🏥 ##****Hospital Analytics Project – End-to-End Data Analysis with Pandas**
📌 ##**Project Overview****

This project is a complete end-to-end data analysis case study built to simulate the kind of work a real data analyst performs in a healthcare environment.
The goal was not just to write code, but to think like an analyst: clean messy data, engineer meaningful features, analyze patterns, and translate results into business-ready insights.

The project was intentionally designed at beginner, intermediate, and advanced levels, covering the full data lifecycle from raw CSV to executive-level KPIs.

🎯 Business Problem

Hospitals deal with:

Rising treatment costs

Patient readmissions

Uneven department performance

Limited visibility into risk-heavy patients

This project answers questions such as:

Which departments are cost-heavy or inefficient

What factors relate to readmission risk

How patient age, cost, and stay duration impact outcomes

How to flag high-risk patients for proactive care

🧰 Tools and Skills Used

Python

Pandas

Data Cleaning and Validation

Feature Engineering

Exploratory Data Analysis (EDA)

Pivot Tables and Aggregations

Time-based Analysis

Business KPI Design

Analytical Storytelling

📂 Dataset

A realistic synthetic hospital dataset was created, containing:

Patient demographics

Admission dates

Departments and doctors

Length of stay

Billing information

Readmission risk indicators

Multiple versions of the dataset were saved to reflect professional versioning practices:

Raw data

Engineered data

Final clean dataset

🔍 Project Workflow
Day 1–2: Data Understanding and Cleaning

Loaded raw hospital data

Identified missing and inconsistent values

Fixed datatypes and invalid records

Ensured data integrity before analysis

Day 3: Feature Engineering

Created age groups

Built cost categories

Calculated length of stay

Designed a readmission risk flag

Saved engineered datasets safely

Day 4: Exploratory Data Analysis

Dataset health checks

Department-level KPIs

Cost distribution analysis

Readmission overview

Efficiency analysis using length of stay

Day 5: Advanced Aggregations

Pivot tables by department and age group

Revenue and cost comparisons

Doctor-level readmission screening

Monthly patient and revenue trends

Day 6: Risk Analysis

Readmission rate analysis

Risk by department and cost category

Identification of high-risk patients using business logic

Day 7: Executive KPIs and Storytelling

Hospital-level KPIs

Department scorecards

Doctor quality snapshots

Patient segmentation

Business insights suitable for leadership

📊 Key Insights

Certain departments consistently show higher cost and longer stays

High readmission risk often correlates with longer stays and higher bills

A small segment of patients drives a large portion of financial risk

Feature engineering enables early identification of high-risk patients

🧠 What This Project Demonstrates

Ability to work end-to-end, not just isolated analysis

Strong understanding of business context, not only code

Clean, structured, and reproducible workflows

Skills directly aligned with junior to mid-level data analyst roles

🚀 Next Steps

Visualization using Power BI or Tableau

Predictive modeling for readmission risk

Dashboard creation for executives

👤 Author

Created by muqadas
Aspiring Data Analyst | Python | Pandas | Analytics


— Muqadas-Arif
