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