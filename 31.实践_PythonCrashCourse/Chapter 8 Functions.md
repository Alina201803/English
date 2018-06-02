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