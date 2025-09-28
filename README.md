# Project Description

As part of this project, I worked on analyzing business data from the **classicmodels** database, which represents the operations of a retailer specializing in classic car models. This database provides detailed information about **customers**, their **orders**, their **payments**, as well as **products**, their **classification**, **employees**, and **offices**.

The main objective of the project was to **extract relevant insights** in order to better understand sales, employee performance, and revenue distribution. To achieve this:

* **Power Query** was used to **transform and clean** the data retrieved from the **MySQL** database.
* **Power BI** was used to model **table relationships**, create **interactive visualizations**, and design **dashboards**.
* **Python** was applied to perform **advanced statistical analyses**.
* **SQL** was used for complex **table joins**.  



![](/Ressources/Visuel.png)


# Repository Architecture


```plaintext

│   Objectifs_du_projet_Data_Analyse.pdf
│   README.md
│
├───Analyse statistique
│       Hypothesis_Testing.ipynb
│
├───Base de données MySQL
│       classicmodels.zip
│       Création_de_la_base_de_données.pdf
│       Description_Classic_model_Database.pdf
│
├───PowerBI
│       Analyse de vente et performances des employés et des clients.pbix
│
└───Ressources
        Visuel.png

```

# Report

### SQL


* Number of records in each table:

  * 23 employees
  * 7 offices
  * 122 customers
  * 326 orders
  * 273 payments
  * 2,996 order details
  * 110 products
  * 7 product lines

* There are **7 different job titles** (President, VP Sales, VP Marketing, Sales Manager (APAC), Sales Manager (EMEA), Sales Manager (NA), Sales Rep). The role of **Sales Rep** is the most common, with **17 occurrences**.

* The **offices** are located in **5 different countries** (United States, France, United Kingdom, Japan, Australia). There are **3 offices in the United States**, while each of the other countries has **only one office**.

* The **customers** are spread across **28 different countries**. **50% of them** are located in the **United States, Germany, and France**.

* The **orders** have **6 different statuses** (Shipped, Resolved, Cancelled, On Hold, Disputed, In Process). Out of the **326 orders**, **303 were shipped**.

---

### Power Query

* Removed columns (other than foreign keys) that referenced another table
* Renamed columns for clarity
* Verified and adjusted column data types
* Removed irrelevant columns such as **“image”** and **“htmlDescription”** from **productlines**
* Deleted empty rows and duplicates

---

### Power BI

* The product **“1992 Ferrari 360 Spider red”** stands out with around **50 units sold**, far above other products which range between 20 and 30 units.
* Two major revenue peaks were observed: around **November 2003** (close to $1M) and **November 2004** (slightly below $1M), indicating significant increases in sales during these periods.
* The customers **“Euro+ Shopping Channel”** and **“Mini Gifts Distributors Ltd.”** made the highest purchases.
* Customers are distributed worldwide, but most are based in the **USA (36)**, followed by **Germany (13)** and **France (12)**.
* **Leslie** and **Gérard** are the top-performing employees in terms of revenue.
* The office located in **Paris** generates the highest revenue.

---

### Statistical Analysis (Hypothesis Testing)

* We **cannot reject** the hypothesis that the average revenue between European and American offices is the same.
* We **can reject** the hypothesis that sales are similar across different product lines, meaning that product line significantly impacts sales.
