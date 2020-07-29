## Data Modeling - Sparkify Postgres ETL

This project extracts, transforms and loads data from the Sparkify app (an app to listen to your favorite musics) logs to create a tables in a relational database:
 - `users`
 - `songs`
 - `artists`
 - `songplays`
 - `time` 
 
With this structured database, we can extract meaningful insights from user habits of listening to music and learn hidden patterns inside this 
large quantity of data. 

### Database Schema Design

Below is the database schema for the Sparkify databse:

#### Song play table

- Name: `songplays`
- Type: Fact table
  * songplay_id
  * start_time
  * user_id
  * level
  * song_id
  * artist_id
  * session_id
  * location
  * user_agent

#### Users table

- Name: `users`
- Type: Dimension table
  * user_id
  * first_name
  * last_name
  * gender
  * level
  
#### Songs table

- Name: `songs`
- Type: Dimension table
  * song_id
  * title
  * artist_id
  * year
  * duration

#### Artists table

- Name: `artists`
- Type: Dimension table
  * artist_id
  * name
  * location
  * latitude
  * longitude

#### Time table

- Name: `time`
- Type: Dimension table
  * start_time
  * hour
  * day
  * week
  * month
  * year
  * weekday

### The project file structure

In order to perform data modeling and ETL, 5 files were created as below:
 - `sql_queries.py` - This files contains a query repository to use throughout the ETL process
 - `create_tables.py` - This file is reponsible for creating tables and deleting tables in the Sparkify database
 - `etl.py` - This file is responsible for the main ETL process (extracting and inserting data into the tables)
 - `etl.ipynb` - This python notebook was written to develop the logic behind the `etl.py` process
 - `test.ipynb` - This notebook was used to test the ETL process to make sure that it works
