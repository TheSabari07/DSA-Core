---

# **Binary Search Explained**

---

## **What is Binary Search?**

Binary Search is a **fast method** to find a target element in a **sorted** array. Instead of checking each element **one by one**, it **cuts the search space in half** at each step, making it much faster.

---

## **How Does It Work?**

1. **Find the middle element** of the array.
2. **Compare it with the target**:
    - If it matches, return the index.
    - If it's **smaller**, search the **right half**.
    - If it's **larger**, search the **left half**.
3. **Repeat the process** until the element is found or the search space is empty.

---

## **Example: Find `7` in the Array**

### **Sorted Array**

| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Value | 1 | 3 | 5 | 7 | 9 | 11 | 13 | 15 | 17 | 19 |

### **Search Process**

| Step | Left (`low`) | Right (`high`) | Middle (`mid`) | Middle Value | Action |
| --- | --- | --- | --- | --- | --- |
| 1 | 0 | 9 | (0+9)/2 = 4 | 9 | 7 is **smaller**, search left |
| 2 | 0 | 3 | (0+3)/2 = 1 | 3 | 7 is **bigger**, search right |
| 3 | 2 | 3 | (2+3)/2 = 2 | 5 | 7 is **bigger**, search right |
| 4 | 3 | 3 | (3+3)/2 = 3 | 7 | **Found!** |

---

# **LeetCode Problem: Search Insert Position**

## **Problem Statement**

Given a **sorted array** and a **target value**, return the index if the target is found. If not, return the **index where it would be inserted** in order.

---

## **Original Code (Binary Search Implementation)**

```cpp
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int low = 0, high = nums.size() - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (nums[mid] == target) return mid;
            else if (nums[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return low;
    }
};

```

---

## **Making the Code Simpler**

### **Key Changes**

✔ Used `mid = (low + high) / 2` for clarity.

✔ Removed unnecessary parentheses for better readability.

✔ The logic remains the same.

```cpp
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int low = 0, high = nums.size() - 1;
        while (low <= high) {
            int mid = (low + high) / 2;
            if (nums[mid] == target) return mid;
            if (nums[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return low;
    }
};

```

---

## **Example Walkthrough**

### **Input**

```cpp
nums = {1, 3, 5, 6}
target = 5

```

### **Step-by-Step Execution**

| Step | `low` | `high` | `mid` | `nums[mid]` | Action |
| --- | --- | --- | --- | --- | --- |
| 1 | 0 | 3 | 1 | 3 | 5 is **bigger**, search right |
| 2 | 2 | 3 | 2 | 5 | **Found! Return 2** |

### **Output**

```cpp
2

```

---

## **What If the Target Is Not in the Array?**

If the target isn't found, `low` will point to the correct insertion index.

### **Example: Insert `2` in `{1,3,5,6}`**

| Step | `low` | `high` | `mid` | `nums[mid]` | Action |
| --- | --- | --- | --- | --- | --- |
| 1 | 0 | 3 | 1 | 3 | 2 is **smaller**, search left |
| 2 | 0 | 0 | 0 | 1 | 2 is **bigger**, search right |
| 3 | 1 | 0 | - | - | **Stop, insert at `low = 1`** |

### **Output**

```cpp
1

```

---

# **Key Takeaways**

✔ **Binary Search** is much faster than Linear Search (`O(log N)` vs `O(N)`).

✔ It works **only on sorted arrays**.

✔ It **reduces the search space by half** at every step.

✔ **If the element is missing, it returns the correct insert position.**

---
# **Binary Search Classification**

Binary Search falls under **Algorithms** and specifically belongs to the category of **Searching Algorithms** in **Data Structures and Algorithms (DSA)**.  

---

## **Classification of Binary Search**

| **Aspect**               | **Details**                            |
|--------------------------|---------------------------------------|
| **Algorithm Type**       | Searching Algorithm                   |
| **Category**            | Divide and Conquer                    |
| **Time Complexity**      | O(log N)                              |
| **Data Structure Dependency** | Works on sorted arrays or lists |

> **Note:** Binary Search is not a Data Structure itself but operates on Data Structures like **arrays, lists, or binary search trees (BSTs)** to efficiently find elements.

---
