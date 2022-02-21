# Automate Csv Data Deletion
**Tools Used: Pandas**

**Description:** 
A simple automation script which deletes unwanted rows and columns from a csv file based on certain keywords, without the user manually opening the files and doing the deletion themselves. 

```python 
def automate_csv(filepath):
    for i in [csv for csv in os.listdir(filepath) if csv.endswith('.csv')]:
        csv_read = pd.read_csv(i, header=None) #1. read csv
    
        refrow2drop = csv_read[csv_read[4].str.contains('REF') == True].index.to_list()[0] #assumes the exact words 'REF'
        clorow2drop = csv_read[csv_read[4].str.contains('CLO') == True].index.to_list()[0] #assumes the exact words 'CLO'
    
        csv_read.drop([refrow2drop, clorow2drop], inplace=True) #2. Drop refrow and clorow
            
        csv_read.drop([3, 4], axis=1, inplace=True) #3. drop unwanted columns -height column and label(REF and CLO)
        
        csv_read.sort_values(by=[0], key=natsort.natsort_keygen(), ascending=True, inplace=True) #4. sort by name
    
        csv_read.to_csv(f"{i}", header=None, index=False) #5. overwrite csv and save in filepath
    
    return 'all done'
``` 

[Github link for complete code and test data](https://github.com/Alyeko/automate-csv)
