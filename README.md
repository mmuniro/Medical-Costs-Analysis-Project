# Medical-Costs-Analysis-Project

## Executive Summary

This report presents an analysis of medical charges based on a dataset of 1,000 patient records. The analysis examines the relationship between medical charges and various demographic and health factors including age, gender, BMI, number of children, smoking status, and geographic region.

## Dataset Overview

- **Total Records**: 1,000 patient personal details
- **Key Variables**: Age, Sex, BMI, Children, Smoker Status, Region, Charges

## Objectives:
- Is there a correlation between age of patient and their medical charges?
- Which gender has highest medical costs?
- Does BMI impact medical costs?
- Is there a correlation between patient's number of children and their medical charges?
- Does being a smoker impact their medical costs?
- Which region has highest medical costs?

## Analysis:
### 1. Age Correlation
<img width="970" height="653" alt="age vs  charges scatter" src="https://github.com/user-attachments/assets/756564c4-40f6-4d7a-bac6-16c71c7969e5" />

**Key Findings:**
- Medical charges generally increase with age
- Older age groups (55+) show the highest average charges
- Moderately strong positive correlation (0.31) between age and medical costs

---

### 2. Gender with Highest Average Costs
<img width="820" height="622" alt="gender vs  avg costs" src="https://github.com/user-attachments/assets/4e4c1e42-b03f-4c2d-a723-fce4127146b2" />

**Key Findings:**
- Males have a higher average cost at $13968 and females at $12945
- Gender appears to have minimal impact on average insurance charges 

---

### 3. BMI Category Analysis
**BMI Categories Defined:**
- **Underweight**: BMI < 18.5
- **Normal**: BMI 18.5-24.9
- **Overweight**: BMI 25.0-29.9
- **Obese**: BMI ≥ 30.0
<img width="793" height="621" alt="bmi vs avg costs" src="https://github.com/user-attachments/assets/4416cbd6-ea35-4012-924e-2ee3d8059a8b" />

**Key Findings:**
- Obese individuals show significantly higher average medical costs at $15712
- Clear progression in charges from overweight to obese ($11058 to $15712)
- BMI is a significant predictor of medical costs

---

### 4. Family Size Correlation (Number of Children)
<img width="861" height="578" alt="children vs charges scatter" src="https://github.com/user-attachments/assets/4f0fe602-1888-4b35-8ce3-fbfea55d4e0f" />

**Key Findings:**
- Number of children shows weak correlation (0.08) with medical costs
- Family size has minimal impact on individual medical costs
- Most patients have 0-3 children

---

### 5. Geographic Regional Analysis
<img width="888" height="580" alt="region vs cost" src="https://github.com/user-attachments/assets/b085d37d-9bdc-418e-90a7-b85e8d551496" />

**Key Findings:**
- Regional variations in average medical costs exist
- Southeast region holds the highest average at $14.5K

---

### 6. Smoking Status - Major Cost Driver
<img width="868" height="555" alt="smoker vs non smoker" src="https://github.com/user-attachments/assets/dfd30b3b-204f-4aca-b7bd-7bdc9528b686" />

**Key Findings:**
- Smoking status is the **strongest predictor** of medical costs
- Smokers have dramatically higher average medical costs than non-smokers ($31.9K vs. $8.5K)
- Significant difference in minimum, maximum, and average charges between status

---

### 7. Combined Risk Factors: Smoking and BMI 
<img width="882" height="573" alt="smoker and bmi avg cost" src="https://github.com/user-attachments/assets/e0c78311-a66e-44fe-a6e7-b7d178d5c478" />

**Key Findings:**
- **Smoking + Obesity combination** represents the highest-cost group at $42K
- Obese smokers have substantially higher charges than any other category
- Non-obese non-smokers represent the lowest-cost group

