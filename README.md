# python-deco
## Problem: Learn how to use Flask and Python decorators
## Solutions
1. Functions can have inputs/functionality/output
```
def add(n1, n2):
    return n1 + n2

def subtract(n1, n2):
    return n1 - n2

def multiply(n1, n2):
    return n1 * n2

def divide(n1, n2):
    return n1 / n2
```

2. Functions are first-class objects, can be passed around as arguments e.g. int/string/float etc.
```
def calculate(calc_function, n1, n2):
    return calc_function(n1, n2)

result = calculate(add, 2, 3)
print(result)
```

3. Functions can be nested in other functions
```
def outer_function():
    print("I'm outer")

    def nested_function():
        print("I'm inner")

    nested_function()

outer_function()
```

4. Functions can be returned from other functions
```
def outer_function():
    print("I'm outer")

    def nested_function():
        print("I'm inner")

    return nested_function

inner_function = outer_function()
inner_function
```


5. Simple Python Decorator Functions
```
import time

def delay_decorator(function):
    def wrapper_function():
        time.sleep(2)
        #Do something before
        function()
        function()
        #Do something after
    return wrapper_function

@delay_decorator
def say_hello():
    print("Hello")
```
5a. With the @ syntactic sugar
```
@delay_decorator
def say_bye():
    print("Bye")

say_bye()
```

5b. Without the @ syntactic sugar
```
def say_greeting():
    print("How are you?")

decorated_function = delay_decorator(say_hello)
decorated_function()
```
## Lessons
1. More to study here: [Primer on Python Decorators](https://realpython.com/primer-on-python-decorators/)
2. Python decorators allow coders to use functions more efficiently by not calling them when they need it each time.
