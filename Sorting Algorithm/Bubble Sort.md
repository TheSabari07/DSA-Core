# Bubble Sort


Check Problem : https://www.geeksforgeeks.org/problems/bubble-sort/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=bubble-sort
## 1. What is Sorting?
Sorting is the process of **arranging elements** in a particular order (ascending or descending).  
It helps in searching, organizing, and analyzing data efficiently.

### Types of Sorting Algorithms
| Sorting Type            | Example Algorithms                    |
|-------------------------|--------------------------------------|
| **Comparison-Based**    | Bubble Sort, Selection Sort, Quick Sort |
| **Non-Comparison-Based** | Counting Sort, Radix Sort |

---

## 2. What is Bubble Sort?
**Bubble Sort** is a simple **comparison-based sorting algorithm** where adjacent elements are repeatedly compared and swapped if they are in the wrong order.  
This process continues until the array is fully sorted.

### Characteristics of Bubble Sort
| Property          | Description                       |
|------------------|---------------------------------|
| **Algorithm Type** | Comparison-based sorting      |
| **Best Case**     | O(n) (Already sorted)         |
| **Worst Case**    | O(n²) (Reverse sorted)        |
| **Average Case**  | O(n²)                          |
| **Space Complexity** | O(1) (In-place sorting)   |

---

## 3. Simple Code Implementation (C++)
```cpp
class Solution {
  public:
    void bubbleSort(vector<int>& arr) {
        int n = arr.size();
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    swap(arr[j], arr[j + 1]); // Swap if out of order
                }
            }
        }
    }
};

```
---

### Step-by-Step Execution:

| Pass | Array State   | Swaps Performed           |
|------|-------------|---------------------------|
| 1    | 1 4 3 7 9  | (4↔1), (4↔3), (9↔7)      |
| 2    | 1 3 4 7 9  | (4↔3)                     |
| 3    | 1 3 4 7 9  | No swaps (sorted)         |

> Since no swaps occurred in the third pass, the sorting is complete.

---

## 5. Advantages and Disadvantages

### Advantages:
- Simple to implement
- Works well for small datasets
- Can detect if an array is already sorted (with an optimization)

###  Disadvantages:
- Inefficient for large datasets
- Performs poorly compared to Quick Sort and Merge Sort

---

## 6. Optimized Bubble Sort (Stops Early if Sorted)

```cpp
void optimizedBubbleSort(vector<int>& arr) {
    int n = arr.size();
    bool swapped;

    for (int i = 0; i < n - 1; i++) {
        swapped = false;
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped) break; // Stop if no swaps occurred
    }
}
```
---
