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
<summary>fillna</summary>
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
