# Question 


<img src="https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/b27c5aed-d97a-45a9-9453-88e279b3230c" width="700"> 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/a4560dfe-d493-4c8d-ac89-3699def67b07)

## Approach 

Since we are concerned with scores of each individual in the competition, the natural and best approach is to go with HashMaps because they can keep record for each player and do every operation in O(1) time. 

- The values in the result array can be used to get index of the winning player in each match from the competition array.
- Simply keep updating the values associated with each player by adding 3 points whenever the results array say they won.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/32c2e919-fb2a-441b-97fd-e32cc9624d3d)

# Takeaway 

- Whenever working with score maintenance of some sort for elements in an array, THINK HASHMAPS!
