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

**Python** is a versatile and popular high-level programming language known for its simplicity, **elegant syntax**, and a vast ecosystem of libraries. Let's look at the key features that make Python stand out.

### Key Features of Python

#### 1. Interpreted and Interactive
Python executes code **line-by-line** via an interpreter, making it ideal for rapid prototyping and debugging. Modern versions also incorporate Just-In-Time (JIT) compilation for improved performance.

#### 2. Easy to Learn and Read
Python's **clean, readable syntax**, often resembling plain English, reduces the cognitive load for beginners and experienced developers alike by using indentation to define code blocks.

#### 3. Cross-Platform Compatibility
Python is portable, running on various platforms such as Windows, Linux, and macOS without requiring platform-specific modifications.

#### 4. Modular and Scalable
Developers can organize their code into modular packages and **reusable** functions, promoting better structure and maintainability for large applications.

#### 5. Rich Library Ecosystem
The Python Package Index (PyPI) hosts **hundreds of thousands** of libraries, providing robust solutions for tasks ranging from web development to artificial intelligence.

#### 6. Exceptionally Versatile
From web applications to scientific computing and automation, Python is a general-purpose language equally proficient in diverse domains.

#### 7. Memory Management
Python automatically allocates and manages memory using a private heap and **garbage collection**, shielding developers from low-level tasks like manual deallocation.

#### 8. Dynamically Typed
Python infers the data type of a variable during execution, easing the **declaration** and manipulation of variables, while supporting optional static type hinting.

#### 9. Object-Oriented
Python supports object-oriented paradigms where everything is an **object**, offering attributes and methods to encapsulate and manipulate data efficiently.

#### 10. Extensible
With its C-language API, developers can integrate performance-critical tasks and existing C/C++ modules directly with Python code.
<br>

## 2. How is _Python_ executed?

**Python** source code undergoes a multi-stage process involving compilation, interpretation, and dynamic optimization before execution. Below are the technical details of this workflow as of 2026.

### Compilation & Interpretation

Python (specifically the standard **CPython** implementation) utilizes a hybrid execution model:

- **Bytecode Compilation**: The source code is first compiled into **Bytecode**, a low-level, platform-independent intermediate representation. This bytecode is a sequence of instructions for the Python Virtual Machine (PVM), often cached in `.pyc` files.
- **The PVM Loop**: The PVM is a stack-based interpreter that iterates through bytecode instructions and executes them sequentially.

### The Compilation Pipeline

The transformation from source code to executable bytecode involves strict steps:

1. **Lexical Analysis**: The tokenizer breaks the source text into individual **tokens** (identifiers, keywords, operators).
2. **Parsing**: Tokens are structured into an **Abstract Syntax Tree (AST)**, which validates the grammar and syntax.
3. **Bytecode Generation**: The compiler traverses the AST, generates a Control Flow Graph (CFG), and emits the final bytecode instructions.

### Adaptive Execution and JIT

Modern Python (post-3.11) employs **Tiered Execution** to optimize performance dynamically:

- **Tier 1: Adaptive Interpretation**: The PVM monitors code as it runs. If specific instructions are executed frequently with consistent types, the interpreter "quickens" them by replacing generic bytecode with **specialized instructions** optimized for those specific types.
- **Tier 2: Just-In-Time (JIT) Compilation**: For highly active code paths ("hot spots"), the JIT compiler (utilizing a copy-and-patch architecture) translates specialized bytecode into native machine code. This bypasses the interpreter loop entirely for those segments, significantly reducing overhead.

### Bytecode versus Machine Code

Unlike languages like C++ that compile directly to hardware-specific **Machine Code**, Python compiles to **Bytecode**.
- **Portability**: Bytecode allows Python programs to run on any device with a PVM, regardless of the underlying hardware.
- **Performance**: While the extra layer of interpretation historically caused latency, the modern **Adaptive Interpreter** and **JIT** bridge the gap by compiling hot code to machine code at runtime.

### Code Example: Disassembly and Optimization

We can inspect the bytecode using the `dis` module. The Python compiler performs **Peephole Optimization** during the compilation phase, such as pre-calculating constant expressions.

```python
import dis

def example_func():
    # The compiler evaluates 15 * 20 at compile-time (Constant Folding)
    return 15 * 20

# Disassemble to view bytecode instructions
dis.dis(example_func)
```

**Output**:
The output reveals that the multiplication does not happen at runtime; the result (`300`) is loaded directly.

```plaintext
  4           0 LOAD_CONST               1 (300)
              2 RETURN_VALUE
```
<br>

## 3. What is _PEP 8_ and why is it important?

### What is PEP 8?

**PEP 8** (Python Enhancement Proposal 8) is the standard style guide for writing Python code. Authored by Guido van Rossum, Barry Warsaw, and Nick Coghlan, it provides guidelines to ensure that Python code is formatted consistently across the entire ecosystem.

### Why It Is Important

-   **Readability**: Code is read much more often than it is written. PEP 8 ensures that code written by one developer appears familiar to another, reducing the cognitive load required to understand the logic.
-   **Consistency**: Adhering to a uniform style makes codebases easier to maintain and review.
-   **Tooling Standard**: Modern linters (e.g., `ruff`, `flake8`) and auto-formatters (e.g., `black`) rely on PEP 8 definitions to automate code quality checks.

### Base Rules

-   **Indentation**: Use **4 spaces** per indentation level. Do not use tabs.
-   **Line Length**: The official guideline is **79 characters** to facilitate side-by-side editing, though many modern teams adjust this limit (e.g., to 88 or 100 characters).
-   **Blank Lines**: Surround top-level function and class definitions with two blank lines. Method definitions inside a class are separated by a single blank line.

### Naming Styles

-   **Class Names**: Use `CapWords` (also known as PascalCase).
-   **Functions & Variables**: Use `snake_case` (lowercase with underscores).
-   **Constants**: Use `UPPER_CASE_WITH_UNDERSCORES`.
-   **Non-public Attributes**: Use a leading underscore (e.g., `_internal_var`) to indicate internal use.

### Documentation & Whitespace

-   **Docstrings**: Use triple double quotes (`"""`) for documentation strings.
-   **Whitespace**: Avoid extraneous whitespace immediately inside parentheses, brackets, or braces. Always surround binary operators (like assignment `=` or addition `+`) with a single space.
-   **Imports**: Place imports at the top of the file, on separate lines, grouped in order: standard library, third-party, and local application.

### Example: Modern Compliant Code

The following example demonstrates PEP 8 spacing, naming, type hinting, and standard library usage (using `pathlib` instead of the older `os` module):

```python
from pathlib import Path

def list_files(base_path: str) -> None:
    """
    Recursively print all file paths in the given directory.
    """
    directory = Path(base_path)

    # rglob is the modern, idiomatic way to walk directories
    for file_path in directory.rglob('*'):
        if file_path.is_file():
            print(file_path)

if __name__ == "__main__":
    list_files('/var/log')
```
<br>

## 4. How is memory allocation and garbage collection handled in _Python_?

In Python, memory management is automated via a **private heap** and a hybrid **garbage collection** mechanism.

### Memory Allocation

*   **Private Heap**: The Python Memory Manager ensures all objects and data structures are stored in a private heap, inaccessible to the programmer directly.
*   **Pymalloc Strategy**: CPython utilizes a specialized allocator (optimized for objects smaller than 512 bytes) to reduce fragmentation and system calls. It organizes memory hierarchically:
    1.  **Arenas**: Large, 256KB chunks mapped from the OS.
    2.  **Pools**: 4KB subdivisions within arenas.
    3.  **Blocks**: Fixed-size units within pools used to store data.
*   **Raw Allocators**: For larger objects, Python bypasses the specialized allocator and interacts directly with the system's standard C allocator (e.g., `malloc`).

### Garbage Collection

Python primarily uses **Reference Counting**, supplemented by a **Generational Garbage Collector**.

#### Reference Counting

*   Every internal object carries a reference count (`ob_refcnt`). When this count drops to $0$, the memory is **immediately deallocated**.
*   This mechanism is highly efficient for the majority of objects, releasing resources without waiting for a GC cycle.
*   **Immortal Objects**: In modern Python (PEP 683), core objects (like `None`, `True`, and small integers) are marked as "Immortal." Their reference counts are not tracked, which improves performance and thread safety.

```python
import sys
x = []
# Output is typically 2: one for variable 'x', one for the getrefcount argument
print(sys.getrefcount(x)) 
```

#### Cycle-Detecting Garbage Collector

*   Reference counting cannot resolve **circular references** (e.g., List A contains List B, and List B contains List A).
*   A separate Cycle-Detecting GC runs periodically to identify these unreachable isolated subgraphs.
*   **Generational Hypothesis**: The GC classifies objects into three generations (0, 1, 2). New objects start in Generation 0. If they survive a collection sweep, they are promoted to older generations. Older generations are scanned less frequently, minimizing runtime overhead.

### Memory Management in Python vs. C

*   **Abstraction**: Python developers are freed from manual `malloc`/`free` calls, eliminating classes of bugs like memory leaks and dangling pointers common in C.
*   **Overhead**: Python objects are C structures containing metadata (headers, reference counts), resulting in higher memory usage than equivalent raw C data types.
*   **Performance**: While Python's allocator is optimized, the overhead of maintaining reference counts and running the cyclic GC makes it less memory-efficient and generally slower than C's manual management.
<br>

## 5. What are the _built-in data types_ in _Python_?

Python provides a rich set of **built-in data types** generally categorized by their mutability—whether their value can be changed after creation.

### Immutable Data Types
These objects cannot be modified once created.

#### 1. int
Represents arbitrary-precision integers.
```python
x = 42
```

#### 2. float
Represents double-precision floating-point numbers.
```python
pi = 3.14159
```

#### 3. complex
Comprises a real and an imaginary part, denoted with a `j` suffix.
```python
c = 3 + 4j
```

#### 4. bool
A subtype of `int` representing boolean truth values: `True` (1) and `False` (0).

#### 5. str
An immutable sequence of Unicode code points (text).
```python
s = "Python 2026"
```

#### 6. tuple
An ordered, immutable collection of items, often heterogeneous.
```python
t = (1, "apple", 3.14)
```

#### 7. frozenset
An immutable version of a `set`. It is hashable and can be used as a dictionary key.
```python
fs = frozenset([1, 2, 3])
```

#### 8. bytes
An immutable sequence of integers in the range $0 \le x < 256$, used for binary data.
```python
b = b'binary data'
```

#### 9. range
Represents an immutable sequence of numbers, typically used in loops.
```python
r = range(0, 10, 2)
```

#### 10. NoneType
Represents the null value or the absence of a value, accessed via the `None` keyword.

### Mutable Data Types
These objects support in-place modifications.

#### 1. list
A dynamic, ordered sequence that can contain mixed data types.
```python
nums = [1, 2, 3]
nums.append(4)
```

#### 2. set
An unordered collection of unique, hashable objects.
```python
unique_ids = {101, 102, 103}
```

#### 3. dict
A mapping of hashable **keys** to arbitrary **values**.
```python
user = {'name': 'Alice', 'id': 42}
```

#### 4. bytearray
A mutable sequence of integers in the range $0 \le x < 256$. It allows in-place modification of binary data.
```python
ba = bytearray(b'hello')
ba[0] = 87  # Changes 'h' to 'W'
```

#### 5. memoryview
Allows Python code to access the internal data of an object (like `bytes` or `bytearray`) without copying, supporting the buffer protocol.
```python
mv = memoryview(b'abc')
```
<br>

## 6. Explain the difference between a _mutable_ and _immutable_ object.

### Key Distinctions

In Python, every variable holds a reference to an object instance. The distinction lies in whether that object's value can change after it is created.

- **Mutable Objects**: The internal state can be modified in place. The object's memory address (identity) remains the same across modifications.
- **Immutable Objects**: The internal state cannot be changed. Any operation that appears to modify the value actually creates a **new object** with a new memory address.

### Common Examples

- **Mutable**: `list`, `dict`, `set`, `bytearray`
- **Immutable**: `int`, `float`, `complex`, `str`, `tuple`, `frozenset`, `bytes`

### Code Example: Immutability in Python

The following code demonstrates that modifying a **mutable** list keeps the same ID, whereas modifying an **immutable** integer changes the ID (rebinding). It also shows the `TypeError` raised when attempting structural changes on immutable types.

```python
# --- Mutable Object (List) ---
my_list = [1, 2]
print(f"Original List ID: {id(my_list)}")

my_list.append(3)  # Modifies in-place
print(f"Modified List ID: {id(my_list)}")  # ID remains the same

# --- Immutable Object (Integer & Tuple) ---
num = 10
print(f"Original Int ID:  {id(num)}")

num += 1  # Rebinds variable to a NEW object
print(f"New Int ID:       {id(num)}")      # ID changes

# Structural modification raises TypeError
my_tuple = (1, 2)
try:
    my_tuple[0] = 100 
except TypeError as e:
    print(f"Error: {e}") # Tuples do not support item assignment
```

### Benefits & Trade-Offs

**Immutability** ensures **hashability**, meaning immutable objects can serve as dictionary keys or set elements. It also provides inherent **thread safety**, as the state cannot change unexpectedly during concurrent execution.

**Mutability** provides better **performance** for large collections. Modifying a large list in place is $O(1)$ or amortized $O(1)$, whereas modifying an immutable sequence (like a string) often requires copying the entire structure, resulting in $O(N)$ complexity.

### Impact on Operations

- **Parameter Passing**: Python passes references by assignment. If a function modifies a **mutable** argument (e.g., appending to a list), the change is reflected globally. If it modifies an **immutable** argument, it only changes the local reference, leaving the external variable untouched.

- **Memory Efficiency**: **Mutable** objects allow in-place updates, reducing memory churn. However, Python caches small **immutable** objects (like small integers and interned strings) to optimize memory usage.
<br>

## 7. How do you _handle exceptions_ in _Python_?

**Exception handling** is a fundamental mechanism in Python that safeguards code against runtime errors, ensuring robust execution flows. The core syntax relies on the `try`, `except`, `else`, and `finally` blocks.

### Core Components

- **`try`**: The block containing code that might raise an exception.
- **`except`**: catche and handles exceptions raised within the `try` block.
- **`else`**: Executes only if the `try` block completes **without** raising an exception.
- **`finally`**: Executes unconditionally after the `try` (and `except`/`else`) blocks. It is primarily used for cleanup operations like closing connections.

### Handling Strategies: Specific, Generic, and Groups

Best practice dictates handling **specific** exceptions first. However, a catch-all is sometimes necessary at the end. Since Python 3.11+, handling multiple unrelated exceptions (often from asynchronous tasks) is supported via `ExceptionGroup` and the `except*` syntax.

```python
try:
    risky_operation()
except (IndexError, KeyError):     # Handle specific standard exceptions
    handle_lookup_error()
except* ValueError:                # Handle part of an ExceptionGroup (Python 3.11+)
    handle_async_validation_error()
except Exception as e:             # General catch-all (Must be last)
    log_generic_error(e)
finally:
    cleanup_resources()
```

### Raising Exceptions

Use the `raise` keyword to trigger exceptions manually when specific conditions are not met, or to re-propagate caught exceptions.

**Raise** a specific exception:
```python
def divide(a, b):
    if b == 0:
        raise ZeroDivisionError("Divisor cannot be zero")
    return a / b
```

**Re-raise** to propagate an error up the stack:
```python
try:
    divide(10, 0)
except ZeroDivisionError:
    logger.error("Calculation failed")
    raise  # Re-raises the active ZeroDivisionError
```

### Resource Management with `with`

The `with` keyword is the standard for managing resources. It utilizes **Context Managers** (objects implementing `__enter__` and `__exit__`) to ensure resources are automatically released, regardless of whether the operation succeeds or fails.

```python
with open("example.txt", "r") as file:
    data = file.read()
# File is automatically closed here, even if read() raises an error.
```

### Control Flow: `pass`, `continue`, and `else`

Control flow keywords allow you to fine-tune how the program proceeds after handling (or avoiding) an error.

- **`pass`**: Silently ignores the exception.
  ```python
  except IgnorableError:
      pass
  ```
- **`continue`**: Used in loops to skip the rest of the current iteration and proceed to the next one.
  ```python
  for item in data:
      try:
          process(item)
      except InvalidItemError:
          continue
  ```
- **`else`**: Placing code in the `else` block prevents the `try` block from becoming too broad. It ensures that exceptions raised by the "success logic" are not caught by the `except` block intended for the "risky logic".

### Global Callback: `sys.excepthook`

To handle **uncaught exceptions** globally (e.g., logging fatal errors before the program terminates), you can override `sys.excepthook`.

```python
import sys

def global_exception_handler(exc_type, value, traceback):
    print(f"Unhandled critical error: {value}")
    # Call the default hook to ensure standard behavior (printing stack trace)
    sys.__excepthook__(exc_type, value, traceback)

sys.excepthook = global_exception_handler
```

*Note*: `sys.excepthook` does not capture `SystemExit` or interactive session errors like `SyntaxError`.
<br>

## 8. What is the difference between _list_ and _tuple_?

**Lists** and **Tuples** are both sequence data types in Python that support indexing and slicing. However, they serve different operational purposes.

### Key Distinctions

- **Mutability**: **Lists** are mutable, allowing dynamic modification (addition, removal, or item assignment). **Tuples** are immutable; once created, their structure cannot be changed.
- **Performance**: **Tuples** are more memory-efficient and faster to iterate over than lists due to fixed memory allocation.
- **Syntax**: **Lists** use square brackets `[]`. **Tuples** use parentheses `()` (though the comma `,` is the primary defining operator).

### When to Use Each

- **Lists**: Ideal for **homogeneous** collections of data where the size or content may change (e.g., a stack of files).
- **Tuples**: Ideal for **heterogeneous** data structures representing a single logical record (e.g., coordinates $(x, y)$ or database rows), or when a hashable key is required for a dictionary.

### Syntax

#### List: Mutable Sequence

```python
my_list = ["apple", "banana", "cherry"]
my_list.append("date")      # Modification allowed
my_list[1] = "blackberry"   # Item assignment allowed
```

#### Tuple: Immutable Record

```python
my_tuple = (1, 2, 3, 4)
# my_tuple[0] = 5  # Raises TypeError
a, b, *rest = my_tuple  # Tuple unpacking
```
<br>

## 9. How do you create a _dictionary_ in _Python_?

Here is the updated answer regarding creating dictionaries in Python, tailored for technical accuracy in 2026.

**Python dictionaries** are mutable, ordered (since Python 3.7+), and versatile data structures that map unique keys to values for efficient data retrieval.

### Key Concepts

- A **dictionary** stores data in `key: value` pairs.
- **Keys** must be unique and **hashable** (immutable types like strings, numbers, or tuples).
- **Values** can be of any data type and can be duplicated.

### Creation Methods

There are several standard ways to instantiate a dictionary:

1.  **Literal Definition**: The most common method using curly braces `{}`.
2.  **`dict()` Constructor**: Creates a dictionary from keyword arguments or an iterable of pairs.
3.  **Dictionary Comprehension**: A concise, functional way to construct dictionaries dynamically.
4.  **`zip()` Function**: Combines two iterables (keys and values) into a dictionary.
5.  **`fromkeys()` Method**: Creates a new dictionary with specified keys and a default value.

### Examples

#### Dictionary Literal Definition

The most direct syntax using curly braces.

```python
# Literal definition
student = {
    "name": "John Doe",
    "age": 21,
    "courses": ["Math", "Physics"]
}
```

#### The `dict()` Constructor

You can pass keyword arguments or a list of tuples to the constructor.

```python
# Using keyword arguments (keys must be valid identifiers)
student_kw = dict(name="Jane Doe", age=22, courses=["Biology"])

# Using a list of tuples (useful for keys that aren't valid identifiers)
student_tuples = dict([
    ("name", "John Doe"),
    ("age", 21),
    (101, "Room Number") 
])
```

#### Dictionary Comprehensions

Similar to list comprehensions, this syntax generates a dictionary based on an expression.

```python
numbers = [1, 2, 3, 4]

# Create a dictionary mapping numbers to their squares
squares = {x: x**2 for x in numbers}
# Result: {1: 1, 2: 4, 3: 9, 4: 16}
```

#### Using `zip()`

Useful when keys and values are in separate lists.

```python
keys = ["a", "b", "c"]
values = [1, 2, 3]

# Zip combines them into pairs, dict converts them
dict_from_zip = dict(zip(keys, values)) 
# Result: {"a": 1, "b": 2, "c": 3}
```
<br>

## 10. What is the difference between _==_ and _is operator_ in _Python_?

Both the **`==`** and **`is`** operators in Python are used for comparison, but they distinguish between **value** and **identity**.

- The **`==`** operator checks for **value equality**. It compares the data content of two objects to see if they are equivalent.
- The **`is`** operator checks for **object identity**. It validates whether two variables point to the exact same instance in memory (checking if their memory addresses are identical).

Internally, **`is`** is faster as it compares integer memory addresses (ids), whereas **`==`** generally invokes the object's `__eq__()` method, which can be arbitrarily complex.

### Code Illustration

```python
# Two lists with the same content
list_a = [1, 2, 3]
list_b = [1, 2, 3] 
list_c = list_a     # Alias referring to the same object as list_a

# Equality Check (==)
print(list_a == list_b)  # True: The contents are the same.

# Identity Check (is)
print(list_a is list_b)  # False: They are two distinct objects in memory.
print(list_a is list_c)  # True: They reference the exact same memory address.
```

### Usage Guidelines

- **`==`**: Use this for standard comparisons (e.g., numbers, strings, lists, custom objects).
- **`is`**: Use this specifically for checking against singletons like **`None`**, **`True`**, or **`False`**.
<br>

## 11. How does a _Python function_ work?

**Python functions** are the fundamental units of code organization, facilitating reusability, modularity, and encapsulation. In modern Python, they are first-class objects that contain compiled bytecode.

### Key Components

- **Function Signature**: Defined by `def`, including the name, parameters, and optional **type hints** (standard in 2026).
- **Function Body**: The indented block containing logic, loops, and conditional checks.
- **Return Statement**: Terminates execution and outputs a value. Returns `None` implicitly if omitted.
- **Local Namespace**: A discrete scope for variables defined within the function.

```python
def process_data(value: int) -> int:  # Signature with Type Hints
    result = value * 2                # Local variable
    return result                     # Return statement
```

### Execution Process

When a function is called, the Python interpreter performs the following:

1.  **Frame Allocation**: A **stack frame** (activation record) is created on the call stack. This object manages the function's local variables, arguments, and the **instruction pointer**.
2.  **Parameter Binding**: Arguments passed by the caller are bound to the parameter names in the local namespace.
3.  **Function Execution**: Control transfers to the function body. The interpreter executes the underlying **bytecode** sequentially.
4.  **Return**: Upon encountering `return`, the expression is evaluated, and the value is passed back to the caller. The stack frame is popped and discarded.
5.  **Post Execution**: If the end of the body is reached without a return statement, `None` is returned automatically.

### Local Variable Scope

Python resolves names using the **LEGB** rule (Local, Enclosing, Global, Built-in).

- **Function Parameters**: Initialized with values passed during invocation, acting as local variables.
- **Local Variables**: Created via assignment inside the function; they exist only during execution.
- **Nested Scopes**: Inner functions (closures) can read variables from enclosing functions. Modification requires the `nonlocal` keyword.

```python
def outer():
    count = 0
    def inner():
        nonlocal count  # Accesses enclosing scope
        count += 1
    inner()
```

### Global Visibility

If a variable is not found in the local scope, Python looks in the **global scope**. Functions can read global variables, but modifying a global reference requires the `global` keyword. Without it, an assignment creates a new local variable, leaving the global one untouched.

### Avoiding Side Effects

Functions provide encapsulation, ensuring internal variables do not leak into the global scope. Minimizing reliance on global state reduces **side effects**, resulting in "pure functions" that are easier to test, debug, and parallelize.
<br>

## 12. What is a _lambda function_, and where would you use it?

A **Lambda function** is a small, anonymous function defined using the `lambda` keyword in Python. Unlike functions defined with `def`, lambdas are expressions used to create function objects on the fly.

### Distinctive Features

- **Anonymity**: Lambdas are not bound to a specific name in the local namespace.
- **Single Expression Body**: The body is restricted to a single expression. Statements (like `return`, `pass`, `assert`) are not allowed.
- **Implicit Return**: The result of the expression is automatically returned; no explicit `return` keyword is needed.
- **Conciseness**: Designed for short, simple operations where a full function definition would be verbose.

### Common Use Cases

- **Key Functions**: The most prevalent use in modern Python is defining the `key` argument for sorting or finding extremes.
- **Functional Constructs**: Used as arguments for higher-order functions like `map()`, `filter()`, and `functools.reduce()`.
- **Callbacks**: effective for delayed execution, such as UI event handlers (e.g., a button click in Tkinter) that require a callable.

#### Code Example

```python
students = [{'name': 'Alice', 'grade': 88}, {'name': 'Bob', 'grade': 95}]

# 1. Using lambda as a key for sorting by grade
sorted_students = sorted(students, key=lambda x: x['grade'], reverse=True)

# 2. Using lambda with filter to get even numbers
evens = list(filter(lambda x: x % 2 == 0, range(10)))
```

### Notable Limitations

- **Readability**: Named functions are preferred for complex logic. Overusing lambdas, especially nested ones, creates "write-only" code.
- **Debugging**: Tracebacks refer to the function simply as `<lambda>`, making it harder to identify the source of an error compared to a named function.
- **PEP 8 Style**: Assigning a lambda to a variable (e.g., `func = lambda x: x`) is discouraged. Use `def func(x): return x` instead to ensure the function has a useful `__name__` for debugging.
<br>

## 13. Explain _*args_ and _**kwargs_ in _Python_.

In Python, `*args` and `**kwargs` enable functions to accept a variable number of arguments.

`*args` collects excess positional arguments into a **tuple**, while `**kwargs` gathers excess keyword arguments into a **dictionary**. Note that in a function signature, `*args` must strictly precede `**kwargs`.

### **\*args**: Variable Positional Arguments

- **Mechanism**: The single asterisk (`*`) operator packs any remaining positional arguments into a tuple. The name `args` is a convention; the syntax depends only on the asterisk.
- **Use-Case**: When the specific number of positional inputs is unknown or flexible.

#### Code Example: `*args` with Type Hints

```python
def sum_all(*args: int) -> int:
    # args is treated as a tuple of integers
    return sum(args)

print(sum_all(1, 2, 3, 4))  # Output: 10
```

### **\*\*kwargs**: Variable Keyword Arguments

- **Mechanism**: The double asterisk (`**`) operator captures named arguments that do not match specific parameters and stores them as key-value pairs in a dictionary.
- **Use-Case**: When a function requires flexibility to accept arbitrary configuration options or data.

#### Code Example: `**kwargs` with Type Hints

```python
from typing import Any

def print_values(**kwargs: Any) -> None:
    # kwargs is a dictionary
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_values(name="John", age=30, city="New York")
# Output:
# name: John
# age: 30
# city: New York
```
<br>

## 14. What are _decorators_ in _Python_?

In Python, a **decorator** is a design pattern that allows for the dynamic modification of functions, methods, or classes. It enables the extension of behavior without explicitly modifying the source code of the wrapped object, adhering to the **Open/Closed Principle**.

### Core Mechanism

- **Higher-Order Functions**: Decorators are functions that accept another function as an argument and return a new function (the wrapper).
- **Closures**: The returned wrapper function usually retains access to the scope of the outer decorator function, allowing it to manipulate the environment or state.
- **Metaprogramming**: This technique treats functions as data, allowing code to inspect and modify other code at runtime.

### Common Use Cases

- **Cross-Cutting Concerns**: Logging, execution time profiling, and error handling.
- **Access Control**: Authorization and authentication (e.g., checking user roles before execution).
- **Caching**: Storing results of expensive function calls (Memoization).
- **Input Validation**: Enforcing type checks or value constraints on arguments.
- **Built-in Decorators**: Python includes standard decorators like `@staticmethod`, `@classmethod`, `@property`, and `@dataclass`.

### Implementation Examples

#### 1. Basic Function Decorator
This example demonstrates a decorator that adds logging before and after the target function runs.

```python
from functools import wraps

def simple_logger(func):
    @wraps(func)  # Preserves metadata (name, docstring)
    def wrapper(*args, **kwargs):
        print(f"LOG: Starting '{func.__name__}'")
        result = func(*args, **kwargs)
        print(f"LOG: Finished '{func.__name__}'")
        return result
    return wrapper

@simple_logger
def greet(name):
    """Greets the user."""
    print(f"Hello, {name}!")

greet("Alice")
# Output:
# LOG: Starting 'greet'
# Hello, Alice!
# LOG: Finished 'greet'
```

#### 2. Decorators Accepting Arguments
To pass arguments to the decorator itself, three levels of nested functions are required.

```python
def repeat(times):
    def decorator_repeat(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            for _ in range(times):
                result = func(*args, **kwargs)
            return result
        return wrapper
    return decorator_repeat

@repeat(times=3)
def say_hi():
    print("Hi!")

say_hi()
# Output:
# Hi!
# Hi!
# Hi!
```

### Syntactic Sugar

The `@decorator_name` syntax is syntactic sugar for passing the function into the decorator and reassigning the result to the original function name.

```python
# The @ syntax:
@simple_logger
def do_work():
    pass

# Is equivalent to:
def do_work():
    pass
do_work = simple_logger(do_work)
```

### Best Practices: `functools.wraps`

When writing custom decorators, always decorate the wrapper function with `@wraps(func)` from the `functools` module. Without this, the decorated function loses its original `__name__`, `__doc__`, and other metadata, which confuses debugging tools and introspection APIs.
<br>

## 15. How can you create a _module_ in _Python_?

### Creating a Module in Python

A **module** in Python is simply a file containing Python definitions (functions, classes, variables) and statements. The file name becomes the module name, and it must have the `.py` extension.

To **create** a module:
1.  **Create a File**: Save a text file with a `.py` extension (e.g., `math_operations.py`).
2.  **Define Content**: Write your Python code inside this file.
3.  **Import**: Use the `import` command in another script to access the code.

*(Note: To organize multiple modules into a directory structure, you create a **package**, which typically involves adding an `__init__.py` file to the directory.)*

### Code Example: Creating a `math_operations` Module

#### Module Definition

Save the code below in a file named `math_operations.py`:

```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        raise ValueError("Cannot divide by zero")
    return x / y
```

#### Module Usage

You can use the `math_operations` module in another script (in the same directory) using `import`:

```python
import math_operations

result = math_operations.add(4, 5)
print(result)  # Output: 9

result = math_operations.divide(10, 5)
print(result)  # Output: 2.0
```

You can also import specific members directly into the namespace, or use the wildcard `*` (though `*` is generally discouraged to avoid name collisions):

```python
from math_operations import add, subtract

# No need to use the module prefix
print(add(3, 2))
```

### Best Practices

Ensure your modules are robust and reusable by following these practices:

*   **Guard Against Side Effects**: Code at the top level of a module executes immediately upon import. To prevent test code or scripts from running when the module is imported, wrap execution logic in the `if __name__ == "__main__":` block.

```python
if __name__ == "__main__":
    # This runs only when executed as 'python math_operations.py'
    # It does NOT run when imported
    print("Running manual tests...")
    print(add(10, 5))
```

*   **Avoid Global Variables**: Encapsulate state within classes or functions rather than relying on global module variables.
*   **Naming**: Module names should be short, all-lowercase, and may use underscores for readability (e.g., `my_module.py`).
<br>



#### Explore all 100 answers here 👉 [Devinterview.io - Python](https://devinterview.io/questions/web-and-mobile-development/python-interview-questions)

<br>

<a href="https://devinterview.io/questions/web-and-mobile-development/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fweb-and-mobile-development-github-img.jpg?alt=media&token=1b5eeecc-c9fb-49f5-9e03-50cf2e309555" alt="web-and-mobile-development" width="100%">
</a>
</p>

