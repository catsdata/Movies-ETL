# Movies-ETL

<details><summary>Table of Contents</summary>
<p>

1. [Overview](https://github.com/catsdata/Movies-ETL#overview)
2. [Resources](https://github.com/catsdata/Movies-ETL#resources)
3. [Deliverables / Results](https://github.com/catsdata/Movies-ETL#deliverables)
    - [Deliverable 1](https://github.com/catsdata/Movies-ETL#deliverable-1-write-an-etl-function-to-read-three-data-files)
    - [Deliverable 2](https://github.com/catsdata/Movies-ETL#deliverable-2-extract-and-transform-the-wikipedia-data)
    - [Deliverable 3](https://github.com/catsdata/Movies-ETL#deliverable-3-extract-and-transform-the-kaggle-data)
    - [Deliverable 4](https://github.com/catsdata/Movies-ETL#deliverable-4-create-the-movie-database)
4. [Summary](https://github.com/catsdata/Movies-ETL#summary)

</p>
</details>

## Overview

Use ETL to Collect, Import, and Process Data

Create an ETL pipeline from raw data that can be updated daily into a SQL database for Amazing Prime movie hackathon.

## Resources

- Data Sources: 
    - [Wikipedia](https://github.com/catsdata/Movies-ETL/blob/main/Data/wikipedia-movies.json)
    - [Kaggle](https://github.com/catsdata/Movies-ETL/blob/main/Data/movies_metadata.csv)
    - [MovieLens](https://github.com/catsdata/Movies-ETL/blob/main/Data/ratings.csv)
- Software:  
    - Jupyter Notebook 6.4.6
    - Python 3.7.11 with dependencies: 
        - pandas 1.3.5
        - numpy 1.20.3
        - json 2.0.9
        - re 2.2.1
        - psycopg2 2.9.3 (dt dec pq3 ext lo64)
    - SQLAlchemy 1.4.31
    - PostgreSQL 12.9.1
    - pgAdmin 4
    

## Deliverables

### Deliverable 1: Write an ETL Function to Read Three Data Files

Code: [ETL_function_test.ipynb](https://github.com/catsdata/Movies-ETL/blob/main/ETL_function_test.ipynb)

- Imported dependencies
 
- Converted Wiki JSON to Pandas dataframe

  ![wiki](https://github.com/catsdata/Movies-ETL/blob/main/Images/wiki_movies_df.PNG)
 
- Converted Kaggle metadata file into Pandas dataframe

  ![kaggle](https://github.com/catsdata/Movies-ETL/blob/main/Images/kaggle_metadata_df.PNG)
 
- Converted Movielens data into Pandas dataframe

  ![movielens](https://github.com/catsdata/Movies-ETL/blob/main/Images/ratings_df.PNG)


### Deliverable 2: Extract and Transform the Wikipedia Data

Code: [ETL_clean_wiki_movies.ipynb](https://github.com/catsdata/Movies-ETL/blob/main/ETL_clean_wiki_movies.ipynb)

- Imported dependencies
 
- Cleaned wiki movies dataframe by:

    - filtered out TV shows
    - caught errors on ID's and dropped duplicates
    - removed nulls
    - created non-null Box Office column
    - cleaned data string formats for Box Office column; parsing dollars
    - cleaned budget column
    - cleaned release date column
    - cleaned runtime column
    - reviewed clean dataframe

        ![cleanwiki](https://github.com/catsdata/Movies-ETL/blob/main/Images/clean_wiki_movies_df.PNG)
 
    - reviewed updated column names
                
        ![cleancolumns](https://github.com/catsdata/Movies-ETL/blob/main/Images/clean_wiki_columns.PNG)
 

### Deliverable 3: Extract and Transform the Kaggle data

Code: [ETL_clean_kaggle_data.ipynb](https://github.com/catsdata/Movies-ETL/blob/main/ETL_clean_kaggle_data.ipynb)

- Imported dependencies

- Added in Deliverable 2 code
 
- Cleaned kaggle data:

    - merged Kaggle and Wiki data into datafram
    - dropped unnecessary columns in new dataframe
    - filled in missing kaggle data
    - filtered and renamed columns
    
- Merged ratings from Movielens to new dataframe for new dataframe with ratings

- Confirmed wiki dataframe still matches Deliverable 2
    
    ![cleanwiki](https://github.com/catsdata/Movies-ETL/blob/main/Images/clean_wiki_del3_df.PNG)
 
- Confirmed movies with ratings dataframe looked correct
    
    ![cleanratings](https://github.com/catsdata/Movies-ETL/blob/main/Images/movies_with_ratings.PNG)
        
- Confirmed movies dataframe looked correct

    ![cleanmovies](https://github.com/catsdata/Movies-ETL/blob/main/Images/movies_df_del3.PNG)
 

### Deliverable 4: Create the Movie Database

Code: [ETL_create_database.ipynb](https://github.com/catsdata/Movies-ETL/blob/main/ETL_create_database.ipynb)

- Imported dependencies

- Added in Deliverable 3 code
 
- Connected to PostgreSQL Database

    - added movies_df to the database
    - added code for elapsed time
    - brought in variables for the files 
    - ran program

    ![database run](https://github.com/catsdata/Movies-ETL/blob/main/Images/import.PNG)
    
- Confirmed PostgreSQL Database movies table had 6052 rows

  ![database movies](https://github.com/catsdata/Movies-ETL/blob/main/Images/movies_query.png)

- Confirmed PostgreSQL Database ratings table had 26,024,289 rows

  ![database ratings](https://github.com/catsdata/Movies-ETL/blob/main/Images/ratings_query.png)


## Summary

Data has been extracted from json, csv, and large file csv into readable and clean data for SQL Database analysis.
- ***Extracted*** the Wikipedia and Kaggle data from their respective files
- ***Transformed*** the datasets by cleaning them up and joining them together
- ***Loaded*** the cleaned dataset into a SQL database
