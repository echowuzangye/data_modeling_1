A. Summary of the project
- Postgres Database sparkifydb was created to help a startup called sparkify better analyze the data they've been collecting on songs and user activity on their new music streaming app. One Fact(songplays) and four dimension(users, songs, artists, time) tables were defined for a star schema, and an ETL pipeline was written that transfers data from files in two local directories into these tables in Postgres using Python and SQL.


B. How to run Python scripts
- Open terminal and run: python create_tables.py
- then run: python etl.py


C. Explanation of the files
- data file contains log data and song data, they are all in json format
- create_tables.py is used to create database, drop tables and create tables. This should be rerun to reset the tables.
- sql_queries.py contains sql queries to create\drop tables, insert records into tables.
- test.ipynb is used to confirm the creation of the tables, insertion of records is correct.
- etl.ipynb is used to build ETL process step by step, each step is focus on a single data file. After each step is finished, test.ipynb is run to confirm the process is legit.
- etl.py is developed based on etl.ipynb to process the whole dataset.


D. Personal Notes:
- Extract Data for Time Table
x = pd.to_datetime(a, unit='ms')
x.dt.year, x.dt.month, x.dt.day, x.dt.hour, x.dt.week, x.dt.dayofweek

- test.ipynb
%load_ext sql - The ipython-sql library is loaded using the %load_ext iPython extension syntax
%sql postgresql://student:student@127.0.0.1/sparkifydb - connect to the database

- etl.ipynb
OS.walk() generate the file names in a directory tree by walking the tree either top-down or bottom-up. For each directory in the tree rooted at directory top (including top itself), it yields a 3-tuple (dirpath, dirnames, filenames).


E. Resources:
https://knowledge.udacity.com/questions/736863
https://knowledge.udacity.com/questions/403616