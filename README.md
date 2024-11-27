# Sales Performance Analysis
## Table of Contents
- Project Overview
- Data Sources
- Recommendations
### Project Overview

## Project Overview
This project focuses on analyzing sales performance using Tableau. The dataset includes sales, customer, and shipping information, which we visualize to derive meaningful insights. The main objectives are:
- To analyze total sales by region, product category, and customer.
- To identify top-performing customers and products.
- To examine shipping modes and their impact on sales.
- To track sales trends over time and seasonal patterns.

## Key Insights:
- **Sales Analysis by Region**: Identifies the top regions for sales performance.
![salesdashboard1](https://github.com/user-attachments/assets/af2ccdc5-6f58-4217-8d1e-192a255bc3c8)
- **Customer Segmentation**: Utilizes RFM (Recency, Frequency, Monetary) analysis to segment customers based on their purchasing behavior.
  ![salesdashboard3](https://github.com/user-attachments/assets/d9fd682d-7587-47f3-b965-ba3a08295e85)
- **Shipping Performance**: Analyzes shipping speed and delivery time and its effect on total sales.
- **Top Products**: Identifies the most profitable products and categories.
  ![salesdashboard2](https://github.com/user-attachments/assets/3e144c90-e796-460d-bb78-bba516663bbd)
  ## Predictive Analytics Overview

### Methodology
1. **Data Preparation:** 
   - Processed historical sales data to clean, aggregate, and structure it for forecasting.
2. **Modeling:**
   - Used **Facebook Prophet** to build the predictive model.
3. **Evaluation:**
   - Analyzed forecast accuracy using confidence intervals and compared it against actual sales.

---

## Key Visualizations

### 1. Customized Forecast of Sales
![Customized Forecast of Sales](https://github.com/user-attachments/assets/5474be3f-175e-4e71-a128-9b444be00902)

- **Description:** Displays the predicted sales over time with historical data and confidence intervals.
- **Purpose:** Highlights how well the model aligns with actual sales trends.

### 2. Forecast Components
![Forecast Components](https://github.com/user-attachments/assets/ced4850e-0f00-46d8-b415-a7dd2d61a43d)
- **Trend Component:** Illustrates the long-term direction of sales.
- **Weekly Component:** Shows day-of-week sales patterns.
- **Yearly Component:** Captures seasonal fluctuations over the year.

### 3. Forecasted Sales Over Time
![Forecasted Sales OverTime](https://github.com/user-attachments/assets/1dbcd843-6438-4e5e-9ff0-a6a91192af64)
- **Description:** Compares historical sales data with the forecast, showing predictions over time.
  ### 4.Sales Forecast with Uncertainty Intervals
  ![Sales Forecast with Uncertainty Intervals](https://github.com/user-attachments/assets/9a95841a-08d9-4a82-9200-e6f42b4e47e5)
  ### 5.Residuals Over Time
  ![Residuals Over Time](https://github.com/user-attachments/assets/ec1571da-997e-4096-91b0-0dedbd34855e)


## Tools and Technologies
- **Tableau**: For data visualization.
- **SQL**: for data Analysis
  ```sql
  SELECT 
    DATEPART(YEAR, ship_date) year,
    DATEPART(QUARTER, ship_date) quarter,
	DATEPART(MONTH, ship_date) month,
	SUM(Sales) total_sales FROM ordersGROUP BY  
	DATEPART(YEAR, ship_date),
    DATEPART(QUARTER, ship_date),
	DATEPART(MONTH, ship_date)
  ORDER BY year, quarter, month ASC;
- **RFM Analysis**: Used for customer segmentation.
- **Data Sources**: Sales, shipping, and customer datasets.
- **Python:** For data visualization.
  ``` python
  import pandas as pd
  data = pd.read_csv('Sales_Dataset.csv')
  data['ds'] = pd.to_datetime(data['Order Date'], format='%d/%m/%Y', dayfirst=True)
  data['y'] = data['Sales']
  data = data[['ds', 'y']]

- **Facebook Prophet:** For time-series prediction.
- **Matplotlib & Seaborn:** For visualizing sales data and model outputs.

## Files in this repository:
- `/data`: Contains datasets used in the analysis (raw/cleaned).
- `/scripts`: Python/R scripts for data analysis and cleaning.
- `/visualizations`: Tableau workbook and dashboards.


