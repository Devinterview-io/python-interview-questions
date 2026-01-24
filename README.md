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

Let's look at the difference between **mutable** and **immutable** objects in Python. This distinction is fundamental to understanding how data is stored, manipulated, and passed around in Python programs.

### Core Definition

The primary difference lies in whether an object's state can be altered after its creation.

#### Mutable Objects
A **mutable object** is an object whose state or content can be changed after it has been created. When a mutable object is modified, its identity (memory address) remains the same, but its value changes. Any variable referencing this object will see the change.

#### Immutable Objects
An **immutable object** is an object whose state or content cannot be changed after it has been created. If an operation appears to "modify" an immutable object, it actually creates a *new* object with the desired changes, and the original object remains untouched. Variables are then re-bound to this new object.

### Common Examples

#### Mutable Types
*   **Lists** (`list`): Ordered, changeable sequence of items.
*   **Sets** (`set`): Unordered collection of unique, mutable items.
*   **Dictionaries** (`dict`): Unordered collection of key-value pairs, where keys must be immutable and unique.
*   **Bytearrays** (`bytearray`): Mutable sequence of bytes.
*   Most custom class instances (unless specifically designed to be immutable).

#### Immutable Types
*   **Numbers** (`int`, `float`, `complex`): Integers, floating-point numbers, and complex numbers.
*   **Strings** (`str`): Ordered, immutable sequence of characters.
*   **Tuples** (`tuple`): Ordered, immutable sequence of items. (Note: A tuple itself is immutable, but if it contains mutable objects, those mutable objects can still be changed).
*   **Frozensets** (`frozenset`): Unordered collection of unique, immutable items.
*   **Bytes** (`bytes`): Immutable sequence of bytes.
*   **Booleans** (`bool`): `True` and `False`.
*   **None** (`NoneType`).

### Code Example: Illustrating Mutability and Immutability in Python

```python
import sys

# --- Immutable objects (int, str, tuple) ---
print("--- Immutable Objects ---")
num = 42
text = "Hello"
my_tuple = (1, [2, 3], 4) # Tuple itself is immutable, but contains a mutable list

print(f"Initial num: {num}, id: {id(num)}")
print(f"Initial text: '{text}', id: {id(text)}")
print(f"Initial my_tuple: {my_tuple}, id: {id(my_tuple)}")

# Attempting to "modify" num (reassignment creates a new object)
num += 10 # This is syntactic sugar for num = num + 10
print(f"After num += 10: {num}, id: {id(num)} (id changed, new object created)")

try:
    # Trying to modify a string (will raise TypeError)
    # Strings do not support item assignment
    # text[0] = 'M'
    pass # Commenting out to allow script to run, but conceptually this fails
except TypeError as e:
    print(f"Error modifying string: {e}")

try:
    # Trying to modify a tuple (will raise TypeError)
    my_tuple[0] = 100
except TypeError as e:
    print(f"Error modifying tuple element: {e}")

# However, elements *within* a mutable object inside an immutable tuple can be changed
print(f"Mutable list inside tuple before change: {my_tuple[1]}, id: {id(my_tuple[1])}")
my_tuple[1].append(5) # This modifies the list object, not the tuple
print(f"Mutable list inside tuple after change: {my_tuple[1]}, id: {id(my_tuple[1])} (id of list unchanged)")
print(f"my_tuple after internal list modification: {my_tuple}, id: {id(my_tuple)} (tuple id unchanged)")


# --- Mutable objects (list, dict, set) ---
print("\n--- Mutable Objects ---")
my_list = [1, 2, 3]
my_dict = {'a': 1, 'b': 2}
my_set = {10, 20}

print(f"Initial my_list: {my_list}, id: {id(my_list)}")
print(f"Initial my_dict: {my_dict}, id: {id(my_dict)}")
print(f"Initial my_set: {my_set}, id: {id(my_set)}")

# Modifications happen in-place; object ID remains the same
my_list.append(4)
my_dict['c'] = 3
my_set.add(30)

print(f"After append my_list: {my_list}, id: {id(my_list)} (id unchanged)")
print(f"After add 'c' my_dict: {my_dict}, id: {id(my_dict)} (id unchanged)")
print(f"After add 30 my_set: {my_set}, id: {id(my_set)} (id unchanged)")

# Example of aliasing with mutable objects
list_a = [1, 2]
list_b = list_a # list_b now refers to the *same* object as list_a
print(f"list_a: {list_a}, id: {id(list_a)}")
print(f"list_b: {list_b}, id: {id(list_b)}")

list_b.append(3) # Modifies the object referenced by both list_a and list_b
print(f"After list_b.append(3):")
print(f"list_a: {list_a}, id: {id(list_a)}") # list_a is also changed!
print(f"list_b: {list_b}, id: {id(list_b)}")
```

### Key Implications and Use Cases

#### Hashability
*   **Immutable objects** are **hashable**. This means they have a hash value that never changes during their lifetime. This property is crucial for using them as keys in dictionaries and elements in sets, as these data structures rely on hashing for efficient lookups.
*   **Mutable objects** are **not hashable** by default because their hash value would change if their content changed, making them unreliable for lookup operations. Consequently, mutable objects like lists, sets, and dictionaries cannot be used as dictionary keys or set members.

#### Thread Safety
*   **Immutable objects** are inherently **thread-safe**. Since their state cannot change after creation, multiple threads can access them concurrently without the need for locks or synchronization mechanisms, simplifying concurrent programming.
*   **Mutable objects** are **not thread-safe** by default. If multiple threads access and modify the same mutable object without proper synchronization, race conditions can occur, leading to unpredictable behavior and data corruption.

#### Predictability and Debugging
*   **Immutable objects** contribute to more **predictable code**. Their fixed state makes it easier to reason about program flow and trace data transformations, as an object's value will not unexpectedly change from another part of the program. This often leads to fewer bugs related to side effects.
*   **Mutable objects**, while powerful, can introduce **side effects**. If a mutable object is passed around and modified by different functions, it can be challenging to track its state and debug issues arising from unintended modifications.

#### Performance and Memory
*   **Mutable objects** can be more **memory-efficient** for in-place updates, especially for large datasets. Modifying a mutable object avoids the overhead of creating a new object and garbage collecting the old one.
*   **Immutable objects** might incur memory and performance overhead if "modifications" lead to frequent creation of new objects. However, immutability can also enable optimizations such as object sharing (multiple references pointing to the same immutable object) or caching of computed values, as their state is guaranteed not to change. Python internally caches small integers and strings for this reason.

Choosing between mutable and immutable objects depends on the specific requirements of the program, balancing considerations like data integrity, concurrent access patterns, and performance characteristics.
<br>

## 7. How do you _handle exceptions_ in _Python_?

**Exception handling** is a fundamental aspect of Python, and it safeguards your code against unexpected errors or conditions. It allows programs to gracefully recover from errors, rather than crashing, and provides mechanisms to perform necessary cleanup operations. Key components of exception handling in Python include:

### Components

-   **Try**: The section of code where exceptions might occur is placed within a `try` block. If an exception occurs in this block, the execution flow is immediately transferred to the corresponding `except` block.

-   **Except**: Any possible exceptions that are `raised` by the `try` block are caught and handled in the `except` block. You can specify which type of exception to catch, or catch multiple types.

-   **Finally**: This block ensures a piece of code always executes, regardless of whether an exception occurred in the `try` block or was caught by an `except` block. It's commonly used for cleanup operations, such as closing files or database connections, to ensure resources are properly released.

### Generic Exception Handling vs. Handling Specific Exceptions

It's good practice to **handle** specific exceptions to provide tailored responses to different error conditions. However, a more **general** approach can also be taken. When combining specific and general exception handlers, ensure that the most specific `except` blocks come first, and the more **general** `except Exception as e` block is placed at the end of the chain. This ensures that specific error conditions are addressed before being caught by a broader handler.

```python
try:
    risky_operation()
except IndexError:  # Handle specific exception types first.
    handle_index_error()
except ValueError: # Another specific exception
    handle_value_error()
except Exception as e:  # More general exception must come last.
    # This will catch any other exception not caught by the specific handlers above
    print(f"An unexpected error occurred: {e}")
    handle_generic_error(e)
finally:
    cleanup() # This always executes
```

### Raising Exceptions

You can use the `raise` statement to **trigger and manage** exceptions under specific circumstances. This is particularly useful when building custom classes or functions where specific conditions should be met, and a failure to meet them warrants an immediate halt and error notification.

**Raise** a specific exception:

```python
def divide(a, b):
    if b == 0:
        # Raising a built-in exception with a custom message
        raise ZeroDivisionError("Divisor cannot be zero")
    return a / b

try:
    result = divide(4, 0)
except ZeroDivisionError as e:
    print(f"Error: {e}") # Output: Error: Divisor cannot be zero
except Exception as e:
    print(f"An unexpected error occurred: {e}")
```

**Raise a general exception**:
While generally recommended to raise specific exceptions (either built-in or custom), you can also raise the base `Exception` class directly for generic error conditions.

```python
def some_risky_operation(condition: bool):
    if condition:
        raise Exception("Some generic error occurred due to a specific condition.")
    return "Operation successful"

try:
    print(some_risky_operation(True))
except Exception as e:
    print(f"Caught a general exception: {e}") # Output: Caught a general exception: Some generic error occurred due to a specific condition.
```

### Using `with` for Resource Management

The `with` keyword provides a more efficient and clean way to handle resources, like files or network connections, ensuring their proper acquisition and release (closure) when operations are complete or in case of any exceptions. Resources that can be used with `with` must implement the `context manager` protocol, typically by having `__enter__` and `__exit__` methods.

Here's an example using a file:

```python
try:
    with open("example.txt", "r") as file:
        data = file.read()
    # File is automatically closed when the 'with' block is exited,
    # even if an exception occurs during file reading.
    print("File content read successfully.")
except FileNotFoundError:
    print("Error: The file 'example.txt' was not found.")
except IOError as e:
    print(f"Error reading file: {e}")
```

### Controlling Flow with `else`, `pass`, and `continue`

These keywords offer different strategies for controlling program flow within or around exception handling blocks, allowing for conditional execution or ignoring certain exceptions.

#### `else` with `try-except` blocks

The `else` block after a `try-except` block will only be executed if **no exceptions** are raised within the `try` block. It serves as a place for code that *must* run only upon successful completion of the `try` block, before the `finally` block (if present).

```python
def perform_division(a, b):
    try:
        result = a / b
    except ZeroDivisionError:
        print("Cannot divide by zero!")
    else:
        # This code runs only if no exception occurred in the try block
        print(f"Division successful. Result: {result}")
        return result
    finally:
        print("Attempted division operation finished.")

perform_division(10, 2)
# Output:
# Division successful. Result: 5.0
# Attempted division operation finished.

perform_division(10, 0)
# Output:
# Cannot divide by zero!
# Attempted division operation finished.
```

#### `pass`

The `pass` statement is a null operation; nothing happens when it executes. It acts as a placeholder where a statement is syntactically required but you don't want any action to be performed, effectively ignoring an exception. While sometimes useful for prototyping, ignoring exceptions in production code should be done cautiously, as it can mask underlying issues.

```python
def risky_operation():
    raise ValueError("Something went wrong!")

try:
    risky_operation()
except ValueError:
    # Explicitly ignoring a specific ValueError
    pass # No action taken, program continues normally
print("Program continues after potentially ignored exception.")
```

#### `continue`

The `continue` keyword is generally used within loops. When executed inside an `except` block within a loop, it immediately skips the rest of the current iteration of the loop and proceeds to the next iteration. This is useful when processing a list of items and you want to skip an item that causes an exception without stopping the entire loop.

```python
data_items = [10, 2, 0, 5, 'error', 1]

for item in data_items:
    try:
        result = 100 / item
        print(f"Result for {item}: {result}")
    except (ZeroDivisionError, TypeError) as e:
        print(f"Skipping item {item} due with error: {e}")
        continue # Move to the next item in the loop
    except Exception as e:
        print(f"An unexpected error occurred for item {item}: {e}")
        continue
```

### Callback Function: `sys.excepthook`

The `sys.excepthook` is a configurable function in the `sys` module that allows you to customize how Python handles *uncaught* exceptions (exceptions that propagate all the way up without being caught by any `except` block). By default, `sys.excepthook` points to `sys.__excepthook__`, which prints the standard Python traceback to `sys.stderr`. You can replace it with your own function to log errors, display custom messages, send notifications, or perform other actions before the program potentially terminates.

Here's an example:

```python
# test_hook.py
import sys

def custom_excepthook(exc_type, exc_value, exc_traceback):
    """
    A custom exception hook that logs the unhandled exception
    and then calls the default hook.
    """
    print(f"*** UNHANDLED EXCEPTION CAUGHT BY CUSTOM HOOK ***")
    print(f"Type: {exc_type.__name__}")
    print(f"Value: {exc_value}")
    # You could log this to a file, send an email, etc.

    # Call the original excepthook to print the standard traceback
    sys.__excepthook__(exc_type, exc_value, exc_traceback)

# Set our custom hook
sys.excepthook = custom_excepthook

def problematic_function():
    print("Inside problematic_function")
    result = 1 / 0 # This will raise a ZeroDivisionError

if __name__ == "__main__":
    print("Calling problematic_function...")
    problematic_function()
    print("This line will not be reached due to unhandled exception.")

```

When `test_hook.py` is executed, the output will first show the custom message from `custom_excepthook` followed by the standard Python traceback, because `sys.__excepthook__` was called.

_Note_: `sys.excepthook` will not capture exceptions raised as the result of interactive prompt commands, such as `SyntaxError` or `KeyboardInterrupt`, nor does it affect exceptions caught by `try...except` blocks. It specifically targets exceptions that would otherwise lead to program termination with a traceback.
<br>

## 8. What is the difference between _list_ and _tuple_?

**Lists** and **Tuples** in Python share many similarities, such as being ordered sequences and supporting indexing, slicing, and iteration. However, they are fundamentally different in their core characteristics, making them suitable for different use cases.

### Key Distinctions

-   **Mutability**: This is the most significant difference.
    *   **Lists** are **mutable**, meaning their elements can be added, removed, or modified after the list has been created. They are dynamic and can change in size and content.
    *   **Tuples** are **immutable**. Once a tuple is created, its size and the elements it contains cannot be changed. While you cannot modify, add, or remove items from a tuple, it's important to note that if a tuple contains mutable objects (e.g., a list), the contents of those mutable objects *can* be changed. The tuple itself still holds the *reference* to that object, and that reference doesn't change.

-   **Performance and Memory Usage**:
    *   **Tuples** are generally more performant and consume less memory than lists for the same number of elements. This is because their fixed size allows Python to make certain optimizations. They have less overhead as they don't need to allocate space for growth or maintain methods for modification.
    *   **Lists**, being mutable, require more memory and can be slightly slower due to the overhead of supporting dynamic operations (resizing, adding, removing elements).

-   **Syntax**:
    *   **Lists** are defined using square brackets `[]`.
    *   **Tuples** are defined using parentheses `()`. A single-element tuple requires a trailing comma (e.g., `(item,)`) to distinguish it from a simple parenthesized expression.

### When to Use Each

-   **Lists** are ideal for collections of items that may change over time, such as a collection of user inputs, a dynamic queue, or a list of items to be processed. They are the preferred choice when you need a modifiable sequence.

-   **Tuples**, due to their immutability and enhanced performance, are a good choice for:
    *   Representing fixed sets of related data, like a record or a point in a coordinate system (e.g., `(x, y)`).
    *   Function arguments and return values, especially when returning multiple items from a function.
    *   Using as keys in dictionaries (provided all elements within the tuple are themselves immutable).
    *   Data that should not be changed, ensuring data integrity.

### Syntax

#### List: Example

Lists demonstrate mutability through operations like appending, removing, or modifying elements.

```python
my_list = ["apple", "banana", "cherry"]
print(f"Initial list: {my_list}")

# Adding an element
my_list.append("date")
print(f"After append: {my_list}")

# Modifying an element
my_list[1] = "blackberry"
print(f"After modification: {my_list}")

# Removing an element
my_list.remove("apple")
print(f"After removal: {my_list}")
```

#### Tuple: Example

Tuples are created with parentheses. Attempts to modify them will result in a `TypeError`.

```python
my_tuple = (1, 2, 3, 4)
print(f"Initial tuple: {my_tuple}")

# Unpacking a tuple (a common operation)
a, b, c, d = my_tuple
print(f"Unpacked values: a={a}, b={b}, c={c}, d={d}")

# Attempting to modify a tuple (will raise a TypeError)
try:
    my_tuple[0] = 5
except TypeError as e:
    print(f"Error attempting to modify tuple: {e}")

# Example of a tuple containing a mutable object
nested_tuple = (1, [2, 3], 4)
print(f"Nested tuple: {nested_tuple}")

# The list inside the tuple *can* be modified, even though the tuple itself is immutable
nested_tuple[1].append(5)
print(f"Nested tuple after modifying inner list: {nested_tuple}")

# The tuple itself still refers to the same list object; its reference hasn't changed.
```
<br>

## 9. How do you create a _dictionary_ in _Python_?

**Python dictionaries** are highly versatile and fundamental data structures that store data in `key:value` pairs, enabling efficient data retrieval. This section will explore the core concepts and various methods for creating dictionaries in Python.

### Key Concepts

-   A **dictionary** in Python is an unordered (as of Python 3.7+, insertion order is preserved, making them *ordered* in practice for CPython, but officially unordered for language specification prior to 3.7) collection of `key:value` pairs.
-   **Keys** must be unique within a dictionary and typically immutable types, such as strings, numbers (integers, floats), or tuples containing only immutable elements. Attempting to use a mutable object (like a list) as a key will raise a `TypeError`.
-   **Values** can be of any data type (strings, numbers, lists, other dictionaries, custom objects, etc.) and can be duplicated across different keys.

### Creating a Dictionary

Python offers several straightforward and efficient methods to create dictionaries:

1.  **Dictionary Literal**: The most common and direct way to define a dictionary, by enclosing `key:value` pairs within curly braces `{}`.
2.  **`dict()` Constructor**: A versatile constructor that can accept different types of arguments to form a dictionary:
    *   An iterable of `key:value` pairs (e.g., a list of tuples or another dictionary's `items()`).
    *   Keyword arguments, where the argument names become string keys and their corresponding values become dictionary values.
    *   Another dictionary, creating a shallow copy.
3.  **Dictionary Comprehensions**: A concise and powerful syntax for creating dictionaries dynamically from other iterables, often involving transformations or conditional logic.
4.  **`dict.fromkeys()` Method**: Useful for creating dictionaries with a sequence of keys and assigning all of them a specified default value (or `None` if no value is provided).
5.  **Using `zip()` with `dict()`**: A common pattern where the `zip()` function pairs elements from two sequences (one for keys, one for values), and the resulting iterable of pairs is then passed to the `dict()` constructor.

### Examples

#### 1. Dictionary Literal

This is the most idiomatic way to create a dictionary.

```python
# Creating a dictionary using a literal
student_profile = {
    "name": "Alice Smith",
    "age": 20,
    "major": "Computer Science",
    "courses": ["Data Structures", "Algorithms", "Databases"],
    "is_enrolled": True
}

print(f"Student Profile (Literal): {student_profile}")
# Expected output: Student Profile (Literal): {'name': 'Alice Smith', 'age': 20, 'major': 'Computer Science', 'courses': ['Data Structures', 'Algorithms', 'Databases'], 'is_enrolled': True}
```

#### 2. Using the `dict()` Constructor

##### From an Iterable of Key-Value Pairs

The `dict()` constructor can take a sequence of two-element iterables (like tuples or lists), where each inner iterable represents a `(key, value)` pair.

```python
# From a list of tuples
faculty_info = dict([
    ("dean", "Dr. Emily White"),
    ("department_head", "Prof. Robert Green"),
    ("number_of_professors", 15)
])
print(f"Faculty Info (from list of tuples): {faculty_info}")
# Expected output: Faculty Info (from list of tuples): {'dean': 'Dr. Emily White', 'department_head': 'Prof. Robert Green', 'number_of_professors': 15}
```

##### From Keyword Arguments

When using named arguments, the argument names become string keys, and their values become the dictionary values.

```python
# From keyword arguments
city_data = dict(name="New York", population=8400000, country="USA")
print(f"City Data (from keyword arguments): {city_data}")
# Expected output: City Data (from keyword arguments): {'name': 'New York', 'population': 8400000, 'country': 'USA'}
```

##### From Another Dictionary (Copying)

This creates a shallow copy of an existing dictionary.

```python
# From an existing dictionary (creating a copy)
student_profile_copy = dict(student_profile) # Using the previously defined student_profile
print(f"Student Profile Copy: {student_profile_copy}")
# Expected output: Student Profile Copy: {'name': 'Alice Smith', 'age': 20, 'major': 'Computer Science', 'courses': ['Data Structures', 'Algorithms', 'Databases'], 'is_enrolled': True}
```

#### 3. Dictionary Comprehensions

Dictionary comprehensions provide a concise way to create dictionaries from expressions and `for` loops.

```python
# Creating a dictionary from a list of numbers, mapping number to its square
squares = {num: num**2 for num in range(1, 6)}
print(f"Squares Dictionary: {squares}")
# Expected output: Squares Dictionary: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Creating a dictionary from two lists, with a condition
employees = ["John", "Jane", "Mike"]
salaries = [60000, 75000, 50000]
employee_salaries = {emp: sal for emp, sal in zip(employees, salaries) if sal > 55000}
print(f"Employee Salaries (filtered): {employee_salaries}")
# Expected output: Employee Salaries (filtered): {'John': 60000, 'Jane': 75000}
```

#### 4. `dict.fromkeys()` Method

This method takes an iterable of keys and an optional `value`. All keys in the new dictionary will be mapped to this `value`. If `value` is omitted, `None` is used.

```python
# Creating a dictionary with default values
default_score = 0
student_scores = dict.fromkeys(["Alice", "Bob", "Charlie"], default_score)
print(f"Student Scores (fromkeys): {student_scores}")
# Expected output: Student Scores (fromkeys): {'Alice': 0, 'Bob': 0, 'Charlie': 0}

# Creating a dictionary with keys and default value None
project_tasks = dict.fromkeys(["Design", "Development", "Testing"])
print(f"Project Tasks (fromkeys with None): {project_tasks}")
# Expected output: Project Tasks (fromkeys with None): {'Design': None, 'Development': None, 'Testing': None}
```

#### 5. Using `zip()` with `dict()`

The `zip()` function pairs corresponding elements from multiple iterables. When combined with `dict()`, it's excellent for creating a dictionary from separate key and value lists.

```python
keys = ["product_id", "name", "price"]
values = [101, "Laptop", 1200.50]

# Using zip() to combine keys and values, then converting to a dictionary
product_details = dict(zip(keys, values))
print(f"Product Details (using zip): {product_details}")
# Expected output: Product Details (using zip): {'product_id': 101, 'name': 'Laptop', 'price': 1200.5}

# Example with different length lists (zip stops at the shortest)
colors = ["red", "green", "blue", "yellow"]
hex_codes = ["#FF0000", "#00FF00", "#0000FF"] # Shorter list
color_map = dict(zip(colors, hex_codes))
print(f"Color Map (zip with different lengths): {color_map}")
# Expected output: Color Map (zip with different lengths): {'red': '#FF0000', 'green': '#00FF00', 'blue': '#0000FF'}
```
<br>

## 10. What is the difference between _==_ and _is operator_ in _Python_?

Both the **`==`** and **`is`** operators in Python are used for comparison, but they serve fundamentally different purposes, focusing on distinct aspects of objects.

### Understanding `==` (Equality Operator)

The **`==`** operator checks for **value equality**. It determines whether two objects have the same content or value.

#### How `==` Works
When `a == b` is evaluated, Python essentially asks: "Do these two objects represent the same value?"

For built-in types:
*   **Numbers, strings, tuples:** `==` compares their literal values.
*   **Lists, dictionaries, sets:** `==` recursively compares their elements.

For custom objects:
The behavior of `==` can be customized by implementing the special method `__eq__(self, other)` within the class definition. If `__eq__` is not implemented, Python's default behavior for custom objects is to check for identity (similar to `is`), but this is rarely the desired behavior for value comparison.

#### Example of `==`
```python
# Comparing built-in types
a = [1, 2, 3]
b = [1, 2, 3]
c = [4, 5, 6]
d = a

print(f"a == b: {a == b}") # Output: True (same content)
print(f"a == c: {a == c}") # Output: False (different content)
print(f"a == d: {a == d}") # Output: True (same content)

# Comparing custom objects with __eq__
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __eq__(self, other):
        if not isinstance(other, Point):
            return NotImplemented
        return self.x == other.x and self.y == other.y

p1 = Point(1, 2)
p2 = Point(1, 2)
p3 = Point(3, 4)

print(f"p1 == p2: {p1 == p2}") # Output: True (due to __eq__ implementation)
print(f"p1 == p3: {p1 == p3}") # Output: False
```

### Understanding `is` (Identity Operator)

The **`is`** operator checks for **object identity**. It determines whether two variables refer to the *exact same object* in memory.

#### How `is` Works
When `a is b` is evaluated, Python asks: "Are `a` and `b` references to the very same object instance?" This is equivalent to checking if `id(a) == id(b)`. The `id()` built-in function returns a unique identifier for an object, which is typically its memory address during its lifetime.

The `is` operator **cannot be overloaded** for custom classes. Its behavior is fixed: it always compares object identities.

#### Example of `is`
```python
# Comparing built-in types
a = [1, 2, 3]
b = [1, 2, 3] # 'b' is a new list object, even if content is identical
c = a         # 'c' refers to the exact same list object as 'a'

print(f"a is b: {a is b}") # Output: False (different objects in memory)
print(f"a is c: {a is c}") # Output: True (same object in memory)

# Comparing custom objects
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

p1 = Point(1, 2)
p2 = Point(1, 2)
p3 = p1

print(f"p1 is p2: {p1 is p2}") # Output: False (p1 and p2 are different objects)
print(f"p1 is p3: {p1 is p3}") # Output: True (p1 and p3 refer to the same object)
```

### Key Differences Summarized

*   **`==`**: Compares the **value** or **content** of objects. Can be customized with `__eq__`.
*   **`is`**: Compares the **identity** (memory address) of objects. Cannot be customized.

### When to Use Which Operator

#### Use `==` for Value Comparison
*   You should almost always use **`==`** when you want to compare if two objects have the same content or value. This is the most common use case for comparison.
*   **Examples:** Comparing numbers, strings, lists, dictionaries, or instances of custom classes where `__eq__` is defined to represent value equality.

#### Use `is` for Identity Comparison
*   **Singletons:** The `is` operator is most reliably and commonly used to check if an object is `None`, `True`, or `False`, as these are singletons in Python (there is only ever one instance of each).
    ```python
    my_variable = None
    if my_variable is None:
        print("Variable is None")
    ```
*   **Checking for the exact same object:** If you specifically need to verify that two variables refer to the exact same object in memory, perhaps to detect alias relationships or for performance optimizations.

#### Important Caveats for `is`
Python performs certain optimizations, such as **object interning**, for immutable types like small integers (typically -5 to 256), `True`, `False`, `None`, and sometimes short strings. This can lead to situations where `is` returns `True` for objects that might logically be considered distinct values, but which Python has optimized to point to the same memory location.

```python
# Integer interning
x = 100
y = 100
print(f"x is y (small int): {x is y}") # Output: True (due to interning)

a = 1000
b = 1000
print(f"a is b (large int): {a is b}") # Output: False (not always interned)

# String interning (can be unpredictable for non-literal strings)
s1 = "hello"
s2 = "hello"
print(f"s1 is s2 (literal string): {s1 is s2}") # Output: True (often interned)

s3 = "hello world"
s4 = "hello world"
print(f"s3 is s4 (longer string): {s3 is s4}") # Output: False (interning less likely)

s5 = "hello"
s6 = "he" + "llo"
print(f"s5 is s6 (concatenated string): {s5 is s6}") # Output: True (optimised at compile time)
```
Because of these optimizations, relying on `is` for value comparison, especially with numbers and strings, can lead to inconsistent and difficult-to-debug behavior. Always use `==` for comparing values unless you have a specific reason to check for object identity.
<br>

## 11. How does a _Python function_ work?

**Python functions** are fundamental constructs for organizing code, embodying principles of reusability, modularity, and encapsulation. They allow developers to break down complex problems into smaller, manageable units, each designed to perform a specific task.

### Core Concepts of a Python Function

Python functions operate on several core principles:

*   **Code Reusability**: Functions define a block of code that can be executed multiple times from different parts of a program, avoiding code duplication.
*   **Modularity**: They promote the division of a program into independent, self-contained modules, making the codebase easier to understand, maintain, and debug.
*   **Encapsulation**: Functions encapsulate their internal logic and data (local variables), minimizing interference with other parts of the program.
*   **First-Class Objects**: In Python, functions are first-class objects, meaning they can be assigned to variables, passed as arguments to other functions, and returned as values from other functions. This enables powerful programming paradigms like higher-order functions and decorators.

### Anatomy of a Python Function

A Python function typically consists of the following parts:

#### Function Signature
The signature defines the function's interface. It begins with the `def` keyword, followed by the function's name, a pair of parentheses enclosing its parameters, and a colon `:`. Modern Python (post-PEP 484) also supports optional **type hints** for parameters and the return value to improve code readability and allow static analysis.

```python
def greet(name: str, message: str = "Hello") -> str:
    # Function body
    pass
```
Here, `greet` is the function name, `name` and `message` are parameters (`message` has a default value), and `-> str` indicates the function is expected to return a string.

#### Function Body
This is an indented block of code that contains the logic performed when the function is called. It can include conditional statements, loops, other function calls, and any other valid Python statements.

#### Return Statement
The `return` statement specifies the value that the function sends back to its caller. If a function reaches its end without an explicit `return` statement, or if `return` is used without an expression, it implicitly returns `None`.

```python
def add(a: int, b: int) -> int:
    result = a + b
    return result

def do_nothing():
    # This function implicitly returns None
    pass

value1 = add(5, 3)  # value1 will be 8
value2 = do_nothing() # value2 will be None
```

#### Docstrings
While not part of the execution, a **docstring** (a multi-line string immediately after the function signature) is a crucial component for documentation. It explains what the function does, its parameters, and what it returns.

```python
def calculate_area(radius: float) -> float:
    """
    Calculates the area of a circle given its radius.

    Args:
        radius (float): The radius of the circle.

    Returns:
        float: The calculated area.
    """
    import math
    return math.pi * radius**2
```

### How a Python Function Executes

When a function is called, a specific sequence of actions occurs:

1.  #### Call Stack and Stack Frames
    Upon a function call, a new **stack frame** (also known as an activation record) is created on the program's **call stack**. This stack frame is a dedicated memory region that stores information relevant to that specific function invocation, including:
    *   The function's parameters.
    *   Its local variables.
    *   The return address (the location in the calling code to resume execution after the function completes).
    *   Other management information.

2.  #### Parameter Binding
    The arguments passed during the function call are bound to the corresponding **parameters** defined in the function's signature. Python supports various ways to pass arguments, including positional arguments, keyword arguments, default values, and arbitrary argument lists (`*args` for positional, `**kwargs` for keyword).

3.  #### Execution Flow
    Control is transferred to the function's body. Statements within the function body are executed sequentially. If an exception occurs, the execution might be interrupted and propagated up the call stack.

4.  #### Returning Control
    When a `return` statement is encountered, the function evaluates the expression (if any) following `return` and sends this value back to the caller. Subsequently, the function's stack frame is **popped** from the call stack, releasing the memory allocated for its local variables and parameters. Execution in the caller resumes from the return address. If no `return` statement is met or the function body completes, `None` is implicitly returned.

### Variable Scope and Lifetime (LEGB Rule)

Python uses the **LEGB rule** to determine the order in which it looks for names (variables, functions, classes) during resolution:

*   **L**ocal: Names assigned within the current function (e.g., `x = 10` inside a `def`). This also includes parameters.
*   **E**nclosing function locals: Names in the local scope of any enclosing function (for nested functions).
*   **G**lobal: Names assigned at the top-level of a module (outside any function).
*   **B**uilt-in: Names pre-assigned in Python's built-in module (e.g., `print`, `len`, `str`).

#### Local Scope (L)
Variables defined inside a function (including its parameters) are **local** to that function. They are created when the function is called and destroyed when the function completes execution. They are not accessible from outside the function.

```python
def my_function():
    local_var = "I am local"
    print(local_var) # Accessible here

my_function()
# print(local_var) # This would raise a NameError
```

#### Enclosing Function Local Scope (E)
In nested functions, the inner function can access variables from its **enclosing (outer) function's scope**. These are often called **non-local** variables. To modify a non-local variable from an inner function, the `nonlocal` keyword must be used. Without `nonlocal`, an assignment inside the inner function would create a new local variable, shadowing the outer one.

```python
def outer_function():
    enclosing_var = "Outer variable"

    def inner_function():
        nonlocal enclosing_var # Declare intent to modify
        enclosing_var = "Modified by inner"
        print(f"Inside inner: {enclosing_var}")

    inner_function()
    print(f"Inside outer: {enclosing_var}")

outer_function()
# Output:
# Inside inner: Modified by inner
# Inside outer: Modified by inner
```

#### Global Scope (G)
Variables defined at the top level of a script or module are **global**. Functions can read global variables directly. However, to **modify** a global variable from within a function, the `global` keyword must be explicitly used. Otherwise, an assignment will create a new local variable with the same name, leaving the global variable unchanged.

```python
global_var = "I am global"

def modify_global():
    global global_var # Declare intent to modify
    global_var = "I was modified"
    print(f"Inside function: {global_var}")

def create_local_with_same_name():
    global_var = "I am a local masking the global" # Creates a new local variable
    print(f"Inside function (local): {global_var}")

print(f"Before call: {global_var}")
modify_global()
print(f"After modify_global: {global_var}")

create_local_with_same_name()
print(f"After create_local_with_same_name: {global_var}")
# Output:
# Before call: I am global
# Inside function: I was modified
# After modify_global: I was modified
# Inside function (local): I am a local masking the global
# After create_local_with_same_name: I was modified (Global variable remains unchanged here)
```

### Best Practices: Minimizing Side Effects

Functions offer a crucial level of encapsulation, which can significantly reduce **side effects**. A side effect occurs when a function modifies something outside its local scope (e.g., a global variable, a mutable argument, or an external system).

While Python's flexibility allows functions to access and modify global/non-local variables (with `global`/`nonlocal`), over-reliance on this can lead to:

*   **Harder Debugging**: It becomes difficult to trace where and when a variable's value changes.
*   **Reduced Readability**: The function's behavior might depend on external state not explicitly passed as arguments.
*   **Lower Testability**: Functions with side effects are harder to test in isolation, as their output depends on the global state.
*   **Less Reusability**: Functions tightly coupled to specific global states are less portable.

As a best practice, strive for **pure functions** where possible: functions that, given the same inputs, always produce the same output and cause no side effects. Minimizing the use of `global` and `nonlocal` keywords, and favoring passing data through arguments and returning results, leads to more robust, predictable, and maintainable codebases.
<br>

## 12. What is a _lambda function_, and where would you use it?

### What is a Lambda Function?

A **lambda function**, often simply called a **lambda**, is a small, anonymous function defined in Python using the `lambda` keyword. Unlike regular functions defined with `def`, a lambda function does not require a name, making it suitable for short, one-off operations. Its body is restricted to a single expression, the result of which is implicitly returned.

While traditional named functions serve most programming needs, lambda expressions provide a concise alternative for simple, functional constructs where a full `def` statement might be considered overly verbose.

### Distinctive Features

*   #### Anonymity
    Lambdas are inherently anonymous; they are not bound to an identifier (name) in the same way `def` functions are. This makes them ideal for situations where a function is needed transiently and will not be reused elsewhere in the codebase.

*   #### Single Expression Body
    The core characteristic of a lambda is its limitation to a single expression. This means its body cannot contain multiple statements (like `if`, `for`, `while`, or `return`). It computes and returns the value of that single expression.
    *   Example: `lambda x, y: x + y` is valid.
    *   Example: `lambda x: if x > 0: return x` is **invalid** because it contains a statement (`if`) and an explicit `return`.

*   #### Implicit Return
    There is no need for an explicit `return` statement within a lambda. The value produced by the single expression in its body is automatically returned.

*   #### Conciseness
    Lambdas enable the definition of straightforward functions in a compact, inline form, which can improve readability for simple operations when used appropriately.

### Common Use Cases

Lambdas shine in functional programming paradigms or when a small, throwaway function is required as an argument to a higher-order function.

*   #### Map, Filter, and Reduce
    Functions like `map()`, `filter()`, and `functools.reduce()` often take a function as an argument to apply a transformation or filter criteria to an iterable. Lambdas provide a convenient way to define these simple operations inline.

    ```python
    # Example: Doubling each element in a list using map and lambda
    my_list = [1, 2, 3, 4]
    doubled_list = list(map(lambda x: x * 2, my_list))
    print(doubled_list) # Output: [2, 4, 6, 8]

    # Example: Filtering even numbers using filter and lambda
    even_numbers = list(filter(lambda x: x % 2 == 0, my_list))
    print(even_numbers) # Output: [2, 4]
    ```

*   #### Sorting with Custom Keys
    The `sort()` method of lists or the built-in `sorted()` function can accept a `key` argument, which is a function that extracts a comparison key from each element in the list. Lambdas are perfect for defining custom sorting logic on the fly.

    ```python
    # Example: Sorting a list of tuples by the second element
    data = [('apple', 10), ('banana', 5), ('cherry', 15)]
    sorted_data = sorted(data, key=lambda item: item[1])
    print(sorted_data) # Output: [('banana', 5), ('apple', 10), ('cherry', 15)]

    # Example: Sorting a list of strings by their length
    words = ["python", "is", "awesome"]
    sorted_words = sorted(words, key=lambda s: len(s))
    print(sorted_words) # Output: ['is', 'python', 'awesome']
    ```

*   #### Callbacks
    In event-driven programming (e.g., GUI frameworks, web frameworks), lambdas are frequently used as callback functions that are executed when a specific action occurs (e.g., a button click, an API response).

    ```python
    # Conceptual example for a GUI button click
    # button.on_click(lambda event: print("Button clicked!"))
    ```

*   #### Simple Functions
    For very basic, self-contained functions that are used immediately and not intended for reuse, a lambda can prevent the clutter of defining a named function.

### Notable Limitations and Alternatives

While useful, lambdas have limitations that often make named functions or other Pythonic constructs preferable.

*   #### Lack of Verbose Readability
    If the logic within a lambda becomes even slightly complex, it can quickly become difficult to read and understand. Named functions with clear names and docstrings generally offer superior readability and maintainability for anything beyond trivial operations.

*   #### No Formal Documentation
    Lambdas do not support docstrings, making it harder to document their purpose directly within the function itself. Their intent must be inferred from context or explained via external comments, which is less ideal.

*   #### Restriction to a Single Expression
    As previously mentioned, lambdas cannot contain statements (assignments, `if`/`else` statements, loops, `try`/`except` blocks, etc.). This severely limits their complexity. For instance, you cannot define a lambda that prints something and then returns a value, as `print()` is a statement. While conditional *expressions* (`x if condition else y`) are allowed, they can quickly become unreadable.

*   #### Alternatives like List Comprehensions
    For many scenarios involving `map()` or `filter()` with simple lambdas, Python's **list comprehensions** (and generator expressions, set comprehensions, dictionary comprehensions) often provide a more readable and Pythonic alternative.

    ```python
    # Using map and lambda
    my_list = [1, 2, 3, 4]
    doubled_list_lambda = list(map(lambda x: x * 2, my_list))

    # Using a list comprehension (often preferred for clarity)
    doubled_list_comprehension = [x * 2 for x in my_list]

    print(doubled_list_lambda)      # Output: [2, 4, 6, 8]
    print(doubled_list_comprehension) # Output: [2, 4, 6, 8]
    ```

In conclusion, lambda functions are a powerful tool for writing concise, anonymous functions for simple, single-expression tasks, particularly when passed as arguments to higher-order functions. However, for more complex logic, better readability, or reusability, a traditional `def` function or other Pythonic constructs are usually the superior choice.
<br>

## 13. Explain _*args_ and _**kwargs_ in _Python_.

In Python, `*args` and `**kwargs` are powerful constructs used to pass a **variable number of arguments** to a function. They enable flexible function definitions that can accept an arbitrary quantity of inputs.

The `*args` syntax collects a variable number of **positional arguments** into a **tuple**, while `**kwargs` does the same for **keyword arguments** into a **dictionary**.

Here are the key features, use-cases, and their respective code examples, along with important related concepts.

### `*args`: Variable Positional Arguments

The single asterisk `*` operator, when used in a function definition, indicates that an arbitrary number of positional arguments can be accepted.

#### How it Works

The name `*args` is a widely adopted **convention**. The asterisk `*` itself is the operator that tells Python to collect all remaining positional arguments into a single **tuple**. This tuple can then be iterated over within the function.

#### Use-Cases

*   When the number of arguments a function needs to operate on is **uncertain** or can vary.
*   To create **flexible functions** that can handle different call signatures for positional data.
*   For **forwarding arguments** from one function to another.

#### Code Example: `*args`

```python
def sum_all(*args):
    """
    Calculates the sum of an arbitrary number of integers.
    The collected arguments are available as a tuple named 'args'.
    """
    result = 0
    print(f"Type of args: {type(args)}") # Output: Type of args: <class 'tuple'>
    for num in args:
        result += num
    return result

print(sum_all(1, 2, 3, 4))        # Output: 10
print(sum_all(10, 20, 30, 40, 50)) # Output: 150
```

### `**kwargs`: Variable Keyword Arguments

The double asterisk `**` operator, when used in a function definition, allows a function to accept an arbitrary number of keyword arguments.

#### How it Works

Similar to `*args`, `**kwargs` is a **convention**, and the double asterisk `**` is the operator. It captures all remaining keyword arguments and their values into a **dictionary**. The keys of this dictionary are the keyword argument names (as strings), and the values are their corresponding argument values.

#### Use-Cases

*   When a function needs to accept an **arbitrary number of named parameters**.
*   To create highly **configurable functions** where options can be passed as keyword arguments.
*   For **building flexible APIs** where different settings can be provided.
*   For **forwarding keyword arguments** from one function to another, especially in decorators or object initializers.

#### Code Example: `**kwargs`

```python
def print_user_info(**kwargs):
    """
    Prints user information passed as keyword arguments.
    The collected arguments are available as a dictionary named 'kwargs'.
    """
    print(f"Type of kwargs: {type(kwargs)}") # Output: Type of kwargs: <class 'dict'>
    if not kwargs:
        print("No user information provided.")
        return

    print("User Info:")
    for key, value in kwargs.items():
        print(f"  {key.replace('_', ' ').title()}: {value}")

# Keyword arguments are captured as a dictionary
print_user_info(name="Alice", age=25, city="London", occupation="Engineer")
# Output:
# Type of kwargs: <class 'dict'>
# User Info:
#   Name: Alice
#   Age: 25
#   City: London
#   Occupation: Engineer

print_user_info() # Output: No user information provided.
```

### Argument Order and Combination

When defining a function that uses a mix of standard arguments, `*args`, and `**kwargs`, there is a specific order that must be followed:

1.  **Standard positional arguments**
2.  **`*args`** (to capture additional positional arguments)
3.  **Keyword-only arguments** (arguments specified after `*args` that *must* be passed by keyword)
4.  **`**kwargs`** (to capture additional keyword arguments)

#### Code Example: Combining `*args` and `**kwargs`

```python
def configure_system(system_name, *settings, debug_mode=False, **options):
    """
    Configures a system with a name, a list of settings, an optional debug mode,
    and arbitrary additional configuration options.
    """
    print(f"Configuring system: {system_name}")
    print(f"  Settings (tuple): {settings}")
    print(f"  Debug Mode (kw-only): {debug_mode}")
    print(f"  Additional Options (dict): {options}")

configure_system("WebServer", "security_patch", "logging_level",
                 debug_mode=True, timeout=30, users_limit=100)
# Output:
# Configuring system: WebServer
#   Settings (tuple): ('security_patch', 'logging_level')
#   Debug Mode (kw-only): True
#   Additional Options (dict): {'timeout': 30, 'users_limit': 100}

configure_system("Database", "replication_enabled")
# Output:
# Configuring system: Database
#   Settings (tuple): ('replication_enabled',)
#   Debug Mode (kw-only): False
#   Additional Options (dict): {}
```

### Unpacking Arguments (The Duality)

The `*` and `**` operators have a dual purpose: they can also be used to **unpack** iterables and dictionaries, respectively, when **calling a function**. This is the inverse operation of collecting arguments.

#### Unpacking with `*`

Using `*` before an iterable (like a list or tuple) in a function call unpacks its elements, treating them as individual positional arguments.

```python
def multiply(a, b, c):
    return a * b * c

numbers = [2, 3, 4]
print(multiply(*numbers)) # Unpacks [2, 3, 4] into 2, 3, 4. Output: 24

coordinates = (10, 20, 30)
print(multiply(*coordinates)) # Unpacks (10, 20, 30) into 10, 20, 30. Output: 6000
```

#### Unpacking with `**`

Using `**` before a dictionary in a function call unpacks its key-value pairs, treating them as individual keyword arguments.

```python
def describe_person(name, age, city):
    print(f"{name} is {age} years old and lives in {city}.")

person_data = {"name": "Charlie", "age": 40, "city": "Paris"}
describe_person(**person_data) # Unpacks dictionary into name="Charlie", age=40, city="Paris".
# Output: Charlie is 40 years old and lives in Paris.

config = {"name": "Server1", "port": 8080, "timeout": 60}

# Can be combined with specific args, as long as there are no conflicts
def connect(name, port, **extra_options):
    print(f"Connecting to {name} on port {port} with options: {extra_options}")

connect(**config)
# Output: Connecting to Server1 on port 8080 with options: {'timeout': 60}
```

### Key Benefits

*   **Flexibility:** Functions can be designed to accept varying numbers of inputs without needing multiple overloaded definitions.
*   **Code Reusability:** Promotes more generic and adaptable function designs.
*   **Argument Forwarding:** Simplifies passing arguments from a wrapper function to an inner function, which is particularly useful in decorators or when building API layers.
<br>

## 14. What are _decorators_ in _Python_?

In Python, a **decorator** is a powerful design pattern and a feature that allows you to modify or extend the behavior of functions or methods dynamically without permanently altering their source code. This is a form of **metaprogramming**, primarily used to keep the code **clean**, **maintainable**, and adhere to the **DRY** (Don't Repeat Yourself) principle.

### How Decorators Work

*   Decorators are essentially **callable objects** (usually functions) that take another function as an argument.
*   They *wrap* the **target function**, allowing you to execute custom code both *before* and *after* the target function's execution.
*   The decorator then returns a new function (or another callable object) that typically replaces the original function. This makes them **higher-order functions**.

### Common Use Cases

Decorators have numerous practical applications, enhancing code modularity and reusability:

*   **Authorization and Authentication**: Restricting access to certain functions based on user roles or permissions.
*   **Logging**: Recording function calls, arguments, return values, or exceptions for debugging and auditing.
*   **Caching**: Storing the results of expensive function calls to avoid recomputing them for the same inputs.
*   **Validation**: Checking input parameters or function output against specified criteria.
*   **Task Scheduling**: Executing a function at a specific time or on a particular event.
*   **Counting and Profiling**: Keeping track of the number of times a function is called or measuring its execution time.
*   **Retries**: Automatically retrying a function call if it fails (e.g., due to network issues).

### Using Decorators in Code

Python's `@decorator` syntax provides **syntactic sugar** for applying decorators.

```python
from functools import wraps
import time

# 1. Basic Decorator (Timer Example)
def timer(func):
    """A decorator that measures the execution time of a function."""
    @wraps(func)  # Preserves the original function's metadata
    def wrapper(*args, **kwargs):
        start_time = time.perf_counter()
        result = func(*args, **kwargs)
        end_time = time.perf_counter()
        print(f'Function {func.__name__!r} executed in {(end_time - start_time):.4f}s')
        return result
    return wrapper

@timer
def long_running_function():
    """Simulates a function that takes some time to execute."""
    time.sleep(0.5)
    print('Long running function completed.')

long_running_function() # Output: Long running function completed. \n Function 'long_running_function' executed in X.XXXs

# 2. Decorators with Arguments (Parameterized Decorator)
def log_level(level):
    """A decorator factory that creates a decorator to log function calls at a specific level."""
    def actual_decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            print(f'[{level.upper()}] Calling {func.__name__!r} with args: {args}, kwargs: {kwargs}')
            result = func(*args, **kwargs)
            print(f'[{level.upper()}] {func.__name__!r} returned: {result}')
            return result
        return wrapper
    return actual_decorator

@log_level('info')
def add(a, b):
    return a + b

@log_level('debug')
def multiply(x, y):
    return x * y

print(add(5, 3)) # Output: [INFO] Calling 'add' with args: (5, 3), kwargs: {} \n [INFO] 'add' returned: 8 \n 8
print(multiply(4, 2)) # Output: [DEBUG] Calling 'multiply' with args: (4, 2), kwargs: {} \n [DEBUG] 'multiply' returned: 8 \n 8
```

### Decorator Syntax in Python

The `@decorator` syntax above is a compact and readable way to apply a decorator. It is entirely equivalent to, and merely **syntactic sugar** for, the following:

```python
def say_hello():
    print('Hello!')

# Applying the decorator manually
say_hello = timer(say_hello) # assuming 'timer' from the example above

say_hello() # This would now also print the execution time
```

### Role of `functools.wraps`

When defining decorators, especially those that return inner functions, it is crucial to use `@wraps(func)` from the `functools` module. This decorator ensures that the original function's **metadata** (like its `__name__`, `__doc__`, `__module__`, and argument lists) is correctly preserved on the wrapper function. Without `@wraps`, the decorated function would appear to be the wrapper function, which can hinder debugging, documentation tools, and introspection.
<br>

## 15. How can you create a _module_ in _Python_?

To create a module in Python, you essentially save Python code in a file with a `.py` extension. This file then becomes a module that can be imported and used in other Python programs or modules.

A **Python module** is a file containing Python definitions and statements. Modules are a fundamental mechanism for organizing related code into logical units, promoting reusability, and avoiding name collisions.

### How to Create a Python Module

The primary and most common way to create a module is as follows:

1.  **Save Python Code as a `.py` File**:
    Simply write your Python code (functions, classes, variables, etc.) in a text file and save it with a `.py` extension. For instance, if you save your code as `my_module.py`, then `my_module` becomes the name of your module.

2.  **Implicitly as Part of a Package (using `__init__.py`)**:
    While not a standalone module itself in the same sense as a `.py` file, an `__init__.py` file *is* a module. Its primary purpose is to mark a directory as a **Python package**. A package is a way to organize related modules into a directory hierarchy. When a directory contains an `__init__.py` file (even an empty one), Python treats that directory as a package, and any `.py` files inside it become modules within that package.
    *Note*: As of Python 3.3, `__init__.py` is optional for *namespace packages*, but it is still commonly used and required for regular packages.

### Accessing a Module

Once a module is created, you can access its functionality using the `import` statement in another Python script or interactive session.

### Code Example: Creating a `math_operations` Module

Let's illustrate by creating a module named `math_operations`.

#### Module Definition

Save the following code in a file named `math_operations.py`:

```python
# math_operations.py

def add(x, y):
    """Adds two numbers and returns the sum."""
    return x + y

def subtract(x, y):
    """Subtracts the second number from the first."""
    return x - y

def multiply(x, y):
    """Multiplies two numbers."""
    return x * y

def divide(x, y):
    """Divides the first number by the second. Handles division by zero."""
    if y == 0:
        raise ValueError("Cannot divide by zero")
    return x / y

PI = 3.14159 # A global variable within the module
```

#### Module Usage

You can use the `math_operations` module by importing it into another Python file (e.g., `main_app.py`) or an interactive interpreter:

```python
# main_app.py

import math_operations # Imports the entire module

# Access functions and variables using the module name
result_add = math_operations.add(4, 5)
print(f"4 + 5 = {result_add}") # Output: 4 + 5 = 9

result_divide = math_operations.divide(10, 5)
print(f"10 / 5 = {result_divide}") # Output: 10 / 5 = 2.0

print(f"Value of PI: {math_operations.PI}") # Output: Value of PI: 3.14159

# Using specific imports for brevity (recommended for specific functions/classes)
from math_operations import multiply, subtract

result_multiply = multiply(6, 7)
print(f"6 * 7 = {result_multiply}") # Output: 6 * 7 = 42

result_subtract = subtract(15, 8)
print(f"15 - 8 = {result_subtract}") # Output: 15 - 8 = 7

# Importing all members (generally discouraged)
# from math_operations import * # Not recommended generally due to potential name collisions and readability concerns

# try:
#     result_zero_divide = math_operations.divide(10, 0)
#     print(result_zero_divide)
# except ValueError as e:
#     print(f"Error: {e}") # Output: Error: Cannot divide by zero
```

### Best Practices for Module Creation

When creating modules, consider the following best practices:

*   **Modularity**: Keep modules focused on a single responsibility or a coherent set of related functionalities.
*   **Documentation**: Use docstrings for modules, functions, and classes to explain their purpose, arguments, and return values. This greatly enhances maintainability.
*   **Guard Against Code Execution on Import**: It's common for modules to contain code that should only run when the module is executed directly (as a script) and not when it's imported into another program. Use the `if __name__ == "__main__":` block for this:

    ```python
    # my_module.py

    def my_function():
        print("This function is part of the module.")

    def main():
        """Main execution logic when the module is run as a script."""
        print("This code runs only when my_module.py is executed directly.")
        my_function()
        # Additional script-specific logic here

    if __name__ == "__main__":
        main()
    ```
    This ensures that the code inside the `main()` function (or directly under the `if` block) is only executed when `my_module.py` is run as the primary script. If `my_module.py` is imported into another file, the `main()` function will not be called automatically, preventing unintended side effects.
<br>



#### Explore all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

