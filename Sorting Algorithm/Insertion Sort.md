```java
public static void insertionSort(int arr[]){
        for(int i=1 ; i<arr.length ; i++){
            int curr = arr[i] ; 
            int prev = i-1 ;
            while(prev >= 0 && arr[prev] > curr){
                arr[prev+1] = arr[prev] ; //Shift towards the right
                prev-- ;
            }
            arr[prev+1] = curr ;
        }
    }
```

## Algorithm 
- Step 1 : It operates by dividing an array into two portions.
- Step 2 : Create two variable **curr** and **prev** which contains `arr[i]`(value) and `i-1`(previous index of the value's index) respectively.
- Step 3 : Run a `for` loop from i = `1` to `arr.length` .
- Step 4 : The important step the condition of while loop is `prev >= 0 && arr[prev] > curr` means `prev >= 0` prevents runtime error .
***Meaning : keep shifting elements right until the correct spot for curr is found.***
  Step 5 : the max element push to right and we update `arr[prev+1]` as `curr`

## Time Complexity : O(n^2)
## Space Complexity : O(1)
