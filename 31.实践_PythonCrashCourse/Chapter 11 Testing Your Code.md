

## Chapter 11: Testing Your Code

### Alina

2018-06-19

```python
def get_formatted_name(first,last):
    """Generate a neatly formatted full name."""
    full_name = first + ' ' + last
    return full_name.title()

import unittest
from name_function import get_formatted_name

class NamesTestCase(unittest.TestCase):
    """Tests for 'name_function.py'."""

    def test_first_last_name(self):
        """Do names like 'Janis Joplin' work?"""
        formatted_name = get_formatted_name('janis','joplin')
        self.assertEqual(formatted_name,'Janis Joplin')

unittest.main()

.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK



def get_formatted_name(first, middle, last):
    """Generate a neatly formatted full name."""
    full_name = first + ' ' + middle + ' ' + last
    return full_name.title()

import unittest
from name_function import get_formatted_name

class NamesTestCase(unittest.TestCase):
    """Tests for 'name_function.py'."""

    def test_first_last_name(self):
        """Do names like 'Janis Joplin' work?"""
        formatted_name = get_formatted_name('janis','joplin')
        self.assertEqual(formatted_name,'Janis Joplin')

unittest.main()

E
======================================================================
ERROR: test_first_last_name (__main__.NamesTestCase)
Do names like 'Janis Joplin' work?
----------------------------------------------------------------------
Traceback (most recent call last):
  File "2018-06-19-1.py", line 9, in test_first_last_name
    formatted_name = get_formatted_name('janis','joplin')
TypeError: get_formatted_name() missing 1 required positional argument: 'last'

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (errors=1)


def get_formatted_name(first, last, middle=''):
    """Generate a neatly formatted full name."""
    if middle:
        full_name = first + ' ' + middle + ' ' + last
    else:
        full_name = first + ' ' + last
    return full_name.title()

import unittest
from name_function import get_formatted_name

class NamesTestCase(unittest.TestCase):
    """Tests for 'name_function.py'."""

    def test_first_last_name(self):
        """Do names like 'Janis Joplin' work?"""
        formatted_name = get_formatted_name('janis','joplin')
        self.assertEqual(formatted_name,'Janis Joplin')

unittest.main()

.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK


import unittest
from name_function import get_formatted_name

class NamesTestCase(unittest.TestCase):
    """Tests for 'name_function.py'."""

    def test_first_last_name(self):
        """Do names like 'Janis Joplin' work?"""
        formatted_name = get_formatted_name('janis','joplin')
        self.assertEqual(formatted_name,'Janis Joplin') 
    
    def test_first_last_middle_name(self):
        """Do names like 'Wolfgang Adadeus Mozart' work?"""
        formatted_name = get_formatted_name(
            'wolfgang','mozart','amadeus')
        self.assertEqual(formatted_name,'Wolfgang Amadeus Mozart')

unittest.main()

..
----------------------------------------------------------------------
Ran 2 tests in 0.010s

OK
```

今日所学：

Testing a Function

Unit Tests and Test Cases

A passing Test, A falling Test

Resonding to a Falied Test

Adding New Tests





2018-06-20

**源代码**

```python
练习11-1
def city_country(city, country):
    city_describe = city + ' ' + country
    return city_describe.title()
import unittest
from city_functions import city_country

class CityTestCase(unittest.TestCase):
    """Tests for 'city_functions.py'."""

    def test_city_country(self):
        """Do like 'chicago, America' work?"""
        full_name = city_country('chicago','america')
        self.assertEqual(full_name,'Chicago America')

unittest.main()
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

11-2(1)
def city_country(city, country, population):
    city_describe = city + ' ' + country + '-' + population
    return city_describe.title()

import unittest
from city_functions import city_country

class CityTestCase(unittest.TestCase):
    """Tests for 'city_functions.py'."""

    def test_city_country(self):
        """Do like 'chicago, America' work?"""
        full_name = city_country('chicago','america')
        self.assertEqual(full_name,'Chicago America')

unittest.main()

E
======================================================================
ERROR: test_city_country (__main__.CityTestCase)
Do like 'chicago, America' work?
----------------------------------------------------------------------
Traceback (most recent call last):
  File "test_cities.py", line 9, in test_city_country
    full_name = city_country('chicago','america')
TypeError: city_country() missing 1 required positional argument: 'population'

----------------------------------------------------------------------
Ran 1 test in 0.000s

FAILED (errors=1)

11-2(2)
def city_country(city, country, population=''):
    if population:
        city_describe = city + ' ' + country + ' - population ' + population
    else:
        city_describe = city + ' ' + country
    return city_describe.title()

import unittest
from city_functions import city_country

class CityTestCase(unittest.TestCase):
    """Tests for 'city_functions.py'."""

    def test_city_country(self):
        """Do like 'chicago, America' work?"""
        full_name = city_country('chicago','america')
        self.assertEqual(full_name,'Chicago America')

unittest.main()

.
----------------------------------------------------------------------
Ran 1 test in 0.000s
OK

11-2(3)
def city_country(city, country, population=''):
    if population:
        city_describe = city + ' ' + country + ' - population ' + str(population)
    else:
        city_describe = city + ' ' + country
    return city_describe.title()

import unittest
from city_functions import city_country

class CityTestCase(unittest.TestCase):
    """Tests for 'city_functions.py'."""

    def test_city_country(self):
        """Do string like 'Chicago, America' work?"""
        full_city = city_country('chicago','america')
        self.assertEqual(full_city,'Chicago America')
    def test_city_country_population(self):
        """Do string like 'Chicago America - Population 5000000'work?"""
        full_city = city_country('chicago','america','5000000')
        self.assertEqual(full_city,'Chicago America - Population 5000000')

unittest.main()
..
----------------------------------------------------------------------
Ran 2 tests in 0.000s

OK

```

**错题集**

```python
.F
======================================================================
FAIL: test_city_country_population (__main__.CityTestCase)
Do string like 'Chicago America - population 5000000'work?
----------------------------------------------------------------------
Traceback (most recent call last):
  File "test_cities.py", line 14, in test_city_country_population
    self.assertEqual(full_city,'Chicago America - population 5000000')
AssertionError: 'Chicago America - Population 5000000' != 'Chicago America - population 5000000'
- Chicago America - Population 5000000
?                   ^
+ Chicago America - population 5000000
?                   ^


----------------------------------------------------------------------
Ran 2 tests in 0.000s

FAILED (failures=1)

self.assertEqual(full_city,) 中，后面写入希望得到的结果要和full_city中存储的一致 将population开头字母大学即可。

代码短再专门写一个检测代码的tests有些麻烦
可能以后代码长了会体会到写testS的好处 哈哈
#是这样的,因此Test会放到最后.
#就如,刚买了一个周的自行车,有人非要教我怎样检查车胎是不是漏气,车辐条是不是绷直一样.

Test的好处是,当有大段的代码的时候,有测试就证明是安全可靠的.
便可以安心的躺在上面休息.
```



You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to some- thing new.



