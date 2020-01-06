# python-cheatsheet

[Documenting Python Code](#documenting-python-code)

## Documenting Python Code

A docstring is a string literal that occurs as the first statement in a module, function, class,
or method definition. Such a docstring becomes the `__doc__` special attribute of that object.

### Class docstrings

Class docstrings should contain the following information:

- A brief summary of its purpose and behavior
- Any public methods, along with a brief description
- Any class properties (attributes)
- Anything related to the interface for subclassers, if the class is intended to be subclassed
  The class constructor parameters should be documented within the **init** class method docstring.

### Class method docstrings

- A brief description of what the method is and what it’s used for
- Any arguments (both required and optional) that are passed including keyword arguments
- Label any arguments that are considered optional or have a default value
- Any side effects that occur when executing the method
- Any exceptions that are raised
- Any restrictions on when the method can be called
