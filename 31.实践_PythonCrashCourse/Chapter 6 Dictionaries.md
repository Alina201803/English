### chapter 6 Dictionaries

#### Alina

2018-05-25

**源代码**

```python
dictionary
In [3]: alien_0 = {'color': 'green','points': 5}

In [4]: alien_0 = {'color': 'green','points': 5}
   ...:
   ...: print(alien_0['color'])
   ...: print(alien_0['points'])
   ...:
green
5
2.assessing values in dictionary
In [5]: alien_0 = {'color': 'green'}

In [6]: print(alien_0['color'])
green

In [7]: alien_0 = {'color': 'green','points': 5}
   ...:

In [8]: new_points = alien_0['points']

In [9]: print("You just earned " + str(new_points) + " points!")
You just earned 5 points!
3.adding new key_value pairs 
In [10]: alien_0 = {'color': 'green','points': 5}
    ...: print(alien_0)
    ...:
{'color': 'green', 'points': 5}

In [11]: alien_0['x_position'] = 0
    ...: alien_0['y_position'] = 25
    ...: print(alien_0)
    ...:
{'x_position': 0, 'y_position': 25, 'color': 'green', 'points': 5}
4.starting with an empty dictionary
In [12]: alien_0 = {}
    ...:
    ...: alien_0['color'] = 'green'
    ...: alien_0['points'] = 5
    ...:

In [13]: print(alien_0)
{'color': 'green', 'points': 5}
5.modifying values in a dictionary
In [14]: alien_0 = {'color':'green'}
    ...: print('The alien is ' + alien_0['color'] + ".")
    ...:
The alien is green.
In [15]: alien_0['color'] = 'yellow'
    ...: print("The alien is now " + alien_0['color'] + ".")
    ...:
The alien is now yellow.

In [16]: alien_0 = {'x_position': 0, 'y_position': 25, 'speed': 'medium'}
    ...: print('Original x_position: ' + str(alien_0['x_position']))
    ...:
Original x_position: 0

In [17]: #Move the alien to the right.
    ...: #determine how far to move the alien based on its current speed.
    ...: if alien_0['speed'] == 'slow':
    ...:     x_increment = 1
    ...: elif alien_0['speed'] == 'medium':
    ...:     x_increment = 2
    ...: else:
    ...:     #This must be a fast alien
    ...:     x_increment = 3
    ...:
    ...: #The new position is the old position plus the increment.
    ...: alien_0['x_position'] = alien_0['x_position'] + x_increment
    ...:

In [18]: print("New x_position: " + str(alien_0['x_position']))
    ...:
    ...:
New x_position: 2
6.removing key-value pairs
In [19]: alien_0 = {'color': 'green', 'points': 5}
    ...: print(alien_0)
    ...:
{'color': 'green', 'points': 5}

In [20]: del alien_0['points']
    ...: print(alien_0)
    ...:
{'color': 'green'}
7.a dictionary of similar objects
In [27]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: print("Sarah's favorite language is " +
    ...:     favorite_languages['sarah'].title() +
    ...:     ".")
    ...:
Sarah's favorite language is C.

练习1
In [29]: person = {'first_name':'david','last_name':'copper','age':24,'city':'B
    ...: eijing'}
    ...: print(person['first_name'].title())
    ...: print(person['last_name'].title())
    ...: print(person['age'])
    ...: print(person['city'])
    ...:
David
Copper
24
Beijing
练习2
In [31]: favorite_numbers = {'amy': 8 ,'kate': 6 ,'david': 3 ,'sarah': 9 , 'vivi
an': 10 ,}
    ...: print("Amy's favorite number is " + str(favorite_numbers['amy']) + '.')

    ...: print("Kate's favorite number is " + str(favorite_numbers['kate']) + '.
')
    ...: print("David's favorite number is " + str(favorite_numbers['david']) +
'.')
    ...: print("Sarah's favorite number is " + str(favorite_numbers['sarah']) +
'.')
    ...: print("Vivian's favorite number is " + str(favorite_numbers['vivian'])
+ '.')
    ...:
Amy's favorite number is 8.
Kate's favorite number is 6.
David's favorite number is 3.
Sarah's favorite number is 9.
Vivian's favorite number is 10.
练习3
In [32]: glossy = {
   ...:     'fuction': 'A series of statements which returns some value to a ca
   ...: ller.',
   ...:     'list': 'A built-in Python sequence.',
   ...:     'statement':'A statement is part of a suite',
   ...:     'slice':'An object usually containing a portion of a sequence.',
   ...:     }
In [33]: print("fuction:\n " + glossy['fuction'])
   ...: print("list:\n "+ glossy['list'])
   ...: print("statement:\n " + glossy['statement'])
   ...: print("slice:\n "  + glossy['slice'])
   ...:
fuction:
 A series of statements which returns some value to a caller.
list:
 A built-in Python sequence.
statement:
 A statement is part of a suite
slice:
 An object usually containing a portion of a sequence.

```

**错题集**

```python
   ...: print('fuction'+ ' :' + \nglossy['fuction'])
   ...: print('list'+ ' :' + \nglossy['list'])
   ...: print('statement'+ ' :' + \nglossy['statement'])
   ...: print('slice'+ ' :' + \nglossy['slice'])
  File "<ipython-input-2-0aab147c1eca>", line 1
    print('fuction'+ ' :' + \nglossy['fuction'])
                                                ^
SyntaxError: unexpected character after line continuation character
    
        print("fuction:\n " + glossy['fuction'])
   ...: print("list:\n "+ glossy['list'])
   ...: print("statement:\n " + glossy['statement'])
   ...: print("slice:\n "  + glossy['slice'])
   ...:
fuction:
 A series of statements which returns some value to a caller.
list:
 A built-in Python sequence.
statement:
 A statement is part of a suite
slice:
 An object usually containing a portion of a sequence.

    


```
2018-05-26

**源代码**

```python
In [1]: user_0 = {
   ...:     'username':'efermi',
   ...:     'first':'enrico',
   ...:     'last':'fermi',
   ...:     }
   ...:

In [2]: for key,value in user_0.items():
   ...:     print("\nkey: "+ key)
   ...:     print("value: "+ value)
   ...:

key: username
value: efermi

key: last
value: fermi

key: first
value: enrico

In [4]: favorite_languages = {
   ...:     'jen': 'python',
   ...:     'sarah': 'c',
   ...:     'edward': 'ruby',
   ...:     'phil': 'python',
   ...:     }
   ...:
   ...: for name,language in favorite_languages.item():
   ...:     print(name.title() + "'s favorite language is " +
   ...:         language.title() + ".")
   ...:
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-4-09fd2eb0e2dd> in <module>()
      6     }
      7
----> 8 for name,language in favorite_languages.item():
      9     print(name.title() + "'s favorite language is " +
     10         language.title() + ".")

AttributeError: 'dict' object has no attribute 'item'

In [5]: favorite_languages = {
   ...:     'jen': 'python',
   ...:     'sarah': 'c',
   ...:     'edward': 'ruby',
   ...:     'phil': 'python',
   ...:     }
   ...:
   ...: for name,language in favorite_languages.items():
   ...:     print(name.title() + "'s favorite language is " +
   ...:         language.title() + ".")
   ...:
Phil's favorite language is Python.
Sarah's favorite language is C.
Jen's favorite language is Python.
Edward's favorite language is Ruby.

In [9]: favorite_languages = {
   ...:     'jen': 'python',
   ...:     'sarah': 'c',
   ...:     'edward': 'ruby',
   ...:     'phil': 'python',
   ...:     }
   ...:
   ...: friends = ['phil','sarah']
   ...: for name in favorite_languages.keys():
   ...:     print(name.title())
   ...:
   ...:     if name in friends:
   ...:         print(" Hi " + name.title() +
   ...:             ", I see your favorite language is " +
   ...:             favorite_languages[name].title() + "!")
   ...:
Phil
 Hi Phil, I see your favorite language is Python!
Sarah
 Hi Sarah, I see your favorite language is C!
Jen
Edward

In [10]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: if 'erin' not in favorite_languages.keys():
    ...:     print("Erin, please take our poll!")
    ...:
Erin, please take our poll!

In [12]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: for name in sorted(favorite_languages.keys()):
    ...:     print(name.title() + " ,thank you for taking the poll.")
    ...:
Edward ,thank you for taking the poll.
Jen ,thank you for taking the poll.
Phil ,thank you for taking the poll.
Sarah ,thank you for taking the poll.

In [13]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: print("The following languages have been mentioned:")
    ...: for language in favorite_languages.values():
    ...:     print(language.title())
    ...:
The following languages have been mentioned:
Python
C
Python
Ruby

In [14]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: print("The following languages have been mentioned:")
    ...: for language in set(favorite_languages.values()):
    ...:     print(language.title())
    ...:
The following languages have been mentioned:
C
Ruby
Python
练习（1）
In [15]: rivers = {
    ...:     'nile':'egypt',
    ...:     'amazon':'brazil',
    ...:     'yangtse':'china',
    ...:     }
    ...:
    ...: for river,country in rivers.items():
    ...:     print("\nThe " + river.title() +
    ...:         "runs through" + country.title() + '.')
    ...:

The Amazonruns throughBrazil.

The Nileruns throughEgypt.

The Yangtseruns throughChina.

In [16]: rivers = {
    ...:     'nile':'egypt',
    ...:     'amazon':'brazil',
    ...:     'yangtse':'china',
    ...:     }
    ...:
    ...: for river,country in rivers.items():
    ...:     print("\nThe " + river.title() +
    ...:         " runs through" + country.title() + '.')
    ...:

The Amazon runs throughBrazil.

The Nile runs throughEgypt.

The Yangtse runs throughChina.

In [17]: rivers = {
    ...:     'nile':'egypt',
    ...:     'amazon':'brazil',
    ...:     'yangtse':'china',
    ...:     }
    ...:
    ...: for river,country in rivers.items():
    ...:     print("\nThe " + river.title() +
    ...:         " runs through " + country.title() + '.')
    ...:

The Amazon runs through Brazil.

The Nile runs through Egypt.

The Yangtse runs through China.

In [19]: rivers = {
    ...:     'nile':'egypt',
    ...:     'amazon':'brazil',
    ...:     'yangtse':'china',
    ...:     }
    ...:

In [20]: for river in rivers.keys():
    ...:     print(river.title())
    ...: for country in rivers.values():
    ...:     print(country.title())
    ...:
Amazon
Nile
Yangtse
Brazil
Egypt
China
练习（2）
In [21]: favorite_languages = {
    ...:     'jen': 'python',
    ...:     'sarah': 'c',
    ...:     'edward': 'ruby',
    ...:     'phil': 'python',
    ...:     }
    ...:
    ...: names = ['jen','sarah','kate','david']
    ...: for name in names:
    ...:     if name in favorite_languages.keys():
    ...:         print(name.title() + " Thank you for responding !")
    ...:     else:
    ...:         print(name.title() + " Please join the poll!")
    ...:
Jen Thank you for responding !
Sarah Thank you for responding !
Kate Please join the poll!
David Please join the poll!

```

**问题集**

```python
In [3]: favorite_languages = {
   ...:     'jen': 'python',
   ...:     'sarah': 'c',
   ...:     'edward': 'ruby',
   ...:     'phil': 'python',
   ...:     }
   ...:
   ...: for name ,language in favorite_languages.item():
   ...:     print(name.title() + "'s favorite language is " +
   ...:         language.title() + ".")
   ...:
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-3-d0fc9145e86c> in <module>()
      6     }
      7
----> 8 for name ,language in favorite_languages.item():
      9     print(name.title() + "'s favorite language is " +
     10         language.title() + ".")

AttributeError: 'dict' object has no attribute 'item'
items() 掉了最后的s 拼成了item()
In [15]: rivers = {
    ...:     'nile':'egypt',
    ...:     'amazon':'brazil',
    ...:     'yangtse':'china',
    ...:     }
    ...:
    ...: for river,country in rivers.items():
    ...:     print("\nThe " + river.title() +
    ...:         "runs through" + country.title() + '.')
    ...:

The Amazonruns throughBrazil.

The Nileruns throughEgypt.

The Yangtseruns throughChina.
注意str（）中加入空格，让output更好看 

```

**问题集**

今日所学：

loop through all key_value pairs in a dictionary

loop through all keys in a dictionary

loop through a dictionary's keys in order 用到了sorted() 果然不用容易忘

loop through all values in a dictionary



2018-05-27

**源代码**

```python
In [1]: alien_0 = {'color': 'green','points':5}
   ...: alien_1 = {'color': 'yellow','points': 10}
   ...: alien_2 = {'color':'red','points': 15}
   ...:
   ...: aliens = [alien_0,alien_1,alien_2]
   ...:
   ...: for alien in aliens:
   ...:     print(alien)
   ...:
{'points': 5, 'color': 'green'}
{'points': 10, 'color': 'yellow'}
{'points': 15, 'color': 'red'}

In [2]: aliens = []
   ...:
   ...: for alien_number in range(30):
   ...:     new_alien = {'color':'green','points':5,'speed':'slow'}
   ...:     aliens.append(new_alien)
   ...:
   ...: for alien in aliens[:5]:
   ...:     print(alien)
   ...: print("...")
   ...:
   ...: print("Total number of aliens: " + str(len(aliens)))
   ...:
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
...
Total number of aliens: 30
In [4]: aliens = []
   ...:
   ...: for alien_number in range(30):
   ...:     new_alien = {'color':'green','points':5,'speed':'slow'}
   ...:     aliens.append(new_alien)
   ...:
   ...: for alien in aliens[0:3]:
   ...:     if alien['color'] == 'green':
   ...:         alien['color'] == 'yellow'
   ...:         alien['speed'] == 'medium'
   ...:         alien['points'] = 10
   ...:
   ...: for alien in aliens[:5]:
   ...:     print(alien)
   ...: print("...")
   ...:
{'points': 10, 'speed': 'slow', 'color': 'green'}
{'points': 10, 'speed': 'slow', 'color': 'green'}
{'points': 10, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
...
In [7]: aliens = []
   ...:
   ...: for alien_number in range(30):
   ...:     new_alien = {'color':'green','points':5,'speed':'slow'}
   ...:     aliens.append(new_alien)
   ...:
   ...: for alien in aliens[0:3]:
   ...:     if alien['color'] == 'green':
   ...:         alien['color'] = 'yellow'
   ...:         alien['speed'] = 'medium'
   ...:         alien['points'] = 10
   ...:     elif alien['color'] =='yellow':
   ...:         alien['color'] ='red'
   ...:         alien['speed'] ='fast'
   ...:         alien['points']=15
   ...:

In [8]:
   ...: for alien in aliens[:5]:
   ...:     print(alien)
   ...: print("...")
   ...:
{'points': 10, 'speed': 'medium', 'color': 'yellow'}
{'points': 10, 'speed': 'medium', 'color': 'yellow'}
{'points': 10, 'speed': 'medium', 'color': 'yellow'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
{'points': 5, 'speed': 'slow', 'color': 'green'}
...

In [9]: pizza = {
   ...:     'crust':'thick',
   ...:     'toppings':['mushrooms','extra cheese'],
   ...:     }
   ...:
   ...: print("You ordered a " + pizza['crust'] + "-crust pizza " +
   ...:     "with the folowing toppings:")
   ...:
   ...: for topping in pizza['toppings']:
   ...:     print("\t" + topping)
   ...:
   ...:
You ordered a thick-crust pizza with the folowing toppings:
        mushrooms
        extra cheese
In [10]: pizza = {
    ...:     'crust':'thick',
    ...:     'toppings':['mushrooms','extra cheese'],
    ...:     }
    ...:
    ...: print("You ordered a " + pizza['crust'] + "-crust pizza " +
    ...:     "with the folowing toppings:")
    ...:
    ...: for topping in pizza['toppings']:
    ...:     print(topping)
    ...:
You ordered a thick-crust pizza with the folowing toppings:
mushrooms
extra cheese
In [19]: favorite_languages = {
    ...:     'jen': ['python','ruby']
    ...:     'sarah': ['c']
    ...:     'edward': ['ruby','go']
    ...:     'phil':['python','haskell']
    ...:     }
    ...:
    ...: for name,languages in favorite_languages.item():
    ...:     print("\n" + name.title() + "'s favorite languages are:")
    ...:     for language in languages:
    ...:         print("\t" + language.title())
    ...:
  File "<ipython-input-19-5d3b1fce21e4>", line 3
    'sarah': ['c']
          ^
SyntaxError: invalid syntax
In [22]: favorite_languages = {
    ...:     'jen': ['python','ruby'],
    ...:     'sarah': ['c'],
    ...:     'edward': ['ruby','go'],
    ...:     'phil':['python','haskell']
    ...:     }
    ...:
    ...: for name,languages in favorite_languages.items():
    ...:     print("\n" + name.title() + "'s favorite languages are:")
    ...:     for language in languages:
    ...:         print("\t" + language.title())
    ...:

Jen's favorite languages are:
        Python
        Ruby

Phil's favorite languages are:
        Python
        Haskell

Edward's favorite languages are:
        Ruby
        Go

Sarah's favorite languages are:
        C
In [23]: favorite_languages = {
    ...:     'jen': ['python','ruby'],
    ...:     'sarah': ['c'],
    ...:     'edward': ['ruby','go'],
    ...:     'phil':['python','haskell']
    ...:     }
    ...:
    ...: for name,languages in favorite_languages.items():
    ...:     print("\n" + name.title() + "'s favorite languages are:")
    ...:     for language in languages:
    ...:         print("    " + language.title())
    ...:

Jen's favorite languages are:
    Python
    Ruby

Phil's favorite languages are:
    Python
    Haskell

Edward's favorite languages are:
    Ruby
    Go

Sarah's favorite languages are:
    C
In [24]: users = {
    ...:     'aeinstein':{
    ...:         'first':'albert',
    ...:         'last': 'einstein',
    ...:         'location':'princeton',
    ...:         },
    ...:     'mcurie':{
    ...:         'first':'marie',
    ...:         'last':'curie',
    ...:         'location':'paris',
    ...:         },
    ...:     }
    ...:

In [25]: for username,user_info in users.items():
    ...:     print("\nUsername: " + username)
    ...:     full_name = user_info['first'] + " " + user.info['last']
    ...:     location = user_info['location']
    ...:
    ...:     print("\tFull name: " + full_name.title())
    ...:     print("\tLocation: " + location,title())
    ...:

Username: aeinstein
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-25-59f2dd8954c4> in <module>()
      1 for username,user_info in users.items():
      2     print("\nUsername: " + username)
----> 3     full_name = user_info['first'] + " " + user.info['last']
      4     location = user_info['location']
      5

NameError: name 'user' is not defined
In [29]: users = {
    ...:     'aeinstein':{
    ...:         'first':'albert',
    ...:         'last': 'einstein',
    ...:         'location':'princeton',
    ...:         },
    ...:     'mcurie':{
    ...:         'first':'marie',
    ...:         'last':'curie',
    ...:         'location':'paris',
    ...:         },
    ...:     }
    ...:
    ...: for username, user_info in users.items():
    ...:     print("\nUsername: " + username)
    ...:     full_name = user_info['first'] + " " + user_info['last']
    ...:     location = user_info['location']
    ...:
    ...:     print("Full name: " + full_name.title())
    ...:     print("Location: " + location.title())
    ...:

Username: aeinstein
Full name: Albert Einstein
Location: Princeton

Username: mcurie
Full name: Marie Curie
Location: Paris


```

**错题集**

```python
In [18]: favorite_languages = {
    ...:     'jen': ['python','ruby']
    ...:     'sarah': ['c']
    ...:     'edward': ['ruby','go']
    ...:     'phil':['python','haskell']
    ...:     }
    ...:
    ...: for name,languages in favorite_languages.items():
    ...:     print("\n" + name.title() + "'s favorite languages are:")
    ...:     for language in languages:
    ...:         print("\t" + language.title())
    ...:
  File "<ipython-input-18-1942d90aa1a5>", line 3
    'sarah': ['c']
          ^
SyntaxError: invalid syntax
In [22]: favorite_languages = {
    ...:     'jen': ['python','ruby'],
    ...:     'sarah': ['c'],
    ...:     'edward': ['ruby','go'],
    ...:     'phil':['python','haskell']
    ...:     }
    ...:
    ...: for name,languages in favorite_languages.items():
    ...:     print("\n" + name.title() + "'s favorite languages are:")
    ...:     for language in languages:
    ...:         print("\t" + language.title())
    ...:

Jen's favorite languages are:
        Python
        Ruby

Phil's favorite languages are:
        Python
        Haskell

Edward's favorite languages are:
        Ruby
        Go

Sarah's favorite languages are:
        C
dictionary中key-value pair 之间需要逗号

In [17]: pizza = {
    ...:     'crust':'thick',
    ...:     'toppings':['mushrooms','extra cheese'],
    ...:     }
    ...:
    ...: print("You ordered a " + pizza['crust'] + "-crust pizza " +
    ...:     "with the folowing toppings:")
    ...:
    ...: for topping in pizza['toppings']:
    ...:     print("\t" + topping)
    ...:
    ...:
    ...:
You ordered a thick-crust pizza with the folowing toppings:
        mushrooms
        extra cheese

```

**问题集**

今天学的nest 

a list of dictionaries； a list in a dictionary ；a dictionary in a dictionary

感觉难度增加了，代码长了，理解难度也加大了，我再多看几遍，研究研究。



2018-05-28

**源代码**

```python
今天完成练习
6-7.people
In [5]: person_1 = {'first':'albert','last': 'einstein','city':'princeton'}
   ...: person_2 = {'first':'marie','last':'curie','city':'paris'}
   ...: person_3 = {'first':'steve','last':'jobs','city':'seattle'}
   ...:
   ...: people = [person_1,person_2,person_3]
   ...:
   ...: for person in people:
   ...:     print(person)
   ...:
{'city': 'princeton', 'first': 'albert', 'last': 'einstein'}
{'city': 'paris', 'first': 'marie', 'last': 'curie'}
{'city': 'seattle', 'first': 'steve', 'last': 'jobs'}
In [6]: ergou = {'first_name':'qili','last_name':'yang','city':'beijing'}
   ...: danliang = {'first_name':'danliang','last_name':'yang','city':'qingdao'
   ...: }
   ...: mingliang = {'first_name':'mingliang','last_name':'zhu','city':'hefei'}
   ...:
   ...: peoples = [ergou,danliang,mingliang]
   ...: for people in peoples:
   ...:     for k,v in people.items():
   ...:         print(k + ' is ' + v)
   ...:     print('\n')
   ...:
last_name is yang
first_name is qili
city is beijing


last_name is yang
first_name is danliang
city is qingdao


last_name is zhu
first_name is mingliang
city is hefei
In [7]: person_1 = {'first':'albert','last': 'einstein','city':'princeton'}
   ...: person_2 = {'first':'marie','last':'curie','city':'paris'}
   ...: person_3 = {'first':'steve','last':'jobs','city':'seattle'}
   ...:
   ...: people = [person_1,person_2,person_3]
   ...:
   ...: for person in people:
   ...:     for key,value in person.items():
   ...:         print(key +" is "+value)
   ...:     print('\n')
   ...:
city is princeton
first is albert
last is einstein


city is paris
first is marie
last is curie


city is seattle
first is steve
last is jobs
6_8.pets
In [11]: ash = {'kind':' Maltese','owner':'david'}
    ...: esme = {'kind':'Scottish Fold','owner':'marie'}
    ...: quella = {'kind':'teddy','owner':'lily'}
    ...:
    ...: pets = [ash,esme,quella]
    ...: for pet in pets:
    ...:     print(pet)
    ...:
{'owner': 'david', 'kind': ' Maltese'}
{'owner': 'marie', 'kind': 'Scottish Fold'}
{'owner': 'lily', 'kind': 'teddy'}
6_9.Favorite Places
In [12]:favorite_places = {
    ...:     'aeinstein':['france','American'],
    ...:     'mcurie':['China']
    ...:     'lily':['Maldives','Bali','Chejudo']
    ...:     }
    ...:
  File "<ipython-input-12-3091d458f946>", line 8
    'lily':['Maldives','Bali','Chejudo']
         ^
SyntaxError: invalid syntax


In [13]: for name,places in favorite_places:
    ...:     print(name)
    ...:         for place in places:
    ...:             print(place)
    ...: print('\n')
  File "<ipython-input-13-ca3b3f0625d1>", line 3
    for place in places:
    ^
IndentationError: unexpected indent
In [16]: favorite_places = {
    ...:     'aeinstein':['france','American'],
    ...:     'mcurie':['China']
    ...:     'lily':['Maldives','Bali','Chejudo']
    ...:     }
    ...:
  File "<ipython-input-16-d0a5f0c2db07>", line 4
    'lily':['Maldives','Bali','Chejudo']
         ^
SyntaxError: invalid syntax
In [17]: for name,places in favorite_places.items():
    ...:     print(name)
    ...: for place in places:
    ...:     print(place)
    ...: print('\n')
    ...:
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-17-1005507f8efb> in <module>()
----> 1 for name,places in favorite_places.items():
      2     print(name)
      3 for place in places:
      4     print(place)
      5 print('\n')

NameError: name 'favorite_places' is not defined
终于对了
In [6]: favorite_places = {
   ...:     'aeinstein':['france','American'],
   ...:     'mcurie':['China'],
   ...:     'lily':['Maldives','Bali','Chejudo'],
   ...:     }
   ...:

In [7]: for name,places in favorite_places.items():
   ...:     print(name)
   ...:     for place in places:
   ...:         print(place)
   ...: print('\n')
   ...:
aeinstein
france
American
lily
Maldives
Bali
Chejudo
mcurie
China
6_10 Favorite Numbers
In [19]: favorite_number = {
    ...:     'david': [1,3],
    ...:     'lily': [2,8,9],
    ...:     'mathew': [3,6],
    ...:     'colin':[6,0],
    ...:     'edward':[8,5],
    ...:     }
    ...: for name,numbers in favorite_number.items():
    ...:     print(name + "'s favorite numbers are:")
    ...:     for number in numbers:
    ...:         print(number)
    ...: print('\n')
    ...:
colin's favorite numbers are:
6
0
david's favorite numbers are:
1
3
edward's favorite numbers are:
8
5
lily's favorite numbers are:
2
8
9
mathew's favorite numbers are:
3
6
In [20]: favorite_number = {
    ...:     'david': [1,3],
    ...:     'lily': [2,8,9],
    ...:     'mathew': [3,6],
    ...:     'colin':[6,0],
    ...:     'edward':[8,5],
    ...:     }
    ...: for name,numbers in favorite_number.items():
    ...:     print(name + "'s favorite numbers are:")
    ...:     for number in numbers:
    ...:         print(str(number))
    ...: print('\n')
    ...:
colin's favorite numbers are:
6
0
david's favorite numbers are:
1
3
edward's favorite numbers are:
8
5
lily's favorite numbers are:
2
8
9
mathew's favorite numbers are:
3
6
6_11Cities
In [22]: cities = {
    ...:     'paris':{'country':'france','population':'million','fact':'city of
    ...:  art'}
    ...:     'new-york':{'country':'American','population':'milliom','fact':'ci
    ...: ty of fashion'}
    ...:     'Singapore':{'country':'singapore','population':'*million','fact':
    ...: 'city-state'}
    ...:     }
    ...:
    ...: for city,city_info in cities.items():
    ...:     print(city)
    ...:     for k,v in city_info:
    ...:         print(k + '' + v)
    ...: print('\n')
    ...:
  File "<ipython-input-22-bba2e39c7650>", line 3
    'new-york':{'country':'American','population':'milliom','fact':'city of fash
ion'}
             ^
SyntaxError: invalid syntax

In [23]: cities = {
    ...:     'paris':{'country':'france','population':'million','fact':'city of
    ...:  art'},
    ...:     'new-york':{'country':'American','population':'milliom','fact':'ci
    ...: ty of fashion'},
    ...:     'Singapore':{'country':'singapore','population':'*million','fact':
    ...: 'city-state'},
    ...:     }
    ...:
    ...: for city,city_info in cities.items():
    ...:     print(city)
    ...:     for k,v in city_info:
    ...:         print(k + '' + v)
    ...: print('\n')
    ...:
paris
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-23-7b9353ac36bd> in <module>()
      7 for city,city_info in cities.items():
      8     print(city)
----> 9     for k,v in city_info:
     10         print(k + '' + v)
     11 print('\n')

ValueError: too many values to unpack (expected 2)
In [25]: cities = {
    ...:     'paris':{'country':'france','population':'million','fact':'city of
    ...:  art'},
    ...:     'new-york':{'country':'American','population':'milliom','fact':'ci
    ...: ty of fashion'},
    ...:     'Singapore':{'country':'singapore','population':'*million','fact':
    ...: 'city-state'},
    ...:     }
    ...:
    ...: for city,city_info in cities.items():
    ...:     print(city)
    ...:     for k,v in city_info.items():
    ...:         print(k + ' ' + v)
    ...: print('\n')
    ...:
paris
fact city of art
country france
population million
new-york
fact city of fashion
country American
population milliom
Singapore
fact city-state
country singapore
population *million
```

**错题集**

```python
1
favorite_places = {
    'aeinstein':['france','American'],
    'mcurie':['China'],
    'lily':['Maldives','Bali','Chejudo'],
    }

for name,places in favorite_places.items():
    print(name)
for place in places:
    print(place)
print('\n')
aeinstein
lily
mcurie
China
1.for place in places 之前需要缩进
2
In [16]: favorite_places = {
    ...:     'aeinstein':['france','American'],
    ...:     'mcurie':['China']
    ...:     'lily':['Maldives','Bali','Chejudo']
    ...:     }
    ...:
  File "<ipython-input-16-d0a5f0c2db07>", line 4
    'lily':['Maldives','Bali','Chejudo']
         ^
SyntaxError: invalid syntax
In [17]: for name,places in favorite_places.items():
    ...:     print(name)
    ...: for place in places:
    ...:     print(place)
    ...: print('\n')
    ...:
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-17-1005507f8efb> in <module>()
----> 1 for name,places in favorite_places.items():
      2     print(name)
      3 for place in places:
      4     print(place)
      5 print('\n')

NameError: name 'favorite_places' is not defined
2.定义dictionary时 每个key-value 之间需要逗号隔开
3
In [23]: cities = {
    ...:     'paris':{'country':'france','population':'million','fact':'city of
    ...:  art'},
    ...:     'new-york':{'country':'American','population':'milliom','fact':'ci
    ...: ty of fashion'},
    ...:     'Singapore':{'country':'singapore','population':'*million','fact':
    ...: 'city-state'},
    ...:     }
    ...:
    ...: for city,city_info in cities.items():
    ...:     print(city)
    ...:     for k,v in city_info:
    ...:         print(k + '' + v)
    ...: print('\n')
    ...:
paris
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-23-7b9353ac36bd> in <module>()
      7 for city,city_info in cities.items():
      8     print(city)
----> 9     for k,v in city_info:
     10         print(k + '' + v)
     11 print('\n')

ValueError: too many values to unpack (expected 2)
3.for loop dictionary 时 最后需要method.items() 
(which returns a list of key-value pairs)
                      
总结 
定义dictionary时，每个key-value 之间需要逗号隔开。
嵌入list之后，太长，容易忘记。
for loop dictionary 时，最后需要method.items()或者,keys().values()
而for loop list不需要
```
学习Chapter6 顺手查的单词

**nest**

1. 助记：来自古英语nest , 来自PIE*nisdos , 鸟巢，来自*ni , 向下，词源同beneath , *sed , 坐，词源同sit . 即坐的地方，落脚的地方，引申词义鸟巢，鸟窝。
2. 词源：Old English nest "bird's nest, snug retreat," also "young bird, brood," from Proto-Germanic *nistaz (source also of Middle Low German, Middle Dutch nest, German Nest), from PIE *nizdo- (source also of Sanskrit nidah "resting place, nest," Latin nidus "nest," Old Church Slavonic gnezdo, Old Irish net, Welsh nyth, Breton nez "nest"), probably from *ni "down" + from PIE root *sed- (1) "to sit."
3. 拓展：**crow's nest**桅杆瞭望台。古代北欧人出海时，习惯将乌鸦装在笼子里带上船，估摸着快到岸边了，鸟笼被放在桅杆高处并把鸟放出来，然后船顺着鸟飞行的方向航行，就能到达岸边。现在crow's nest可以指任何瞭望台，比如山顶上的也可以。The sailor in the crow's nest is right,we are close to the land. 

**crust**

1. 助记：来自PIE*kreus,冷冻，结晶，词源同crystal,cryogenic.原指由冷冻形成的硬壳。
2. 词源：early 14c., "hard outer part of bread," from Old French crouste (13c., Modern French croûte) and directly from Latin crusta "rind, crust, shell, bark," from PIE *krus-to- "that which has been hardened," suffixed form of root *kreus- "to begin to freeze, form a crust." From mid-15c. as "any hard, external portion of comparative thinness;" meaning "outer shell of the earth" is from 1550s.
3. 拓展：**upper crust**上流社会。crust在这里特指面包皮，词根本意是“硬的”（因为面包皮更硬一些），与希腊词源的crystal水晶同源。同时因为面包皮的香味更浓些，所以对主食是面包的中世纪英国人来说，面包皮是要留给领主吃的。Much of this, however, may benefit only a thin upper crust of Indian society. 



