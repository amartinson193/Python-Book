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
</details>

<details> --------------------------------------------
<summary>append</summary>
</details>

<details> --------------------------------------------
<summary>apply</summary>
</details>

<details> --------------------------------------------
<summary>assign</summary>
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
</details>

<details> --------------------------------------------
<summary>div</summary>
</details>

<details> --------------------------------------------
<summary>drop</summary>
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

## G
<details> --------------------------------------------
<summary>groupby</summary>
</details>

## I
<details> --------------------------------------------
<summary>iloc</summary>
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
</details>

<details> --------------------------------------------
<summary>isna</summary>
</details>

<details> --------------------------------------------
<summary>iterrows</summary>
</details>

## L
<details> --------------------------------------------
<summary>loc</summary>
</details>

## M
<details> --------------------------------------------
<summary>map</summary>
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
</details>

<details> --------------------------------------------
<summary>pivot_table</summary>
</details>

## Q
<details> --------------------------------------------
<summary>quantile</summary>
</details>

## R
<details> --------------------------------------------
<summary>reindex</summary>
</details>

<details> --------------------------------------------
<summary>rename</summary>
</details>

<details> --------------------------------------------
<summary>replace</summary>
</details>

<details> --------------------------------------------
<summary>resample</summary>
</details>

<details> --------------------------------------------
<summary>reset_index</summary>
</details>

<details> --------------------------------------------
<summary>rolling</summary>
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
</details>

<details> --------------------------------------------
<summary>shift</summary>
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
