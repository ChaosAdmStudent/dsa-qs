1. If a solution is getting too complicated and long, ESPECIALLY IF ITS AN EASY LEVEL PROBLEM, try to rethink from scratch from a different perspective.
   
3. Dont shy away from space complexities exceeding O(1). Keep that in the picture too unless stated otherwise in the question.
4. Whenever working with score maintenance of some sort for elements in an array, THINK HASHMAPS!
5. For traversal problems, look at one particular pattern that is repeating over and over to do the traversal. For spiral traversal, this meant realizing that we need to keep iteratively traversing the perimeter of the rectangle and update the rectangle being traversed to the inner rectangle after the outer ones are traversed successfully.
6. If an array of positive and negative numbers are sorted, the biggest even power of elements inside this array will either be in the start or beginning of the array, depending on their absolute values. Use this concept to recursively update the start and end pointer comparisons.
7. Try to think if using two pointers instead of one within an array, moving in different directions can reduce time complexity.
8. When working with arrays to find a minimum of some sort, sort the array and then look at it from that perspective.
9. If two arrays are sorted and you take difference of elements of array 1 with array 2's specific element, the difference will move in the positive direction as you move ahead in array One
10. Whenever stuck with arrays or have array problem statements where some minimum amount calculation in the natural number series is being considered, try sorting the array.
11. Take small sized arrays and experiment with one of the numbers to see where certain conditions of the problem statement are broken.
12. When mutating an array in place where you have to do some operation of moving elements from one place to another, try to think of the problem from the perspective of two pointers moving towards each other from opposite directions.
13. Read and understand the question properly.
14. Make use of every single detail given in the prompt. They will never give extra details.
15. If all numbers in an array are between 1 and n, you can use the values itself to reference index positions in the array.
16. Any form of overlapping operation/checking in an array should be done after sorting the array. 
