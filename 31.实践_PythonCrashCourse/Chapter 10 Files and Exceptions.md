### Chapter 10 Files and Exceptions

#### Alina

2018-06-12

**源代码**

```python
with open('pi_digits.txt') as file_object:
    contents = file_object.read()
    print(contents)

with open('pi_digits.txt') as file_object:
    contents = file_object.read()
    print(contents.rstrip())

with open('python_work/text_files/pi_digits.txt') as file_object:
    contents = file_object.read()
    print(contents)

file_path = 'C:/Users/Administrator/Desktop/python_work/text_files/pi_digits.txt'
with open(file_path) as file_object:
    contents = file_object.read()
    print(contents)

filename = 'pi_digits.txt'

with open(filename) as file_object:
    for line in file_object:
        print(line)

filename = 'pi_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.strip()

print(pi_string)
print(len(pi_string))

filename = 'pi_million_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.strip()

print(pi_string[:52] + '...')
print(len(pi_string))

"Is your birthday contained in pi 游戏"
filename = 'pi_million_digits.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

pi_string = ''
for line in lines:
    pi_string += line.rstrip()

birthday = input("Enter your birthday, in the form mmddyy: ")
if birthday in pi_string:
    print("Your birthday appears in the first million digits of pi!")
else:
    print("Your birthday does not appear in the first million digits of pi.")

Enter your birthday, in the form mmddyy: 121696
Your birthday does not appear in the first million digits of pi.

练习 10-1
filename = 'learning_python.txt'

with open(filename) as file_object:
    for line in file_object:
        print(line.rstrip())

filename = 'learning_python.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

learning_string = ''
for line in lines:
    learning_string += line.rstrip()

print(learning_string)
So far I have learned in python:
variables and simple data types
lists
working with lists
if statements
dictionaries
user input and while loops
functions
classes
10-2
filename = 'learning_python.txt'

with open(filename) as file_object:
    lines = file_object.readlines()

learning_string = ''
for line in lines:
    learning_string += line.rstrip()

print(learning_string.replace('python','C'))
```

**错题集**

```python
我的Windows笔记本写文件地址时可以用 / （forward slash）  不需要改为\ （back slash）
```

今日所学

reading en entire file

file paths

reading line by line

making a list of lines from a file

