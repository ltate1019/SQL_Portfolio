#Assign a query to see the number of employees at each company in the technology or finance fields 
#where the revenue is greater than or equal to 200 to see the correlation between number of employees 
#and revenue. 
#In technology the highest number of employees directly correlates to the highest amount of revenue
#In finance the lowest amount of employees correlates to the highest amount of revenue. 

SELECT employees, company_name, industry, revenue
FROM fortune_companies
WHERE industry = 'Technology' 
OR industry = 'Finance'
AND revenue >=200
ORDER BY employees;

#Assign a rating to the amount of PTO days an employee receives as 'Excellent 
#PTO' (>/=20 days), 'Great PTO' (>/=15 days), 'Substandard" (<15 days). 
#Comparing the technology and finance fields, all technology companies have an
#'Excellent PTO' rating, whereas, all finance companies have a 'Substandard' rating. 

SELECT company_name, industry,
CASE 
  WHEN paid_time_off_days >= 20 THEN 'Excellent PTO'
  WHEN paid_time_off_days >= 15 THEN 'Good PTO'
  ELSE 'Substandard'
  END AS pto_rating
FROM fortune_companies
WHERE industry = 'Technology' OR industry = 'Finance'; 

#Identify the industry with the maximum and minimum number of PTO days.
#It is interesting to note that finance has the minimum number of PTO days out 
#of all industries while technology has the maximum number of PTO days out of
#all industries. 
SELECT company_name, industry, MAX(paid_time_off_days)
FROM fortune_companies; 

SELECT company_name, industry, MIN(paid_time_off_days)
FROM fortune_companies; 

#Which industry offer both at least 10 weeks of maternity and healthcare benefits? 
#Technology offers the highest amount of maternity leave while also offering benefits. 
SELECT industry, ROUND(AVG(maternity_leave_weeks), 1)
FROM fortune_companies
GROUP BY industry
HAVING healthcare_benefits = 1
AND maternity_leave_weeks >= 10;
