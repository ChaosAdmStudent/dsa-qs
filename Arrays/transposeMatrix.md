# Question 

You're given a 2D array of integers `matrix`. Write a function that returns the transpose of the matrix. The transpose of a matrix is a flipped version of the original matrix across its main diagonal (which runs from top-left to bottom-right); it switches the row and column indices of the original matrix. You can assume the input matrix always has at least 1 value; however its width and height are not necessarily the same.  

## Approach 1 (Naive/Complicated) [First idea in head] 

I overcomplicated by trying to think with a symmetrical line of thought where I would convert any given array into a square array filled with 0's if its a nonSquare matrix and then find the transpose by swapping elements along the diagonals. 

- Make function that returns transpose of a square matrix within the function
- For non square matrices, insert appropriate number of rows/cols filled with 0s to make it square
- Find transpose using the function made in step 1
- After transpose, return the matrix without the rows/cols with only 0s

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/ef5fb1e9-eafb-4ea2-a1e1-ffde7a83b841) 

## Approach 2 (Easy) 

After giving it another thought, I realized that I was thinking of a square matrix because I was essentially running out of index positions if I tried to SWAP elements in a non square matrix with the method used above. However, this was easily doable if I initialized another result array with dimensions flipped around. 

- Initialize array of 0s with dimensions MxN
- newarr[i][j] = oldarr[j][i]

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/2bfce02d-ac02-4edc-b475-55d8cd616939)

# Takeaway 

- If a solution is getting too complicated and long, ESPECIALLY IF ITS AN EASY LEVEL PROBLEM, try to rethink from scratch from a different perspective.
- Dont shy away from space complexities exceeding O(1). Keep that in the picture too unless stated otherwise in the question.


