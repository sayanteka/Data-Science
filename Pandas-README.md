
# Update
1. df2.update(df1) 
   
# concat
1. df3 = pd.concat([df1, df2]).drop_duplicates().reset_index(drop=True)  
   
# Merge
1. df3=pd.merge(df2,df1,how="outer", indicator="Exist") 
   
# If else in pandas
1. df['A']=  df['C'].where(df['C'].notna(),df['A']) 
2. df['A']=  df['A'].where(df['C'].isna(),df['C'])
3. df.replace('', np.nan, inplace=True)
4. df['abc'] =np.where(df['M'].isna() & ~df['Earliest_M'].isna(),2, np.where(~df['M'].isna(), 1, np.nan))

# Loc
1. for index,row in df.iterrows():
   
       df.loc[index, 'colA']=row['colB']
   
2. data.loc[(data['colA'] == 'val1') & (data['colB'] == 'val2'), 'colB'] = new_value

3. df.loc[df['colA'] == 'val1', 'colB']*=5

# Statistics
1. df.info()
   
2. df['A'].value_counts()
   
3. df.sort_values(by = ['colA', 'colB'], ascending = [False, True]).head(2)

4. df.drop_duplicates(subset=['colA']).head(2)
   
5. df['colA'].drop_duplicates().head(2)

# Rank
1. df['rank'] = df['position'].rank(method='first')
   
   top10 = df[df['rank'] <= 10]


   


