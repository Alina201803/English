

## Chapter 2: Variables and Simple Data Types



------

### 豆腐块



**1.源代码**

这里写,这一章节中,我输入的代码, 比如:

```python
#hello_world.py
print("Hello Python world!")a
```

上面的这两行的格式:是这样设置的:

可以快捷键: Ctrl + Option + C

**2.错题本**

过程中,由于马虎或者不小心犯的错误. 比如

```python
In [2]: prnt("Hello Python world!")
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-2-1edf4e8977d8> in <module>()
----> 1 prnt("Hello Python world!")

NameError: name 'prnt' is not defined

```

print拼写错误.



**3.问题集**

什么是variable?

Google之外的搜索网站:

搜狗英文版 http://english.sogou.com/?b_o_e=1&ie=utf8&fr=common_index_nav&query=

必应: www.bing.com



---

### Alina

2018-05-13

1.**源代码**

```python
print("hello python world!")

 message = "hello python world!"

 print(message)

 mesage ="hello python Crash Course reader!"

 print(mesage)
```

**2.错题本**

```python
 File "<ipython-input-1-bed9a149a6a8>", line 1
    print("hello python world!)
                         ^
SyntaxError: EOL while scanning string literal
```

value最后没有对应的双引号

**3.问题集**

function讲解

Functions assign a single output for each of their inputs.

https://www.khanacademy.org/math/algebra/algebra-functions/evaluating-functions/v/what-is-a-function



2018-5-14

1. 源代码
   ```python
   In [1]: name = "ada lovelace"
   ```

   ```python
   In [2]: print(name.title())
   Ada Lovelace

   In [1]: name ="ada lovelace"

   In [2]: print(name.upper())
   ADA LOVELACE

   In [3]: print(name.lower())
   ada lovelace

   In [8]: frist_name = "ada"

   In [9]: last_name = "lovelace"

   In [10]: full_name = frist_name + " " + last_name

   In [11]: print(full_name)
   ada lovelace

   In [12]: print("hello," + full_name.title() + "!")
   hello,Ada Lovelace!

   In [13]: message = "hello," + full_name.title() + "!"

   In [14]: print(message)
   hello,Ada Lovelace!
   ```


```python
   In [17]: print("\tpython")
           python

   In [18]: print("languages:\npython\nC\nJavaScript")
   languages:
   python
   C
   JavaScript

   In [20]: print("language:\n\tPython\n\tC\n\tJavaScript")
   language:
           Python
           C
           JavaScript
```

2. 错题集
   ```python
   In [19]: print("languages:\n\tPython\n\tC\n\tJavaScript)
     File "<ipython-input-19-daaf4fbab88e>", line 1
       print("languages:\n\tPython\n\tC\n\tJavaScript)
                                                      ^
   SyntaxError: EOL while scanning string literal
   又一次忘记打上后引号
   #写大段的代码的时候可以在vscode中,双引号会自动补全.
   ```

3. 问题集
   **Python Methods** In the simplest term a method is a function inside of an object. You can pass attributes (variable inside a method) to the class and method that will get processed inside of the method and independently for each object.
   what is a “method” in python？
   https://stackoverflow.com/questions/3786881/what-is-a-method-in-python

   > 真牛,说上手就上手了, methods就是第八章的functions(中文翻译成函数,应该翻译成do something)
   >
   > 现在用的method, 比如print, 是python已经写好的,直接用就可以,
   >
   > 后面学到function可以自己写去做任何事情的function.




2018-05-15

**源代码**

```python
In [1]: favorite_language = 'python '

In [2]: favorite_language = favorite_language.rstrip()

In [3]: favorite_language
Out[3]: 'python'

In [6]: favorite_language = ' python '

In [7]: favorite_language.rstrip()
Out[7]: ' python'

In [8]: favorite_language.lstrip()
Out[8]: 'python '

In [9]: favorite_language.strip()
Out[9]: 'python'

In [10]: message = "One of Python's strengths is its diverse community."

In [11]: print(message)
One of Python's strengths is its diverse community.
In [14]: name = "Eric"

In [15]: message = "hello," + name.title() + "would you like to learn some Pyth
    ...: on today?"

In [16]: print(message)
hello,Ericwould you like to learn some Python today?

In [1]: name = "albert einstein"
In [4]: message = '"A person who never made a mistake never tried anything new.
   ...: "'

In [5]: print(name.title() + "once said," + message)
Albert Einsteinonce said,"A person who never made a mistake never tried anything
 new."

```

**错题集**

```python
1. 
In [13]: name = Eric
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-13-131e1517a5f0> in <module>()
----> 1 name = Eric

NameError: name 'Eric' is not defined
定义variable时 需要引号

2.
In [22]: name = "albert einstein"

In [23]: message = "A person who never made a mistake never tried anything new"
    ...:

In [24]: message = "A person who never made a mistake never tried anything new.
    ...: "

In [25]: print(name,title() + "once said," + ""message"")
  File "<ipython-input-25-13429ee7b222>", line 1
    print(name,title() + "once said," + ""message"")
                                                ^
SyntaxError: invalid syntax
In [4]: message = '"A person who never made a mistake never tried anything new.
   ...: "'
单引号内可以嵌入双引号（quotation marks)
```

今天把之前学的又练习了一下。

2018-05-16

**源代码**

```python
 2 + 3
 5

 3 - 2
 1

 3 * 2
 6

 3 / 2
 1.5

 3 ** 3
 27

 10 ** 2
 100

 2 + 3*4
 14

 0.2 + 0.3
 0.5

 2 * 0.1
 0.2

 0.1 * 0.2
 0.020000000000000004

 age = 23

 message = "Happy " + age + "rd Birthday!"
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-12-1109a656b8f5> in <module>()
----> 1 message = "Happy " + age + "rd Birthday!"

TypeError: Can't convert 'int' object to str implicitly

message = "Happy " + str(age) + "rd Birthday!"
print(message)
Happy 23rd Birthday!

print(3+5)
print(10-2)
print(2*4)
print(16/2)   
8
8
8
8.0

number = 5
message = "there are " + str(number) + " apples"
print(message)
there are 5 apples

#Say hello to everyone.
print("hello Python people!")
hello Python people!

import this
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!

```

**问题集**

feature 是什么意思?

**feature** 

early 14c., "make, form, fashion" (obsolete), from Anglo-French feture, from Old French faiture "deed, action; fashion, shape, form; countenance," from Latin factura "a formation, a working," from past participle stem of facere "make, do, perform" (from PIE root *dhe- "to set, put").

2018-05-17

**源代码**

```python
bicycles = ["trek" , "cannondale" , "redline" , "specialized" ]
print(bicycles)
['trek', 'cannondale', 'redline', 'specialized']

bicycles = ['trek','cannondale','redline','specialized']
print(bicycles)
['trek', 'cannondale', 'redline', 'specialized']
print(bicycles[0])
trek
print(bicycles[0].title())
Trek
print(bicycles[1])
cannondale
print(bicycles[2])
redline
print(bicycles[-1])
specialized
print(bicycles[-2]
     
     
message = "My first bicycle was a " + bicycles[0].title() + "."
print(message)
My first bicycle was a Trek.

names = ['Lida','Olivia','Kaga','Yuriya']
print(names[0])
Lida
print(names[3])
Yuriya
print(names[-1])
Yuriya
message = "Hello, " + names[0] + "!" 
print(message)
Hello, Lida!
message = "Hello, " +names[1] + "!"
print(message)
Hello, Olivia!

motorcycles = ['honda','yamaha','suzuki']
print(motorcycles)
['honda', 'yamaha', 'suzuki']
      
motorcycles.append('ducati')
print(motorcycles)
['ducati', 'yamaha', 'suzuki', 'ducati']

motorcycles = []
 motorcycles.append('handa')
 motorcycles.append('yamaha')
 motorcycles.append('suzuki')
 print(motorcycles)
['handa', 'yamaha', 'suzuki']

 motorcycles.insert(0,'ducati')
 print(motorcycles)
['ducati', 'handa', 'yamaha', 'suzuki']

 del motorcycles[0]
 print(motorcycles)
['handa', 'yamaha', 'suzuki']

 del motorcycles[1]
 print(motorcycles)
['handa', 'suzuki']

 motorcycles = ['honda','yamaha','suzuki']
 print(motorcycles)
['honda', 'yamaha', 'suzuki']
 popped_motorcycle = motorcycles.pop()
 print(motorcycles)
['honda', 'yamaha']
 print(popped_motorcycle)
suzuki

 motorcycles = ['honda','yamaha','suzuki']
    ...: last_owed = motorcycles.pop()
    ...: print('The last motorcycles I owed was a '+ last_owed.title() + ".")
    ...:
    ...:
The last motorcycles I owed was a Suzuki.
```

**错题集**

```python
In [24]: motocycles[0] = 'ducati'
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-24-b84fb9895f63> in <module>()
----> 1 motocycles[0] = 'ducati'

NameError: name 'motocycles' is not defined
motorcycles 拼错了
```

**问题集**

```python
1 motorcycles = ['honda','yamaha','suzuki']
 print(motorcycles)
['honda', 'yamaha', 'suzuki']
 popped_motorcycle = motorcycles.pop()
2 print(motorcycles)
['honda', 'yamaha']
print(popped_motorcycle)
suzuki
不太明白为什么1和2中的print(motorcycles)结果不一样，我认为并没有从新定义motorcycles，只是新定义了一个popped_motorcycles.

```

You should spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to some- thing new.