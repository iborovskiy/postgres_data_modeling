### Date created
2022-08-16


### Project Title
Udacity course project: Data Modeling with Postgres


### General Description
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app.
The analytics team is particularly interested in understanding what songs users are listening to.

The goal of this project is to create a Postgres database with tables designed to optimize queries on song play analysis.
In this project, the following data modeling tasks were completed:
1. Defining database schema design (star schema)
2. Defining dimension and fact tables for selected database design
3. Building ETL pipeline that transfers data from original data files into Postgres DB tables


### Details of database schema design and ETL pipeline
For this project, dimensional modeling was selected as it is best suited for OLAP goals of analytics team.
We use a **star schema** optimized for queries on song play analysis.
Schema consists of the following tables:
_Fact tables (measurements, metrics or facts of a business process)_
**songplays** - records in log data associated with song plays

_Dimension tables (categorize facts and measures to answer a business questions)_
**users** - users in the app
**songs** - songs in music database
**artists** - artists in music database
**time** - timestamps of records in **songplays** broken down into specific units (hour, day, week, month, year, etc.)

**ETL pipeline** performs the following functions:
1. Reads data from JSON-log files
2. Cleans and transforms this data
3. Loads processed data into the database tables


### Instructions for running the Python scripts
Run the following scripts in installed python interpreter:
- **create_tables.py** for creating database tables. You must run this script to reset your tables before each time you run ETL script.
- **etl.py** for executing ETL pipeline logic.

The following file is required for correct execution of the scripts above:
- **sql_queries.py** - contains all sql queries, and is imported into the files above.

For correct functioning of ETL pipeline you must create two subdirectories in database working directory:
- **data\\song_data** - collection of data files in JSON format that contain metadata about a song and the artist of that song
![Example of the metadata in a song file](/img/song-data.PNG "Example of the metadata in a song file")
- **data\\log_data** - collection of data files in JSON format that contain activity logs from a msuic streaming app
![Example of the data in a log file](/img/log-data.png "Example of the data in a log file")

Following Jupyter notebooks is not part of the project and included for testing purposes:
- **test.ipynb** - displays the first few rows of each table to let you check your database
- **etl.ipynb** - reads and processes a single file from \\song_data and \\log_data and loads the data into your tables


### Credits

**This entire project is based on learning materials from Udacity:**
https://learn.udacity.com/

The song dataset is a subset of real data from the Million Song Dataset:
http://millionsongdataset.com/

The log dataset consists of log files in JSON format generated by the following event simulator:
https://github.com/Interana/eventsim
