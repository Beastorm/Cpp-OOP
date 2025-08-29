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

**Benefits:**
- Code reuse  
- Efficiency  
- Generic programming  
- Reduced development time  

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

**Examples:**
```cpp
#include <vector>
#include <list>
#include <deque>

std::vector<int> v = {1,2,3};
v.push_back(4);

std::list<int> l = {5,6,7};
l.push_front(4);

std::deque<int> d;
d.push_back(1);
d.push_front(0);
```
## 2.2 Associative Containers

- Store elements in a **sorted order**, allow fast retrieval.
- Containers:
  - `set` / `multiset` → unique / non-unique elements
  - `map` / `multimap` → key-value pairs  
- **Key operations**: `insert`, `find`, `erase`, `count`

**Example:**

```cpp
#include <set>
#include <map>

std::set<int> s = {3,1,4};
s.insert(2); // {1,2,3,4}

std::map<std::string,int> m;
m["apple"] = 5;
m["orange"] = 3;
```
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

### Example:

```cpp
#include <stack>
#include <queue>

std::stack<int> st;
st.push(1);
st.top(); // 1
st.pop();

std::priority_queue<int> pq;
pq.push(10);
pq.push(5);
pq.top(); // 10
```
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

### Example
```cpp
#include <vector>
#include <iostream>

std::vector<int> v = {1,2,3};
for(auto it = v.begin(); it != v.end(); ++it)
    std::cout << *it << " ";
```
## 4. Algorithms

Predefined generic operations on containers.

### Categories
- **Non-modifying algorithms**: `for_each`, `count`, `find`, `binary_search`  
- **Modifying algorithms**: `copy`, `replace`, `fill`, `swap`  
- **Sorting / Partitioning**: `sort`, `partial_sort`, `stable_sort`, `nth_element`  
- **Set operations**: `set_union`, `set_intersection`  
- **Numeric algorithms**: `accumulate`, `adjacent_difference`, `iota`  

### Example
```cpp
#include <algorithm>
#include <vector>
#include <numeric>
#include <iostream>

std::vector<int> v = {1,3,2};
std::sort(v.begin(), v.end());  // 1,2,3
int sum = std::accumulate(v.begin(), v.end(), 0); // 6
```
## 5. Functors / Function Objects

Objects that can be called like a function.  
Used in algorithms to define custom behavior.  

### Example
```cpp
#include <algorithm>
#include <vector>
#include <functional>

std::vector<int> v = {1,2,3};
std::sort(v.begin(), v.end(), std::greater<int>());
```
## 6. Lambda Functions (C++11)

Anonymous inline functions for algorithms.  

### Example
```cpp
#include <vector>
#include <algorithm>
#include <iostream>

std::vector<int> v = {1,2,3};
std::for_each(v.begin(), v.end(), [](int x){ std::cout << x*x << " "; });
```
## 7. Allocators

Control how memory is allocated for containers.  
Rarely used directly; STL uses `std::allocator<T>` by default.  

### Example
```cpp
#include <vector>
#include <memory>

std::vector<int, std::allocator<int>> v;
```
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



