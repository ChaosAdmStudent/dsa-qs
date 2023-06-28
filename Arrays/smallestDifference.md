# Question 

Write a function that takes in two non-empty arrays of integers, finds the pair of numbers (one from each array) whose absolute difference is closest to zero, and returns an array containing these two numbers, with the number from the first array in the first position. Note that the absolute difference of two integers is the distance between them on the real number line. For example, the absolute difference of -5 and 5 is 10, and the absolute difference of -5 and -4 is 1. You can assume that there will only be one pair of numbers with the smallest difference. 

```
Sample Input: 
﻿
arrayOne = [-1, 5, 10, 20, 28, 3]
arrayTwo = [26, 134, 135, 15, 17]

Sample Output: [28, 26]
```

## Approach (First idea in head and optimal) 

- Taking the takeaway from minNonConstructibleChange question, since we are concerned with comparing values in arrays to find some MINIMUM value, I initially sorted both the arrays in ascending order using O(nlogn) + O(mlogm) time. 

- In the sample case the arrays become: 
```
arrayOne = [-1,3,5,10,20,28]
arrayTwo = [15,17,26,134,135]
```
- We will maintain the smallest absolute difference in a variable `smallestDifference`
- Now, keeping one pointer each at the starting of both the arrays, we will subtract the values they point at. If they make the smallest absolute difference, we update the variable above.
- If difference is negative, that means element of arrayOne is smaller. Since the arrays are already sorted, this means that moving the arrayOne pointer ahead will move the difference in the positive direction, in the hope of getting closer to 0.
- Consequently, if the difference is positie, this means we can reduce it by moving pointer of arrayTwo in the forward direction.
- As soon as one of the pointer for any of the array moves out of its range, we can stop looping at that point.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/9fc88a72-c3a4-4fbc-8c20-135e17e331f4)

# Takeaway 

- When working with arrays to find a minimum of some sort, sort the array and then look at it from that perspective.
- If two arrays are sorted and you take difference of elements of array 1 with array 2's specific element, the difference will move in the positive direction as you move ahead in array One

