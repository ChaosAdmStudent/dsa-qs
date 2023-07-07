# Question 

You walk into a theatre you're about to see a show in. The usher within the theatre walks you to your row and mentions you're allowed to sit anywhere within the given row. Naturally you'd like to sit in the seat that gives you the most space. You also would prefer this space to be evenly distributed on either side of you (e.g. if there are three empty seats in a row, you would prefer to sit in the middle of those three seats).

Given the theatre row represented as an integer array, return the seat index of where you should sit. Ones represent occupied seats and zeroes represent empty seats. You may assume that someone is always sitting in the first and last seat of the row. Whenever there are two equally good seats, you should sit in the seat with the lower index. If there is no seat to sit in, return -1. The given array will always have a length of at least one and contain only ones and zeroes.

```
Sample Input: [1,0,1,0,0,0,1]
Sample Output: 4 
```

## Approach (First idea in head) [Optimal]

My approach to this question was similar to how I first thought of approaching the maximumPeak problem, i.e, via a single pointer moving from left to right, keeping track of the maximum number of 0s that occurred consecutively and a flag variable whose boolean values tell whether we are encountering consecutive 0s or not.  

- I maintain 2 variables:
  - `maxSpace` for maximum number of consecutive 0s encountered
  - `bestIdx` for the index of the first 0 corresponding to the `maxSpace` above.

- For every iteration, I check if the value is 0. If it is, I increase the temporary variable `space` value by 1. Thereafter, I check if the `startedZero` flag variable is False. If it is, this means this is the first 0 in the series. In that case, I make `startedZero` True and set the `idx` to the current position of the pointer. If the `startedZero` variable is True, that means this 0 is part of a running series of consecutive zeros and I simply increase the `space` variable alone.

- If the value of the element is 1, I reset all temporary variables, i.e,  `space=0` and `startedZero=False`. At the same time, I compare if the `space` is greater than `maxSpace` and update  `maxSpace` and `bestIdx` accordingly if that is the case.
- Finally, for bestIdx, the simple mathematical computation will do it: `bestIdx = idx + int((maxSpace-1)/2)` (This ensures that if spaces are even, the lower index of the middle two best seats are returned)

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/de125d68-3b28-4e8f-9d31-12d0d7588c8b) 


