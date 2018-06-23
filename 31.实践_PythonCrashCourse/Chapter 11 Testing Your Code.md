

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
      #  print(question) #书上这里是错误的.
        print(self.question) #attribute的调用,必须self.的方式.


    def store_response(self, new_response):
        """store a single reponse to the survey."""
        self.responses.append(new_response)

    def show_results(self):
        """show all the responses that have been given."""
        print("Survey results:")
   #    for response in responses: #书上这个地方也是错误的. responses的调用self.responses
        for response in self.responses
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


tests_survey.py
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
 TestAnonymousSurvey(unittest.TestCase):
    """Tests for the class AnonymousSurvey."""
    def setUp(self):
        """Creat a survey and a set of responses for use in all test methods"""
        question = "What language did you first learn to speak?"
        self.my_survey =  AnonymousSurvey(question)
        self.responses = ['English','Spanish','Mandarin']

    def test_store_single_response(self):
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
-----------------------
关于setUp()method 这篇代码看的我有些混乱 可能在学class是没有理解好self.......
我理解class中的 self 是对所创造实例的指代，也将类中的method和实例连接。
self.my_survey =  AnonymousSurvey(question) 在实例my_survey前还有一个self,有点搞不清楚
-------------------------------
关于setUp()method 这篇代码看的我有些混乱 可能在学class是没有理解好self.......
我理解class中的 self 是对所创造实例的指代，也将类中的method和实例连接。
#理解的完全正确, 
#class中的self是从这个class中创造的实例的指代.
TestAnonymousSurvey(unittest.TestCase):
    """Tests for the class AnonymousSurvey."""
    def setUp(self):
        """Creat a survey and a set of responses for use in all test methods"""
        question = "What language did you first learn to speak?"
        self.my_survey =  AnonymousSurvey(question)
        self.responses = ['English','Spanish','Mandarin']
#这里的self, 指的是从
Class TestAnonymousSurvey创造出来的实例 
TestAnonymousSurvey()
而非
AnonymousSurvey的实例     
        
self.my_survey =  AnonymousSurvey(question) 在实例my_survey前还有一个self,有点搞不清楚

my_survey是self的属性,属性可以是任何Object,可以是age,name,也可以是实例.
也就是说,一个实例可以是其他实例的属性.

#首先, setUp(self):这个method的作用;
在这个啰嗦的写法的测试中,
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

#实例my_survey = AnonymousSurvey(question)分别写在了
def test_store_single_response(self):和
def test_store_three_responses(self):中, 
#做了重复的工作,因此在重构的时候,考虑将两处的实例my_survey = AnonymousSurvey(question)合并到一处. 这是setUp()的作用, 在这里创建AnonymousSurvey(question)这个实例,供test_store_single_response(self)和test_store_three_responses(self)这两个method调用.


#然后再看, self.my_survey =  AnonymousSurvey(question), 你对self的理解完全正确.
但是,重新看看下面的代码:
这里的self是`TestAnonymousSurvey`的实例,测试匿名调查的实例,也就是说
self就是TestAnonymousSurvey()这个实例, 是一个不需要传入参数的实例
而my_survey是AnonymousSurvey(question)这个实例.

#看一下下面的代码:
class TestAnonymousSurvey(unittest.TestCase):
    """Tests for the class AnonymousSurvey."""
    def setUp(self):
        """Creat a survey and a set of responses for use in all test methods"""
        question = "What language did you first learn to speak?"
        self.my_survey =  AnonymousSurvey(question)
        self.responses = ['English','Spanish','Mandarin']

    def test_store_single_response(self):
        self.my_survey.store_response(self.responses[0])
        self.assertIn(self.responses[0], self.my_survey.responses)

    
    def test_store_three_responses(self):
    
        for response in self.responses:
            self.my_survey.store_response(response)

        for response in self.responses:
            self.assertIn(response, self.my_survey.responses)
 
#####接着聊
self.my_survey =  AnonymousSurvey(question)
这个写法相当于
TestAnonymousSurvey().my_survey =  AnonymousSurvey(question)
将实例AnonymousSurvey(question), 变成了
实例TestAnonymousSurvey()的一个属性, 

这样在
def test_store_single_response(self) 
def test_store_three_responses(self)
中才能直接调用    
self.my_survey =  AnonymousSurvey(question)

这跟第九章中的self.age, self.name是相同的.
不仅name(text文本), age(number)可以作为attribute
实例也可以作为attribute.
实际上在Python中因为,万物皆object,function,Instance等都可以作为attribute
class Dog():
    """A simple attempt to model a dog."""

    def __init__(self,name,age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age 

    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(self.name.title() + " is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(self.name.title() + " rolled over!")

#总结,你的理解没有错误,
#实例self可以有属性, 而实例本身又可以作为其他实例的属性.因为实例也是Object没有特殊之处.
            
```





**错题集**

```python
运行language_survey.py 时 出现报错，提示我没有定义question 和 responses 仔细检查之后，也没发现survey.py里的错误 不知道问题出哪里了....
#这里是教材中的错误,
#应该是self.question和self.responses
#真没想到教材里有这么低级的错误,也说明大家都在一个水平上,不存在高不可攀.
#相信自己的电脑和自己的判断.


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
  File "C:\Users\	Administrator\desktop\survey.py", line 38, in <module>
    my_survey.show_results()
  File "C:\Users\Administrator\desktop\survey.py", line 19, in show_results
    for response in responses:
NameError: name 'responses' is not defined


```



**问题:**

关于`setUp()method `这篇代码看的我有些混乱 可能在学`class`是没有理解好`self`.......
我理解class中的 self 是对所创造实例的指代，也将类中的`method`和实例连接。
`self.my_survey =  AnonymousSurvey(question) `在实例`my_survey`前还有一个`self`,有点搞不清楚



1. `self.my_survey =  AnonymousSurvey(question) `在实例`my_survey`前还有一个`self`,有点搞不清楚

    - 先只看左边: `self.my_survey =`

      与name在`self.name = "xiaoqiang"`和age在`self.age = 18` 相同, 

      `my_survey`是`self`的一个attribute,  `self.my_survery`, 就是`self.attribute`,并没有特殊之处

    - 不同之处是, self.name的value是文本字符串"小强", self.age的value是数字18

    - 而`self.my_survey =  AnonymousSurvey(question) ` 的value是一个实例. 实例可以作为属性,任何Object都可以作为属性, 在Python中万物皆Object.



2. 我理解class中的 self 是对所创造实例的指代，也将类中的`method`和实例连接。

   self 指代他所隶属的class中创造的实例, 

   这里self隶属的Class是`class TestAnonymousSurvey(unittest.TestCase):`

   ​







我上传了一本书, OReilly.Think.Python.2nd.Edition.2015.12

第18章的inheritance,是一扑克牌的案例,有时间看看.

另外class可以在不断地练习中慢慢掌握.





2018-06-23

**源代码**

```python
完成练习11-3
employee.py
class Employee():
    """A simple attempt to represent a employee."""

    def __init__(self, first_name, last_name, annual_salary):
        self.first_name = first_name
        self.last_name = last_name
        self.annual_salary = annual_salary
        print(self.first_name + self.last_name)
    def give_raise(self,raise_salary = 5000):
        self.annual_salary += raise_salary
        
testemployee.py
import unittest
from employee import Employee

class TestEmployee(unittest.TestCase):
    """Test for the class Employee"""
    
    def setUp(self):
        self.my_employee = Employee('James','Browm',0)
    def test_give_default_raise(self):  
        self.my_employee.give_raise()  
        self.assertEqual(self.my_employee.annual_salary() ,5000)  #去掉()
    def test_give_custom_raise(self):  
        self.my_employee.give_raise(8000)
        self.assertEqual(self.my_employee.annual_salary() ,8000)  
unittest.main()  
EE
======================================================================
ERROR: test_give_custom_raise (__main__.TestEmployee)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "testemployee.py", line 14, in test_give_custom_raise
    self.assertEqual(self.my_employee.annual_salary() ,8000)
TypeError: 'int' object is not callable

======================================================================
ERROR: test_give_default_raise (__main__.TestEmployee)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "testemployee.py", line 11, in test_give_default_raise
    self.assertEqual(self.my_employee.annual_salary() ,5000) 
TypeError: 'int' object is not callable

----------------------------------------------------------------------
Ran 2 tests in 0.010s

 
```



**错题集**

```python
EE
======================================================================
ERROR: test_give_custom_raise (__main__.TestEmployee)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "testemployee.py", line 14, in test_give_custom_raise
    self.assertEqual(self.my_employee.annual_salary() ,8000)
TypeError: 'int' object is not callable

======================================================================
ERROR: test_give_default_raise (__main__.TestEmployee)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "testemployee.py", line 11, in test_give_default_raise
    self.assertEqual(self.my_employee.annual_salary() ,5000)
TypeError: 'int' object is not callable

----------------------------------------------------------------------
Ran 2 tests in 0.010s


'int' object is not callable  int不能获取 没明白这个报错.....

#只有method和function才能call,
    def __init__(self, first_name, last_name, annual_salary):
        self.first_name = first_name
        self.last_name = last_name
        self.annual_salary = annual_salary
self.annual_salary, annual_salary是attribute,不是method,
因此 self.assertEqual(self.my_employee.annual_salary() ,8000) 应该去掉()
self.assertEqual(self.my_employee.annual_salary,8000)
```







2018-06-23

大致总结了一下最近所学。

![1](C:\Users\Administrator\Desktop\1.jpg)

![2](C:\Users\Administrator\Desktop\3.jpg)

![2](C:\Users\Administrator\Desktop\2.jpg)







You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to some- thing new.



