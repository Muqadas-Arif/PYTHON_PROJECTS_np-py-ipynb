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





— Muqadas-Arif
