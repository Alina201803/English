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



