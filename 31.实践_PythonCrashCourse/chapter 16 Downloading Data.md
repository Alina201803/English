### chapter 16 Downloading Data

2018-07-02

**源代码**

```python
import csv

filename = 'sitka_weather_07-2014.csv'
with open(filename) as f:
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

header_row = next(reader)   是将 reader object 中的第一行存储到header_row中，然后下面的 for row in reader:  就只涉及数据的意思嘛

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

**今日所学**

ploting data in temperature chart

plotting dates

plotting a longer timeframe，

plotting a second data series 

shading an area in the chart