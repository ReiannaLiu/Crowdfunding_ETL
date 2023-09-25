# Crowdfunding_ETL

An ETL (Extract Transform Load) mini project that uses Pyhton,Pandas, Numpy to create a PostgreSQL database which is managed with PgAdmin 4 . 


## Table of Contents
#### Introduction
#### Requirements & Dependencies
#### Analysis and Results
#### Usage
#### Contributing
#### License
<br>

#### Introduction
This ETL project demonstrates skills to extract and transform data using two xlsx files to export four csv files, which are then used to load tables in a PostgreSQL database managed by PgAdmin 4. 
- This project was completed by three persons: O Dumbuya, R Liu, and T Barnett. Each contributor's work is delineated below. 


#### Features
- Extract Data with Pandas 'read_excel' function. 

- Use NumPy 'arrange' function and list comprehension to create dataframe  subsets.  

- Use Pandas 'astype' and 'to-datetime' functions to convert data types.

- Use Pandas 'rename' function to rename columns.

- Use Pandas/Regex/JSON functions such as 'merge', 'drop', "itertuples' and 'split' to prepare data for appropriate normal form use in relational database.

<br>

#### Requirements & Dependencies
You will need the following software to run the ETL script:
- Python 3.10
- Pandas
- NumPy
- JSON
- PgAdmin 4 
- PostgreSQL Database Server
<br>

### Project Structure
### **Part 1.** 
##### Completed by R Liu
<br>
Use Pandas to read the crowdfunding.xlsx file into a DataFrame and check the head.
<img src = "Images/crwdfnd_df_head.png" width="1200"/>
<br>
<br>

Get the summary of crowdfunding DataFrame. 
<img src = "Images/crwdfnd_dtypes.png" width="500"/>
<br>
<br>

Check the crowndfunding DataFrame columns.
<img src = "Images/crwdfnd_cols.png" width="600"/>
<br>
<br>

Split the 'category&sub-category' column to create two new columns: 'category' and ' subcategory. 
<img src = "Images/crwdfnd_cat_split.png" width="1200"/>
<br>
<br>

Create one list for 'catgeories' and another for 'subcategories'.
<img src = "Images/cat_subcat_list.png" width="1400"/>
<br>
<br>

Get the number of distinct values in the 'categories' and 'subcategories' lists.
<img src = "Images/len_cat_subcat.png" width="100"/>
<br>
<br>

Create NumPy arrays for categories and subcategories.
<img src = "Images/cat_subcat_array.png" width="1000"/>
<br>
<br>

Use list comprehension to prepare the category and subcategory values and the create two DataFrames for category and subcategory.  
<img src = "Images/cat_subcat_list.png" width="2000"/>  
<br>

Category DataFrame
<img src = "Images/cat_df.png" width="600"/> 
<br>

Subcategory DataFrame
<img src = "Images/subcat_df.png" width="600"/> 
<br>
<br>

Export the category and subcategory DataFrames as two separate CSV files to the Resources folder. 
<br>
<br>
<br>

### **Part 2.** 
##### Completed by O Dumbuya
<br>

Create a campaign DataFrame as a copy of the crowdfunding Dataframe with the added category and subcategory columns, and then check the head.
<img src = "Images/crwdfnd_cat_split.png" width="1200"/>
<br>
<br>

i.  Rename the 'blurb', 'launched_at' and 'deadline' columns as 'description',   'launch_date' and 'end_date'.
ii. Convert the 'goal' and 'pledged' columns data types to float. 
iii. Check that the data types were changed.
<img src = "Images/campaign_df_dtypes.png" width="500"/>
<br>
<br>
i. Format the 'launch_date' and 'end_date' columns to YYYY-MM-DD format.
ii. Merge the campaign DataFrame to the category and subcategory DataFrames on category and subcategory, respectively.
iii. Drop the unwanted columns, and check the cleaned campaign Dataframe head. 
<img src = "Images/campaign_df_clean.png" width="1600"/>
<br>
<br>
Export the clean campaign DataFrame as a CSV file to the Resources folder. 
<img src = "Images/crwdfnd_cat_split.png" width="1200"/>
<br>
<br>
<br>

### **Part 3.** 
##### Completed by R Liu
<br>


##### Option 1-Pandas

<br>

Use Pandas to read the contacts.xlsx file and check the head.
<img src = "Images/contact_df_head.png" width="1200"/>
<br>
<br>

Convert each row of data to a dictionary and print out the results.
<img src = "Images/contact_dict.png" width="2000"/>
<br>
<br>

Create a contacts DataFrame with the dictionary values and check the head. 
<img src = "Images/contact_df_clean_head.png" width="1200"/>
<br>
<br>

Check the contact DataFrame data types.
<img src = "Images/contact_dtypes.png" width="800"/>
<br>
<br>

i. Split the 'name' column to create a 'first_name' column and a 'last_name' column.
ii. Drop the 'name' column. 
iii. Reorder the columns: 'contact_id', 'first_name', 'last_name', 'email'.
iv. Check the Dataframe head. 
<img src = "Images/contact_df_clean_final.png" width="1200"/>
<br>
<br>

Check the clean contacts DataFrame datatypes and export the DataFrame as a CSV file to the Resources folder. 
<img src = "Images/contact_final_dtypes.png" width="500"/>
<br>
<br>

##### Option 2-Regex
<br>
Make a copy of the contacts DataFrame that was created when Pandas was used to read the contacts.xlsx file in Option 1, and check the head.
<img src = "Images/contact_df_head.png" width="1200"/>
<br>



<br>

---
*

<br>

---

---
#### Usage
1. Ensure that you have the appropriate CSV and XlSX files.
2. Run the  script in an appropriate code editor such as Jupyter Notebook. 
3. Run the app.py script in an appropriate code editor and render in a web browser such as Google Chrome with the necessary extensions, to optimize JSON, for example.

#### Contributions
Contributions to this project are highly encouraged! If you wish to contribute, please follow these guidelines:

- Fork the crowdfunding_ETL repository and clone it locally.
- Create a new branch for your feature or bug fix.
- Commit your changes with descriptive commit messages.
- Push your branch to your forked repository.
- Submit a pull request to the original repository.
- Please ensure that your code adheres to the project's coding style and conventions.


If you encounter any issues or have suggestions for improvements, please open an issue on the GitHub repository.

### License
These projects are licensed under the MIT License. Feel free to use, modify, and distribute the code as per the terms of the license. 