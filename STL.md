# C++ STL Topics – Complete Map

---

## 1. Introduction to STL
**What is STL?**  
- Standard Template Library (STL) provides generic, reusable components.

**Components:**
- Containers  
- Iterators  
- Algorithms  
- Functors  
- Allocators  

---

## 2. Containers
Containers store collections of objects.

### 2.1 Sequence Containers
Store elements in order of insertion.

- **`vector`**
  - Dynamic array, contiguous memory.
  - Key functions: `push_back`, `pop_back`, `size`, `capacity`, `reserve`, `emplace_back`.

- **`deque`**
  - Double-ended queue, fast insertion/removal at both ends.

- **`list`**
  - Doubly-linked list, fast insertion/removal anywhere.

- **`forward_list`** (C++11)  
  - Singly-linked list.

- **`array`** (C++11)  
  - Fixed-size array.

- **`string`**
  - Sequence of characters with STL-like methods.

## 2.2 Associative Containers

- Store elements in a **sorted order**, allow fast retrieval.
- Containers:
  - `set` / `multiset` → unique / non-unique elements
  - `map` / `multimap` → key-value pairs  
- **Key operations**: `insert`, `find`, `erase`, `count`

## 2.3 Unordered Containers (C++11)

- Implemented using **hash tables** (not sorted).  
- Examples: `unordered_set`, `unordered_map`  
- Average complexity:  
  - `insert` → **O(1)**  
  - `find` → **O(1)**  
  - `erase` → **O(1)**  

---

## 2.4 Container Adaptors

- Adapt one container for specific behavior.  
- Examples:  
  - `stack` → **LIFO** (usually uses `deque`)  
  - `queue` → **FIFO** (usually uses `deque`)  
  - `priority_queue` → **max-heap** or **min-heap**  

## 3. Iterators

Iterators provide a uniform way to traverse containers.

### Types
- **Input Iterator** – read-only, one-pass  
- **Output Iterator** – write-only, one-pass  
- **Forward Iterator** – read/write, multi-pass  
- **Bidirectional Iterator** – can move forward and backward (`list`, `set`)  
- **Random Access Iterator** – can jump (`vector`, `deque`, `array`)  

### Common Operations
- `++it`, `--it`, `*it`, `it + n`

## 4. Algorithms

Predefined generic operations on containers.

### Categories
- **Non-modifying algorithms**: `for_each`, `count`, `find`, `binary_search`  
- **Modifying algorithms**: `copy`, `replace`, `fill`, `swap`  
- **Sorting / Partitioning**: `sort`, `partial_sort`, `stable_sort`, `nth_element`  
- **Set operations**: `set_union`, `set_intersection`  
- **Numeric algorithms**: `accumulate`, `adjacent_difference`, `iota`  

## 5. Functors / Function Objects

Objects that can be called like a function.  
Used in algorithms to define custom behavior.  

## 6. Lambda Functions (C++11)

Anonymous inline functions for algorithms.  

## 7. Allocators

Control how memory is allocated for containers.  
Rarely used directly; STL uses `std::allocator<T>` by default.  

## 8. Iterators + Algorithms Patterns

STL emphasizes separating **data structure (container)** from **operations (algorithms)** using iterators.  

- Examples: `std::copy`, `std::transform`, `std::accumulate`  
- Supports **generic programming**  

---

## 9. Advanced STL Topics

- **Move semantics** – `emplace_back`, `std::move`  
- **Smart pointers** – `std::unique_ptr`, `std::shared_ptr`  
- **STL Performance Patterns** – prefer `vector` over `list` in most cases (cache-friendly)  
- **Custom comparators** – for `set`, `map`, `priority_queue`  
- **Ranges and Views (C++20)** – `std::ranges::filter`, `transform_view`  



