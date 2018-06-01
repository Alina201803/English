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

2018-05-30

**源代码**

```python
In [1]: unconfirmed_users = ['alice','brian','candace']
   ...: confirmed_users = []
   ...:

In [2]: while unconfirmed_users:
   ...:     current_user = unconfirmed_users.pop()
   ...:     print("Verifying user: " + current_user.title())
   ...:     confirmed_users.append(current_user)
   ...: print("\nThe following users have been confirmed:")
   ...: for confirmed_user in confirmed_users:
   ...:     print(confirmed_user.title())
   ...:
Verifying user: Candace
Verifying user: Brian
Verifying user: Alice

The following users have been confirmed:
Candace
Brian
Alice
In [3]: pets = ['dog','cat','dog','goldfish','cat','rabbit','cat']
   ...: print(pets)
   ...: while cat in pets:
   ...:     pets.remove('cat')
   ...: print(pets)
   ...:
['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-3-bf8ab05af090> in <module>()
      1 pets = ['dog','cat','dog','goldfish','cat','rabbit','cat']
      2 print(pets)
----> 3 while cat in pets:
      4     pets.remove('cat')
      5 print(pets)

NameError: name 'cat' is not defined

In [4]: pets = ['dog','cat','dog','goldfish','cat','rabbit','cat']
   ...: print(pets)
   ...: while 'cat' in pets:
   ...:     pets.remove('cat')
   ...: print(pets)
   ...:
['dog', 'cat', 'dog', 'goldfish', 'cat', 'rabbit', 'cat']
['dog', 'dog', 'goldfish', 'rabbit']
In [5]: polling active = True
   ...: while polling active:
   ...:     name = input("\nWhat is your name? ")
   ...:     reponse = input("Which mountain would you like to climb someday? ")
   ...:
   ...:     responses[name] = response
   ...:     repeat = input("Would you like to let another person respond? (yes/
   ...: no) ")
   ...:     if repeat == 'no':
   ...:         polling active = False
   ...: print("\n---poll Results---")
   ...: for name, response in response.items():
   ...:     print(name + " Would like to climb " + response + ".")
   ...:
  File "<ipython-input-5-5e774c94e4d7>", line 1
    polling active = True
                 ^
SyntaxError: invalid syntax
In [8]: responses = {}
   ...:
   ...: polling_active = True
   ...: while polling_active:
   ...:     name = input("\nWhat is your name? ")
   ...:     response = input("Which mountain would you like to climb someday? "
   ...: )
   ...:     responses[name] = response
   ...:     repeat = input("Would you like to let another person respond? (yes/
   ...: no) ")
   ...:     if repeat == 'no':
   ...:         polling_active = False
   ...: print("\n---poll Results---")
   ...: for name, response in responses.items():
   ...:     print(name + " Would like to climb " + response + ".")
   ...:

What is your name? Eric
Which mountain would you like to climb someday? Denali
Would you like to let another person respond? (yes/no) yes

What is your name? Lynn
Which mountain would you like to climb someday? Devil's Thumb
Would you like to let another person respond? (yes/no) no

---poll Results---
Eric Would like to climb Denali.
Lynn Would like to climb Devil's Thumb.

练习：
7-8
In [9]: sandwich_orders = ['tuna','bacon','reuben']
   ...: finished_sandwiches = []
   ...: while sandwich_orders:
   ...:     sandwich_order = sandwich_orders.pop()
   ...:     print("I made your " + sandwich_order + " sandwich.")
   ...:     finished_sandwiches.append(sandwich_order)
   ...: for finished_sandwich in finished_sandwiches:
   ...:     print(finished_sandwich.title())
   ...:
I made your reuben sandwich.
I made your bacon sandwich.
I made your tuna sandwich.
Reuben
Bacon
Tuna
In [10]: sandwich_orders = ['tuna','bacon','reuben']
    ...: finished_sandwiches = []
    ...: while sandwich_orders:
    ...:     sandwich_order = sandwich_orders.pop()
    ...:     print("I made your " + sandwich_order + " sandwich.")
    ...:     finished_sandwiches.append(sandwich_order)
    ...: print("\nThe following sandwiches have been finished")
    ...: for finished_sandwich in finished_sandwiches:
    ...:     print(finished_sandwich.title())
    ...:
I made your reuben sandwich.
I made your bacon sandwich.
I made your tuna sandwich.

The following sandwiches have been finished
Reuben
Bacon
Tuna
7-9
In [11]: sandwich_orders = ['pastrami','tuna','bacon','pastrami','reuben','past
    ...: rami']
    ...: while 'pastrami' in sandwich_orders:
    ...:     sandwich_orders.remove('pastrami')
    ...: print(sandwich_orders)
    ...:
['tuna', 'bacon', 'reuben']
7-10
In [20]: Dream_vacation = {}
    ...: polling_active = True
    ...: while polling_active:
    ...:     name = input("What's your name? ")
    ...:     place = input("\nIf you could visit one place in the world, where
    ...: would you go? ")
    ...:     Dream_vacation[name] = place
    ...:     repeat = input("Enter quit to end the program.")
    ...:     if repeat == 'quit':
    ...:         polling_active = False
    ...:
    ...: print("\n---Poll Results---")
    ...: for name,place in Dream_vacation.items():
    ...:     print(name + " Would like to go to the " + place + '.')
    ...:
What's your name? Alina

If you could visit one place in the world, where would you go? France
Enter quit to end the program.quit

---Poll Results---
Alina Would like to go to the France.
  
```

**错题集**

```python
In [12]: Dream_vacation = {}
    ...: polling_active = True
    ...: while polling active:
    ...:     name = input("What's your name? ")
    ...:     place = input("If you could visit one place in the world, where wo
    ...: uld you go? ")
    ...:     Dream_vacation[name] = place
    ...:     repeat = input("Enter quit to end the program.")
    ...:     if repeat == 'quit':
    ...:         polling_active = False
    ...:
    ...: print("\n---Poll Results---")
    ...:     for name,place in Dream_vacation.items():
    ...:         print(name + " Would like to go to the " + palce + '.')
    ...:
  File "<ipython-input-12-d33a80dc4ba1>", line 3
    while polling active:
                       ^
SyntaxError: invalid syntax
polling 和 active之间缺少 连字符_
                           
                          
```

今日所学：

moving items from one list to another

removing all instances of specific values from a list

filling a dictionary with user input