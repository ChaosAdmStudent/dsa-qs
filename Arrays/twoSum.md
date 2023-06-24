# Question 

Write a function that takes in a non-empty array of distinct integers and an integer representing a target sum. If any two numbers in the input array sum up to the target sum, the function should return them in an array, in any order. If no two numbers sum up to the target sum, the function should return an empty array. Note that the target sum has to be obtained by summing two different integers in the array; you can't add a single integer to itself in order to obtain the target sum. You can assume that there will be at most one pair of numbers summing up to the target sum.  

## Naive Approach 

- Just looping through the array n^2 times to compare all possible pairings.

```
# O(n^2) 

def twoNumberSum(array, targetSum):
    for i in range(len(array)): 
        for j in range(i+1, len(array)): 
            if array[i] + array[j] == targetSum: 
                return [array[i], array[j]] 

    return [] 
```

## Mathematical Approach  

The mathematical approach realizes that we are basically looking for the `targetSum - currentElement` in an array which might be somewhere in the array. The better way here is to try to think of Hash Maps.

- Iterate through array once
- For every element as the key, store its needed pair element as the value in a dictionary.
- Check at each iteration if the needed pair element already exists as a key (which would indicate that the needed element has already been iterated over in the traversal)
- This way, we only have to traverse the whole array once, with one looping variable.

```
# O(n) 

def twoNumberSum(array, targetSum):
    hashTable = {} 
    for x in array:  # O(n) 
        hashTable[x] = targetSum - x  # O(1)
        y = hashTable.get(targetSum-x) # O(1) 
        if y != None and  (targetSum-x) != x:
            return [x,hashTable[x]]

    return [] 
```
