# Crowdfunding ETL Pipeline

![ETLdiagram](Resources/etl_pic.png)

## Overview
This project is aimed to get a better understanding of the ETL pipeline. In this project we built an ETL pipeline utilizing Python, Pandas, and Python dictionary methods to extract and transform the data. After this process, we created 4 CSV files, and used the CSV files to create an ERD and a table schema. The CSV files were then uploaded into a Postgres database. 

## Contributors
- Julia Liou
- Oguz Kilicarslan

## Resources

- [crowdfunding](Resources/crowdfunding.xlsx)
- [contacts](Resources/contacts.xlsx)

### Software utilized:
Jupyter Notebooks, Pandas, Numpy, PostGresSQL, QuickDBD, pgAdmin4

## Data Extraction and Transformation 

File location for code: [ETL Mini Project](ETL_Mini_Project_JLiou_OKilicarslan.ipynb)

### Category DataFrames
- A DataFrame is created for categories.
- The DataFrame contains a "category_id" column with sequential entries from "cat1" to "catn" for unique categories.
- The DataFrame has a "category" column that contains only the category titles.
- The category DataFrame is exported as [category.csv](Resources/category.csv).

### Subcategory DataFrame
- A DataFrame is created for subcategories.
- The DataFrame contains a "subcategory_id" column with sequential entries from "subcat1" to "subcatn" for unique subcategories.
- The DataFrame contains a "subcategory" column that contains only the subcategory titles.
- The subcategory DataFrame is exported as [subcategory.csv](Resources/subcategory.csv).

### Campaign Dataframe 
- A DataFrame is created for campaigns.
- The DataFrame includes various columns such as "cf_id", "contact_id", "company_name", "description", "goal", "pledged", "outcome", "backers_count", "country", "currency", "launch_date", "end_date", "category_id", and "subcategory_id".
- The "launch_date" and "end_date" columns are formatted as "YYYY-MM-DD".
- The campaign DataFrame is exported as [campaign.csv](Resources/campaign.csv).

### Contacts DataFrame
- A DataFrame is created for contacts.
- The DataFrame includes columns for "contact_id", "first_name", "last_name", and "email".
- The contacts DataFrame is exported as [contacts.csv](Resources/contacts.csv).

## Database Creation and Import
### Crowdfunding Database
- Utilizing the 4 CSV files created, we created a ERD:
![ERD](<Resources/ERD - crowdfunding_db.png>)

- We created a table schema for each CSV file (which includes the primary keys, foreign keys, and other constraints)
- The Database schema is created as a Postgres file named [crowdfunding_db_schema.sql ](crowdfunding_db_schema.sql)
- A new Postgres database was created: crowdfunding_db with tables for campaign, category, subcategory, and contacts 
- We can import each CSV file into it's corresponding SQL table
- We can verify that each table has the correct data by running a SELECT statement for each. (See screenshots utilizing the SELECT statement for each table in [ SQL_screenshots](SQL_screenshots) for your reference.) 

## Usage
To run the ETL pipeline and populate the PostgreSQL database:

- Ensure you have Python and the required dependencies installed.
- Execute the [Jupyter Notebook](ETL_Mini_Project_JLiou_OKilicarslan.ipynb) containing the ETL pipeline code.
- Verify that the CSV files (contacts, campaign, category, subcategory) are created and the PostgreSQL database is populated.
- Use SELECT statements to retrieve and analyze the data from the database.