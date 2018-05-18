### Chapter 3 Introducing Lists

##### Alina

2018-05-18

**源代码**

```python
In [1]: motorcycles = ['handa','yamaha','suzuki']

In [2]: first_owned = motorcycles.pop(0)

In [3]: print('The first motorcycles I owned was a ' + first_owned.title() + '.')
The first motorcycles I owned was a Handa.

In [4]: motorcycles = ['honda','yamaha','suzuki','ducati']

In [5]: print(motorcycles)
['honda', 'yamaha', 'suzuki', 'ducati']

In [6]: motorcycles.remove('ducati')

In [7]: print(motorcycles)
['honda', 'yamaha', 'suzuki']

In [8]: motorcycles.append('ducati')

In [9]: print(motorcycles)
['honda', 'yamaha', 'suzuki', 'ducati']

In [10]: too_expensive ='ducati'

In [11]: motorcycles.remove(too_expensive)

In [12]: print(motorcycles)
['honda', 'yamaha', 'suzuki']

In [17]: print('\nA '+too_expensive.title()+' is too expensive for me.')

A Ducati is too expensive for me.


2In [18]: cars=['bmw','audi','toyota','subaru']

In [19]: cars.sort()

In [20]: print(cars)
['audi', 'bmw', 'subaru', 'toyota']

In [21]: cars = ['bmw','audi','toyota','subaru']

In [22]: cars.sort(reverse=Ture)
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-22-8b43e828ed43> in <module>()
----> 1 cars.sort(reverse=Ture)

NameError: name 'Ture' is not defined

In [23]: cars.sort(reverse=True)

In [24]: print(cars)
['toyota', 'subaru', 'bmw', 'audi']

In [25]: cars = ['bmw','audi','toyota','subaru']

In [26]: print(cars)
['bmw', 'audi', 'toyota', 'subaru']

In [27]: print('\nHere is the sorted list:')

Here is the sorted list:

In [28]: print('\nHere is the original list again:')

Here is the original list again:

In [29]: print(sorted(cars))
['audi', 'bmw', 'subaru', 'toyota']

In [30]: print(cars)
['bmw', 'audi', 'toyota', 'subaru']

In [31]: cars = ['bmw','audi','toyota','subaru']

In [32]: print(cars)
['bmw', 'audi', 'toyota', 'subaru']

In [33]: cars.reverse()

In [34]: print(cars)
['subaru', 'toyota', 'audi', 'bmw']

In [35]: len(cars)
Out[35]: 4

3. 
In [36]: motorcycles = ['honda','yamaha','suzuki']

In [37]: print(motorcycles[3])
---------------------------------------------------------------------------
IndexError                                Traceback (most recent call last)
<ipython-input-37-0ae292d351b4> in <module>()
----> 1 print(motorcycles[3])

IndexError: list index out of range

4.
练习（1）
In [38]: names = ['lida','yuriya','vera','emma']

In [39]: print(names[0].title() + ', Welcome to my dinner!')
Lida, Welcome to my dinner!

In [40]: print(names[3].title() + "can't make it.")
Emmacan't make it.

In [41]: print(names[3].title() + " can't make it.")
Emma can't make it.

In [42]: names[3] = 'victoria'

In [43]: print(names)
['lida', 'yuriya', 'vera', 'victoria']

In [44]: print('I found a bigger dinner table!')
I found a bigger dinner table!

In [45]: names.insert.(0,'elizabeth')
  File "<ipython-input-45-7a6e992220f5>", line 1
    names.insert.(0,'elizabeth')
                 ^
SyntaxError: invalid syntax


In [46]: names.insert(0,'elizabeth')

In [47]: print(names)
['elizabeth', 'lida', 'yuriya', 'vera', 'victoria']

In [48]: names.insert(3,'bellah')

In [49]: print(names)
['elizabeth', 'lida', 'yuriya', 'bellah', 'vera', 'victoria']

In [50]: names.append('alek')

In [51]: print(names)
['elizabeth', 'lida', 'yuriya', 'bellah', 'vera', 'victoria', 'alek']

In [52]: print('Sorry! I can invite only two guests')
Sorry! I can invite only two guests

In [53]: popped_names = names.pop()

In [54]: print(names)
['elizabeth', 'lida', 'yuriya', 'bellah', 'vera', 'victoria']

In [55]: print('Sorry! '+ popped_names)
Sorry! alek

In [56]: popped_names = names.pop()

In [57]: print(names)
['elizabeth', 'lida', 'yuriya', 'bellah', 'vera']

In [58]: print('Sorry!' + poped_names)
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-58-761746b79ef2> in <module>()
----> 1 print('Sorry!' + poped_names)

NameError: name 'poped_names' is not defined

In [59]: print('Sorry!' + popped_names)
Sorry!victoria

In [60]: del names[-1]

In [61]: del names[-2]

In [62]: del names[-3]

In [63]: print(names)
['lida', 'bellah']

练习（2）
In [64]: places = ['Roma','Paris','Atlanda','New York','Budan']

In [65]: places.sorted()
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-65-0c611d34450f> in <module>()
----> 1 places.sorted()

AttributeError: 'list' object has no attribute 'sorted'

In [66]: print(sorted(places))
['Atlanda', 'Budan', 'New York', 'Paris', 'Roma']

In [67]: print(places)
['Roma', 'Paris', 'Atlanda', 'New York', 'Budan']

In [68]: places.sorted(reverse=Ture)
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-68-6fba50af9555> in <module>()
----> 1 places.sorted(reverse=Ture)

AttributeError: 'list' object has no attribute 'sorted'

In [69]: print(sorted(Places,reverse=True))
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-69-acb20a8ec1cb> in <module>()
----> 1 print(sorted(Places,reverse=True))

NameError: name 'Places' is not defined

In [70]: print(sorted(places,reverse=True))
['Roma', 'Paris', 'New York', 'Budan', 'Atlanda']

In [71]: print(places)
['Roma', 'Paris', 'Atlanda', 'New York', 'Budan']

In [72]: print(places.reverse())
None

In [73]: places.reverse()

In [74]: print(places)
['Roma', 'Paris', 'Atlanda', 'New York', 'Budan']

In [75]: places.reverse()

In [76]: print(places)
['Budan', 'New York', 'Atlanda', 'Paris', 'Roma']

In [77]: places.sort()

In [78]: print(places)
['Atlanda', 'Budan', 'New York', 'Paris', 'Roma']

In [79]: places.sort(reverse=True)

In [80]: print(places)
['Roma', 'Paris', 'New York', 'Budan', 'Atlanda']

In [81]: len(places)
Out[81]: 5


```

**错题集**

```python
1.
In [69]: print(sorted(Places,reverse=True))
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-69-acb20a8ec1cb> in <module>()
----> 1 print(sorted(Places,reverse=True))

NameError: name 'Places' is not defined
定义时'places'为小写，使用时大写


2.
In [65]: places.sorted()
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-65-0c611d34450f> in <module>()
----> 1 places.sorted()

AttributeError: 'list' object has no attribute 'sorted'

In [72]: print(places.reverse())
None
sored() 是一个function 与method的使用方式略有差异，应注意。


3.
In [56]: popped_names = names.pop()

In [57]: print(names)
['elizabeth', 'lida', 'yuriya', 'bellah', 'vera']

In [58]: print('Sorry!' + poped_names)
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-58-761746b79ef2> in <module>()
----> 1 print('Sorry!' + poped_names)
popped_names 使用时掉了一个p
NameError: name 'poped_names' is not defined
    
4.
In [45]: names.insert.(0,'elizabeth')
  File "<ipython-input-45-7a6e992220f5>", line 1
    names.insert.(0,'elizabeth')
                 ^
SyntaxError: invalid syntax

```

**问题集**

**What is an argument in programming?**

Sometimes abbreviated as arg, when referring to programming or the command line an argument is a value that is passed into a command, function, or routine. In the example below, "myfile.txt" is the argument for the edit command.

argument(actual parameter)指的是函数调用时的实际参数。（百度）