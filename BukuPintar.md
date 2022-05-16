# Buku Pintar

## Renaming columns
`pandas.DataFrame.rename(columns={'old_column_name':'new_column_name'})`  
`pandas.DataFrame.columns = ['your', 'new', 'column', 'names']`  
`pandas.DataFrame.set_axis(['your', 'new', 'column', 'names'2], axis=1)`  
(changes the whole set of column headings)

[dataindependent.com/pandas/pandas-change-column-names-3-methods/](https://dataindependent.com/pandas/pandas-change-column-names-3-methods/)

## Dropping columns
`del df['Locations']`  
`df.drop(labels='Locations', 'Founder'], axis=1)`  
`df.drop(columns=['Founder', 'Locations'])`  
(There's more)

[www.machinelearningplus.com/pandas/pandas-drop-column-using-dataframe-drop/](https://www.machinelearningplus.com/pandas/pandas-drop-column-using-dataframe-drop/)

## Listing columns

`df.columns`


[www.machinelearningplus.com/pandas/pandas-drop-column-using-dataframe-drop/](https://www.machinelearningplus.com/pandas/pandas-drop-column-using-dataframe-drop/)

## Doing an anti-join
Do an outer join first:

`df = pd.merge(df1,df2, how='outer', left_on='key', right_on='key', indicator = True)`

The `indicator = True` adds a new column called `_merge` and populates it with either  `both`, `left_only` or `right_only`.

Now to e.g find the left anti-join:

`df.loc[df['_merge']!='left_only']`

[predictivehacks.com/?all-tips=anti-joins-with-pandas](https://predictivehacks.com/?all-tips=anti-joins-with-pandas)

## Exporting without the index
`dfleft.to_csv('hurrah2.csv',index=False)`

## Sorting a dataframe
`df.sort_values(by=['Year','Brand'], inplace=True)`

[datatofish.com/sort-pandas-dataframe/](https://datatofish.com/sort-pandas-dataframe/)

## Multi-argument functions on dataframes
```
>>> def fxy(x, y):
...     return x * y

>>> df['newcolumn'] = df.apply(lambda x: fxy(x['A'], x['B']), axis=1)
>>> df
    A   B  newcolumn
0  10  20        200
1  20  30        600
2  30  10        300
```
[stackoverflow.com/questions/19914937/applying-function-with-multiple-arguments-to-create-a-new-pandas-column](https://stackoverflow.com/questions/19914937/applying-function-with-multiple-arguments-to-create-a-new-pandas-column)

## Single argument function on dataframes
```
def percent(a):
    a = a.replace('%','')
    return float(a)/100
    
df['pct_to_target']=df['pct_to_target'].apply(percent)
```

From Chapter 7 of Talk Python Excel to Python course.

## Extacting things in brackets
```
df['Allocate'] = df['Notes'].str.extract(r'\((.*?)\)', expand=False).str.strip()
```

or

```
notes[notes.find("(")+1:notes.find(")")]
```

## Changing characters
```
df["Times"].str.replace(")","")
df["Times"].str.replace("(","")
```