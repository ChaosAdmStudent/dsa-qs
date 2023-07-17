# Question 

﻿Write a function that takes in a non-empty, unordered array of positive integers and returns the array's majority element without sorting the array and without using more than constant space.

An array's majority element is an element of the array that appears in over half of its indices. Note that the most common element of an array (the element that appears the most times in the array) isn't necessarily the array's majority element; for example, the arrays
[3, 2, 2, 1] and [3, 4, 2, 2, 1] both have 2 as their most common element, yet neither of these arrays have a majority element, because neither 2 nor any other element appears in over half of the respective arrays' indices.

You can assume that the input array will always have a majority element.

```
Sample Input: [1,2,3,2,2,1,2]
Sample Output: 2 // 2 occurs in 4/7 array indices, making it the majority element
```

## Approach 

- Maintain a answer pointer initialized to the first element of the array with a counter of 1. 
- We traverse through the array and while doing that, look at the subarray from 1st index to the position we are currently on. For every occurrence of the answer pointer, we increment the counter; else decrement.
- If the counter touches 0 at any point, that means in that specific instance, our currently assigned answer pointer does not occur in majority anymore and is instead exactly half of the elements in the subarray upto that point.
- Thus, if a majority element exists, that will definitely be the majority element in the remaining subarray ahead. So, we update the answer pointer to the next array element and reset counter to 1.
- After we reach the end of the array, our answer pointer will have the majority element.

### Workflow for sample input: 

Initially: 
`answer=1` 
`count = 1` 
`i = 1` (start looping from 2nd element) 

1. 2 is not equal to 1, => count = 0. Hence, in the subarray [1,2] , 1 is not the majority element. Thus, update `answer = 3` (next element), `count=1`
2. 2 is not equal to 3, => count = 0. Hence again in subarray [3,2], 3 is not the majorty. => `answer = 2`, `count=1`
3. 1 is not equal to 2. => count = 0. Hence, in subarray [2,1], 2 is not the majortity element. => `answer = 2`, `count=1`
4. 2 is the only element in the subarray [2] and thus is the majority element.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/7b47904b-dbf7-4d6f-aaf7-d9823d9679d4)


# Takeaway 

- For occurence frequency questions in arrays, try solving using a common counter which looks at the subarray that gets built while traversing through the array. 
