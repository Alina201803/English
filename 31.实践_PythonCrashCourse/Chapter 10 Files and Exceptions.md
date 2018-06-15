### Chapter 10 Files and Exceptions

#### Alina

2018-06-12

**源代码**

```python
with open('pi_digits.txt') as file_object:
    contents = file_object.read()
    print(contents)
    
#file_object,这里的file_object的命名是提醒,
#open命令是将pi_digits.txt这个电脑中的文件,转换成Python中的Object.
#这样,一个文件就活了起来,能跑会跳,比如有read,write等method,当然也有attribute比如
file_object.name #会输出
pi_digits.txt

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
这点真是意外,windows一贯反人性😆.
#关于运行文件,不必总是黏贴复制到ipython
1. 可以在git bash中运行, 
python a_python_file.py #
2. 也可以在ipython中运行. 
!python a_python_file.py #这是ipython提供的便利, 不必先退出ipython回到git bash中,运行文件,然后再回来.
#也可以更加简单,不过这个命令只在ipython中好用
run a_python_file.py
```

今日所学

reading en entire file

file paths

reading line by line

making a list of lines from a file



**如何理解`/` (forward slash) 和`\`back slash**

1. 从形状上, `/`头部超前, 前趋，向前走

   ​                `\`头部朝后, 后仰,也可以理解为转过身向后走. 

   ​

   这是最直观的理解

2. `/` 是向上的阶梯(扶梯),向上攀爬; `\ `是向下的滑梯, 可以理解在 `\n`  `\t`, 中`\`被称为escape character, 顺着滑梯溜走逃逸.

3. 记住在键盘上的位置, 无论是`/`还是`\`, 都表示一段叙述结束,要开始新的或者要收尾.

   比如`"python_work/text_files/"`Python_work这个文件夹结束了,要引出子文件夹,

   或者"This is is text. /n" /n是一段话结束了,回车换行.

   ​

   这样理解有什么用呢? 可以帮助锁定他们在键盘上的位置,

   他们都在键盘的右侧,因此可以表示一段意思的结束.

   另外, 

   `/`在键盘的右下方,说明是在往上走,在攀爬上升阶段, 是上楼的自动扶梯

   `\`在键盘的右上方,是往下走,在下滑阶段,是下楼的自动扶梯. windows偏爱走下坡路这个符号.





建议设置输入法,在中文状态下使用英文标点.

![Screen Shot 2018-06-13 at 6.47.34 AM](https://github.com/M-DFK/English/blob/master/31.%E5%AE%9E%E8%B7%B5_PythonCrashCourse/images/Screen%20Shot%202018-06-13%20at%206.47.34%20AM.png?raw=true)



2018-06-13

**源代码**

```python
filename = 'programming.txt'

with open(filename,'w') as file_object:
    file_object.write("I love programming.")

filename = 'programming.txt'

with open(filename,'w') as file_object:
    file_object.write("I love programming.")
    file_object.write("I love creating new game.")

filename = 'programming.txt'

with open(filename,'w') as file_object:
    file_object.write("I love programming.\n")
    file_object.write("I love creating new game.\n")

filename = 'programming.txt'

with open(filename,'a') as file_object:
    file_object.write("I also love finding meaning in large datasets.\n")
    file_object.write("I love creating apps that can run in a browser.\n")

练习：   
10-3
user_name = input("Please enter your name: ")

filename  = 'user_name.md'

with open(filename,'w') as file_object:
    file_object.write(user_name)

10-4
user_name = input("Please enter your name: ")
while user_name:
    print("Welcome! " + user_name.title())
    filename = 'guest_book.txt'
    with open(filename,'a') as file_object:
        file_object.write(user_name + '\n')
    break

10-5
reason = input("Why you like programming? ")
while reason:
    filename = "reason_programming.md"
    with open(filename,'a') as file_object:
        file_object.write(reason + '\n')
    break
```

**错题集**

```python
1
user_name = input("Please enter your name: ")

filename  = 'user_name.md'

with open(filename,'w') as file_object:
    file_object.write(user_name)
filename = 'user_name.md' user.name 后加上文件类型，否则需要选择打开方式
2
user_name = input("Please enter your name: ")
while user_name:
    print("Welcome! " + user_name.title())
    filename = 'guest_book.txt'
    with open(filename,'a') as file_object:
        file_object.write(user_name + '\n')
 使用while loop 忘记break  gitbash 打印个不停.....
```

今日所学

writing to a file

writing multiple lines

appending to a file

2018-06-14

**源代码**

```python
print(5/0)
$ python 2018-06-14.py
Traceback (most recent call last):
  File "2018-06-14.py", line 1, in <module>
    print(5/0)
ZeroDivisionError: division by zero

try:
    print(5/0)
except ZeroDivisionError:
    print("You can't divide by zero!")
You can't divide by zero!

print("Give me two numbers, and I'll divide them.")
print("Enter 'q' to quit.")

while True:
    first_number = input("\nFirst number: ")
    if first_number == 'q':
        break
    second_number = input("\nSecond number: ")
    if seconf_number == 'q':
        break
    anwser = int(first_number)/int(second_number)
    print(answer)

$ python 2018-06-14-1.py
Give me two numbers, and I'll divide them.
Enter 'q' to quit.

First number: 5

Second number: 0
Traceback (most recent call last):
  File "2018-06-14-1.py", line 9, in <module>
    if seconf_number == 'q':
NameError: name 'seconf_number' is not defined

print("Give me two numbers, and I'll divide them.")
print("Enter 'q' to quit.")

while True:
    first_number = input("\nFirst number: ")
    if first_number == 'q':
        break
    second_number = input("\nSecond number: ")
    try:
        answer = int(first_number)/int(second_number)
    except ZeroDivisionError:
        print("You can't divide by 0!")
    else:
        print(answer)

Give me two numbers, and I'll divide them.
Enter 'q' to quit.

First number: 5

Second number: 0
You can't divide by 0!

First number: 5

Second number: 2
2.5

First number: q

```

今日所学

exceptions

handing the ZeroDivisionError Exception

using exceptions to prevent crashes

the else block

**Try and Except**

Try except,  结果导向, 以终为始, 事先考虑到可能遇到的报错.

"EAFP，easier ask for forgiveness than permission"

if (then),条件判断, LBYL，look before your leap三思而后行, 

if elif else,几乎是最有用的逻辑,

但是在一大段代码里全部都是if, else,显得过于单调, 就跟写文章的时候,用同义词一样.

2018-06-15

**源代码**

```python
filename = 'alice.txt'

with open(filename) as f_obj:
    contents = f_obj.read()
Traceback (most recent call last):
  File "2018-06-15.py", line 3, in <module>
    with open(filename) as f_obj:
FileNotFoundError: [Errno 2] No such file or directory: 'alice.txt'

filename = 'alice.txt'

try:
    with open(filename) as f_obj:
        contents = f_obj.read()
except FileNotFoundError:
    msg = "Sorry, the file " + filename + " dose not exist."
    print(msg)
Sorry, the file alice.txt dose not exist.
filename = 'alice.txt'

try:
    with open(filename) as f_obj:
        contents = f_obj.read()
except FileNotFoundError:
    msg = "Sorry, the file " + filename + " dose not exist."
    print(msg)
else:
    # Count the approximate number of words in the file.
    words = contents.split()
    num_words = len(words)
    print("The file " + filename + " has about " + str(num_words) + " words.")


def count_words(filename):

    """Count the approximate number of words in file."""
    try:
        with open(filename) as f_obj:
            contents = f_obj.read()
    except FileNotFoundError:
        msg = "Sorry, the file " + filename + " dose not exist."
        print(msg)
    else:
    # Count the approximate number of words in the file.
        words = contents.split()
        num_words = len(words)
        print("The file " + filename + " has about " + str(num_words) + " words.")

filename = 'alice.txt'
count_words(filename)

def count_words(filename):

    """Count the approximate number of words in file."""
    try:
        with open(filename) as f_obj:
            contents = f_obj.read()
    except FileNotFoundError:
        msg = "Sorry, the file " + filename + " dose not exist."
        print(msg)
    else:
    # Count the approximate number of words in the file.
        words = contents.split()
        num_words = len(words)
        print("The file " + filename + " has about " + str(num_words) + " words.")

filenames = ['alice.txt','siddhartha.txt','moby_dick.txt','little_women.txt']
for filename in filenames:
    count_words(filename)



def count_words(filename):

    """Count the approximate number of words in file."""
    try:
        with open(filename) as f_obj:
            contents = f_obj.read()
    except FileNotFoundError:
        pass
    else:
    # Count the approximate number of words in the file.
        words = contents.split()
        num_words = len(words)
        print("The file " + filename + " has about " + str(num_words) + " words.")

filenames = ['alice.txt','siddhartha.txt','moby_dick.txt','little_women.txt']
for filename in filenames:
    count_words(filename)

The file alice.txt has about 29461 words.
The file moby_dick.txt has about 215136 words.
The file little_women.txt has about 189079 words.
```

**错题集**

```python
try:
        with open(filename) as f_obj:
        contents = f_obj.read()
    except FileNotFoundError:
        pass
 File "2018-06-15-1.py", line 6
    contents = f_obj.read()
           ^
IndentationError: expected an indented block

    contents前面需要缩进
    
```

今日所学

hand the FileNotFoundError Exception

Analyzing text

working with nultiple files

failing ailently