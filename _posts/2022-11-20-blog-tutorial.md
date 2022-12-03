---
layout: post
title:  "A Beginner's Guide to Data Wrangling with Pandas"
date:   2022-11-20
author: Che Wei Liu
description: After reading this guide, you will be more familiar with Pandas Basics 
image: /assets/images/Pandas.avif
---

**Have you ever wondered what is Pandas? With the rising need of data science nowadays, you definitely heard of Python; if you know Python, you definitely heard of Pandas. Not the panda who knows Kung Fu! But once you know Pandas, you will gain a superpower called data analysis which is as cool as Kung Fu. In this post, I will introduce to you some very common and useful functions of Pandas, get ready!**  
<br>
# What is Pandas?
<br>
<br>
pandas is a software library written for the Python programming language for **data manipulation and analysis**. In particular, it offers data structures and operations for manipulating numerical tables and time series. It is free software released under the three-clause BSD license. The name is derived from the term **"panel data"**, an econometrics term for data sets that include observations over multiple time periods for the same individuals. Its name is a play on the phrase "Python data analysis" itself. Wes McKinney started building what would become pandas at AQR Capital while he was a researcher there from 2007 to 2010.
<br>
<br>
# How do I call Pandas library?
<br>
It's fairly easy to call Pandas in Python. We just use `import pandas as pd`. You don't have to use "pd" as Pandas's nickname, you can choose whatever you want, it's just "pd" is commonly used by almost all Pandas users. Everyone knows "pd" represents Pandas!
<br>
<br>
# How to create a series or a dataframe in Pandas?
<br>
**Series:**<br>
`s = pd.Series([1, 2, 3, 4],  index=['a',  'b',  'c',  'd'])`<br><br>
**Dataframe:**<br>
`data = {'Country': ['Taiwan',  'Korea',  'Japan'], 'Capital': ['Taipei',  'Seoul',  'Tokyo'], 'Population': [23920776, 51375508, 125543793]}`
<br>
`df = pd.DataFrame(data,columns=['Country',  'Capital',  'Population'])`
<br>
<br>
![Test Image](https://raw.githubusercontent.com/Che-Wei-Liu/stat386-projects/main/assets/images/dataframe.jpg)
<br>
<br>
# Read and write to csv/Excel
<br>
Oftentimes we need to output our dataframe to csv file, here is how we do it:
<br>
**csv:**<br>
`pd.read_csv('file.csv', header=None, nrows=10)`<br>
`df.to_csv('mydataFrame.csv')`
<br>
<br>
**Excel:**<br>
`pd.read_excel('file.xlsx')`
`df.to_excel('dir/myDataFrame.xlsx',  sheet_name='Sheet1')`
<br>
<br>
# Selecting
<br>
**By label/position**<br>
`df[1:2]` will get you the first row of this dataframe. Likewise, `df[1:3]` will get you index 1 to index 2<br>
**Note: The index in Python starts at 0. So if you want the fifth item, the index for it is 4**
<br>
`df[1:]` will get the rest of the dataframe starting from index 1.
<br><br>
![Test Image](https://raw.githubusercontent.com/Che-Wei-Liu/stat386-projects/main/assets/images/the rest.jpg)
<br>
<br>
**Conditional Selecting**
<br>
Sometimes we need to select by some conditions. This is when >, <, ==, !=, &, | come in handy.</ul>
<br><br>
**Let's see some examples here:**
<br>
1. `df[df['Population']>120000000]`
<br><br>
![Test Image](https://raw.githubusercontent.com/Che-Wei-Liu/stat386-projects/main/assets/images/japan.jpg)
<br><br>
2. `df[(df['Population']<50000000)&(df['Capital']!='Seoul')]`
<br><br>
![Test Image](https://raw.githubusercontent.com/Che-Wei-Liu/stat386-projects/main/assets/images/taiwan.jpg)
<br><br>
3. `df[(df['Population']<120000000)|(df['Capital']=='Tokyo')]`<br>
The above code will give us all three cities since we use | (or) expression. All cities satisfy the conditions.</ul>
<br><br>
# Dropping, sort and rank
<br>
**Drop:**<br>
`df.drop('Country', axis=1)` This will help us drop the "Country" column.<br><br>
**Sort & Rank**<br>
`df.sort_index()` Sort by labels along an axis<br>
`df.sort_values(by='Country')` Sort by the values along an axis<br>
`df.rank()` Assign ranks to entries<br>
<br>
# Retrieve dataframe information<br>
**Basic information**<br>
`df.shape` Retrieve (rows, columns)<br>
`df.index` Describe index<br>
`df.columns` Describe DataFrame columns<br>
`df.info()` Info on DataFrame<br>
`df.count()` Number of non-NA values<br>
<br>
**Basic statistical information**<br>
`df.sum()` Sum of values<br>
`df.cumsum()` Cumulative sum of values<br>
`df.min()/df.max()` Minimum/maximum values<br>
`df.idxmin()/df.idxmax()` Minimum/Maximum index value<br>
`df.describe()` Summary statistic<br>
`df.mean()` Mean of values<br>
`df.median()` Median of values<br> 
<br>
# Reshaping data - change the layout of a data set
<br>
1. Transfer your data set from wide to long<br>
`pd.melt(df, id_vars=['id_var'], value_vars=['value_var'])` This is extremely helpful when you are tidying your data<br>
2. Transfer your data set from long to wide<br>
`df.pivot(columns='var', values='val')` This is extremely helpful when you are tidying your data<br>
3. Append rows of dataframes<br>
`pd.concat([df1, df2])`<br>
4. Append columns of dataframes<br>
`pd.concat([df1, df2, axis=1])`<br></ul>
<br><br>
![Test Image](https://raw.githubusercontent.com/Che-Wei-Liu/stat386-projects/main/assets/images/tables.jpg)
<br><br>
# Conclusion<br>
Pandas is a extremly powerful tool in data tidying, wrangling, and analysis. This post is not an exhaustive look at Pandas, there are a lot of different ways to achieve the same results. Some are smarter and faster than my methods. Below are a list of helpful links that will enhance your understanding and ability of utilizing this robust library. As you diligently research and apply different methods in your python script using Pandas, you will surely become a better data analyst and a Pandas expert!<br>
[W3Schools on Pandas](https://www.w3schools.com/python/pandas/default.asp)<br>
[GeeksforGeeks on Pandas](https://www.geeksforgeeks.org/introduction-to-pandas-in-python/)<br>
[Python Pandas tutorial](https://www.learndatasci.com/tutorials/python-pandas-tutorial-complete-introduction-for-beginners/)<br>
[tutorialspoint on Pandas](https://www.tutorialspoint.com/python_pandas/index.htm)<br>
[Real Python on Pandas](https://realpython.com/learning-paths/pandas-data-science/)<br>

