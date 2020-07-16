---
title:  "Python for Beginners- Your First Line of Python Code"
date:   2020-07-15 11:00:00
comments: true
description: In this Tutorial, you will learn how to write your first python program.
categories: ['R', 'Python', 'Data Science']
tags: ['coding', 'educational', 'Tutorial', 'Data Science', 'Jupyter Notebooks']
header-img: "/assets/images/learn python R data science.png"
---

Hey guys, welcome back to another tutorial on **data-analysis and programming with Python and R**. I hope you are already setup with *Jupyter Notebook* to run your first python program. If not, you can checkout my [previous article](https://ajitjohnson.com/setup-jupyter-notebook-python-R/) on how to set up a *jupyter notebook* for Python.

> **Download the Jupyter Notebook for this [tutorial here](https://github.com/ajitjohnson/ajitjohnson.github.io/blob/master/assets/data/2020-07-15-python-for-beginners-first-program/2020-07-15-python-for-beginners-first-program.ipynb.zip)**

<a href="https://github.com/ajitjohnson/ajitjohnson.github.io/blob/master/assets/data/2020-07-15-python-for-beginners-first-program/2020-07-15-python-for-beginners-first-program.ipynb.zip" download="2020-07-15-python-for-beginners-first-program.ipynb.zip">download this</a>

## Let's Get Started
### Simple arithmetic  operations

You can treat python like a simple calculator. Type `1 + 1` and see what happens.

```python
1 + 1
```




    2

## Using Variables

Variables are are nothing but containers for storing data values. As you can see below, we are storing a value of 1 into a variable `x` and `y`. We can then perform arithmetic operations as before.


```python
x = 1
y = 1
x + y
```




    2


We can store much more than numbers into variables, here we are storing two pieces of text into `x` and `y`. Keep in mind that if you use the same variable names, the previous values will be overwritten with the new values.

We can store a variety of other datatypes such as dataframes, arrays, dictionary and so on. We will cover that in future tutorials.

Any way similar to what we did previously, run `x + y` to see what happens.

```python
x = 'Ajit'
y = 'Johnson'
x + y
```




    'AjitJohnson'

Since python recognized that both the variables contain just text, it literally stitched them together.

**What happens if you add an integer and a text togeather?. Do you think python will throw an error? Run it in your jupyter notebook and find out.**


```python
x = 1
y = 'Johnson'
x + y
```

# Write your first function

In Python, a function is a bunch of code that performs a specific task.

**A Function needs to be written with a specific structure**
1. Keyword `def` that marks the start of the function header.
2. A function name to uniquely identify the function.
3. Parameters (arguments) through which we pass values to a function. They are optional.
4. A colon (:) to mark the end of the function header.
5. One or more valid python statements that make up the function body. Statements must have the same indentation level (4 spaces).
6. An optional `return` statement to return a value from the function.
<br>

```python
def add (a,b):
    sum = a + b
    return sum
```

As you can see in the above example, we have used all 6 syntax to build a function. We begin the function with a `def` and gave a name to the function- `add`. We then defined two `Parameters` for the function `a` and `b` that the function will accept from the user who uses it. We then define some computation within the function (`a + b`) and finally, `return` the calculated value.  

Once you have defined the function, it is very easy to use. To call a function we simply type the function name with appropriate parameters as shown below.


```python
add (a = 1, b = 1)
```




    2


Below is another example, where we write a function to calculate the Body Mass Index (BMI).  

Btw, if you notice that we have some additional text in the code block below that are preceded by a pound symbol (`#`). This is called commenting in python. Commenting is generally used to add human readable details within the code that might help in readability of the code or other information that you would like to share. Anything that is followed by a `#` sign is not executed by python.  

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



## Let's write a more *fun* function
Birthday's are fun right? Let's write a function to identify the number of days left for your birthday. Unlike the previous two functions, you will notice that there is an extra line that says with `import datetime` below. These are called packages or modules.

> A module is a piece of software that has a specific functionality and are imported using the `import` command.

There are 100,000+ modules available for python. These are written by python users such as you and me and have decided to make it available to the community. The cool thing about these packages is that you can simply import them and use them without having to re-write the code.

For example, remember we wrote the `add` function to sum two numbers above? There is a package called `numpy` that has a function called `sum` which does the exact same thing in a much more elegant manner, so in a way we could have simply imported that package and used it instead of writing our own.  

Anyway let's get into our days to birthday calculator. First let's import the `datetime` package.

You can simply import it as `import datetime`, however you might have noticed that I performed the import by using `import datetime as dt`. The `as` command is optional and is just a matter of convenience. In python, anytime you want to use a function from a package, you will need to be explicit. For example, if you would like to use the `date` function from the `datetime` module, you code it as `datetime.date()`. However, if you are lazy like me and would like to keep it short, you can use the `as` command during import and then re-write the above command as `dt.date()`.

You might also wonder how I figured out that there is a function called `date` in the `datetime` module? Most packages come with documentation and you will just need to go through them. The documentation of the `datetime` package is [here](https://docs.python.org/2/library/datetime.html)

```python
# Import Module/Package
import datetime as dt
```
Now, lets find today's date. As you can see below, we do that by calling the `date.today()` function within the  `datetime` package.

```python
now = dt.date.today()
now
```




    datetime.date(2020, 7, 15)


We can save today's date into a variable called `now` and extract individual components such as `date`, `month` or `year` as shown below.

```python
now.year
```




    2020


**Awesome, now that we are clear about how to import a package let's use it to write our days to birthday calculator.**  

- Step 1: define the function `daystobirthday` that aceepts your birthday. The `year` parameter is however not the year of your birthday but rather the current/next year.
- Step 2: Import the `datetime` package
- Step 3: Identify today's date
- Step 4: Set the next birthday date based on the input parameters.
- Step 5: Subtract the birthday date from today's date to calculate the number of days left to birthday.
- Step 6: Return the result.
<br>
You would have noticed that we did not have to pass in any information about the number of days in any given month and so on. This is the power of using the `datetime` package. It already knows. If we had not used it, you would need to write all those computations yourself.

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

Run the function as below and see how many day's are left for your birthday. In this case it is 93 days.


```python
daystobirthday (year=2020, month=10, date=16)
```




    datetime.timedelta(days=93)


Of course we can modify this function to be more intelligent. For example, one can write the function such that the user does not need to pass in the `year` parameter, but, rather infer it from the month passed and the current month- i.e. if the current month is before than the birthday month then the year would be the same year (i,e 2020), else it will be the next year (2021).

However, in order to implement that, you will need to learn how to write an `if else` statement. We will learn that in the next tutorial.

Finally, below is a challenge for you. **I cannot stress how important this is.** The only way to learn to code is to  practice continuously. Go ahead and [download](https://github.com/ajitjohnson/ajitjohnson.github.io/blob/master/assets/data/2020-07-15-python-for-beginners-first-program/2020-07-15-python-for-beginners-first-program.ipynb) this notebook, execute the previous commands and complete the challenge below. If you get stuck at any point, drop me a comment below or if you successfully completed the task, let me know that in the comments as well.

# The Challenge
> **Write a python program to calculate the the number of days between your birthday and Christmas.**

#### Well, that's pretty much it
Hope you enjoyed the this article on the **Data analysis and Programming Series**. If you would like me to drop you an email on the next post, leave your email below.

<!-- Begin Mailchimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/horizontal-slim-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; width:100%;}
	/* Add your own Mailchimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="https://ajitjohnson.us10.list-manage.com/subscribe/post?u=1ea7a1f023e20dd49bb557f0b&amp;id=e2a3044de8" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">New Post Alert !</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_1ea7a1f023e20dd49bb557f0b_e2a3044de8" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->


<br>
Bye for now! Have a nice day 😊
