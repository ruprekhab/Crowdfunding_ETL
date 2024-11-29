# ETL Mini Project: Crowdfunding Data Analysis

## Authors: Ruprekha Baruah, Vidushi Bundhooa, Rushad Confectioner
## Setup:
To download the required libraries, run the following in your console:
* pip install -r installed_packages.txt

## Introduction
This ETL mini project demonstrates the implementation of an ETL pipeline using Python, Pandas, and regular expressions to extract, transform, and load crowdfunding data. The pipeline extracts data from Excel files, transforms it into well-structured DataFrames, and saves them as CSV files. These CSV files were then used to create an Entity-Relationship Diagram (ERD), a database schema, and populate a PostgreSQL database.

## Files and Folders
### 1. Resources Folder
This folder contains all input and output files used in the project:
* **CSV Files**: Generated from the DataFrames, used for creating the database schema.
   * campaign.csv
   * category.csv
   * contacts.csv
   * subcategory.csv
* **Excel Files**: Raw data files imported for transformation.
   * contacts.xlsx
   * crowdfunding.xlsx

### 2. Scripts
* **ETL_Mini_Project_RBaruah_VBundhooa_Rconfectioner.py**: Contains the Python script to extract, transform, and export data as CSV files.

### 3. Database schema and ERD
   * **crowdfunding_db_schema.sql**: PostgreSQL database schema defining the table structure.
   * **database_ERD.png**: Entity-Relationship Diagram of the database.

## Workflow
This project is divided into four main parts:
### Part 1: Create the Category and Subcategory DataFrames
**Steps**:
* Extracted data from crowdfunding.xlsx to create a Category DataFrame with:
   * category_id: Unique IDs (e.g., "cat1", "cat2", …).
   * category: Titles of each category.
   * Created a Subcategory DataFrame with:
   * subcategory_id: Unique IDs (e.g., "subcat1", "subcat2", …).
   * subcategory: Titles of each subcategory.
* Exported category.csv and subcategory.csv to the repository.
### Part 2: Create the Campaign DataFrame
**Steps**:
* Extracted and transformed data from crowdfunding.xlsx to create a Campaign DataFrame with columns:
   * The "cf_id" column
   * The "contact_id" column
   * The "company_name" column
   * The "blurb" column, renamed to "description"
   * The "goal" column, converted to the float data type
   * The "pledged" column, converted to the float data type
   * The "outcome" column
   * The "backers_count" column
   * The "country" column
   * The "currency" column
   * The "launched_at" column, renamed to "launch_date" and with the UTC times     converted to the datetime format
   * The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format
   * The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame
   * The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame 
   * Exported the DataFrame as campaign.csv. 
   
### Part 3: Create the Contacts DataFrame Using Regular Expressions
**Steps**:
   * Imported contacts.xlsx into a DataFrame
   * Extracted contact_id, name, email using regular expressions
   * Split the name column into first_name and last_name
   * Converted contact_id into integer format
   * Exported the DataFrame as contacts.csv
 
### Part 4: Create the Crowdfunding Database
**Steps**:
   * Designed an ERD using QuickDBD based on the transformed data
   * Created a database schema in crowdfunding_db_schema.sql
   * Set up a PostgreSQL database (crowdfunding_db) and tables using the schema
   * Imported CSV files into corresponding SQL tables 
     

## Summary
This project highlights the complete ETL process from data extraction and transformation to database population. It uses Python, PostgreSQL, and visualization tools to manage and structure data effectively. The database can now be queried for insights, enabling further analysis of crowdfunding campaigns.

## Technologies Used:
   * Languages: Python, SQL
   * Libraries: Pandas, Regular Expressions
   * Database: PostgreSQL
   * Tools: QuickDBD for ERD, Excel for raw data
   


 