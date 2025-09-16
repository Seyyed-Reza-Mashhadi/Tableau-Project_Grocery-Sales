<h1 align="center">Grocery Sales Dashboard in Tableau</h1>  

<p align="center">
  <img src="https://github.com/user-attachments/assets/7d19a203-e2f7-4a63-a6bd-526a867b633e">
</p>

## 🧩 About Project  

This project showcases an interactive **Tableau dashboard** built on the same grocery sales dataset from Kaggle used in my previous [Power BI project](https://github.com/Seyyed-Reza-Mashhadi/PowerBI-Project_Grocery-Sales).  

While the Power BI version was focused on answering business questions, this Tableau project is primarily designed to explore Tableau’s features — such as dashboard design, navigation, interactivity, and **Tableau Prep Builder** workflows. The result is a two-page mini-dashboard:  
- A Home Dashboard that mirrors the Power BI version for consistency and cross-tool comparison.  
- An Employee Dashboard that dives into employee performance metrics and demographics.  

🔗 **Dataset:** The raw CSV files are available on [Kaggle](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14). Unlike the Power BI project (which used a PostgreSQL database), this Tableau project is built directly on raw CSV files in order to explore and demonstrate the features of Tableau Prep Builder.

## 💡 Objectives  

Unlike the Power BI dashboard, which had explicit business-analysis goals, this Tableau project has slightly different objectives:  
- **Explore Tableau Prep Builder** and demonstrate its use for ETL workflows  
- **Build an interactive Tableau dashboard**:
  - Replicating the Power BI homepage dashboard to enable direct comparison between the two tools  
  - Highlight features such as navigation buttons, interactive filters, and cross-dashboard linking  

## 🛠️ Data Preparation with Tableau Prep Builder  

To explore Tableau Prep Builder, I used raw CSVs in this project instead of a PostgreSQL database or Azure SQL Database. Tableau Prep Builder was used to design a **data flow** to prepare a dataset with a star schema suitable for data analytics:  

- Removed duplicates, standardized column names, and corrected data types (dates, numeric fields).  
- Joined `cities` and `countries` tables to `customers` and `employees`. Also joined `categories` to `products`. This resulted in three dimension tables and a fact table.  
- Created calculated fields such as full employee names.  
- Saved clean, analysis-ready data outputs (e.g., `.hyper` or `.csv`) in a specified directory, which were then imported into Tableau for analysis.  

<br>
<p align="center"><em>Screenshots from Tableau Prep Builder</em></p>
<table align="center">
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/848e1517-2946-4181-ad21-7bf7b280fdf7" width="250" style="border: 2px solid black;">
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/e7468a77-6836-42a9-9c31-83fa2e2eb52d" width="600" style="border: 2px solid black;">
    </td>
  </tr>
</table>

## 📈 Data Analytics with Tableau  

### 📥 Data Import  
A connection was created to the cleaned files generated in Tableau Prep Builder. In the **Data Source** tab, the fact table was dragged onto the canvas first, followed by the dimension tables. Primary and foreign keys were then checked to ensure proper relationships, with many-to-one links defined between the sales fact table and the dimensions. Note that all tables and their connections were defined in the **logical layer** of Tableau.

<p align="center">
  <img src="https://github.com/user-attachments/assets/b4110d27-5ead-452c-ac85-fe37d380f9d7" width="600">
</p>

### 🎨 Dashboard Design  

A consistent color theme was applied to ensure visual harmony. Two dashboards are designed in this project as follows:

- **Home Dashboard** replicates the Power BI homepage to enable direct comparison between the two tools. This page confirms consistency of values across tools and shows Tableau’s ability to recreate the same analytical story. Key elements include:  
  - KPIs: Total revenue, number of transactions, number of items sold, Average Order Value (AOV), and Average Basket Size.  
  - Monthly revenue trend over the 128 days of sales, complemented by a table showing number of transactions, items sold, and revenue per month.  
  - Pie chart showing revenue by different product classes.  

<br>
<p align="center"><em>Open the gif below to see the interactive dashboard in Tableau</em></p>

![Recording 2025-09-15 233411](https://github.com/user-attachments/assets/0be0cc18-3740-4759-b457-cd6b6d2bc930)  

- **Employee Dashboard** includes:  
  - Scatter plots of employee experience vs. revenue and employee age vs. revenue, with a **reference line** showing the median of "total revenue generated per employee". These plots show little variability in revenue between employees, suggesting that neither age nor experience is a strong factor in sales performance.  
  - Top 5 Employees Table showing best-performing employees ranked by revenue.  
  - Gender distribution pie chart showing that most employees are male.  

<p align="center">
  <img src="https://github.com/user-attachments/assets/505a28cb-9c25-4ebb-a6d7-a261fdce260d" width="700" > 
</p>

**Navigation Note:**
A **button** is placed on the top-right corner to switch between the Home and Employee dashboards. Custom icons and **tooltip** text were added to make navigation more user-friendly.  

<br>
<p align="center"><em>Example of dashboard navigation</em></p>

![drillthrough](https://github.com/user-attachments/assets/384d5356-3a9f-4bff-98f2-e4822b96ede3)  

## 📝 Conclusions
### 🔑 Summary of Key Findings  

- Total revenue, Average Order Value, and Average Basket Size are consistent with the Power BI project, confirming data accuracy.  
- Monthly revenue and sales follow a relatively steady pattern over time.  
- Employee Insights:  
  - No significant correlation between employee age/experience and revenue generated.  
  - Revenue distribution among employees is relatively even.  
  - Male employees make up the majority of the workforce.  

### 🔍 Tableau vs. Power BI Comparison 

This project provided an opportunity to reflect on the strengths and trade-offs of Tableau compared to Power BI.  

- **Data Preparation**:  
  - In Power BI, **Power Query Editor** is embedded and automatically loads cleaned data into the model.  
  - In **Tableau Prep Builder**, cleaned outputs must be saved separately (e.g., as `.csv` or `.hyper`) and then imported into a Tableau workbook. This adds extra steps and requires additional storage. However, Tableau Prep Builder offers a visually intuitive, flow-based interface for ETL processes, similar to dataflows in Azure Data Factory, making data cleaning and preparation more transparent and easier to follow.

- **Data Modeling**:  
  - Tableau supports both **logical** and **physical** layers. This allows flexible handling of datasets that don’t follow strict schemas.  
  - Power BI enforces stricter star/snowflake schema relationships, which ensures data integrity but offers less flexibility in unusual data models.  

- **Dashboard Design & Visualization Flexibility**:  
  - Tableau generally offers **greater freedom in design**, making it easier to build more complex or highly customized charts and polished dashboards.  
  - Power BI favors **structured layouts and quick deployment** of standard visuals, which can save time but sometimes limits design flexibility.  

- **Ease of Use & Learning Curve**:  
  - Power BI is **more user-friendly** and easier to learn, with smoother integration into the Microsoft ecosystem.  
  - Tableau offers deeper customization but comes with a **steeper learning curve**, especially for advanced calculations and interactions.  

- **Pricing**:  
  - Power BI Pro costs **around $10 per user/month**, making it affordable for individuals and small teams.  
  - Tableau Creator licenses are **about $70 per user/month**, with additional costs for Explorer and Viewer roles.  

- **Advanced Analytics & Features**:  
  - Tableau is often stronger in data visualization flexibility, storytelling, and interactivity.  
  - Power BI integrates better with Azure services.  

**In Summary**:  
- Tableau excels in **visualization depth, design freedom, and flexible data modeling**, making it well-suited for advanced analytics teams or organizations needing high customization.  
- Power BI is stronger in **cost efficiency, ease of use, and Microsoft ecosystem integration**, making it a practical choice for many businesses.  

## 🔁 Related Projects  

- 📊 [**Power BI Project**](https://github.com/Seyyed-Reza-Mashhadi/PowerBI-Project_Grocery-Sales): Full analytical exploration of the same dataset with detailed insights.  
- 🗄️ [**SQL Project**](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales): PostgreSQL database design and analytical SQL queries forming the data backbone of the Power BI dashboard.  

## 📦 Tableau File Availability  

The Tableau workbook (`.twbx`) and Prep Builder flow file are not included in the repository due to size constraints. Please contact me if you would like access to them.  
