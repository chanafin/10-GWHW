SQL Alchemy

Surfs Up - Now that the foundation for SQL and python has been laid, the ability to use Python to extract and manipulate Data from a SQL query is the next goal. Using the declarative_base, which allows the user to define/create schema, the user can then create Classes(Tables) which are built upon the Base. In this case, the goal is to create two separate classes, Surfers and Boards. The name of the table and each Column must be indiviudal instatiated. By creating a connection to a database with create_engine,the path and file name have been instatiated. By using Base.metadata.create_all, there is now a SQLite DB with the created Table with Columns. The next objective is to create instances for both classes. Once a surfer and board instance are created, the next step is to instatiate a session, add the classes, and finally commit the changes. Lastly, the newly created database can be accessed through Python using session.query.

Emoji Plotting -  After importing the new dependencies, the first step is to create an engine which connects with SQL database, where the data is located.The user can either go directly to the SQL DB, but if that is not possible, it it important to extract both table and column information before running queries. This is accomplished through the .get_table_names() and .get_columns('table_name') functions. Once we have the table and column and table info, loop through the columns variable and print the information needed, which in this case is 'name' and 'type'. Once exploration and analysis is complete. There are several routes one can take to extract and explore the information to be analyzed. In this instance, we want to create a reflection, which mirrors the structure of the existing table into our metadata. Here, automap_base() automaticall defines the structure of the class. The next step is to instatiate a session with the DB. Once the session is established, it is now possible to query the table for the columns needed for analysis. The emoji character, ID and score are all extracted but are served up in a Tuple. The data is unpacked and stored into separate list using list comprehensions. The separate lists are then plotted in MatPlotLib & turned into a DataFrame and plotted in Pandas. THe final goal is to use pd.read_sql to connect to our engine and access the Table through a more streamlined process.

Hawaii Weather - This is a more involved project that will test abilities to use SQLalchemy Declarations and Reflections and will incorporate a final step: Flask Endpoints.The first section is located in the Jupyter Notebook, hawaii_climates. After importing dependencies, the engine is created to the DB and is reflected. The user can now view all the classes (tables) within the DB. Now a session can be created to the engine which represents the link from Python to the SQL DB. Now, the analysis begins. The first object is to plot the last 12 months of precipitation data. It starts with SQL query to the 'Measurement' class that filters any date outside the desired time frame. The queried data is then put into a DataFrame, sorted and plotted. The next objective is to plot temperature observation data for the most active station in the measurement class. The first step is to determine how many total stations there are. This is accomplished through the func.count for the station class. Then, through a query, we group and sort the count of measurements by station. The most active station is then captured and the last tweleve months of temparature measurements will be plotted. The next goal is to apply functions using SQLAlchemy. The first function calculates the minimum, maximum and average temperatures for a window of dates the user is able to input. After creating and testing the function. We apply the function to our vacation's time which is then plotted. A second function is defined that caluclates the daily temperatures for a specific month and date.

The last step is the exercise is to incorporate Flask endpoints. The database is connected to and reflected and a session is created. The default Flask Route provides a list of endpoints. If a user enters a certain endpoint, there is a designated function that will run and return a query. 