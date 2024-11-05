# Toyota Car Reviews Data Analysis

🎯 The aim of this project is to extract insights from Edmund car reviews.


The repository contains all related files in my portfolio.

The data is driven from the Edmunds Kaggle dataset, which contains customer reviews from 50 different car brands.
This project focuses merely on Toyota review data. The original data has more than 18 thousand rows and six columns. 

## 📋Data Pipeline

### 📌1. Data Preprocessing (Roughly 50-60% of workload)

**🩺 1.1 Quick Data Diagnosis - Check for any issues with the original data by screening it with Excel.**

   🔍 There are empty values in the review column.
   
   🔍 Parts of reviews in the Review column were split into a few following rows in the first column; therefore, it leads to more than extra redundant 4000 rows. Deleting data might be quite risky as some insights won't be discovered or affect other insights and analyses. As I estimate, the time to complete this cleaning task manually is 4 hours (20 seconds for each row; each review error contains 1-5 redundant rows). With in-depth analysis, I will perform full cleaning. I will perform general data analysis for this data, so I opted out of this cleaning task.

   🔍 Values in the Review_Date column contain both date and time published reviews. Ex: on 02/02/17 19:53 PM (PST). The date values are in 24-hour format, so I don't keep PM or AM values.

   🔍 In the Vehicle_Title colunn
   
   ![image](https://github.com/user-attachments/assets/b47b3093-a08c-441b-af82-5d8b94634086)

The values contain something like this: 2007 Toyota Avalon Sedan Limited 4dr Sedan (3.5L 6cyl 5A). There is valuable information such as year_made, Model, body type, version, number of doors, and engine.
   

**⚕️1.2 Treatment**

**1.2.1 Clean the redundant texts appearing in a few rows of the first column by moving them into their belonging text above.**
  
  💊 Using Excel to delete rows with empty values in a specific column, Ctrl + G -> Special -> Select Blank -> Right-click highlighted cell -> Select delete rows. 

**1.2.2 Make two new columns to separate values in the Review_Date column into date and time**

 💊 Use the Excel MID function to extract date and time values.

 💊 Change values in the Date column to Date format DD/MM/YY by selecting Data-> Text to column -> Date

**🧬1.3 Transformation**
 
 -> Iterate the process to thoroughly extract the model, body type, version, and engine. The final data would look neat and tidy. 
 
 
 ![image](https://github.com/user-attachments/assets/5f560162-09bd-4fd4-a218-82ebfe2d19db)

  -> Apply filters in Excel to identify issues( missing data and wrong values) in the 4 columns

💊 Assign Regular Cab|CrewMax Cab|Xtracab|Extended Cab|Access Cab|Double Cab to "Cab" in Body_type as those are all cabs body.

💊 Use the if function to extract version information as it appears between Body type and number of doors.

💊 Use re.search () function to extract engine information that appears inside parentheses ()


### 📌2. SQL Queries for negative reviews
-> MySQL is used to run through 10 queries to find insights from negative reviews.

**💡Takeaways:**

➢  Each car model has different prevalent complaints. For example: the Camry has a lot of complaints about interior quality, waranty and service complaints while the Tacoma has the most complaints about Transmission and Fuel Economy, AC & Heating.

➢ Warranty, service, and interior are the main factors causing frustration for
customers.

➢ Each year, each car model has different major issues.

➢ The more popular a car is, the more likely it is to receive negative reviews.

### 📌3. Data Visualization

**📊3.1. Visualize plots**

☑️ Load data to Power BI Desktop
  
**💡Takeaways:**
* XYZ

**🔮3.2. 3D-Visualization**


**Key points from 3D Visualizations (Package: Plotly):**
- The majority of negative reviews range from 2.5 to 3.5.
- Sienna and Corrolla are 2 Toyota models that received more intense negative reviews (2 -2.5 ~ orange, brown) than others. 
