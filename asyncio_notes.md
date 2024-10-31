# Asyncio in Python  

## What is asyncio?

**Asyncio** is a python library that helps write concurrent code using the `await` or `async` syntax.

- It is particularly useful for I/O-bound tasks, i.e. file operations, network requests, or any code that involves waiting for external resources.

### 1. Coroutines

- **Coroutines** are functions defined with `async def`. They can __pause__ at `await` expressions, allowing other coroutines to run during those pauses.

```python
import asyncio

async def my_coroutine():
    print("Start")
    await asyncio.sleep(1)  
    print("End")

# Running the coroutine
asyncio.run(my_coroutine())

```

The line of code `await asyncio.sleep(1)` simulates an I/O-bound operation, and it pauses the coroutine for 1 second, allowing other tasks to run concurrently.

### 2. Event Loop
- __Event Loop__ manages and schedules the execution of coroutines. It is where tasks are __registered__ and __managed__.
- `asyncio.run()` is used to start an event loop, run a coroutine, and stop the loop automatically after the coroutine completes.

### 3. Tasks
- A **task** is a wrapper for a coroutine that allows it to run concurrently.
- `ayncio.create_task()` creates a task.
- It is a subclass of `Future`.


#### Example

```python
import asyncio # Importing the library

async def task_one():
    print("Task one start")
    await asyncio.sleep(2)
    print("Task one done")

async def task_two():
    print("Task two start")
    await asyncio.sleep(1)
    print("Task two done")

async def main():
    task1 = asyncio.create_task(task_one())
    task2 = asyncio.create_task(task_two())
    
    # Wait for both tasks to complete
    await task1
    await task2

# Running the main coroutine
asyncio.run(main())
```

#### Output

~~~
Task one start
Task two start
Task two done
Task one done
~~~



### 4. Gathering tasks

- `ansycio.gather` runs multiple coroutines concurrently. It's useful when awaiting a group of coroutines to complete.

#### Example

```python
async def task_one():
    await asyncio.sleep(1)
    return "Task one result"

async def task_two():
    await asyncio.sleep(2)
    return "Task two result"

async def main():
    results = await asyncio.gather(task_one(), task_two())
    print(results)

asyncio.run(main())
```

#### Output 
~~~
Task one start
Task two start
Task two done
Task one done
~~~
 ### 5. Handling exceptions
 
```python
async def faulty_task():
    raise ValueError("Something went wrong")

async def main():
    try:
        await faulty_task()
    except ValueError as e:
        print(f"Caught an exception: {e}")

asyncio.run(main())
```

#### Output
~~~
Caught an exception: Something went wrong
~~~

### 6. Timeouts

- `asyncio.wait_for()` can set time limits on coroutines. If a **task** exceeds the given time, an exception is raised.

#### Example

```python
import asyncio

async def my_task():
    await asyncio.sleep(3)
    return "Done"

async def main():
    try:
        result = await asyncio.wait_for(my_task(), timeout=2)
    except asyncio.TimeoutError:
        print("Task took too long!")
    else:
        print(result)

asyncio.run(main())
```

#### Output
~~~
Task took too long!
~~~

### 7. Running in parallel with `asyncio.to_thread`

- `asyncio.to_thread()` runs blocking code in a separate thread without blocking the event loop.

### 8. Futures

- A `Future` is an object that ill hold the results( or exception) of an operation that hasn't completed yet, allowing checking or waiting for that result later.
- It comes to play when integrating non-`asyncio` code or doing more advanced operations.
- `asyncio.Future()` manually creates a `Future` object.

```python
import asyncio

async def wait_for_result(future):
    await asyncio.sleep(1)  # Simulate some I/O
    future.set_result("Result is ready!")  # Manually set the result
    print("Result set!")

async def main():
    future = asyncio.Future()  # Create an empty future
    await asyncio.create_task(wait_for_result(future))  # Wait for the future to be completed
    print(await future)  # Await the result of the future

asyncio.run(main())

```

#### Output
~~~
Result set!
Result is ready!
~~~

#### Checking if a `Future` is done
- The code example below not only checks if a `Future` , it also checks whether it was successful of failed.

```python
future = asyncio.Future()
print(future.done())  # False (not yet done)

# Set a result or exception
future.set_result(42)
print(future.done())  # True (the future is now completed)
print(future.result())  # 42 (the result is ready)
```

#### Setting Exceptions on a `Future`

```python
 async def fail_later(future):
    await asyncio.sleep(1)
    future.set_exception(ValueError("An error occurred"))

async def main():
    future = asyncio.Future()
    await asyncio.create_task(fail_later(future))
    try:
        result = await future  # This will raise the exception
    except ValueError as e:
        print(f"Caught exception: {e}")

asyncio.run(main())
```

In the above example, the `future.set_exception` sets an exception, and the future is waited, raising the specified exception.

#### Using `asyncio.ensure_future()`

- `asyncio.ensure_future()`is used to wrap either a couroutine or a `Future` in a `Task`. This ensures the coroutine is executed in the event loop even if the result isn't awaited immediately.

```python
async def slow_operation():
    await asyncio.sleep(2)
    return "Slow operation result"

async def main():
    future = asyncio.ensure_future(slow_operation())  # Run in background
    await asyncio.sleep(1)  # Do other work while waiting
    result = await future  # Wait for the future's result
    print(result)

asyncio.run(main())
```
