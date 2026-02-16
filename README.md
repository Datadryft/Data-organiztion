"# Data-organization" 

# Data-organization (Weather Station Analysis)

 In this File I used Python and Google collab to seperate CSV formatted Data 
  Open This file In google collab and you should be able to 
  Run the code in blocks so you can see every step of the way
  
  Make sure that you uploaded your data into google collabe if you are going to use 
  Google collab, if you are using Other coding software
  Make sure that your data is in the correct Directory, and That is it in CSV format
  As this code Is designed for CSV
  
## Getting Into Data Orginzation
  
  First Step is to import the necessary Modules 
  
  ```python
import pandas as pd
import numpy as np
  
```

Next step is to make sure that your data is the right directory, for use.


![Screenshot 2023-04-14 112250](https://user-images.githubusercontent.com/70156560/232087014-ee873bcb-3747-402a-9bae-e126f1de5a59.png)

After That Use the Pandas Libraries to read in the CSV file as a DataFrame object:

```
df = pd.read_csv('/content/1m-PDDS(2023-04-12).csv')
```

Then Sort the Data Frames Based on the Variables

```

df = df.sort_values(by=['Location', 'Site', 'Plot','Subplot'])
```

You Can use the print function to view your how your data is organized thus far

```
print(df_sorted)
print(df_sorted.head())
```

Should look somthing Like this (Based on the variables you used)

![Screenshot 2023-04-14 112942](https://user-images.githubusercontent.com/70156560/232088151-26b04cfd-fc3b-4001-8f95-76f4b5edfe1f.png)



Great! Now We will begin grouping the data
```
grouped_df.size()
```


![Screenshot 2023-04-14 113148](https://user-images.githubusercontent.com/70156560/232088748-b9cdf6e2-06d5-4089-a583-3821bd138959.png)



It will look like this showing you how it is grouped and how many times it repeats

Next is Grouping and Download in groups of "Location, Site, Plot" Variables

```
grouped = df_sorted.groupby(['Location', 'Site', 'Plot'])

for name, group in grouped:
    filename = f"{name[0]}_{name[1]}_{name[2]}.csv"
    group.to_csv(filename, index=False)
```


## And Thats It!

Review Your Data to Make sure all went Well 
#Happy Coding!
