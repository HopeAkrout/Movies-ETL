# Movies-ETL
Create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables to keep current dataset updated daily.

## Background

The original process can be seen in "Movies-ETL Practice.ipynb."  Scraped Wikipedia data stored as a JSON and Kaggle data stored in CSVs were used as the original data sets to extract from.  The data was transformed and then loaded into an SQL database.

In this project, I was tasked with creating an automated pipeline to continue adding to the database daily.

## Process

The ETL_function_test.ipynb was created as the first step.  This process opens and reads the data then converts the three different datasets into data frames.

The ETL_clean_wiki_movies.ipynb was created to perform the cleaning steps needed for the JSON file.  List comprehensions to filter out superfluous data, iterate through cleaned lists, deleting duplicate lines or columns with no readable data, and merging of various columns for the same purpose are performed to organize and streamline the information so that as new data is added to the data frame, it remains easy to decipher and clutter-free.  ETL_clean_kaggle_data.ipynb likewise cleans and streamlines the .csv files.

Finally, the ETL_create_database.ipynb is used to upload the new data using "if_exists='replace'" or "if_exists='append'" to avoid creating our own duplicate lines.
