### Chapter 9 Classes

@Alina

**源代码**

```python
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

my_dog = Dog('willie',6)
my_dog.sit()
my_dog.roll_over()
#class的概念,无缝对接了现实世界和虚拟世界.
#这里的dog就完全抽象自现实世界,他有属性,有行为.属性是名字,行为是跑和跳.
#有了class,程序就像动物一样,活了起来.

print("My dog's name is " + my_dog.name.title() + '.')
print("My dog is " + str(my_dog.age) + " years old")

class Test:
   ...:     def __init__(self,name):
   ...:         self.name = name
   ...:         print("%s Welcome to python!" % self.name)

class Dog(object):    #可以加object也可以不加, 不加就是默认继承自Object.
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def sit(self):
        print(self.name.title()+" is now sitting");
    def roll_over(self):
        print(self.name.title()+" rolled over!");

mydog = Dog('w',6) #这个function,理解成榨汁机是一样的,传入参数,就活了,
                   #从dog这个概念,成为一条真实的狗.
print("My dog's name is "+ mydog.name.title()+" .")
print("My dog is "+str(mydog.age)+" years old!")

class Restaurant():
    def __init__(self, restaurant_name,cuisine_type):
        self.restaurant_name = restaurant_name  
        self.cuisine_type = cuisine_type
    def describe_restaurant(self):
        print(self.name.title() + " is a "+ self.type + " resturant.")
    def open_restaurant(self):
        print(self.name.title() + "is open ")


my = Restaurant('WTP','Chinese') 
my.describe_reataurant()
my.open_restaurant()

class Restaurant():  
 def __init__(self,restaurant_name,cuisine_type):  
    self.restaurant_name = restaurant_name  
    self.cuisine_type = cuisine_type  
 def describe_restaurant(self):  
     print(self.restaurant_name)  
     print(self.cuisine_type)  
 def open_restaurant(self):  
     print("This restaurant is open")  
one = Restaurant('Yun Shui Yao','chinese food')  
one.describe_restaurant()  
one.open_restaurant()  

In [4]: class Dog():
   ...:     """A simple attempt to model a dog."""
   ...:
   ...:     def __init__(self,name,age):
   ...:         """Initialize name and age attributes."""
   ...:         self.name = name
   ...:         self.age = age
   ...:
   ...:     def sit(self):
   ...:         """Simulate a dog sitting in response to a command."""
   ...:         print(self.name.title() + " is now sitting.")
   ...:
   ...:     def roll_over(self):
   ...:         """Simulate rolling over in response to a command."""
   ...:         print(self.name.title() + " rolled over!")
   ...:
   ...: my_dog = Dog('willie',6)
   ...: my_dog.sit()
   ...: my_dog.roll_over()
   ...:
Willie is now sitting.
Willie rolled over!
In [5]: class Dog():
   ...:     """A simple attempt to model a dog."""
   ...:
   ...:     def __init__(self,name,age):
   ...:         """Initialize name and age attributes."""
   ...:         self.name = name
   ...:         self.age = age
   ...:
   ...:     def sit(self):
   ...:         """Simulate a dog sitting in response to a command."""
   ...:         print(self.name.title() + " is now sitting.")
   ...:

In [6]:     def roll_over(self):
   ...:         """Simulate rolling over in response to a command."""
   ...:         print(self.name.title() + " rolled over!")
   ...:
   ...: my_dog = Dog('willie',6)
   ...: my_dog.sit()
   ...: my_dog.roll_over()
   ...:
Willie is now sitting.
---------------------------------------------------------------------------
AttributeError                            Traceback (most recent call last)
<ipython-input-6-9be2d0143d31> in <module>()
      5 my_dog = Dog('willie',6)
      6 my_dog.sit()
----> 7 my_dog.roll_over()
练习：
In [2]: class Restaurant():
   ...:  def __init__(self,restaurant_name,cuisine_type):
   ...:     self.restaurant_name = restaurant_name
   ...:     self.cuisine_type = cuisine_type
   ...:  def describe_restaurant(self):
   ...:      print(self.restaurant_name)
   ...:      print(self.cuisine_type)
   ...:  def open_restaurant(self):
   ...:      print("This restaurant is open")
   ...: one = Restaurant('Yun Shui Yao','chinese food')
   ...: one.describe_restaurant()
   ...: one.open_restaurant()
   ...:
Yun Shui Yao
chinese food
This restaurant is open

```

**错题集**

```python
object() takes no parameters
def __init__(self, restaurant_name,cuisine_type)
init两边 有两个下划线__
#1. init两边有下划线,是因为init是一个比较常见的单词,Python为了避免与程序员的常用命名冲突就加了两条下划线,只是为了避免冲突的一个命名规则,没有特殊的含义.
#另外,还有__str__, __repr__, 等等,都是为了避免与开发者自己的命名冲突.
#两条下划线默认作为python的专属命名.
#2. 关于object, 它是python的原子,所有的其他东西,都是从Object创建出来的.
#观察object的内部,可以看到全部都是__**__两条下划线.
#只是一个命名规则,没有特别之处.就跟有人姓王,有人姓李一样, 需要一个规格区分,谁是谁.见到双下划线就知道是Python自己的属性,也叫元属性, meta.
In [20]: dir(object)
Out[20]: 
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
 '__le__',
 '__lt__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__']

```

今日所学：

creating and using a class