
# Update
1. df2.update(df1) #Values should be at same index in both the dataframes
   
# concat
1. df3 = pd.concat([df1, df2]).drop_duplicates().reset_index(drop=True) #bydefault axis=0 #drop index and don't add as column
   therefore drop=true.

