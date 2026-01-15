```java
public static void bubbleSort(int arr[]){
    int n = arr.length;
    for(int i = 0; i < n - 1; turn++){
        for(int j = 0; j < n - 1 - i; j++){
            if(arr[j] > arr[j + 1]){
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
```
## Step 1: Compare Adjacent Elements

- Run the outer loop from `i = 0` to `n - 1`
- Then run the inner loop from `j = 0` to `n - 1 - i`

> **Learning Tip:**  
> It is difficult to remember the range of `j` at first.  
> Use this intuition:
> 
> `i + j = n - 1`  
> or  
> `j = n - 1 - i`

## Step 2: Swap if Needed
- If the previous element `arr[j]` is greater than `arr[j+1]` then Swap those.

## Step 3: Repeat for Remaining Elements
- then , this process continue until `arr[n-1]`
- After every pass, the largest element settles at the end of the array.

## Time Complexity : O(n^2)
## Space Complexity : O(1)

 
