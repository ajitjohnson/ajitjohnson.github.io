## Python for Beginners- Your First Line of Python Code
**Author:** Ajit Johnson Nirmal <br>
**Date Created:** July 14 2020 <br>
**Website:** ajitjohnson.com

## Simple arithmetic  operations


```python
1 + 1
```




    2




```python
(10 * 500) / (3 ^ 5)
```




    833.3333333333334



## Using Variables
You will learn that numbers or strings can be assigned to variable among others which we will learn later.  
Variables can be over written.


```python
x = 1
y = 1
```


```python
x + y
```




    2




```python
x = 'Ajit'
y = 'Johnson'
```


```python
x + y
```




    'AjitJohnson'




```python
x = 1
y = 'Johnson'
```


```python
x + y
```

# Write your first function
You will learn how to intialize and run a function.  
*A function is a block of organized, reusable code that is used to perform a particular action.*  
You will also learn how to add comments to your code.


```python
def add (a,b):
    sum = a + b
    return sum
```


```python
add (a = 1, b = 1)
```




    2




```python
# BMI calculator
# Formula: weight (kg) / [height (m)]2
# 18 to 25 is normal BMI
def bmi (weight, height):
    bmi = weight / (height*height)
    return bmi
```


```python
bmi (weight = 75, height = 1.8)
```




    23.148148148148145



## A more *fun* function
You will learn how to *import* and use packages that has been written by others.  
Identify the number of days left to your birthday.



```python
# Import Module/Package
import datetime as dt
```


```python
now = dt.date.today()
```


```python
now  
```




    datetime.date(2020, 7, 15)




```python
now.year
```




    2020




```python
def daystobirthday (year, month, date):
    
    # Import Module/Package
    import datetime as dt

    # Identify the current date
    now = dt.date.today()
    
    # Set the birth date in package readable format
    birthday = dt.date(year,month,date)
    
    # Identify the number of days left to birthday
    days_left = birthday - now
    
    #days_left = print ('Your Birthday is in ' + str(days_left.days) + ' days.. Yeyyy!!!')
    
    # Return the result
    return days_left
```


```python
daystobirthday (year=2020, month=10, date=16)
```




    datetime.timedelta(days=93)



## Challenge
**Write a python program to calculate the the number of days between your birthday and christmas**
