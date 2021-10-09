# Movies-ETL

## Module 8 repository

The jupyter notebooks contained in this repository were used to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. They are based on the refactored code from Module 8, and are utilized to create one function that takes in three files — Wikipedia json data (*wikipedia-movies.json*), Kaggle metadata (*movies_metadata.csv*), and the MovieLens rating data (*ratings.csv*). The function then performs the ETL process by adding the data to a PostgreSQL database named *movie_data*.

The four jupyter notebook files are a progression on each other, with each building and adding additional code to the previous one in order to test and validate the code along each step. The progression order of the notebooks is:

* Deliverable 1: *ETL_function_test.ipynb* - basic code for a function (*extract_transform_load()*) that takes three imputs (*wiki*, *kaggle* and *rating*, which point to the file name and directory of the three data files). The function reads in the three data files and creates three separate DataFrames from these files.

* Deliverable 2: *ETL_clean_wiki_movies.ipynb* - includes additional code to the function in order to extract and transform the Wikipedia data so that it can be merged with the Kaggle metadata. Extraction of the IMDb IDs employs a regular expression string and drops duplicates, as well as a try-except block to catch errors.

* Deliverable 3: *ETL_clean_kaggle_data.ipynb* - includes further code to extract and transform the Kaggle metadata and MovieLens rating data, then converts the transformed data into separate DataFrames. Then, the Kaggle metadata DataFrame is merged with the Wikipedia movies DataFrame to create the movies_df DataFrame. Finally, the MovieLens rating data DataFrame is merged with the movies_df DataFrame to create the movies_with_ratings_df.

* Deliverable 4: *ETL_create_database.ipynb* - Finally, code is added to export the movies_df DataFrame (as *movies.csv* table) and MovieLens rating CSV data (as *ratings.csv* table) to an SQL database (*movie_data*) in PostreSQL.