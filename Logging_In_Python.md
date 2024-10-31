# Logging in Python

### Example

~~~
import logging
from datetime import datetime

name = "Tshegofatso"
print(f"{str(datetime.now())} -- {name}")

~~~

### Output

~~~

~~~

To set a logger, the importation of logger is enough. An initialization of a logger is as follows:

- A `CRITICAL` error stops the program from running.
- It's not adviceable to use a print() funtion with logs.

enums: 

It's not recommended to use the root logger.