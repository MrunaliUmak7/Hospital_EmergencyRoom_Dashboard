# Hospital_EmergencyRoom_Dashboard

# Hospital Emergency Room (ER) Dashboard

This project presents an interactive **Power BI dashboard** to analyze Emergency Room (ER) data, providing hospital administrators and healthcare professionals with actionable insights on patient flow, admission rates, and performance metrics.

---

## 🎯 Objective
- Monitor ER admissions and discharge patterns  
- Track patient inflow trends by date, time, and day of the week  
- Identify key metrics such as admission rate, average wait time, and patient demographics  
- Support hospital staff in decision-making and resource management  

---

## 🛠️ Tools & Technologies
- **Power BI** – for dashboard creation and visual analytics  
- **DAX** – for calculated columns and measures  
- **Excel/CSV** – as data source  
- **Data Modeling** – for relationships and filters  

---

## 📂 Dataset Overview
Key fields include:
- Patient ID  
- Date & Time of Visit  
- Gender  
- Age Group  
- Admission Flag  
- Reason for Visit  
- Department  
- Discharge Status  

> **Note:** The dataset is a simulated sample for educational purposes.  

---

## 📊 Dashboard Features
- Total ER Visits and Admissions  
- Admission Rate (calculated using DAX)  
- Patient Trends by Weekday and Hour  
- Age and Gender Distribution  
- Filter by Date Range, Department, and Reason  
- Clean layout with slicers and drill-downs  

---

## 📌 DAX Highlight
Example formulas used:

```DAX
-- Admission Status
Admission Status = IF('ER_Data'[Patient Admission Flag] = TRUE(), "Admitted", "Not Admitted")

-- Month & Year
Month & Year = FORMAT('Date Table'[Date], "MMM") & " " & YEAR('Date Table'[Date])

-- Age Group
Age Group = SWITCH(
    TRUE(),
    'ER_Data'[Age] <= 12, "Child",
    'ER_Data'[Age] <= 19, "Teen",
    'ER_Data'[Age] <= 35, "Young Adult",
    'ER_Data'[Age] <= 60, "Adult",
    "Senior"
)


