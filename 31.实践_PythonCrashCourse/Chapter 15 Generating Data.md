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

```

**今日所学**

plotting a simple line graph

changing the label type and graph thickness

correcting the plot

plotting and styling individual points with scatter()

poltting a series of points with scatter()

calculating data automatically

