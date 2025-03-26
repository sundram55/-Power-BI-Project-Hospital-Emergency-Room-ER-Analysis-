# Power BI Project : Hospital Emergency Room(ER)-Analysis

---

# 📊 Hospital Emergency Room Dashboard  

## 🏥 Overview  

This repository contains a **Power BI project** that provides a **comprehensive dashboard** for analyzing **Emergency Room (ER) patient data**. The dashboard offers insights into **patient wait times, satisfaction levels, demographics, referral patterns, admission statistics**, and **peak busy periods**, helping **healthcare professionals** optimize resource allocation and improve patient care.  

---

# 🚀 Live Power BI Dashboard
https://app.powerbi.com/view?r=eyJrIjoiZWUxYjFlNjItNGU5Zi00ZGMyLWJkZmItMDVhYTk3ZmZhODZlIiwidCI6IjgxOGFkMzE5LWY2ZjctNDU4Yy1hNDg3LWI5NTdiZmE2ODkwNyJ9

---

## 📂 Repository Structure  

```
📂 Hospital-ER-Dashboard
│── 📜 README.md                # Project Documentation
│── 📜 Hospital ER.pdf          # Power BI Dashboard Report
│── 📊 Hospital ER_Data.csv     # Raw ER Data for Analysis
│── 📊 PowerBI_Dashboard.pbix   # Power BI Dashboard File
│── 📊 project images.zip       # iamges used in this project
```

---

## 📈 Key Insights  

### 🕒 **Patient Wait Time & Satisfaction**  
- **Average Wait Time**: ⏳ **35.26 minutes**  
- **Average Satisfaction Score**: ⭐ **4.99 / 10**  
- **Only 59.3% of patients were seen within 30 minutes**, highlighting an area for **process improvement**.  

### 🏥 **Admission & Referral Patterns**  
- **Total Patients**: 👨‍⚕️ **9,216**  
- **Admitted**: ✅ **4,612 (50.04%)**  
- **Not Admitted**: ❌ **4,604 (49.96%)**  
- **Department Referrals**:  
  - **General Practice**: **1,840**  
  - **Orthopedics**: **995**  
  - **Physiotherapy**: **276**  
  - **Cardiology**: **248**  
  - **Neurology**: **193**  

### 📊 **Peak Busy Periods**  
- **Busiest Days**: **Saturday (1,377), Thursday (1,322), Sunday (1,318)**  
- **Busiest Hours**: **11 AM, 7 PM, 1 PM, 11 PM**  
- **Recommendation**: **Increase staffing during peak hours** to reduce wait times.  

### 👤 **Demographics**  
- **Gender Distribution**: **Male (51.05%)** | **Female (48.69%)**  
- **Age Group**:  
  - **30-39 years**: **1,200 patients** (largest group)  
  - **20-29 years**: **1,188 patients**  
  - **40-49 years**: **1,135 patients**  
- **Race Distribution**:  
  - **White**: **2,571**  
  - **African American**: **1,951**  
  - **Multiracial**: **1,557**  
  - **Asian**: **1,060**  
  - **Declined to Identify**: **1,030**  

---

## 🎯 Project Objectives  

- 📊 **Analyze ER patient flow** to identify **bottlenecks** and optimize hospital efficiency.  
- 🏥 **Improve patient care** by understanding **waiting times** and **satisfaction scores**.  
- 🚑 **Optimize staffing** by identifying **peak busy periods**.  
- 👥 **Assess demographic trends** to ensure **equitable healthcare access**.  

---

## 📌 Tools & Techniques Used  

### 🏆 **Power BI**  
- **Data Cleaning & Transformation**: Utilized **Power Query Editor** to clean and process raw data.  
- **Advanced DAX Calculations**: Created **calculated measures and columns** to enhance analysis.  
- **Interactive Dashboards**: Designed **dynamic visuals** to track key ER performance metrics.  

### 🔢 **Advanced DAX Formulas & Measures Used**  
- **Total Patients**:  
  ```DAX
  No. Of Patients = DISTINCTCOUNT('Hospital ER_Data'[Patient Id])
  ```
- **Average Wait Time by Department**:  
  ```DAX
  Avg. Wait Time = AVERAGE('Hospital ER_Data'[Patient Waittime])
  ```
- **No. of Patients Referred**:  
  ```DAX
  No. of Patients Referred = CALCULATE(COUNTROWS('Hospital ER_Data'),'Hospital ER_Data'[Department Referral] <> "None"
      )
  ```
- **Waittime Interval**:  
  ```DAX
  Waittime Interval = SWITCH(TRUE(),
                     'Hospital ER_Data'[Admission Hour] < 2, "00-02",
                     'Hospital ER_Data'[Admission Hour] < 4, "03-04",
                     'Hospital ER_Data'[Admission Hour] < 6, "05-06",
                     'Hospital ER_Data'[Admission Hour] < 8, "07-08",
                     'Hospital ER_Data'[Admission Hour] < 10, "09-10",
                     'Hospital ER_Data'[Admission Hour] < 12, "11-12",
                     'Hospital ER_Data'[Admission Hour] < 14, "13-14",
                     'Hospital ER_Data'[Admission Hour] < 16, "15-16",
                     'Hospital ER_Data'[Admission Hour] < 18, "17-18",
                     'Hospital ER_Data'[Admission Hour] < 20, "19-20",
                     'Hospital ER_Data'[Admission Hour] < 22, "21-22",
                     'Hospital ER_Data'[Admission Hour] < 24, "23-24",
                     "Above 24"
      )
  ```
- **Custom Age Group Column**:  
  ```DAX
  Age Group = SWITCH(TRUE(),
              'Hospital ER_Data'[Patient Age] >= 100, "100+",
              'Hospital ER_Data'[Patient Age] >= 90, "90-99",
              'Hospital ER_Data'[Patient Age] >= 80, "80-89+",
              'Hospital ER_Data'[Patient Age] >= 70, "70-79",
              'Hospital ER_Data'[Patient Age] >= 60, "60-69",
              'Hospital ER_Data'[Patient Age] >= 50, "50-59",
              'Hospital ER_Data'[Patient Age] >= 40, "40-49",
              'Hospital ER_Data'[Patient Age] >= 30, "30-39",
              'Hospital ER_Data'[Patient Age] >= 20, "20-29",
              'Hospital ER_Data'[Patient Age] >= 10, "10-19",
              "0-9"
      )
  ```

---

## 🚀 How to Use This Project  

### 1️⃣ **Download the Dataset**  
- Get the raw **CSV file** (`Hospital ER_Data.csv`) from the repository.  

### 2️⃣ **Open in Power BI**  
- If you have **Power BI**, open the `PowerBI_Dashboard.pbix` file.  

### 3️⃣ **Explore the Dashboard**  
- View interactive reports:  
  - **1) Monthly View**  
  - **2) Consolidated View**  
  - **3) Patient Deatils**  
  - **4) Key Takeaways**

---

## 📬 Let's connect.

- 📧 Email: sundrammishra5556@gmail.com
- 🔗 LinkedIn: https://www.linkedin.com/in/sundrammishra55/  

---

🔹 **If you find this project useful, please ⭐ Star this repository!** 🚀  

---
