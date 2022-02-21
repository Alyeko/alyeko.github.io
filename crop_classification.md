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
#Investingating the imbalanced nature of the data
df = pd.DataFrame({'labels':['1', '2', '3', '4', '5', '6', '7'], 'value':[len(data[data['label']==n+1]) for n in range(data['label'].nunique())]})
ax = df.plot.bar(x='labels', y='value', rot=0)
plt.rcParams['figure.figsize'] =[7, 5]
plt.ylabel('Total number of occurences in dataset')

mapping = {1:'Corn', 2:'Pea', 3:'Canola', 4:'Soy', 5:'Oat', 6:'Wheat', 7:'Broadleaf'           
for j in mapping:
    print('{} has {}% rows of data out of the entire dataset.'.format(mapping[j], round(len(data[data['label']==j])/(len(data))*100, 2)))

```

```python 
#Hyperparameter tuning
param_grid = [{'max_depth':[2, 3, 5, 7, 9],
               'min_samples_split': [2, 3, 4, 5], 
               'splitter': ['best', 'random']}]

tree_clf = DecisionTreeClassifier()
grid_search = GridSearchCV(tree_clf, param_grid, cv=5, verbose=2)
grid_search.fit(X_train, y_train)
```

Github link for complete code for eda, dealing with imbalanced class and classification](https://github.com/Alyeko/crop-classfication)
