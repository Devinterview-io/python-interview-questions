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

**Python** is a versatile and popular programming language known for its simplicity, **elegant syntax**, and a vast ecosystem of libraries. As of 2026, its relevance and adoption continue to grow across various industries. Let's look at some of the key features that make Python stand out.

### Key Features of Python

#### 1. Interpreted and Interactive

Python code is executed **line-by-line** by an interpreter, not compiled to machine code before runtime. This characteristic facilitates **rapid prototyping**, experimentation, and easier debugging, as errors are typically detected only when that specific line of code is executed. Python also provides an interactive shell where developers can execute commands and see results immediately.

```python
# Example of interactive mode
>>> print("Hello, Python!")
Hello, Python!
>>> x = 10
>>> y = 20
>>> x + y
30
```

#### 2. Easy to Learn and Read

Python's **clean, readable syntax** closely resembles plain English, significantly reducing the cognitive load for both beginners and experienced developers. Its mandatory use of **significant whitespace** (indentation) for defining code blocks enforces a consistent and highly readable code style, making it easier to maintain and understand code written by others.

#### 3. Cross-Platform Compatibility

Python is a **cross-platform language**, meaning code written on one operating system (e.g., Windows) can run seamlessly on others (e.g., Linux, macOS) without requiring platform-specific modifications. This "write once, run anywhere" capability is facilitated by the Python interpreter being available for diverse platforms.

#### 4. Modular and Scalable

Python promotes modular programming through **modules** and **packages**. Developers can organize code into reusable files (modules) and directories of modules (packages), which can then be easily imported and used in other parts of a project. This modularity enhances code organization, reusability, and maintainability, making Python suitable for developing **large-scale and complex applications**.

```python
# Example of importing a module
import math

radius = 5
area = math.pi * (radius ** 2)
print(f"Area of circle: {area}")
```

#### 5. Rich Library Ecosystem

The Python Package Index (PyPI) is a vast repository hosting over **500,000 libraries and frameworks** (and growing rapidly). This **extensive ecosystem** provides ready-to-use solutions for almost any programming task, from:
*   **Web Development**: Django, Flask, FastAPI
*   **Data Science & Analytics**: NumPy, Pandas, SciPy
*   **Machine Learning & AI**: TensorFlow, PyTorch, scikit-learn
*   **Automation**: Selenium, Ansible
*   **GUI Development**: PyQt, Kivy, Tkinter

This rich collection significantly speeds up development and innovation.

#### 6. General-Purpose and Versatile

Python is a **general-purpose programming language**, meaning it is not specialized for any single domain but is rather highly adaptable to a multitude of applications. Its versatility allows it to be effectively used in areas such as web and desktop applications, scientific and numerical computing, artificial intelligence and machine learning, data analysis, network programming, scripting, and automation.

#### 7. Automatic Memory Management

Python features **automatic memory management**, relieving developers from manual memory allocation and deallocation tasks. It primarily uses **reference counting** and a **generational garbage collector** to automatically detect and reclaim memory occupied by objects that are no longer referenced. This significantly reduces the chances of memory leaks and simplifies application development.

#### 8. Dynamically Typed

Python is a **dynamically typed language**, which means the type of a variable is determined at runtime, not at compile time. Developers do not need to explicitly declare the data type of a variable; Python infers it during execution. This offers flexibility and faster development cycles, though it can sometimes lead to type-related errors only detectable at runtime.

```python
# Example of dynamic typing
my_variable = 10         # my_variable is an integer
print(type(my_variable)) # Output: <class 'int'>

my_variable = "hello"    # Now my_variable is a string
print(type(my_variable)) # Output: <class 'str'>
```

#### 9. Object-Oriented Programming (OOP)

Python is a **multi-paradigm language** that fully supports and leverages the **object-oriented programming (OOP)** paradigm. In Python, everything is an **object**, and it facilitates concepts like **classes**, **objects**, **inheritance**, **polymorphism**, and **encapsulation**. This object-oriented nature helps in structuring complex applications into manageable and reusable components.

#### 10. Extensible & Embeddable

Python is highly **extensible**, allowing developers to integrate code written in other languages, particularly C and C++, for performance-critical tasks. This is commonly done using the **CPython C API**, `ctypes` module, or tools like **Cython**. Conversely, Python is also **embeddable**, meaning the Python interpreter can be integrated into applications written in other languages, allowing them to execute Python code and leverage its scripting capabilities.
<br>

## 2. How is _Python_ executed?

### How Python is Executed

Python source code undergoes a multi-stage process involving both **compilation** and **interpretation** before it can be executed. Understanding these stages is key to comprehending Python's performance characteristics and portability.

### Compilation & Interpretation

Python employs a hybrid execution model:

-   **Bytecode Compilation**: When a Python program is run, the source code (`.py` files) is first translated into an intermediate format called **bytecode**. This process is performed by the Python interpreter's **compiler component**. Bytecode is a low-level, platform-independent set of instructions, typically stored in `.pyc` files (Python compiled files) within `__pycache__` directories for faster loading on subsequent runs.
-   **Bytecode Interpretation**: The generated bytecode is then executed by the **Python Virtual Machine (PVM)**. The PVM is a runtime engine that reads and executes bytecode instructions one by one. This step-by-step execution is the "interpretation" phase.

This "compile-to-bytecode then interpret" approach is characteristic of many virtual machine-based languages and offers significant advantages.

### Bytecode versus Machine Code Execution

Some programming languages (like C++ or Rust) compile directly to **machine code**, which is specific to a computer's architecture (e.g., x86, ARM) and can be executed directly by the CPU. Python, on the other hand, compiles to **bytecode**.

-   **Performance**: The extra layer of abstraction introduced by the PVM interpreting bytecode *can* make standard Python implementations (like CPython) slower in certain CPU-bound scenarios compared to languages that compile directly to optimized machine code. However, constant improvements in CPython's interpreter and standard library, along with the increasing use of optimized C extensions, significantly mitigate this in many real-world applications.
-   **Portability**: The primary advantage of bytecode is its **platform independence**. A Python program's bytecode can be executed on any machine that has a compatible PVM, regardless of the underlying operating system or hardware architecture. This ensures excellent cross-platform support.

### Source Code to Bytecode: Compilation Steps

The process of translating Python source code into bytecode involves several standard compiler phases:

1.  #### Lexical Analysis (Scanning)
    The source code is broken down into a stream of **tokens**. Tokens are the smallest meaningful units in the language, such as keywords (`def`, `return`), identifiers (`example_func`), operators (`*`), and literals (`15`, `20`).
2.  #### Syntax Parsing
    The stream of tokens is then analyzed to ensure it conforms to Python's grammatical rules. This phase constructs an **Abstract Syntax Tree (AST)**, which is a hierarchical representation of the program's structure.
3.  #### Semantic Analysis
    The AST is checked for semantic correctness. This involves tasks like ensuring variables are defined before use, type checking (where applicable), and verifying that operations are valid for their operands. Python performs some semantic checks at this stage, though many type-related checks occur at runtime due to its dynamic nature.
4.  #### Bytecode Generation
    Finally, based on the validated AST, the **bytecode instructions** are generated. These instructions are tailored for execution by the PVM.

### Just-In-Time (JIT) Compilation and Alternative Implementations

While the default CPython interpreter primarily relies on bytecode interpretation, the concept of **Just-In-Time (JIT) compilation** is highly relevant to Python's execution ecosystem.

-   **JIT's Role**: A JIT compiler compiles parts of the bytecode into native machine code *during runtime*, typically focusing on frequently executed sections (hot paths). This can significantly boost performance by eliminating the overhead of bytecode interpretation for those sections.
-   **CPython vs. JIT**: It's crucial to note that **standard CPython does not include a JIT compiler** as of 2026. CPython's performance improvements mostly come from optimizing its interpreter loop, specializing opcodes, and better memory management.
-   **Alternative Implementations**: JIT compilation is a core feature of alternative Python implementations like **PyPy**. PyPy's JIT compiler often delivers substantial speedups for pure Python code compared to CPython, especially for long-running processes with repetitive computations. Other projects and experimental CPython forks might explore JIT integration in the future, but it's not a standard feature of the mainstream CPython distribution.

Therefore, when discussing "how Python is executed," it's generally understood to refer to CPython's bytecode interpretation model, while acknowledging that other implementations leverage JIT for enhanced performance.

### Code Example: Disassembly of Bytecode

Python's `dis` module allows us to inspect the bytecode generated for a function or code object, providing a direct view into the instructions the PVM will execute.

```python
import dis

def calculate_product():
    a = 15
    b = 20
    return a * b

# Disassemble to view bytecode instructions
dis.dis(calculate_product)
```

Here's the disassembled output for the `calculate_product` function:

```plaintext
  4           0 LOAD_CONST               1 (15) # Load integer 15
              2 STORE_FAST               0 (a)  # Store it in local variable 'a'

  5           4 LOAD_CONST               2 (20) # Load integer 20
              6 STORE_FAST               1 (b)  # Store it in local variable 'b'

  6           8 LOAD_FAST                0 (a)  # Load value of 'a'
             10 LOAD_FAST                1 (b)  # Load value of 'b'
             12 BINARY_MULTIPLY                 # Multiply the top two values on stack
             14 RETURN_VALUE                    # Return the result
```

This output clearly shows the PVM instructions for loading constants, storing them in local variables, loading the variables again, performing the multiplication, and finally returning the value. This granular view demonstrates the step-by-step nature of bytecode execution.
<br>

## 3. What is _PEP 8_ and why is it important?

### What is PEP 8 and why is it important?

**PEP 8** is the official style guide for Python code. Its primary purpose is to promote code consistency, readability, and maintainability across the Python community. The name stands for **P**ython **E**nhancement **P**roposal, and PEPs are the primary mechanism for proposing and standardizing new features, changes, and conventions for the Python language itself.

While not a rigid set of mandatory rules, PEP 8 provides comprehensive guidelines that help developers write Python code that is visually uniform and thus significantly easier to understand, navigate, and debug for anyone reading it. Adherence to PEP 8 fosters a common coding style, reducing cognitive load when moving between different Python projects or collaborating with other developers.

### Key Design Principles

PEP 8's recommendations are rooted in several fundamental design principles:

*   #### Readability
    Code should be as easy to read and understand as plain English, even by someone unfamiliar with the codebase or the original author. Clear and consistent formatting significantly contributes to this.
*   #### Consistency
    A codebase should adhere to a predictable and uniform style. This minimizes surprises and allows developers to focus on the logic rather than deciphering varied formatting choices.
*   #### Maintainability
    Consistent and readable code is inherently easier to maintain, update, and debug over time. It reduces the effort required to onboard new team members and ensures the longevity of the software.
*   #### Explicit over Implicit
    Python's philosophy often favors explicit code over implicit code. PEP 8 extends this by encouraging clear and unambiguous formatting.

### Core Guidelines

PEP 8 covers a wide range of formatting conventions. Some of the most frequently applied guidelines include:

*   #### Indentation
    Use **4 spaces** per level of logical indentation. Tabs should be avoided entirely for indentation.
    ```python
    # PEP 8 compliant indentation
    def example_function(arg1, arg2):
        if arg1 > arg2:
            print("arg1 is greater")
        else:
            print("arg2 is greater or equal")
    ```
*   #### Line Length
    Limit all lines of code to a maximum of **79 characters**. For docstrings and comments, the limit is often recommended to be **72 characters**. This guideline improves readability, especially when viewing code on smaller screens or in side-by-side diffs. While the official PEP 8 recommendation remains 79 characters, it's worth noting that many modern Python projects, especially those using auto-formatters like `Black` or `Ruff`, often adopt slightly longer line lengths (e.g., 88 or 120 characters) for practical reasons, as long as readability isn't compromised.
*   #### Blank Lines
    Use blank lines to separate logical sections of code, such as functions, classes, and larger blocks within functions. Generally, two blank lines separate top-level function and class definitions, and one blank line separates method definitions within a class. Avoid excessive blank lines.
*   #### Imports
    Imports should typically be on separate lines and grouped as follows: standard library imports, third-party imports, and local application-specific imports. Each group should be separated by a blank line.
    ```python
    import os
    import sys

    import requests
    from numpy import array

    from my_package.my_module import MyClass
    ```

### Naming Styles

Naming conventions are critical for understanding the purpose of different code elements.

*   #### Class Names
    Use `CapWords` (also known as `CamelCase`), where each word in the name starts with a capital letter.
    *   `class MyClassName:`
    *   `class HTTPRequest:`
*   #### Function and Variable Names
    Use `snake_case` (all lowercase with words separated by underscores).
    *   `def my_function():`
    *   `variable_name = 10`
*   #### Module Names
    Use short, all-lowercase names. Underscores can be used if it improves readability for multi-word module names.
    *   `import mymodule`
    *   `import another_module`
*   #### Constants
    Use `ALL_CAPS_WITH_UNDERSCORES` to denote constants (variables whose values are intended to remain unchanged throughout the program's execution).
    *   `MAX_CONNECTIONS = 100`
    *   `DEFAULT_TIMEOUT = 30`

### Documentation

*   #### Docstrings
    Use triple-quoted strings (`"""Docstring content"""` or `'''Docstring content'''`) for documentation strings (docstrings) for modules, classes, functions, and methods. These explain the purpose and usage of the code.
*   #### Comments
    Comments (`#`) should be used to explain *why* certain code exists or how a complex piece of code works, rather than just *what* it does (which should be evident from the code itself). They should be concise, up-to-date, and on their own line preceding the code they refer to.

### Whitespace Usage

Appropriate use of whitespace enhances readability around operators and punctuation.

*   #### Operators
    Surround binary operators (e.g., `=`, `+`, `-`, `*`, `/`, `==`, `>`, `<`, `and`, `or`) with a single space on either side.
    *   `x = 1 + 2`
    *   `if a == b:`
*   #### Commas, Semicolons, Colons
    Always follow a comma, semicolon, or colon with a space. Avoid spaces before them.
    *   `my_list = [1, 2, 3]`
    *   `def func(arg1, arg2):`
*   #### Parentheses, Brackets, Braces
    Avoid extraneous whitespace immediately inside parentheses, brackets, or braces.
    *   `my_list[index]` (not `my_list[ index ]`)
    *   `my_tuple = (1, 2)` (not `my_tuple = ( 1, 2 )`)

### Example: PEP 8 Compliant Directory Walker

The following Python code snippet adheres to several PEP 8 guidelines, demonstrating proper indentation, naming conventions, and spacing.

```python
import os

def walk_directory_and_print_files(base_path):
    """
    Recursively walks a given directory path and prints the full path of each file found.

    Args:
        base_path (str): The starting directory path to walk.
    """
    for dirpath, dirnames, filenames in os.walk(base_path):
        for filename in filenames:
            file_path = os.path.join(dirpath, filename)
            # This print statement is for demonstration; in a real app,
            # you might process the file_path further.
            print(f"Found file: {file_path}")

# Example usage (replace with an actual path for execution)
# Ensure the path exists, e.g., 'C:/Users/YourUser/Documents' or '/home/user/my_docs'
if __name__ == "__main__":
    # You might get this path from user input or configuration
    test_path = './my_test_dir' # Current directory example
    
    # Create a dummy directory and file for demonstration if it doesn't exist
    if not os.path.exists(test_path):
        os.makedirs(test_path)
        with open(os.path.join(test_path, 'example.txt'), 'w') as f:
            f.write("Hello PEP 8!")
    
    walk_directory_and_print_files(test_path)
```
<br>

## 4. How is memory allocation and garbage collection handled in _Python_?

In Python, **memory allocation** and **garbage collection** are handled automatically and transparently by the Python interpreter, abstracting these complexities away from the developer. This significantly reduces the likelihood of memory-related bugs like leaks or segmentation faults.

### Memory Allocation

Python manages its own private heap space, where all Python objects (e.g., integers, strings, lists, dictionaries, custom objects) reside. The **Python Memory Manager** is responsible for allocating and deallocating memory within this heap.

#### Specialized Allocators

To optimize performance for various object sizes, Python employs a tiered memory allocation strategy:

*   **`pymalloc` (or `obmalloc`)**: For small and medium-sized objects (typically less than 512 bytes), Python uses a specialized allocator known as `pymalloc` (historically) or more generally, the `obmalloc` system in CPython. This system pre-allocates large blocks of memory from the operating system (called **arenas**) and then subdivides them into smaller fixed-size **pools** and **blocks**. This greatly reduces the overhead of frequent small allocations and deallocations, as Python reuses these internal memory blocks efficiently. This mechanism is crucial for the performance of typical Python programs that create many small objects.
*   **System `malloc`**: For larger objects (greater than 512 bytes) or when the `pymalloc` system cannot satisfy a request, Python directly falls back to the underlying operating system's memory allocator (e.g., `malloc` and `free` from the C standard library like `Glibc`).

#### Stack vs. Heap

It's important to distinguish between the **stack** and the **heap**:

*   **Stack**: The call stack stores function call frames, local variables, and references to objects. Variables on the stack are typically primitives or pointers/references to objects.
*   **Heap**: This is where all actual Python objects are stored. Python's memory manager exclusively deals with the **Python private heap**. When a Python variable is created, it's typically a reference on the stack pointing to an object on the heap.

```python
# Example of object creation and memory allocation
my_list = [1, 2, 3] # A list object is allocated on the heap.
                   # 'my_list' is a reference on the stack pointing to this object.

my_dict = {'a': 1, 'b': 2} # A dictionary object is allocated on the heap.

# Small integers (and some strings) are often interned for efficiency,
# meaning they are pre-allocated and reused.
x = 10
y = 10 # x and y might point to the same integer object on the heap
```

### Garbage Collection

Python employs a hybrid approach to garbage collection, combining **reference counting** with a **cycle-detecting garbage collector**.

#### Reference Counting

*   **Mechanism**: Every Python object maintains a **reference count**, which tracks how many references (variables, container elements, etc.) point to it. When an object is created, its reference count is 1. When a new reference points to it, the count increments; when a reference is removed (e.g., variable goes out of scope, `del` keyword used, reference reassigned), the count decrements.
*   **Deallocation**: When an object's reference count drops to zero, it means no active references point to it, making it unreachable. The object is then immediately deallocated, and its memory is returned to the `pymalloc` system or the OS.
*   **Efficiency**: Reference counting is generally very efficient and allows for prompt memory reclamation. Most objects are deallocated as soon as they become unreachable.

```python
import sys

# An empty list object is created
a = []
print(f"Reference count for a after creation: {sys.getrefcount(a) - 1}") # -1 for temporary ref from getrefcount

# Another reference to the same list object
b = a
print(f"Reference count after b = a: {sys.getrefcount(a) - 1}")

# Remove reference b
del b
print(f"Reference count after del b: {sys.getrefcount(a) - 1}")

# Once 'a' is also deleted or reassigned, the count will drop to 0,
# and the list object will be deallocated.
```

#### Cycle-Detecting Garbage Collector

*   **Problem**: Reference counting alone cannot detect and reclaim memory occupied by **circular references**. A circular reference occurs when two or more objects refer to each other, forming a closed loop, even if no external references point to the cycle. In such cases, the reference count of each object within the cycle might never drop to zero, leading to a memory leak.
*   **Solution**: Python includes a separate, optional, **generational garbage collector** designed to identify and collect these uncollectable cycles.
    *   **Generations**: The collector categorizes objects into three generations (0, 1, and 2) based on their age. New objects start in generation 0. If an object survives a collection in generation 0, it's promoted to generation 1, and so on. Older generations are collected less frequently because objects that have survived longer are less likely to be part of a temporary cycle.
    *   **Collection Process**: When invoked (either automatically or manually via `gc.collect()`), the collector traverses object graphs to find unreachable cycles. It temporarily unlinks references within potential cycles to see if any object's reference count drops to zero. If so, those objects are deemed part of an uncollectable cycle and are deallocated.
*   **Performance**: Cycle detection is a more computationally intensive process than reference counting, so it runs much less frequently. The `gc` module provides an interface to control and inspect the garbage collector.

```python
import gc

class Node:
    def __init__(self, value):
        self.value = value
        self.next = None # Reference to another Node
        # print(f"Node {self.value} created") # For demonstration

    def __del__(self):
        # This destructor will be called when the object is truly deallocated
        print(f"Node {self.value} destroyed")

# Disable automatic garbage collection for clearer demonstration
gc.disable()

n1 = Node(1)
n2 = Node(2)

n1.next = n2
n2.next = n1 # Circular reference: n1 -> n2 -> n1

print("References created. Objects n1 and n2 still exist in memory.")

del n1
del n2 # Variables n1 and n2 are deleted, but the objects themselves are not __del__-ed

print("Local references n1 and n2 are gone, but objects still exist due to circularity.")

# The objects n1 and n2 are still alive because their reference counts within the cycle
# prevent them from being zero, even though no external references point to the cycle.

print("\nRunning cycle-detecting garbage collector...")
gc.collect() # This will detect the cycle and deallocate the objects,
             # triggering their __del__ methods.

gc.enable() # Re-enable garbage collection
```

### Memory Management in Python vs. C/C++

Python's approach to memory management differs significantly from lower-level languages like C or C++:

*   **Automation vs. Manual Control**: Python provides **automatic memory management**, relieving developers from explicitly allocating (`malloc`/`new`) or deallocating (`free`/`delete`) memory. This contrasts sharply with C/C++, where manual memory management is a core responsibility.
*   **Reduced Bugs**: The automation in Python greatly reduces the risk of common memory-related bugs such as memory leaks, double-frees, or dangling pointers.
*   **Performance and Overhead**:
    *   Python's general-purpose memory manager, combined with the overhead of dynamic typing, reference counting, and the cycle-detecting garbage collector, can result in higher memory consumption and potentially slower performance compared to finely tuned C/C++ applications.
    *   Each Python object also carries additional overhead (e.g., type information, reference count) that isn't present in raw C data structures.
*   **Developer Productivity**: The trade-off is a significant boost in **developer productivity** and ease of use, as developers can focus on application logic rather than intricate memory handling.
<br>

## 5. What are the _built-in data types_ in _Python_?

Python offers numerous **built-in data types** that provide varying functionalities and utilities. These types are fundamental to programming in Python and can be broadly categorized into immutable and mutable types, depending on whether their state can be changed after creation.

### Immutable Data Types
Immutable objects cannot be modified after they are created. Any operation that appears to modify an immutable object actually creates a new object.

#### 1. int
Represents **whole numbers** (integers) of arbitrary precision. There is no practical limit to how large an integer value can be, other than the available memory.
```python
x = 42
print(type(x)) # <class 'int'>
```

#### 2. float
Represents **floating-point numbers** (decimal numbers). Python's `float` type typically implements the IEEE 754 double-precision standard.
```python
pi = 3.14159
print(type(pi)) # <class 'float'>
```

#### 3. complex
Represents **complex numbers**, comprising a real and an imaginary part. The imaginary part is denoted by `j` or `J`.
```python
z = 3 + 4j
print(type(z)) # <class 'complex'>
```

#### 4. bool
Represents **boolean values**, which can be either `True` or `False`. `bool` is a subclass of `int`, where `True` is equivalent to `1` and `False` to `0`.
```python
is_active = True
is_empty = False
print(type(is_active)) # <class 'bool'>
```

#### 5. str
Represents **sequences of Unicode characters**, used for text. String literals are enclosed within single quotes, double quotes, or triple quotes.
```python
message = "Hello, Python!"
print(type(message)) # <class 'str'>
```

#### 6. tuple
An **ordered, immutable collection** of items. Tuples can contain heterogeneous data types and are typically enclosed within parentheses.
```python
coords = (10, 20, 'north')
print(type(coords)) # <class 'tuple'>
```

#### 7. frozenset
An **immutable version of a `set`**. It is a collection of unique, hashable objects and cannot be modified after creation. `frozenset` objects are created using the `frozenset()` constructor.
```python
immutable_items = frozenset([1, 2, 3, 2])
print(immutable_items) # frozenset({1, 2, 3})
print(type(immutable_items)) # <class 'frozenset'>
```

#### 8. bytes
Represents an **immutable sequence of 8-bit bytes**. It is primarily used to handle binary data. `bytes` literals are prefixed with `b`.
```python
binary_data = b'hello'
print(type(binary_data)) # <class 'bytes'>
```

#### 9. NoneType
The type of the **`None` object**, which indicates the absence of a value or a null value. `None` is a singleton object.
```python
result = None
print(type(result)) # <class 'NoneType'>
```

#### 10. type
The **metaclass** for all new-style classes in Python. It is the type of types themselves.
```python
t = type(10) # t is <class 'int'>
print(type(t)) # <class 'type'>
```

#### 11. object
The **base class** from which all other classes in Python implicitly or explicitly inherit. It is the root of the class hierarchy.
```python
o = object()
print(type(o)) # <class 'object'>
```

### Mutable Data Types
Mutable objects can be modified after they are created. Changes made to a mutable object directly affect the object's state.

#### 1. list
An **ordered, mutable collection** of items. Lists are highly versatile, can contain heterogeneous data types, and offer dynamic sizing. They are enclosed within square brackets.
```python
my_list = [1, 'two', 3.0, [4, 5]]
my_list.append(6)
print(type(my_list)) # <class 'list'>
```

#### 2. set
An **unordered, mutable collection of unique, hashable objects**. Sets are useful for operations like membership testing, removing duplicates, and mathematical set operations. They are characterized by curly braces.
```python
unique_numbers = {1, 2, 3, 2}
unique_numbers.add(4)
print(unique_numbers) # {1, 2, 3, 4} (order may vary)
print(type(unique_numbers)) # <class 'set'>
```

#### 3. dict
A **key-value paired collection** that is mutable and since Python 3.7+, insertion-ordered. Keys must be unique and hashable, while values can be of any type. Dictionaries are enclosed within curly braces.
```python
person = {'name': 'Alice', 'age': 30, 'city': 'New York'}
person['age'] = 31
print(type(person)) # <class 'dict'>
```

#### 4. bytearray
A **mutable version of the `bytes` type**. It represents a mutable sequence of 8-bit bytes and allows in-place modification of binary data.
```python
mutable_binary = bytearray(b'world')
mutable_binary[0] = ord('W')
print(mutable_binary) # bytearray(b'World')
print(type(mutable_binary)) # <class 'bytearray'>
```

#### 5. memoryview
A **built-in type that exposes the buffer protocol** of an object (like `bytes` or `bytearray`). It allows direct access to an object's internal data without copying, aiding efficient viewing and manipulation of large data blocks.
```python
data = bytearray(b'abcdef')
mv = memoryview(data)
print(mv[0]) # 97 (ASCII for 'a')
mv[0] = 100 # Change 'a' to 'd'
print(data) # bytearray(b'dbcdef')
print(type(mv)) # <class 'memoryview'>
```

#### 6. array.array
The `array` module provides an **array type that can store a sequence of items of a single, specified numeric type**. It is similar to a `list` but is more memory-efficient for storing large numbers of homogeneous elements. It must be imported from the `array` module.
```python
import array
my_array = array.array('i', [1, 2, 3, 4]) # 'i' for signed int
my_array.append(5)
print(type(my_array)) # <class 'array.array'>
```

#### 7. collections.deque
The `collections` module provides `deque` (double-ended queue), which is a **list-like container with optimized appends and pops from both ends** with approximately O(1) performance. It must be imported from the `collections` module.
```python
from collections import deque
my_deque = deque([1, 2, 3])
my_deque.appendleft(0) # [0, 1, 2, 3]
my_deque.pop()       # 3
print(type(my_deque)) # <class 'collections.deque'>
```

#### 8. types.SimpleNamespace
The `types` module provides `SimpleNamespace`, which is a **simple `object` subclass that allows arbitrary attribute assignment**. It's useful for creating lightweight data objects. It must be imported from the `types` module.
```python
import types
ns = types.SimpleNamespace(a=1, b='hello')
ns.c = [1, 2, 3]
print(ns.a, ns.b, ns.c) # 1 hello [1, 2, 3]
print(type(ns)) # <class 'types.SimpleNamespace'>
```

#### 9. types.ModuleType
The `types` module provides `ModuleType`, which is the **type of all modules**. It represents the actual module object loaded into Python. It must be imported from the `types` module.
```python
import sys
module_type_example = type(sys)
print(module_type_example) # <class 'module'>
print(type(module_type_example)) # <class 'type'> (ModuleType itself is a type)
```

#### 10. types.FunctionType
The `types` module provides `FunctionType`, which is the **type of user-defined functions**. It represents callable objects created with `def`. It must be imported from the `types` module.
```python
import types
def my_function():
    pass
func_type_example = type(my_function)
print(func_type_example) # <class 'function'>
print(type(func_type_example)) # <class 'type'> (FunctionType itself is a type)
```
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

