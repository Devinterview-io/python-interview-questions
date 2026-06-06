# 100 Core Python Interview Questions in 2026

<div>
<p align="center">
<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

#### You can also find all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

## 1. What are the _key features_ of _Python_?

**Python** is a high-level, multi-paradigm programming language known for its simplicity, **readable syntax**, and a massive ecosystem. It is widely used in AI, web development, and automation.

### Key Features of Python

#### 1. Interpreted and Interactive
Python is an **interpreted language**, meaning code is executed line-by-line by the **CPython** interpreter. This removes the need for a separate compilation step, enabling an **interactive** workflow through REPLs and notebooks.

#### 2. Simple and Readable Syntax
Python uses **significant indentation** rather than curly braces or keywords to define code blocks. Its syntax mimics natural English, adhering to the **PEP 8** style guide to ensure high maintainability and readability.

#### 3. Cross-Platform Compatibility
Python is **platform-independent**. Code written on one operating system (e.g., Windows) runs seamlessly on others (e.g., Linux, macOS) without modification, provided the Python interpreter is installed.

#### 4. Modular and Scalable
Python encourages **modularity** through modules and packages. Developers can organize complex logic into reusable components, which facilitates the development of large-scale applications.

#### 5. Massive Library Ecosystem
The **Python Package Index (PyPI)** hosts over 500,000 libraries. It provides specialized tools for **Data Science** (Pandas), **Machine Learning** (PyTorch, TensorFlow), and **Web Development** (Django, FastAPI).

#### 6. Versatile Application Domains
Python is a "general-purpose" language. It dominates diverse fields including **Artificial Intelligence**, scientific computing, backend web development, and DevOps scripting.

#### 7. Automatic Memory Management
Python manages memory automatically using **Reference Counting** and a **Cyclic Garbage Collector**. This abstracts low-level memory allocation, preventing common errors like memory leaks and segmentation faults.

#### 8. Dynamically Typed with Type Hinting
Python is **dynamically typed**, meaning variable types are determined at runtime. However, modern Python (3.5+) supports **optional type hinting**, allowing for better IDE support and static analysis.

```python
# Dynamic typing with Type Hinting
def add_numbers(a: int, b: int) -> int:
    return a + b

result = add_numbers(10, 20) # Types inferred and checked
```

#### 9. Object-Oriented and Multi-Paradigm
Everything in Python is an **object**. It supports **Object-Oriented Programming (OOP)**, functional programming, and procedural styles, allowing developers to choose the best approach for their specific problem.

#### 10. Extensible and Integratable
Python can be extended with modules written in **C, C++, or Rust** for performance-critical tasks. It acts as a "glue language," easily integrating with existing legacy codebases and low-level APIs.
<br>

## 2. How is _Python_ executed?

**Python** source code is not directly executed by the CPU. Instead, it undergoes a multi-stage process involving both **compilation** and **interpretation**.

### Compilation & Interpretation

Python utilizes a hybrid model to balance portability and ease of development.

- **Bytecode Compilation**: When a script is run, the Python interpreter first compiles the high-level source code into **bytecode**. This is an intermediate, platform-independent representation of the code, often stored in `__pycache__` directories as `.pyc` files.
- **Python Virtual Machine (PVM)**: The PVM is the runtime engine that executes the bytecode. It iterates through the instructions and maps them to the corresponding machine-specific actions.

This "compile then interpret" workflow allows Python to be **cross-platform**, as the same bytecode can run on any system with a compatible PVM.

### Bytecode versus Machine Code

Unlike languages like C++ that compile to native **machine code** (binary instructions for a specific CPU), Python's bytecode is a higher-level abstraction. 

While this abstraction ensures flexibility, the additional layer of the PVM can introduce overhead. However, modern implementations mitigate this by using **internal optimizations** and **specialized opcodes** to speed up the execution of common patterns.

### Source Code to Bytecode: Compilation Steps

The transformation from text to executable instructions follows these standard compiler phases:

1.  **Lexical Analysis**: The source code is broken into **tokens** (keywords, identifiers, literals).
2.  **Syntax Parsing**: Tokens are organized into a **Parse Tree** or **Abstract Syntax Tree (AST)** based on Python’s grammar rules.
3.  **Semantic Analysis**: The AST is analyzed for context (e.g., variable scope and name resolution).
4.  **Bytecode Generation**: The final AST is converted into a sequence of bytecode instructions.

### Just-In-Time (JIT) Compilation and Modern Optimizations

As of Python 3.11+, CPython introduced the **Specializing Adaptive Interpreter**. This mechanism identifies "hot" (frequently executed) code and optimizes it by replacing generic bytecode instructions with specialized versions tailored to the specific data types encountered at runtime.

Furthermore, Python 3.13 introduced an experimental **JIT compiler** based on a "copy-and-patch" architecture. This allows the PVM to transform certain bytecode sequences directly into machine code, narrowing the performance gap between Python and compiled languages.

### Code Example: Disassembly of Bytecode

We can inspect the bytecode generated by the compiler using the `dis` module.

```python
import dis

def example_func():
    # Constant folding: 15 * 20 is calculated at compile-time
    return 15 * 20

# Disassemble the function to see PVM instructions
dis.dis(example_func)
```

**Bytecode Output:**

```plaintext
  3           0 LOAD_CONST               1 (300)
              2 RETURN_VALUE
```

In this output, `LOAD_CONST` pushes the pre-calculated value $300$ onto the evaluation stack, and `RETURN_VALUE` returns it to the caller. This demonstrates how the Python compiler performs optimizations like **constant folding** before the PVM even begins interpretation.
<br>

## 3. What is _PEP 8_ and why is it important?

**PEP 8** is the official **Style Guide for Python Code**, established as a **Python Enhancement Proposal**. It defines the conventions for formatting and structuring Python code to maximize **readability**, **consistency**, and **maintainability** across the global Python ecosystem.

As Python creator Guido van Rossum famously stated, "code is read much more often than it is written." Adhering to PEP 8 reduces cognitive load, allowing developers to focus on logic rather than formatting quirks.

### Key Design Principles

*   **Readability**: Prioritizes human comprehension; if a style choice makes code harder to understand, readability takes precedence.
*   **Consistency**: Ensures a uniform "look and feel" within a project and across the community.
*   **The "Pythonic" Way**: Encourages the philosophy that there should be one—and preferably only one—obvious way to write a solution.

### Formatting and Structure

#### Base Rules
*   **Indentation**: Use exactly **4 spaces** per indentation level. Do not use tabs.
*   **Line Length**: Limit lines to a maximum of **79 characters**. While modern tools like **Black** or **Ruff** often default to $88$ or $100$ characters, 79 remains the standard for maximizing compatibility with multi-file side-by-side views.
*   **Blank Lines**: Use two blank lines to surround top-level function and class definitions. Use a single blank line to separate methods inside a class.

#### Naming Styles
*   **Classes**: Use `CapWords` (PascalCase).
*   **Functions and Variables**: Use `lower_case_with_underscores` (snake_case).
*   **Constants**: Use `UPPER_CASE_WITH_UNDERSCORES`.
*   **Modules**: Use short, lowercase names; underscores are discouraged unless necessary.

#### Whitespace Usage
*   **Operators**: Surround assignment ($=$), comparisons ($==, <, >$), and Booleans (`and`, `or`) with a single space.
*   **Delimiters**: Avoid extraneous whitespace inside parentheses, brackets, or braces. Always follow a comma or semicolon with a space.

#### Documentation
*   **Docstrings**: Use triple double quotes (`"""`) for all public modules, functions, classes, and methods.
*   **Comments**: Ensure comments are up-to-date and explain the "why" (intent) rather than the "what" (obvious logic).

### Example: PEP 8 Compliant Implementation

This script utilizes modern **pathlib** (the Pythonic standard for paths) while adhering to PEP 8 conventions:

```python
from pathlib import Path

class DirectoryScanner:
    """Provides utilities for scanning file systems."""

    def __init__(self, target_directory: str):
        self.target_path = Path(target_directory)

    def scan_files(self) -> None:
        """Recursively iterates through directory and prints file paths."""
        if not self.target_path.is_dir():
            return

        for file_path in self.target_path.rglob("*"):
            if file_path.is_file():
                print(file_path.resolve())

if __name__ == "__main__":
    scanner = DirectoryScanner("/path/to/data")
    scanner.scan_files()
```
<br>

## 4. How is memory allocation and garbage collection handled in _Python_?

In Python, **memory allocation** and **garbage collection** are managed automatically by the runtime, primarily through the **Python Memory Manager**. This system abstracts complex memory operations, ensuring safety and developer productivity.

### Memory Allocation

Python manages a private **Heap** containing all objects and data structures. The **Python Memory Manager** controls this heap through several layers:

*   **Hierarchical Allocation**: For small objects ($\le 512$ bytes), Python uses a specialized allocator called `obmalloc`. It organizes memory into **Arenas** ($256$ KB), which are subdivided into **Pools** ($4$ KB), and further into **Blocks**.
*   **Object-Specific Allocators**: Certain types (like `int` or `list`) use dedicated free lists to speed up allocation and reduce fragmentation.
*   **Raw Memory**: Large objects (typically $> 512$ bytes) bypass `obmalloc` and use the standard C `malloc()` to request memory directly from the OS.
*   **Stack vs. Heap**: The **Heap** stores the actual objects and data, while the **Stack** stores references to those objects and the execution frames.

### Garbage Collection

Python utilizes **Reference Counting** as its primary mechanism, supplemented by a **Generational Garbage Collector** to handle cyclic dependencies.

#### Reference Counting

Every Python object contains a field in its header called `ob_refcnt`.
*   The count increases when an object is assigned to a variable or added to a container.
*   The count decreases when a reference is deleted or goes out of scope.
*   When $ref\_count == 0$, the memory is immediately deallocated. Modern Python (3.12+) also uses **Immortal Objects**, which have a fixed reference count to improve performance for shared constants.

```python
import sys

a = [1, 2, 3]
print(sys.getrefcount(a))  # Output: 2 (variable 'a' and the argument to getrefcount)
b = a
print(sys.getrefcount(a))  # Output: 3
```

#### Generational Garbage Collector

To reclaim **Circular References** (where objects point to each other), Python's `gc` module uses a cycle-detecting algorithm.
*   **Generations**: Objects are categorized into $G_0$, $G_1$, and $G_2$.
*   **Promotion**: New objects start in $G_0$. If they survive a collection cycle, they are promoted to $G_1$, and eventually $G_2$.
*   **Thresholds**: Collection is triggered when the number of allocations minus deallocations exceeds a specific **Threshold**. $G_0$ is scanned most frequently, while $G_2$ is scanned least often, following the heuristic that younger objects are more likely to die young.

### Memory Management in Python vs. C

Python's architecture prioritizes safety over manual control:

*   **Abstraction**: Unlike C, where developers use `malloc()` and `free()`, Python’s manager prevents **Memory Leaks** and **Dangling Pointers** automatically.
*   **Overhead**: Python objects have significant overhead; every object must store its **Type Pointer** and **Reference Count**. A 4-byte `int` in C is significantly smaller than a Python `int` object.
*   **Performance**: Python's automatic management introduces occasional "stop-the-world" pauses during **Generational GC** cycles, whereas C offers deterministic performance at the cost of manual memory tracking.
<br>

## 5. What are the _built-in data types_ in _Python_?

Python offers numerous **built-in data types** that provide varying functionalities and utilities for efficient memory management and data manipulation. These are generally categorized by their **mutability**.

### Immutable Data Types

#### 1. int
Represents **arbitrary-precision integers**, such as `42` or `-10`. In modern Python, the **int** type handles all integer sizes automatically, removing the need for a separate "long" type.

#### 2. float
Represents **double-precision floating-point numbers**, such as `3.14` or `-0.001`, following the IEEE 754 standard.

#### 3. complex
Used for mathematical computations involving a real and an imaginary part, represented as $z = a + bj$, where $j = \sqrt{-1}$.

#### 4. bool
A subclass of integers representing logical values: **True** (internally 1) and **False** (internally 0).

#### 5. str
An immutable sequence of **Unicode characters**. Python strings are optimized for performance and support extensive slicing and formatting capabilities.

#### 6. tuple
An ordered, immutable collection of items. **Tuples** are often used to store heterogeneous data and are **hashable**, allowing them to be used as keys in dictionaries.

#### 7. frozenset
An immutable version of a set. It is **hashable** and contains unique elements, making it suitable as a dictionary key or an element of another set.

#### 8. bytes
An immutable sequence of single bytes (8-bit values). It is primarily used for handling **binary data**, such as images, encoded text, or network packets.

#### 9. range
Represents an immutable sequence of numbers, typically used for iterating in loops. It is memory-efficient because it calculates values on demand rather than storing them in memory (**lazy evaluation**).

#### 10. NoneType
The type for the singleton object **None**, which is used to signal the absence of a value, a null pointer equivalent, or a default state.

### Mutable Data Types

#### 1. list
A dynamic, ordered collection of items. **Lists** are highly versatile, supporting indexing, slicing, and various in-place modifications like `append()` and `extend()`.

#### 2. set
An unordered collection of unique, **hashable** items. **Sets** provide optimized $O(1)$ average-time complexity for membership testing and support mathematical operations like intersection and union.

#### 3. dict
A collection of **key-value pairs**. Since Python 3.7+, dictionaries maintain **insertion order** as a guaranteed language feature while providing $O(1)$ average-time complexity for lookups.

#### 4. bytearray
A mutable counterpart to `bytes`. It allows in-place modification of binary sequences without the overhead of creating new objects.

#### 5. memoryview
A generalized pointer that allows accessing the internal data of an object that supports the **buffer protocol** (like `bytes` or `bytearray`) without copying the data.

#### 6. array (array.array)
Space-efficient storage for basic values (integers, floats) constrained to a **single type**. It is available via the `array` module and is more memory-efficient than a list for large datasets of primitive types.

#### 7. deque (collections.deque)
A double-ended queue designed for fast $O(1)$ appends and pops from both ends. It is provided by the `collections` module and is preferred over lists for queue implementations.

#### 8. object
The most fundamental base type in Python. Every class inherits from **object**, and it can be instantiated to create a unique **sentinel** object.

#### 9. types.SimpleNamespace
A simple object that allows for the attribution of arbitrary properties via dot notation. It is often used as a lightweight, mutable alternative to an empty class.

#### 10. types.FunctionType
The internal type for user-defined functions. Functions are **first-class citizens** in Python, meaning they can be passed as arguments, returned from other functions, and assigned attributes.

```python
# Illustrating core built-in types
integer_val = 10                        # int
string_val = "Python 2026"              # str
list_val = [1, 2, 3]                    # list (mutable)
tuple_val = (1, 2, 3)                   # tuple (immutable)
dict_val = {"key": "value"}             # dict (mapping)

# Using complex numbers and sets
complex_num = 2 + 3j                    # complex
unique_elements = {1, 2, 2, 3}          # set: {1, 2, 3}

# Binary and specialized types
raw_data = b"binary"                    # bytes
mutable_buffer = bytearray(raw_data)    # bytearray
```
<br>

## 6. Explain the difference between a _mutable_ and _immutable_ object.

The distinction between **mutable** and **immutable** objects is a core principle of Python’s data model, determining how objects are stored, accessed, and modified in memory.

### Key Distinctions

- **Mutable Objects**: These objects allow their internal state or content to be changed **in-place** after creation. Modifications do not change the object’s unique identity, which is retrieved via `id()`.
- **Immutable Objects**: These objects cannot be altered once created. Any operation that purports to modify an immutable object actually results in the creation of a **new object** with a unique identity and the updated value.

### Common Examples

- **Mutable**: `list`, `set`, `dict`, `bytearray`, and most user-defined classes (unless explicitly made immutable).
- **Immutable**: `int`, `float`, `complex`, `str`, `tuple`, `frozenset`, `bytes`, and `bool`.

### Code Example: Immutability vs. Mutability

The following example illustrates how Python handles memory and identity for both types:

```python
# Immutable objects (str, tuple)
text = "Hello"
my_tuple = (1, 2, 3)

try:
    text[0] = 'M'       # Raises TypeError: 'str' object does not support item assignment
    my_tuple[0] = 100   # Raises TypeError
except TypeError as e:
    print(f"Error: {e}")

# Mutable objects (list)
my_list = [1, 2, 3]
original_id = id(my_list)

my_list.append(4)       # Modified in-place
print(id(my_list) == original_id)  # Output: True (Identity is preserved)

# Reassignment of an immutable integer
x = 10
first_id = id(x)
x += 1                  # Creates a new int object; x now points to a different id
print(id(x) == first_id) # Output: False
```

### Benefits & Trade-Offs

#### Safety and Hashability
**Immutable** objects provide **data integrity** and are inherently **thread-safe** because their state cannot be changed by concurrent processes. Crucially, only immutable objects (or containers like tuples containing only immutable elements) are **hashable**. This allows them to be used as **dictionary keys** or elements in a **set**, as their hash value remains constant.

#### Performance
**Mutable** objects are more memory-efficient when dealing with large datasets or frequent updates. Modifying a collection in-place typically has a time complexity of $O(1)$ for many operations. Conversely, "modifying" an immutable object often requires a full copy of the existing data, leading to $O(n)$ complexity.

### Impact on Operations

- **Memory Management**: Python optimizes memory for specific immutable objects through **interning** (e.g., small integers and certain strings are reused rather than recreated). Mutable objects are managed via dynamic resizing and lack this specific reuse optimization.
- **Function Arguments**: Python utilizes **Pass-by-Assignment**. When a **mutable** object is passed to a function, any modifications made inside the function persist in the original object. When an **immutable** object is passed, the original variable remains unchanged because any "modification" inside the function scope creates a local reference to a new object.
<br>

## 7. How do you _handle exceptions_ in _Python_?

**Exception handling** in Python is a structured mechanism used to manage runtime errors gracefully, ensuring program stability. It relies on a block-based syntax to catch, process, and recover from exceptions without terminating the execution flow unexpectedly.

### Core Components

The standard syntax involves four primary blocks:

- **`try`**: Contains code that might raise an exception.
- **`except`**: Executes if an exception occurs. It is best practice to catch **specific exceptions** (e.g., `ValueError`) rather than using a bare `except:`.
- **`else`**: Executes only if the `try` block completes without any exceptions.
- **`finally`**: Executes regardless of the outcome. This is used for **resource cleanup**, such as closing file descriptors or database connections.

```python
try:
    file = open("data.txt", "r")
    data = int(file.read())
except FileNotFoundError:
    print("Error: File missing.")
except ValueError:
    print("Error: Invalid data format.")
else:
    print(f"Data processed: {data}")
finally:
    if 'file' in locals():
        file.close()
```

### Exception Groups and `except*`

Introduced in Python 3.11, **Exception Groups** (`ExceptionGroup`) allow the propagation of multiple unrelated exceptions simultaneously. This is essential for asynchronous tasks or concurrent executions (e.g., `asyncio`). The `except*` syntax allows you to handle specific exception types within a group.

```python
try:
    raise ExceptionGroup("Batch error", [ValueError("Invalid ID"), TypeError("Limit reached")])
except* ValueError as eg:
    for e in eg.exceptions:
        print(f"Handled ValueError: {e}")
except* TypeError as eg:
    for e in eg.exceptions:
        print(f"Handled TypeError: {e}")
```

### Context Managers (`with` statement)

The `with` keyword implements the **Context Manager** protocol, utilizing `__enter__` and `__exit__` methods. It ensures that resources are automatically released, effectively handling exceptions that occur during resource usage without explicit `finally` blocks.

```python
with open("log.txt", "a") as f:
    f.write("Log entry...")
# File is closed automatically, even if write fails.
```

### Raising and Chaining

The `raise` statement manually triggers an exception. **Implicit and Explicit Chaining** preserves the traceback of the original cause using the `from` keyword, which is critical for debugging complex failures.

```python
def fetch_api():
    try:
        return perform_request()
    except ConnectionError as e:
        # Explicitly chain the original error to a custom exception
        raise RuntimeError("API unavailable") from e
```

### Exception Enrichment and Global Hooks

Modern Python allows attaching metadata to exceptions using the `add_note()` method (3.11+), which is useful for adding contextual information without modifying the exception's message.

#### Global Hooks
For unhandled exceptions, `sys.excepthook` allows developers to define a custom global handler for logging or telemetry before the interpreter exits.

```python
import sys

def global_logger(exctype, value, tb):
    print(f"CRITICAL: {value}")

sys.excepthook = global_logger
```

### Flow Control: `pass` and `continue`

Within an `except` block:
- **`pass`**: Silently suppresses an exception (use with caution).
- **`continue`**: Skips the current iteration of a loop when an error occurs, allowing the rest of a dataset to be processed.

```python
for item in raw_data:
    try:
        process(item)
    except DataEntryError:
        continue # Skip corrupted record and move to next
```
<br>

## 8. What is the difference between _list_ and _tuple_?

**Lists** and **Tuples** are ordered sequences in Python, but they differ significantly in **mutability**, **performance**, and **storage behavior**.

### Key Distinctions

- **Mutability**: Lists are **mutable**, meaning elements can be added, removed, or modified after creation. Tuples are **immutable**; their structure and references cannot be changed once instantiated.
- **Memory & Performance**: Tuples have a lower memory footprint. Lists utilize **over-allocation** to facilitate $O(1)$ amortized time for `append()` operations, whereas tuples are allocated the exact amount of memory required. Consequently, tuples are faster to create and slightly faster to iterate over.
- **Hashability**: Because they are immutable, tuples (containing only hashable elements) are **hashable** and can be used as **dictionary keys** or **set** elements. Lists are **unhashable** and will raise a `TypeError` if used in such contexts.

### When to Use Each

- **Lists** are ideal for collections of items that require frequent updates, resizing, or sorting during a program's execution.
- **Tuples** are preferred for fixed data structures, protecting data from accidental modification, and serving as constant keys in mapping types. They are often used for heterogeneous data (records), whereas lists are typical for homogeneous data.

### Syntax

#### List: Example

```python
my_list = ["apple", "banana"]
my_list.append("cherry")
my_list[1] = "blackberry"
```

#### Tuple: Example

```python
my_tuple = (1, 2, 3, 4)
# Unpacking a tuple
a, b, c, d = my_tuple
# my_tuple[0] = 5  # This would raise a TypeError
```
<br>

## 9. How do you create a _dictionary_ in _Python_?

In **Python**, a **dictionary** is an **ordered** collection of `key:value` pairs that provides $O(1)$ average time complexity for lookups, insertions, and deletions. They are highly optimized hash tables and serve as one of the most fundamental data structures in the language.

### Key Concepts

- **Keys**: Must be **unique** and **hashable** (immutable types like `str`, `int`, or a `tuple` containing only hashable elements).
- **Values**: Can be of any data type, including lists or other dictionaries, and can be duplicated.
- **Ordered**: Since Python 3.7+, dictionaries are guaranteed to maintain the **insertion order** of items.
- **Mutable**: You can add, remove, or modify items after the dictionary is created.

### Creation Methods

There are several idiomatic ways to create a dictionary in Python:

1. **Literal Syntax**: Defining pairs directly within curly braces `{}`.
2. **`dict()` Constructor**: Utilizing keyword arguments or a sequence of key-value pairs.
3. **Dictionary Comprehension**: Generating a dictionary dynamically using an iterable and logic.
4. **`zip()` Function**: Mapping two separate iterables (one for keys, one for values) together.
5. **`fromkeys()` Method**: Creating a dictionary with a predefined set of keys and an optional shared default value.

### Examples

#### Literal Definition
The most common and readable way to initialize a dictionary.

```python
# Creating a dictionary using literals
student = {
    "name": "John Doe",
    "age": 21,
    "courses": ["Math", "Physics"]
}
```

#### The `dict()` Constructor
Useful when keys are valid identifiers or when converting existing sequences into a dictionary mapping.

```python
# Using keyword arguments
user = dict(username="jdoe", status="active", id=452)

# Using a list of tuples (sequence of key-value pairs)
data = dict([("id", 1), ("type", "admin")])
```

#### Dictionary Comprehension
A concise way to transform one iterable into a dictionary, providing high performance for dynamic creation.

```python
# Squaring numbers using comprehension
squares = {x: x**2 for x in range(1, 6)}
# Result: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

#### Using `zip()`
Ideal for merging two distinct lists or tuples into a dictionary mapping.

```python
keys = ["CPU", "GPU", "RAM"]
values = ["Intel i7", "NVIDIA RTX", "32GB"]

# Pairing keys and values into a dictionary
specs = dict(zip(keys, values))
```

#### Using `fromkeys()`
Used to initialize a dictionary with a specific set of keys and a shared default value.

```python
keys = ["task1", "task2", "task3"]
# Initializes all keys with the value "Pending"
todo_list = dict.fromkeys(keys, "Pending")
```
<br>

## 10. What is the difference between _==_ and _is operator_ in _Python_?

### Difference between == and is in Python

Both the **`==`** and **`is`** operators in Python facilitate different types of comparisons:

- The **`==`** operator evaluates **value equality**. It checks if the data held by two objects is equivalent, typically by invoking the `__eq__` method.
- The **`is`** operator evaluates **object identity**. It verifies if two variables reference the exact same instance in memory.

In Python, every object has a unique identifier assigned by the interpreter. The **`is`** operator compares these memory addresses. If $id(a) = id(b)$, then `a is b` evaluates to `True`.

#### Comparison Logic
- **`is`**: Compares the **identity** (memory address) of two objects using the `id()` function.
- **`==`**: Compares the **value** (contents) of two objects by checking for logical equivalence.

#### Code Example
```python
# Initialize two lists with identical values
list_a = [1, 2, 3]
list_b = [1, 2, 3]
list_c = list_a

print(list_a == list_b)  # True: The values are the same
print(list_a is list_b)  # False: They are different objects in memory
print(list_a is list_c)  # True: Both point to the same memory address
```

#### Best Practices for Usage
- **`==`**: Use for standard equality comparisons, such as comparing strings, numbers, or data structures where the content is the primary concern.
- **`is`**: Use exclusively when comparing against **singletons**, most commonly for **`None`** checks (e.g., `if val is None:`), to ensure identity-level precision. Avoid using `is` for comparing literals like integers or strings, as this relies on implementation-specific behavior such as **interning**.
<br>

## 11. How does a _Python function_ work?

**Python functions** are **first-class objects** that encapsulate logic, enable reusability, and manage state through scoping. In Python, a function is an instance of the `function` class, allowing it to be passed as an argument, returned from other functions, and assigned to variables.

### Key Components

- **Function Signature**: Defined by the `def` keyword, it includes the name, parameters (positional, keyword-only, or variadic), and optional **type hints** for static analysis.
- **Function Body**: An indented block of code containing the logic. Python compiles this into **bytecode** (stored in the `__code__` attribute) upon definition.
- **Return Statement**: Explicitly exits a function with a value. If omitted, the function implicitly returns the `None` singleton.
- **Function Object**: When defined, Python creates a name binding in the current namespace that points to the function object stored in memory.

### Execution Process

When a function is invoked, the Python interpreter performs the following steps:

1. **Frame Creation**: A **Frame Object** is pushed onto the **Call Stack**. This frame encapsulates the execution environment, including the local symbol table and the evaluation stack.
2. **Parameter Binding**: Arguments are assigned to parameters using **pass-by-object-reference** (also known as pass-by-assignment). If a mutable object (e.g., a `list`) is passed, modifications inside the function affect the original object.
3. **Bytecode Execution**: The **Python Virtual Machine (PVM)** executes the bytecode. Since Python 3.11+, the **Specializing Adaptive Interpreter** may optimize this bytecode inline for increased performance.
4. **Return and Cleanup**: Upon a `return` or reaching the end of the block, the return value is passed to the calling context, the frame is popped, and local variables are eligible for **Garbage Collection** via reference counting.

### Scope and Variable Resolution

Python uses the **LEGB Rule** to resolve names during execution:

#### The LEGB Rule
- **Local (L)**: Names assigned within the function (and not declared global).
- **Enclosing (E)**: Names in the local scope of any enclosing functions (relevant for **Closures**).
- **Global (G)**: Names assigned at the top level of the module or declared via the `global` keyword.
- **Built-in (B)**: Names pre-assigned in the `builtins` module (e.g., `len`, `range`).

```python
def outer_function(x: int):
    # Enclosing scope
    y = 10 
    
    def inner_function(z: int) -> float:
        # Local scope accessing Enclosing (x, y) and Global
        return (x + y + z) * 1.0 
    
    return inner_function

# Usage
closure = outer_function(5)
result = closure(3) # Result: 18.0
```

### Advanced Function Mechanics

- **Closures**: Functions that "remember" values from their enclosing lexical scope even after the outer function has finished executing, stored in the `__closure__` attribute.
- **Decorators**: Higher-order functions that take a function as an argument and return a new function, typically to extend behavior without modifying the source code.
- **Recursion Limits**: Python imposes a **maximum recursion depth** (default is usually 1000) to prevent infinite recursion from exhausting the C stack, though modern interpreters handle frame management more efficiently.

### Avoiding Side Effects

Functions should ideally be **pure**—returning values based solely on inputs without modifying global state. Using the `nonlocal` or `global` keywords allows modification of outer scopes but increases complexity and reduces predictability. Encapsulating logic within functions ensures that data $x$ processed by $f(x)$ remains isolated, enhancing maintainability.
<br>

## 12. What is a _lambda function_, and where would you use it?

A **lambda function** is a small, **anonymous function** defined using the `lambda` keyword. Unlike standard functions defined with `def`, lambdas are typically used for short-lived operations where a formal name is unnecessary for the logic being performed.

### Distinctive Features

#### Anonymity
Lambdas are not bound to a name by default, making them ideal for **one-off** utility tasks within a localized scope, such as inside a function call.

#### Single Expression Body
The body is strictly limited to a **single expression**. This facilitates brevity but prevents the use of multiple statements, assignments, or complex control flow (like loops) within the function body.

#### Implicit Return
There is no explicit `return` statement; the evaluated result of the expression is returned automatically. The syntax follows: $\text{lambda arguments: expression}$.

#### Conciseness
Lambdas streamline code by allowing function definitions in-place, reducing the structural overhead of defining a full function block for simple transformations or predicates.

### Common Use Cases

#### Map, Filter, and Reduce
Functions like `map()` and `filter()` often take a lambda as an argument to define transformations or predicates on the fly. 
```python
numbers = [1, 2, 3, 4]
# Squaring elements in a list
squared = list(map(lambda x: x**2, numbers)) # [1, 4, 9, 16]
```
Note: To use `reduce()`, you must import it from the `functools` module.

#### Sorting and Min/Max
Lambdas frequently serve as a **custom key** for sorting complex data structures. This is highly effective for ordering dictionaries or objects by specific attributes:
```python
data = [{'name': 'Alice', 'age': 30}, {'name': 'Bob', 'age': 25}]
# Sort by age attribute
sorted_data = sorted(data, key=lambda x: x['age'])
```

#### Callbacks and Closures
Lambdas are used in GUI frameworks or asynchronous programming as **callbacks**, where a function is passed as an argument to be executed upon an event. They are also useful as return values from higher-order functions to create specialized behaviors (closures) without naming every intermediate function.

### Notable Limitations

#### Readability and PEP 8
Named functions are preferred when logic is not immediately obvious. **PEP 8** specifically discourages binding lambdas to identifiers (e.g., `f = lambda x: x+1`) because it defeats the purpose of anonymity; a `def` statement should be used for such cases.

#### Documentation and Debugging
Lambdas cannot contain **docstrings**, making them harder to document. Additionally, because they are anonymous, tracebacks will identify them only as `<lambda>`, which can complicate the debugging process compared to named functions.
<br>

## 13. Explain _*args_ and _**kwargs_ in _Python_.

In **Python**, `*args` and `**kwargs` are special syntaxes used in function definitions to handle a **variable number of arguments**, providing flexibility in how functions are called and how data is passed.

`*args` collects extra positional arguments into a **tuple**, while `**kwargs` collects extra keyword arguments into a **dictionary**.

### **\*args**: Variable Positional Arguments

- **Mechanism**: The single asterisk `*` is the **unpacking operator**. When placed before a parameter name in a function definition, it packs any additional positional arguments into a **tuple**. While `args` is the standard naming convention, only the `*` is syntactically mandatory.
- **Use-Case**: Ideal for functions where the number of inputs is unknown at runtime, such as mathematical aggregators or API wrappers that forward arguments to other functions.

#### Code Example: `*args`

```python
def sum_all(*args):
    # args is a tuple of all positional arguments passed
    return sum(args)

print(sum_all(1, 2, 3, 4, 5))  # Output: 15
```

### **\*\*kwargs**: Variable Keyword Arguments

- **Mechanism**: The double asterisk `**` captures any named (keyword) arguments that were not explicitly defined in the parameter list. These are stored in a **dictionary**, where keys represent the argument names and values represent the argument data.
- **Use-Case**: Widely used in **class inheritance** (passing parameters to a superclass constructor) and **decorators** to handle arbitrary configuration settings without modifying the function signature.

#### Code Example: `**kwargs`

```python
def print_metadata(**kwargs):
    # kwargs is a dictionary of named arguments
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_metadata(version="1.2.0", author="Dev", status="Production")
# Output:
# version: 1.2.0
# author: Dev
# status: Production
```

### Argument Order and Syntax Rules

Python requires a specific order in the function signature to prevent ambiguity and ensure correct argument binding. The hierarchy is defined as follows:

1.  **Standard Positional Arguments**
2.  **Variable Positional Arguments** (`*args`)
3.  **Keyword-Only Arguments** (with or without default values)
4.  **Variable Keyword Arguments** (`**kwargs`)

#### Example of a Complex Signature:

```python
def complex_func(a, b, *args, mode="fast", **kwargs):
    print(a, b, args, mode, kwargs)

complex_func(1, 2, 3, 4, mode="slow", debug=True)
# Output: 1 2 (3, 4) slow {'debug': True}
```

This structure allows the interpreter to differentiate between values intended for specific parameters and those intended for the flexible `*args` or `**kwargs` containers. Note that in modern Python, a bare `*` can also be used in a signature to force all subsequent arguments to be keyword-only.
<br>

## 14. What are _decorators_ in _Python_?

In Python, a **decorator** is a design pattern and a language feature that allows you to dynamically modify or extend the behavior of functions or classes without permanently changing their source code. They are a form of **metaprogramming** where one function (the wrapper) modifies the behavior of another.

### How Decorators Work

- **Higher-Order Functions**: Decorators are functions that take another function as an argument and return a new function.
- **Closures**: They leverage Python’s support for **closures** to "wrap" the original function, allowing code execution both before and after the target function runs.
- **First-Class Objects**: Since functions in Python are **first-class objects**, they can be passed as arguments, assigned to variables, and returned from other functions.

### Common Use Cases

- **Authorization**: Verifying user permissions or authentication tokens before executing a route or method.
- **Logging and Profiling**: Measuring execution time ($\Delta t$) or recording function call frequency.
- **Caching/Memoization**: Optimizing performance by storing results of expensive computations (e.g., via `@functools.cache`).
- **Validation**: Enforcing type safety, data constraints, or input sanitization.
- **Rate Limiting**: Throttling how often a specific function can be invoked within a set timeframe.

### Implementing Decorators

#### Basic Decorator
Modern Python development requires `functools.wraps` to preserve the original function's **metadata** (such as `__name__`, `__doc__`, and type annotations).

```python
from functools import wraps
from typing import Callable, Any

def my_decorator(func: Callable) -> Callable:
    @wraps(func)
    def wrapper(*args: Any, **kwargs: Any) -> Any:
        # Logic executed before the function
        result = func(*args, **kwargs)
        # Logic executed after the function
        return result
    return wrapper

@my_decorator
def say_hello(name: str) -> None:
    """Greets the user."""
    print(f"Hello, {name}!")
```

#### Decorators with Arguments
To pass arguments to the decorator itself, you must implement an additional layer of nesting, known as a **decorator factory**.

```python
from functools import wraps
from typing import Callable, Any

def repeat(times: int) -> Callable:
    def decorator(func: Callable) -> Callable:
        @wraps(func)
        def wrapper(*args: Any, **kwargs: Any) -> Any:
            result = None
            for _ in range(times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator

@repeat(times=3)
def greet() -> None:
    print("Execution...")
```

### The @ Syntax and Metadata Preservation

The `@decorator` syntax is **syntactic sugar**. The following two approaches are functionally identical:

```python
# Modern Syntactic Sugar
@my_decorator
def func(): ...

# Manual Equivalent
func = my_decorator(func)
```

Without `@wraps(func)`, the decorated function would lose its identity, appearing to debugging tools and IDEs as the internal `wrapper` function. In professional 2026 development, preserving this **introspection** capability is essential for maintainability, documentation generators, and robust type-checking via tools like MyPy or Pyright.
<br>

## 15. How can you create a _module_ in _Python_?

You can **create** a Python module through the following standard methods:

-   **Define**: Save a Python file with a `.py` extension. This file acts as a **module**, where the filename (without the extension) serves as the module name.
-   **Package Initialization**: To organize multiple modules into a **package**, place an `__init__.py` file inside the directory. While implicit namespace packages exist, including this file explicitly marks a directory as a **regular package** and allows for package-level initialization.

Next, use the **import** statement to access the module and its functionality within your project.

### Code Example: Creating a `math_operations` Module

#### Module Definition

Save the below code as a file named `math_operations.py`. Note the use of **type hints**, which is standard for modern Python modules:

```python
# math_operations.py

def add(x: float, y: float) -> float:
    return x + y

def subtract(x: float, y: float) -> float:
    return x - y

def multiply(x: float, y: float) -> float:
    return x * y

def divide(x: float, y: float) -> float:
    """Returns the result of $\frac{x}{y}$"""
    if y == 0:
        raise ValueError("Cannot divide by zero.")
    return x / y
```

#### Module Usage

You can utilize the `math_operations` module by using **import** as shown below:

```python
import math_operations

# Access functions using the module prefix
result = math_operations.add(4, 5)
print(result)  # Output: 9.0

result = math_operations.divide(10, 5)
print(result)  # Output: 2.0
```

Alternatively, use the `from` syntax to import specific members directly into the **local namespace**:

```python
from math_operations import add, subtract

result = add(3, 2)
print(result) # Output: 5.0
```

### Best Practices

To ensure the module is professional and reusable, follow these **Best Practices**:

-   **Namespace Safety**: Avoid using `from module import *` as it can lead to **name collisions** and reduces code readability (making it difficult for linters and IDEs to track origins).
-   **Execution Guard**: Use the `__name__` global variable to prevent code from executing automatically when the module is imported.

```python
def main():
    # Logic for manual testing or CLI usage
    print("Testing add function:", add(10, 20))

if __name__ == "__main__":
    main()
```

This ensures that the block following `if __name__ == "__main__":` only runs when the script is executed directly, keeping the module "clean" for external imports.
<br>

## 16. What are _async_/_await_ in _Python_, and how does the _event loop_ work?

`async`/`await` is Python's native syntax (introduced in **PEP 492**, Python 3.5) for writing **coroutine-based concurrency**. It enables a single thread to handle thousands of **I/O-bound** operations cooperatively, without the overhead of OS threads or the contention of the **Global Interpreter Lock (GIL)**.

### Concurrency vs. Parallelism

A crucial distinction that interviewers probe:

- **Concurrency**: Dealing with many tasks by **interleaving** their execution (one CPU core, tasks take turns). This is what `asyncio` provides.
- **Parallelism**: Executing many tasks **simultaneously** on multiple cores (e.g., `multiprocessing`).

Because of the **GIL**, `asyncio` does *not* speed up **CPU-bound** work — it shines for **I/O-bound** workloads (network calls, disk, databases) where the program would otherwise sit idle waiting on `read()`/`write()` syscalls.

### How the Event Loop Works

The **event loop** is the orchestrator. It maintains a queue of ready-to-run tasks and a set of resources being awaited (sockets, timers).

1. A coroutine runs until it hits an `await` on something not yet ready (e.g., a network response).
2. At that point it **yields control** back to the loop, returning a state machine that "remembers" where it paused.
3. The loop registers the awaited resource (often via `selectors`/`epoll`/`kqueue`) and runs **other** ready tasks.
4. When the OS signals the resource is ready, the loop **resumes** the suspended coroutine exactly where it left off.

This cooperative model means a single blocking call (e.g., `time.sleep`, a heavy CPU loop) **freezes the entire loop**, starving every other task.

### Coroutines, Awaitables, and Tasks

- **Coroutine**: The object returned by calling an `async def` function. Calling it does **nothing** until it is awaited or scheduled.
- **Awaitable**: Anything usable with `await` — coroutines, `Task`s, and `Future`s.
- **Task**: A coroutine *wrapped and scheduled* on the loop so it runs concurrently with others.

```python
import asyncio

async def fetch(name: str, delay: float) -> str:
    await asyncio.sleep(delay)  # non-blocking; yields to the loop
    return f"{name} done in {delay}s"

async def main() -> None:
    # Sequential: ~3s total (each awaited one after another)
    print(await fetch("A", 1))
    print(await fetch("B", 2))

asyncio.run(main())  # asyncio.run sets up and tears down the loop
```

### Running Coroutines Concurrently

The real value appears when tasks overlap. A common interview trap is awaiting calls sequentially when they could be concurrent.

```python
import asyncio

async def fetch(name: str, delay: float) -> str:
    await asyncio.sleep(delay)
    return name

# Modern, structured approach (Python 3.11+): TaskGroup
async def main() -> None:
    async with asyncio.TaskGroup() as tg:
        t1 = tg.create_task(fetch("A", 1))
        t2 = tg.create_task(fetch("B", 2))
    # Block exits only when all tasks finish (~2s, not 3s)
    print(t1.result(), t2.result())

asyncio.run(main())
```

`asyncio.TaskGroup` is preferred over the older `asyncio.gather` because it provides **structured concurrency**: if one child task raises, the others are **cancelled**, and exceptions propagate together via an `ExceptionGroup` (catchable with `except*`).

### Async Context Managers and Iterators

Modern async code frequently uses `async with` and `async for`, backed by `__aenter__`/`__aexit__` and `__anext__`.

```python
import asyncio
from collections.abc import AsyncIterator

async def stream_lines() -> AsyncIterator[int]:
    for i in range(3):
        await asyncio.sleep(0.1)
        yield i  # this is an async generator

async def main() -> None:
    async for value in stream_lines():
        print(value)

asyncio.run(main())
```

### Common Pitfalls

- **Forgetting `await`**: `fetch(...)` alone creates a coroutine that never runs and emits a `RuntimeWarning: coroutine was never awaited`.
- **Blocking the loop**: Calling synchronous blocking code (e.g., `requests.get`, `time.sleep`) stalls everything. Offload it with `await asyncio.to_thread(blocking_fn, ...)`.
- **Fire-and-forget tasks**: A `Task` referenced by nothing can be garbage-collected mid-flight; keep a reference or use a `TaskGroup`.
- **Mixing sync and async**: You cannot `await` inside a regular `def`, and you cannot call `asyncio.run()` from within an already-running loop.

In professional 2026 development, `async`/`await` underpins high-throughput web frameworks (FastAPI, ASGI servers like Uvicorn) and is the standard for scalable network services where threads would be too costly.
<br>



#### Explore all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

