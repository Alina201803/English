### Chapter 7 User Input and While loops

#### Alina

2018-05-29

**源代码**

```python
message = input("Tell me something, and I will repeat it back to you: ")
print(message)

name = input("Please enter your name: ")
print("Hello, " + name + "!")

prompt = "If you tell us who you are, we can personalize the message you see."
prompt +="\nWhat is your first name? "

name = input(prompt)
print("\nHello " + name + "!")

age = input("How old are you? ")

height = input("How tall are you, in inches? ")
height = int(height)
if height >= 36:
    print("\nYou're tall enough to ride!")
else:
    print("\nYou'll be able to ride when you're a litte older.")

number = input("Enter a number, and I'll tell you if it's even or add: ")
number = int(number)

if number % 2 == 0:
    print("\nThe number " + str(number) + " is even.")
else:
    print("\nThe number " + str(number) + " is odd.")
    
练习：
7-1
message = input("What kind of rental car you would like? : ")
print("Let me see if I can find you a " + message)

7-2
message = input("How many people are in your dinner group? : ")
message = int(message)
if message >= 8:
    print("You will have to wait for a table.")
else:
    print("You table is ready.")

7-3
number = input("Enter a number, and I'll tell you if it's a mulyiple of 10 or not: ")
number = int(number)
if number % 10 == 0:
    print("Yes")
else:
    print("No")

In [52]: current_number = 1
    ...: while current_number <= 5:
    ...:     print(current_number)
    ...:     current_number += 1
    ...:
1
2
3
4
5
In [53]: 4 % 3
Out[53]: 1

In [54]: 5 % 2
Out[54]: 1

In [55]: 6 % 7
Out[55]: 6

In [56]: prompt = "\nTell me something, and I will repeat it back to you: "
    ...: prompt += "\nEnter 'quit' to end the program. "
    ...: message = ""
    ...: while message != 'quit':
    ...:     message = input(prompt)
    ...:     print(message)
    ...:

Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. Hello everyone!
Hello everyone!

Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. Hello again.
Hello again.

Tell me something, and I will repeat it back to you:
Enter 'quit' to end the program. quit
quit

```

**问题集**

今日所学：input(), int(), modulo opeater, while loop

2018-05-30

**源代码**

```python
prompt = "\nTell me something, and I will repeat it back tou you: "
prompt += "\nEnter 'quit' to end the program. "

message = ""
while message != 'quit':
    message = input(prompt)

    if message !='quit':
        print(message)
        
prompt = "\nTell me something, and I will repeat it back tou you: "
prompt += "\nEnter 'quit' to end the program. "

active = True
while active:
    message = input(prompt)

    if message == 'quit':
        active = False
    else:
        print(message)
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\nEnter 'quit' when you are finished. "

while True:
    city = input(prompt)

    if city == 'quit':
        break
    else:
        print("I'd love to go to " + city.title() + "!")
x = 1
while x <= 5:
    print(x)
    x += 1
练习：
7-4
prompt = "Please enter a series of pizza toppings:"
prompt += "Enter 'quit' to finish."


while message != 'quit':
    message = input(prompt)
    if message != 'quit':
        print("I will add " + message + " to your pizza.")
      
prompt = "Please enter a series of pizza toppings:"
prompt += "Enter 'quit' to finish."

message = input(prompt)
while message != 'quit':
    if message != 'quit':
        print("I will add " + message + " to your pizza.")
Please enter a series of pizza toppings:Enter 'quit' to finish.
这样会循环个不停 打印 I will add mashrooms to your pizza.

prompt = "How old are you? "
7-5
while age < 3:
    age = input(prompt)
    age = int(age) 
    print("The ticket is free.")
while age < 12:
    age = input(prompt)
    age = int(age) 
    print("The price is $10.")
while age > 12:
    age = input(prompt)
    age = int(age) 
    print("The price is $15.")
搜索了一下答案 更简洁
while True:
    print("Enter 'quit' when you are finished.")
    age = input("请输入你的年龄：")
    if age == 'quit':
        break
    elif int(age) < 3:
        print("The price of you is free.")
    elif 3 <= int(age) <12:
        print("The price of you is $10.")
    elif 12 <= int(age) :
        print("The price of you is $15.")
  
prompt = "Please enter a series of pizza toppings:"
prompt += "\nEnter 'quit' to finish."

active = True
while active:
    message = input(prompt)
    if message == 'quit':
        acive = False
        break
    else:
        print("I will add " + message + " to your pizza.")
In [32]: prompt = "Please enter a series of pizza toppings:"
   ...: prompt += "\nEnter 'quit' to finish."
   ...:
   ...: active = True
   ...: while active:
   ...:     message = input(prompt)
   ...:     if message == 'quit':
   ...:         acive = False
   ...:     else:
   ...:         print("I will add " + message + " to your pizza.")
   ...:
Please enter a series of pizza toppings:
Enter 'quit' to finish.mashrooms
I will add mashrooms to your pizza.
Please enter a series of pizza toppings:
Enter 'quit' to finish.quit
Please enter a series of pizza toppings:
Enter 'quit' to finish.
prompt = "Please enter a series of pizza toppings:"
prompt += "\nEnter 'quit' to finish."

active = True
while active:
    message = input(prompt)
    if message == 'quit':
        acive = False
        break
    else:
        print("I will add " + message + " to your pizza.")
 
In [33]: prompt = "Please enter a series of pizza toppings:"
   ...: prompt += "\nEnter 'quit' to finish."
   ...:

In [34]: active = True
   ...: while active:
   ...:     message = input(prompt)
   ...:     if message == 'quit':
   ...:         acive = False
   ...:         break
   ...:     else:
   ...:         print("I will add " + message + " to your pizza.")
   ...:
Please enter a series of pizza toppings:
Enter 'quit' to finish.mashrooms
I will add mashrooms to your pizza.
Please enter a series of pizza toppings:
Enter 'quit' to finish.quit

```

**错题集**


```python
prompt = "Please enter a series of pizza toppings:"
prompt += "Enter 'quit' to finish."

message = input(prompt
while message != 'quit':
    if message != 'quit':
        print("I will add " + message + " to your pizza.")
Please enter a series of pizza toppings:Enter 'quit' to finish.
这样会一直循环不停打印 I will add mashrooms to your pizza.
原因 message = input（prompt）没有起作用
如下修改即可            
prompt = "Please enter a series of pizza toppings:"
prompt += "Enter 'quit' to finish."
while message != 'quit'：
message = input(prompt)
    if message != 'quit':
        print("I will add " + message + " to your pizza.")
Please enter a series of pizza toppings:Enter 'quit' to finish.

```
 今日所学using a flag, break, continue, avoiding infinite loops