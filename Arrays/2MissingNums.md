# Question 

﻿You're given an unordered list of unique integers nums in the range [1, n], where n represents the length of nums + 2 . This means that two numbers in this range are missing from the list.

Write a function that takes in this list and returns a new list with the two missing numbers, sorted numerically. 

```
Sample Input: nums: [1,4,3]
Sample Output: [2,5] // n is 5, meaning the completed list should have been [1,2,3,4,5]  
```

## Approach 1 (O(n) time, O(n) space) [ First idea ] 

Drawing from the takeaway from the DuplicateValue question, since all values in the array were linked with the length of the array, I thought of using the values of the array as indices to solve the problem. 

- I initilize a completed list `bigList` of size n with values -1
- Traversing through the `nums` array, I place the value at the corresponding index (i-1) in the completed list.
- Finally, I traverse through `bigList` once more and if a negative number is encountered, that means it wasn't encountered in the `nums` array. Hence when we reach this negative number in `bigList` we append (i+1) to the missingNums array, denoting the missing number.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/e303659b-48d6-4de6-a22d-321d061fa375)

## Approach 2 ( O(n) time O(1) space) [Optimal] 

Solved this on my own as well. This solution is purely mathematical and realizes the fact that we can solve 2 missing nums if we can make a relationship between them through 2 equations. 

  - x + y = (Sum of first n natural numbers) - (Sum of numbers in `nums`)
  - x*y = (Product of first n natural numbers, i.e, n!) / (Product of numbers in `nums`)

- We can do substitution to simply the above as: 
` x^2 - x(totalSum-sum) + (n!/product) ` 

- For the quadratic equation above:
  - a = 1
  - b = -(totalSum-sum)
  - c = n!/product
 
- Now using quadratic equation solution formula, we can find two missing values.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/6cf3e097-c680-482f-b374-e3646c06d888)

# Takeaway 

- For arrays whose values are linked with the length of the array, use the values as indices in some way
- For problems where 2 values are missing, try to find 2 equations that relate the missing values. This is because we can solve a system of 2 equations and 2 variables.
