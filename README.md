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
