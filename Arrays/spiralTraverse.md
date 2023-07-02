# Question 

Write a function that takes in an nxm two-dimensional array (that can be square-shaped when n==m) and returns a one-dimensional array of all the array's elements in spiral order. 

Spiral order starts at the top left corner of the two-dimensional array, dgoes to the right, and proceeds in a spiral pattern all the way until every element has been visited.  

```
Sample Input: "array": [
    [1, 2, 3, 4],
    [12, 13, 14, 5],
    [11, 16, 15, 6],
    [10, 9, 8, 7]
  ]
Sample Output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16] 
```

## Approach 

Realizing that spiral traversal is pretty much traversing along perimeters of rectangles. 

- Define 4 boundary points for each of the corners of the outermost rectangle of the array.
- Traverse in the order: top, right, bottom, left. Before traversing a particular perimeter, check if length of the 1D array has become equal to number of elements in the 2D array. This would mean all elements have been covered and we can break out the loop.
- After successfully traversing through all sides of the rectangle, move all boundary points inward to form the next rectangle enclosed within the outermost rectangle and keep repeating this process till the starting boundary points for the row and column is behind the end boundary points.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/5baa82e3-5fcf-43d5-ae61-5c39bbb9d5b8)

# Takeaway 

- For traversal problems, look at one particular pattern that is repeating over and over to do the traversal. For spiral traversal, this meant realizing that we need to keep iteratively traversing the perimeter of the rectangle and update the rectangle being traversed to the inner rectangle after the outer ones are traversed successfully. 
