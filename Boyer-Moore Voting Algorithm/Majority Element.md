The name of **Majority Element** is itself stated that in an array is the element that appears more than `n/2 times`, where n is the size of the array.

To solve this problem our first try should be Brute approach :

Let's take an example : int nums[] = {4 , 5 , 4 , 4 , 2 ,3} ;
## Brute Approach 
```java
    public static int majorityElement(int nums[]){
        for(int i=0 ; i<nums.length ; i++){
            int count = 0 ;
            for(int j=0 ; j<nums.length ; j++){
                if (nums[j] == nums[i]) count++;
            }
           if (count > nums.length / 2) return nums[i];
       }
      return -1; // no majority element
     } 
```

## let's give a look on Algorithm   
### i = 0 , j = 0 
```java
4 , 5 , 4 , 4 , 2 ,3
i
j
```
`nums[j] == nums[i]` Condition satisfy , so that `count` increase by 1 .
### i = 0 , j = 1
```java
4 , 5 , 4 , 4 , 2 , 3
i
    j
```
`nums[j] == nums[i]` Condition doesn't satisfy , so that `count` remains same .
### i = 0 , j = 2
```java
4 , 5 , 4 , 4 , 2 , 3
i
        j
```
`nums[j] == nums[i]` Condition satisfy , so that `count` increase by 1 .
### i = 0 , j = 3
```java
4 , 5 , 4 , 4 , 2 , 3
i
            j
```
`nums[j] == nums[i]` Condition satisfy , so that `count` increase by 1 .
### i = 0 , j = 4
```java
4 , 5 , 4 , 4 , 2 , 3
i
                j
```
`nums[j] == nums[i]` Condition doesn't satisfy , so that `count` remains same .

### i = 0 , j = 5
```java
4 , 5 , 4 , 4 , 2 , 3
i
                    j
```
`nums[j] == nums[i]` Condition doesn't satisfy , so that `count` remains same . 

After that `arr[i] = 4` appears three times means `6/2` so , 4 is the major element .

Outer loop runs n times

Inner loop runs n times for each outer loop

## Time and Space Complexity : 
- Outer loop runs n times
- Inner loop runs n times for each outer loop means Time complexity - ***O(n^2)*** and space complexity - ***O(1)***

## Optimal Approach (Boyer-Moore Majority Voting Algorithm)
**The Boyer-Moore voting algorithm is one of the popular optimal algorithms which is used to find the majority element among the given elements that have more than N/ 2 occurrences. This works perfectly fine for finding the majority element which takes 2 traversals over the given elements, which works in O(N) time complexity and O(1) space complexity.**

```java
    public static int majorityElement(int nums[]){
        int n = nums.length ;
        int count = 0 , candidate = 0 ;

        for(int i=0 ; i<nums.length ; i++){
            if(count == 0) candidate = nums[i] ;

            count += (nums[i] == candidate) ? 1 : -1 ; // Find Candidate
        }

   count = 0;
    for (int index = 0; index < nums.length; index++) {
      if (nums[index] == candidate)
        count++;
    }
    if (count > (nums.length / 2)) // Check condition is satisfying or not
      return candidate;
    return -1;
    }
```
| i | nums[i] | candidate | count |
| - | ------- | --------- | ----- |
| 0 | 4       | 4         | 1     |
| 1 | 5       | 4         | 0     |
| 2 | 4       | 4         | 1     |
| 3 | 4       | 4         | 2     |
| 4 | 2       | 4         | 1     |
| 5 | 3       | 4         | 0     |


### Time complexity : O(n) , Space complexity : O(1)

