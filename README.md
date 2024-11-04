# Toyota Car Reviews Data Analysis
The repository contains all related files in my portfolio

The data is driven from the Edmunds Kaggle dataset, which contains customer reviews from 50 different car brands.
This project focuses merely on Toyota review data. The original data has more than 18 thousand rows and six columns. 

## 📋Data Pipeline: 

### 📌1. Data Preprocessing

**🩺 Quick Data Diagnosis - Check for any issues with the original data by screening it with Excel.**

   🔍 There are empty values in the review column.
   
  🔍 Parts of reviews in the Review column were split into a few following rows in the first column; therefore, it leads to more than extra redundant 4000 rows. Deleting data might be quite risky as some insights won't be discovered or affect other insights and analyses. As I estimate, the time to complete this cleaning task manually is 4 hours(20 seconds for each row; each review error contains 1-5 redundant rows).

**⚕️ Treatment**
* Clean the redundant texts appearing in a few rows of the first column by moving them into their belonging text above.
  
  💊 Using Excel to delete rows with empty values in a specific column, Ctrl + G -> Special -> Select Blank -> Right-click highlighted cell -> Select delete rows. 


**🧬 Transformation**

**Key points from 3D Visualizations (Package: Plotly):**
- The majority of negative reviews range from 2.5 to 3.5.
- Sienna and Corrolla are 2 Toyota models that received more intense negative reviews (2 -2.5 ~ orange, brown) than others. 
