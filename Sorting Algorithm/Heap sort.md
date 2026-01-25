## <ins>Introduction</ins> : Heap sort is a comparison-based sorting algorithm that uses a binary heap data structure to organize elements. It is essentially an optimized version of selection sort that reduces the time to find the maximum (or minimum) element from leveraging a heap.

```java
public static void heapify(int arr[], int i, int size) {
    int left = 2 * i + 1;
    int right = 2 * i + 2;
    int maxIdx = i;

    if (left < size && arr[left] > arr[maxIdx]) {
        maxIdx = left;
    }

    if (right < size && arr[right] > arr[maxIdx]) {
        maxIdx = right;
    }

    if (maxIdx != i) {
        int temp = arr[i];
        arr[i] = arr[maxIdx];
        arr[maxIdx] = temp;

        // recursive call ONLY after swap
        heapify(arr, maxIdx, size);
    }
}

public static void heapSort(int arr[]) {
    int n = arr.length;

    // Step 1: Build Max Heap
    for (int i = (n / 2) - 1; i >= 0; i--) {
        heapify(arr, i, n);
    }

    // Step 2: Extract elements from heap
    for (int i = n - 1; i > 0; i--) {
        int temp = arr[0];
        arr[0] = arr[i];
        arr[i] = temp;

        heapify(arr, 0, i);
    }
}
```

## Algorithm 
It is a two step algorithms.
### Step 1 : Build maxheap first means **Transform the unsorted array into a Max-Heap. In this structure, every parent node is greater than or equal to its children, ensuring the largest element is at the root (index 0)**.
- i = `i = (n / 2) - 1` to greater than or equalto `0` a non-leaf node(means it has left and right children or previous level of last level) build max heap through called `heapify` function .
  
### Step 2 : 
- Swap: Exchange the root `arr[0]` with the last element `arr[i]` in the current heap.
- Shrink: Decrease the size of the considered heap by one, effectively "locking" the largest element `arr[i]` at the end of the array.
- Heapify: The new root may violate the heap property. Call the heapify function `heapify(arr, 0, i)` on the root to restore the Max-Heap structure for the remaining unsorted elements.

## Time and Space complexity : Time complexity -  O(n log n) , Space complexity - O(1) .

