# EXPLORATORY DATA ANALYSIS  IN PYTHON 2024

## Introduction
This project conducts an Exploratory Data Analysis (EDA) on a dataset of Electric Vehicles (EV) using Python. The dataset provides information on various attributes of electric vehicles, including their manufacturers, electric range, vehicle types, and more.

## Goals of the EDA
1. Get to know the top manufacturers of Electric Vehicles
2. Get to know the Average Electric Range(The distance an electric vehicle can travel purely on electric charge) per manufacturer
3. Uncover the association between Electric vehicle type and Manufacturer
4. Find new avenues for analysis

## Data source
- The data is from Data.org. Click [HERE](https://catalog.data.gov/dataset/electric-vehicle-population-data) to access.
## EDA IN PYTHON
### Importing Relevant Packages
```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```

### Importing the Data
```python
EV = pd.read_csv(r'C:\\Users\\Brian Motee\\Desktop\\dataset\\Electric_Vehicle.csv')
```

### Inspecting the Data Structure
```python
EV.info()
```

## Data Preprocessing

### Renaming Variables
```python
EV.rename(columns={'VIN (1-10)':'Vin','Postal Code':'Postal_Code','Model Year':'Model_Year','Electric Vehicle Type':'Electric_Vehicle_Type','Clean Alternative Fuel Vehicle (CAFV) Eligibility':'Clean_Alternative_Fuel_Vehicle_Eligibility','Electric Range':'Electric_Range','Base MSRP':'Base_MSRP','Legislative District':'Legislative_District','DOL Vehicle ID':'DOL_Vehicle_ID','Vehicle Location':'Vehicle_Location','Electric Utility':'Electric_Utility','2020 Census Tract':'2020_Census_Tract'}, inplace=True)
```

### Changing Data Types
```python
EV = EV.astype({'Vin':'string','County':'string','City':'string','State':'string','Make':'string','Model':'string','Electric_Vehicle_Type':'string','Electric_Utility':'string'})
```

### Handling Missing Values
```python
EV = EV.dropna(subset=['Electric_Range'])
```

## Exploratory Data Analysis

### Univariate Statistics

#### Electric Range
```python
print('The average electric range is ' + str(EV.Electric_Range.mean()))
print('The median electric range is ' + str(EV.Electric_Range.median()))
print('The mode electric range is ' + str(EV.Electric_Range.mode()))
```

### Bivariate Statistics

#### Association between Manufacturers and Electric Range
```python
Mean_Tesla = np.mean(Tesla_EV)
Mean_Nissan = np.mean(Nissan_EV)
#Printing the means
print("This is Tesla's average Electric Range: " + str(Mean_Tesla))
print("This is Nissan's average Electric Range: " + str(Mean_Nissan))
```

#### Association between Electric Vehicle Type and Electric Range
```python
#Getting the means
BEV_Mean = np.mean(BEV)
PHEV_Mean = np.mean(PHEV)
#Printing the means
print("The average BEV Electric range is " + str(BEV_Mean))
print("The average PHEV Electric range is " + str(PHEV_Mean))
```
## Results
Tesla is the largest manufacturer of Electric vehicles. The sales of Teslar electric vehicles are driven by the fact that its cars have more than two times the electric range of its competitors. This provides an avenue for further research and analysis to uncover the sales drivers of Tesla and its competitive advantage.
## Conclusion
This EDA highlights significant associations between electric vehicle attributes, such as manufacturers and electric range, and between electric vehicle types and range. Further analysis and modeling can be performed based on these insights.
