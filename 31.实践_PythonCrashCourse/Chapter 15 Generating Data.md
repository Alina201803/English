### Chapter 15 Generating Data 

#### @Alina

2018-06-23

```python
import matplotlib.pyplot as plt

squares = [1, 4, 9, 16, 25]
plt.plot(squares)
plt.show()
看到一个图显示出来，感觉很神奇
#嗯,Python开始办实事了.
```

可以去matplotlib的官网看看.[Gallery — Matplotlib 2.2.2 documentation](https://matplotlib.org/gallery/index.html)



2018-06-24

**源代码**

```python
import matplotlib.pyplot as plt
squares = [1, 4, 9, 16, 25]
plt.plot(squares, linewidth=5)


#set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value",fontsize=14)
plt.ylabel("Square of value",fontsize=14)

#set size of tick labels.
plt.tick_params(axis='both',labelsize=14)

plt.show()


import matplotlib.pyplot as plt


input_values = [1, 2, 3, 4, 5]
squares = [1, 4, 9, 16, 25]
plt.plot(input_values, squares, linewidth=5)

#set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value",fontsize=14)
plt.ylabel("Square of value",fontsize=14)

#set size of tick labels.
plt.tick_params(axis='both',labelsize=14)

plt.show()


import matplotlib.pyplot as plt

plt.scatter(2, 4, s=200)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of value",fontsize=14)

#Set size of tick labels.
plt.tick_params(axis='both', which='major', labelsize=14)

plt.show()


import matplotlib.pyplot as plt

x_values = [1, 2, 3, 4, 5]
y_values = [1, 4, 9, 16, 25]


plt.scatter(x_values, y_values, s=100)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of value",fontsize=14)

#Set size of tick labels.
plt.tick_params(axis='both', which='major', labelsize=14)

plt.show()


import matplotlib.pyplot as plt

x_values = list(range(1,1001))
y_values = [x**2 for x in x_values]

plt.scatter(x_values, y_values, s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of value",fontsize=14)

#Set size of tick labels.
plt.tick_params(axis='both', which='major', labelsize=14)

#Set the range for each axis.
plt.axis([0, 1100, 0, 1100000])

plt.show()

```

**问题集**

```python
plt.tick_params(axis='both', which='major', labelsize=14)
which='major'表示什么 书上没提

which: [‘major’ | ‘minor’ | ‘both’]
Default is ‘major’; 
apply arguments to which ticks.
which一共3个参数[‘major’ | ‘minor’ | ‘both’]
默认是major表示主刻度，后面分布为次刻度及主次刻度都显示
来源：知乎
#嗯,python crash course是台阶, 
#以后估计每天的工作就是搜索和查官方文档.

```

**今日所学**

plotting a simple line graph

changing the label type and graph thickness

correcting the plot

plotting and styling individual points with scatter()

poltting a series of points with scatter()

calculating data automatically

2018-06-25

**源代码**

```python
import matplotlib.pyplot as plt

x_values = [1, 2, 3, 4, 5]
y_values = [1, 4, 9, 16, 25]

plt.scatter(x_values, y_values, edgecolor = 'none', s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize = 24)
plt.xlabel("Value", fontsize = 14)
plt.ylabel("Square of Value", fontsize = 14)

plt.show()

import matplotlib.pyplot as plt

x_values = [1, 2, 3, 4, 5]
y_values = [1, 4, 9, 16, 25]

plt.scatter(x_values, y_values, c='red', edgecolor = 'none', s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize = 24)
plt.xlabel("Value", fontsize = 14)
plt.ylabel("Square of Value", fontsize = 14)

plt.show()

import matplotlib.pyplot as plt

x_values = [1, 2, 3, 4, 5]
y_values = [1, 4, 9, 16, 25]

plt.scatter(x_values, y_values, c=(0.8, 0, 0.5), edgecolor = 'none', s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize = 24)
plt.xlabel("Value", fontsize = 14)
plt.ylabel("Square of Value", fontsize = 14)

plt.show()

import matplotlib.pyplot as plt

x_values = list(range(1001))
y_values = [x**2 for x in x_values]

plt.scatter(x_values, y_values, c=y_values, cmap=plt.cm.Blues, edgecolor = 'none', s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize = 24)
plt.xlabel("Value", fontsize = 14)
plt.ylabel("Square of Value", fontsize = 14)

plt.show()

import matplotlib.pyplot as plt

x_values = list(range(1001))
y_values = [x**2 for x in x_values]

plt.scatter(x_values, y_values, c=y_values, cmap=plt.cm.Blues, edgecolor = 'none', s=40)

#Set chart title and label axes.
plt.title("Square Numbers", fontsize = 24)
plt.xlabel("Value", fontsize = 14)
plt.ylabel("Square of Value", fontsize = 14)

plt.savefig('squares_plot.png',bbox_inches='tight')

练习
import matplotlib.pyplot as plt

x_values = list(range(1,5001))
y_values = [x**3 for x in x_values]

plt.scatter(x_values, y_values, c=y_values, cmap=plt.cm.Blues, edgecolor='none', s=40)

#set chart title and label axes.
plt.title("Square Number", fontsize=24)
plt.xlabel("Value", fontsize=14)
plt.ylabel("Square of Value", fontsize=14)

#Set the range for each axis.
plt.axis([1, 5500, 1, 100000000])

plt.show()
```

**今日所学**

removing outlines from data points

defining custom colors

using a colomap

saving your plots automatically

练习

2018-06-26

**源代码**

```python
from random import choice

class RandomWalk():
    """A calss to generate random walks."""

    def __init__(self, num_points=5000):

        self.num_points = num_points

        #All walks start at(0,0)
        self.x_values = [0]
        self.y_values = [0]

    def fill_walk(self):
        """Caculate all the points in the walk."""

        #Keep taking steps until the walk reaches the desired length.
        while len(self.x_values) < self.num_points:
            #Decide which direction to go and how far to go in that direction.
            x_direction = choice([1, -1])
            x_distance = choice([0, 1, 2, 3, 4])
            x_step = x_direction * x_distance

            y_direction = choice([1, -1])
            y_distance = choice([0, 1, 2, 3, 4])
            y_step = y_direction * y_distance

            #Reject moves that go nowhere.
            if x_step == 0 and y_step == 0:
                continue

            #Calculate the next x and y values
            next_x = self.x_values[-1] + x_step
            next_y = self.y_values[-1] + y_step

            self.x_values.append(next_x)
            self.y_values.append(next_y)

            
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Make a random walk, and plot the points.
rw = RandomWalk()
rw.fill_walk()
plt.scatter(rw.x_values, rw.y_values, s=15)
plt.show()


import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk()
    rw.fill_walk()
    plt.scatter(rw.x_values, rw.y_values, s=15)
    plt.show()

    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break

import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk()
    rw.fill_walk()
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=15)
    plt.show()

    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break

```

**今日所学**

greating the randomwalk() class

choosing directions

plotting the random walk

generating multiple random walks

coloring the points



2018-06-27

**源代码**

```python
ploting the starting and ending points
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk()
    rw.fill_walk()
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=15)
    
    #Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',s=100)
    
    plt.show()
    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break
        
 cleaning up the axes
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk()
    rw.fill_walk()
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=15)
    
    #Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',s=100)
    
    #Remove the axes.
    plt.axes().get_xaxis().set_visible(False)
    plt.axes().get_yaxis().set_visible(False)
    
    plt.show()
    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break

 adding plot points
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk(50000)
    rw.fill_walk()
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=1)
    
    #Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',s=100)
    
    #Remove the axes.
    plt.axes().get_xaxis().set_visible(False)
    plt.axes().get_yaxis().set_visible(False)
    
    plt.show()
    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break

altering the size to fil the screen
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk(50000)
    rw.fill_walk()

    #Set the size of the plotting window.
    plt.figure(figsize=(10, 6))
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=1)
    
    #Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',s=100)
    
    #Remove the axes.
    plt.axes().get_xaxis().set_visible(False)
    plt.axes().get_yaxis().set_visible(False)
    
    plt.show()
    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break

练习
import matplotlib.pyplot as plt

from random_walk import RandomWalk
#Keep making new walks, as long as the program is active.
while True:
    #Make a random walk, and plot the points.
    rw = RandomWalk(50000)
    rw.fill_walk()

    #Set the size of the plotting window.
    plt.figure(dpi=128, figsize=(10, 6))
   
    point_numbers = list(range(rw.num_points))
    plt.scatter(rw.x_values, rw.y_values, c=point_numbers, cmap=plt.cm.Blues, edgecolor='none', s=1)
    
    #Emphasize the first and last points.
    plt.scatter(0, 0, c='green', edgecolors='none', s=100)
    plt.scatter(rw.x_values[-1], rw.y_values[-1], c='red', edgecolors='none',s=100)
    
    #Remove the axes.
    plt.axes().get_xaxis().set_visible(False)
    plt.axes().get_yaxis().set_visible(False)
    
    plt.show()
    keep_running = input("Making another walk?(y/n):")
    if keep_running == 'n':
        break
```

**问题集**

```python

plt.axes().get_xaxis().set_visible(False)
plt.axes().get_yaxis().set_visible(False)
chaining of methods/method chaining

维基百科
Method chaining, also known as named parameter idiom, is a common syntax for invoking multiple method calls in object-oriented programming languages Each method returns an object, allowing the calls to be chained together in a single statement without requiring variables to store the intermediate results.Local variable declarations are syntactic sugar because of the difficulty humans have with deeply nested method calls.A method chain is also known as a train wreck due to the increase in the number of methods that come one after another in the same line that occurs as more methods are chained together even though line breaks are often added between methods.

Method chaining, also known as named parameter idiom, is a common syntax for invoking multiple method calls in object-oriented programming languages. Each method returns an object, allowing the calls to be chained together in a single statement without requiring variables to store the intermediate results.


有的python初学者对python方法连续调用不是很清楚，像雾里看花一样。
python一切都是对象，对象调用它的方法，如果带返回值，放回值也是对象，  
这个返回值也有方法，当然就可以用点号调用它的方法， 
```

**今日所学**

ploting the starting and ending points

cleaning up the axes

adding plot points

altering the size to fil the screen



2018-06-28

**源代码**

```python
from random import randint

class Die():
    """A class representing a single die."""

    def __init__(self, num_sides=6):
        """Assume a six-sided die."""
        self.num_sides = num_sides

    def roll(self):
        """Return a random value between 1 and number of sides."""
        return randint(1, self.num_sides)

    
from die import Die 

#Creat a D6
die = Die()

#Make some rolls, and store results in a list
results = []
for roll_num in range(100):
    result = die.roll()
    results.append(result)

print(results)


from die import Die 

#Creat a D6
die = Die()

#Make some rolls, and store results in a list
results = []
for roll_num in range(1000):
    result = die.roll()
    results.append(result)

#Analyze the results.
frequencies = []
for value in range(1, die.num_sides+1):
    frequency = results.count(value)
    frequencies.append(frequency)

print(frequencies)

```

**今日所学**

installing pygal

creating the die class

rolling the Die

analyzing the Results



2017-06-30

**源代码**

```python
import pygal
from die import Die

#Creat a D6.
die = Die()

#Make some rolls, and store restults in a list.
results = []
for roll_num in range(1000):
    result = die.roll()
    results.append(result)

#Analyze the results.
frequencies = []
for value in range(1, die.num_sides+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rolling one D6 1000 times."
hist.x_labels = ['1', '2', '3', '4', '5', '6']
hist.x_title = "Result"
hist.y_title = "Frequency of Result"

hist.add('D6', frequencies)
hist.render_to_file('die_visual.svg')

```

**今日所学**

```python
import pygal
from die import Die

#Creat a D6.
die = Die()

#Make some rolls, and store restults in a list.
results = []
for roll_num in range(1000):
    result = die.roll()
    results.append(result)

#Analyze the results.
frequencies = []
for value in range(1, die.num_sides+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rolling one D6 1000 times."
hist.x_labels = ['1', '2', '3', '4', '5', '6']
hist.x_title = "Result"
hist.y_title = "Frequency of Result"

hist.add('D6', frequencies)
hist.render_to_file('die_visual.svg')

```

今日所学

making a histogram

2018-06-30

**源代码**

```python
import pygal

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()

#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() + die_2.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides

for value in range(2, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_label = ['2','3','4','5','6','7','8','9','10','11','12']
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 + D6', frequencies)
hist.render_to_file('dice_visual.svg')

```

**今日所学**

rolling two dies

2018-07-01

**源代码**

```python
from die import Die

import pygal

#Creat a D6 and a D10
die_1 = Die()
die_2 = Die(10)

#Make some rolls, and store results in a list
results = []
for roll_num in range(50000):
    result = die_1.roll() + die_2.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides
for value in range(2, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results
hist = pygal.Bar()

hist.title = "Results of rolling a D6 and a D10 50000 times."
hist.x_labels = ['2','3','4','5','6','7','8','9','10','11','12','13','14','15','16']
hist.x_title = "Result"
hist.y_title = "Frequency of Result"

hist.add('D6 + D10', frequencies)
hist.render_to_file('dice_visual.svg')

```

**今日所学**

rilling dice of different sizes



2018-07-04

**源代码**

```python
15-6
import pygal

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()

#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() + die_2.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides

for value in range(2, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_labels = list(range(2, max_result+1))
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 + D6', frequencies)
hist.render_to_file('dice_visual.svg')


import pygal

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()

#Make some rolls, and store results in a list.
results = []
results=[die_1.roll()+die_2.roll() for roll_num in range(1000)]
#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides

frequencies=[results.count(value) for value in range(2,max_result+1)]

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_labels = [i for i in range(2, max_result+1)]
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 + D6', frequencies)
hist.render_to_file('dice_visual.svg')

15-7
import pygal

from die import Die

#Creat two D6 dice
die_1 = Die(8)
die_2 = Die(8)

#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() + die_2.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides

for value in range(2, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_labels = ['2','3','4','5','6','7','8','9','10','11','12','13','14','15','16']
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 + D8', frequencies)
hist.render_to_file('8_dice_visual.svg')


15-8
import pygal

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()
die_3 = Die()

#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() + die_2.roll() + die_3.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides +die_3.num_sides

for value in range(3, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_labels = list(range(3, max_result+1))
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 + D6 + D6', frequencies)
hist.render_to_file('3_dice_visual.svg')


15_9
import pygal

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()


#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() * die_2.roll()
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides * die_2.num_sides 

for value in range(1, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
hist = pygal.Bar()

hist.title = "Results of rilling two D6 dice 1000 times."
hist.x_labels = list(range(1, max_result+1))
hist.x_title = 'Result'
hist.y_title = 'Frequency of Result'

hist.add('D6 * D6', frequencies)
hist.render_to_file('multiplication_dice_visual.svg')

15-10
import matplotlib.pyplot as plt

from die import Die

#Creat two D6 dice
die_1 = Die()
die_2 = Die()


#Make some rolls, and store results in a list.
results = []
for roll_num in range(10000):
    result = die_1.roll() + die_2.roll() 
    results.append(result)

#Analyze the results.
frequencies = []
max_result = die_1.num_sides + die_2.num_sides 

for value in range(2, max_result+1):
    frequency = results.count(value)
    frequencies.append(frequency)

#Visualize the results.
x_values = list(range(2, max_result+1))
y_values = frequencies
plt.scatter(x_values, y_values, s = 100)
plt.show()

```

**错题集**

```python
hist.x_labels() 错写成list.x_label()..... x轴 没有横坐标  需注意函数名字
```

**今日所学**

完成练习