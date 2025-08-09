~~~ SQL
-- Average charges by age group
SELECT 
    CASE 
        WHEN age < 25 THEN '18-24'
        WHEN age < 35 THEN '25-34'
        WHEN age < 45 THEN '35-44'
        WHEN age < 55 THEN '45-54'
        ELSE '55+'
    END as age_group,
    AVG(charges) as avg_charges,
    COUNT(*) as count
FROM medical_data_dataset 
GROUP BY age_group
ORDER BY avg_charges;
~~~
<img width="454" height="196" alt="age_vs_charges" src="https://github.com/user-attachments/assets/c3178f10-8614-444d-9d08-fe825037ef43" />

~~~ SQL
-- Correlation between age and charges
SELECT 
    (COUNT(*) * SUM(age * charges) - SUM(age) * SUM(charges)) / 
    (SQRT(COUNT(*) * SUM(age * age) - SUM(age) * SUM(age)) * 
     SQRT(COUNT(*) * SUM(charges * charges) - SUM(charges) * SUM(charges))) AS correlation_age_charges
FROM medical_data_dataset;
~~~
<img width="206" height="83" alt="corr_age_charges" src="https://github.com/user-attachments/assets/45972d3a-aee2-4bfd-bede-bd884e1b3a1d" />

There is a moderately positive correlation between age and medical costs.


~~~ SQL
-- Average charges by gender
SELECT sex, 
       AVG(charges) as avg_charges,
       COUNT(*) as count
FROM medical_data_dataset 
GROUP BY sex;
~~~
<img width="457" height="114" alt="gender_vs_charges" src="https://github.com/user-attachments/assets/a627d391-ca6a-4ba4-b7f4-b1bcae91bad2" />

Males on average have higher medical costs.


~~~ SQL
-- Average charges by BMI category
SELECT 
    CASE 
        WHEN bmi < 18.5 THEN 'Underweight'
        WHEN bmi < 25 THEN 'Normal'
        WHEN bmi < 30 THEN 'Overweight'
        ELSE 'Obese'
    END as bmi_category,
    AVG(charges) as avg_charges,
    COUNT(*) as count
FROM medical_data_dataset 
GROUP BY bmi_category
ORDER BY avg_charges DESC;
~~~
<img width="457" height="170" alt="bmi_vs_charges" src="https://github.com/user-attachments/assets/56acff96-f963-4336-9c5b-3f9e5ddc55ee" />

Obesity significantly increases medical costs.


~~~ SQL
-- Average charges by number of children
SELECT children, 
       AVG(charges) as avg_charges,
       COUNT(*) as count
FROM medical_data_dataset 
GROUP BY children
ORDER BY children;
~~~
<img width="455" height="227" alt="children_vs_charges" src="https://github.com/user-attachments/assets/f1439d79-436e-4d11-83a0-862246e6a262" />

~~~ SQL
-- Correlation between number of children and charges
SELECT 
    (COUNT(*) * SUM(children * charges) - SUM(children) * SUM(charges)) / 
    (SQRT(COUNT(*) * SUM(children * children) - SUM(children) * SUM(children)) * 
     SQRT(COUNT(*) * SUM(charges * charges) - SUM(charges) * SUM(charges))) AS correlation_children_charges
FROM medical_data_dataset;
~~~
<img width="234" height="86" alt="corr_children_charges" src="https://github.com/user-attachments/assets/2041b476-5bad-4999-930b-17e10b95cdb3" />

There is virtually no correlation between number of children and medical costs. 


~~~ SQL
-- Average charges by region
SELECT region, 
       AVG(charges) as avg_charges,
       COUNT(*) as count
FROM medical_data_dataset 
GROUP BY region
ORDER BY avg_charges DESC;
~~~
<img width="457" height="139" alt="region_vs_charges" src="https://github.com/user-attachments/assets/4a0ae0c4-8834-4096-8ab0-734a23c75f53" />

Southeast Region has the highest average medical costs.


~~~ SQL
-- Average charges by smoker
SELECT smoker, 
       AVG(charges) as avg_charges,
       MIN(charges) as min_charges,
       MAX(charges) as max_charges,
       COUNT(*) as count
FROM medical_data_dataset    
GROUP BY smoker;
~~~
<img width="757" height="114" alt="smoker_vs_charges" src="https://github.com/user-attachments/assets/9f6ba2ac-3e94-4d4f-b369-fa1928159e11" />

Smoking is the biggest cost driver with almost a 400% increase on average.


Bonus Analysis:
~~~ SQL
-- Smoking + BMI combination
SELECT 
    smoker,
    CASE WHEN bmi >= 30 THEN 'Obese' ELSE 'Not Obese' END as obesity_status,
    AVG(charges) as avg_charges,
    COUNT(*) as count
FROM medical_data_dataset 
GROUP BY smoker, obesity_status
ORDER BY avg_charges DESC;
~~~
<img width="608" height="170" alt="smoker_obese_vs_charges" src="https://github.com/user-attachments/assets/3e533fa3-996f-4f92-aa26-83a4e9f394df" />

Non-obese smoker has almost 300% more medical costs than an obese non-smoker.

Medical costs of obese smoker almost doubles non-obese smoker.

Smoking + Obesity = Extremely high costs

