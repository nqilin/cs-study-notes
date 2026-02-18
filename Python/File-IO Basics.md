# File I/O Basics

File I/O (Input/Output) refers to reading data from and writing data to files on disk. Python provides built-in functions to handle file operations safely and efficiently.

---

## 1. Opening a File

Use the `open()` function to open a file. It returns a file object, which is used to read or write the file.

### Syntax
```python
file_object = open(filename, mode, encoding="utf-8")
```

### Common File Modes
| Mode | Description                                  |
|------|----------------------------------------------|
| `'r'` | Read (default). The file must exist.         |
| `'w'` | Write. Creates a new file or overwrites an existing one. |
| `'a'` | Append. Writes data to the end of the file without overwriting. |
| `'r+'`| Read and write. The file must exist.          |
| `'b'` | Binary mode (e.g., `'rb'`, `'wb'`).           |

### Example
```python
# Open a file for reading
f = open("example.txt", "r", encoding="utf-8")
```

---

## 2. Closing a File

Always close a file after use to free up system resources. Use the `close()` method.

```python
f = open("example.txt", "r")
# ... operations ...
f.close()
```

**Recommended:** Use the `with` statement, which automatically closes the file when the block is exited.

```python
with open("example.txt", "r", encoding="utf-8") as f:
    # File operations here
    pass
# File is closed automatically here
```

---

## 3. Reading from a File

### 3.1 Read the entire file
Use `read()` to read the entire content of the file as a single string.

```python
with open("example.txt", "r", encoding="utf-8") as f:
    content = f.read()
    print(content)
```

### 3.2 Read line by line
Use `readline()` to read one line at a time, or `readlines()` to read all lines into a list.

```python
# readline()
with open("example.txt", "r", encoding="utf-8") as f:
    line1 = f.readline()
    line2 = f.readline()

# readlines()
with open("example.txt", "r", encoding="utf-8") as f:
    lines = f.readlines()  # List of strings, each representing a line
    for line in lines:
        print(line.strip())  # strip() removes newline characters
```

### 3.3 Iterate over lines
Iterate directly over the file object to read lines one by one (memory efficient).

```python
with open("example.txt", "r", encoding="utf-8") as f:
    for line in f:
        print(line.strip())
```

---

## 4. Writing to a File

### 4.1 Write a string
Use `write()` to write a string to a file.

```python
with open("output.txt", "w", encoding="utf-8") as f:
    f.write("Hello, World!\n")
    f.write("This is a new line.\n")
```

### 4.2 Write multiple lines
Use `writelines()` to write a list of strings to a file. Note that it does not automatically add newlines.

```python
lines = ["First line\n", "Second line\n", "Third line\n"]
with open("output.txt", "w", encoding="utf-8") as f:
    f.writelines(lines)
```

### 4.3 Append to a file
Use mode `'a'` to append data to the end of an existing file.

```python
with open("output.txt", "a", encoding="utf-8") as f:
    f.write("This line is appended.\n")
```

---

## 5. Working with Binary Files

Use mode `'b'` to read or write binary files (e.g., images, executables).

```python
# Copy a binary file
with open("input.jpg", "rb") as src, open("output.jpg", "wb") as dst:
    dst.write(src.read())
```

---

## 6. Common Exceptions in File I/O

- `FileNotFoundError`: Raised when the file does not exist (in read mode).
- `PermissionError`: Raised when you do not have permission to access the file.
- `IsADirectoryError`: Raised when you try to open a directory as a file.

### Example with error handling
```python
try:
    with open("missing.txt", "r", encoding="utf-8") as f:
        content = f.read()
except FileNotFoundError:
    print("Error: The file does not exist.")
except PermissionError:
    print("Error: You do not have permission to read this file.")
