# Notes

* Shares a lot of methods with dictionaries     
* One big difference is that you can have multiple indices with the same value (key) 

# Attributes

# Methods

## D
<details> --------------------------------------------
<summary>dtype</summary>
    
property Series.dtype           
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.dtype.html?highlight=dtype#pandas.Series.dtype)        
  
**Notes**
* Checking types 
  * .dtypes 
    * This will get you the data type of the column 
  * Type() 
    * This will get you the variable type (i.e. index, list, object, etc...) 
  * Other Sources:  
    * https://realpython.com/python-type-checking/ 
</details>
    
# G
<details> --------------------------------------------
<summary>get</summary>
  
Series.get(key, default=None)
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.get.html?highlight=get#pandas.Series.get)
  
**Notes**  
* You can pass a list to get multiple indices 
* Acts similar to a dictionary get 
* Also available for the dataframe method
</details>

## I
<details> --------------------------------------------
<summary>items</summary>
  
Series.items()  
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.items.html?highlight=items#pandas.Series.items)
</details>
  
## N
<details> --------------------------------------------
<summary>nunique</summary>
  
DataFrame.nunique(axis=0, dropna=True)  
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.nunique.html?highlight=nunique#pandas.DataFrame.nunique) 
</details>
  
## T
<details> --------------------------------------------
<summary>to_frame</summary>
  
Series.to_frame(name=None)      
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.to_frame.html?highlight=to_frame#pandas.Series.to_frame)  
  
**Notes**
* Converts series to dataframe 
</details>
  
<details> --------------------------------------------
<summary>tolist</summary>  
  
Series.tolist() 
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.tolist.html?highlight=tolist#pandas.Series.tolist)  
  
**Notes**  
* Return a list of the values 
* I prefer the list function over this one   
</details>
    
## U
<details> --------------------------------------------
<summary>unique</summary>
  
Series.unique()   
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.unique.html?highlight=unique#pandas.Series.unique)   
    
**Notes**
* Returns the unique values of the series object 
* Returns values as a numpy array 
* Drop_duplicates keeps it as a dataframe, while unique makes it into a numpy array 
</details>
