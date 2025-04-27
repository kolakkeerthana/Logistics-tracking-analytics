

# 📦 Logistics Tracking and Transportation Analysis
![image](https://github.com/user-attachments/assets/35607d84-67be-44ad-b390-d9fabbd2797f)
Image : Broad Range Logistics
## 📌 Introduction
This project explores a dataset sourced from Kaggle containing detailed records of logistics tracking and transportation events. The dataset was originally in `.xlsx` format and focuses on shipment timelines, supplier performance, vehicle utilization, and delivery efficiency.

Our objective is to clean, validate, and analyze the dataset to derive actionable insights on delivery performance, vehicle optimization, and monthly transportation trends. These insights can help organizations enhance operational efficiency and supplier management.

## 🧹 Data Cleaning & Preparation

1. **File Extraction**
   - The `.zip` dataset was extracted using Python's `zipfile` module.

2. **Initial Data Validation**
   - Reviewed dataset for missing values, duplicates, and unusual trends.
   - Focused on key columns: booking dates, ETA (Planned and Actual), origin, destination, supplier ID, and vehicle information.

3. **Handling Null Values**
   - Dropped rows where both `ontime` and `delay` columns were missing, ensuring every record had a delivery status.

4. **Data Type Conversion**
   - Converted date-related columns (`Planned_ETA`, `actual_eta`, `BookingID_Date`) to datetime format for accurate analysis.
   
5. **Delay Duration Calculation**
   - Created a new feature `delay_duration` (in hours) by calculating the difference between actual and planned arrival times.
   - Any negative delays were treated as zero (early deliveries).

6. **Outlier Removal**
   - Used the IQR (Interquartile Range) method to filter out extreme outliers from delay durations for clearer trend visualization.

---

## 🔍 Exploratory Data Analysis (EDA)

1. **Delivery Performance Breakdown**
   - Created a pie chart visualizing the percentage of on-time vs delayed deliveries.

2. **Top Delayed Routes**
   - Identified origin-destination pairs with the highest number of delayed trips and calculated their average delay duration.

3. **Vehicle Performance**
   - Found underutilized and overutilized vehicles based on trip counts.
   - Highlighted vehicles that were either overworked or seldom used.

4. **Supplier Performance**
   - Computed average transportation distance per supplier, enabling supplier efficiency comparison.

5. **Monthly Trip Trends**
   - Analyzed the number of trips each month across two years.
   - Created pivot tables to separate trends for each year and plotted comparative line graphs.

6. **Delay Trends Over Time**
   - Tracked monthly average delivery delay durations, both with and without outlier influence, using line and bar charts.

7. **Correlation Analysis**
   - Explored relationships between transportation distance and delivery timelines.

---

## 📊 Dashboard Highlights (Visualized in Matplotlib)

- 📈 **Trips Per Month**: Line graphs showcasing volume trends year-over-year.
- 🚛 **Vehicle Utilization**: Identified the most and least used vehicles.
- 🕒 **Delay Distribution**: Bar graphs showing how delays fluctuate monthly.
- 🛤️ **Top Routes with Delays**: Focused tables revealing logistics bottlenecks.

---

## 📈 Business Insights

- **Optimize Vehicle Deployment**  
  Underutilized and overutilized vehicles highlight opportunities for better fleet distribution and trip allocation.

- **Supplier Evaluation**  
  Suppliers with consistently high transportation distances or associated delays need strategic intervention.

- **Monitor Delivery Punctuality**  
  Delay trends can be monitored seasonally to plan better during peak load months.

- **Route Planning Enhancements**  
  Frequently delayed routes can be flagged for reevaluation, potentially optimizing logistics paths.

---

## 🛠️ Tools & Technologies Used

- Python (Pandas, Matplotlib, Seaborn)
- Excel (for initial checks)
- Kaggle (Dataset Source)
