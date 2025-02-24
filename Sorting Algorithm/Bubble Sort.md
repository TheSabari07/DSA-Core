# Bubble Sort

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

