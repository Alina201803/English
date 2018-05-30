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

