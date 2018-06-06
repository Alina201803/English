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

2018-06-2

**源代码**

```python
def get_formatted_name(first_name,last_name):
    """Return a full name, neatly formatted."""
    full_name = first_name + ' ' + last_name
    return full_name.title()

musician = get_formatted_name('jimi','hendrix')
print(musician)


def get_formatted_name(first_name,middle_name,last_name):
    """Return a full name, neatly formatted."""
    full_name = first_name + ' '+middle_name + ' ' + last_name
    return full_name.title()

musician = get_formatted_name('jimi', 'lee','hendrix')
print(musician)

def get_formatted_name(first_name,last_name,middle_name=''):
    """Return a full name,neatly formatted."""
    if middle_name:
        full_name = first_name + ' ' + middle_name + ' ' + last_name
    else:
        full_name = first_name + ' ' + last_name
    return full_name.title()

musician = get_formatted_name('jimi','hendrix')
print(musician)

musician = get_formatted_name('join','hooker','lee')
print(musician)

def build_person(first_name,last_name):
    """Return a dictionary of information about a person."""
    person = {'first': first_name,'last': last_name}
    return person

musician = build_person('jimi','hendrix')
print(musician)


def build_person(first_name,last_name,age=''):
    """Return a dictionary of information about a person."""
    person = {'first':first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person

musician = build_person('jimi','hendrix',age=27)
print(musician)


def get_formatted_name(first_name,last_name):
    """Return a full name,neatly formatted."""
    full_name = first_name + ' ' + last_name
    return full_name.title()

while True:
    print("\nPlease tell me your name:")
    f_name = input("First_name: ")
    l_name = input("Last_name: ")

    formatted_name = get_formatted_name(f_name,l_name)
    print("\nHello, " + formatted_name + "!")

def get_formatted_name(first_name,last_name):
    """Return a full name,neatly formatted."""
    full_name = first_name + ' ' + last_name
    return full_name.title()

while True:
    print("\nPlease tell me your name:")
    print("(enter 'q' at any time to quit)")

    f_name = input("First name: ")
    if f_name == 'q':
        break

    l_name = input("Last name: ")
    if l_name == 'q':
        break
    
    formatted_name = get_formatted_name(f_name,l_name)
    print("\nHello, " + formatted_name + "!")
    
练习：
def city_country(city,country):
    """Return a city and its country"""
    city_country_pair = city + ',' + country
    return city_country_pair.title()

describe_city = city_country('Guangzhou','china')
print(describe_city)

def city_country(city,country):  
    return city+','+country  
print(city_country("Guangzhou","China"))  
print(city_country("Lodon","UK"))  
print(city_country("New York","USA")) 

```

**错题集**

```python
def city_country(city,country):
    return city + ',' + country
    print(city_country('Guangzhou','china'))
改为：
def city_country(city,country):
    return city + ',' + country
print(city_country('Guangzhou','china'))
```

今日所学：returning a simple value, making an argument optinal, returning a dictinary, while a function with a while loop

2018-06-03

```python
In [1]: unprinted_designs = ['iphone case','robot pendant','dodecahedron']
   ...: completed_models = []
   ...: while umprinted_desgins:
   ...:     current_desgin = unprinted_design.pop()
   ...:     print("Printing model: " + current_desgin)
   ...:
   ...: print("\nThe following models have been printed:")
   ...: for completed_model in completed models:
   ...:     print(completed_model)
   ...:
  File "<ipython-input-1-d6a4fd6b6702>", line 8
    for completed_model in completed models:
                                          ^
SyntaxError: invalid syntax
In [8]: unprinted_designs = ['iphone case','robot pendant','dodecahedron']
   ...: completed_models = []
   ...: while unprinted_designs:
   ...:     current_design = unprinted_designs.pop()
   ...:     print("Printing model: " + current_design)
   ...:
   ...: print("\nThe following models have been printed:")
   ...: for completed_model in completed_models:
   ...:     print(completed_model)
   ...:
Printing model: dodecahedron
Printing model: robot pendant
Printing model: iphone case

The following models have been printed:
In [9]: unprinted_designs = ['iphone case','robot pendant','dodecahedron']
   ...: completed_models = []
   ...: while unprinted_designs:
   ...:     current_design = unprinted_designs.pop()
   ...:     print("Printing model: " + current_design)
   ...:     completed_models.append(current_design)
   ...:
   ...: print("\nThe following models have been printed:")
   ...: for completed_model in completed_models:
   ...:     print(completed_model)
   ...:
   ...:
Printing model: dodecahedron
Printing model: robot pendant
Printing model: iphone case

The following models have been printed:
dodecahedron
robot pendant
iphone case
In [10]: def printed_models(unprinted_designs,completed_models):
    ...:     while unprinted_designs:
    ...:     current_design = unprinted_designs.pop()
    ...:     print("Printing model: " + current_design)
    ...:     completed_models.append(current_design)
    ...:
    ...: def show_completed_models(completed_models):
    ...:     print("\nThe following models have been printed:")
    ...:     for completed_model in completed_models:
    ...:         print(completed_model)
    ...:
  File "<ipython-input-10-cdcf86fc5150>", line 3
    current_design = unprinted_designs.pop()
                 ^
IndentationError: expected an indented block
In [13]: def print_models(unprinted_designs,completed_models):
    ...:     while unprinted_designs:
    ...:         current_design = unprinted_designs.pop()
    ...:         print("Printing model: " + current_design)
    ...:         completed_models.append(current_design)
    ...:
    ...: def show_completed_models(completed_models):
    ...:     print("\nThe following models have been printed:")
    ...:     for completed_model in completed_models:
    ...:         print(completed_model)
    ...:
    ...: unprinted_designs = ['iphone case','robot pendant','dodecahedron']
    ...: completed_models = []
    ...:

In [14]: print_models(unprinted_designs,completed_models)
    ...: show_completed_models(completed_models)
    ...:
Printing model: dodecahedron
Printing model: robot pendant
Printing model: iphone case

The following models have been printed:
dodecahedron
robot pendant
iphone case
练习：
8-9
In [18]: def show_magicians(names):
    ...:     for name in magician_names:
    ...:         print(name)
    ...:
    ...: magician_names = ['amanda','finoa','maria']
    ...: show_magicians(magician_names)
    ...:
amanda
finoa
maria
In [21]: def make_great(names):
    ...:     """add phrase the Great to each magician"""
    ...:     for number in range(len(magician_names)):
    ...:         magician_names[number] = "The Great" + magician_names[number].
    ...: title()
    ...:
    ...: def show_magicians(names):
    ...:     for name in magician_names:
    ...:         print(name)
    ...:
    ...: magician_names = ['amanda','finoa','maria']
    ...: make_great(magician_names)
    ...: show_magicians(magician_names)
    ...:
The GreatAmanda
The GreatFinoa
The GreatMaria
In [22]: def make_great(names):
    ...:     """add phrase the Great to each magician"""
    ...:     for number in range(len(magician_names)):
    ...:         magician_names[number] = "The Great " + magician_names[number]
    ...: .title()
    ...:
    ...: def show_magicians(names):
    ...:     for name in magician_names:
    ...:         print(name)
    ...:

In [23]: magician_names = ['amanda','finoa','maria']
    ...: make_great(magician_names)
    ...: show_magicians(magician_names)
    ...:
The Great Amanda
The Great Finoa
The Great Maria
In [27]: def make_great(names):
    ...:     """add phrase the Great to each magician"""
    ...:     for number in range(len(magician_names)):
    ...:         magician_names[number] = "The Great " + magician_names[number]
    ...:
    ...:     return magician_names
    ...: def show_magicians(names):
    ...:     for name in magician_names:
    ...:         print(name)
    ...:
    ...: magician_names = ['amanda','finoa','maria']
    ...: new_magician_names = make_great(magician_names[:])
    ...: show_magicians(magician_names)
    ...: show_magicians(new_magician_names)
    ...:
The Great amanda
The Great finoa
The Great maria
The Great amanda
The Great finoa
The Great maria
In [29]: def show_magicians(magicians):
    ...:     for magician in magicians:
    ...:         print(magician)
    ...:
    ...:
    ...: def make_great(magicians):
    ...:     for num in range(len(magicians)):
    ...:         magicians[num] = 'the Great ' + magicians[num]
    ...:     return magicians
    ...:
    ...:
    ...: magicians = ['Criss Angel', 'David Copperfield', 'Jason Latimer']
    ...: new_magicians = make_great(magicians[:])
    ...: show_magicians(magicians)
    ...: show_magicians(new_magicians)
    ...:
Criss Angel
David Copperfield
Jason Latimer
the Great Criss Angel
the Great David Copperfield
the Great Jason Latimer
```

今日所学：passing a list, modifying a list in a function,preventing a function from modifying a list 

2018-06-04

**源代码**

```python
In [1]: def make_pizza(*toppings):
   ...:     """Summarize the pizza we are about to make"""
   ...:     print("\nMaking a pizza with the following toppings:")
   ...:     for topping in toppings:
   ...:         print("- " + topping)
   ...:
   ...: make_pizza('pepperoni')
   ...: make_pizza('mushrooms','green peppers','extra cheese')
   ...:

Making a pizza with the following toppings:
- pepperoni

Making a pizza with the following toppings:
- mushrooms
- green peppers
- extra cheese

In [2]: def make_pizza(size,*toppings):
   ...:     """Summarize the pizza we are about to make."""
   ...:     print("\nMaking a " + str(size) +
   ...:           "-inch pizza with the following toppings:")
   ...:     for topping in toppings:
   ...:         print("- " + topping)
   ...:

In [3]: make_pizza(16,'pepprtoni')
   ...: make_pizza(12,'mushrooms','green peppers','extra cheese')
   ...:

Making a 16-inch pizza with the following toppings:
- pepprtoni

Making a 12-inch pizza with the following toppings:
- mushrooms
- green peppers
- extra cheese
In [4]: def build_profile(first,last,**user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in uesr_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:
   ...: user_profile = build_profile('albert','einstein',
   ...:                              location='princeton',
   ...:                              field='physics')
   ...: print(user_profile)
   ...:
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-4-bb38fb692cd5> in <module>()
     10 user_profile = build_profile('albert','einstein',
     11                              location='princeton',
---> 12                              field='physics')
     13 print(user_profile)

<ipython-input-4-bb38fb692cd5> in build_profile(first, last, **user_info)
      4     profile['first_name'] = first
      5     profile['last_name'] = last
----> 6     for key,value in uesr_info.items():
      7         profile[key] = value
      8     return profile

NameError: name 'uesr_info' is not defined

In [5]: def build_profile(first,last,**user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in user_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:
   ...: user_profile = build_profile('albert','einstein',
   ...:                              location='princeton',
   ...:                              field='physics')
   ...: print(user_profile)
   ...:
{'first_name': 'albert', 'field': 'physics', 'location': 'princeton', 'last_name
': 'einstein'}
In [6]: def build_profile(first,last,**user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in user_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:
   ...: user_profile = build_profile('albert','einstein',
   ...:                              location='princeton',
   ...:                              field='physics')
   ...: print(user_profile)
   ...:
{'first_name': 'albert', 'field': 'physics', 'location': 'princeton', 'last_name
': 'einstein'}
In [6]: def build_profile(first,last,**user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in user_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:
   ...: user_profile = build_profile('albert','einstein',
   ...:                              location='princeton',
   ...:                              field='physics')
   ...: print(user_profile)
   ...:
{'first_name': 'albert', 'field': 'physics', 'location': 'princeton', 'last_name
': 'einstein'}
In [7]: def build_profile(first,last,**user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in user_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:

In [8]: user_profile = build_profile('albert','einstein',
   ...:                             location='princeton',
   ...:                             field='physics')
   ...: print(user_profile)
   ...:
{'first_name': 'albert', 'field': 'physics', 'location': 'princeton', 'last_name
': 'einstein'}

In [9]: def build_profile(first, last, **user_info):
   ...:     """Build a dictionary containing everything we know abou a user."""
   ...:
   ...:     profile = {}
   ...:     profile['first_name'] = first
   ...:     profile['last_name'] = last
   ...:     for key,value in user_info.items():
   ...:         profile[key] = value
   ...:     return profile
   ...:
   ...: user_profile = build_profile('albert','einstein',
   ...:                             location='princeton',
   ...:                             field='physics')
   ...: print(user_profile)
   ...:
{'first_name': 'albert', 'field': 'physics', 'location': 'princeton', 'last_name
': 'einstein'}
练习
 8-12
In [10]: def make_sandwich(*fillings):
    ...:     """summarize the sandwich being ordered"""
    ...:     print("\nThe sandwich is being ordered:")
    ...:     for filling in fillings:
    ...:         print(filling)
    ...:
    ...: make_sandwich('Reuben','Tuna',)
    ...: make_sandwich('Meat')
    ...: make_sandwich('Po-boy')
    ...:

The sandwich is being ordered:
Reuben
Tuna

The sandwich is being ordered:
Meat

The sandwich is being ordered:
Po-boy
8-13
In [11]: def build_profile(first, last, **user_info):
    ...:     """Build a dictionary containing everything we know abou a user.""
    ...: "
    ...:     profile = {}
    ...:     profile['first_name'] = first
    ...:     profile['last_name'] = last
    ...:     for key,value in user_info.items():
    ...:         profile[key] = value
    ...:     return profile
    ...:
    ...: user_profile = build_profile('albert','einstein',
    ...:                             "location'='princeton',
    ...:                             'field'='physics')
    ...: print(user_profile)
    ...:
  File "<ipython-input-11-40e4196c0ba4>", line 11
    "location'='princeton',
                           ^
SyntaxError: EOL while scanning string literal
In [12]: def build_profile(first, last, **user_info):
    ...:     """Build a dictionary containing everything we know abou a user.""
    ...: "
    ...:     profile = {}
    ...:     profile['first_name'] = first
    ...:     profile['last_name'] = last
    ...:     for key,value in user_info.items():
    ...:         profile[key] = value
    ...:     return profile
    ...:
    ...: user_profile = build_profile('Qiuru','Shen',location='Harbin',field='R
    ...: ussian')
    ...:
    ...: print(user_profile)
    ...:
{'first_name': 'Qiuru', 'field': 'Russian', 'location': 'Harbin', 'last_name': '
Shen'}
8-14
In [15]: def make_car(manufacturer,model_name,**info):
    ...:     car = {}
    ...:     car['manufacturer'] = manufacturer
    ...:     car['modle_name']=model_name
    ...:     for key,value in info.items():
    ...:         car[key]=value
    ...:     return car
    ...:
    ...: user_car = make_car('subaru','outback',color='blue',tow_package = Tru
    ...: )
    ...: print(user_car)
    ...:
{'color': 'blue', 'manufacturer': 'subaru', 'modle_name': 'outback', 'tow_pack
e': True}
 8-7
In [19]: def                                         make_album(artist_name,album_title,number=''):
    ...:     describe_album = {'name':artist_name,'title':album_title,}
    ...:     if 'number':
    ...:         describe_album['number']=number
    ...:     return describe_album
    ...:

In [20]: album_ = make_album("Yu Wenwen","Timian",1)
    ...: print(album_)
    ...: album_ = make_album("Jay Chou","Jay")
    ...: print(album_)
    ...: album_ = make_album("Eason Chan","C'mon in~",10)
    ...: print(album_)
    ...:
{'title': 'Timian', 'number': 1, 'name': 'Yu Wenwen'}
{'title': 'Jay', 'number': '', 'name': 'Jay Chou'}
{'title': "C'mon in~", 'number': 10, 'name': 'Eason Chan'}


```

今日所学：

passing an arbitrary number of arguments, 

mixing positional and arbitrary arguments, 

using arbitrary keyword arguments

2018-06-05

**源代码**

```python
import pizza

pizza.make_pizza(16,'pepperoni')
pizza.make_pizza(12,'mushrooms','green peppers','extra cheese')

from pizza import make_pizza

make_pizza(16,'pepperoni')
make_pizza(12,'mushrooms','green peppers','extra cheese')

from pizza import make_pizza as mp

mp(16,'pepperoni')
mp(12,'mushrooms','green peppers','extra cheese')


import pizza as p

p.make_pizza(16,'pepperoni')
p.make_pizza(12,'mushrooms','green peppers','extra cheese')

练习
8-15
import printing_functions

unprinted_designs = ['iphone case','robot pendant','dodecahedron']
completed_models = []
printing_functions.print_models(unprinted_designs,completed_models)
8-16
from printing_functions import print_models

unprinted_designs = ['iphone case','robot pendant','dodecahedron']
completed_models = []
print_models(unprinted_designs,completed_models)

from printing_functions import print_models as pm

unprinted_designs = ['iphone case','robot pendant','dodecahedron']
completed_models = []
pm(unprinted_designs,completed_models)

import printing_functions as pf

unprinted_designs = ['iphone case','robot pendant','dodecahedron']
completed_models = []
pf.print_models(unprinted_designs,completed_models)

from printing_functions import *

unprinted_designs = ['iphone case','robot pendant','dodecahedron']
completed_models = []
print_models(unprinted_designs,completed_models)


```

**错题集**

```python
parameter = 'default value'

parameter='default value' no spaces should be used on either side of the equal sign.
```



今日所学 

今天内容不多，明天开始chapter 9 classes

storing your functions in modules

import specific functions 

using as to give a function an alias

importing all functions in a module

