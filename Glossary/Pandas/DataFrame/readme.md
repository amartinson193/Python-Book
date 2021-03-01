# Notes

[Docs - Full list of methods + attributes](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html)    
[Using text in Pandas Tutorial](https://pandas.pydata.org/pandas-docs/stable/user_guide/text.html )

To select columns as a dataframe use [[]]    
To select columns as a series use []     
To select a multi-index use tuples     
     
# Attributes

* shape
* columns
* index
* values
* dtypes

# Methods

## A
<details> --------------------------------------------
<summary>add</summary>
</details>

<details> --------------------------------------------
<summary>agg</summary>
     
DataFrame.agg(func=None, axis=0, *args, **kwargs)           
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.agg.html?highlight=agg#pandas.DataFrame.agg)  
     
**Notes** 
* Agg is short for aggregate, use the alias instead 
* Agg using a dictionary: data.groupby('Species').agg({'SepalLengthCm':'mean','SepalWidthCm':'median'}) 
     
</details>

<details> --------------------------------------------
<summary>append</summary>
</details>

<details> --------------------------------------------
<summary>apply</summary>
     
DataFrame.apply(func, axis=0, raw=False, result_type=None, args=(), **kwds)         
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.apply.html)          
**Notes** 
* Use a function on all values in a dataframe 
* Apply can be used, but transform or agg should try to be used first since they are faster 
* I guess map is another option here too 
     
</details>

<details> --------------------------------------------
<summary>assign</summary>
     
DataFrame.assign(**kwargs)              
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.assign.html?highlight=assign#pandas.DataFrame.assign)
     
**Notes** 
* Create multiple new columns at once 
</details>

<details> --------------------------------------------
<summary>astype</summary>
</details>

## B
<details> --------------------------------------------
<summary>bfill</summary>
</details>

## C
<details> --------------------------------------------
<summary>copy</summary>
          
 DataFrame.copy(deep=True)         
 [Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.copy.html?highlight=copy#pandas.DataFrame.copy)         
          
 **Notes**
 * Manipulate the dataset without changing the original data 
 * Also for Series/Index
</details>

<details> --------------------------------------------
<summary>corr</summary>
     
DataFrame.corr(method='pearson', min_periods=1)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.corr.html?highlight=corr#pandas.DataFrame.corr )    
     
**Parameters**     
* Method (opt) = (‘pearson’, ‘kendall’, ‘spearman’}) 
* Min_periods (opt) = the minimum number of observations to compute a correlation, only available for pearson and spearman 
     
**Notes**
* This only works for linear relationships. It will underestimate non-linear relationships. 
</details>

## D
<details> --------------------------------------------
<summary>describe</summary>

DataFrame.describe(percentiles=None, include=None, exclude=None, datetime_is_numeric=False)
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.describe.html?highlight=describe#pandas.DataFrame.describe)        
     
</details>

<details> --------------------------------------------
<summary>div</summary>
</details>

<details> --------------------------------------------
<summary>drop</summary>
     
DataFrame.drop(labels=None, axis=0, index=None, columns=None, level=None, inplace=False, errors='raise')      
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop.html)
     
**Notes** 
* Remove a column or items in a column/row 
* Pandas.dataframe.drop -- gold standard 
* Del df['column to be deleted'] 
* E.g. - Source: Cleaning Data in Python - "Data Range Constraints" Video 
* Using .index to create a dataframe and pass an expression to drop #dotindex 
```
# Drop values using filtering
movies = movies[movies['avg_rating'] <= 5]
# Drop values using .drop()
movies.drop(movies[movies['avg_rating'] > 5].index, inplace = True)
```
* An alternate method for dropping rows is using the tilde operator. See keywords -> tilde for more details 
</details>

<details> --------------------------------------------
<summary>drop_duplicates</summary>
</details>

<details> --------------------------------------------
<summary>dropna</summary>
 
 DataFrame.dropna(axis=0, how='any', thresh=None, subset=None, inplace=False)        
 [Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.dropna.html?highlight=dropna#pandas.DataFrame.dropna)        
          
**Parameters**
* axis{0 or ‘index’, 1 or ‘columns’}, default 0 
     * Determine if rows or columns which contain missing values are removed. 
     * 0, or ‘index’ : Drop rows which contain missing values. 
     * 1, or ‘columns’ : Drop columns which contain missing value. 
     * Changed in version 1.0.0: Pass tuple or list to drop on multiple axes. Only a single axis is allowed. 
* how{‘any’, ‘all’}, default ‘any’ 
     * Determine if row or column is removed from DataFrame, when we have at least one NA or all NA. 
* ‘any’ : If any NA values are present, drop that row or column. 
* ‘all’ : If all values are NA, drop that row or column. 
* thresh: int, optional 
     * Require that many non-NA values. 
* Subset = array-like, optional 
     * Labels along other axis to consider, e.g. if you are dropping rows these would be a list of columns to include. 
     * Has to be a list 

**Notes**      
* Also applies to Series and Index
</details>

<details> --------------------------------------------
<summary>duplicated</summary>
</details>

## E
<details> --------------------------------------------
<summary>expanding</summary>
</details>

## F
<details> --------------------------------------------
<summary>fillna</summary>.
     
DataFrame.fillna(value=None, method=None, axis=None, inplace=False, limit=None, downcast=None)           
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.fillna.html?highlight=fillna)            
          
**Parameters**
* Value (partial req; value or method) = The number/string to use as a filler, can also be a dictionary 
     * e.g. To fill with the mean, you would do something like  
```
rating_mean= wine['rating'].mean() 
wine_imputed= wine.fillna({'rating': rating_mean})
```
     
**Notes**     
* Fill missing values 
</details>

## I
<details> --------------------------------------------
<summary>iloc</summary>
     
property DataFrame.iloc            
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.iloc.html#pandas.DataFrame.iloc)     

</details>

<details> --------------------------------------------
<summary>index</summary>
     
DataFrame.index: Index
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.index.html?highlight=index#pandas.DataFrame.index)
     
     
</details>


## G
<details> --------------------------------------------
<summary>groupby</summary>
     
</details>   

<details> --------------------------------------------
<summary>info</summary>
      
 DataFrame.info(verbose=None, buf=None, max_cols=None, memory_usage=None, show_counts=None, null_counts=None)          
 [Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.info.html?highlight=info#pandas.DataFrame.info )         
          
 **Notes**
 * Find general information like dtypes and non-null counts 
 * See also describe
 * Similar to summary in R
</details>

<details> --------------------------------------------
<summary>isin</summary>
     
DataFrame.isin(values)     
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.isin.html)      
     
**Notes**
* Similar to 'in' using SQL 
</details>

<details> --------------------------------------------
<summary>isna</summary>
</details>

<details> --------------------------------------------
<summary>iterrows</summary>

DataFrame.iterrows()
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.iterrows.html)

**Notes**
* Loop over rows of a dataframe 
</details>

## L
<details> --------------------------------------------
<summary>loc</summary>
     
property DataFrame.loc             
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.loc.html)

**Notes** 
* Changing a data value 
     * wards.loc[wards['ward'] == '1', 'ward'] = '61' 
* Select a column 
     * gdp_sp500.loc[:,['gdp','returns']] 
     * Need to use the colon 
* Select all columns following a certain column by using colons after the name 
     * Data.loc[:,'columns':]      
</details>

## M
<details> --------------------------------------------
<summary>map</summary>
     
Series.map(arg, na_action=None)    
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.Series.map.html?highlight=map#pandas.Series.map)

**Notes** 
* Replace values in a dataframe 
* Pandas.dataframe.map 
* Map values to a dataframe 
* E.g. from https://kanoki.org/2019/04/06/pandas-map-dictionary-values-with-dataframe-columns/:
```
country_capital= { 'Germany':'Berlin', 'Brazil':'Brasília', 'Budapest':'Hungary', 'China':'Beijing', 'India':'New Delhi', 'Norway':'Oslo', 'France':'Paris', 'Indonesia': 'Jakarta', 'USA':'Washington' } 

df['Capital'] = df['Country'].map(country_capital) 
```
* See also Dataframe.pandas.replace 
* I think the main difference is replace replaces the values for the column specified, but that doesn't seem like that big of a difference 
* This is very similar to the map base function in Python –except this version can take a dictionary instead of just functions like in the base Python version 

</details>

<details> --------------------------------------------
<summary>max</summary>    
     
DataFrame.max(axis=None, skipna=None, level=None, numeric_only=None, **kwargs)       
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.max.html?highlight=max#pandas.DataFrame.max )       
 
</details>

<details> --------------------------------------------
<summary>mean</summary>
     
DataFrame.mean(axis=None, skipna=None, level=None, numeric_only=None, **kwargs)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.mean.html)   
     
**Notes**     
* Mean can be used on strings     
* Not a built in function     
</details>

<details> --------------------------------------------
<summary>melt</summary>
</details>

<details> --------------------------------------------
<summary>memory_usage</summary>
</details>

<details> --------------------------------------------
<summary>merge</summary>
</details>

<details> --------------------------------------------
<summary>merge_asof</summary>
</details>

<details> --------------------------------------------
<summary>merge_ordered</summary>
</details>

<details> --------------------------------------------
<summary>mul</summary>
</details>

## N
<details> --------------------------------------------
<summary>nlargest</summary>
         
DataFrame.nlargest(n, columns, keep='first')           
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.nlargest.html)   
     
**Parameters**
* N(required) = integer of the number of largest values in desc order 
* Columns(required) = label or list of labels 
* Keep ('first','last', or 'all'): If duplicates, which occurrence do you keep 
          
**Notes**          
* Get the top 5 in a data frame
* Select the first or second row of a groupby 
     * https://stackoverflow.com/questions/20067636/pandas-dataframe-get-first-row-of-each-group 
     * .first() 
     * .nth() 
     * .head()  
</details>

<details> --------------------------------------------
<summary>notna</summary>
     
DataFrame.notna()
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.notna.html#pandas.DataFrame.notna)

**Notes** 
* Identify non-null values 
</details>

<details> --------------------------------------------
<summary>nsmallest</summary>
      
DataFrame.nsmallest(n, columns, keep='first')          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.nsmallest.html)      
          
**Parameters**
* N(required) = integer of the number of largest values in desc order 
* Columns(required) = label or list of labels 
* Keep ('first','last', or 'all'): If duplicates, which occurrence do you keep 
</details>

## P
<details> --------------------------------------------
<summary>pct_change</summary>
     
DataFrame.pct_change(periods=1, fill_method='pad', limit=None, freq=None, **kwargs)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.pct_change.html?highlight=pct_change#pandas.DataFrame.pct_change)

**Notes**
* Use previous rows in calculating percent change 
</details>

<details> --------------------------------------------
<summary>pivot_table</summary>
</details>

## Q
<details> --------------------------------------------
<summary>quantile</summary>
     
DataFrame.query(expr, inplace=False, **kwargs)              
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.query.html?highlight=query#pandas.DataFrame.query)

**Notes**
* Restrict the data using SQL where-like statements 
     * Dataframe.query() 
          * Enter a SQL-like statement in quotes 
          * Need == instead of one = to say something is equal to 
          * Double quotes are also needed around words 
          * Used to unintentionally ending the statement 
</details>

<details> --------------------------------------------
<summary>query</summary>
</details>

## R
<details> --------------------------------------------
<summary>reindex</summary>
</details>

<details> --------------------------------------------
<summary>rename</summary>
     
DataFrame.rename(mapper=None, index=None, columns=None, axis=None, copy=True, inplace=False, level=None, errors='ignore')              
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rename.html?highlight=rename#pandas.DataFrame.rename)     

**Parameters**
* Mapper (req) = dictionary or function to remap the values 
* Index = dict-like or function; Alternative to specifying axis (mapper, axis=0 is equivalent to index=mapper). 
* Columns = dict-like or function; Alternative to specifying axis (mapper, axis=1 is equivalent to columns=mapper). 
* Axis (opt) = specify which axis you are renaming using either a string ('axis', 'column') or integer 
* Level (opt) = only rename for the level specified 

**Notes** 
* Rename a column 
* Either rename all columns by passing a list equal to df.columns length OR use pandas.df.rename() 
     * https://stackoverflow.com/questions/11346283/renaming-columns-in-pandas 
</details>

<details> --------------------------------------------
<summary>replace</summary>
</details>

<details> --------------------------------------------
<summary>resample</summary>
</details>

<details> --------------------------------------------
<summary>reset_index</summary>
     
DataFrame.reset_index(level=None, drop=False, inplace=False, col_level=0, col_fill='')         
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.reset_index.html?highlight=reset_index#pandas.DataFrame.reset_index)

</details>

<details> --------------------------------------------
<summary>rolling</summary>

DataFrame.rolling(window, min_periods=None, center=False, win_type=None, on=None, axis=0, closed=None)        
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.rolling.html?highlight=rolling#pandas.DataFrame.rolling)

**Notes**
* Can just add .sum() at the end in order to get the sum for the rolling window
</details>

<details> --------------------------------------------
<summary>round</summary>
</details>

## S
<details> --------------------------------------------
<summary>sample</summary>
</details>

<details> --------------------------------------------
<summary>set_index</summary>
     
DataFrame.set_index(keys, drop=True, append=False, inplace=False, verify_integrity=False)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.set_index.html?highlight=set_index)

</details>

<details> --------------------------------------------
<summary>shift</summary>
     
DataFrame.shift(periods=1, freq=None, axis=0, fill_value=<object object>)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.shift.html?highlight=shift#pandas.DataFrame.shift)  
     
**Notes**
* Use previous rows in a calculation      

</details>

<details> --------------------------------------------
<summary>size</summary>       
     
DataFrame.size           
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.size.html?highlight=size#pandas.DataFrame.size )    
          
**Notes**
* Number of rows if Series or the number of columns * rows if dataframe 
</details>

<details> --------------------------------------------
<summary>smallest</summary>
</details>

<details> --------------------------------------------
<summary>sort_index</summary>
</details>

<details> --------------------------------------------
<summary>sort_values</summary>
</details>

<details> --------------------------------------------
<summary>std</summary>
     
DataFrame.std(axis=None, skipna=None, level=None, ddof=1, numeric_only=None, **kwargs)         
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.std.html)        

</details>

<details> --------------------------------------------
<summary>subtract</summary>
</details>

<details> --------------------------------------------
<summary>sum</summary>
</details>

## T
<details> --------------------------------------------
<summary>to_dict</summary>
</details>

<details> --------------------------------------------
<summary>transform</summary>
     
DataFrameGroupBy.transform(func, *args, engine=None, engine_kwargs=None, **kwargs)     
[Docs] (https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.transform.html?highlight=transform#pandas.core.groupby.DataFrameGroupBy.transform)


</details>

## U
<details> --------------------------------------------
<summary>unique</summary>
</details>

<details> --------------------------------------------
<summary>unstack</summary>
</details>

## V
<details> --------------------------------------------
<summary>value_counts</summary>
</details>
