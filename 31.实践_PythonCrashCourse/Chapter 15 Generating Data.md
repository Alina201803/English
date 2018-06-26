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