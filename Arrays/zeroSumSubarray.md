# Question 

﻿You're given a list of integers `nums`. Write a function that returns a boolean representing whether there exists a zero- sum subarray of `nums`.
A zero-sum subarray is any subarray where all of the values add up to zero. A subarray is any contiguous section of the array. For the purposes of this problem, a subarray can be as small as one element and as long as the original array. 

```
Sample Input: [-5,-5,2,3,-2]
Sample Output: True // [-5,2,3] adds up to 0 
```

## Approach  

I couldn't think of any solution to this problem and had to refer to the hints totally. 

- Keep track of all the sums from 0 to index i of an array while traversing through it.
- If at any index i, we encounter a sum that has already been encountered before, it means that there must have been a collection of elements that added up to 0 between when that sum was first encountered and when it occurred the second time.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/22f14d11-8eaf-4896-903e-913684e7287c)

# Takeaway 

- For subarray problems, see if the problem statement can be solved by storing information of subarrays made from 0th index to the pointer index as the pointer traverses once over the main array. 
