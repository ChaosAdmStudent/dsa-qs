# Question 

Given an array of positive integers representing the values of coins in your possession, write a function that returns the minimum amount of change (the minimum sum of money) that you cannot create. The given coins can have any positive integer value and aren't necessarily unique (i.e., you can have multiple coins of the same value). For example, if you're given coins = [1, 2, 5], the minimum amount of change that you can't create is 4. If you're given no coins, the minimum amount of change that you can't create is 1. 

## Approach 

### Mathematical Formula At Use 

In a sorted array, a[i+1] <= sum(a[0]...a[i]) + 1 

### Intuition/Logic behind above formula 

- This is a problem where we are trying to find a minimum sum of possible groups of numbers, so it is a good idea to sort the array and look at it from there.
- In a sorted array, let's say K represents that a change CAN be reached from 1 up to the number K.
- Now, if we look at a coin with value N that is added to this collection, we can make note of the following:
    - Obviously, N itself can be reached because we have a coin of exactly that value.
    - Since 1 can be reached, so can N+1
    - Since 2 can be reached, so can N+2
    - and so on till K

 - So, if we have K=7 and we have a new coin worth 9, then 9+1 = 10 onward till 9+7 = 16 can also be reached. However, 8 cant be. Hence, we need the new number to be maximum of 1 above the sum that could be achieved from the elements before.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/946b2744-d47b-4132-8948-000c3a4fe169)  

# Takeaway 

- Whenever stuck with arrays or have array problem statements where some minimum amount calculation in the natural number series is being considered, try sorting the array.
- Take small sized arrays and experiment with one of the numbers to see where certain conditions of the problem statement are broken. In this case [1,2,5] would violate the construction of change=4. That wont have been the case for any number less than 5 as the third element in this array. By doing this, try to play out the mathematical reasoning (and logical intuition behind why its working) through the equation that would fit.
