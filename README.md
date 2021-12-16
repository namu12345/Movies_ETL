# Movies_ETL

## Purpose of Analysis :

The Amazing Prime, a video streaming company, decided to sponsor a hackathon, where participants trying to predict which low budget movies being released will become popular. Participants of a hackathon need a clean data in order to perform analyses for their algorithms. In order to provide organized and clean dataset, this project focuses on ETL* or Extract, Transform and Load process and includes the following:

- Extracting data from two different sources.
    - web scrape of Wikipedia website for all movies released since 1990
    - data from Kaggle website for rating data.
- Transforming data using Jupyter Notebook, Python, Pandas and Python RegEx module.
- Loading data using PostgreSQL and pgAdmin to host final cleaned data set.

## Overview of the code:

The goal of this analysis is to create automated pipeline that extracts, transform and loads data. This analysis consists of four parts, where each step is building up from beginning of extracting data and function testing, through transformation and cleaning process to its final step connect and load to the database. The entire process of ETL can be executed with a single call of the function extract_transform_load in the final step ETL_create_database.ipynb. The ETL process is broken down into four jupyter notebook files:

- ETL_function_test.ipynb

  - Data is extracted from the website in JSON and CSV formats.
  - Data is transformed into Pandas data frames.
  - JSON file requires extra step – loading file first and then transforming into data frame.
![image](https://user-images.githubusercontent.com/92283185/146216350-33e0bfc3-8b82-46b0-b076-a6d78837d14d.png)


- ETL_clean_wiki_movies.ipynb

  - Function clean_movie combines scattered data of alternative languages into one column alt_titles.

  - Its subfunction change_column_name organizes column names into consistent pattern.

  - In the function extract_transform_load the transformation process of wiki movies data begins and includes:

      - Python list comprehensions. (quick screenshot for an example)
   ![image](https://user-images.githubusercontent.com/92283185/146217678-0ef2f3f0-b022-408d-b6e5-649526bd8594.png)

      - apply() and map() methods in combination with lambda functions & regular expressions or RegEx as shown below :
    
   ![image](https://user-images.githubusercontent.com/92283185/146217873-0c96fe77-97d0-4ab7-bfaa-1e3c30b9004a.png)


- ETL_clean_kaggle_data.ipynb

  - Function extract_transform_load gets new tasks for cleaning Kaggle data and includes:

      - Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
  
  ![image](https://user-images.githubusercontent.com/92283185/146218570-23c0988b-ab03-4779-ac70-58c80bf0691c.png)
  
      - Merging data frames using pd_merge method & Filling missing values and filtering unwanted columns.
  ![image](https://user-images.githubusercontent.com/92283185/146219892-625dee1b-1554-4d51-a7a7-3007546b0926.png)


- ETL_create_database.ipynb

  - Finally, the function in its final step connects to the database by sqlalchemy library and to_sql method.
  ![image](https://user-images.githubusercontent.com/92283185/146221092-0460e25b-d005-4d9c-9682-75eafa3f67ae.png)

  
## Results :
As mentioned earlier the Complete ETL process can be executed with a single function extract_transform_load call which resulted as follows :
![image](https://user-images.githubusercontent.com/92283185/146222608-e50437a9-6e40-49a7-b6a3-8caf7cf7ce62.png)


## Resources:

- Software
  - Python v3.x
- Dependencies:
  - pandas
  - json
  - numpy
  - re
  - sqlalchemy
  - psychopg2
  - time
  - PostgreSQL
  - pgAdmin
- Files:
    - [movies_metadata.csv](https://github.com/namu12345/Movies_ETL/blob/main/Resources/movies_metadata.csv)
   - [ratings.csv](https://github.com/namu12345/Movies_ETL/blob/main/Resources/ratings.csv)
   - [wikipedia-movies.json](https://github.com/namu12345/Movies_ETL/blob/main/Resources/wikipedia-movies.json)
