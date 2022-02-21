# Machine Learning Classification of Crops
**Tools Used: Python, Pandas, Scikit-Learn, Matplotlib**

**Description:** 
(Project in Progress...)

1. Exploratory Data Analysis of the crop dataset
2. Feature Engineering 
3. Dealing with imbalanced nature of the data using SMOTE
4. Hyperparameter tuning 
5. Checking the accuracy of the model using the validation set 
6. Classification of the test data using diferent machine learning algorithms.
```python
df = pd.DataFrame({'labels':['1', '2', '3', '4', '5', '6', '7'], 'value':[len(data[data['label']==n+1]) for n in range(data['label'].nunique())]})
ax = df.plot.bar(x='labels', y='value', rot=0)
plt.rcParams['figure.figsize'] =[7, 5]
plt.ylabel('Total number of occurences in dataset')

mapping = {1:'Corn', 2:'Pea', 3:'Canola', 4:'Soy', 5:'Oat', 6:'Wheat', 7:'Broadleaf'           
for j in mapping:
    print('{} has {}% rows of data out of the entire dataset.'.format(mapping[j], round(len(data[data['label']==j])/(len(data))*100, 2)))

```
Github link for complete code for eda, dealing with imbalanced class and classification](https://github.com/Alyeko/crop-classfication)
