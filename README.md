# ECE-2112-PA-3
Miguel Joaquin T. Cariño
# Programming Assingment 3
Before staring the Programming Assignment Python Data Analysis was import as pd. 
```python
import pandas as pd
```
## A. Positional and Label-Based Slicing
# Objective
The objective of this problem is to be able to load the csv file (cars.csv) into a Pandas Dataframe and practice selecting rows using positional indexing and columns using labels. 
# Discussion
The cars.csv file is loaded into a Dataframe and displayed to understand its structure. 
The shape and the complete column of models are displayed.
```python
cars = pd.read_csv('cars.csv')
cars
print(cars.shape)
cars.loc[0:32, ['Model']]
```
Using positional indexing (.iloc) rows 6 through 10 are selected.
```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```
The selected rows are now used in to display the selected cars to display its Model, mpg, cyl, hp, and gear, in the required order. 
```python
cars.loc[[5,6,7,8,9],['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
```python
  Model	          mpg	 cyl	hp	gear 
5	Valiant	      18.1	6	  105	  3
6	Duster360	  14.3	8	  245	  3
7	Merc240D	  24.4	4	  62	  4
8	Merc230	      22.8	4	  95	  4
9	Merc280	      19.2	6	  123	  4
```

## B. Model Lookup
# Objective
The objective of this problem is to locate specific models and extract either their complete records or selected columns using boolean indexing. 

# Discussion
The Toyota Corolla is located by checking the Model Column using Boolean indexing. The complete row for the Corolla Model is now displayed.
```python
toyota = cars.loc[cars['Model']=='Toyota Corolla']
toyota
```
```python
    Model	        mpg	   cyl  disp	 hp	    drat	wt	   qsec	  vs am  gear	carb
19	Toyota Corolla	33.9	4	 71.1	  65	4.22  1.835	  19.9     1  1	    4	   1
```
For the Pontiac Firebird, in order to locate for this model Boolean indexing is also used, but only displaying the only required columns such as Model, mpg, hp and wt.
```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac
```
```python
    Model	            mpg	   hp	  wt
24  Pontiac Firebird	19.2	175	3.845
```

## C. Multi Model Subsetting
# Objective
The objective of this problem is to create a new Dataframe including the records for the models Datsub 710, Lotus Europa, and Ferrari Dino, while only displayin the required columns and models. It is also required to locate them using only their model names.


# Discussion
Boolean indexing is used with multiple conditions is used to select the three required models. The | represents as OR, it allows specified model to be selected. The selected cars only retains the Model, mpg, cyl, hp, and gear columns are selected. 
```python
selected_cars = cars.loc[
    (cars['Model'] == 'Datsun 710') |
    (cars['Model'] == 'Lotus Europa') |
    (cars['Model'] == 'Ferrari Dino'),
    ['Model', 'mpg', 'cyl', 'hp', 'wt']]
selected_cars
```
```python
    Model	          mpg	 cyl	hp	wt
2	  Datsun 710	 22.8	 4	  93	2.320
27  Lotus Europa	30.4	4	  113	1.513
29	Ferrari Dino	19.7	6	  175	2.770
```
The resulting Dataframe and it's shape are displayed to verify that it contains exactly three rows and five columns.
```python
selected_cars.shape
```
```python
(3, 5)
```
Version History 
September 8, 2026 - Initial Commit

September 8, 2026 - Uploaded ipynb file

Septembr 9, 2026 - Updated Code and Read
