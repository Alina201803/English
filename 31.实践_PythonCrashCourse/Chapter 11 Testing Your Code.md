

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





2018-06-12

**源代码**

```python
survey.py
class AnonymousSurvey():
    """collect anonymous answers to a survey question."""

    def __init__(self, question):
        self.question = question
        self.responses = []

    def show_question(self):
        """show the survey question"""
        print(question)

    def store_response(self, new_response):
        """store a single reponse to the survey."""
        self.responses.append(new_response)

    def show_results(self):
        """show all the responses that have been given."""
        print("Survey results:")
        for response in responses:
            print('- ' + response)

            
language_survey.py
from survey import AnonymousSurvey

#Define a question, and make a survey.
question = "What language did you first learn to speak?"
my_survey = AnonymousSurvey(question)

#Show the question, and store responses to the question.
my_survey.show_question()
print("Enter 'q' at any time to quit.\n")
while True:
    response = input('Language: ')
    if response == 'q':
        break
    my_survey.store_response(response)

#Show the survey results.
print("\nThank you to everyone who participated in the survey!")
my_survey.show_results()


tests.py
import unittest
from survey import AnonymousSurvey

class TestAnonymousSurvey(unittest.TestCase):
    """Test that a single reponse is stored properly."""
    def test_store_single_response(self):
        question = "What language did you first learn to speak?"
        my_survey = AnonymousSurvey(question)
        my_survey.store_response('English')

        self.assertIn('English', my_survey.responses)

unittest.main()

.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK

import unittest
from survey import AnonymousSurvey

class TestAnonymousSurvey(unittest.TestCase):
    """Test that a single reponse is stored properly."""
    def test_store_single_response(self):
        question = "What language did you first learn to speak?"
        my_survey = AnonymousSurvey(question)
        my_survey.store_response('English')

        self.assertIn('English', my_survey.responses)
    
    def test_store_three_responses(self):
        question = "What language did you first learn to speak?"
        my_survey = AnonymousSurvey(question)
        responses = ['English','Spanish','Mandarin']
        for response in responses:
            my_survey.store_response(response)

        for response in responses:
            self.assertIn(response, my_survey.responses)


unittest.main()
..
----------------------------------------------------------------------
Ran 2 tests in 0.000s

OK

import unittest
from survey import AnonymousSurvey


The setUp() Method
class TestAnonymousSurvey(unittest.TestCase):
    """Tests for the class AnonymousSurvey."""
    def setUp(self):
        """Creat a survey and a set of responses for use in all test methods"""
        question = "What language did you first learn to speak?"
        self.my_survey =  AnonymousSurvey(question)
        self.responses = ['English','Spanish','Mandarin']

    def test_store_single_response(self):
        question = "What language did you first learn to speak?"
        self.my_survey.store_response(self.responses[0])
        self.assertIn(self.responses[0], self.my_survey.responses)

    
    def test_store_three_responses(self):
    
        for response in self.responses:
            self.my_survey.store_response(response)

        for response in self.responses:
            self.assertIn(response, self.my_survey.responses)


unittest.main()
..
----------------------------------------------------------------------
Ran 2 tests in 0.000s

OK

关于setUp()method 这篇代码看的我有些混乱 可能在学class是没有理解好self.......
我理解class中的 self 是对所创造实例的指代，也将类中的method和实例连接。
self.my_survey =  AnonymousSurvey(question) 在实例my_survey前还有一个self,有点搞不清楚
```



**错题集**

```python
运行language_survey.py 时 出现报错，提示我没有定义question 和 responses 仔细检查之后，也没发现survey.py里的错误 不知道问题出哪里了....


Traceback (most recent call last):
  File "language_survey.py", line 7, in <module>
    my_survey.show_question()
  File "C:\Users\Administrator\desktop\survey.py", line 10, in show_question
    print(question)
NameError: name 'question' is not defined
    
    
    
What language did you first learn to speak?
Enter 'q' at any time to quit.

Language: q

Thank you to everyone who participated in the survey!
Survey results:
Traceback (most recent call last):
  File "language_survey.py", line 1, in <module>
    from survey import AnonymousSurvey
  File "C:\Users\Administrator\desktop\survey.py", line 38, in <module>
    my_survey.show_results()
  File "C:\Users\Administrator\desktop\survey.py", line 19, in show_results
    for response in responses:
NameError: name 'responses' is not defined


```







You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to some- thing new.



