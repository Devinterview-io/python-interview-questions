# Top 100 Python Interview Questions

<div>
<p align="center">
<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

#### You can also find all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

## 1. What are the _key features_ of _Python_?

**Python** is a versatile and dominant programming language known for its simplicity, **elegant syntax**, and massive ecosystem. Below are the defining features that maintain its popularity in 2026.

### Key Features of Python

#### 1. Interpreted and Interactive
Python executes code **line-by-line** via an interpreter, facilitating rapid prototyping and debugging. Modern versions utilize a specializing **adaptive interpreter** to optimize performance during execution.

#### 2. Easy to Learn and Read
Python's **clean syntax** resembles plain English and relies on indentation for structure. This high readability significantly reduces the cognitive load for both beginners and maintenance engineers.

#### 3. Cross-Platform Compatibility
Python is platform-independent, running seamlessly on Windows, Linux, macOS, and **WebAssembly (WASM)** environments without requiring platform-specific code modifications.

#### 4. Modular and Scalable
The language encourages modularity through packages and modules, allowing developers to organize code into **reusable** functions and classes for scalable application architectures.

#### 5. Rich Library Ecosystem
The Python Package Index (PyPI) hosts **hundreds of thousands** of libraries, providing immediate solutions for Artificial Intelligence, Data Science, Web Development, and Cloud Computing.

#### 6. Exceptionally Versatile
Python serves as a general-purpose language, equally proficient in scripting, building complex web applications, and performing high-performance **scientific computing**.

#### 7. Automatic Memory Management
Python manages memory automatically via a private heap and built-in **Garbage Collection**, shielding developers from low-level details like manual memory deallocation.

#### 8. Dynamically Typed with Gradual Typing
Python infers data types at runtime (dynamic typing). However, modern Python embraces **Type Hints**, enabling static analysis and robust tooling while retaining runtime flexibility.

#### 9. Object-Oriented
Python strictly follows object-oriented paradigms. Everything, including functions and data types, is an **object**, supporting inheritance, polymorphism, and encapsulation.

#### 10. Extensible and Embeddable
Python allows integration with C/C++ for performance-critical tasks. It is also **embeddable**, allowing integration into other applications to provide scripting interfaces.
<br>

## 2. How is _Python_ executed?

### Execution Overview
Python is a hybrid language that utilizes a two-step process involving **compilation** to an intermediate format followed by **interpretation**. This design balances development speed with portability.

### Compilation & Interpretation
The standard execution flow in CPython (the reference implementation) consists of:

- **Bytecode Compilation**: The Python compiler translates high-level source code (`.py`) into **bytecode**. Bytecode represents a set of platform-independent instructions optimized for the Python Virtual Machine (PVM). These compiled files are often cached in the `__pycache__` directory (as `.pyc` files) to speed up subsequent startups.
  
- **Interpretation**: The PVM acts as a loop that iterates through bytecode instructions, executing them one by one. It abstracts the underlying hardware, ensuring the code runs on any operating system.

### Source Code to Bytecode: Key Steps
1.  **Lexical Analysis (Tokenization)**: The source code is broken down into a stream of atomic elements called tokens (keywords, identifiers, literals).
2.  **Parsing**: Tokens are organized into an **Abstract Syntax Tree (AST)**, a tree representation of the code's logical structure.
3.  **Symbol Table Generation**: The compiler analyzes the AST to define scopes and variable bindings (semantic analysis).
4.  **Bytecode Generation**: The AST is traversed to emit the final bytecode instructions encapsulated in code objects.

### Modern Optimization: Adaptive Interpreter & JIT
Since Python 3.11 (and enhanced in 3.13+), the execution model has evolved to include dynamic optimization:

- **Tier 1: Adaptive Interpretation**: The PVM monitors code as it runs. If specific instructions are executed frequently with consistent types (e.g., binary addition of two integers), the interpreter "specializes" them on-the-fly, replacing generic bytecode with faster, type-specific versions.
- **Tier 2: JIT Compilation**: Modern CPython utilizes a **Copy-and-Patch JIT** (Just-In-Time) compiler. For "hot" code paths, specialized bytecode is translated into machine code micro-operations, significantly reducing the overhead of the interpretation loop.

### Code Example: Bytecode Inspection
We can use the `dis` module to view the underlying bytecode. The example below also demonstrates **constant folding**, an optimization where the compiler pre-calculates constant expressions.

```python
import dis

def example_func():
    return 15 * 20

# Disassemble to view bytecode instructions
dis.dis(example_func)
```

**Output:**
```plaintext
  4           0 LOAD_CONST               1 (300)
              2 RETURN_VALUE
```
*(The compiler computed `15 * 20` -> `300` during compilation, issuing a single `LOAD_CONST` instruction rather than a runtime multiplication.)*
<br>

## 3. What is _PEP 8_ and why is it important?

### What is PEP 8?

**PEP 8** is the official style guide for Python code. It stands for *Python Enhancement Proposal 8* and provides conventions for writing clear, consistent, and standard Python. Its primary goal is to improve the readability of code and make it indistinguishable across different developers.

In 2026, while strict manual adherence is less common, PEP 8 remains the foundational configuration for modern auto-formatters (like **Ruff** or **Black**) and linters.

### Key Design Principles

PEP 8 emphasizes:

- **Readability**: Code is read much more often than it is written.
- **Consistency**: A uniform style reduces cognitive load, allowing developers to focus on logic rather than formatting.
- **Explicit Layout**: Visual cues (indentation, spacing) should reflect the logical structure of the code.

### Base Rules

- **Indentation**: Use **4 spaces** for each indentation level. Do not use tabs.
- **Line Length**: The official limit is **79 characters** to facilitate side-by-side code review. (Note: Many modern teams extend this to 88 or 100 characters via configuration).
- **Blank Lines**: Use two blank lines to separate top-level functions and classes; use one blank line for method definitions inside classes.
- **Imports**: Place imports at the top of the file, on separate lines.

### Naming Styles

- **Class Names**: Use `CapWords` (PascalCase).
- **Functions and Variables**: Use `snake_case` (lowercase with underscores).
- **Constants**: Use `UPPER_CASE_WITH_UNDERSCORES`.
- **Modules**: Keep names short and `lowercase`.

### Documentation

- **Docstrings**: Use triple double-quotes (`"""`) for all public modules, functions, classes, and methods.
- **Comments**: Comments should be complete sentences. Inline comments should be separated by at least two spaces from the code.

### Whitespace Usage

- **Operators**: Surround binary operators with a single space (e.g., `x = y + 1`).
- **Grouping**: Avoid extraneous whitespace inside parentheses, brackets, or braces (e.g., `call(arg)` not `call( arg )`).

### Example: Directory Walker

The following code illustrates PEP 8 compliance, including standard spacing, naming conventions, and modern type hints:

```python
import os

def walk_directory(path: str) -> None:
    """Traverse the directory and print all file paths."""
    for dirpath, _, filenames in os.walk(path):
        for filename in filenames:
            file_path = os.path.join(dirpath, filename)
            print(file_path)

if __name__ == "__main__":
    walk_directory('/path/to/directory')
```
<br>

## 4. How is memory allocation and garbage collection handled in _Python_?

In Python, **both memory allocation** and **garbage collection** are handled discretely.

### Memory Allocation

- The "heap" is the pool of memory for storing objects. The Python memory manager allocates and deallocates this space as needed.

- In latest Python versions, the `obmalloc` system is responsible for small object allocations. This system preallocates small and medium-sized memory blocks to manage frequently created small objects.

- The `allocator` abstracts the system-level memory management, employing memory management libraries like `Glibc` to interact with the operating system.

- Larger blocks of memory are primarily obtained directly from the operating system.

- **Stack** and **Heap** separation is joined by "Pool Allocator" for internal use.

### Garbage Collection

Python employs a method called **reference counting** along with a **cycle-detecting garbage collector**.

#### Reference Counting

- Every object has a reference count. When an object's count drops to zero, it is immediately deallocated.

- This mechanism is swift, often releasing objects instantly without the need for garbage collection.

- However, it can be insufficient in handling **circular references**.

#### Cycle-Detecting Garbage Collector

- Python has a separate garbage collector that periodically identifies and deals with circular references.

- This is, however, a more time-consuming process and is invoked less frequently than reference counting.

### Memory Management in Python vs. C

Python handles memory management quite differently from languages like C or C++:

- In Python, the developer isn't directly responsible for memory allocations or deallocations, reducing the likelihood of memory-related bugs.

- The memory manager in Python is what's known as a **"general-purpose memory manager"** that can be slower than the dedicated memory managers of C or C++ in certain contexts.

- Python, especially due to the existence of a garbage collector, might have memory overhead compared to C or C++ where manual memory management often results in minimal overhead is one of the factors that might contribute to Python's sometimes slower performance.

- The level of memory efficiency isn't as high as that of C or C++. This is because Python is designed to be convenient and easy to use, often at the expense of some performance optimization.
<br>

## 5. What are the _built-in data types_ in _Python_?

Python offers numerous **built-in data types** that provide varying functionalities and utilities.

### Immutable Data Types

#### 1. int
   Represents a whole number, such as 42 or -10.

#### 2. float
   Represents a decimal number, like 3.14 or -0.01.

#### 3. complex
   Comprises a real and an imaginary part, like 3 + 4j.

#### 4. bool
   Represents a boolean value, True or False.

#### 5. str
   A sequence of unicode characters enclosed within quotes.

#### 6. tuple
   An ordered collection of items, often heterogeneous, enclosed within parentheses.

#### 7. frozenset
   A set of unique, immutable objects, similar to sets, enclosed within curly braces.

#### 8. bytes
   Represents a group of 8-bit bytes, often used with binary data, enclosed within brackets.

#### 9. bytearray
   Resembles the 'bytes' type but allows mutable changes.

#### 10. NoneType
   Indicates the absence of a value.

### Mutable Data Types

#### 1. list
   A versatile ordered collection that can contain different data types and offers dynamic sizing, enclosed within square brackets.

#### 2. set
   Represents a unique set of objects and is characterized by curly braces.

#### 3. dict
   A versatile key-value paired collection enclosed within braces.

#### 4. memoryview
   Points to the memory used by another object, aiding efficient viewing and manipulation of data.

#### 5. array
   Offers storage for a specified type of data, similar to lists but with dedicated built-in functionalities.

#### 6. deque
   A double-ended queue distinguished by optimized insertion and removal operations from both its ends.

#### 7. object
   The base object from which all classes inherit.

#### 8. types.SimpleNamespace
   Grants the capability to assign attributes to it.

#### 9. types.ModuleType
   Represents a module body containing attributes.

#### 10. types.FunctionType
   Defines a particular kind of function.
<br>

## 6. Explain the difference between a _mutable_ and _immutable_ object.

Let's look at the difference between **mutable** and **immutable** objects.

### Key Distinctions

- **Mutable Objects**: Can be modified after creation.
- **Immutable Objects**: Cannot be modified after creation.

### Common Examples

- **Mutable**: Lists, Sets, Dictionaries
- **Immutable**: Tuples, Strings, Numbers

### Code Example: Immutability in Python

Here is the Python code:

```python
# Immutable objects (int, str, tuple)
num = 42
text = "Hello, World!"
my_tuple = (1, 2, 3)

# Trying to modify will raise an error
try:
    num += 10
    text[0] = 'M'  # This will raise a TypeError
    my_tuple[0] = 100  # This will also raise a TypeError
except TypeError as e:
    print(f"Error: {e}")

# Mutable objects (list, set, dict)
my_list = [1, 2, 3]
my_dict = {'a': 1, 'b': 2}

# Can be modified without issues
my_list.append(4)
del my_dict['a']

# Checking the changes
print(my_list)  # Output: [1, 2, 3, 4]
print(my_dict)  # Output: {'b': 2}
```

### Benefits & Trade-Offs

**Immutability** offers benefits such as **safety** in concurrent environments and facilitating **predictable behavior**.

**Mutability**, on the other hand, often improves **performance** by avoiding copy overhead and redundant computations.

### Impact on Operations

- **Reading and Writing**: Immutable objects typically favor **reading** over **writing**, promoting a more straightforward and predictable code flow.  

- **Memory and Performance**: Mutability can be more efficient in terms of memory usage and performance, especially concerning large datasets, thanks to in-place updates.

Choosing between the two depends on the program's needs, such as the required data integrity and the trade-offs between predictability and performance.
<br>

## 7. How do you _handle exceptions_ in _Python_?

**Exception handling** is a fundamental aspect of Python, and it safeguards your code against unexpected errors or conditions. Key components of exception handling in Python include:

### Components

- **Try**: The section of code where exceptions might occur is placed within a `try` block.

- **Except**: Any possible exceptions that are `raised` by the `try` block are caught and handled in the `except` block.

- **Finally**: This block ensures a piece of code always executes, regardless of whether an exception occurred. It's commonly used for cleanup operations, such as closing files or database connections.

### Generic Exception Handling vs. Handling Specific Exceptions

It's good practice to **handle** specific exceptions. However, a more **general** approach can also be taken. When doing the latter, ensure the general exception handling is at the end of the chain, as shown here:

```python
try:
    risky_operation()
except IndexError:  # Handle specific exception types first.
    handle_index_error()
except Exception as e:  # More general exception must come last.
    handle_generic_error()
finally:
    cleanup()
```

### Raising Exceptions

Use this mechanism to **trigger and manage** exceptions under specific circumstances. This can be particularly useful when building custom classes or functions where specific conditions should be met.

**Raise** a specific exception:

```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Divisor cannot be zero")
    return a / b

try:
    result = divide(4, 0)
except ZeroDivisionError as e:
    print(e)
```

**Raise a general exception**:

```python
def some_risky_operation():
    if condition: 
        raise Exception("Some generic error occurred")
```

### Using `with` for Resource Management

The `with` keyword provides a more efficient and clean way to handle resources, like files, ensuring their proper closure when operations are complete or in case of any exceptions. The resource should implement a `context manager`, typically by having `__enter__` and `__exit__` methods.

Here's an example using a file:

```python
with open("example.txt", "r") as file:
    data = file.read()
# File is automatically closed when the block is exited.
```

### Silence with `pass`, `continue`, or `else`

There are times when not raising an exception is appropriate. You can use `pass` or `continue` in an exception block when you want to essentially ignore an exception and proceed with the rest of your code.

- **`pass`**: Simply does nothing. It acts as a placeholder.

  ```python
  try:
      risky_operation()
  except SomeSpecificException:
      pass
  ```

- **`continue`**: This keyword is generally used in loops. It moves to the next iteration without executing the code that follows it within the block.

  ```python
  for item in my_list:
      try:
          perform_something(item)
      except ExceptionType:
          continue
      ```

- **`else` with `try-except` blocks**: The `else` block after a `try-except` block will only be executed if no exceptions are raised within the `try` block

  ```python
  try:
      some_function()
  except SpecificException:
      handle_specific_exception()
  else:
      no_exception_raised()
  ```

### Callback Function: `ExceptionHook`

Python 3 introduced the better handling of uncaught exceptions by providing an optional function for printing stack traces. The `sys.excepthook` can be set to match any exception in the module as long as it has a `hook` attribute.

Here's an example for this test module:

```python
# test.py
import sys

def excepthook(type, value, traceback):
    print("Unhandled exception:", type, value)
    # Call the default exception hook
    sys.__excepthook__(type, value, traceback)

sys.excepthook = excepthook

def test_exception_hook():
    throw_some_exception()
```

When run, calling `test_exception_hook` will print "Unhandled exception: ..."

_Note_: `sys.excepthook` will not capture exceptions raised as the result of interactive prompt commands, such as SyntaxError or KeyboardInterrupt.
<br>

## 8. What is the difference between _list_ and _tuple_?

**Lists** and **Tuples** in Python share many similarities, such as being sequences and supporting indexing.

However, these data structures differ in key ways:

### Key Distinctions

- **Mutability**: Lists are mutable, allowing you to add, remove, or modify elements after creation. Tuples, once created, are immutable.

- **Performance**: Lists are generally slower than tuples, most apparent in tasks like iteration and function calls.

- **Syntax**: Lists are defined with square brackets `[]`, whereas tuples use parentheses `()`.

### When to Use Each

- **Lists** are ideal for collections that may change in size and content. They are the preferred choice for storing data elements.

- **Tuples**, due to their immutability and enhanced performance, are a good choice for representing fixed sets of related data.

### Syntax

#### List: Example

```python
my_list = ["apple", "banana", "cherry"]
my_list.append("date")
my_list[1] = "blackberry"
```

#### Tuple: Example

```python
my_tuple = (1, 2, 3, 4)
# Unpacking a tuple
a, b, c, d = my_tuple
```
<br>

## 9. How do you create a _dictionary_ in _Python_?

**Python dictionaries** are versatile data structures, offering key-based access for rapid lookups. Let's explore various data within dictionaries and techniques to create and manipulate them.

### Key Concepts

- A **dictionary** in Python contains a collection of `key:value` pairs.
- **Keys** must be unique and are typically immutable, such as strings, numbers, or tuples.
- **Values** can be of any type, and they can be duplicated.

### Creating a Dictionary

You can use several methods to create a dictionary:

1. **Literal Definition**: Define key-value pairs within curly braces { }.

2. **From Key-Value Pairs**: Use the `dict()` constructor or the `{key: value}` shorthand.

3. **Using the `dict()` Constructor**: This can accept another dictionary, a sequence of key-value pairs, or named arguments.

4. **Comprehensions**: This is a concise way to create dictionaries using a single line of code.

5. **`zip()` Function**: This creates a dictionary by zipping two lists, where the first list corresponds to the keys, and the second to the values.

### Examples

#### Dictionary Literal Definition

Here is a Python code:

```python
# Dictionary literal definition
student = {
    "name": "John Doe",
    "age": 21,
    "courses": ["Math", "Physics"]
}
```

#### From Key-Value Pairs

Here is the Python code:

```python
# Using the `dict()` constructor
student_dict = dict([
    ("name", "John Doe"),
    ("age", 21),
    ("courses", ["Math", "Physics"])
])

# Using the shorthand syntax
student_dict_short = {
    "name": "John Doe",
    "age": 21,
    "courses": ["Math", "Physics"]
}
```

#### Using `zip()`

Here is a Python code:

```python
keys = ["a", "b", "c"]
values = [1, 2, 3]

zipped = zip(keys, values)
dict_from_zip = dict(zipped) # Result: {"a": 1, "b": 2, "c": 3}
```

#### Using `dict()` Constructor

Here is a Python code:

```python
# Sequence of key-value pairs
student_dict2 = dict(name="Jane Doe", age=22, courses=["Biology", "Chemistry"])

# From another dictionary
student_dict_combined = dict(student, **student_dict2)
```
<br>

## 10. What is the difference between _==_ and _is operator_ in _Python_?

Both the **`==`** and **`is`** operators in Python are used for comparison, but they function differently.

-  The **`==`** operator checks for **value equality**.
- The **`is`** operator, on the other hand, validates **object identity**,

In Python, every object is unique, identifiable by its memory address. The **`is`** operator uses this memory address to check if two objects are the same, indicating they both point to the exact same instance in memory.

- **`is`**: Compares the memory address or identity of two objects.
- **`==`**: Compares the content or value of two objects.

While **`is`** is primarily used for **None** checks, it's generally advisable to use **`==`** for most other comparisons.

### Tips for Using Operators

- **`==`**: Use for equality comparisons, like when comparing numeric or string values.
- **`is`**: Use for comparing membership or when dealing with singletons like **None**.
<br>

## 11. How does a _Python function_ work?

**Python functions** are the building blocks of code organization, often serving predefined tasks within modules and scripts. They enable reusability, modularity, and encapsulation.

### Key Components

- **Function Signature**: Denoted by the `def` keyword, it includes the function name, parameters, and an optional return type.
- **Function Body**: This section carries the core logic, often comprising conditional checks, loops, and method invocations.
- **Return Statement**: The function's output is determined by this statement. When None is specified, the function returns by default.
- **Local Variables**: These variables are scoped to the function and are only accessible within it.

### Execution Process

When a function is called:

1. **Stack Allocation**: A stack frame, also known as an activation record, is created to manage the function's execution. This frame contains details like the function's parameters, local variables, and **instruction pointer**.
  
2. **Parameter Binding**: The arguments passed during the function call are bound to the respective parameters defined in the function header.

3. **Function Execution**: Control is transferred to the function body. The statements in the body are executed in a sequential manner until the function hits a return statement or the end of the function body.

4. **Return**: If a return statement is encountered, the function evaluates the expression following the `return` and hands the value back to the caller. The stack frame of the function is then popped from the call stack.

5. **Post Execution**: If there's no `return` statement, or if the function ends without evaluating any return statement, `None` is implicitly returned.

### Local Variable Scope

- **Function Parameters**: These are a precursor to local variables and are instantiated with the values passed during function invocation.
- **Local Variables**: Created using an assignment statement inside the function and cease to exist when the function execution ends.
- **Nested Scopes**: In functions within functions (closures), non-local variables - those defined in the enclosing function - are accessible but not modifiable by the inner function, without using the `nonlocal` keyword.

### Global Visibility

If a variable is not defined within a function, the Python runtime will look for it in the global scope. This behavior enables functions to access and even modify global variables.

### Avoiding Side Effects

Functions offer a level of encapsulation, potentially reducing side effects by ensuring that data and variables are managed within a controlled environment. Such containment can help enhance the robustness and predictability of a codebase. As a best practice, minimizing the reliance on global variables can lead to more maintainable, reusable, and testable code.
<br>

## 12. What is a _lambda function_, and where would you use it?

A **Lambda function**, or **lambda**, for short, is a small anonymous function defined using the `lambda` keyword in Python.

While you can certainly use named functions when you need a function for something in Python, there are places where a lambda expression is more suitable.

### Distinctive Features

- **Anonymity**: Lambdas are not given a name in the traditional sense, making them suited for one-off uses in your codebase.
- **Single Expression Body**: Their body is limited to a single expression. This can be an advantage for brevity but a restriction for larger, more complex functions.
- **Implicit Return**: There's no need for an explicit `return` statement.
- **Conciseness**: Lambdas streamline the definition of straightforward functions.

### Common Use Cases

- **Map, Filter, and Reduce**: Functions like `map` can take a lambda as a parameter, allowing you to define simple transformations on the fly. For example, doubling each element of a list can be achieved with `list(map(lambda x: x*2, my_list))`.
- **List Comprehensions**: They are a more Pythonic way of running the same `map` or `filter` operations, often seen as an alternative to lambdas and `map`.
- **Sorting**: Lambdas can serve as a custom key function, offering flexibility in sort orders.
- **Callbacks**: Often used in events where a function is needed to be executed when an action occurs (e.g., button click).
- **Simple Functions**: For functions that are so basic that giving them a name, especially in more procedural code, would be overkill.

### Notable Limitations

- **Lack of Verbose Readability**: Named functions are generally preferred when their intended use is obvious from the name. Lambdas can make code harder to understand if they're complex or not used in a recognizable pattern.
- **No Formal Documentation**: While the function's purpose should be apparent from its content, a named function makes it easier to provide direct documentation. Lambdas would need a separate verbal explanation, typically in the code or comments.
<br>

## 13. Explain _*args_ and _**kwargs_ in _Python_.

In Python, `*args` and `**kwargs` are often used to pass a variable number of arguments to a function. 

`*args` collects a variable number of positional arguments into a **tuple**, while `**kwargs` does the same for keyword arguments into a **dictionary**.

Here are the key features, use-cases, and their respective code examples.

### **\*args**: Variable Number of Positional Arguments

- **How it Works**: The name `*args` is a convention. The asterisk (*) tells Python to put any remaining positional arguments it receives into a tuple.

- **Use-Case**: When the number of arguments needed is uncertain.

#### Code Example: "*args"

```python
def sum_all(*args):
    result = 0
    for num in args:
        result += num
    return result

print(sum_all(1, 2, 3, 4))  # Output: 10
```

### **\*\*kwargs**: Variable Number of Keyword Arguments

- **How it Works**: The double asterisk (**) is used to capture keyword arguments and their values into a dictionary.

- **Use-Case**: When a function should accept an arbitrary number of keyword arguments.

#### Code Example: "**kwargs"

```python
def print_values(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Keyword arguments are captured as a dictionary
print_values(name="John", age=30, city="New York")
# Output:
# name: John
# age: 30
# city: New York
```
<br>

## 14. What are _decorators_ in _Python_?

In Python, a **decorator** is a design pattern and a feature that allows you to modify functions and methods dynamically. This is done primarily to keep the code clean, maintainable, and DRY (Don't Repeat Yourself).

### How Decorators Work

- Decorators wrap a target function, allowing you to execute custom code before and after that function.
- They are typically **higher-order functions** that take a function as an argument and return a new function.
- This paradigm of "functions that modify functions" is often referred to as **metaprogramming**.

### Common Use Cases

- **Authorization and Authentication**: Control user access.
- **Logging**: Record function calls and their parameters.
- **Caching**: Store previous function results for quick access.
- **Validation**: Verify input parameters or function output.
- **Task Scheduling**: Execute a function at a specific time or on an event.
- **Counting and Profiling**: Keep track of the number of function calls and their execution time.

### Using Decorators in Code

Here is the Python code:

```python
from functools import wraps

# 1. Basic Decorator
def my_decorator(func):
    @wraps(func)  # Ensures the original function's metadata is preserved
    def wrapper(*args, **kwargs):
        print('Something is happening before the function is called.')
        result = func(*args, **kwargs)
        print('Something is happening after the function is called.')
        return result
    return wrapper

@my_decorator
def say_hello():
    print('Hello!')

say_hello()

# 2. Decorators with Arguments
def decorator_with_args(arg1, arg2):
    def actual_decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            print(f'Arguments passed to decorator: {arg1}, {arg2}')
            result = func(*args, **kwargs)
            return result
        return wrapper
    return actual_decorator

@decorator_with_args('arg1', 'arg2')
def my_function():
    print('I am decorated!')

my_function()
```

### Decorator Syntax in Python

The `@decorator` syntax is a convenient shortcut for:

```python
def say_hello():
    print('Hello!')
say_hello = my_decorator(say_hello)
```

### Role of **functools.wraps**

When defining decorators, particularly those that return functions, it is good practice to use `@wraps(func)` from the `functools` module. This ensures that the original function's metadata, such as its name and docstring, is preserved.
<br>

## 15. How can you create a _module_ in _Python_?

You can **create** a Python module through one of two methods:

- **Define**: Begin with saving a Python file with `.py` extension. This file will automatically function as a module. 

- **Create a Blank Module**: Start an empty file with no extension. Name the file using the accepted module syntax, e.g., `__init__ `, for it to act as a module. 

Next, use **import** to access the module and its functionality.

### Code Example: Creating a `math_operations` Module

#### Module Definition

Save the below `math_operations.py` file :

```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    return x / y
```

#### Module Usage

You can use `math_operations` module by using import as shown below:

```python
import math_operations

result = math_operations.add(4, 5)
print(result)

result = math_operations.divide(10, 5)
print(result)
```

Even though it is not required in the later **versions of Python**, you can also use statement `from math_operations import *` to import all the members such as functions and classes at once:

```python
from math_operations import *  # Not recommended generally due to name collisions and readability concerns

result = add(3, 2)
print(result)
```

### Best Practice
Before submitting the code, let's make sure to follow the **Best Practice**:

- **Avoid Global Variables**: Use a `main()` function.
- **Guard Against Code Execution on Import**: To avoid unintended side effects, use:

```python
if __name__ == "__main__":
    main()
```

This makes sure that the block of code following `if __name__ == "__main__":` is only executed when the module is run directly and not when imported as a module in another program.
<br>



#### Explore all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

