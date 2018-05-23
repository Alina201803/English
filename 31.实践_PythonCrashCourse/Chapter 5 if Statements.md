### Chapter 5 If Statements

#### Alina

2018-05-22

**源代码**

```python
1.
In [1]: cars = ['audi','bmw','subaru','toyota']
   ...:
   ...: for car in cars:
   ...:     if car = 'bmw'
   ...:         print(car.upper())
   ...:     else:
   ...:         print(car.title())
   ...:
  File "<ipython-input-1-e109ccd0a172>", line 4
    if car = 'bmw'
           ^
SyntaxError: invalid syntax
    
In [4]: cars = ['audi','bmw','subaru','toyota']
   ...:
   ...: for car in cars:
   ...:     if car == 'bmw':
   ...:         print(car.upper())
   ...:     else:
   ...:         print(car.title())
   ...:
Audi
BMW
Subaru
Toyota

2.
In [5]: car = 'bmw'

In [6]: car == 'bmw'
Out[6]: True

In [7]: car = 'audi'

In [8]: car == 'bmw'
Out[8]: False

In [9]: car = 'Audi'

In [10]: car =='audi'
Out[10]: False
3.
In [13]: car = 'Audi'
In [14]: car.lower() == 'audi'
Out[14]: True
In [15]: car
Out[15]: 'Audi'
!=
In [17]: requested_topping = 'mushroom'
    ...: if requested_topping !='anchovies':
    ...:     print('Hold the anchovies')
    ...:
Hold the anchovies
In [18]: age = 18

In [19]: age == 18
Out[19]: True

In [20]: answer = 17
    ...: if answer !=42:
    ...:     print("That is not the correct answer. Please try again!")
    ...:
That is not the correct answer. Please try again!
数字
In [21]: age = 19

In [22]: age < 21
Out[22]: True

In [23]: age > 21
Out[23]: False

In [24]: age >= 21
Out[24]: False

In [25]: age_0 = 22
    ...: age_1 = 18
    ...: age_0 >= 21 and age_1 >=21
    ...:
Out[25]: False

In [26]: age_1 = 22
    ...: age_0 >= 21 and age_1 >= 21
    ...:
Out[26]: True

In [27]: age_0 = 22
    ...: age_1 = 18
    ...: age_0 >= 21 or age_1 >=21
    ...:
Out[27]: True
in  
In [28]: requested_toppings = ['mushrooms','onions','pineapple']
    ...: 'mushrooms'in requested_toppings
    ...:
Out[28]: True

In [29]: 'pepperoni'in requested_toppings
Out[29]: False

In [31]: banned_users =['andrew','carolina','david']
    ...: user = 'marie'
    ...:
    ...: if user not in banned_users:
    ...:     print(user.title() + ", you can post a reponse if you wish")
    ...:
Marie, you can post a reponse if you wish

练习
In [34]: car = 'subaru'
    ...: print("Is car == 'subaru'? I predict True.")
    ...: print(car == 'subaru')
    ...:
Is car == 'subaru'? I predict True.
True

In [35]: print("\nIs car == 'audi'? I predict False")
    ...: print(car == 'audi')
    ...:

Is car == 'audi'? I predict False
False


```

**错题集**

```python
In [1]: cars = ['audi','bmw','subaru','toyota']
   ...:
   ...: for car in cars:
   ...:     if car = 'bmw'
   ...:         print(car.upper())
   ...:     else:
   ...:         print(car.title())
   ...:
  File "<ipython-input-1-e109ccd0a172>", line 4
    if car = 'bmw'
           ^
SyntaxError: invalid syntax
= 与 == 的含义不同
car = 'audi'   Set the value of car equal to 'audi'
car== 'bmw'    Is the value of car equal to 'bmw'
```
2018-05-23

**源代码**

```python
In [1]: age = 19
   ...: if age >= 18:
   ...:     print("You are old enough to vote!")
   ...:
You are old enough to vote!

In [3]: age = 19
   ...: if age >= 18:
   ...:     print("You are old enough to vote!")
   ...:     print("Have you registered to vote yet?")
   ...:
You are old enough to vote!
Have you registered to vote yet?

In [4]: age = 17
   ...: if age >= 18:
   ...:     print("You are old enough to vote!")
   ...:     print("Have you registered to vote yet?")
   ...: else:
   ...:     print("Sorry,you are too young to vote.")
   ...:     print("Please register to vote as soon as you turn 18!")
   ...:
Sorry,you are too young to vote.
Please register to vote as soon as you turn 18!

In [5]: age = 12
   ...:
   ...: if age < 4:
   ...:     print("Your admission cost is $0.")
   ...: elif age < 8:
   ...:     print("Your admission cost is $5.")
   ...: else:
   ...:     print("Your admission cost is $10.")
   ...:
Your admission cost is $10.

In [6]: age = 12
   ...:
   ...: if age < 4:
   ...:     price = 0
   ...: elif age < 18:
   ...:     price = 5
   ...: else:
   ...:     price = 10
   ...:

In [7]: print("Your admission cost is $"+str(price) + ".")
   ...:
Your admission cost is $5.

In [8]: age = 12
   ...:
   ...: if age < 4:
   ...:     price = 0
   ...: elif age < 18:
   ...:     price = 5
   ...: elif age < 65:
   ...:     price = 10
   ...: else:
   ...:     price = 5
   ...: print("Your admission cost is $"+str(price) + ".")
   ...:
Your admission cost is $5.

In [10]: requested_toppings = ['mushrooms','extra cheese']
    ...:
    ...: if 'mushrooms' in requested_toppings:
    ...:     print("Adding mushrooms.")
    ...: if 'pepperoni' in requested_toppings:
    ...:     print("Adding pepperoni.")
    ...: if 'extra cheese' in requested_toppings:
    ...:     print("Adding extra cheese.")
    ...:
    ...: print("\nFished making your pizza!")
    ...:
Adding mushrooms.
Adding extra cheese.

Fished making your pizza!

In [11]: requested_toppings = ['mushrooms','extra cheese']
    ...:
    ...: if 'mushrooms' in requested_toppings:
    ...:     print("Adding mushrooms.")
    ...: elif 'pepperoni' in requested_toppings:
    ...:     print("Adding pepperoni.")
    ...: elif 'extra cheese' in requested_toppings:
    ...:     print("Adding extra cheese.")
    ...:
    ...: print("\nFished making your pizza!")
    ...:
Adding mushrooms.

Fished making your pizza!

练习：
1.
In [12]: alien_color = ['green','yellow','red']
    ...:
    ...: Alien = alien_color[0]
    ...: if Alien == 'green':
    ...:     print('You just earned 5 points!')
    ...:
You just earned 5 points!

In [13]: alien_color = ['green','yellow','red']
    ...:
    ...: Alien = alien_color[0]
    ...: if Alien == 'red':
    ...:     print('You just earned 5 points!')
    ...:

In [14]: alien_color = ['green','yellow','red']
    ...:
    ...: Alien = alien_color[2]
    ...: if Alien == 'green':
    ...:     print('You just earned 5 points!')
    ...: elif Alien != 'green':
    ...:     print("You just earned 10 points!")
    ...:
You just earned 10 points!

In [15]: alien_color = ['green','yellow','red']
    ...:
    ...: Alien = alien_color[2]
    ...: if Alien == 'green':
    ...:     print('You just earned 5 points!')
    ...: else:
    ...:     print("You just earned 10 points!")
    ...:
You just earned 10 points!

In [16]: alien_color = ['green','yellow','red']
    ...:
    ...: Alien = alien_color[2]
    ...: if Alien == 'green':
    ...:     print('You just earned 5 points!')
    ...: elif Alien == 'yellow':
    ...:     print("You just earned 10 points!")
    ...: elif Alien == 'red':
    ...:     print("You just earned 15 points!")
    ...:
You just earned 15 points!
2.
In [23]: age = 44
    ...: if age < 2:
    ...:     print('The person is a baby.')
    ...: elif age <4:
    ...:     print('The person is a toddler.')
    ...: elif age <13:
    ...:     print('The person is a kid.')
    ...: elif age <20:
    ...:     print('The person is a teenager.')
    ...: elif age <65:
    ...:     print('The person is a adult.')
    ...:
    ...: else:
    ...:      print('The person is a elder.')
    ...:
The person is a adult.


```

**错题集**

```python
In [20]: age = 44
    ...: if age < 2:
    ...:     print('The person is a baby.')
    ...: elif age >= 2:
    ...:     print('The person is a toddler.')
    ...: elif age >= 4:
    ...:     print('The person is a kid.')
    ...: elif age >= 13:
    ...:     print('The person is a teenager.')
    ...: elif age >= 20:
    ...:     print('The person is a adult.')
    ...: elif age >=65:
    ...:     print('The person is a elder.')
    ...: else:
    ...:      print('The person is a elder.')
    ...:
The person is a toddler.
改为
In [23]: age = 44
    ...: if age < 2:
    ...:     print('The person is a baby.')
    ...: elif age <4:
    ...:     print('The person is a toddler.')
    ...: elif age <13:
    ...:     print('The person is a kid.')
    ...: elif age <20:
    ...:     print('The person is a teenager.')
    ...: elif age <65:
    ...:     print('The person is a adult.')
    ...:
    ...: else:
    ...:      print('The person is a elder.')
    ...:
The person is a adult.

```

**问题集**

今日所学：if statements, if -else, if-elif-else 

