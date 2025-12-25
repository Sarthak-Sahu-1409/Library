## 1. How is `std::map` (C++) or `TreeMap` (Java) implemented internally?

**Interview-style answer:**

`std::map` in C++ and `TreeMap` in Java are both implemented using **Red–Black Trees**, which are self-balancing Binary Search Trees.

A Red–Black Tree maintains balance using node coloring rules (red or black), ensuring the tree height remains **O(log n)**. Because of this:

- Search, insert, and delete operations run in **O(log n)** time.
- Keys are stored in **sorted order**.

**Important properties:**
- Each node is either red or black  
- Root is always black  
- No two red nodes can be adjacent  
- Every path from a node to its leaf nodes has the same number of black nodes  

**Example:**
If keys `10, 20, 30` are inserted:
- A normal BST would skew.
- A Red–Black Tree performs rotations and recoloring to keep the tree balanced.

This makes `map` / `TreeMap` suitable for ordered data with predictable performance.

---

## 2. Difference between Red–Black Trees and AVL Trees

**Interview-style answer:**

Both are self-balancing BSTs with `O(log n)` operations, but they differ in how strictly they maintain balance.

### Red–Black Tree
- Loosely balanced  
- Height ≤ `2 * log₂(n)`  
- Fewer rotations during insert/delete  
- Better for **write-heavy** workloads  
- Used in `std::map`, `TreeMap`

### AVL Tree
- Strictly balanced (balance factor −1, 0, +1)  
- Shorter height than Red–Black Trees  
- More rotations during insert/delete  
- Faster lookups due to tighter balance  
- Slower updates compared to Red–Black Trees  

**Summary:**
- **AVL Trees** → read-heavy systems  
- **Red–Black Trees** → mixed or write-heavy systems  

This is why standard libraries prefer Red–Black Trees.

---

## 3. What is the technical difference between HTTP and HTTPS?

**Interview-style answer:**

The primary difference is **security**.

### HTTP
- Plain-text communication  
- Vulnerable to eavesdropping and modification  
- No server authentication  
- Default port: **80**

### HTTPS
- HTTP over **TLS/SSL encryption**  
- Provides confidentiality, integrity, and authentication  
- Server identity is verified using certificates  
- Default port: **443**

---



