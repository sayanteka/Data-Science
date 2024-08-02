
# Update
1. df2.update(df1) 
   
# concat
1. df3 = pd.concat([df1, df2],ignore_index=True).drop_duplicates().reset_index(drop=True)  
   
# Merge
1. df3=pd.merge(df2,df1,how="outer", indicator="Exist") 
   
# If else in pandas
1. df['A']=  df['C'].where(df['C'].notna(),df['A']) 
2. df['A']=  df['A'].where(df['C'].isna(),df['C'])
3. df.replace('', np.nan, inplace=True)
4. df['abc'] =np.where(df['M'].isna() & ~df['Earliest_M'].isna(),2, np.where(~df['M'].isna(), 1, np.nan))

# Loc & Filtering
1. for index,row in df.iterrows():
   
       df.loc[index, 'colA']=row['colB']
   
2. data.loc[(data['colA'] == 'val1') & (data['colB'] == 'val2'), 'colB'] = new_value

3. df.loc[df['colA'] == 'val1', 'colB']*=5

4. df[df['year'].isin([2017, 2018])]

# Statistics
1. df.info()
   
2. df['A'].value_counts()
   
3. df.sort_values(by = ['colA', 'colB'], ascending = [False, True]).head(2)

4. df.drop_duplicates(subset=['colA']).head(2)
   
5. df['colA'].drop_duplicates().head(2)

6. df.unique()

7. df.nunique()

# Rank
1. df['rank'] = df['position'].rank(method='first')
   
   top10 = df[df['rank'] <= 10]

# Explode

1. df['A']=df['A'].str.split('/')

2. df=df.explode('A')

3. df['A']=pd.to_numeric(df['A'])

# GroupBy
1. df.groupby(['A', 'B'])['C'].mean()
   
2. df.groupby(['A', 'B'],as_index=False)['C'].mean()

3. df.groupby(['A','B'], as_index = False).agg({'C' : 'mean'})

4. df.groupby(['A','B'], as_index = False).agg({'C' : 'mean','D':'max'})

5. def custom_func(group):
    if group['G'].eq('COM').any() and pd.isna(group['A']).any() and group['Category'].eq('Gen').any():
   
        group.loc[group['Gate'] == 'not_in_category', 'Actual'] = np.nan
   
    return group

6. indices = group[group['A'] == '3'].index
   
   is_blank = group.loc[indices, 'Actual'].isna()
   
   table.loc[3_indices[is_blank], 'Actual'] = date


# Lambda
1. df['A'] = df['A'].apply(lambda x : len(x.split(",")))

2. df= df.applymap(lambda x: x.strip() if type(x) == str and x.strip() != x else x)

3. df_set = set(zip(df2['A'], df2['B'], df2['C'], df2['D']))

4. filtered_df = df1[(df1.apply(lambda row: (row['A'], row['B'],row['C'],row['D']) not in 
   df_set,axis=1))].reset_index(drop=True)

# Regex
 1. matches = df['Email'].str.contains(pattern, regex=True)
    
    print(df[matches])
    
    pattern: '@example\.com$'

2. for index, name in enumerate(id):
   
       df.loc[df['B'].str.contains(name, regex=True, na=False), 'B'] = name

# idxmax or idxmin

1. df.idxmax()
   
2. df.idxmin()

# iter-tuples

1. for row in df.itertuples(index=True, name='Pandas'):
   
       print(getattr(row, "Name"), getattr(row, "Percentage"))

# Pivot-table

1. df.set_index('Name')
   
2. pivot_table = pd.pivot_table(df, values='Value', index='Date', columns='Categorical_col_val', aggfunc='sum')
     


   


