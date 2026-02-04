# python-core

------> METHODS -------

---->Types of Methods in Python

Python mainly has three types of methods:
1.Instance Methods
2.Class Methods
3.Static Methods
1️⃣ Instance Methods
What are Instance Methods?
-Work with object (instance) data
-Use the keyword self
-Can access and modify instance variables
SYNTAX : class ClassName:
            def method_name(self):
EXAMPLE : 
class Student:
    def set_data(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Marks:", self.marks)

s1 = Student()
s1.set_data("Tejaswini", 85)
s1.display()

KEY POINTS
-self refers to the current object
-Instance methods are most commonly used

2️⃣ Class Methods
What are Class Methods?
-Work with class-level data
-Use cls instead of self
-Defined using @classmethod decorator
SYNTAX : 
class ClassName:
    @classmethod
    def method_name(cls):
        # code

EXAMPLE : 
class College:
    college_name = "ABC Engineering"

    @classmethod
    def show_college(cls):
        print("College:", cls.college_name)

College.show_college()

KEY POINTS
-Access class variables
-Called using class name
-Cannot directly access instance variables

3️⃣ Static Methods
What are Static Methods?
-Do not use self or cls
-General utility functions
-Defined using @staticmethod
SYNTAX :
class ClassName:
    @staticmethod
    def method_name():
        # code
EXAMPLE :
class MathOps:
    @staticmethod
    def add(a, b):
        return a + b

print(MathOps.add(10, 20))

KEY POINTS
No access to instance or class variables

-----------
| Method Type     | Uses          | Keyword | Access           |
| --------------- | ------------- | ------- | ---------------- |
| Instance Method | Object data   | `self`  | Instance + Class |
| Class Method    | Class data    | `cls`   | Class only       |
| Static Method   | Utility logic | None    | Neither          |

------>
Built-in Methods Example
String Methods------->
"CODE"
text = "python"
print(text.upper())

------->
LIST METHODS
------>
"CODE"
nums = [10, 20, 30]
nums.append(40)
nums.insert(1, 15)
nums.remove(20)
print(nums)

print(text.capitalize())
print(text.islower())




What is an Instance Method?

An instance method is a method that:

Belongs to an object (instance) of a class

Uses self

Works with instance variables

👉 In simple words:
Instance methods define what an object can do.

Real-Life Example First 🧠

Think of a Student:

Data (variables) → name, marks

Actions (methods) → read(), write(), display_marks()

Each student has their own data, so we use instance methods.

Basic Structure of an Instance Method
class ClassName:
    def method_name(self):
        # code

Why self?

self refers to the current object

It helps Python know which object’s data to use

Simple Example (Step by Step)
class Student:
    def display(self):
        print("This is an instance method")

Creating an object
s1 = Student()
s1.display()


🟢 Output:

This is an instance method


Here:

display() → instance method

s1 → object

self → automatically refers to s1

Instance Variables + Instance Methods

Instance variables are created using self.

Example
class Student:
    def set_data(self, name, marks):
        self.name = name
        self.marks = marks

    def show_data(self):
        print("Name:", self.name)
        print("Marks:", self.marks)

Using the class
s1 = Student()
s1.set_data("Tejaswini", 85)
s1.show_data()


🟢 Output:

Name: Tejaswini
Marks: 85

What is Happening Internally?

When you write:

s1.set_data("Tejaswini", 85)


Python actually understands it as:

Student.set_data(s1, "Tejaswini", 85)


👉 That’s why self is compulsory in instance methods.

Multiple Objects = Different Data
s1 = Student()
s2 = Student()

s1.set_data("Tejaswini", 85)
s2.set_data("Anitha", 92)

s1.show_data()
s2.show_data()


🟢 Output:

Name: Tejaswini
Marks: 85
Name: Anitha
Marks: 92


Each object has its own copy of data.

Instance Method with __init__() (Constructor)

__init__() is a special instance method that runs automatically when an object is created.

Example
class Student:
    def __init__(self, name, marks):
        self.name = name
        self.marks = marks

    def display(self):
        print("Name:", self.name)
        print("Marks:", self.marks)

Usage
s1 = Student("Tejaswini", 85)
s1.display()

Instance Method Modifying Data

Instance methods can change object data.

class Bank:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print("Balance:", self.balance)

    def withdraw(self, amount):
        self.balance -= amount
        print("Balance:", self.balance)

b = Bank(1000)
b.deposit(500)
b.withdraw(300)

Key Rules to Remember ⭐

Instance methods must have self

They are called using object name

They can:

Access instance variables

Modify instance variables

Each object has separate data

Common Beginner Mistakes ❌
Forgetting self
def show():
    print("Hello")


❌ Error

✅ Correct:

def show(self):
    print("Hello")

Using class name without object
Student.display()


❌ Error (needs object)

✅ Correct:

s1.display()

Very Short Comparison (Just for clarity)
Feature	Instance Method
Keyword used	self
Called using	Object
Works on	Object data
Common usage	Very high
One-Line Definition (Exam Ready)

Instance method is a method that is used to access and modify instance variables using self and is called through an object.
