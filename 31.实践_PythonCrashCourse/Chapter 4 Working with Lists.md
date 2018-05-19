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