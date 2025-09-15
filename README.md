<h1 align="center">Grocery Sales Dashboard in Tableau</h1>  

<p align="center">
  <img src="https://github.com/user-attachments/assets/7d19a203-e2f7-4a63-a6bd-526a867b633e">
</p>

## 🧩 About Project  

This project showcases an interactive Tableau dashboard built on the same grocery sales dataset from Kaggle used in my previous [Power BI project](https://github.com/Seyyed-Reza-Mashhadi/PowerBI-Project_Grocery-Sales).  

While the Power BI version was focused on answering business questions, this Tableau project is primarily designed to explore Tableau’s features — such as dashboard design, navigation, interactivity, and Prep Builder workflows.  The result is a two-page mini-dashboard:  
- A **Home Dashboard** that mirrors the Power BI version for consistency and cross-tool comparison.  
- An **Employee Dashboard** that dives into employee performance metrics and demographics.  

🔗 **Dataset:** The raw CSV files are available on [Kaggle](https://www.kaggle.com/datasets/155a87ba8d7e92c5896ddc7f3ca3e3fa9c799207ed8dbf9a1cedf2e2e03e3c14). Unlike the Power BI project (which used a PostgreSQL database), this Tableau project is built directly on **cleaned and transformed CSVs** using Tableau Prep Builder.  

## 💡 Objectives  

Unlike the Power BI dashboard, which had explicit business-analysis goals, this Tableau project has slightly different objectives:  
- Showcase the use of **Tableau Prep Builder** for ETL workflows with raw CSV files
- Compare Tableau and Power BI dashboards by replicating the homepage dashboard in Tableau
- Explore Tableau features such as navigation buttons, interactive filters, and cross-dashboard linking 
- Build an Employee-focused dashboard highlighting performance and demographics (not presented in Power BI project)

## 🛠️ Data Preparation with Tableau Prep Builder  

To explore Tableau Prep Builder, I used raw CSVs in this project instead of a postgreSQL database, or Azure SQL Database. Tableau Prep Builder was used to design a **data flow** with the following steps:  

- Removed duplicates, Standardized column names, and corrected data types (dates, numeric fields).  
- Joined cities and countries tables to customers and employees. Also, joined categories to products. This resulted in three dimension tables and a fact table with a star schema ideal for data analytics purposes.

- Created calculated fields such as full employee names.  
- saved clean, analysis-ready data as ".hyper" format in a specified directory. (i want to later mention later at the conclusions or sth that power query editor in power BI seems to be better in that sense that you dont need to save data and import it to tableau. This means you need further disk space, also, if you do a simple update or sth, you need to run, save, and ... which makes an extra step. However, tabluea prep builder is visually pleasing and it provides an easy data cleaning workflow, similar to dataflows in azure data factor ) 

<br>
<p align="center"><em>Screenshots from Tableau Prep Builder</em></p>
<table align="center">
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/848e1517-2946-4181-ad21-7bf7b280fdf7" width="250" alt="mobile_immobile_pairplot" style="border: 2px solid black;">
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/e7468a77-6836-42a9-9c31-83fa2e2eb52d" width="600" alt="Boxplot_sand" style="border: 2px solid black;">
    </td>
  </tr>
</table>

## 🎨 Dashboard Design and Interactivity  

### Home Dashboard 
The Home Dashboard replicates the Power BI homepage to enable direct comparison between the two tools. Key elements include:  
- KPIs: Total revenue, number of transactions, number of items sold, Average Order Value (AOV), and Average Basket Size.  
- Monthly revenue trend over the 128 days of sales. This is complemeted by a Table showing number of transactions, items sold, and revenue per month.   
- Pie chart showing revenue by different product classes.  

This page confirms consistency of values across tools and shows Tableau’s ability to recreate the same analytical story.  

<br>
<p align="center"><em>Open the gif below to see the interactive dashboard in Tabluea</em></p>
![Recording 2025-09-15 233411](https://github.com/user-attachments/assets/0be0cc18-3740-4759-b457-cd6b6d2bc930)

A button is designed on the top right corner to navigate from Home to Employee's Dashboard and vice versa. Specific icons  are used for the buttons to improve visualization in the dashboard, and tooltip text is added for the bottun to make it more user freindly.
<br>
<p align="center"><em>Open the gif below to see the interactive dashboard in Tabluea</em></p>
![drillthrough](https://github.com/user-attachments/assets/384d5356-3a9f-4bff-98f2-e4822b96ede3)

### Employee Dashboard  
The Employee Dashboard highlights Tableau’s flexibility for deeper visual exploration. It includes:  
- Employee experience vs.  revenue generated and  employee age vs. revenue generated scatter plots illustreted together with the median generated revenue line. These plots show that there is not much variability in generated revenue between employees, and all points lie close to the median trend line. This indicates that neither age or experience is an important factor in employees sales performance.  
- Top 5 Employees Table shows Best-performing employees ranked by generated revenue.  
- Gender Distribution Pie Chart shows that most of employees are male.   


## 🔑 Key Takeaways  

- The **Home Dashboard** validates Tableau’s ability to replicate the Power BI version with the same results and KPIs.  
- The **Employee Dashboard** showcases Tableau’s interactivity and layout flexibility, including navigation buttons.  
- Tableau Prep Builder played a central role in preparing raw CSVs for analysis, highlighting a full ETL workflow within the Tableau ecosystem.  
- While not designed for in-depth business analysis, the dashboards still allow exploration of key questions around revenue, products, and employee performance.  

---

## 🔁 Related Projects  

- 📊 [**Power BI Project**](https://github.com/Seyyed-Reza-Mashhadi/PowerBI-Project_Grocery-Sales): Full analytical exploration of the same dataset with detailed insights.  
- 🗄️ [**SQL Project**](https://github.com/Seyyed-Reza-Mashhadi/SQL-Project_Grocery-Sales): PostgreSQL database design and analytical SQL queries forming the data backbone of the Power BI dashboard.  

---

## 📦 Tableau File Availability  

The Tableau workbook (`.twbx`) and Prep Builder flow file are not included in the repository due to size constraints. Please contact me if you would like access to them.  
