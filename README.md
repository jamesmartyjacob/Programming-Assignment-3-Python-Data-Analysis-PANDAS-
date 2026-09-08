# Experiment #3: Python Data Analysis
## Made by: James Marty Jacob | 2ECE-B

#### Objectives: 
1. Load a CSV dataset into a Pandas DataFrame
2. Select rows and columns using positional and label-based indexing
3. Filter records using conditions on a DataFrame column
4. Extract a well-defined subset of data without changing the source data

#### Initial Conditions 
1. ```import pandas as pd``` to use the Python Data Analysis Library in Python.
2. ```cars = pd.read_csv('cars.csv')``` to import and read the CSV file used in the program.

### Problem A. Positional and Label-Based Slicing
The program displays the shape and a complete list of column names from cars.csv. Then, using positional slicing, create a subset containing rows 6 through 10 of the original dataset storing it in cars_6_to_10. The program then displays specific columns namely, "Model", "mpg", "cyl", hp", and "gear". 

##### Solution: 

###### Part A.a
1. ```cars``` reads and displays the cars.csv database.
2. ```print("Cars Dataset Shape:", cars.shape)``` prints the dataset's shape including number of rows and columns.
3. ```print("Cars Column Names:", cars.columns.tolist())``` prints a list of all the dataset's column names.

###### Part A.b
1. ```cars_6_to_10 = cars.iloc[5:10]``` obtains rows 6 to 10 of the list, with row 1 being index 0.
2. To check ```cars_6_to_10``` is used.

###### Part A.c
1. ```subset_c = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]``` creates another subset of cars_6_to_10 that includes only the columns "Model, mpg, cyl, hp, and gear".
2. ```display(subset_c)``` displays the subset with specified columns.

### Problem B. Model Lookup 
The program utilizes Boolean indexing on the ```Model``` column to obtain two specific vehicle models without using hard-coded row index numbers. 

##### Solution:

###### Part B.a
1. The code ```toyota = cars[cars['Model'] == 'Toyota Corolla']``` searches for the model "Toyota Corolla" within the original dataset and then stores all the information it has in "toyota".
2. ```display(toyota)``` displays only the toyota row.

###### Part B.b
1. The code ```pontiac_col = ['Model', 'mpg', 'hp', 'wt']``` obtains only the columns specified, marking it as pontiac_col.
2. ```pontiac = cars[cars['Model'] == 'Pontial Firebird'][pontiac_col]``` looks for the "Pontial Firebird" model and obtains the columns specified in pontiac_col through ```[pontiac_col``` attached at the end of the syntax.
3. ```display(pontiac)``` then displays the Pontiac Firebird row.

### Problem C. Multi-Model Subsetting
The program obtains three specific car models, namely, "Datsun 710, Lotus Europa, and Ferrari Dino". Then creates a subset that includes columns "Model, mpg, cyl, hp, and gear" using model values. The output is then validated to ensure that it satisfies the required dimensions of 3 rows and 5 columns.

##### Solution: 
1. ```target_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']``` Stores the text values of the target models in target_models.
2. ```target_cols = ['Model', 'mpg', 'cyl', 'hp', 'gear']``` Stores the columns of the specific vehicle variables required.
3. ```selected_cars = cars[cars['Model'].isin(target_models)][target_cols]``` Obtains the model specified with ```.isin(target_models)``` by checking the variables contained within target_models then subsets it with columns contained within ```[target_cols]```.
4. ```display(selected_cars)``` Displays the list specified.
5. ```print("Shape of selected_cas:", selected_Cars.shape)``` displays the shape of selected_cars.
6. An if-else statement is used to check if selected_cars has the correct number of rows and columns.

### Repository Structure 

    -cars.csv #Dataset
    -JACOB_2ECE_B_PA3.ipynb #Main Jupyter Notebook
    -README.md # Project Documentation
