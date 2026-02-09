## <ins>Introduction</ins> : The Two-Pointers Technique is a simple yet powerful strategy where you use two indices (pointers) that traverse a data structure—such as an array, list, or string—either toward each other or in the same direction to solve problems more efficiently.

Let's take an example , 
### arr[ ] = {1 , 1 , 2 , 2 , 2 , 3 , 3}

```java
public int removeDuplicates(int[] nums) {
        // HashSet to store unique elements we have seen
        HashSet<Integer> set = new HashSet<>();

        // Position to overwrite next unique element
        int idx = 0;

        // Loop over each number in nums
        for (int num : nums) {
            // If num is not in the set, it is unique
            if (!set.contains(num)) {
                // Add num to the set
                set.add(num);

                // Write num at current index position
                nums[idx] = num;

                // Move index forward
                idx++;
            }
        }
        // Return number of unique elements
        return index;
    }
```

## Dry Run 



