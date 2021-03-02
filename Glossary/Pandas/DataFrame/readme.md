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
     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.add.html?highlight=add#pandas.DataFrame.add)        
DataFrame.add(other, axis='columns', level=None, fill_value=None)

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
<summary>any</summary>
     
DataFrame.any(axis=0, bool_only=None, skipna=True, level=None, **kwargs**)        
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.any.html?highlight=any#pandas.DataFrame.any)       
     
**Notes**
* It essentially can flatten a list of boolean values into one True or one False 
</details>
<details> --------------------------------------------
<summary>append</summary>
     
DataFrame.append(other, ignore_index=False, verify_integrity=False, sort=False)           
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.append.html?highlight=append#pandas.DataFrame.append)  

**Notes**
* Append rows of other to the end of caller, returning a new object. 
* Columns in other that are not in the caller are added as new columns. 


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
     
DataFrame.astype(dtype, copy=True, errors='raise')               
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.astype.html?highlight=astype#pandas.DataFrame.astype)         
     
**Notes**
* Converting type of a column for a dataframe 
     * .astype(keyword for type that you need (int, str, etc...)) 
* Converting type 
     * .astype() 
     * E.g. convert to string 
          * .astype('str') 
* Converting to a category can be two things: 
```
cat_dtype = pd.api.types.CategoricalDtype(categories=[2, 1], ordered=True) 
>>> ser.astype(cat_dtype) OR 
Ser.astype(type='category', ordered = True, categories = categories) 
```
</details>

## B
<details> --------------------------------------------
<summary>bfill</summary>
     
DataFrame.bfill(axis=None, inplace=False, limit=None, downcast=None)            
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.bfill.html?highlight=bfill#pandas.DataFrame.bfill)     
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

<details> --------------------------------------------
<summary>corr</summary>
     
DataFrame.count(axis=0, level=None, numeric_only=False)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.count.html?highlight=count#pandas.DataFrame.count)       

</details>
## D
<details> --------------------------------------------
<summary>describe</summary>

DataFrame.describe(percentiles=None, include=None, exclude=None, datetime_is_numeric=False)
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.describe.html?highlight=describe#pandas.DataFrame.describe)        
     
</details>

<details> --------------------------------------------
<summary>div</summary>
     
DataFrame.div(other, axis='columns', level=None, fill_value=None)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.div.html?highlight=div#pandas.DataFrame.div)
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
     
Series.drop_duplicates(keep='first', inplace=False)              
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.drop_duplicates.html)         
     
**Notes**
* Get the unique values for a selected column 
     
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
     
DataFrame.duplicated(subset=None, keep='first')             
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.duplicated.html?highlight=duplicated#pandas.DataFrame.duplicated)       
     
**Notes**
* Can use this to get a list of the duplicated values 
</details>

## E

<details> --------------------------------------------
<summary>equals</summary>
     
DataFrame.equals(other)            
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.equals.html?highlight=equals#pandas.DataFrame.equals)     
</details>  
<details> --------------------------------------------
<summary>expanding</summary>
          
DataFrame.expanding(min_periods=1, center=None, axis=0)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.expanding.html?highlight=expanding#pandas.DataFrame.expanding)     
     
**Notes**
* Creates a running total, mean, etc... Whatever aggregation you want 
* Grows as it goes down the rows 
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

<details> --------------------------------------------
<summary>isna</summary>
     
DataFrame.isna()              
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.isna.html?highlight=isna#pandas.DataFrame.isna)          
     
**Notes**
* Returns all values as boolean 
* Count the number of nulls in pandas 
     * .isna().sum() 
     * Isnull().sum() 
* Isnull is an alias of isna 
* dataframe.isna().any() 
     * Tells you if there are any na's by column 
     * Not above 
* dataframe.isna().fillna(0) 

</details>


## G
<details> --------------------------------------------
<summary>groupby</summary>
     
DataFrame.groupby(by=None, axis=0, level=None, as_index=True, sort=True, group_keys=True, squeeze=\lesserthanhere object object \greaterthanhere, observed=False, dropna=True)       
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.groupby.html)              
     
**Notes**       
* User guide: https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html   
* Another reference: https://realpython.com/pandas-groupby/   
* Sort within a groupby : https://medium.com/@arccoder/pandas-sort-within-groups-e1f3b6a10a3f   
* E.g. grouped2 = grouped.groupby('year').apply(lambda x: x.sort_values(['set_num'],ascending=False))   
* If specifying more than one aggregation in agg, you need a list  
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
     
DataFrame.melt(id_vars=None, value_vars=None, var_name=None, value_name='value', col_level=None, ignore_index=True)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.melt.html?highlight=melt#pandas.DataFrame.melt)     

**Notes**
* See also reset_index() 
* Example: 
```
import pandas as pd 
df = pd.DataFrame( 
    {'id':range(1,4), 'var_day':['Monday','Tuesday','Wednesday'], 'Week':[11,12,13]} 
) 
print(df,'\n') 
print(df.melt(id_vars='id', value_vars='Week', var_name='VARIABLE',value_name='VALUE')) 
```
</details>

<details> --------------------------------------------
<summary>memory_usage</summary>
     
DataFrame.memory_usage(index=True, deep=False)              
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.memory_usage.html?highlight=memory_usage#pandas.DataFrame.memory_usage)      
     
**Notes**
* Returns the memory usage by column 

</details>

<details> --------------------------------------------
<summary>merge</summary>
     
DataFrame.merge(right, how='inner', on=None, left_on=None, right_on=None, left_index=False, right_index=False, sort=False, suffixes=('_x', '_y'), copy=True, indicator=False, validate=None)            
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html)      

**Notes** 
* See also pd.merge() 
* Merging on multiple columns 
```
Data1.merge(data2, on = ['col1','col2']) 
```
* Merging multiple tables 
```
Data1.merge(data2, on='col1').merge(data3, on='other_col') 
```
* Merging on index 
     * Exact same way on columns since the merge method adjusts the on argument to either index or col names 
     * Need to use left_index=True and right_index=True when using the left_on and right_on arguments with index 
* Semi-Join 
     * Returns the intersection, similar to an inner join 
     * Returns only columns from the left table and not the right 
     * No duplicates
```
genres_tracks = genres.merge(top_tracks, on='gid'(
top_genres = genres[genres['gid'].isin(genres_tracks['gid'])]
print(top_genres.head())
 ```
 * Steps for the above code:
     * 1. Merge using an inner join 
     * 2. Filter using isin() 
     
* Anti-join
     * Returns the left table, excluding the intersection
     * Returns only columns from the left table and **not** the right
     
```
genres_tracks = genres.merge(top_tracks, on='gid', how='left', indicator=True)
gid_list = genres.tracks.loc[genrees_tracks['_merge'] == 'left_only','gid']
non_top_genres = genres[genres['gid'].isin(gid_list)]
print(non_top_genres.head())
```  
     
* Steps for the code above
     * 1. Merge using a left join 
     * 2. Filter to left only 
     * 3. Use the result with the isin()     
</details>

<details> --------------------------------------------
<summary>merge_asof</summary>
          
pandas.merge_asof(left, right, on=None, left_on=None, right_on=None, left_index=False, right_index=False, by=None, left_by=None, right_by=None, suffixes=('_x', '_y'), tolerance=None, allow_exact_matches=True, direction='backward')                    
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge_asof.html)      
     
**Notes**
* Fuzzy Matching - How to join on non-exact fields, such as date time 
     * Use the merge_asof method 
   
</details>

<details> --------------------------------------------
<summary>merge_ordered</summary>
                 
pandas.merge_ordered(left, right, on=None, left_on=None, right_on=None, left_by=None, right_by=None, fill_method=None, suffixes=('_x', '_y'), how='outer')      
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.merge_ordered.html?highlight=merge_ordered#pandas.merge_ordered)        

**Notes**
* How to forward/back fill
     * Use the fill_method arg of dataframe.pandas.merge_ordered     
</details>

<details> --------------------------------------------
<summary>mul</summary>
     
DataFrame.mul(other, axis='columns', level=None, fill_value=None)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.mul.html?highlight=mul#pandas.DataFrame.mul)        

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
<summary>pivot</summary>
     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.pivot.html)      
DataFrame.pivot(index=None, columns=None, values=None)      
     
**Notes**
* Only has 3 inputs and is a lower-level form of pivot_table 
* Does not support aggregation, multiple values create a hierarchical index 
  
</details> 
<details> --------------------------------------------
<summary>pivot_table</summary>
     
pandas.pivot_table(data, values=None, index=None, columns=None, aggfunc='mean', fill_value=None, margins=False, dropna=True, margins_name='All', observed=False)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.pivot_table.html?highlight=pivot_table#removepandas.pivot_table)     
     
**Notes** 
* Pivot a Table 
```
table = pd.pivot_table(df, values=['D', 'E'], index=['A', 'C'], 
...                     aggfunc={'D': np.mean, 
...                              'E': np.mean}) 
>>> table 
                D         E 
A   C 
bar large  5.500000  7.500000 
    small  5.500000  8.500000 
foo large  2.000000  4.500000 
    small  2.333333  4.333333 
```
* Just remember: value, index, column, aggfunc 
* Need to do dataframe.pivot_table, otherwise include data argument in the pivot table function 
</details>

## Q
<details> --------------------------------------------
<summary>quantile</summary>
     
DataFrame.quantile(q=0.5, axis=0, numeric_only=True, interpolation='linear')                
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.quantile.html?highlight=quantile#pandas.DataFrame.quantile)     

</details>

<details> --------------------------------------------
<summary>query</summary>
     
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

## R
<details> --------------------------------------------
<summary>reindex</summary>
     
DataFrame.reindex(labels=None, index=None, columns=None, axis=None, method=None, copy=True, level=None, fill_value=nan, limit=None, tolerance=None)             
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.reindex.html?highlight=reindex#pandas.DataFrame.reindex)     
     
**Notes**
* Reindex a dataframe 
* Cols = ['a', 'b', 'c', 'd', 'e'] 
* Df = df.reindex(cols) 

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
     
Series.replace(to_replace=None, value=None, inplace=False, limit=None, regex=False, method='pad')             
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.replace.html?highlight=replace#pandas.DataFrame.replace)      
     
**Parameters**
* to_replace = str, regex, list, dict, Series, int, float, or None 
     * string to be replaced 
     * How to find the values that will be replaced. 
     * numeric, str or regex: 
          * numeric: numeric values equal to to_replace will be replaced with value 
          * str: string exactly matching to_replace will be replaced with value 
          * regex: regexs matching to_replace will be replaced with value 
     * list of str, regex, or numeric: 
          * First, if to_replace and value are both lists, they must be the same length. 
          * Second, if regex=True then all of the strings in both lists will be interpreted as regexs otherwise they will match directly. This doesn’t matter much for value since there are only a few possible substitution regexes you can use. 
          * str, regex and numeric rules apply as above. 
     * dict: 
          * Dicts can be used to specify different replacement values for different existing values. For example, {'a': 'b', 'y': 'z'} replaces the value ‘a’ with ‘b’ and ‘y’ with ‘z’. To use a dict in this way the value parameter should be None. 
          * For a DataFrame a dict can specify that different values should be replaced in different columns. For example, {'a': 1, 'b': 'z'} looks for the value 1 in column ‘a’ and the value ‘z’ in column ‘b’ and replaces these values with whatever is specified in value. The value parameter should not be None in this case. You can treat this as a special case of passing two lists except that you are specifying the column to search in. 
          * For a DataFrame nested dictionaries, e.g., {'a': {'b': np.nan}}, are read as follows: look in column ‘a’ for the value ‘b’ and replace it with NaN. The value parameter should be None to use a nested dict in this way. You can nest regular expressions as well. Note that column names (the top-level dictionary keys in a nested dictionary) cannot be regular expressions. 
     * None: 
          * This means that the regex argument must be a string, compiled regular expression, or list, dict, ndarray or Series of such elements. If value is also None then this must be a nested dictionary or Series. 
* See the examples section for examples of each of these. 
* Value = string to replace text of value to be replaced 
     
**Notes**
* The bitwise | operator (or) works when looking at Strings 
* See also Pandas.DataFrame.map 
</details>

<details> --------------------------------------------
<summary>resample</summary>
     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.resample.html?highlight=resample#pandas.DataFrame.resample)              
DataFrame.resample(rule, axis=0, closed=None, label=None, convention='start', kind=None, loffset=None, base=None, on=None, level=None, origin='start_day', offset=None)        
     
**Parameters**
* Rule = [DateOffset, Timedelta or str]; The offset string or object representing target conversion. 
     * e.g. 'M' for month 
     * Here is a list of all the rules (source: https://stackoverflow.com/questions/17001389/pandas-resample-documentation) 
``` 
B business day frequency 
C custom business day frequency (experimental) 
D calendar day frequency 
W weekly frequency 
M month end frequency 
SM semi-month end frequency (15th and end of month) 
BM business month end frequency 
CBM custom business month end frequency 
MS month start frequency 
SMS semi-month start frequency (1st and 15th) 
BMS business month start frequency 
CBMS custom business month start frequency 
Q quarter end frequency 
BQ business quarter endfrequency 
QS quarter start frequency 
BQS business quarter start frequency 
A year end frequency 
BA, BY business year end frequency 
AS, YS year start frequency 
BAS, BYS business year start frequency 
BH business hour frequency 
H hourly frequency 
T, minminutely frequency 
S secondly frequency 
L, ms milli seconds 
U, us microseconds 
N nanoseconds 
```
     
**Notes**
* Pandas.dataframe.resample 
* Makes grouping by month or any other time period really easy 
* Meant for time series 
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
     
DataFrame.round(decimals=0, *args*, **kwargs**)      
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.round.html?highlight=round#pandas.DataFrame.round)      
     
**Notes**
* Can also round each column separately 

</details>

## S
<details> --------------------------------------------
<summary>sample</summary>
     
DataFrame.sample(n=None, frac=None, replace=False, weights=None, random_state=None, axis=None)           
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sample.html?highlight=sample#pandas.DataFrame.sample)     
</details>

<details> --------------------------------------------
<summary>set_index</summary>
     
DataFrame.set_index(keys, drop=True, append=False, inplace=False, verify_integrity=False)     
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.set_index.html?highlight=set_index)

</details>

<details> --------------------------------------------
<summary>shift</summary>
     
DataFrame.shift(periods=1, freq=None, axis=0, fill_value=\lesserthanhere object object \greaterthanhere)     
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
     
DataFrame.sort_index(axis=0, level=None, ascending=True, inplace=False, kind='quicksort', na_position='last', sort_remaining=True, ignore_index=False, key=None)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_index.html?highlight=sort_index#pandas.DataFrame.sort_index)
     
     
</details>

<details> --------------------------------------------
<summary>sort_values</summary>
     
DataFrame.sort_values(by, axis=0, ascending=True, inplace=False, kind='quicksort', na_position='last', ignore_index=False, key=None)             
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.sort_values.html)     
     
**Parameters**
* Key
     * Apply the key function to the values before sorting. This is similar to the key argument in the builtin sorted() function, with the notable difference that this key function should be vectorized. It should expect a Series and return a Series with the same shape as the input. It will be applied to each column in by independently. 
     
</details>

<details> --------------------------------------------
<summary>std</summary>
     
DataFrame.std(axis=None, skipna=None, level=None, ddof=1, numeric_only=None, **kwargs)         
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.std.html)        

</details>

<details> --------------------------------------------
<summary>subtract</summary>
     
DataFrame.subtract(other, axis='columns', level=None, fill_value=None)          
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.subtract.html)
**Notes**
* Subtract from all elements in the dataframe 
     * Df - 1 
     * Df.subtract(1) 
     * Df.loc[df['eggs']-1] 
</details>

<details> --------------------------------------------
<summary>sum</summary>
     
DataFrame.sum(axis=None, skipna=None, level=None, numeric_only=None, min_count=0, **kwargs**)    
[Docs](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.sum.html?highlight=sum#pandas.DataFrame.sum)       

</details>

## T
<details> --------------------------------------------
<summary>to_dict</summary>
     
DataFrame.to_dict(orient='dict', into=<class 'dict'>)            
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_dict.html?highlight=to_dict#pandas.DataFrame.to_dict)      

</details>

<details> --------------------------------------------
<summary>transform</summary>
     
DataFrameGroupBy.transform(func, *args*, engine=None, engine_kwargs=None, **kwargs**)     
[Docs] (https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.core.groupby.DataFrameGroupBy.transform.html?highlight=transform#pandas.core.groupby.DataFrameGroupBy.transform)
     
**Notes**
* Turn a dataframe into a dictionary 
* By argument specifies if you want a nested dictionary (default) or a list or something else 
</details>

## U
<details> --------------------------------------------
<summary>unstack</summary>
     
DataFrame.unstack(level=- 1, fill_value=None)               
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.unstack.html?highlight=unstack#pandas.DataFrame.unstack) 
     
**Notes**
* Pivot a multi-index into a dataframe 
</details>

## V
<details> --------------------------------------------
<summary>value_counts</summary>
     
DataFrame.value_counts(subset=None, normalize=False, sort=True, ascending=False)               
[Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.value_counts.html?highlight=value_counts#pandas.DataFrame.value_counts)   
     
**Notes**
* Series value counts has diff params 
</details>
