# Automobile Sales & Campaign Data Analysis

> End-to-end data analytics project covering vehicle sales performance, customer segmentation, marketing campaign effectiveness, and multi-model demand forecasting for an automotive business dataset.

---

## 📌 Business Objectives

- Analyze vehicle sales performance across brands, models, and fuel types
- Evaluate dealership and regional sales performance
- Measure marketing campaign effectiveness through ROI and conversion analysis
- Understand customer purchasing behavior and demographics
- Segment customers based on value and engagement
- Estimate Customer Lifetime Value (CLV)
- Forecast future sales demand to support inventory and operational planning
- Identify growth opportunities and operational inefficiencies

---

## 🗂️ Dataset Description

The project utilizes multiple interconnected fact and dimension tables representing various aspects of automotive operations.

### Fact Tables

| Table | Description |
|-------|-------------|
| `Fact_VehicleSales` | Vehicle sales transactions including units sold, sale amount, and discounts |
| `Fact_MarketingCampaignPerforman` | Marketing campaign performance metrics |
| `Fact_TestDrive` | Test drive activity and outcomes |

### Dimension Tables

| Table | Description |
|-------|-------------|
| `Dim_Customer` | Customer demographics and profile |
| `Dim_Vehicle` | Vehicle brand, model, and fuel type details |
| `Dim_Dealer` | Dealership information |
| `Dim_Region` | Geographic region data |
| `Dim_Campaign` | Campaign metadata |
| `Dim_Channel` | Sales and marketing channel details |
| `Dim_Date` | Date dimension for time-based analysis |
| `Dim_SalesExecutive` | Sales executive profiles |

---

## 🧹 Data Preparation

### Data Cleaning
- Removed duplicate records
- Handled missing values
- Standardized categorical variables
- Corrected inconsistent entries
- Validated relationships between fact and dimension tables

### Feature Engineering

| Feature | Description |
|---------|-------------|
| Customer Age Groups | Bucketed age for segmentation |
| Campaign Conversion Rates | Leads → Test Drives → Bookings → Purchases |
| ROI Percentage | Revenue vs. campaign spend |
| Revenue per Customer | SaleAmount aggregated by customer |
| Customer Lifetime Value (CLV) | Long-term value estimation |
| Test Drive Conversion Metrics | Funnel drop-off at each stage |
| Time-Based Sales Features | Monthly aggregations for forecasting |

---

## 📊 Exploratory Data Analysis

### Vehicle Sales Performance
- Sales by brand, model, and fuel type
- Revenue contribution and units sold
- Top-performing and underperforming vehicle categories

### Regional & Dealer Analysis
- Revenue and units by region
- Dealer ranking and performance comparison
- High-growth market identification

### Marketing Campaign Performance
- Total impressions, leads, test drives, bookings, and revenue per campaign
- ROI analysis across campaigns and channels
- Funnel conversion: Impressions → Leads → Test Drives → Bookings → Purchases

### Customer Segmentation & CLV
- Segmentation by spending behavior, purchase frequency, demographics, and vehicle preference
- CLV estimation using revenue contribution, purchase history, and engagement

---

## 📈 Demand Forecasting

Time-series forecasting was performed on **monthly UnitsSold** to predict future demand and support inventory planning.

- **Target Variable:** `UnitsSold` (monthly aggregated)
- **Forecast Horizon:** 6 months
- **Evaluation Metrics:** MAE (Mean Absolute Error), RMSE (Root Mean Squared Error)

### Models Used

| Model | Why It Was Used |
|-------|----------------|
| **Prophet** | Handles yearly seasonality in car buying trends automatically; robust to missing data |
| **SARIMA(1,1,1)(1,1,1,12)** | Classic statistical model; captures monthly and yearly seasonal patterns |
| **LSTM (Long Short-Term Memory)** | Captures non-linear, long-term temporal dependencies that classical models miss |

All three models were trained and evaluated side-by-side. The best-performing model (lowest MAE) was automatically selected for inventory planning.

### Inventory Planning Output

| Column | Description |
|--------|-------------|
| `Forecast_Units` | Predicted units for each future month |
| `Safety_Stock` | Forecast + 20% buffer for demand variability |
| `Reorder_Point` | Forecast + 10% as the restocking trigger |

---

## 🛠️ Technologies Used

### Programming
- Python

### Data Processing
- Pandas
- NumPy

### Visualization
- Matplotlib
- Plotly

### Forecasting & Machine Learning
- Statsmodels (SARIMA)
- Prophet (Facebook/Meta)
- TensorFlow / Keras (LSTM)
- Scikit-learn (evaluation metrics)

### Dashboarding
- Power BI

### Development Environment
- Jupyter Notebook / Google Colab
- VS Code

---

## 📁 Project Structure

```
Automobile-Sales-and-Campaign-Analysis/
│
├── data/
│   ├── raw_data/
│   └── processed_data/
│
├── notebooks/
│   ├── data_cleaning.ipynb
│   ├── exploratory_analysis.ipynb
│   ├── customer_segmentation.ipynb
│   └── forecasting.ipynb
│
├── dashboard/
│   └── Automobile_Sales_Dashboard.pbix
│
├── images/
│   └── dashboard_screenshots/
│
├── reports/
│   └── business_insights.pdf
│
└── README.md
```

---

## ✅ Key Outcomes

- Identified top-performing vehicle categories, brands, and regions
- Evaluated marketing campaign profitability, ROI, and funnel conversion rates
- Analyzed customer behavior, demographics, and purchasing patterns
- Built customer segmentation and CLV models to support targeted marketing
- Compared Prophet, SARIMA, and LSTM for demand forecasting; auto-selected best model
- Generated a 6-month inventory plan with safety stock and reorder point recommendations
- Produced actionable insights for business growth and operational optimization

---

## 👤 Author

**Dhaani Bahl**

Data Analytics | Machine Learning | Business Intelligence

Skills: Python, SQL, Power BI, Machine Learning, Data Visualization, Forecasting

