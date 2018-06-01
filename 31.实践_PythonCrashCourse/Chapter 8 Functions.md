### Capter 8 Functions

#### Alina

2018-06-01

**源代码**

```python
In [3]: def greet_user(username):
   ...:     """Display a simple greeting."""
   ...:     print("Hello, " + username.title() + "!")
   ...:
   ...: greet_user('jesse')
   ...:
Hello, Jesse!
In [5]: def favorite_book(name_book):
   ...:     """favorite book"""
   ...:     print("One of my favorite books is " + name_book)
   ...:
   ...: favorite_book(Alice in Wonderland)
   ...:
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-5-452e0647af19> in <module>()
      3     print("One of my favorite books is " + name_book)
      4
----> 5 favorite_book(Alice in Wonderland)

NameError: name 'Alice' is not defined

In [7]: favorite_book("Alice in Wonderland")
One of my favorite books is Alice in Wonderland

In [8]: def favorite_book(name_book):
   ...:     """favorite book"""
   ...:     print("One of my favorite books is " + name_book)
   ...:
   ...: favorite_book("Alice in Wonderland.")
   ...:
One of my favorite books is Alice in Wonderland.
In [8]: def favorite_book(name_book):
   ...:     """favorite book"""
   ...:     print("One of my favorite books is " + name_book)
   ...:
   ...: favorite_book("Alice in Wonderland.")
   ...:
One of my favorite books is Alice in Wonderland.
In [11]: def describe_pet(animal_type,pet_name):
    ...:     """Display information about a pet."""
    ...:     print("\nI have a " + animal_type + ".")
    ...:     print("My " + animal_type  + "'s name is " + pet_name.title() + ".
    ...: ")
    ...:

In [12]: describe_pet('hamster','harry')
    ...:

I have a hamster.
My hamster's name is Harry.
In [13]: describe_pet('dog','willie')

I have a dog.
My dog's name is Willie.

In [14]: describe_pet('harry','hamster')

I have a harry.
My harry's name is Hamster.
In [17]: def describe_pet(animal_type,pet_name):
    ...:     """Display information about a pet."""
    ...:     print("\nI have a " + animal_type + ".")
    ...:     print("My " + animal_type  + "'s name is " + pet_name.title() + ".
    ...: ")
    ...: describe_pet(animal_type='hamster',pet_name='harry')
    ...:

I have a hamster.
My hamster's name is Harry.

In [18]: describe_pet(pet_name='harry',animal_type='hamster')

I have a hamster.
My hamster's name is Harry.
In [20]: def describe_pet(pet_name,animal_type='dog'):
    ...:     """Display information about a pet."""
    ...:     print("\nI have a " + animal_type + ".")
    ...:     print("My " + animal_type  + "'s name is " + pet_name.title() + ".
    ...: ")
    ...: describe_pet(pet_name='willie')
    ...:

I have a dog.
My dog's name is Willie.
In [21]: def describe_pet(pet_name,animal_type='dog'):
    ...:     """Display information about a pet."""
    ...:     print("\nI have a " + animal_type + ".")
    ...:     print("My " + animal_type  + "'s name is " + pet_name.title() + ".
    ...: ")
    ...: describe_pet('willie')
    ...:

I have a dog.
My dog's name is Willie.
练习
8-3
                   
In [25]: def make_shirt(size,text):
    ...:     """Let's make T-Shirt"""
    ...:     print("The size is "+ size + "The text on it is " + text )
    ...:

In [26]: make_shirt('Large','I love python')
The size is LargeThe text on it is I love python
In [30]: def make_shirt(size,text):
    ...:     """Let's make T-Shirt"""
    ...:     print("The size is "+ size + " \nThe text on it is " + text )
    ...:
    ...: make_shirt('Large','"I love python"')
    ...:
The size is Large
The text on it is "I love python"
8-4
In [32]: def make_shirt(text,size='Large'):
    ...:     """Let's make T-Shirt"""
    ...:     print("The size is "+ size + " \nThe text on it is " + text )
    ...:
    ...: make_shirt('"N,Y,C"')
    ...:
The size is Large
The text on it is "N,Y,C"
8-5
In [34]: def describe_city(city_name,country_name):
    ...:     """Which country does the city in"""
    ...:     print(city_name + " is in " + country_name + ".")
    ...:
    ...: describe_city('Reykjavik','Iceland')
    ...:
Reykjavik is in Iceland.                 
```

```python
In [11]: def describe_pet(animal_type,pet_name):
    ...:     """Display information about a pet."""
    ...:     print("\nI have a " + animal_type + ".")
    ...:     print("My " + animal_type  + "'s name is " + pet_name.title() + ".
    ...: ")
    ...:
In [14]: describe_pet('harry','hamster')

I have a harry.
My harry's name is Hamster.
positional arguments中 顺序弄反 会funny
```

**问题集**

What are arguments in python?

https://stackoverflow.com/questions/14924825/what-are-arguments-in-python

