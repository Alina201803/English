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