# Hash Map with Chaining

This project implements a hash map with chaining in Python. The hash map uses a linked list for each bucket to handle collisions, which makes this implementation robust in situations where multiple keys hash to the same index.

## Features

- Hash map implementation with separate chaining.
- Two different hash functions to choose from.
- Operations supported: insert (add), remove, get value by key, and resize the hash table.

## Classes and Functions

### SLNode

Represents a node in the singly linked list used for chaining in the hash map.

### LinkedList

A simple linked list class to manage collisions in the hash map.

### HashMap

The main hash map class containing the following key methods:

- `__init__(self, capacity, function)`: Initializes the hash map with a specified capacity and hash function.
- `clear(self)`: Clears all elements in the hash map.
- `get(self, key)`: Fetches the value associated with the given key.
- `resize_table(self, capacity)`: Resizes the hash map to the given capacity and rehashes all keys.

### Hash Functions

- `hash_function_1(key)`: A simple hash function that sums the ASCII values of each character in the key.
- `hash_function_2(key)`: A hash function that sums the ASCII values of the key's characters, each multiplied by its 1-based index.

## Usage

1. **Initialize the Hash Map:**

    ```python
    from main import HashMap, hash_function_1

    capacity = 10
    hashmap = HashMap(capacity, hash_function_1)
    ```

2. **Insert key-value pairs:**

    ```python
    hashmap._buckets[0].add_front("key1", "value1")
    hashmap._buckets[1].add_front("key2", "value2")
    ```

3. **Get value by key:**

    ```python
    value = hashmap.get("key1")
    print(value)  # Outputs: value1
    ```

4. **Remove key-value pair:**

    ```python
    hashmap._buckets[0].remove("key1")
    ```

5. **Resize the Hash Map:**

    ```python
    hashmap.resize_table(20)
    ```

## Example

Here is a quick example to demonstrate the usage of the hash map:

```python
from main import HashMap, hash_function_1

# Initialize hash map
capacity = 10
hashmap = HashMap(capacity, hash_function_1)

# Insert some key-value pairs
hashmap._buckets[0].add_front("key1", "value1")
hashmap._buckets[1].add_front("key2", "value2")

# Retrieve value by key
print(hashmap.get("key1"))  # Output: value1

# Resize the hash map
hashmap.resize_table(20)