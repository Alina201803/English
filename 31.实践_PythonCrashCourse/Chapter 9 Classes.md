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



2018-06-07

**源代码**

```python
###modifying an Attribute's Value Directly
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")

my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name())
my_new_car.odometer_reading = 23
my_new_car.read_odometer()
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")

my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name()
my_new_car.read_odometer()
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")

    def update_odometer(self,mileage):
        """Set the odometer reading to the given value."""
        self.odometer_reading = mileage

my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name())
my_new_car.update_odometer(23)
my_new_car.read_odometer()
###modifying an Attribute's value Through a Method.
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 25
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")

    def update_odometer(self,mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
        

my_new_car = Car('audi', 'a4', 2016)
print(my_new_car.get_descriptive_name())
my_new_car.update_odometer(23)
my_new_car.read_odometer()
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 25
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")
    def update_odometer(self,mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")        
    def increment_odometer(self,miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

my_used_car = Car('subaru','outback',2013)
print(my_used_car.get_descriptive_name())
my_used_car.update_odometer(23500)
my_used_car.read_odometer()
my_used_car.increment_odometer(100)
my_used_car.read_odometer()
练习：
9-4
class Restaurant():
    def __init__(self,restaurant_name,cuisine_type)
        """Initialize attributes to describe a restaurant"""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type

    def describe_restaurant(self):
        print(self.restaurant_name + ' ' + self.cuisine_type)

    def open_restaurant(self):
        print("The restaurant are open: " + self.restaurant_name)

one = Restaurant('huangjihuang','chinese food')
one.describe_restaurant()
one.open_restaurant()
      
class Restaurant():
    def __init__(self,restaurant_name,cuisine_type):
        """Initialize attributes to describe a restaurant"""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0
    def describe_restaurant(self):
        print(self.restaurant_name + ' provides ' + self.cuisine_type)

    def open_restaurant(self):
        print("The restaurant are open: " + self.restaurant_name)
    def restaurant_number(self):
        print("The restaurant has served " + str(self.number_served) + " people.")
    def set_number_served(self,number):
        self.number_served = number
    def increment_number(self,figure):
        self.number_served += figure
        

restaurant = Restaurant('huangjihuang','chinese food')
restaurant.set_number_served(55)
restaurant.increment_number(25)
restaurant.describe_restaurant()
restaurant.open_restaurant()
restaurant.restaurant_number()
```

**错题集**

```python
class Restaurant():
    def __init__(self,restaurant_name,cuisine_type):
        """Initialize attributes to describe a restaurant"""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type
        self.number_served = 0
    def describe_restaurant(self):
        print(self.restaurant_name + ' provides ' + self.cuisine_type)

    def open_restaurant(self):
        print("The restaurant are open: " + self.restaurant_name)
    def restaurant_number(self):
        print("The restaurant has served " + str(self.number_served) + " people.")
    def set_number_served(self,number):
        self.number_served = number
    def increment_number(self,figure):
        self.number_served += figure
#错误       
restaurant = Restaurant('huangjihuang','chinese food')
restaurant.describe_restaurant()
restaurant.open_restaurant()
restaurant.restaurant_number()
restaurant.set_number_served(55)
huangjihuang provides chinese food
The restaurant are open: huangjihuang
The restaurant has served 0 people.
#正确
restaurant = Restaurant('huangjihuang','chinese food')
restaurant.set_number_served(55)
restaurant.describe_restaurant()
restaurant.open_restaurant()
restaurant.restaurant_number()
huangjihuang provides chinese food
The restaurant are open: huangjihuang
The restaurant has served 55 people.
注意 restaurant.set_number_served(55) 放到正确的位置，放到调用self.number_served = 0之后，不起作用。
#因为def set_number_served(self,number):这个method的功能就是重置, 
#self.number_served, 的默认值设置为零,所以在输入的class的输入中没有number_served这个参数,self,restaurant_name,cuisine_type,
#这个练习的目的是让人清楚,可以把参数一次性弄好,同时也可以在后面调整.

#比如dog的例子
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
In [5]: my_dog
Out[5]: <__main__.Dog at 0x11008a1d0>
In [6]: vars(my_dog)
Out[6]: {'name': 'willie', 'age': 6}
#它今年6岁,明年就七岁了,
#如果只有一只宠物狗,可以修改年龄
In [7]: my_dog.age = 7
In [8]: vars(my_dog) #查看my_dog的内容.
Out[8]: {'name': 'willie', 'age': 7}
#如果是养殖场,这么一个一个的修改会累死人,因此在定义的是时候就价格reset_age的method
class Dog():
    """A simple attempt to model a dog."""

    def __init__(self,name,age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age 
    def reset_age(self,new_age):
        self.age = new_age
    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(self.name.title() + " is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(self.name.title() + " rolled over!")
#class Dog被重新改写了, 需要重新复制到ipython中,不然,他执行的还是原来的Dog      
In [10]:  my_dog = Dog('willie',6)
In [11]: vars(my_dog)
Out[11]: {'name': 'willie', 'age': 6}
In [12]: my_dog.reset_age(7)
In [13]: vars(my_dog)
Out[13]: {'name': 'willie', 'age': 7}
#这样做的好处是什么呢? 加入我有3条狗,
dog1 = Dog('tiger','6')
dog2 = Dog('lion','6')
dog3 = Dog('cat','6')
#我就可以用for循环来修改他们的年龄
for dog in [dog1, dog2, dog3]:
    dog.reset_age(7)
#查看是否修改成功
In [21]: for dog in [dog1, dog2, dog3]:
    ...:     print(vars(dog))
    ...:     
{'name': 'tiger', 'age': 7}
{'name': 'lion', 'age': 7}
{'name': 'cat', 'age': 7}
#当然这个方法,并不适用,不一定所有的狗都是7岁.那就重新定义一个增长一岁method
class Dog():
    """A simple attempt to model a dog."""

    def __init__(self,name,age):
        """Initialize name and age attributes."""
        self.name = name
        self.age = age
        
    def reset_age(self,new_age):
        self.age = new_ags
        
    def increase_ages(self, ages): #定义了新的方法
        self.age = self.age + ages
        
    def sit(self):
        """Simulate a dog sitting in response to a command."""
        print(self.name.title() + " is now sitting.")

    def roll_over(self):
        """Simulate rolling over in response to a command."""
        print(self.name.title() + " rolled over!")
#这段代码重新复制到ipython中
#instanciate my dog, 
my_dog = Dog('willie',6)
In [23]: my_dog.name
Out[23]: 'willie'
#最为Class和Object(instance),与function的不同就是,传入参数后,我们还可以取出来,为我所用
In [24]: my_dog.age
Out[24]: 6
In [25]: my_dog.age * 100
Out[25]: 600
#修改age
my_dog.increase_ages(1)
In [29]: my_dog.increase_ages(1)
In [30]: vars(my_dog)
Out[30]: {'name': 'willie', 'age': 7}
In [31]: my_dog.increase_ages(2
In [32]: vars(my_dog)
Out[32]: {'name': 'willie', 'age': 9}
In [33]: my_dog.age
Out[33]: 9
#你厌烦了不断去修改Dog, 而且在ipython中,我已经执行了Dog, 只能从别的地方修改好,再黏贴回来, 没有办法在ipython中直接修改class Dog, 就如过去的时间一样,永远触碰不到.
#怎么办? 定义一个新的狗 类
class NewDog(Dog):
    def rename(self, new_name):
        self.name = new_name
In [34]: my_dog = NewDog('willie',6)
In [37]: my_dog.rename("Kitty")
AttributeError: 'Dog' object has no attribute 'rename'                         
#当然可以直接修改名字
In [38]: my_dog.name = "SanMao"
Out[38]: {'name': 'SanMao', 'age': 6}
#但这样的手工操作,不适用大量的任务.
In [39]: class NewDog(Dog):
    ...:     def rename(self, new_name):
    ...:         self.name = new_name
    ...:         

In [40]: my_dog = NewDog('willie',6)
In [41]: my_dog.rename("Kitty")
In [42]: my_dog.name
Out[42]: 'Kitty'
                              
                              
#这就是inheritance(继承), NewDog继承了Dog的所有财产,然后自己再加点新花样.(本质就是省略了不断地黏贴和复制原来的代码)
Dog(object):#Dog继承了Object, 可以省略是因为Python里的任何一草一木都继承自Object. 包括list, tuple,dict, function,class等等.这些都是Python事先写好的工具. 当然我们也可以自己写. 就是
class List: 写一堆代码
            
In [46]: list("text") #list是一个系统定义好的类,不是function
Out[46]: ['t', 'e', 'x', 't']
#如果我们自己写的话,就是 List('text')                            
```

**今日所学**

set a default for an attribute

modify attribute values : directly, through a method()

increnment an attribute through a method 

2018-06-09

**源代码**

```python
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")
    def update_odometer(self,mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")        
    def increment_odometer(self,miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class ElectricCar(Car):
    """Represent aspects of a car, specific to electric vehicles."""
    def  __init__(self, make, model, year):
        """Initialize attributes of the parent class."""
        super().__init__(make, model,year)
        self.battery_size = 70

    def describe_battery(self):
        print("This car has a " + str(self.battery_size) + "-kwh battery.")

my_tesla = ElectricCar('tesla','model s',2016)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()

class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
        self.fill_gas_tank = 100
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")
    def update_odometer(self,mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")        
    def increment_odometer(self,miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles
    


class ElectricCar(Car):
    """Represent aspects of a car, specific to electric vehicles."""
    def  __init__(self, make, model, year):
        """Initialize attributes of the parent class."""
        super().__init__(make, model,year)
        self.battery_size = 70

    def describe_battery(self):
        print("This car has a " + str(self.battery_size) + "-kwh battery.")
    

my_tesla = ElectricCar('tesla','model s',2016)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()
```

**错题集**

```python
class Car():
    """A simple attempt to repersent a car."""

    def __init__(self, make, model, year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name."""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()
    def read_odometer(self):
        """Print a statement showing the car's mileage."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")
    def update_odometer(self,mileage):
        """
        Set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")        
    def increment_odometer(self,miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

class ElectricCar():
    """Represent aspects of a car, specific to electric vehicles."""
    def  __init__(self, make, model, year):
        """Initialize attributes of the parent class."""
        super().__init__(make, model,year)
        self.battery_size = 70

    def describe_battery(self):
        print("This car has a " + str(self.battery_size) + "-kwh battery.")

my_tesla = ElectricCar('tesla','model s',2016)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()
这个错误卡了很长时间，试了好多次才发现，新定义的class ElectricCar(): 没有填入Car, 看来不能太晚学编程，脑子不清楚.....
#卡了很长时间才发现错误,虽然煎熬,but很有价值,这样才能深入的理解.
#inheritance很比较多的作用,其中的第一点,可以简单理解为,省去了繁琐的复制黏贴.只需要把parent class "Car", 复制到child class ElectricCar()中,而不需要复制其中的大段代码.

```

今日所学：

inheritance

the __init()method for a child class

defining attribute and methods for the child class



2018-06-09

**源代码**

```python
9-3
class Users():
    def __init__(self,first_name,last_name,location):
        self.first_name = first_name.title()
        self.last_name = last_name.title()
        self.location = location.title()

    def describe_users(self):
       """summarize the user's information"""
       print(self.first_name + ' ' + 
            self.last_name + " lives in " +
            self.location)

    def greet_users(self):
        print("Hello," +
            self.first_name + ' ' + 
            self.last_name)

user = Users('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
9-6
class Restaurant():
    def __init__(self,restaurant_name,cuisine_type):
        """Initialize attributes to describe a restaurant"""
        self.restaurant_name = restaurant_name
        self.cuisine_type = cuisine_type

    def describe_restaurant(self):
        print(self.restaurant_name + ' ' + self.cuisine_type)

    def open_restaurant(self):
        print("The restaurant are open: " + self.restaurant_name)


class IcecreamStand(Restaurant):
    def __init__(self,restaurant_name,cuisine_type,flavors =
                ['chocolate','strawberry','green tea']):
        super().__init__(restaurant_name,cuisine_type)
        self.flavors = flavors
    def show_flavors(self):
        for f in self.flavors:
            print(f)

stand = IcecreamStand('good time','icecream')
print('flavors are:')
stand.show_flavors()
stand.describe_restaurant()
stand.open_restaurant()
9-7
class Users():
    def __init__(self,first_name,last_name,location):
        self.first_name = first_name.title()
        self.last_name = last_name.title()
        self.location = location.title()

    def describe_users(self):
       """summarize the user's information"""
       print(self.first_name + ' ' + 
            self.last_name + " lives in " +
            self.location)

    def greet_users(self):
        print("Hello," +
            self.first_name + ' ' + 
            self.last_name)

class Admin(Users):
    def __init__(self,first_name,last_name):
        super.__init__(self,first_name,last_name)
        self.privilieges = ['can add post','can delete post','can ban user']
    def show_privilieges():
        print(self.privilieges)
        

user = Users('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
user.show_privilieges()

class Users():
    def __init__(self,first_name,last_name,location):
        self.first_name = first_name.title()
        self.last_name = last_name.title()
        self.location = location.title()

    def describe_users(self):
       """summarize the user's information"""
       print(self.first_name + ' ' + 
            self.last_name + " lives in " +
            self.location)

    def greet_users(self):
        print("Hello," +
            self.first_name + ' ' + 
            self.last_name)

class Admin(Users):
    def __init__(self,first_name,last_name,location,privilieges):
        super().__init__(first_name,last_name,location)
        self.privilieges = [can add post','can delete post','can ban user']
    def show_privilieges(self):
        print(self.privilieges)
        

user = Admin('adam','cliton','Amarica','can add post')
user.describe_users()
user.greet_users()
user.show_privilieges()
9-8
class Users():
    def __init__(self,first_name,last_name,location):
        self.first_name = first_name.title()
        self.last_name = last_name.title()
        self.location = location.title()

    def describe_users(self):
       """summarize the user's information"""
       print(self.first_name + ' ' + 
            self.last_name + " lives in " +
            self.location)

    def greet_users(self):
        print("Hello," +
            self.first_name + ' ' + 
            self.last_name)

class Privilieges():
    def __init__(self,privilieges = ['can add post','can delete post','can ban user']):
        self.privilieges = privilieges
    def show_privilieges(self):
        for p in self.privilieges:
            print("\nThe admin's prinilieges is: " + p)

class Admin(Users):
    def __init__(self,first_name,last_name,location):
        super().__init__(first_name,last_name,location)
        self.privilieges = Privilieges()
    
        

user = Admin('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
user.privilieges.show_privilieges()


```

今日所学：

instances as attributes

练习9-3 9-6 9-7 9-8



2018-06-10

**源代码**

```python
car.py
"""A class that can be used to represent a car."""
class Car():
    """A simple attempt to represent a car"""

    def __init__(self,make,model,year):
        """Initialize attributes to describe a car."""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0 
    def get_descriptive_name(self):
        """Return a neatly formatted descriptive name"""
        long_name = str(self.year) + ' ' + self.make + ' ' + self.model
        return long_name.title()

    def read_odometer(self):
        """Print a statement showing the car's milege."""
        print("This car has " + str(self.odometer_reading) + " miles on it.")
        
    def update_odometer(self,mileage):
        """
        set the odometer reading to the given value.
        Reject the change if it attempts to roll the odometer back.
        """
        if mileage >=self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self,miles):
        """Add the given amount to the odometer reading."""
        self.odometer_reading += miles

        
electric_car.py
"""A set of classes that can be used to represent electric cars."""

from car import Car

class Battery():
    """A simple attempt to model a battery for an electric car."""

    def __init__(self,battery_size = 70):
        """Initialize the battery's attributes."""
        self.battery_size = battery_size
    
    def describe_battery(self):
        """Print a statement describing the battery size."""
        print("This car has a " + str(self.battery_size) + "-KWH battery.")

    def get_range(self):
        """Print a statement about the range this battery provides."""
        if self.battery_size == 70:
            range = 240
        elif self.battery_size == 85:
            range = 270
        message = "This car can go approximately " + str(range)
        message += " miles on a full charge."
        print(message)

class ElectricCar(Car):
    """Models aspects of a car, specific to electric vehicles."""

    def __init__(self,make,model,year):
        """
        Initialize attributes of the parent class
        Then initialize attributes specific to an electric car.
        """
        super().__init__(make,model,year)
        self.battery = Battery()
 
my_electric_car.py
from car import ElectricCar

my_tesla = ElectricCar('tesla','modle s', 2016)

print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()
my_tesla.battery.get_range()

my_car.py
from car import Car

my_new_car = Car('audi','a4',2016)
print(my_new_car.get_descriptive_name())

my_new_car.odometer_reading = 23
my_new_car.read_odometer()

my_cars.py
from car import Car
from electric_car import ElectricCar


my_beetle = Car('volkswagen','beetle',2016)
print(my_beetle.get_descriptive_name())

my_tesla = ElectricCar('tesla','roadster',2016)
print(my_tesla.get_descriptive_name())

练习9-12
user.py
class Users():
    def __init__(self,first_name,last_name,location):
        self.first_name = first_name.title()
        self.last_name = last_name.title()
        self.location = location.title()

    def describe_users(self):
       """summarize the user's information"""
       print(self.first_name + ' ' + 
            self.last_name + " lives in " +
            self.location)

    def greet_users(self):
        print("Hello," +
            self.first_name + ' ' + 
            self.last_name)
privileges.py
from user import Users

class Privilieges():
    def __init__(self,privilieges = ['can add post','can delete post','can ban user']):
        self.privilieges = privilieges
    def show_privilieges(self):
        for p in self.privilieges:
            print("\nThe admin's prinilieges is: " + p)
class Admin(Users):
    def __init__(self,first_name,last_name,location):
        super().__init__(first_name,last_name,location)
        self.privilieges = Privilieges()
        
 instance.py  
import privileges

import privileges

user = privileges.Admin('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
user.privilieges.show_privilieges()

```

**错题集**

```python
import privileges
错误
user = Admin('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
user.privilieges.show_privilieges()
改为
user = privileges.Admin('adam','cliton','Amarica')
user.describe_users()
user.greet_users()
user.privilieges.show_privilieges()

import entire module之后 在创建实例时需要module的名字 module_name.calss_name.
import calss 时不需要 因为from module_name import class.name语句 已经指明使用哪个class
```

今日所学

importing classes

a single class,  multiple classes, entire module

import a module into  a module



2016-06-11

**源代码**

```python
from collecctions import OrderedDict

favorite_languages = OrderedDict()

favorite_languages['jen'] = 'python'
favorite_languages['sarah'] = 'c'
favorite_languages['edward'] = 'ruby'
favorite_languages['phil'] = 'python'

for name,langugae in favorite_languages.items():
    print(name.title() + "'s favorite language is " + 
        language.title() + ".")
        

 练习
9-14
class Die():
    def __init__(self,sides= 6):
        self.sides = sides

    def roll_die(self):
        x = randint(1, self.sides)
        print(x)
    def update_sides(self,sides= 10):
        self.sides = sides
        x = randint(1,self.sides)
        print(x)
roll_dies = Die()
for i in range(1,10):  
    roll_dies.roll_die()
for i in range(1.10): #这里出了一点小问题, range(1, 10)
    roll_dies.update_sides() 
#你写的比答案好多了,答案里roll_die10()这个命名好草率.
#roll_dies.update_sides() 这里,显性的标注sides=10会更可读
for i in range(1, 10):
    roll_dies.update_sides(sides=10) #这样不看你的源代码也会知道明白代码
#python的报错并不可靠,只能作为辅助.
    
搜索答案
from random import randint
class Die():
	"""docstring for Die"""
	def __init__(self):
		self.sides = 6
	def roll_die(self):
		x = randint(1,6)
		self.sides=x
		print(self.sides)
	def roll_die10(self):
		x = randint(1,10)
		self.sides = x
		print(self.sides)
	
die = Die()
print(die.sides)
print("6 sides")
for i in range(0,10):
	die.roll_die()
print("10 sides")
for i in range(0,10):
	die.roll_die10()

```

**错题集**

```python
$ python die.py
Traceback (most recent call last):
  File "die.py", line 1, in <module>
    from random import randint
  File "C:\Users\Administrator\desktop\random.py", line 141
    except ValueError, e:
                     ^
SyntaxError: invalid syntax
import random 时 output告诉我标准库里有错误 不知道什么情况
....
#这是代码里Python解释器找不到错误(就是写Python的没有预先放进去的报错),会瞎报,
#标准库里的代码不会有问题.
#另外,现在千万别花费时间读源代码,尤其是Python自己标准库的源代码
#看看标准库里有哪些工具对自己有用,再拿来用用.
```

今日所学

the python standard libarary

今天去http://pymotw.com/逛了逛

下载了random.py 的源代码 

random会用就好了, Python自己的standard libarary源代码很难,

当开始用一些简单的第三方的library的时候再开始读源代码.

Python标准库里很多内容,只看对自己有用的, 不必要看全.(出于兴趣的话,当然可以随意看看.)



以后要常常查询的文档:

1. [3.6.5 Documentation](https://docs.python.org/3/index.html) python的官方文档,

   文档中有一个官方的tutorial,有空可以看看

   [The Python Tutorial — Python 3.6.5 documentation](https://docs.python.org/3/tutorial/index.html)

2. [Python 3 Module of the Week — PyMOTW 3](https://pymotw.com/3/)

   这个网站是对python standard lib解释的最好的一个,官方的文档比较难懂.

3. 另外对标准库的态度,

   1. 标准库的初衷是要帮助我们,不然就需要自己去github上搜索,安装,找文档学习,等等;

      所以看着很多,不要烦,

   2. 用哪个学哪个, 不用全看,可以浏览浏览都有什么;

   3. 别看标准库的源代码,是架构最底层的源代码,以后不会写这样的代码.

   ​





