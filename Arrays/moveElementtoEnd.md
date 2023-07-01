# Question 

You're given an array of integers and an integer. Write a function that moves all instances of that integer in the array to the end of the array and returns the array. The function should perform this in place(i.e, it should mutate the input array) and doesn't need to maintain the order of the other. 

## Approach (First Idea in Head) [Optimal] 

- Maintain two pointers for start and end
- If end element is the target integer, we can skip and move the end pointer back. Similarly, if start element points to a non-target element, we can skip that
- As soon as start element points to the target integer, we can swap the elements pointed by start and end and move both of them in their corresponding direction
- Do this till start pointer is behind end pointer.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/c53cfafa-47e6-4633-bd03-a86b77b7b803)

# Takeaway 

- When mutating an array in place where you have to do some operation of moving elements from one place to another, try to think of the problem from the perspective of two pointers moving towards each other from opposite directions. 
