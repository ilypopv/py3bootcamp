# **1️⃣ Python is Dynamically Typed** {color="blue_bg"}
<columns>
	<column ratio="50">
		In Python, variable types are checked **at runtime**, and a single variable can be reassigned to completely different data types throughout execution.
		- **Dynamic Typing (Python, JS):** High flexibility and fast prototyping, but type errors only surface when the code actually runs.
		```python
# Python: Fully valid dynamic reassignment
x = 42         # x is an int
x = "Hello"    # x is now a str
x = [1, 2, 3]  # x is now a list
		```
	</column>
	<column ratio="50">
		In statically typed languages (like C++, Java, or Rust), variable types are locked at declaration and checked **at compile time**. Reassigning a different type causes a build error.
		- **Static Typing (Java, C++):** Extra boilerplate upfront, but the compiler catches type mismatches before execution.
		```java
int x = 42;
x = "Hello"; // ❌ Compile-time Error: incompatible types: String cannot be converted to int
		```
	</column>
</columns>
Since Python is dynamically typed, you can inspect the current type of any variable at runtime using the built-in `type()`function.
```python
x = 42
print(type(x))  # <class 'int'>

x = "Hello"
print(type(x))  # <class 'str'>

x = [1, 2, 3]
print(type(x))  # <class 'list'>
```
> **Pro-tip:** To check if a variable matches a specific type inside code logic, `isinstance(x, int)` is preferred over `type(x) == int` because it also accounts for class inheritance.
---
# 2️⃣ Data Types Table {color="blue_bg"}
<table header-row="true">
<colgroup>
<col color="green_bg" width="114.7734375">
<col width="108.7734375">
<col width="139.7734375">
<col width="156.7734375">
<col width="136.77777777777777">
<col width="136.77777777777777">
<col width="136.77777777777777">
<col width="136.77777777777777">
<col width="136.77777777777777">
</colgroup>
<tr color="green_bg">
<td>**Name**</td>
<td>**Integers**</td>
<td>**Floating point**</td>
<td>**Strings**</td>
<td>**Lists**</td>
<td>**Dictionaries**</td>
<td>**Tuples**</td>
<td>**Sets**</td>
<td>**Booleans**</td>
</tr>
<tr>
<td>**Type**</td>
<td>`int`</td>
<td>`float`</td>
<td>`str`</td>
<td>`list`</td>
<td>`dict`</td>
<td>`tuple`</td>
<td>`set`</td>
<td>`bool`</td>
</tr>
<tr>
<td>**Description**</td>
<td>Whole numbers</td>
<td>Floating Point numbers which are numbers with a decimal</td>
<td><span color="blue">**Ordered**</span> sequence of characters, <span color="yellow">using the syntax of either single quotes or double quotes</span></td>
<td><span color="blue">**Ordered**</span> sequences that can hold a variety of object types. <span color="yellow">They use </span><span color="red">`[]`</span> <span color="yellow">brackets and commas to separate objects in the list</span></td>
<td><span color="pink">**Unordered**</span> mappings for storing objects. Dictionaries use a `Key:Value` pairing.<br><br><span color="yellow">Dictionaries use curly braces and colons to signify the keys and their associated values.</span></td>
<td><span color="blue">Ordered</span> immutable sequence of objects<br><br><span color="yellow">Tuples use parenthesis.</span></td>
<td><span color="pink">Unordered</span> collection of unique elements</td>
<td>Logical value indicating</td>
</tr>
<tr>
<td>**Essentials**</td>
<td></td>
<td></td>
<td>  • String methods like `.replace()` or `.upper()` never modify the original string – they always allocate and return a completely new string object.</td>
<td>  • Can be nested.</td>
<td>  •  `Key:Value` pair allows to quickly grab objects without needing to know an index location.<br>  • Keys must be immutable/hashable types.</td>
<td>  • Tuples are very similar to lists. However they have one key difference  **immutability**.<br>  • Once an element is inside a tuple, it can not be reassigned.</td>
<td>  • There can only be one representative of the same object.</td>
<td>  •  `bool` is a literal subclass of `int`. `True` evaluates to `1` and `False` to `0` in arithmetic operations (e.g., `sum([True, False, True])` equals `2`)</td>
</tr>
<tr>
<td>**Example**</td>
<td>`1`; `2`; `3`</td>
<td>`3.14`; `4.6`; `100.0`</td>
<td>`"hello"`; `'Sammy'`; `"2000"`; `"楽しい”`</td>
<td>`[10, "hello", 200.3]`</td>
<td>`{"mykey" : "value",<br>"name" : "Frankie"}`</td>
<td>`(10, "hello", 200.3)`</td>
<td>`{"a", "b"}`</td>
<td>`True` or `False`</td>
</tr>
<tr>
<td>**Mutability**</td>
<td>❌</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
</tr>
<tr>
<td>**Hashable**</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
<td>✅<br>*(if elements are hashable)*</td>
<td>❌</td>
<td>✅</td>
</tr>
<tr>
<td>**Iterable**</td>
<td>—</td>
<td>—</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>✅</td>
<td>—</td>
</tr>
<tr>
<td>**Ordered**</td>
<td>—</td>
<td>—</td>
<td>✅</td>
<td>✅</td>
<td>❌</td>
<td>✅</td>
<td>❌</td>
<td>—</td>
</tr>
<tr>
<td>**Indexing / slices**</td>
<td>❌</td>
<td>❌</td>
<td>✅</td>
<td>✅</td>
<td>❌<br>*(objects retrieved by key name)*</td>
<td>✅</td>
<td>❌</td>
<td>❌</td>
</tr>
</table>
<callout icon="ℹ️" color="purple_bg">
	Ordered sequences allow you to use indexing and slicing to extract specific parts of the sequence.
</callout>
---
# 3️⃣ Data Type Examples in Practice {color="blue_bg"}
Quick reference snippets showing indexing, slicing, and the most common operations for each data type from the table above.
<columns>
	<column ratio="29.17">
		#### Strings `“string”`
		```python
s = "Hello"

s[0]       # 'H'
s[-1]      # 'o'
s[1:4]     # 'ell'
s[::-1]    # 'olleH'
		```
	</column>
	<column ratio="37.5">
		#### Lists `[a, b, c, a, b, c]`
		```python
lst = ['Hi', 'my', 'name', 'is', 'Anton']

lst[0]      # 'Hi' (indexing)
lst[0:2]    # ['Hi', 'my'] (slicing)
lst[-1]     # 'Anton' (negative indexing)
		```
	</column>
	<column ratio="33.33">
		#### Tuples `(a, b, c, a, b, c)`
		```python
tup = ("Hi", "my", "name", "is", "Anton")

tup[0]     # 'Hi'
tup[1:3]   # ('my', 'name')

# tup[0] = "Hello"  ❌ TypeError!
		```
	</column>
</columns>
<columns>
	<column ratio="33.33">
		#### Dictionaries `{”key”: value}`
		```python
user = {"name": "Anton", "age": 25}

user["name"]       # 'Anton'
user.get("age")    # 25

# user[0]          ❌ KeyError!
		```
	</column>
	<column ratio="33.33">
		#### Sets `{a, b, c}`
		```python
a = {1, 2, 3}
b = {3, 4, 5}

# a[0]             ❌ TypeError!

a.intersection(b)  # {3}
a.union(b)         # {1, 2, 3, 4, 5}
		```
	</column>
	<column ratio="33.33">
		#### Booleans `True` / `False`
		```python
is_active = True

is_active + 1      # 2
False * 10         # 0
		```
	</column>
</columns>
---
# 4️⃣ Python Core Mechanics {color="blue_bg"}
<columns>
	<column ratio="50">
		#### **Indentation Defines Code Blocks**
		Python uses whitespace (indentation – typically 4 spaces) instead of curly braces `{}` or keywords to define blocks of code.
		<span color="green">Indentation</span> tells the interpreter which statements belong to a specific function, loop, or conditional block.
		```python
# ❌ IndentationError: expected an indented block
if True:
print("Hello")

# ✅ Correct indentation
if True:
    print("Hello")  # 4 spaces define the block
		```
	</column>
	<column ratio="50">
		#### **Methods vs. Built-in Functions**
		<span color="purple">**Methods**</span> are functions attached directly to specific data types or objects.
		They are invoked using dot notation (`object.method()`) to inspect or transform the underlying object.
		```python
text = "hello"
print(text.upper())  # 'HELLO' (string method)

lst = [1, 2]
lst.append(3)        # lst becomes [1, 2, 3] (list method)
		```
		> **Key Difference:** Global built-in functions like `len(text)` stand alone, while methods like `text.upper()` are explicitly bound to the object and called via a dot.
	</column>
</columns>
---
# 5️⃣ Iteration & Range Conversions {color="blue_bg"}
<columns>
	<column ratio="50">
		#### **Iterating Over Dictionaries**
		By default, iterating over a dictionary loops through its **keys**. To access values or both key-value pairs simultaneously, use explicit dictionary methods:
		```python
user = {"name": "Anton", "age": 25}

# Iterating over keys (default behavior)
for key in user:
    print(key)  # 'name', 'age'

# Iterating over values
for value in user.values():
    print(value)  # 'Anton', 25

# Iterating over key-value pairs
for key, value in user.items():
    print(f"{key}: {value}")  # 'name: Anton', 'age: 25'
		```
	</column>
	<column ratio="50">
		#### **Converting ****`range()`**** to a ****`list`**
		The `range()` function generates an immutable, memory-efficient sequence on demand—it does not build a full list in memory. To create an actual list of integers, pass the `range` object directly into `list()`:
		```python
# range() yields numbers lazily on the fly
r = range(1, 6)
print(r)  # range(1, 6)

# Consume the range object into a list
numbers = list(range(1, 6))
print(numbers)  # [1, 2, 3, 4, 5]
		```
	</column>
</columns>
> **Key takeaway:** Both dictionary view objects (`.keys()`, `.values()`, `.items()`) and `range()` objects are iterable sequences that can be explicitly converted into lists using `list(...)`.
---
# **6️⃣ Difference Between ****`print()`**** and ****`return`**** in functions** {color="blue_bg"}
<columns>
	<column ratio="50">
		**`print()`** displays data to the console for the user to see. It returns `None` and does not pass values back to the rest of the program.
		```python
# ❌ Using print(): Output is shown, but result cannot be saved
def add_print(a, b):
    print(a + b)

result1 = add_print(5, 3)  # Prints: 8
print(result1)             # Prints: None (No value was saved!)
		```
	</column>
	<column ratio="50">
		**`return`** sends the function's calculated result back to the caller, allowing you to store the output in a variable or pass it into another function.
		```python
# ✅ Using return: Output is handed back to the caller
def add_return(a, b):
    return a + b

result2 = add_return(5, 3) # Saves 8 inside result2
print(result2 * 2)         # Prints: 16 (Can be reused in calculations)
		```
	</column>
</columns>
> **Key Takeaway:** Use `print()` for debugging or logging to the terminal. Use `return` when your code needs to work with the function's output later.
---
# 7️⃣ Modulo Operator (`%`) {color="blue_bg"}
The `%` symbol is known as the **Modulo Operator** (often called **Mod** for short). In English, an expression like `7 % 4` is read as *"seven modulo four"* or *"seven mod four"*. It calculates the **remainder** left over after integer division.
### Visualizing `7 % 4 = 3`
Think of modulo as dividing items into full groups and counting what is left over:
```plain text
Total items: 7  [ █  █  █  █ ] [ █  █  █ ]
Group size:  4  |-- 1 Group -| |-- Remainder --|

7 / 4 = 1 full group of 4, with 3 left over.
Therefore, 7 % 4 = 3
```
#### Common Use Cases
<columns>
	<column ratio="50">
		**Checking Odd or Even Numbers (****`n % 2`****)** Dividing any integer by `2` leaves a remainder of `0` for even numbers and `1` for odd numbers.
		```python
n = 7

if n % 2 == 0:
    print("Even")
else:
    print("Odd")  # Output: Odd (since 7 % 2 is 1)
		```
	</column>
	<column ratio="50">
		**Cycling through a Fixed Range (Wrapping Around)** Modulo keeps a counter within the range of `0` to `N-1`. This is useful for circular lists, games, or clock arithmetic.
		```python
# Keep index within 0 to 2 for a list of size 3
index = 5 % 3  # Output: 2 (Wraps around back into valid range)
		```
		<empty-block/>
	</column>
</columns>
---
# 8️⃣ Control Flow {color="blue_bg"}
## `if / elif / else` and `for / while` Loops {color="green_bg"}
Control flow determines the order in which statements are executed based on conditions and repeating logic.
<columns>
	<column ratio="33.33">
		### Conditionals (`if / elif / else`)
		Conditionals execute different blocks of code based on whether boolean expressions evaluate to `True` or `False`.
		```python
age = 20

if age < 18:
    print("Minor")
elif age < 65:
    print("Adult")  # Output: Adult
else:
    print("Senior")
		```
		- **`if`**: The initial check. Runs if `True`.
		- **`elif`** (*short for else-if*): Checked sequentially if preceding conditions are `False`.
		- **`else`**: The fallback block. Runs if **none** of the above conditions were met.
	</column>
	<column ratio="33.33">
		### Definite Iteration (`for` loop)
		Used when you want to iterate over a **known sequence** (like a `list`, `str`, `tuple`, or `range`).
		```python
# Iterating through a sequence
names = ["Alice", "Bob", "Anton"]

for name in names:
    print(f"Hello, {name}!")

# Output:
# Hello, Alice!
# Hello, Bob!
# Hello, Anton!
		```
		<empty-block/>
	</column>
	<column ratio="33.33">
		### Indefinite Iteration (`while` loop)
		Repeats a block of code as long as a condition remains `True`. Useful when you **do not know in advance** how many times the loop needs to run.
		```python
attempts = 0

# Loop until attempts reach 3
while attempts < 3:
    print(f"Attempt #{attempts + 1}")
    attempts += 1  # Crucial! Update condition to avoid an infinite loop

# Output:
# Attempt #1
# Attempt #2
# Attempt #3
		```
		> **Warning:** If the condition never becomes `False` (and no `break` is executed), you end up with an **infinite loop**.
	</column>
</columns>
## `break`, `continue`, and `pass` {color="green_bg"}
<columns>
	<column ratio="33.33">
		### `break` — "Stop and Exit right now"
		Terminates the loop completely and moves execution to the first line *after* the loop.
		- **Analogy:** Emergency stop button.
		```python
# Real-world use case: Searching for a user
users = ["Alice", "Bob", "Anton", "Charlie"]

for user in users:
    if user == "Anton":
        print("User found! Stopping search.")
        break  # Exits the loop immediately, ignoring remaining users
    print(f"Checking: {user}")

# Output:
# Checking: Alice
# Checking: Bob
# User found! Stopping search.
		```
	</column>
	<column ratio="33.33">
		### `continue` — "Skip the rest of this loop iteration"
		Skips the current cycle's remaining code and jumps straight to the next item in the loop.
		- **Analogy:** Pressing "Skip" on a single music track.
		```python
# Real-world use case: Processing non-spam items
emails = ["ok_mail", "SPAM_mail", "ok_mail2"]

for mail in emails:
    if "SPAM" in mail:
        continue  # Skip processing for spam, jump straight to next mail

    print(f"Sending notification for: {mail}")

# Output:
# Sending notification for: ok_mail
# Sending notification for: ok_mail2
		```
	</column>
	<column ratio="33.33">
		### `pass` — "Do nothing (Placeholder)"
		Does absolutely nothing. Used when Python's syntax demands code inside a block, but you aren't ready to write the logic yet.
		- **Analogy:** A "To-Do Later" sticky note.
		```python
# Real-world use case: Drafting code structure
for item in range(5):
    if item == 3:
        pass  # TODO: Handle special logic for 3 later without causing a syntax error
    print(item)

# Output: Prints 0, 1, 2, 3, 4 without crashing or stopping
		```
	</column>
</columns>
### Combined Control Flow Summary
<table header-row="true">
<colgroup>
<col width="149.5">
<col width="336.5">
</colgroup>
<tr>
<td>**Control Statement**</td>
<td>**What It Does**</td>
</tr>
<tr>
<td>`if / elif / else`</td>
<td>Chooses a code path based on conditions</td>
</tr>
<tr>
<td>`for`</td>
<td>Iterates over items in an iterable collection</td>
</tr>
<tr>
<td>`while`</td>
<td>Loops continually as long as a condition is `True`</td>
</tr>
<tr>
<td>`break`</td>
<td>Exits a `for` or `while` loop completely</td>
</tr>
<tr>
<td>`continue`</td>
<td>Skips the current loop iteration and moves to the next</td>
</tr>
<tr>
<td>`pass`</td>
<td>Placeholder that does nothing (keeps syntax valid)</td>
</tr>
</table>
---
# 9️⃣ List Comprehensions & Generator Expressions {color="blue_bg"}
A list comprehension condenses a `for` loop into a single line that builds a list.
```python
# Traditional for loop
squares = []
for x in range(5):
    squares.append(x**2)

# List comprehension — same result
squares = [x**2 for x in range(5)]
# [0, 1, 4, 9, 16]
```
<columns>
	<column ratio="50">
		#### Adding a condition
		Append `if` at the end to filter items:
		```python
evens = [x for x in range(11) if x % 2 == 0]
# [0, 2, 4, 6, 8, 10]
		```
	</column>
	<column ratio="50">
		#### Nesting
		Comprehensions can be nested for multi-step transforms:
		```python
squares = [x**2 for x in range(5)]
quads = [x**2 for x in squares]
# [0, 1, 16, 81, 256]
		```
	</column>
</columns>
#### Generator expressions — same syntax, lazy result
Swap `[]` for `()` and you get a **generator expression**: values are produced one at a time instead of building the whole list in memory.
```python
gen = (x**2 for x in range(5))
gen        # <generator object <genexpr> at ...>
next(gen)  # 0
list(gen)  # [1, 4, 9, 16] — remaining items, consumed
```
> **Key takeaway:** `[]` builds the full list upfront; `()` builds a generator that yields items lazily and can only be consumed once. Full generator functions (`yield`) are covered later in the course.
---
# 🔟 `*args` and `**kwargs` {color="blue_bg"}
Both let a function accept an **arbitrary number of arguments** without pre-defining each parameter.
<columns>
	<column ratio="50">
		#### `*args` — arbitrary positional args
		Collects extra positional arguments into a **tuple**.
		```python
def total(*args):
    return sum(args)

total(1, 2, 3)  # 6
		```
	</column>
	<column ratio="50">
		#### `**kwargs` — arbitrary keyword args
		Collects extra keyword arguments into a **dict**.
		```python
def greet(**kwargs):
    print(kwargs.get("name", "stranger"))

greet(name="Anton")  # Anton
		```
	</column>
</columns>
Combine both in one function — `*args` must always come **before** `**kwargs`:
```python
def combo(*args, **kwargs):
    print(args, kwargs)

combo(1, 2, fruit="apple")  # (1, 2) {'fruit': 'apple'}
```
> **Key takeaway:** The names `args`/`kwargs` are just convention — what matters is the `*`/`**` prefix and the ordering: positional → `*args` → keyword → `**kwargs`.
---
# 1️⃣1️⃣ Scope & the LEGB Rule {color="blue_bg"}
**Scope** determines where a variable name is visible. Python resolves a name by checking scopes in this order — remembered as **LEGB**:
<table header-row="true">
<tr>
<td>**L**ocal</td>
<td>**E**nclosing</td>
<td>**G**lobal</td>
<td>**B**uilt-in</td>
</tr>
<tr>
<td>Assigned inside the current function</td>
<td>In any enclosing function's scope (nested functions)</td>
<td>Assigned at module top level</td>
<td>Preassigned by Python itself (`len`, `range`, ...)</td>
</tr>
</table>
```python
x = "global"

def outer():
    x = "enclosing"
    def inner():
        x = "local"
        print(x)      # local
    inner()
    print(x)          # enclosing

outer()
print(x)               # global
```
#### The `global` keyword
Assigning to a name inside a function makes it **local** by default, even if a global with the same name exists. Use `global` to modify the actual global variable:
```python
count = 0

def increment():
    global count
    count += 1

increment()
print(count)  # 1
```
> **Key takeaway:** Reading an outer-scope variable works without any keyword; **writing** to it from inside a function requires `global` (or `nonlocal` for enclosing scopes).
---
# 1️⃣2️⃣ Lambda Expressions {color="blue_bg"}
A **lambda** is an anonymous, single-expression function — a shorthand for a simple `def` you only need once.
<columns>
	<column ratio="50">
		```python
def square(n):
    return n**2
		```
	</column>
	<column ratio="50">
		```python
square = lambda n: n**2
		```
	</column>
</columns>
```python
square(4)   # 16
```
- The body is a single **expression**, implicitly returned — no statements, no multiple lines.
- Can take multiple arguments: `lambda x, y: x + y`
- Mostly used **inline**, as a throwaway function passed into another function (e.g. `map`, `filter`, `sorted(key=...)`).
> **Key takeaway:** If the logic needs more than one expression, use `def` — lambda trades generality for brevity.
---
# 1️⃣3️⃣ `map()` and `filter()` {color="blue_bg"}
Both apply a function to every item of an iterable — they just differ in what they keep.
<columns>
	<column ratio="50">
		#### `map()` — transform every item
		Applies a function to each item, returning the results.
		```python
nums = [1, 2, 3, 4]
list(map(lambda n: n**2, nums))
# [1, 4, 9, 16]
		```
	</column>
	<column ratio="50">
		#### `filter()` — keep matching items
		Keeps only items where the function returns `True`.
		```python
nums = [1, 2, 3, 4]
list(filter(lambda n: n % 2 == 0, nums))
# [2, 4]
		```
	</column>
</columns>
> **Key takeaway:** Both `map()` and `filter()` return lazy iterator objects — wrap them in `list(...)` to see the results. They're commonly paired with `lambda`, since the function passed in is usually only needed once.
