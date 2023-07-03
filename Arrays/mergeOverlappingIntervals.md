# Question 

﻿Write a function that takes in a non-empty array of arbitrary intervals, merges any overlapping intervals, and returns the new intervals in no particular order. Each interval interval is an array of two integers, with interval[0] as the start of the interval and interval[1] as the end of the interval. Note that back-to-back intervals aren't considered to be overlapping. For example, [1, 5] and [6, 7] aren't overlapping; however, [1, 6] and [6, 7] are indeed overlapping. Also note that the start of any particular interval will always be less than or equal to the end of that interval.

 ## Approach (O(nlogn) time; O(1) space) 

 Since we are working with intervals that should overlap, it is a good idea to sort the intervals based on their starting element first. This will take O(nlogn) time. Now we loop through array and just check 2 main conditions: 

 - If next intervals's start is less than current interval's end AND next interval's end is more than current interval's end, that means we are merging these two intervals, i.e, end = nextEnd.
 - Otherwise, if nextStart < currentEnd AND nextEnd < currentEnd, this means that the next interval is totally enclosed within the current interval and we can simply skip the next interval and point to the interval after the next interval and compare current interval with that.
 - In the end, when we reach the end of the array, we will add whatever is the currentStart and currentEnd to the result list. 

### Code 

![image](https://github.com/ChaosAdmStudent/dsa-qs/assets/53689018/132a60c9-1353-481c-b603-8dd2ec8c3818)

# Takeaway 

- Any form of overlapping operation/checking in an array should be done after sorting the array. 
