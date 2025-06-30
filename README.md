# ASA-Project
This project aims to gather up data from a csv zipe file and then create an ETL pipeline using Python Jupyter Notebook and Snowflake Connector.
The project will aim to first extract the data from the csv zip file; thereafter cleaning the data, in separate dataframes, in Python Jupyter Notebook.
Once the cleaning process finishes, the Snowflake Connector will be used to update the dataframes into an instance of Snowflake for analysis.

The project's timeline will go as follow:
   In Python Juypter Notebook:
  1) Data Extraction:
     A. First Calling the necessary libraries (pandas, numpy, seaborn, matplotlib, etc...)
     B. Using Pandas to unzip the folder and extract the csv files as dataframes
     C. Append the dataframes to a list to assign each file to a designated dataframe
     D. Execute the segmentation of all csv files into specific dataframe based on the list from step "C"
  3) Data Normalization.
     A. Clean all of the fields to follow the same nomenclature from dataframe to dataframe (mainly descriptive fields such as gender, ethnic banground, etc...)
     B. Make sure that they all match the same format.
  4) Data Cleaning.
     A. Utilize lambda functions to clean up timestamp fields and ensure test/gpa fields can be calculated.
     B. Perform a quality check by looking at the head/tail of the dataframe(s)
     C. Save all dataframes to Pandas object for ease of use.
  6) Snowflake Connection.
     A. Call Snowflake libraries in Notebook
     B. Input the following fields from my Snowflake instance:
       I. Username
       II. Password
       III. AccountName
       IV. Data Wharehouse
       V. Schema
     C. Create a connection to Snowflake and begin the layout for the dataframes' schema execution.
  7) Schema Execution for the various dataframes.
      A. Run each dataframe's Schema execution using the Snowflake Connector.
  8) Loading of the dataframes onto Snowflake using Snowflake Connector.
      A. Load all of the dataframes into Snowflake Connector using Jupyter Notebook SQL Connection.
    
  9) Verify that the ETL scripts were successful through Querying the data in Snowflake.
      A. Run a partition SQL script to find the top performing students within each ethnic group based on their average Test Score across the board
