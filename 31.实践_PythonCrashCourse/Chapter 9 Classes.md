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


print("My dog's name is " + my_dog.name.title() + '.')
print("My dog is " + str(my_dog.age) + " years old")

class Test:
   ...:     def __init__(self,name):
   ...:         self.name = name
   ...:         print("%s Welcome to python!" % self.name)

class Dog(object):    #可以加object也可以不加
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def sit(self):
        print(self.name.title()+" is now sitting");
    def roll_over(self):
        print(self.name.title()+" rolled over!");

mydog = Dog('w',6)
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
```

今日所学：

creating and using a class