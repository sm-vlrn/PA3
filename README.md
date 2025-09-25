# PA3

## PROGRAMMING ASSIGNMENT 3

### PROBLEM 1
The goal of this problem is to load the dataset cars.csv into Python using pandas, then display the first and last five rows. This helps us confirm that the file was loaded correctly and lets us preview the data.

```
import pandas as pd

# Load the dataset
cars = pd.read_csv('cars.csv')
cars

# Show first 5 rows
cars.head()

# Show last 5 rows
cars.tail()
```
The function pd.read_csv() loads the file cars.csv into a DataFrame called cars. The commands .head() and .tail() display the first and last five rows. This way, we can easily check the beginning and end of the dataset.

### PROBLEM 2
The goal of this problem is to practice selecting rows and columns in pandas. We will subset data using .iloc and .loc to answer specific questions like:
#### How to get only odd-numbered columns for the first 5 rows?
Here, we use .iloc to pick only odd-numbered columns for the first five rows.
```
cars.iloc[0:5, ::2]
```
The code iloc[0:5, ::2] means rows 0–4 and every second column (step of 2). This gives us the odd-numbered columns only.

#### How to find the row for a specific car model?
```
cars.loc[cars['Model'] == 'Mazda RX4']
```
The .loc command is used to filter rows where the column Model is equal to "Mazda RX4".

#### How to check the cylinder count for a car?
```
cars.loc[cars['Model'] == 'Camaro Z28', ['cyl']]
```
Here we filter the row where Model is "Camaro Z28", but only show the cyl column.

#### How to get both cyl and gear values for specific models?
The cyl and gear values of three models: "Mazda RX4 Wag", "Ford Pantera L", and "Honda Civic".
```
result = cars.loc[
    cars['Model'].isin(['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']),
    ['Model', 'cyl', 'gear']
]
print(result)
```
The .isin([...]) function checks if the Model is one of the three. Then we display only cyl and gear.
