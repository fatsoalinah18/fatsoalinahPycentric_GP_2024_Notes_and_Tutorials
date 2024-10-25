# Python 3.13 New Features Overview

## New Features

### 1. Improved Interactive Interpreter
- **Description**: A new and improved interactive interpreter based on PyPy's, featuring:
  - Multi-line editing
  - Color support
  - Colorized exception tracebacks
- **Alternative**: Use existing interactive environments like Jupyter Notebook for enhanced interactivity.


### 2. Experimental Free-Threaded Build Mode
- **Description**: Disables the Global Interpreter Lock (GIL), allowing threads to run more concurrently.
- **Use Case**: Useful for CPU-bound multi-threaded applications.
- **Alternative**: Use the `multiprocessing` module for parallel execution if GIL is a limitation.
~~~
import sys

if hasattr(sys, 'is_free_threaded'):
    print("Free-threaded mode is enabled.")
else:
    print("Free-threaded mode is not available.")

~~~

### 3. Preliminary Experimental JIT
- **Description**: Provides groundwork for significant performance improvements.
- **Use Case**: Optimize performance for computationally intensive applications.
- **Alternative**: Consider using Cython for compiling Python to C for performance gains.

### 4. Enhanced `locals()` Function
- **Description**: The `locals()` builtin function has well-defined semantics when mutating the returned mapping.
- **Use Case**: Improves consistency for debuggers.
- **Alternative**: Use dictionary methods directly for variable inspection in debugging.
~~~
def debug_function():
    a = 10
    b = 20
    print(locals())  # Returns a dictionary of local variables

debug_function()

~~~

### 5. Modified Version of `mimalloc`
- **Description**: Included by default if supported, required for free-threaded build mode.
- **Use Case**: Optimizes memory allocation performance.
- **Alternative**: Use custom memory allocators if specific performance characteristics are needed.

### 6. Stripped Docstring Indentation
- **Description**: Leading indentation is stripped from docstrings, reducing memory use and .pyc file size.
- **Use Case**: More efficient memory usage.
- **Alternative**: No direct alternative; follows Python’s emphasis on clean code.

### 7. New `dbm` Module Backend
- **Description**: The `dbm` module now uses `dbm.sqlite3` as the default backend for new files.
- **Use Case**: Simplifies the database management process.
- **Alternative**: Use other database solutions like SQLite directly for more advanced features.

~~~
import dbm

# Create a new dbm file with sqlite3 backend
with dbm.open('mydb', 'c') as db:
    db['key'] = 'value'
    print(db['key'])  # Output: value
~~~

### 8. macOS Support Update
- **Description**: Minimum supported macOS version changed from 10.9 to 10.13.
- **Impact**: Older versions will no longer be supported.

### 9. Tier 2 and Tier 3 Platform Support
- **Description**:
  - **WASI** is now Tier 2 supported.
  - **iOS** and **Android** are now Tier 3 supported.
- **Impact**: Expands the ecosystems where Python can be utilized.

## Typing Improvements

### 10. Type Defaults in Type Parameters
- **Description**: Support for specifying default types in type parameters.
- **Use Case**: Enhances type hinting flexibility.

### 11. New Type Narrowing Annotation
- **Description**: `typing.TypeIs` for narrowing types.
- **Use Case**: Improves type safety in complex applications.

### 12. New Annotations for TypeDicts
- **Description**: Read-only items in `TypeDicts`.
- **Use Case**: Enhances clarity and intent in type definitions.

### 13. New Deprecation Annotations
- **Description**: New annotation for marking deprecations in the type system.
- **Use Case**: Helps maintain codebase and communicate changes effectively.

## Removals and Deprecations

### 14. PEP 594 Removals
- **Description**: Scheduled removals of deprecated modules:
  - Examples: `aifc`, `cgi`, `telnetlib`, etc.
- **Impact**: Encourages the use of modern alternatives.

### 15. Other Deprecations
- **Description**: Removal of deprecated classes, functions, and methods across various standard library modules.
- **Impact**: Encourages codebase updates and modernization.

### 16. C API Removals and Deprecations
- **Description**: Several C API functions are deprecated or removed, with some reversals based on feedback.
- **Impact**: Affects C extensions; developers should update their extensions accordingly.


