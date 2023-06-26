# Question 

Given two non-empty arrays of integers, write a function that determines whether the second array is a subsequence of the first one. A subsequence of an array is a set of numbers that aren't necessarily adjacent in the array but that are in the same order as they appear in the array. For instance, the numbers [1, 3, 4] form a subsequence of the array [1, 2, 3, 4], and so do the numbers [2, 4]. Note that a single number in an array and the array itself are both valid subsequences of the array. 

## Approach 

The approach here is simple. Think of two pointers. One going through the main array, and the other pointing at the first element of the subsequence. 
- Iterate only through the main array and for every element, check if it matches with the subsequence's first element.
- If it does, move the subsequence pointer ahead by 1 position (O(1))
- At the end of the main array iteration, if the subsequence pointer ends up covering all elements, it means the main array contains the subsequence in order.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/80701842-9a60-4bb3-83a7-68726bf1ccc1)
