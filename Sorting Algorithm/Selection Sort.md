```java
  public static void selectionSort(int arr[]){
        int n = arr.length ;
        for(int i=0 ; i<n-1 ; i++){
            int minIdx = i ;
            for(int j=i+1 ; j<n ; j++){
                if(arr[minIdx] > arr[j]){
                    minIdx = j ;
                }
            }
            int temp = arr[minIdx];
            arr[minIdx] = arr[i];
            arr[i] = temp;
        }
    }
```

## Algorithm 
- Step 1 : Outer loop run for i = `0` to `n-1` and create a var name minIdx which store currernt `i` th position

- Step 2 : Inner loop run for j = `i+1` to `n` and always check the condition ..
- Step 3 : Everytime we check if `arr[minIdx] > arr[j]` , we update minIdx as `j` . Cause we always want minimum element in increasing sorted array .
- Step 4 : Swap the values of `minIdx` and `i` as `minIdx` already hold the minimum value .
- Step 5 : In everypass the process will continue until whole array is sorted.

## Time Complexity : O(n^2)
## Space Complexity : 1
