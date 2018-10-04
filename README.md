
# Python Object Initialization

## Introduction
Now that we've begun to see OOP and class structures, we're going to investigate the __init__ method more. The __init__ method allows classes to have default behaviors and attributes.

## Objectives
* Define custom __init__ methods for object initialization
* Create instance variables in the __init__ method
* Use default arguments in the __init__ method

## Introducing __init__

By using the `__init__` method, we can initialize instances of objects with defined attributes. Without this, attributes are not defined until other methods are called that would populate these fields. trying to call an attribute of a class will produce an error. For example, imagine a person class with methods to set_name and set_job:


```python
class Person:
    def set_name(self, name):
        self.name = name
    def set_job(self, job):
        self.job = job
```


```python
bob = Person()
```

If we try to access an attribute before setting it we'll get an error.


```python
bob.name
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-12-6a5ddef64c8c> in <module>()
    ----> 1 bob.name
    

    AttributeError: 'Person' object has no attribute 'name'



```python
bob.set_name('Bob')
```


```python
bob.name
```




    'Bob'



Using the __init__ method allows us to set attributes on instantiation.


```python
class Person:
    def __init__(self, name, job):
        self.name = name
        self.job = job
```


```python
bob = Person('Bob', 'Carpenter')
print(bob.name)
print(bob.job)
```

    Bob
    Carpenter


Written like this, these arguments then become required:


```python
someone = Person()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-20-42fc89f0c051> in <module>()
    ----> 1 someone = Person()
    

    TypeError: __init__() missing 2 required positional arguments: 'name' and 'job'


# Setting default arguments in the __init__ method
To circumvent this, we can also define __init__ to have default arguments. This allows parameters to be specified if desired but are not required.


```python
class Person:
    def __init__(self, name=None, job=None):
        self.name = name
        self.job = job
```


```python
someone = Person()
print(someone.name)
print(someone.job)

print('\n')
governer = Person(job = 'Carpenter')
print(governer.name)
print(governer.job)

print('\n')
bob = Person('Bob', 'Carpenter')
print(bob.name)
print(bob.job)
```

    None
    None
    
    
    None
    Carpenter
    
    
    Bob
    Carpenter


## Summary
In this lesson you got a brief introduction to the __init__ method and how you can use it to set attributes when objects are initialized, including default parameters.


```python

```
