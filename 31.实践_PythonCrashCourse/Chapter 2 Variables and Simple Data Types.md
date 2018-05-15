

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





----

### Aqua







**1.源代码**





**2.错题本**





**3.问题集**





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




----

### 幽幽





**1.源代码**





**2.错题本**





**3.问题集**





----

### 旷野



**1.源代码**





**2.错题本**





**3.问题集**







----

### 秋风凌





**1.源代码**





**2.错题本**





**3.问题集**





You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to some- thing new.