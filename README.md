# etl-project
crowdfunding-etl

Project Overview

This project demonstrates the process of building an ETL (Extract, Transform, Load) pipeline for a crowdfunding dataset using Python, Pandas, and SQL. The pipeline extracts data from Excel files, transforms it into structured formats, and loads it into a PostgreSQL database. The goal is to create a well-defined relational database for analyzing crowdfunding campaigns.

Table of Contents
	1.	Project Goals
	2.	Technologies Used
	3.	ETL Pipeline
	    •	Category and Subcategory DataFrames
	    •	Campaign DataFrame
	    •	Contacts DataFrame
	4.	Database Design
	5.	Outputs
	6.	Credits

Project Goals
	1.	Extract: Load data from Excel files.
	2.	Transform: Clean and restructure the data to create meaningful DataFrames.
	3.	Load: Create a PostgreSQL database and populate it with the transformed data.

Technologies Used
	•	Python (Pandas, NumPy, Regex)
	•	Jupyter Notebook
	•	PostgreSQL
	•	SQLAlchemy
	•	QuickDBD (for ERD diagram)

ETL Pipeline

1. Category and Subcategory DataFrames
Process:
	•	Extracted category and subcategory information from the Excel file crowdfunding.xlsx.
	•	Created unique IDs (category_id and subcategory_id) for categories and subcategories.
	•	Exported the cleaned DataFrames as category.csv and subcategory.csv.
2. Campaign DataFrame
Process:
	•	Extracted campaign data from crowdfunding.xlsx.
	•	Cleaned and transformed columns:
	•	Renamed blurb to description.
	•	Converted goal and pledged to float data types.
	•	Converted timestamps (launched_at and deadline) to datetime format.
	•	Mapped category_id and subcategory_id using the Category and Subcategory DataFrames.
	•	Exported as campaign.csv.
3. Contacts DataFrame
Process:
	•	Extracted contact_id, name, and email using regex from contacts.xlsx.
	•	Split name into first_name and last_name.
	•	Exported as contacts.csv.

Database Design

Entity-Relationship Diagram (ERD):
The ERD was created using QuickDBD to define the relationships between the tables.
	•	Tables:
	    1.	category
	    2.	subcategory
	    3.	campaign
	    4.	contacts
	•	Relationships:
	    •	campaign table references:
	        •	category_id from category.
	        •	subcategory_id from subcategory.
	        •	contact_id from contacts.
	•	Schema File: See crowdfunding_db_schema.sql for the complete schema.

Outputs
	1.	CSV Files:
	    •	category.csv
	    •	subcategory.csv
	    •	campaign.csv
	    •	contacts.csv
	2.	SQL Database:
	    •	PostgreSQL database crowdfunding_db with all tables populated.

Credits

This project was developed by Elizabeth Conn. It is part of the ETL mini-project to learn data extraction, transformation, and loading techniques.