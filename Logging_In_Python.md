# Logging in Python

### Example

```python
import logging
from datetime import datetime

name = "Tshegofatso"
print(f"{str(datetime.now())} -- {name}")

```

### Output

~~~
# The output will show the current date and time followed by the name:
# 2024-10-31 10:00:00.000000 -- Tshegofatso
~~~

To set a logger, the importation of logger is enough. An initialization of a logger is as follows:

```python
import logging

# Set up basic configuration for the logger
logging.basicConfig(level=logging.DEBUG)
logger = logging.getLogger(__name__)
```

- A `CRITICAL` error stops the program from running.
- It's not adviceable to use a print() funtion with logs.

enums: 

It's not recommended to use the root logger.