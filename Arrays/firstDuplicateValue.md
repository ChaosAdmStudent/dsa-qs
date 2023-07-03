# Question 

﻿Given an array of integers between 1 and n, inclusive, where n is the length of the array, write a function that returns the first integer that appears more than once (when the array is read from left to right). In other words, out of all the integers that might occur more than once in the input array, your function should return the one whose first duplicate value has the minimum index. If no integer appears more than once, your function should return -1. Note that you're allowed to mutate the input array. 

 ## Approach (O(n) time O(1) space)

 This would have been a O(n) time and O(n) space if some of the extra details were not given and we could have used hashmaps to do it. However, there is two key information available here: 
   - All numbers in the array are between 1 and the length of the array
   - We can mutate the array itself

This is how we approach now:  

- Since, all numbers are between 1 to n, we can use each element's value to reference an index position in the array. For example, value 2 in an array will correspond to index position (2-1) = 1 etc.
- While looping through the array, we look at the relevant index position of the current element we are pointing at and see if the value at that index is negative (initially, everything is positive!).
- If it is not negative, then we make the element at that index negative. This is a way of flagging that index and making note that we have encountered the element corresponding to that index position previously.
- Note that we are always referencing index position of a particular value by taking (absolute value of element - 1) so that if it was made negative before, it doesnt impact the referencing.
- As soon as we reach an element whose corresponding index position holds a negative number, it means that same element had been encountered before and we instantly return the element we are currently pointing at.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/888e08d4-a6eb-441b-b959-f52e9fe79c82)

# Takeaway 

- Make use of every single detail given in the prompt. They will never give extra details.
- If all numbers in an array are between 1 and n, you can use the values itself to reference index positions in the array. 
