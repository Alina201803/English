### Working with lists

##### Alina

2018-05-19

**源代码**

```python
1.
In [1]: magicians = ['alice','david','carolina']

In [2]: for magician in magivians
  File "<ipython-input-2-c29d55e6b034>", line 1
    for magician in magivians
                             ^
SyntaxError: invalid syntax


In [3]: for magician in magicians:
   ...:     print(magician)
   ...:
alice
david
carolina

In [4]: magicians = ['alice','david','carolina']

In [5]: for magician in magicians:
   ...:     print(magician.title() + ", that was a great trick!")
   ...:
Alice, that was a great trick!
David, that was a great trick!
Carolina, that was a great trick!

In [6]: for magician in magicians:
   ...:     print(magician.title() + ", that was a great trick!")
   ...:     print("I can't wait to see your next trick, " + magician.title() + "
   ...:
Alice, that was a great trick!
I can't wait to see your next trick, Alice.



In [3]: for magician in magicians:
   ...:     print(magician)
   ...:
alice
david
carolina

In [4]: magicians = ['alice','david','carolina']

In [5]: for magician in magicians:
   ...:     print(magician.title() + ", that was a great trick!")
   ...:
Alice, that was a great trick!
David, that was a great trick!
Carolina, that was a great trick!

In [6]: for magician in magicians:
   ...:     print(magician.title() + ", that was a great trick!")
   ...:     print("I can't wait to see your next trick, " + magician.title() + "
.\n")
   ...:
Alice, that was a great trick!
I can't wait to see your next trick, Alice.

David, that was a great trick!
I can't wait to see your next trick, David.

Carolina, that was a great trick!
I can't wait to see your next trick, Carolina.


In [7]: for magician in magicians:
   ...:     print(magician.title() + " , that was a great trick!")
   ...:     print("I can't wait to see your next trick, " + magician.title() + "
.\n")
   ...: print("Thank you ,everyone. That was a great magic show!")
   ...:
Alice , that was a great trick!
I can't wait to see your next trick, Alice.

David , that was a great trick!
I can't wait to see your next trick, David.

Carolina , that was a great trick!
I can't wait to see your next trick, Carolina.

Thank you ,everyone. That was a great magic show!

                  
练习：
In [8]: pizzas = ['sicilian','neapolitan','chicago']

In [9]: for pizza in pizzas
  File "<ipython-input-9-588963abfe77>", line 1
    for pizza in pizzas
                       ^
SyntaxError: invalid syntax


In [10]: for pizza in pizzas:
    ...:     print("I like " + pizza.title() +" pizza!")
    ...:
I like Sicilian pizza!
I like Neapolitan pizza!
I like Chicago pizza!

In [11]:     print("I like " + pizza.title() +" pizza!" + " I really love it!")
I like Chicago pizza! I really love it!

In [12]:

In [12]: for pizza in pizzas:
    ...:     print("I like " + pizza.title() +" pizza!" + " I really love it!")
    ...:
I like Sicilian pizza! I really love it!
I like Neapolitan pizza! I really love it!
I like Chicago pizza! I really love it!

In [13]: animals = ['dog','cat','monkey']

In [14]: for animal in animals:
    ...:     print("A " + animal+ "can make a great pet!")
    ...:
A dogcan make a great pet!
A catcan make a great pet!
A monkeycan make a great pet!

In [15]: for animal in animals:
    ...:     print("A " + animal+ " can make a great pet!")
    ...:
    ...:
A dog can make a great pet!
A cat can make a great pet!
A monkey can make a great pet!
```

**错题集**

```python
In [1]: magicians = ['alice','david','carolina']

In [2]: for magician in magivians
  File "<ipython-input-2-c29d55e6b034>", line 1
    for magician in magivians
                             ^
SyntaxError: invalid syntax
forgetting the Colon 
想要和计算机对话，让它明白 for loop 语句，冒号不能少
```

**问题集**

发现一个有意思的单词

**indent**

in-进入，使 + dent-齿，咬合，用于指古代锯齿状凹痕的法定文件或有法律效力的文书，引申词义下订单，订合同。

indenture（契约）：以锯齿状边缘分割的契约
英语单词indenture由in+dent（齿）+ure（名词后缀）构成，表示契约。契约和齿有什么关系呢？原来，在中世纪，人们在签订契约时，往往会把两份内容相同的契约写在同一张羊皮纸上，然后在中间以锯齿状边缘分割开，双方各持一份。以后需要比对契约真伪，只需要查看两份契约的锯齿边缘能否对上即可。这种以锯齿状边缘分割的契约就被称为indenture。现在虽然不再这么做了，但这个词却保留了下来。



indentation 在计算机中 为缩进的意思  想象 参差不齐 有凹近 有突出 



2018-05-20

**源代码**

```python
1.
In [1]: for value in range(1,5):
   ...:     print(value)
   ...:
1
2
3
4

In [2]: for value in range(1,6):
   ...:     print(value)
   ...:
1
2
3
4
5

In [3]: numbers = list(range(1,6))

In [4]: print(numbers)
[1, 2, 3, 4, 5]

In [5]: even_numbers = list(range(2,11,2))

In [6]: print(even_numbers)
[2, 4, 6, 8, 10]

2.
In [7]: squares = []
In [9]: for value in range(1,11):
   ...:     square = value**2
   ...:     squares.append(square)
   ...: print(squares)
   ...:
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
更简洁
In [23]: squares =[]
In [24]: for value in range(1,11):
    ...:     squares.append(value**2)
    ...:

In [25]: print(squares)
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

3.
In [26]: digits = [1,2,3,4,5,6,7,8,9,0]

In [27]: min(digits)
Out[27]: 0

In [28]: max(digits)
Out[28]: 9

In [29]: sum(digits)
Out[29]: 45

4.
list comprehension
In [30]: squares = [value**2 for value in range(1,11)]

In [31]: print(squares)
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

练习：
In [32]: for value in range(1,21):
    ...:     print(value)
    ...:
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20

In [33]: numbers = list(range(1,1000001))
In [34]: min(numbers)
Out[34]: 1
In [35]: max(numbers)
Out[35]: 1000000
In [36]: sum(numbers)
Out[36]: 500000500000

In [39]: numbers =list(range(1,21,2))
In [40]: print(numbers)
[1, 3, 5, 7, 9, 11, 13, 15, 17, 19]

In [41]: cubes =[]
In [42]: for value in range(3,31):
    ...:     cube = value**3
    ...:     cubes.append(cube)
In [43]: print(cubes)
[27, 64, 125, 216, 343, 512, 729, 1000, 1331, 1728, 2197, 2744, 3375, 4096, 4913
, 5832, 6859, 8000, 9261, 10648, 12167, 13824, 15625, 17576, 19683, 21952, 24389
, 27000]

In [44]: cubes = []
In [45]: for value in range(1,11):
    ...:     cube = value**3
    ...:     cubes.append(cube）
In [46]: print(cubes)
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]

In [47]: cubes = [value**3 for value in range(1,11)]

In [48]: print(cubes)
[1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]


```

**错题集**

```python
In [2]: cubes =[value**3 for value in range(1,11):]
  File "<ipython-input-2-77dc9a385b94>", line 1
    cubes =[value**3 for value in range(1,11):]
                                           ^
SyntaxError: invalid syntax
list comprehension中 for loop statement 最后不用冒号

```
2018-05-21

**源代码**

```python
1.
In [1]:  players = ['charles','martina','michael','florence','eli']
   ...: print(players[0:3])
   ...:
['charles', 'martina', 'michael']

In [3]: print(players[1:4])
['martina', 'michael', 'florence']

In [4]: print(players[:4])
['charles', 'martina', 'michael', 'florence']

In [5]: print(players[2:])
['michael', 'florence', 'eli']

In [6]: print(players[-3:])
['michael', 'florence', 'eli']

In [7]: print("Here are the first three palyers on my team:")
Here are the first three palyers on my team:

In [8]: for player in players[:3]:
   ...:     print(player.title())
   ...:
Charles
Martina
Michael

2.
In [9]: my_foods = ['pizza','falafel','carrot cake']

In [10]: friend_foods = my_foods[:]

In [11]: print("My favorite foods are:")
My favorite foods are:
3.
In [14]: my_foods = ['pizza','falafel','carrot cake']
    ...: friend_foods = my_foods[:]
    ...: print("My favorite foods are:")
    ...: print(my_foods)
    ...: print("\nMy friend's favorite foods are:")
    ...: print(friend_foods)
    ...:
My favorite foods are:
['pizza', 'falafel', 'carrot cake']

My friend's favorite foods are:
['pizza', 'falafel', 'carrot cake']
4.
In [15]: my_foods.append('cannoli')
    ...: friend_foods.append('ice cream')
    ...: print("My favorite foods are:")
    ...: print(my_foods)
    ...: print("\nMy friend's favorite foods are:")
    ...: print(friend_foods)
    ...:
My favorite foods are:
['pizza', 'falafel', 'carrot cake', 'cannoli']

My friend's favorite foods are:
['pizza', 'falafel', 'carrot cake', 'ice cream']

In [16]: my_foods = ['pizza','falafel','carrot cake']
    ...: friend_foods = my_foods
    ...: my_foods.append('cannoli')
    ...: friend_foods.append('ice cream')
    ...: print("My favorite foods are:")
    ...: print(my_foods)
    ...: print("\nMy friend's favorite foods are:")
    ...: print(friend_foods)
    ...:
My favorite foods are:
['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']

My friend's favorite foods are:
['pizza', 'falafel', 'carrot cake', 'cannoli', 'ice cream']

5.
In [17]: dimensions = (200,5)
    ...: print(dimensions[0])
    ...: print(dimensions[1])
    ...:
200
5
In [18]: dimensions[0] = 250
----------------------------------------------------------------------
TypeError                                 Traceback (most recent call
<ipython-input-18-7e4e55b78966> in <module>()
----> 1 dimensions[0] = 250

TypeError: 'tuple' object does not support item assignment

In [20]: dimensions = (200,5)
    ...: print("Original dimensions")
    ...: for dimension in dimensions:
    ...:     print(dimension)
    ...: dimensions = (400,100)
    ...: print("\nModified dimensions")
    ...: for dimension in dimensions:
    ...:     print(dimension)
    ...:
Original dimensions
200
5

Modified dimensions
400
100

```

**错题集**

```python
今天没有意外的错误:) 

总结一下所学内容：

1.slicing a list : print(players[0:3])

2.looping through a slice : for player in players[:3]:
                            	print(player)
            
3.copying a list : friend_foods = my_foods[:]
  friend_foods = my_foods (doesn't work)
                           
4.tuples:an immutable list 将lists中的[] 换为（）

```







