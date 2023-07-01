# Question 

Write a function that takes in an array of integers and returns a boolean representing whether the array is monotonic.

An array is said to be monotonic if its elements, from left to right, are entirely non-increasing or entirely non-decreasing. Non-increasing elements aren't necessarily exclusively decreasing; they simply don't increase. Similarly, non-decreasing elements aren't necessarily exclusively increasing; they simply don't decrease. Note that empty arrays and arrays of one element are monotonic.  

```
Sample Input: [-1, -5, -10, -1100, -900, -1101, -1102, -9001]
Sample Output: False
Reason: Function started decreasing initially, but at one point increased from -1100 to -900 

Sample Input: [1, 1, 2, 3, 4, 5, 5, 5, 6, 7, 8, 7, 9, 10, 11]
Sample Output: False
Reason: Function started increasing initially, but at one point decreased from 8 to 7.
```

## Approach 

Exclusively increasing and decreasing arrays work. The only condition is that once the array starts off in one direction (increasing or decreasing), it should never switch to the opposite direction. Becoming constant in between is okay but never switch directions). 

- Run a loop initially to get initial direction of the array (This is done because unlike my first thought where I was simply doing `initialDirection = array[1] - array[0]`, there is a possibility that the array is initially constant. So we loop through the array till the point where we get the first directional movement of the array and store that direction in `initialDirection`
- Now, all we have to do is make sure that while iterating through the whole array, at no point is the difference of two consecutive elements in the opposite direction of initialDirection. This means if initialDirection is negative, at no point should the difference between consecutive elements be positive (being 0, i.e, constant is okay) and vice versa.

### Code 
![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/a6a10242-58fe-4614-afd5-ef1d9f64ebeb)

# Takeaway 

- Read and understand the question properly.

