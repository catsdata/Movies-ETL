# Movies-ETL

<details><summary>Table of Contents</summary>
<p>

1. [Overview](https://github.com/catsdata/Pewlett-Hackard-Analysis#overview)
2. [Resources](https://github.com/catsdata/Pewlett-Hackard-Analysis#resources)
3. [Deliverables / Results](https://github.com/catsdata/Pewlett-Hackard-Analysis#results)
    - [Deliverable 1]()
    - [Deliverable 2]()
    - [Deliverable 3]()
    - [Deliverable 4]()
4. [Summary](https://github.com/catsdata/Pewlett-Hackard-Analysis#summary)

</p>
</details>

## Overview

What it is

## Resources

What I used

## Deliverables

### Deliverable 1: Write an ETL Function to Read Three Data Files

- Imported dependencies
 
- Converted Wiki JSON to Pandas dataframe

  ![wiki](https://github.com/catsdata/Movies-ETL/blob/main/Images/wiki_movies_df.PNG)
 
- Converted Kaggle metadata file into Pandas dataframe

  ![kaggle](https://github.com/catsdata/Movies-ETL/blob/main/Images/kaggle_metadata_df.PNG)
 
- Converted Movielens data into Pandas dataframe

  ![movielens](https://github.com/catsdata/Movies-ETL/blob/main/Images/ratings_df.PNG)


### Deliverable 2: Extract and Transform the Wikipedia Data

- Imported dependencies
 
- Cleaned wiki movies dataframe by:

    - filter out TV shows
    - catch errors and drop duplicates
    - remove nulls
    - create non-null Box Office column
    - clean data string formats for Box Office column; parsing dollars
    - clean budget column
    - clean release date column
    - clean runtime column
    - review clean dataframe

        ![cleanwiki](https://github.com/catsdata/Movies-ETL/blob/main/Images/clean_wiki_movies_df.PNG)
 
    - review updated column names
                
        ![cleancolumns](https://github.com/catsdata/Movies-ETL/blob/main/Images/clean_wiki_columns.PNG)
 

### Deliverable 3: Extract and Transform the Kaggle data

### Deliverable 4: Create the Movie Database

## Summary

What it means
