
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
   
2.


