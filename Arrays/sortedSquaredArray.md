# Question 

Write a function that takes in a non-empty array of integers that are sorted in ascending order and returns a new array of the same length with the squares of the original integers also sorted in ascending order. 

## Naive Approach 

- You just add x^2 after going through each element in the array iteratively, but then you realize negative numbers are also allowed here
- So you just append squares of the elements and call `array.sort()` at the end which would take O(nlogn) time. 

## Approach 1 (First idea in my head!)  

The first approach deals with taking two pointers within the same array that move in opposite directions inside the array, so that each element is covered only once. This way the time complexity would stay at O(N) 

- First, (try to) locate the element where positive numbers start. This is my pivot point from where I want to iterate two pointers in opposite directions, one for negative numbers (left of this pivot) and one for positive numbers (this element onward towards the right)
- Now, compare the squares of the negativePointer element with the positivePointer element. Whichever is smaller is added to the result array and the corresponding pointer is moved further in its direction
- If negativePointer runs behind the beginning index of the array, we can simply append the positivePointer elements' squares one after another, knowing that it will preserve the ascending order.
- If positivePointer exceeds the end of the array, we can simply append the negativePointer elements' squares one after another since the negativePointer is essentially running in descending order and thus the squares would be preserve ascending order.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/b629e203-e7cf-4197-acd0-af4679fb36d9)

## Approach 2 (Similar concept but tidier code) 

The approach here is similar, in that, it uses two pointers within the array so that each element is covered only once. However, it realizes the fact that we don't need to locate the pivot element for positive or negative numbers. We can simply start comparing the beginning and end of the array and keep iterating them closer to each other till they meet at the same index. 

- Instead of appending to a new array, we initialize the result array with the size equal to that of the input array, so that we can directly alter values in the result array using specific index positions
- Keep one pointer at the beginning and one pointer at the end of the array.
- **It is guaranteed that either the element at the beginning or the end will have the largest square, depending on whose absolute value is larger.** Using this mathematical idea, we move the start pointer ahead if the start element has a bigger value or the end pointer back if vice versa.

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/0b6815c3-8c59-4d4e-8873-f30d1fbb9ace)

# Takeaway 

- If an array of positive and negative numbers are sorted, the biggest even power of elements inside this array will either be in the start or beginning of the array, depending on their absolute values. Use this concept to recursively update the start and end pointer comparisons.
- Try to think if using two pointers instead of one within an array, moving in different directions can reduce time complexity.
