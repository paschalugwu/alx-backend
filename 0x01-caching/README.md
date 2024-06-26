# Caching Algorithms Project

Welcome to the **Caching Algorithms Project**! This project involves implementing various caching mechanisms in Python. Below, you'll find a structured overview of the project's objectives, resources, and the different caching algorithms you will implement.

## Table of Contents

- [Background](#background)
- [Learning Objectives](#learning-objectives)
- [Requirements](#requirements)
- [Caching Classes](#caching-classes)
  - [BasicCache](#basiccache)
  - [FIFOCache](#fifocache)
  - [LIFOCache](#lifocache)
  - [LRUCache](#lrucache)
  - [MRUCache](#mrucache)
  - [LFUCache](#lfucache)
- [Project Structure](#project-structure)
- [License](#license)

## Background

In this project, you'll explore and implement different caching algorithms. Caching is a key concept in optimizing data retrieval, and understanding various caching strategies is essential for efficient system design.

### Resources

- [Cache Replacement Policies - FIFO](https://en.wikipedia.org/wiki/Cache_replacement_policies#First-in,_first-out_(FIFO))
- [Cache Replacement Policies - LIFO](https://en.wikipedia.org/wiki/Cache_replacement_policies#Last-in,_first-out_(LIFO))
- [Cache Replacement Policies - LRU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least_recently_used_(LRU))
- [Cache Replacement Policies - MRU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Most_recently_used_(MRU))
- [Cache Replacement Policies - LFU](https://en.wikipedia.org/wiki/Cache_replacement_policies#Least_frequently_used_(LFU))

## Learning Objectives

By the end of this project, you should be able to explain:

- What a caching system is and its purpose
- The meaning and implementation of:
  - FIFO (First-In-First-Out)
  - LIFO (Last-In-First-Out)
  - LRU (Least Recently Used)
  - MRU (Most Recently Used)
  - LFU (Least Frequently Used)
- The limitations of caching systems

## Requirements

### Python Scripts

- Must be compatible with Ubuntu 18.04 LTS using Python 3.7.
- Files must end with a new line.
- First line of all files should be `#!/usr/bin/env python3`.
- Code style must adhere to `pycodestyle` (version 2.5).
- All files must be executable.
- Proper documentation is required for modules, classes, and functions.

### BaseCaching Class

All classes inherit from the `BaseCaching` class provided:

```python
class BaseCaching():
    MAX_ITEMS = 4

    def __init__(self):
        self.cache_data = {}

    def print_cache(self):
        ...

    def put(self, key, item):
        ...

    def get(self, key):
        ...
```

## Caching Classes

### BasicCache

A simple caching system without any limits.

- **put(key, item)**: Stores the item under the key in the cache.
- **get(key)**: Retrieves the item stored under the key.

### FIFOCache

Implements FIFO (First-In-First-Out) caching policy.

- **put(key, item)**: Adds the item to the cache. Discards the oldest item if the cache exceeds `MAX_ITEMS`.
- **get(key)**: Retrieves the item stored under the key.

### LIFOCache

Implements LIFO (Last-In-First-Out) caching policy.

- **put(key, item)**: Adds the item to the cache. Discards the newest item if the cache exceeds `MAX_ITEMS`.
- **get(key)**: Retrieves the item stored under the key.

### LRUCache

Implements LRU (Least Recently Used) caching policy.

- **put(key, item)**: Adds the item to the cache. Discards the least recently used item if the cache exceeds `MAX_ITEMS`.
- **get(key)**: Retrieves the item stored under the key and marks it as recently used.

### MRUCache

Implements MRU (Most Recently Used) caching policy.

- **put(key, item)**: Adds the item to the cache. Discards the most recently used item if the cache exceeds `MAX_ITEMS`.
- **get(key)**: Retrieves the item stored under the key and marks it as most recently used.

### LFUCache

Implements LFU (Least Frequently Used) caching policy.

- **put(key, item)**: Adds the item to the cache. Discards the least frequently used item if the cache exceeds `MAX_ITEMS`. Uses LRU as a tie-breaker.
- **get(key)**: Retrieves the item stored under the key and increments its usage frequency.

## Project Structure

```plaintext
.
├── base_caching.py          # BaseCaching class
├── 0-basic_cache.py         # BasicCache class
├── 1-fifo_cache.py          # FIFOCache class
├── 2-lifo_cache.py          # LIFOCache class
├── 3-lru_cache.py           # LRUCache class
├── 4-mru_cache.py           # MRUCache class
└── 100-lfu_cache.py         # LFUCache class
```

---

Happy coding and enjoy learning about caching mechanisms! If you have any questions, feel free to reach out.
