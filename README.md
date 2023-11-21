# YouTube Suscribers and Channel Analysis

# Analysis Description
The distribution of channel types from the top 1000 records is computed by this Python script, which also loads the data into a MySQL database after analyzing YouTube channel data from a dataset.

# Getting Started

# Prerequisites
See to it you have installed the following:

- Notebook Jupiter
- Anaconda    
- MySQL Workbench

# Installing

Start Jupiter Notebook and add the following libraries. The user will be able to utilize the Jupiter Notebook's functions through these libraries.
```bash
import pandas as pd
import pandas as pd
from sqlalchemy import create_engine
import pymysql
```

Use the following command to connect the Python to the MySQL database. 

The command pip install pymysql installs the pymysql Python package, enabling communication with MySQL databases through Python scripts.
```bash
pip install pymysql
``

Using the username "usert" and password "password," the create_engine command connects to a MySQL database called "assignment4" that is hosted locally.

```bash

# create engine
engine = create_engine('mysql+pymysql://usert:password@localhost/assignment4')
```

The conn = engine.connect() command establishes a connection (conn) to a database using the SQLAlchemy engine (engine).

```bash
# create engine
conn = engine.connect()
```
Now we are all set to do the youtube channel analysis  



## Running the analysis
+ Download the assignemt4.ipynb file to your local computer before launching Jupiter Notebook to begin the analysis.


+ Now navigate to the Jupiter Notebook's file section, find assignemt4.ipynb, and click on it.
![image](https://github.com/ashutoshnandurbarkar04/Data_1202/assets/151588085/41fa4004-a91a-491f-822c-fa78151d1059)
![image](https://github.com/ashutoshnandurbarkar04/Data_1202/assets/151588085/cb387ca0-cb04-4f1e-bf5d-d8559d39d4fb)

+ When you click on it, an interface similar to this one appears.
![image](https://github.com/ashutoshnandurbarkar04/Data_1202/assets/151588085/2313b7bd-6aa2-45ac-af39-a4970aa3d6d7)

+ Now, simply select the cell and press the run button on the above ribbion to begin running the command.
+ Ensure that the file path points to the location where you downloaded the dataset.
![image](https://github.com/ashutoshnandurbarkar04/Data_1202/assets/151588085/3b06bb91-fe6c-4ba8-b658-1ada5e27930d)

+ Finally, adjust the credentials based on what the user has configured on their MySQL workbench in order to establish a connection.
 ![image](https://github.com/ashutoshnandurbarkar04/Data_1202/assets/151588085/1408c8f2-9471-4919-9cc1-279c1fd7512b)

  ### Breakdown of Tests

1. **Determine the Distribution Channels.:**
   - Description: Calculates the distribution of channel types from the loaded dataset.
   - Command: 
     ```
     channel_distribution_result = calculate_channel_distribution(data)
     print(channel_distribution_result)
     ```

2. **Load Top 1000 Data:**
   - Description: Loads the top 1000 records from the sorted dataset into a CSV file.
   - Command: 
     ```
     top_1000_data = load_data_top_1000(data)
     ```

3. **Examine and confirm loaded data.:**
   - Description: Reads the CSV file containing the top 1000 records and displays the loaded DataFrame.
   - Command: 
     ```
     data2 = pd.read_csv('top_1000_channels.csv')
     data2.head()
     ```

4. **Database Link and Inquiry:**
   - Description: Creates a connection to a MySQL database using SQLAlchemy and reads a simple query into a DataFrame.
   - Command: 
     ```
     df = pd.read_sql("SELECT * FROM assignment4.youtube_dataset", conn)
     print(df.head())
     ```

5. **Write Data to MySQL Table:**
   - Description: Writes the loaded DataFrame to a MySQL table.
   - Command: 
     ```
     data2.to_sql(table_name, con=engine, if_exists='replace', index=False)
     ```

Note: Ensure that the MySQL server is running and the database and table names match your actual setup.

Feel free to modify the descriptions and commands as needed for your specific project.


##  Deployment 
Make sure you have a MySQL database setup before deploying this script, and adjust the script's connection parameters. To load the data into the database, run the script after that.

## Author
Ashutosh Nandurbarkar

## Lisence
This project is licensed under the MIT License - see the LICENSE.md file for details.
