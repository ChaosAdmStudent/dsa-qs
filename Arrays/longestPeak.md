# Question  

Write a function that takes in an array of integers and returns the length of the longest peak in the array.
A peak is defined as adjacent integers in the array that are strictly increasing until they reach a tip (the highest value in the peak), at which point they become strictly decreasing. At least three integers are required to form a peak. For example, the integers [1, 4, 10, 2] form a peak, but the integers [4, 0, 16] don't and neither do the integers [1, 2, 2, 0]. Similarly, the integers [1, 2, 3] don't form a peak because there aren't any strictly decreasing integers after the 3. 
```
Sample Input
array = [1, 2, 3, 3, 4, 8, 10, 6, 5, -1, -3, 2, 3]
Sample Output.
6 // 0, 10, 6, 5, -1, -3
```

## Approach 1 (My approach -- Complicated code but optimal time/space complexity) [O(n) time, O(1) space] 

I maintain variables `direction` for maintaining the current direction of the rise/fall. `directionChange` to store status update about whether there was a change in direction from strictly increasing to strictly decreasing. 

- If the next element is greater when the current direction was in strictly decreasing order, that means the peak streak is broken and we have to start fresh. Else, it means we just started increasing or were already increasing so we can add to the length of peak and move ahead.
- If the next element is smaller than current element when the direction is pointing to null, we can simply ignore this iteration and move ahead because decreasing behavior without a prior +ve direction violates the peak condition. 
- Otherwise, if its reducing when the current direction had been strictly increasing, it means there is a change in direction of the peak. So we change `directionChange` to True. Now, doesnt matter if it was already in a -ve direction or +ve trend, we will increment the length of the peak.
- If the next element is the same element as the current one, we check if the `directionChange` variable points to True. If it does, it means that a peak had already been encoutered before this, so we compare the length accumulated so far with the largest Peak length and update it if needed.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/834ef281-bd7e-4408-a095-76eb154cd465)

## Approach 2 (Shorter code; same time/space complexity) 

Instead of having so many conditionals which is needed for a single pointer traversing from start to end, we will make use of two pointers to do the same without any complicated conditional statements. We wont need any `directionChange` or `direction` variables because of this. 

- We loop the array from 2nd element till the 2nd last element till we find an element which is greater than both the element before it and after it (a peak point basically)
- After this, we set `currentLength` to 3 since we have already confirmed it. Now, we make use of another pointer j which is set to 2 elements before i. We continually check the element at jth position if its smaller than its next element till either it reaches the start of the array or it points to an element which is greater than the next element. This gives the length of the peak towards the left side of the peak point.
- Then, we set j to 2 positions AHEAD of the peak point and do the same till the end of the array or till we reach the point where jth element is greater than the previous element.

Finally, we update the main looping variable i to j's position to start considering next potential longest peak. 

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/bc75cdd3-8054-45ef-8ebc-e95490f678f5)

# Takeaway 

- When doing TRAVERSAL based questions, try to think from perspective of two pointers (already said this before!!)
- Here, instead of having to go through so many conditionals, the better way is to use a 2nd pointer going in either direction of the peak point till the peak condition provided in the question keeps getting fulfilled.

