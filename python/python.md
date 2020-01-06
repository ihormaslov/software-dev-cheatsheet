# Common python notes

## What is PEP8

PEP 8 is Python's style guide. It's a set of rules for how to format your Python code to maximize its readability.

## Python Design Patterns

[https://refactoring.guru/design-patterns/python](https://refactoring.guru/design-patterns/python)

## What is Decorator

A decorator is a design pattern in Python that allows a user to add new functionality to an existing object without modifying its structure. Decorators are usually called before the definition of a function you want to decorate.

## What is Metaprogramming

Metaprogramming is a programming technique in which computer programs can treat other programs as their data.
Metaprogramming is the code that manipulates code.

## [What is Metaclass](https://stackoverflow.com/a/6581949/4381376)

The main purpose of a metaclass is to change the class automatically when it's created.

- intercept a class creation
- modify the class
- return the modified class

Everything is an object in Python, and they are all either instance of classes or instances of metaclasses.

Except for `type`.

`type` is its own metaclass. That is not something you could reproduce in pure Python and is done by cheating a little bit at the implementation level.

**Metaclass can be any callable**, but prefer **classes** instead of functions
There are several reasons to do so:

- The intention is clear. When you read UpperAttrMetaclass(type), you know what's going to follow
- You can use OOP. Metaclass can inherit from metaclass, override parent methods. Metaclasses can even use metaclasses.
- Subclasses of a class will be instances of its metaclass if you specified a metaclass-class, but not with a metaclass-function.
- You can structure your code better. You never use metaclasses for something as trivial as the above example. It's usually for something complicated. Having the ability to make several methods and group them in one class is very useful to make the code easier to read.
- You can hook on **new**, **init** and **call**. This will allow you to do different stuff. Even if usually you can do it all in **new**, some people are just more comfortable using **init**.
- These are called metaclasses, damn it! It must mean something!

## What is difference between `__new__` and `__init__`?

- `__new__()`: It’s a method which is called before `__init__()`. It creates the object (class object) and returns it. We can override this method to control how the objects are created.
- `__init__()`: This method just initialize the created object (class instance) passed as a parameter

## Code Style Checkers

A tool which looks for programming errors helps to enforce a coding standard, sniffs for code smells and offers simple refactoring suggestions
pychecker, pylint, pyflakes

## What is Mocking

Mocking is a library for testing in Python. It allows you to replace parts of your system under test with mock objects and make assertions about how they have been used

## [Data Types](https://docs.python.org/3/library/datatypes.html)

- [Numeric](https://www.geeksforgeeks.org/python-data-types/#numeric)
- [Sequence Type](https://www.geeksforgeeks.org/python-data-types/#Sequence)
- [Boolean](https://www.geeksforgeeks.org/python-data-types/#boolean)
- [Set](https://www.geeksforgeeks.org/python-data-types/#set)
- [Dictionary](https://www.geeksforgeeks.org/python-data-types/#dictionary)

![Python Data Types](https://media.geeksforgeeks.org/wp-content/uploads/20191023173512/Python-data-structure.jpg)

### Numeric

Numeric data type represents the data that has a numeric value.

- **Integers** – This value is represented by int class. It contains positive or negative whole numbers (without fraction or decimal). In Python, there is no limit to how long an integer value can be.
- **Float** – This value is represented by float class. It is a real number with floating-point representation. It is specified by a decimal point. Optionally, the character e or E followed by a positive or negative integer may be appended to specify scientific notation.
- **Complex Numbers** – Complex number is represented by a complex class. It is specified as (real part) + (imaginary part)j. For example – 2+3j

### Sequence Type

A sequence is the ordered collection of similar or different data types

- **String** - Strings are arrays of bytes representing Unicode characters. A string is a collection of one or more characters put in a single quote, double-quote or triple quote.
- **List** - Lists are just like the arrays. A list may contain DataTypes like Integers, Strings, as well as Objects. Lists are mutable, and hence, they can be altered even after their creation. List in Python are ordered and have a definite count. The elements in a list are indexed according to a definite sequence and the indexing of a list is done with 0 being the first index. Each element in the list has its definite place in the list, which allows duplicating of elements in the list, with each element having its own distinct place and credibility. It is represented by a list class.
- **Tuple** - Tuples can contain any number of elements of any datatypes (like strings, integers, list, etc.). To access the tuple items refer to the index number. Use the index operator [ ] to access an item in a tuple. Deletion or Updation of a tuple is not allowed. This will cause an error because updating or deleting from a tuple is not supported. This is because tuples are immutable, hence elements of a tuple cannot be changed once it has been assigned. Only new tuples can be reassigned to the same name.

### Boolean

Data type with one of the two built-in values - True or False. But non-Boolean objects can be evaluated in the Boolean context as well and determined to be true or false.

### Set

Set is an unordered collection of data type that is iterable, mutable and has no duplicate elements. The major advantage of using a set, as opposed to a list, is that it has a highly optimized method for checking whether a specific element is contained in the set.

Elements can be added to the Set by using a built-in add() function. Only one element at a time can be added to the set by using add() method. For the addition of two or more elements Update() method is used.

Set items cannot be accessed by referring to an index since sets are unordered the items has no index. But you can loop through the set items using a for loop, or ask if a specified value is present in a set, by using the in a keyword.

Elements can be removed from the Set by using built-in remove() function but a KeyError arises if an element doesn’t exist in the set.

### Dictionary

Dictionary in Python is an ordered (unordered up until Python 3.6) collection of data values, used to store data values like a map, which unlike other Data Types that hold only a single value as an element, Dictionary holds key:value pair. Key-value is provided in the dictionary to make it more optimized. Each key-value pair in a Dictionary is separated by a `colon :`, whereas each key is separated by a `comma`.
Addition of elements can be done in multiple ways. One value at a time can be added to a Dictionary by defining value along with the key e.g. Dict[Key] = ‘Value’. Updating an existing value in a Dictionary can be done by using the built-in update() method.

| Mutable              | Immutable |
| -------------------- | --------- |
| List                 | Int       |
| Dictionary           | Float     |
| Set                  | Decimal   |
| User-defined classes | Bool      |
|                      | String    |
|                      | Tuple     |
|                      | Range     |

## Hash Table

Hash tables are a type of data structure in which the address or the index value of the data element is generated from a hash function. That makes accessing the data faster as the index value behaves as a key for the data value. In other words, the Hash table stores key-value pairs but the key is generated through a hashing function.

So the search and insertion function of a data element becomes much faster as the key values themselves become the index of the array which stores the data.

In Python, the Dictionary data types represent the implementation of hash tables. The Keys in the dictionary satisfy the following requirements.

- The keys of the dictionary are hashable i.e. they are generated by hashing function which generates unique results for each unique value supplied to the hash function.

## Iterators, Generators

`iterator` is a more general concept: any object whose class has the next method (`__next__` in Python 3) and an `__iter__` method that does return `self`

## GIL

In CPython, the global interpreter lock, or GIL, is a mutex that protects access to Python objects, preventing multiple threads from executing Python bytecodes at once. This lock is necessary mainly because CPython's memory management is not thread-safe.
210

Python's GIL is intended to serialize access to interpreter internals from different threads. On multi-core systems, it means that multiple threads can't effectively make use of multiple cores. (If the GIL didn't lead to this problem, most people wouldn't care about the GIL - it's only being raised as an issue because of the increasing prevalence of multi-core systems.) If you want to understand it in detail, you can view [this video](https://www.youtube.com/watch?v=ph374fJqFPE) or look at [this set of slides](http://www.dabeaz.com/python/GIL.pdf). It might be too much information, but then you did ask for details :-)

## Garbage Collection: What It Is and How It Works

Standard CPython's garbage collector has two components, the reference counting collector and the generational garbage collector, known as gc module.

The reference counting algorithm is incredibly efficient and straightforward, but it cannot detect reference cycles. That is why Python has a supplemental algorithm called generational cyclic GC, that specifically deals with reference cycles.

The reference counting module is fundamental to Python and can't be disabled, whereas the cyclic GC is optional and can be invoked manually.

## What kinds of things should I use Celery for

Answer: [Queue everything and delight everyone](https://decafbad.com/blog/2008/07/04/queue-everything-and-delight-everyone) is a good article describing why you’d use a queue in a web context.

These are some common use cases:

- Running something in the background. For example, to finish the web request as soon as possible, then update the user's page incrementally. This gives the user the impression of good performance and “snappiness” even though the real work might actually take some time.
- Running something after the web request has finished.
- Making sure something is done, by executing it asynchronously and using retries.
- Scheduling periodic work.

And to some degree:

- Distributed computing.
- Parallel execution.
