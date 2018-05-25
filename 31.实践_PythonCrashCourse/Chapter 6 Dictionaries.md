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