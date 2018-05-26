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