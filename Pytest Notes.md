# Pytest Notes

### Prerequisites
- Python 3.8+
- pytest 8.3.3

# 1. Create a Test

- Create a file `test_sample.py`

## Things to Consider When Creating a Test Script
- Test function names should start with `test_`.
- Use `assert` statements to check expected outcomes.
- Each test should check one aspect of your function.
  

## TESTING 
## Assertions

### Example Test Script

```python
# test_sample.py

from calculator import add, subtract, multiply, divide
import pytest

def test_add():
    assert add(1, 2) == 3
    assert add(-1, 1) == 0
    assert add(0, 0) == 0

def test_subtract():
    assert subtract(5, 3) == 2
    assert subtract(3, 5) == -2
    assert subtract(0, 0) == 0

def test_multiply():
    assert multiply(3, 4) == 12
    assert multiply(-1, 1) == -1
    assert multiply(0, 5) == 0

def test_divide():
    assert divide(10, 2) == 5
    assert divide(-6, 2) == -3
    with pytest.raises(ValueError, match="Cannot divide by zero"):
        divide(10, 0)
