# Pewlett-Hackard-Analysis
Module 7
# Analyzing Employee data with SQL
## Overview of Project
This project is a SQL analysis of a large company's employee data in pgAdmin 4. The company, Pewlett-Hackard, is in the process of migrating their company data into a database with SQL, which takes place during this analysis. The initial datasets imported into pgAdmin 4 were 6 csv files; a spreadsheet of departments, and some employee spreadsheets consisting of hundreds of thousands of rows. From the six initial csv files, 12 new datasets are developed via joins between two or more datasets.
### Purpose
The purpose of this project is to design entity relationship diagram (ERD), assigning primary and foreign keys to 6 different employee data csv files imported into pgAdmin 4 in order to design new datasets. The new datasets designed are intended to assist management in determining upcoing company hiring procedures with respect to current expected employee retirement. In some cases, datasets are designed and filtered with respect to company department to satisfy respective department managers. Finally, three datasets are designed to show 1) retiring employees by company position, 2) total retiring employees for each company position, and 3) employees, with thier positions listed, eligible for training new hires.
## Results
### Deliverable 1
* A SQL query is written with an inner join from the employees.csv table on the title.csv table. The resulting table gives retiring employee by employee position. https://github.com/stereo-chemistry/Pewlett-Hackard-Analysis/blob/3469290c696e135901edd57993ff5c5ab744d521/Queries/Employee_Database_challenge.sql#L3-L10
* In order to resolve duplicate employee entries in retirement_titles.csv, a DISTINCT ON () method of selecting employee ID column data was used, sorting by descending to_date in order to capture each employee in their current position.
* Finally, a SELECT COUNT () method is used from the unique_titles.csv employee IDs, GROUPED BY employee position in order to determine the sums of retiring employees in each position.
* This dataset unique_titles.csv (cite) is useful to assist in determining upcoming hiring procedures in terms of job positions to be filled.
### Deliverable 2
* A SQL query is writtin with two inner joins from the employees.csv on dept_emp.csv and from employees.csv on titles.csv.
* The data is filtered by and exported to show, without duplicate, current employees.
* The data is further filtered to show employees born in the year 1965.
* The dataset serves as a spreadsheet of employees eligible for training new hires by employee position.
## Summary
In the dataset exported as retirement_emp_info.csv (link), we can see that are 33,118 current employees that will soon retire. Pewlett-Hackard will need to hire as many to keep these positions filled. In the mentorship_eligibility.csv (link), we can see that there are 1549 employees eligible to train the next generation of Pewlett-Hackard hires, suggesting each mentor would be responosible for training about 21 new hires- this could pose an issue for Pewlett-Hackard. To get a better idea of which departments will have the heaviest training loads, one query I'd advise running is the sums of eligible mentors by employee position to compare to the sums of retiring employees by employee position in unique_titles.csv (cite). In order to deal with a potentially difficult hiring/training process and transition, Pewlett-Hackard could consider additional management and a query for management elegibility.
