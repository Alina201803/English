### Chapter 16 Downloading Data

2018-07-02

**源代码**

```python
import csv

filename = 'sitka_weather_07-2014.csv'
#with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)
    print(header_row)


import csv
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    header_row = next(reader)

for index, colum_header in enumerate(header_row):
    print(index, colum_header)

```

**今日所学**

the csv file format

parsing the csv file headers

printing the headers and their positions



2018-07-03

**源代码**

```python
import csv

#Get high temperatures from file.
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    highs = []
    for row in reader:
        highs.append(row[1])

    print(highs)

import csv

#Get high temperatures from file.
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    highs = []
    for row in reader:
        high = int(row[1])
        highs.append(high)

    print(highs)
```

**今日所学**

extracting and reading data



2018-07-05

**源代码**

```python
     （1）ploting data in temperature chart

import csv

from matplotlib import pyplot as plt

#Get high temperatures from file.
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    highs = []
    for row in reader:
        high = int(row[1])
        highs.append(high)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(highs, c="red")

#Format plot
plt.title("Daily high temperatures, July 2014", fontsize=24)
plt.xlabel('', fontsize=16)
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

    (2)plotting dates
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high temperatures from file.
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs = [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red")

#Format plot
plt.title("Daily high temperatures, July 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.auto_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

Traceback (most recent call last):
  File "highs_low.py", line 14, in <module>
    current_date = datetime.strptime(row[0], "%y-%m-%d")
  File "D:\Anaconda\lib\_strptime.py", line 510, in _strptime_datetime
    tt, fraction = _strptime(data_string, format)
  File "D:\Anaconda\lib\_strptime.py", line 343, in _strptime
    (data_string, format))
ValueError: time data '2014/7/1' does not match format '%Y-%m-%d'

   
    (3) plotting a longer timeframe
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high temperatures from file.
filename = 'sitka_weather_2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs = [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red")

#Format plot
plt.title("Daily high temperatures - 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.autofmt_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

    （4）plotting a second data series
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high and low temperatures from file.
filename = 'sitka_weather_2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs, lows = [], [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

        low = int(row[3])
        lows.append(low)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red")
plt.plot(dates, lows, c="blue")

#Format plot
plt.title("Daily high and low temperatures - 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.autofmt_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

    （5）shading an area in the chart
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high and low temperatures from file.
filename = 'sitka_weather_2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs, lows = [], [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

        low = int(row[3])
        lows.append(low)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red", alpha=0.5)
plt.plot(dates, lows, c="blue", alpha=0.5)
plt.fill_between(dates, highs, lows, facecolor="blue", alpha=0.1)

#Format plot
plt.title("Daily high and low temperatures - 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.autofmt_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

```

**问题集**

1.不太理解 CSV module 中的 return（），书上解释为 return（），which returns the next line in the file when passed the reader object    Python 怎么知道下一行是哪一行 

header_row = next(reader)   是将 reader object 中的第一行存储到header_row中，然后下面的 for row in reader:  就只涉及数据的意思嘛.

**Answer:**

```python
#书里讲得不好, 
#Python 怎么知道下一行是哪一行?
#这个问题很棒,已经到达了Python最核心的知识点了. 
先看前面的知识点
class Dog():
     def __init__(self, name):
        self.name = name
     def __str__(self): #这里define a string
        return self.name
In [21]: dog = Dog("tiger")
In [22]: str(dog)
Out[22]: 'tiger'
#问题,为什么python的 str() 知道return 'tiger'呢,因为在Class Dog里 defined __str__

#同理,为什么python的next知道下一行呢,因为object reader里定义了 __next__
In [23]: dir(reader)
Out[23]: 
['__class__',
 '__delattr__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__lt__',
 '__ne__',
 '__new__',
 '__next__',  #在这里, 看我,看我
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'dialect',
 'line_num']

#然后再看看next()这个builtin function
In [26]: help(next)
Help on built-in function next in module builtins:
next(...)
    next(iterator[, default])
    
    Return the next item from the iterator. If default is given and the iterator
    is exhausted, it is returned instead of raising StopIteration.
    
#iterator
#说明reader的数据类型是iterator, python将CSV文件转换成了iterator这个数据类型.

#如何创建iterator object呢? 跟list(), tuple(), dict()一样
#用iter() Return an iterator object. 
help(iter)
Help on built-in function iter in module builtins:
iter(...)
    iter(iterable) -> iterator
    iter(callable, sentinel) -> iterator
    
    Get an iterator from an object.  In the first form, the argument must
    supply its own iterator, or be a sequence.
    In the second form, the callable is called until it returns the sentinel.
官方文档:
 [2. Built-in Functions — Python 3.7.0 documentation](https://docs.python.org/3/library/functions.html#iter)

                                                      
#创建一个iterator用next看看
In [29]: test_iterator = iter("test_iterator")
In [30]: next(test_iterator)
Out[30]: 't'
In [31]: next(test_iterator)
Out[31]: 'e'
In [32]: next(test_iterator)
Out[32]: 's'
In [33]: next(test_iterator)
Out[33]: 't'
#查看test_iterator的attributes和methods                                                   
In [34]: dir(test_iterator)
Out[34]: 
['__class__',
 '__delattr__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__iter__',  #iterator,我在这里,__iter__告诉python这是一个iterator, 
 '__le__',
 '__length_hint__',
 '__lt__',
 '__ne__',
 '__new__',
 '__next__',  #在这里
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__setstate__',
 '__sizeof__',
 '__str__',
 '__subclasshook__']
                                                      
#有next才能用for循环, for 循环就是不断地调用next.
python内置的list, tuple, dict可以直接用for循环或者slice切片,是因为他们的源代码用C语言写好了next.
那么,如果我们自己定义的Class, 也想用for循环或者切片,怎么办呢? 显然不能用C语言写,
python就很nice的提供了__iter__和__next__.
#查看list的属性
In [44]: l = list('list')
In [45]: dir(l)
Out[45]: 
['__add__',
....
 '__iter__', #我在这里
 '__le__',
 ....
]
#但是没有next, 因为是用C语言预先写在了里面..                                                    
In [46]: next(l)
TypeError: 'list' object is not an iterator
#这里的iterator是狭义的定义. 凡是能用for循环的都是iterator,python这样做,是为了将内置的list,tuple与其他自定义的iterator区分开来.
                                                      
这一点可以暂时不求甚解.
只要知道python是用__iter__和__next__这两个内置method定义iterator,
然后用next()调用__next__,for循环调用__next__就行. 不然,for循环他会静止在一个地方,不可能自动执行下一个.
def __next__(self):
#这里面实际写的是  i = i + 1,
   
                                                      
#总结,csv.reader(f)是将一个csv格式的文本转化成python的iterator object.
                                                   
```

[python - What exactly are iterator, iterable, and iteration? - Stack Overflow](https://stackoverflow.com/questions/9884132/what-exactly-are-iterator-iterable-and-iteration)



2.

```python 
(2)plotting dates
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high temperatures from file.
filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs = [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red")

#Format plot
plt.title("Daily high temperatures, July 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.auto_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

Traceback (most recent call last):
  File "highs_low.py", line 14, in <module>
    current_date = datetime.strptime(row[0], "%y-%m-%d")
  File "D:\Anaconda\lib\_strptime.py", line 510, in _strptime_datetime
    tt, fraction = _strptime(data_string, format)
  File "D:\Anaconda\lib\_strptime.py", line 343, in _strptime
    (data_string, format))
ValueError: time data '2014/7/1' does not match format '%Y-%m-%d'
 
current_date = datetime.strptime(row[0], "%Y-%m-%d") 
'2014/7/1' 与'%Y-%m-%d'不匹配  不明白怎么回事
源代码 (3) plotting a longer timeframe，（4）plotting a second data series 和（5）shading an area in the chart中同样的代码：current_date = datetime.strptime(row[0], "%Y-%m-%d") 并没有出现报错 难道是文件的问题
我把两个svc 文件也放入文件夹 
```



**Answer**

```python
current_date = datetime.strptime(row[0], "%Y-%m-%d") 
'2014/7/1' 与'%Y-%m-%d'不匹配  不明白怎么回事
'2014/7/1'的格式是'%Y/%m/%d' 以 /分割,

In [49]: date_str = '2014/7/1'
In [50]: current_date = datetime.strptime(date_str, '%Y/%m/%d')
In [51]: current_date
Out[51]: datetime.datetime(2014, 7, 1, 0, 0)
#另外/ - 等没有任何神奇的含义,就是普通的字符. 起作用的是% interpolation符号.

In [53]: datetime.strftime(current_date, "Year: %Y, Month: %m, a very special da
    ...: y: %d")
Out[53]: 'Year: 2014, Month: 07, a very special day: 01'
#如何将上面的这一段再转化回去呢, 怎样将日期都提取出来.
date_str = 'Year: 2014, Month: 07, a very special day: 01' 
date_format = "Year: %Y, Month: %m, a very special day: %d"
In [56]: current_date = datetime.strptime(date_str, date_format)
In [57]: current_date
Out[57]: datetime.datetime(2014, 7, 1, 0, 0)
In [58]: str(current_date)
Out[58]: '2014-07-01 00:00:00'
#%Y就是告诉python Year在哪里,%m告诉Month在哪里, %d告诉Day在哪里, 匹配找出来.
```





**今日所学**

ploting data in temperature chart

plotting dates

plotting a longer timeframe，

plotting a second data series 

shading an area in the chart



2018-07-06

**源代码**

```python
error-checking 
import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high and low temperatures from file.
filename = 'death_valley_2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs, lows = [], [], []
    for row in reader:
        current_date = datetime.strptime(row[0], "%Y-%m-%d")
        dates.append(current_date)

        high = int(row[1])
        highs.append(high)

        low = int(row[3])
        lows.append(low)

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red", alpha=0.5)
plt.plot(dates, lows, c="blue", alpha=0.5)
plt.fill_between(dates, highs, lows, facecolor="blue", alpha=0.1)

#Format plot
plt.title("Daily high and low temperatures - 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.autofmt_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

Traceback (most recent call last):
  File "2018-07-06.py", line 17, in <module>
    high = int(row[1])
ValueError: invalid literal for int() with base 10: ''


import csv
from datetime import datetime

from matplotlib import pyplot as plt

#Get dates and high and low temperatures from file.
filename = 'death_valley_2014.csv'
with open(filename) as f:
    reader = csv.reader(f)
    header_row = next(reader)

    dates, highs, lows = [], [], []
    for row in reader:
        try:
            current_date = datetime.strptime(row[0], "%Y-%m-%d")
            high = int(row[1])
            low = int(row[3])
        except ValueError:
            print(current_date, 'missing data')
        else:
            dates.append(current_date)
            highs.append(high)
            lows.append(low)
        

#plot data
fig = plt.figure(dpi = 128, figsize=(10, 6))
plt.plot(dates, highs, c="red", alpha=0.5)
plt.plot(dates, lows, c="blue", alpha=0.5)
plt.fill_between(dates, highs, lows, facecolor="blue", alpha=0.1)

#Format plot
plt.title("Daily high and low temperatures - 2014", fontsize=24)
plt.xlabel('', fontsize=16)
fig.autofmt_xdate()
plt.ylabel("Temperature (F)", fontsize=16)
plt.tick_params(axis='both', which='major', labelsize=16)

plt.show()

mapping global data sets : json format
extracting relevant data
import json

#Load the data into a list
filename = 'population_data.json'

with open(filename) as f:
    pop_data = json.load(f)

#Print the 2010 population for each country.
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = pop_dict["Value"]
        print(country_name + ": " + population)

converting strings into numerical values
import json

#Load the data into a list
filename = 'population_data.json'

with open(filename) as f:
    pop_data = json.load(f)

#Print the 2010 population for each country.
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(pop_dict["Value"])
        print(country_name + ": " + str(population))
Arab World: 357868000
Caribbean small states: 6880000
East Asia & Pacific (all income levels): 2201536674
East Asia & Pacific (developing only): 1961558757
Euro area: 331766000
Europe & Central Asia (all income levels): 890424544
Europe & Central Asia (developing only): 405204000
European Union: 502125000
Heavily indebted poor countries (HIPC): 635663000
Traceback (most recent call last):
  File "2018-07-06-1.py", line 13, in <module>
    population = int(pop_dict["Value"])
ValueError: invalid literal for int() with base 10: '1127437398.85751'


import json

#Load the data into a list
filename = 'population_data.json'

with open(filename) as f:
    pop_data = json.load(f)

#Print the 2010 population for each country.
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict["Value"]))
        print(country_name + ": " + str(population))
```

今日所学：

error-checking 

mapping global data sets : json format

extracting relevant data

converting strings into numerical values

 2018-07-07

**源代码**

```python
countries.py
from pygal.i18n import COUNTRIES

for country_code in sorted(COUNTRIES.keys()):
    print(country_code, COUNTRIES[country_code])

country_codes.py
from pygal_maps_world.i18n import COUNTRIES

def get_country_code(country_name):
    """Return the Pygal 2-digit country code for the given country."""
    for code, name in COUNTRIES.items():
        if name == country_name:
            return code
    # If the country wasn't found, return None.
    return None
print(get_country_code('Andorra'))
print(get_country_code('United Arab Emirates'))
print(get_country_code('Afghanistan'))

world_population.py
import json

from country_codes import get_country_code

#load the data into a list.
filename = 'population_data.json'
with open(filename) as f:
    pop_data = json.load(f)
#Print the 2010 population for each country.
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict['Value']))
        code = get_country_code(country_name)
        if code:
            print(code + ": " + str(population))
        else:
            print('ERROR - ' +country_name)

americas.py
import pygal.maps.world

wm = pygal.maps.world.World()
wm.title = 'North, Central, and South America'

wm.add('North America', ['ca', 'mx', 'us'])
wm.add('Central America', ['bz','cr','gt','hn','ni','pa','sv'])
wm.add('South America', ['ar','bo','br','cl','co','ec','gf','gy','pe','py','sr','uy','ve'])

wm.render_to_file('americas.svg')

na_populations.py
import pygal.maps.world

wm = pygal.maps.world.World()
wm.title = 'populations of Countries in North America'
wm.add('North America', {'ca': 34126000, 'us': 309349000, 'mx':113423000})

wm.render_to_file('na_population.svg')


import json

import pygal.maps.world

from country_codes import get_country_code
#load the data into a list.
filename = 'population_data.json'
with open(filename) as f:
    pop_data = json.load(f)
#Build a dictionary of population data.
cc_populations = {}
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict['Value']))
        code = get_country_code(country_name)
        if code:
            cc_populations[code] = population
wm = pygal.maps.world.World()
wm.title = 'World Population in 2010, by Country'
wm.add('2010', cc_populations)

wm.render_to_file('world_population.svg')
```

ImportError: No module named 'pygal.i18n'

AttributeError: module 'pygal' has no attribute 'Worldmap'

报错，解答：

本章用到`pygal.i18n`获取国别码, 现在pygal已经没有i18n模块，要改用`pygal_maps_world.i18n`，解决方法如下：

```
在终端中运行下面语句（注意pip3/pip）
pip install pygal_maps_world12
在代码文件中添加下面语句：
from pygal_maps_world.i18n import COUNTRIES

改为 import pygal.maps.world
wm = pygal.maps.world.World()
```

**今日所学**

obtaining two-digit country codes

building a world map

plotting numerical data on a world map

plotting a complete population map



2018-07-08

**源代码**

```python
import json

import pygal.maps.world

from country_codes import get_country_code
#load the data into a list.
filename = 'population_data.json'
with open(filename) as f:
    pop_data = json.load(f)
#Build a dictionary of population data.
cc_populations = {}
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict['Value']))
        code = get_country_code(country_name)
        if code:
            cc_populations[code] = population

#Group the countries into 3 population levels.
cc_pops_1, cc_pops_2, cc_pops_3 = {}, {}, {}
for cc, pop in cc_populations.items():
    if pop < 10000000:
        cc_pops_1[cc] = pop
    elif pop < 1000000000:
        cc_pops_2[cc] = pop
    else:
        cc_pops_3[cc] = pop

#See how many countries are in each level.
print(len(cc_pops_1), len(cc_pops_2), len(cc_pops_3))

wm = pygal.maps.world.World()
wm.title = 'World Population in 2010, by Country'
wm.add('0-10m', cc_pops_1)
wm.add('10m-1bn',cc_pops_2)
wm.add('>1bn',cc_pops_3)

wm.render_to_file('world_population.svg')

import json

import pygal.maps.world
from pygal.style import RotateStyle

from country_codes import get_country_code
#load the data into a list.
filename = 'population_data.json'
with open(filename) as f:
    pop_data = json.load(f)
#Build a dictionary of population data.
cc_populations = {}
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict['Value']))
        code = get_country_code(country_name)
        if code:
            cc_populations[code] = population

#Group the countries into 3 population levels.
cc_pops_1, cc_pops_2, cc_pops_3 = {}, {}, {}
for cc, pop in cc_populations.items():
    if pop < 10000000:
        cc_pops_1[cc] = pop
    elif pop < 1000000000:
        cc_pops_2[cc] = pop
    else:
        cc_pops_3[cc] = pop

#See how many countries are in each level.
print(len(cc_pops_1), len(cc_pops_2), len(cc_pops_3))

wm_style = RotateStyle('#336699')
wm = pygal.maps.world.World(style=wm_style)
wm.title = 'World Population in 2010, by Country'
wm.add('0-10m', cc_pops_1)
wm.add('10m-1bn',cc_pops_2)
wm.add('>1bn',cc_pops_3)

wm.render_to_file('world_population.svg')

import json

import pygal.maps.world
from pygal.style import RotateStyle
from pygal.style import LightColorizedStyle

from country_codes import get_country_code
#load the data into a list.
filename = 'population_data.json'
with open(filename) as f:
    pop_data = json.load(f)
#Build a dictionary of population data.
cc_populations = {}
for pop_dict in pop_data:
    if pop_dict['Year'] == '2010':
        country_name = pop_dict['Country Name']
        population = int(float(pop_dict['Value']))
        code = get_country_code(country_name)
        if code:
            cc_populations[code] = population

#Group the countries into 3 population levels.
cc_pops_1, cc_pops_2, cc_pops_3 = {}, {}, {}
for cc, pop in cc_populations.items():
    if pop < 10000000:
        cc_pops_1[cc] = pop
    elif pop < 1000000000:
        cc_pops_2[cc] = pop
    else:
        cc_pops_3[cc] = pop

#See how many countries are in each level.
print(len(cc_pops_1), len(cc_pops_2), len(cc_pops_3))

wm_style = RotateStyle('#336699', base_style=LightColorizedStyle)
wm = pygal.maps.world.World(style=wm_style)
wm.title = 'World Population in 2010, by Country'
wm.add('0-10m', cc_pops_1)
wm.add('10m-1bn',cc_pops_2)
wm.add('>1bn',cc_pops_3)

wm.render_to_file('1_world_population.svg')

```

**今日所学**

grouping countries by population

styling world maps in pygal

lighting the color theme



2018-07-09

**源代码**

```python
练习 16-6
from country_codes import get_country_code
import pygal.maps.world
import csv

#Get countries and GDP datas from file
filename = 'GDP.csv'
with open (filename, encoding='ISO-8859-1') as f:
    reader = csv.reader(f)
    header_row = next(reader)
    print(header_row)
    row_1 = next(reader)
    print(row_1)
    row_2 = next(reader)
    print(row_2)
    row_3 = next(reader)
    print(row_3)
    row_4 = next(reader)
    print(row_4)

#Build a dictionary of gdp data.
    country_gdp = {}
    for row in reader:
        gdp = row[4]
        country = row[3]
        code = get_country_code(country)
        if code:
            country_gdp[code] = gdp



wm = pygal.maps.world.World()
wm.title = 'GDP of countries in the world'
wm.add('GDP', country_gdp)

wm.render_to_file('gdp of countries in the world.svg')
练习 16-7
from country_codes import get_country_code
import pygal.maps.world
import csv

#Get countries and  datas from file
filename = 'API_AG.csv'
with open(filename, encoding='gb18030',errors='ignore') as f:
    reader = csv.reader(f)
    header_row = next(reader)
    print(header_row)
    row_1 = next(reader)
    print(row_1)
    row_2 = next(reader)
    print(row_2)
    row_3 = next(reader)
    print(row_3)
    row_4 = next(reader)
    print(row_4)
    row_5 = next(reader)
    print(row_5)
#Build a dictionary of  data.
    country_agricultural_land = {}
    for row in reader:
        land = row[6]
        country = row[0]
        code = get_country_code(country)
        if code:
           country_agricultural_land[code] = land

wm = pygal.maps.world.World()
wm.title = 'country_agricultural_land of countries in the world in 1961'
wm.add('1961', country_agricultural_land)

wm.render_to_file('country_agricultural_land of countries in the world.svg')
TypeError: unsupported operand type(s) for -: 'str' and 'str'
Traceback (most recent call last):
  File "test.py", line 34, in <module>
    wm.render_to_file('country_agricultural_land of countries in the world.svg')
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\public.py", line 114, in render_to_file
    f.write(self.render(is_unicode=True, **kwargs))
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\public.py", line 52, in render
    self.setup(**kwargs)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\base.py", line 217, in setup
    self._draw()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\graph.py", line 933, in _draw
    self._plot()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\map.py", line 83, in _plot
    ratio = .3 + .7 * (value - min_) / (max_ - min_)
TypeError: unsupported operand type(s) for -: 'str' and 'str'

练习 16-8
import unittest
from country_codes import get_country_code

class TestCountryCodes(unittest.TestCase):
    """针对get_country_codes的测试类"""
 
    def test_country_codes(self):
        country_name = 'Australia'
        code = get_country_code(country_name)
        self.assertEqual(code, 'au')

unittest.main()

```

**错题集**

```python
1.练习 16-6 16-7 引入文件时报错
UnicodeDecodeError: 'gbk' codec can't decode byte 0xbf in position 2: illegal multibyte sequence”
搜索给出解决方案：
with open (filename, encoding='ISO-8859-1') as f:  加上 encoding='ISO-8859-1'
2 运行 16-7 出现报错 没搜索到解决办法......
TypeError: unsupported operand type(s) for -: 'str' and 'str'
Traceback (most recent call last):
  File "test.py", line 34, in <module>
    wm.render_to_file('country_agricultural_land of countries in the world.svg')
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\public.py", line 114, in render_to_file
    f.write(self.render(is_unicode=True, **kwargs))
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\public.py", line 52, in render
    self.setup(**kwargs)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\base.py", line 217, in setup
    self._draw()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\graph.py", line 933, in _draw
    self._plot()
  File "C:\Users\Administrator\AppData\Roaming\Python\Python35\site-packages\pyg                                                                                                                al\graph\map.py", line 83, in _plot
    ratio = .3 + .7 * (value - min_) / (max_ - min_)
TypeError: unsupported operand type(s) for -: 'str' and 'str'

 
```

今日所学

练习（从网上下载数据，利用pygal使数据可视化）

练习做得很艰难，报错，搜索修改，有些自己改正了，但还是有错误.......



2018-07-10

**源代码**

```python
练习16-7
(1)
import csv
from country_codes import get_country_code
import pygal.maps.world

filename = 'API_AG.csv'
with open(filename, encoding='utf-8') as f:
    reader = csv.reader(f)
    header_row = next(reader)
    row_1 = next(reader)
    row_2 = next(reader)
    row_3 = next(reader)
    row_4 = next(reader)
    print(row_4)

   
    for row in reader:
        country_name = row[0]
        try:
            Agricultural_land = int(float(row[5]))
        except ValueError:
            print('MISSING DATA')
        else:
            data = {}
            code = get_country_code(country_name)
            data[code] = Agricultural_land
            print(data)
       

wm = pygal.maps.world.World()
wm.title = 'Agricultural_land of countries in the world'
wm.add('argu_land',data)
wm.render_to_file('Agricultural_land of countries in the world.svg')

(2)
import csv
from country_codes import get_country_code
import pygal.maps.world

filename = 'API_AG.csv'
with open(filename, encoding='utf-8') as f:
    reader = csv.reader(f)
    header_row = next(reader)
    row_1 = next(reader)
    row_2 = next(reader)
    row_3 = next(reader)
    row_4 = next(reader)
    print(row_4)

    data = {}
    for row in reader:
        country_name = row[0]
        try:
            Agricultural_land = int(float(row[5]))
        except ValueError:
            print('MISSING DATA')
        else:
            code = get_country_code(country_name)
            data[code] = Agricultural_land
            print(data)

wm = pygal.maps.world.World()
wm.title = 'Agricultural land (% of land area) in the world'
wm.add('argu_land',data)
wm.render_to_file('1_Agricultural_land of countries in the world.svg')

(3)
import csv
from country_codes import get_country_code
import pygal.maps.world

filename = 'API_AG.csv'
with open(filename, encoding='utf-8') as f:
    reader = csv.reader(f)
    header_row = next(reader)
    row_1 = next(reader)
    row_2 = next(reader)
    row_3 = next(reader)
    row_4 = next(reader)
    print(row_4)

    data = {}
    for row in reader:
        country_name = row[0]
        try:
            Agricultural_land = int(float(row[5]))
        except ValueError:
            print('MISSING DATA')
        else:
            code = get_country_code(country_name)
            data[code] = Agricultural_land
            print(data)

ar_land_10, ar_land_50 , ar_land_100 = {}, {}, {}
for co, Ag_land in datas.items():
    if  Ag_land < 10:
        ar_land_10[co] = Ag_land #ag_land
    elif Ag_land < 50:
        ar_land_50[co] = Ag_land #ag_land
    else:
        ar_land_100[co] = Ag_land #ag_land

wm = pygal.maps.world.World()
wm.title = 'Agricultural land (% of land area) in the world'
wm.add('0-10',  ar_land_10)
wm.add('10-50', ar_land_50)
wm.add('50-100', ar_land_100 )

wm.render_to_file('Agricultural land (% of land area) in the world.svg')


```

**错题集**

```python
(1)
import csv
from country_codes import get_country_code
import pygal.maps.world

filename = 'API_AG.csv'
#这里不必用utf-8,python默认便是用utf-8解析,
#with open(filename, encoding='utf-8') as f:
#修改后,解释见文末。
with open(filename, newline="") as f:
    reader = csv.reader(f)
    header_row = next(reader)
    row_1 = next(reader)
    row_2 = next(reader)
    row_3 = next(reader)
    row_4 = next(reader)
    print(row_4)

    #data = {} 
    for row in reader:
        country_name = row[0]
        try:
            Agricultural_land = int(float(row[5]))
            #agricultural_land = float(row[5])
            #这里是重复的, 
            #接Agricultural_land = float(row[5])
            #要么Agricultural_land = int(row[5])
            #Agricultural的首字母A,按规范,不推荐大写,只有自定义class的时候用大写.
            #agricultural_land
        except ValueError:
            print('MISSING DATA')
        else:
            data = {} #你说得对, data放在这里每次都会被清空,最后只留下一个数据.
            code = get_country_code(country_name)
            data[code] = Agricultural_land #agricultural_land
            print(data)
       

wm = pygal.maps.world.World()
wm.title = 'Agricultural_land of countries in the world'
wm.add('argu_land',data)
wm.render_to_file('Agricultural_land of countries in the world.svg')
今天把昨天的错误分析了一下，又看了一遍教材讲解，决定再做一遍习题16-7
这次Python没有报错，很开心。结果出来的visualization有问题，只显示一个国家（Agricultural_land of countries in the world.svg）
很不解，鼓捣半天不知道哪里错了，又读了一遍题目: generates a dictionary with Pygal's two_latter country codes as its keys and chosen data from data from the files as its values，
发现我创建的data{} 是一个一个孤立小字典,不是一个将数据囊括的大字典。print（data)的结果如下：
{None: 11}
{'af': 57}
{'ao': 45}
{'al': 44}
{'ad': 55}
   省略
{'us': 48}
MISSING DATA
{None: 44}
{'za': 83}
{'zm': 25}
{'zw': 28}
翻看教材明白明白是创建的data{}不正确。，找到原因 data{} 不应该放在for loop里。在（2）中改正之后，终于出来了完整的visualization(1_Agricultural_land of countries in the world.svg)。在（3）中将效果优化(Agricultural land (% of land area) in the world.svg)
```

**今日所学**

完成练习16-7 

对`csv`的使用,Python3的官方文档建议, 

If *csvfile* is a file object, it should be opened with `newline=''`.

[14.1. csv — CSV File Reading and Writing — Python 3.7.0 documentation](https://docs.python.org/3/library/csv.html)

This enables universal `newlines` mode, which allows the csv module to read and write new lines correctly for **all operating systesm**.































