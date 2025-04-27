

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


## 🔍 Exploratory Data Analysis (EDA)

1. **Delivery Performance Breakdown**
   - Created a pie chart visualizing the percentage of on-time vs delayed deliveries.
![image](https://github.com/user-attachments/assets/ca1e0d3c-1734-466b-b214-67c63d30f6f0)

the image displays ontime vs delivery rate in the dataset.

---
2. **Top Delayed Routes**
   - Identified origin-destination pairs with the highest number of delayed trips and calculated their average delay duration.

Average Delay Duration (hours): 237.80
Maximum delay(hours):7394.95

---
3. **Vehicle Performance**
   - Found underutilized and overutilized vehicles based on trip counts.
   - Highlighted vehicles that were either overworked or seldom used.
![image](https://github.com/user-attachments/assets/63d9b18e-e7e1-4d6f-9c3e-fc39f60d2924)
![image](https://github.com/user-attachments/assets/c6f749cb-47df-43e6-a69a-f2220e302b9a)

---
4. **Supplier Performance**
   - Computed average transportation distance per supplier, enabling supplier efficiency comparison.
![image](https://github.com/user-attachments/assets/ccec1b7f-f079-4dac-800e-44cb3f69f57b)

---
5. **Monthly Trip Trends**
   - Analyzed the number of trips each month across two years.
   - Created pivot tables to separate trends for each year and plotted comparative line graphs.
![image](https://github.com/user-attachments/assets/b0cfdc50-802c-4a4f-be03-36409a81e11d)
The chart represents number of trips permonth. 

---
6. **Delay Trends Over Time**
   - Tracked monthly average delivery delay durations, both with and without outlier influence, using line and bar charts.
![image](https://github.com/user-attachments/assets/5c57257a-b4d3-4ce0-8601-167307c67fa2)
The image shows the average delay duration for every month but the lines are dicontinuous because of outlliers making t difficult to understand the data. 
![image](https://github.com/user-attachments/assets/5e599169-be56-4437-9198-6285c0f2eb2a)
The image shows the average delivery duration.    
--
7. **Correlation Analysis**
   - Explored relationships between transportation distance and delivery timelines.

Correlation Matrix:
                               TRANSPORTATION_DISTANCE_IN_KM  actual_eta  \
TRANSPORTATION_DISTANCE_IN_KM                       1.000000    0.125025   
actual_eta                                          0.125025    1.000000   
Planned_ETA                                         0.129862    0.999515   

                               Planned_ETA  
TRANSPORTATION_DISTANCE_IN_KM     0.129862  
actual_eta                        0.999515  
Planned_ETA                       1.000000 

---

## 📊 Dashboard Highlights (Visualized in Matplotlib)

- 📈 **Trips Per Month**: Line graphs showcasing volume trends year-over-year.
- 🚛 **Vehicle Utilization**: Identified the most and least used vehicles.
- 🕒 **Delay Distribution**: Bar graphs showing how delays fluctuate monthly.
- 🛤️ **Top Routes with Delays**: Focused tables revealing logistics bottlenecks.



## 📈 Business Insights

- **Optimize Vehicle Deployment**  
  Underutilized and overutilized vehicles highlight opportunities for better fleet distribution and trip allocation.

- **Supplier Evaluation**  
  Suppliers with consistently high transportation distances or associated delays need strategic intervention.

- **Monitor Delivery Punctuality**  
  Delay trends can be monitored seasonally to plan better during peak load months.

- **Route Planning Enhancements**  
  Frequently delayed routes can be flagged for reevaluation, potentially optimizing logistics paths.



## 🛠️ Tools & Technologies Used

- Python (Pandas, Matplotlib, Seaborn)
- Excel (for initial checks)
- Kaggle (Dataset Source)

The dataset is very rich and would love to explore more and perform analysis in the future. 
