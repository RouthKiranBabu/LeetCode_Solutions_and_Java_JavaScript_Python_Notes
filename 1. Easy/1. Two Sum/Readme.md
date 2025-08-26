# Map in Python, Java, and JavaScript

This guide explains how to **create a Map**, and how to **set** and **get** values in **Python, Java, and JavaScript**. Each section includes:

* **Definition**
* **Full Syntax with Explanation**
* **Examples**

---

## 📌 1. Python: Dictionary (`dict`)

In Python, a **Map-like structure** is implemented using a **dictionary (`dict`)**.

### Definition

A dictionary in Python is an unordered collection of key-value pairs where keys must be unique and immutable.

### Syntax

```python
# Creating a dictionary
my_dict = {
    key1: value1,
    key2: value2,
}

# Setting a value
my_dict[key] = value

# Getting a value
value = my_dict[key]          # Raises KeyError if key not found
value = my_dict.get(key)      # Returns None (or default) if key not found
```

### Example

```python
# Create a dictionary
student = {
    "name": "Alice",
    "age": 21
}

# Set a new value
student["grade"] = "A"   # Adds key 'grade'

# Get values
print(student["name"])         # Output: Alice
print(student.get("age"))      # Output: 21
print(student.get("city", "Not Found"))  # Output: Not Found
```

---

## 📌 2. Java: `HashMap`

In Java, a **Map** is an interface, and the most commonly used implementation is **`HashMap`**.

### Definition

A `HashMap` stores key-value pairs. Keys are unique, and values can be duplicated. It allows **null values** and one **null key**.

### Syntax

```java
// Import
import java.util.HashMap;

// Create a HashMap
HashMap<KeyType, ValueType> map = new HashMap<>();

// Set a value
map.put(key, value);

// Get a value
ValueType value = map.get(key);      // Returns null if key not found
```

### Example

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // Create a HashMap
        HashMap<String, Integer> scores = new HashMap<>();

        // Set values
        scores.put("Alice", 90);
        scores.put("Bob", 85);

        // Get values
        System.out.println(scores.get("Alice")); // Output: 90
        System.out.println(scores.get("Charlie")); // Output: null
    }
}
```

---

## 📌 3. JavaScript: `Map`

In JavaScript, the **`Map` object** is used to store key-value pairs. Unlike objects, keys can be of any type.

### Definition

A `Map` holds key-value pairs and remembers the original insertion order of the keys.

### Syntax

```javascript
// Create a Map
const myMap = new Map();

// Set a value
myMap.set(key, value);

// Get a value
let value = myMap.get(key);   // Returns undefined if key not found
```

### Example

```javascript
// Create a Map
const student = new Map();

// Set values
student.set("name", "Alice");
student.set("age", 21);

// Get values
console.log(student.get("name"));  // Output: Alice
console.log(student.get("age"));   // Output: 21
console.log(student.get("grade")); // Output: undefined
```

---

## ✅ Summary

| Language       | Map Structure | Set Value              | Get Value                            |
| -------------- | ------------- | ---------------------- | ------------------------------------ |
| **Python**     | `dict`        | `my_dict[key] = value` | `my_dict[key]` or `my_dict.get(key)` |
| **Java**       | `HashMap`     | `map.put(key, value)`  | `map.get(key)`                       |
| **JavaScript** | `Map`         | `map.set(key, value)`  | `map.get(key)`                       |

Each language has its own way of handling **maps/dictionaries**, but the concept remains the same: **store key-value pairs and retrieve them efficiently**.
