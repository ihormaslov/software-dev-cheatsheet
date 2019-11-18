
# What is PEP8
PEP 8 is Python's style guide. It's a set of rules for how to format your Python code to maximize its readability. Writing code to a specification helps to make large code bases, with lots of writers, more uniform and predictable, too.

# Python Design Patterns
[https://refactoring.guru/design-patterns/python](https://refactoring.guru/design-patterns/python)

# What is Decorator
A decorator is a design pattern in Python that allows a user to add new functionality to an existing object without modifying its structure. Decorators are usually called before the definition of a function you want to decorate.

# What is Metaprogramming
Metaprogramming is a programming technique in which computer programs have the ability to treat other programs as their data.
Metaprogramming is the code which manipulates code

# [What is Metaclass](https://stackoverflow.com/a/6581949/4381376)
The main purpose of a metaclass is to change the class automatically, when it's created.
- intercept a class creation
- modify the class
- return the modified class

Everything is an object in Python, and they are all either instances of classes or instances of metaclasses.

Except for `type`.

`type` is actually its own metaclass. This is not something you could reproduce in pure Python, and is done by cheating a little bit at the implementation level.

**Metaclass can be any callable**, but prefer **classes** instead of functions
There are several reasons to do so:

- The intention is clear. When you read UpperAttrMetaclass(type), you know what's going to follow
- You can use OOP. Metaclass can inherit from metaclass, override parent methods. Metaclasses can even use metaclasses.
- Subclasses of a class will be instances of its metaclass if you specified a metaclass-class, but not with a metaclass-function.
- You can structure your code better. You never use metaclasses for something as trivial as the above example. It's usually for something complicated. Having the ability to make several methods and group them in one class is very useful to make the code easier to read.
- You can hook on __new__, __init__ and __call__. Which will allow you to do different stuff. Even if usually you can do it all in __new__, some people are just more comfortable using __init__.
- These are called metaclasses, damn it! It must mean something!



