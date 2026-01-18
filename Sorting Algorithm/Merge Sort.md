## <ins>Introduction</ins>: Merge sort is an efficiently sorting algorithoms which is based on ***Divide and Conquer*** strategy . It works by recursively dividing the list into two half util each half conatains a single element .Then Conquer both parts again in the sorted manner.

## Code :
```java
public static void mergeSort(int arr[], int si, int ei) {
        if (si >= ei) {
            return;
        }

        int mid = si + (ei - si) / 2;

        mergeSort(arr, si, mid);      // left part
        mergeSort(arr, mid + 1, ei);  // right part

        merge(arr, si, mid, ei);      // merge both
    }

    public static void merge(int arr[], int si, int mid, int ei) {
        int temp[] = new int[ei - si + 1];

        int i = si;       // left iterator
        int j = mid + 1;  // right iterator
        int k = 0;        // temp iterator

        while (i <= mid && j <= ei) {
            if (arr[i] < arr[j]) {
                temp[k++] = arr[i++];
            } else {
                temp[k++] = arr[j++];
            }
        }

        while (i <= mid) {
            temp[k++] = arr[i++];
        }

        while (j <= ei) {
            temp[k++] = arr[j++];
        }

        // copy temp to original array
        for (k = 0, i = si; k < temp.length; k++, i++) {
            arr[i] = temp[k];
        }
    }
```
## Algorithm 
- Step 1 : We create a `mergeSort` recursive function to half the array by `mid` where `mid` is `si+(ei-si)/2` . we use this formula instead of `si+ei/2` for large size of array.(si = 0 and ei = arr.length)
- Step 2 : Left part `mergeSort(arr, si, mid)` and right part `mergeSort(arr, mid+1, ei)` . To merge again both we have to create `merge` function .
> We create a temporary array `temp` having length of `ei-si+1` .
> initialized three pointers `i`=si ,`j`=mid+1 and `k`=0 for left part , right part and temp array respectively.
> Then compare two pointers index's element and store to `temp` in the sorted manner .
- Step 3 : Copy the all elements from `temp` array to original array `arr`.

## Time Complexity : O(logn)
