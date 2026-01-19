## <ins>Introduction</ins> : Quick Sort is an efficinet sorting algorithm basedon the deivide and conquer strategy . It works by selecting a "pivot" and partioning the list into elements less than or equal to the pivot and egreate than a pivot. It's a recursively process.

```java
    public static void quickSort(int arr[], int si, int ei) {
    if (si >= ei) return;

    int pivotIdx = partition(arr, si, ei);
    quickSort(arr, si, pivotIdx - 1);   // left part
    quickSort(arr, pivotIdx + 1, ei);   // right part
}

public static int partition(int arr[], int si, int ei) {
    int pivot = arr[ei];
    int i = si - 1;

    for (int j = si; j < ei; j++) {
        if (arr[j] <= pivot) {
            i++;
            int temp = arr[j];
            arr[j] = arr[i];
            arr[i] = temp;
        }
  }
    // place pivot at correct position
    i++;
    int temp = arr[i];
    arr[i] = arr[ei];
    arr[ei] = temp;

    return i;
    }
```
## Step 1: Choose Pivot

- Select the last element of the array as pivot.

- Step 2: Partition the Array

- Rearrange the array so that:

> All elements ≤ pivot come before it

> All elements > pivot come after it

- After partitioning, pivot is in its correct sorted position.

## Step 3: Recursively Apply Quick Sort

- Apply Quick Sort on:

> Left subarray (elements before pivot)

> Right subarray (elements after pivot)

## Step 4: Stop Condition

- If the subarray has 0 or 1 element, stop (already sorted).

## Key Observations (Exam-Important)
- Pivot always placed at correct position
  
- Average Time: O(n log n)
- Worst Case: O(n²) (already sorted + bad pivot)
- Space: O(log n) (recursion stack)
