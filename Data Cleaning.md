Data Cleaning with Python & R
==================

Brought to you by [Lesley Cordero](http://www.columbia.edu/~lc2958) and [ADI](https://adicu.com)

## Table of Contents

- [0.0 Setup](#00-setup)
	+ [0.1 Python & Pip](#01-python--pip)
	+ [0.2 R & R Studio](#02-r--r-studio)
	+ [0.3 Other](#03-other)
- [1.0 Background](#10-background)
- [5.0 Resources](#50-resources)


## 0.0 Setup

This guide was written in Python 3.5 and R 3.2.3.

### 0.1 Python & Pip

Download [Python](https://www.python.org/downloads/) and [Pip](https://pip.pypa.io/en/stable/installing/).

### 0.2 R & R Studio

Install [R](https://www.r-project.org/) and [R Studio](https://www.rstudio.com/products/rstudio/download/).

### 0.3 Virtual Environment

If you'd like to work in a virtual environment, you can set it up as follows: 
```
pip3 install virtualenv
virtualenv your_env
```
And then launch it with: 
```
source your_env/bin/activate
```

To execute the visualizations in matplotlib, do the following:

```
cd ~/.matplotlib
vim matplotlibrc
```
And then, write `backend: TkAgg` in the file. Now you should be set up with your virtual environment!

Cool, now we're ready to start! 

## 1.0 Introduction


## 2.0 Data Manipulation

One of the most important skills of a data scientist is manipulating data. It’s more of a general approach than a specific technique, so we’ll just work through a handful of examples to give you the flavor of it.

## Strings

The `upper()` and `lower()` string methods return a new string where all the letters in the original string have been converted to uppercase or lower-case, respectively. Nonletter characters in the string remain unchanged. 

### Lower and Upper

``` python
spam = 'Hello World!'
spam = spam.upper()
```

And that returns:
```
'HELLO WORLD!'
```

Likewise:

``` python
spam = spam.lower()
```

And that returns:
```
'hello world!'
```

These methods don't change the string itself but return new strings. If you want to change the original string, you have to call `upper()` or `lower()` on the string and then assign the new string to the variable where the original was stored. This is why you must use `spam = spam.upper()` to change the string in spam instead of simply `spam.upper()`. 

The `upper()` and `lower()` methods are helpful if you need to make a case-insensitive comparison. The strings 'great' and 'GREat' are not equal to each other. But in the many instances, it does not matter whether the user types Great, GREAT, or grEAT because the string is first converted to lowercase.

### StartsWith and EndsWith

The `startswith()` and `endswith()` methods return `True` if the string value they are called on begins or ends (respectively) with the string passed to the method; otherwise, they return False. 

``` python
'Hello world!'.startswith('Hello')
```
returns `True`, as expected.

``` python
'Hello world!'.endswith('world')
```
also returns `True`, as expected.

Now, here's an example where we return a `false`:
``` python
'abc123'.startswith('abcdef')
```

These methods are useful alternatives to the == equals operator if you need to check only whether the first or last part of the string, rather than the whole thing, is equal to another string.

### Join and Split

The `join()` method is useful when you have a list of strings that need to be joined together into a single string value. The `join()` method is called on a string, gets passed a list of strings, and returns a string. The returned string is the concatenation of each string in the passed-in list. 

``` python
', '.join(['python', 'R', 'Java'])
```

This returns:
```
'python, R, Java'
```

Oppositely, you can split a sentence into its word components. In natural language processing, this is called <b>word tokenization</b>. 

``` python
'My name is Lesley'.split()
```
And you get:
```
['My', 'name', 'is', 'Lesley']
```


## Data Munging 

Data Munging is the process of fixing particular issues with the data, such as missing values in some variables, which can overcome by estimating those values wisely depending on the amount of missing values and the expected importance of variables.

It also includes outliers on either end. Though they might make intuitive sense, they should be treated appropriately. This is outlier detection.

### Missing Values

Let us look at missing values in all the variables because most of the models don’t work with missing data and even if they do, imputing them helps more often than not. So, let us check the number of nulls / NaNs in the dataset

``` python
df.apply(lambda x: sum(x.isnull()),axis=0) 
```

Remember that missing values may not always be NaNs.

### Outlier Detection

#### Chebyshev Theorem 

The Chebyshev Theorem provides a powerful algorithm to detect outliers and is fairly simple to implement. It's based on the distance of z-scores from k standard deviation.



## 5.0 Final Words

### 5.1 Resources

