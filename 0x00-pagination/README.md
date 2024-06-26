# Pagination Project

## Overview

This project focuses on implementing pagination in a back-end system, utilizing a dataset of popular baby names. It involves developing functions and classes to paginate data, both in simple and hypermedia formats, ensuring the system is resilient to data deletions.

## Learning Objectives

By the end of this project, you will be able to:

- Paginate a dataset using page and page size parameters.
- Implement pagination with hypermedia metadata.
- Handle pagination in a manner that is resilient to deletions.

## Requirements

- All code will be interpreted/compiled on Ubuntu 18.04 LTS using Python 3.7.
- Files should follow the pycodestyle (version 2.5.*) style guide.
- Each module and function must include comprehensive documentation.
- Functions and coroutines must have type annotations.

## Setup

Use the `Popular_Baby_Names.csv` file as the dataset for all tasks.

## Tasks

### 0. Simple Helper Function

**File:** `0-simple_helper_function.py`

**Objective:** 
Create a function `index_range` that returns a tuple containing the start and end index for paginating a list.

- Takes two arguments: `page` and `page_size`.
- Returns a tuple `(start_index, end_index)`.

**Example Usage:**
```python
index_range(1, 7)  # (0, 7)
index_range(3, 15) # (30, 45)
```

### 1. Simple Pagination

**File:** `1-simple_pagination.py`

**Objective:**
Implement a `Server` class that paginates a dataset using a method `get_page`.

- Method `get_page` takes `page` (default 1) and `page_size` (default 10).
- Use `assert` to ensure arguments are positive integers.
- Use `index_range` to determine the slice of the dataset to return.
- Return an empty list if indices are out of range.

**Example Usage:**
```python
server = Server()
print(server.get_page(1, 3))  # First 3 records
print(server.get_page(3, 2))  # Records 5 and 6
```

### 2. Hypermedia Pagination

**File:** `2-hypermedia_pagination.py`

**Objective:**
Extend the `Server` class with a `get_hyper` method that provides additional metadata for hypermedia pagination.

- `get_hyper` returns a dictionary with `page_size`, `page`, `data`, `next_page`, `prev_page`, and `total_pages`.
- Reuse `get_page` in implementation.

**Example Usage:**
```python
server = Server()
print(server.get_hyper(1, 2))
```

### 3. Deletion-Resilient Hypermedia Pagination

**File:** `3-hypermedia_del_pagination.py`

**Objective:**
Implement a `get_hyper_index` method that maintains pagination integrity even when rows are deleted from the dataset.

- `get_hyper_index` takes `index` and `page_size`, returning a dictionary with `index`, `next_index`, `page_size`, and `data`.
- Use an indexed dataset for pagination.
- Handle cases where rows have been removed between queries.

**Example Usage:**
```python
server = Server()
server.indexed_dataset()
print(server.get_hyper_index(3, 2))
```

## Repository

- **GitHub repository:** `alx-backend`
- **Directory:** `0x00-pagination`

## Additional Notes

- Ensure that all modules and methods have appropriate documentation.
- Write clean and maintainable code following Python conventions and style guides.

For more details on REST API pagination, refer to the provided resources on [Pagination](https://restfulapi.net/pagination/) and [HATEOAS](https://restfulapi.net/hateoas/).
