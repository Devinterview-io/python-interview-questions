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

Python is a **high-level, interpreted, general-purpose programming language** renowned for its **simplicity, readability, and extensive ecosystem**. Its design philosophy emphasizes code readability with its use of significant indentation.

Here are the key features of Python:

### Key Features of Python

#### Simplicity and Readability
Python's syntax is designed to be **highly readable and intuitive**, often compared to plain English. It uses **indentation** to define code blocks, which enforces a clean and consistent style, making it easier to write, understand, and maintain code.

```python
# Simple and readable syntax
name = "Alice"
if name == "Alice":
    print(f"Hello, {name}!")
else:
    print("Who are you?")
```

#### Versatility and General-Purpose
Python is a **general-purpose language**, meaning it can be used for a wide variety of applications across different domains. This includes web development (Django, Flask), data science and machine learning (NumPy, Pandas, TensorFlow), automation, scripting, game development, scientific computing, desktop GUIs, and more.

#### Interpreted Language
Python is an **interpreted language**, meaning source code is executed directly line by line by an interpreter, without an explicit compilation step into machine code beforehand. This leads to a faster development cycle and easier debugging.

#### Dynamically Typed
Python is **dynamically typed**, meaning the type of a variable is checked at runtime rather than at compile time. You don't need to declare the type of a variable explicitly; Python infers it based on the value assigned.

```python
# Dynamically typed
x = 10         # x is an integer
print(type(x))
x = "hello"    # x is now a string
print(type(x))
```

#### High-Level Language
Python is a **high-level language**, which means it abstracts away complex details of computer architecture and memory management. Developers can focus more on solving the problem at hand rather than low-level system details.

#### Object-Oriented Programming (OOP)
Python fully supports the **Object-Oriented Programming (OOP)** paradigm, allowing for modular and reusable code through concepts like classes, objects, inheritance, polymorphism, and encapsulation.

```python
# Simple class definition
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed

    def bark(self):
        return f"{self.name} says Woof!"

my_dog = Dog("Buddy", "Golden Retriever")
print(my_dog.bark())
```

#### Extensive Standard Library
Python comes with a **"batteries-included" philosophy**, offering a vast and comprehensive **standard library** that provides modules and packages for a wide range of tasks. This includes file I/O, networking, regular expressions, database access, web services, and more, reducing the need for external dependencies for many common tasks.

#### Cross-Platform Compatibility
Python is **cross-platform** (or platform-independent). Python programs can run on various operating systems, including Windows, macOS, Linux, and Unix, with little to no modification, as long as a Python interpreter is installed.

#### Open Source and Large Community
Python is **open-source**, meaning its source code is freely available for use and modification. This has fostered a **large and active global community** of developers who contribute to its development, create extensive documentation, provide support, and develop a wealth of third-party libraries and frameworks.

#### Embeddable and Extensible
Python can be **embedded** within other applications to provide scripting capabilities, and it can be **extended** with modules written in other languages (like C or C++) to perform computationally intensive tasks, allowing for performance optimization where needed.

#### Automatic Memory Management
Python features **automatic memory management** through a built-in garbage collector. Developers don't need to manually allocate or deallocate memory, which reduces common programming errors like memory leaks and dangling pointers, making development easier and safer.

### Conclusion
These key features collectively contribute to Python's popularity and versatility, making it an excellent choice for beginners and experienced developers alike across a multitude of domains, from small scripts to large-scale enterprise applications.
<br>

## 2. How is _Python_ executed?

Python execution is a multi-step process orchestrated by the **Python interpreter**. While often described as an **interpreted language**, Python actually involves an intermediate compilation step to **bytecode** before execution by a **virtual machine**.

Here's a detailed breakdown of how Python code is executed:

### **1. Source Code**
*   Python programs are initially written as **source code** files, typically with a `.py` extension. These files contain human-readable instructions following Python's syntax.

### **2. Lexing and Parsing**
*   When you execute a Python script (e.g., `python your_script.py`), the **Python interpreter** first reads the source code.
*   It performs **lexical analysis** (tokenizing the code into meaningful units like keywords, identifiers, operators, etc.) and **parsing** (checking the syntax and building an Abstract Syntax Tree - **AST**). This ensures the code is syntactically valid and represents a coherent program structure.

### **3. Compilation to Bytecode**
*   The interpreter then takes the AST and compiles it into **bytecode**.
*   **Bytecode** is a low-level, platform-independent representation of your Python source code. It's a set of instructions for the **Python Virtual Machine (PVM)**, much like assembly language for a physical CPU.
*   For imported modules, this bytecode is often cached in `.pyc` files (e.g., `your_module.cpython-3xx.pyc`) within a `__pycache__` directory. This caching mechanism helps speed up subsequent executions by skipping the lexical analysis, parsing, and compilation steps if the source code hasn't changed.
*   For top-level scripts executed directly, the bytecode is typically generated in memory and executed directly, without necessarily being saved to a `.pyc` file.

### **4. Execution by the Python Virtual Machine (PVM)**
*   The generated bytecode is then executed by the **Python Virtual Machine (PVM)**.
*   The PVM is a software component that acts as a runtime engine. It reads each bytecode instruction and performs the corresponding operation. These operations include manipulating objects, performing arithmetic, managing memory, calling functions, and interacting with the operating system (e.g., file I/O, network requests).
*   The PVM effectively translates the high-level Python operations into lower-level operations that the underlying operating system and hardware can understand.

### **5. Interaction with Underlying System and Libraries**
*   During execution, the PVM frequently interacts with the underlying operating system and external libraries. Many core Python functionalities and highly optimized libraries (especially in CPython) are implemented in C. The PVM handles the calls to these native components to perform tasks that cannot be handled by Python bytecode alone (e.g., direct system calls, complex mathematical computations, hardware interactions).

#### **Summary of the Execution Flow:**

```
Source Code (.py)
      ↓
Lexing & Parsing (builds AST)
      ↓
Compilation (to Bytecode)
      ↓
Bytecode (.pyc files / in-memory)
      ↓
Python Virtual Machine (PVM)
      ↓
Execution (with OS/Native library interaction)
      ↓
Result
```

### **Key Components and Concepts:**
*   **Python Interpreter:** The overall program that manages the entire process—reading, compiling, and executing Python code.
*   **Bytecode:** An intermediate, low-level, platform-independent representation of Python code, designed for efficient execution by the PVM.
*   **Python Virtual Machine (PVM):** The runtime environment that executes the bytecode instructions. It provides an abstraction layer between the bytecode and the underlying hardware/operating system.

### **Different Python Implementations:**

It's important to note that the description above primarily refers to **CPython**, which is the reference and most common implementation of Python (written in C). Other implementations exist, each with its own approach to execution:
*   **Jython:** Compiles Python code into Java bytecode, which is then executed by the Java Virtual Machine (JVM).
*   **IronPython:** Compiles Python code into Common Intermediate Language (CIL) bytecode, executed by the .NET Common Language Runtime (CLR).
*   **PyPy:** Uses a Just-In-Time (JIT) compiler. Instead of just interpreting bytecode, PyPy translates frequently executed bytecode segments into highly optimized machine code at runtime, often leading to significant performance improvements.
<br>

## 3. What is _PEP 8_ and why is it important?

### What is PEP 8?

**PEP** stands for **Python Enhancement Proposal**. These are design documents that provide information to the Python community or describe a new feature for Python, its processes, or environment.

**PEP 8** is the **style guide for Python code**. It provides a comprehensive set of recommendations on how to write Python code to ensure it is readable, consistent, and maintainable across the vast Python ecosystem. It was authored by Guido van Rossum, Barry Warsaw, and Nick Coghlan.

### Key Aspects of PEP 8

PEP 8 covers a wide array of stylistic recommendations, including but not limited to:

*   #### Code Layout
    *   **Indentation**: Use 4 spaces per indentation level.
    *   **Line Length**: Lines should ideally be limited to 79 characters.
    *   **Blank Lines**: Use blank lines to logically separate blocks of code or function/class definitions.
    *   **Whitespace**: Avoid superfluous whitespace in expressions and statements (e.g., `spam (1)` instead of `spam(1)`).
*   #### Naming Conventions
    *   **Modules**: `lowercase_with_underscores`.
    *   **Classes**: `CamelCase`.
    *   **Functions/Variables**: `lowercase_with_underscores`.
    *   **Constants**: `ALL_CAPS_WITH_UNDERSCORES`.
    *   **Private/Protected Members**: Prefix with single/double underscores (e.g., `_private_var`, `__mangled_var`).
*   #### Comments
    *   Write clear, concise, and up-to-date comments.
    *   Use **docstrings** for modules, classes, and functions to describe their purpose and usage.
*   #### Imports
    *   Place all imports at the top of the file.
    *   Group imports in the following order: standard library, third-party, and local application-specific imports.
    *   Use absolute imports primarily.

### Why is PEP 8 Important?

PEP 8 is fundamentally important for several reasons that contribute to the overall quality, efficiency, and collaborative nature of Python development:

*   #### Readability
    *   **Consistent Style**: By adhering to a common style, Python code becomes significantly easier to read and understand, regardless of who wrote it. This minimizes the **cognitive load** required to parse unfamiliar code. As PEP 8 itself famously states, "Readability counts."
    *   **Reduced Mental Effort**: Developers spend more time reading code than writing it. A consistent style makes the code's structure and intent more immediately apparent.
*   #### Maintainability
    *   **Reduced Errors**: Clean, consistent code is generally less prone to subtle bugs and easier to debug when issues arise.
    *   **Easier Refactoring and Extension**: When code adheres to a standard, modifying, extending, or refactoring it in the future becomes more straightforward and less error-prone.
*   #### Collaboration
    *   **Team Cohesion**: For teams, adopting PEP 8 ensures that all members are working with the same coding conventions, reducing debates over style during code reviews and fostering smoother teamwork.
    *   **Onboarding**: New team members can quickly get up to speed with an existing codebase if it follows a widely recognized and consistent standard like PEP 8.
*   #### Ecosystem Consistency
    *   **Open Source**: The vast majority of open-source Python projects follow PEP 8. This makes it easier for developers to contribute to various projects without needing to adapt to a unique style guide for each one.
    *   **Professionalism**: Adhering to a widely accepted standard demonstrates professionalism and attention to detail, indicating a commitment to high-quality code.
*   #### Tooling Support
    *   **Automated Checking and Formatting**: A rich ecosystem of tools leverages PEP 8 to assist developers. **Linters** like **Flake8** and **Pylint** can automatically check for PEP 8 compliance (and other code quality issues), while **code formatters** like **Black** and **autopep8** can automatically reformat code to adhere to PEP 8 guidelines. This automates much of the stylistic enforcement, allowing developers to focus on logic and functionality.

In summary, PEP 8 serves as the "common language" for Python code style, fostering a more consistent, readable, and maintainable ecosystem that benefits individual developers, teams, and the entire Python community.
<br>

## 4. How is memory allocation and garbage collection handled in _Python_?

Python's memory management is a sophisticated system that handles both the allocation and deallocation of memory for its objects. It primarily employs a **private heap space** for allocation and a combination of **reference counting** and a **generational cycle detector** for garbage collection.

### Memory Allocation

Python manages memory primarily through a **private heap space**. All Python objects and data structures reside in this private heap. The Python interpreter allocates and deallocates memory from this heap, abstracting the underlying operating system's memory management.

*   **Python's Private Heap**: This is a dedicated region of memory managed solely by the Python interpreter. Python programmers do not directly interact with this heap; instead, Python's object manager handles all memory operations within it.
*   **`pymalloc`**: For smaller objects (typically less than 512 bytes), Python uses a specialized memory allocator called `pymalloc`. This allocator is optimized for speed and space efficiency, reducing the overhead of repeated calls to the underlying `malloc` and `free` system calls. It pre-allocates large blocks of memory from the OS and then efficiently sub-allocates them for small Python objects, often pooling memory for objects of similar sizes.
*   **General-purpose allocator**: For larger objects, Python typically falls back to the system's standard `malloc` and `free` functions, relying on the operating system to manage these larger memory blocks.
*   **Object-centric Allocation**: Every piece of data in Python is an object, and each object carries its own memory overhead, including meta-information like its type, size, and most importantly, its reference count.

### Garbage Collection

Python employs a multi-pronged approach to garbage collection, primarily relying on **reference counting** and a **generational cycle detector**.

#### Reference Counting

This is the primary and most fundamental mechanism for garbage collection in Python.

*   **Mechanism**: Each Python object has a counter that tracks the number of references pointing to it. In CPython, this is an integer field within the object structure, often referred to as `ob_refcnt`.
*   **Incrementing/Decrementing**:
    *   The count **increases** when:
        *   An object is assigned to a new variable (e.g., `y = x`).
        *   It's passed as an argument to a function.
        *   It's inserted into a container (e.g., a list, dictionary, or tuple).
    *   The count **decreases** when:
        *   A variable referencing the object goes out of scope.
        *   A variable is re-assigned to a different object (e.g., `x = 10`).
        *   An object is explicitly deleted using `del` (which only removes the reference, not necessarily the object).
        *   An object is removed from a container.
*   **Deallocation**: When an object's reference count drops to **zero**, Python immediately deallocates the memory associated with it. This memory is then returned to the `pymalloc` or general-purpose allocator for reuse.
*   **Pros**:
    *   **Simplicity**: Conceptually easy to understand and implement.
    *   **Immediate Reclamation**: Memory is freed as soon as it's no longer referenced, minimizing memory footprints and preventing memory from accumulating unnecessarily.
*   **Cons**:
    *   **Overhead**: Every reference assignment or deletion requires updating the counter, which adds a slight performance overhead.
    *   **Cannot Detect Reference Cycles**: This is its major limitation. If two or more objects reference each other, forming a closed loop, their reference counts will never drop to zero, even if no external references point to the cycle. This leads to a memory leak.

#### Generational Cycle Detector

To address the major limitation of reference counting – its inability to collect **reference cycles** – Python introduces a supplementary garbage collector, which is a **generational, tracing garbage collector**.

*   **Reference Cycles**: Occur when objects directly or indirectly refer to each other, forming a closed loop, even if no external references point to the cycle. For example:
    ```python
    list_a = []
    list_b = []
    list_a.append(list_b)
    list_b.append(list_a)
    # Now, if list_a and list_b are no longer referenced externally,
    # their ref counts remain 1, preventing them from being collected by reference counting.
    del list_a, list_b
    ```
*   **Generations**: Objects are grouped into three generations (0, 1, 2) based on their age.
    *   **Generation 0**: Contains newly created objects.
    *   **Generation 1**: Contains objects that survived at least one Generation 0 collection.
    *   **Generation 2**: Contains objects that survived at least one Generation 1 collection.
    The intuition behind generations is that most objects have short lifespans ("die young"). Therefore, collecting Generation 0 frequently is efficient, while older objects are collected less often, reducing overall overhead.
*   **Detection Process**:
    1.  The collector maintains a list of "candidate" container objects (e.g., lists, dictionaries, instances of user-defined classes) that could potentially be part of a cycle and are eligible for collection.
    2.  When triggered (based on allocation/deallocation thresholds), it identifies all objects reachable from the "root set" (objects directly accessible to the program, like global variables, stack frames) and temporarily ignores objects that might be part of a cycle.
    3.  It then simulates the effect of removing all external references to these candidate objects by temporarily decrementing their reference counts.
    4.  Any objects whose reference count drops to zero after this simulated decrement are considered truly unreachable and not part of a cycle; they are collected by the standard reference counting mechanism.
    5.  Objects whose reference counts are still greater than zero after this process *must* be part of a reference cycle. These objects are then explicitly collected by the cycle detector.
    6.  The reference counts of other objects are restored.
*   **Triggering**: The cycle detector runs periodically when a certain number of object allocations and deallocations have occurred, specified by configurable thresholds (`gc.get_threshold()`). It runs more frequently for younger generations.
*   **Weak References**: Python's `weakref` module provides a way to create references to objects that do not increase their reference count. This is a manual technique that can be used to prevent reference cycles from forming in specific situations, especially when dealing with parent-child relationships where the child should not keep the parent alive.

### Conclusion

Python's memory management system is a robust, two-tiered approach: **reference counting** provides efficient and immediate reclamation for the vast majority of objects, while the **generational cycle detector** acts as a crucial safety net to identify and collect unreachable objects involved in reference cycles. This combination ensures efficient memory utilization and prevents common types of memory leaks, offering a good balance between performance and memory safety.
<br>

## 5. What are the _built-in data types_ in _Python_?

Python comes with several **built-in data types** that are fundamental for storing and organizing data. These types define the kind of value a variable can hold and the operations that can be performed on it. Understanding them is crucial for effective Python programming.

Here are the primary built-in data types in Python:

### 1. Numeric Types
Used to store numerical values.

#### `int` (Integers)
*   Represents whole numbers, positive or negative, without a decimal point.
*   Python integers have **arbitrary precision**, meaning their size is limited only by available memory.
*   **Immutable**.
```python
age = 30
big_number = 12345678901234567890
```

#### `float` (Floating-Point Numbers)
*   Represents real numbers (numbers with a decimal point) or numbers in exponential form.
*   Typically implement **double precision** (64-bit) floating-point numbers.
*   **Immutable**.
```python
price = 99.99
pi = 3.14159
```

#### `complex` (Complex Numbers)
*   Represents numbers with a real and an imaginary part, denoted by `j` or `J`.
*   **Immutable**.
```python
z = 3 + 4j
```

### 2. Sequence Types
Ordered collections of items that support indexing and slicing.

#### `str` (Strings)
*   An **immutable** sequence of **Unicode characters**.
*   Strings are enclosed in single quotes (`''`), double quotes (`""`), or triple quotes (`''' '''` or `""" """`).
```python
name = "Alice"
message = 'Hello World!'
```

#### `list` (Lists)
*   A **mutable** ordered sequence of items.
*   Lists can contain items of different data types and are defined by square brackets `[]`.
*   Support adding, removing, and changing elements.
```python
my_list = [1, "hello", 3.14, True]
my_list.append(5) # Modifies the list
```

#### `tuple` (Tuples)
*   An **immutable** ordered sequence of items, similar to lists.
*   Tuples are defined by parentheses `()` and are often used for heterogeneous collections where the elements' order and number are important.
*   Cannot be changed after creation.
```python
my_tuple = (1, "hello", 3.14)
# my_tuple.append(5) # This would raise an error as tuples are immutable
```

### 3. Mapping Type
An unordered collection of key-value pairs.

#### `dict` (Dictionaries)
*   A **mutable** collection of **key-value pairs**.
*   Each key must be unique and **immutable** (e.g., strings, numbers, tuples). Values can be of any type.
*   Dictionaries are defined by curly braces `{}`. As of Python 3.7+, dictionaries maintain **insertion order**.
```python
person = {"name": "Bob", "age": 25, "city": "New York"}
person["age"] = 26 # Modifies the dictionary
```

### 4. Set Types
Unordered collections of **unique** items.

#### `set` (Sets)
*   A **mutable** unordered collection of unique hashable items.
*   Duplicate elements are automatically removed.
*   Sets are defined by curly braces `{}` (for non-empty sets) or the `set()` constructor.
```python
unique_numbers = {1, 2, 3, 3, 4} # Results in {1, 2, 3, 4}
unique_numbers.add(5) # Modifies the set
```

#### `frozenset` (Frozen Sets)
*   An **immutable** version of a set.
*   Once created, its elements cannot be changed. This makes them suitable for use as dictionary keys or elements within other sets.
```python
immutable_set = frozenset({1, 2, 3})
# immutable_set.add(4) # This would raise an error
```

### 5. Boolean Type
Represents truth values.

#### `bool` (Booleans)
*   Represents one of two values: `True` or `False`.
*   Often the result of comparison operations or logical operations.
*   **Immutable**. `True` and `False` are instances of the `bool` type, which is a subclass of `int` (where `True` behaves like `1` and `False` like `0`).
```python
is_active = True
is_admin = False
```

### 6. None Type
Represents the absence of a value.

#### `NoneType` (None)
*   A unique constant `None` used to signify the absence of a value, a null operation, or an empty placeholder.
*   It's often used as a default value for function arguments or to initialize variables that will later hold a value.
*   `None` is the sole instance of the `NoneType` class.
*   **Immutable**.
```python
result = None
```

### Key Considerations
*   **Mutability vs. Immutability**: This is a critical distinction. **Mutable** objects (lists, dictionaries, sets) can be changed after creation, while **immutable** objects (numbers, strings, tuples, frozensets, booleans, None) cannot. This has implications for how they are passed to functions, stored in data structures (e.g., dictionary keys must be immutable), and memory management.
*   **Ordered vs. Unordered**: Sequence types (strings, lists, tuples) are ordered, meaning their elements have a defined position (index). Sets are unordered. Dictionaries are ordered by insertion (from Python 3.7+).
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

