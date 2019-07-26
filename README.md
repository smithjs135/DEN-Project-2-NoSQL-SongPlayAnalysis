# **Sparkify -** Song Play Analysis

Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.

## Introduction
Sparkify recently released a music streaming application and they strongly desire to increase their appeal to customer.  The analytics team provided JSON logs which track user activity and JSON metadata which contain data related the songs that are currently available on the application.  The analytics team is particularly interested in understanding what songs users are listening to. 

## Database schema desing
The data is stored in a star schema on a dedicated Postgres database.  This approach was determined ideal with the following considerations in mind:
- Small data volume
- fast query aggregation
- Low to moderate level of query complexity
- Moderate level of data integrity is required

**Fact table:** Songplays contains reference links Dimension tables 

**Dimension tabes:** users, songs, artists, time

## ETL pipeline

Selected data for the **songs** and **artists** table was extracted from song_data metadata files(JSON). 
Selected data for the **users** and **time** tables was extracted from log_data files(JSON). 

## Summary

**sql_queries.py** contents:
- Create and drop database table scripts
- Data import scripts

**create_tables.py** contents:
- Running this script will call sql_queries.py and create tables and content

**etl.ipynb** contents:
- ETL of small sample sets 

**etl.py** contents:
- ETL of all datae sets

**test.ipynb** contents:
- Database connection and queries 
- Data analytics output

**Libraries used:**
- os
- glob
- psycopg2
- pandas

**Database utilized:**
- DB name: sparkifydb
- IP: 127.0.0.1

## Run the following steps in Python3 to repopulate and analyze the data 
1. create_tables.py
2. etl.ipynb / etl.py
3. test.ipynb
