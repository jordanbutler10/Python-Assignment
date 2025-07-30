# 🛡️ Python Algorithm: IP Allow List Management

## 📘 Project Overview

This project simulates a real-world cybersecurity task: managing access controls for a sensitive subnetwork at a healthcare company. Employees access the network through specific IP addresses, which are stored in an allow list. To maintain security, IPs on a separate remove list must be removed from the allow list. This Python script automates the removal process.

## 📂 Files Included

- `allow_list.txt`: A file containing currently authorized IP addresses (one per line).
- `remove_list.txt`: A file containing IP addresses that need to be revoked.
- `update_allow_list.py`: The Python script that performs the file read, comparison, and update.

---

## ⚙️ How It Works

### Step 1: Open and Read the Allow List

```python
with open("allow_list.txt", "r") as file:
    allow_list_data = file.read()
````

* Uses the `with` statement for automatic file handling.
* `.read()` reads file contents as a single string.

### Step 2: Convert the String to a List

```python
allow_list = allow_list_data.splitlines()
```

* `.splitlines()` separates the string into a list by line breaks.

### Step 3: Read and Parse the Remove List

```python
with open("remove_list.txt", "r") as file:
    remove_list = file.read().splitlines()
```

* Reads and parses the remove list into a list of IPs.

### Step 4: Remove IPs Found in the Remove List

```python
for ip in remove_list:
    if ip in allow_list:
        allow_list.remove(ip)
```

* Uses a `for` loop to iterate through the removal list.
* Uses `.remove()` to delete the matching IP from the allow list.

### Step 5: Write the Updated Allow List to File

```python
with open("allow_list.txt", "w") as file:
    for ip in allow_list:
        file.write(ip + "\n")
```

* Opens the file in write mode (`"w"`).
* Writes each remaining IP back to the file with newline characters.

---

## 💡 Key Python Concepts Used

| Concept         | Description                                 |
| --------------- | ------------------------------------------- |
| `with open()`   | Safely opens and closes files automatically |
| `.read()`       | Reads entire file as a string               |
| `.write()`      | Writes strings to a file                    |
| `.splitlines()` | Splits string into a list by lines          |
| `for` loop      | Iterates through list items                 |
| `.remove()`     | Deletes specific items from a list          |

---

## 🧪 Example Input/Output

### `allow_list.txt` (before):

```
192.168.1.1
10.0.0.5
172.16.0.2
```

### `remove_list.txt`:

```
10.0.0.5
```

### `allow_list.txt` (after script runs):

```
192.168.1.1
172.16.0.2
```

---

## 📝 Summary

This project demonstrates basic file handling, list manipulation, and control logic in Python—skills essential for cybersecurity professionals working with automation and access control. The algorithm provides a scalable and efficient way to enforce dynamic access policies within secure environments.

---

## 🔐 Created By

Jordan Butler
Cybersecurity Professional | SOC Analyst Trainee
[GitHub Portfolio](https://github.com/yourusername)
