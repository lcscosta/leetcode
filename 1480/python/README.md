# 1480. Running Sum of 1d Array
Easy 6.9K

Given an array nums. We define a running sum of an array as `runningSum[i] = sum(nums[0]…nums[i])`.

Return the running sum of nums.

Example 1:

```
Input: nums = [1,2,3,4]
Output: [1,3,6,10]
Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].
```

Example 2:

```
Input: nums = [1,1,1,1,1]
Output: [1,2,3,4,5]
Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].
```

Example 3:

```
Input: nums = [3,1,2,10,1]
Output: [3,4,6,16,17]
```

Constraints:

    1 <= nums.length <= 1000
    -10^6 <= nums[i] <= 10^6

# 1st Solution

Using List Comprehension from Python

```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        return [sum(nums[0:i+1]) for i in range(len(nums))]
```

Statistics from solution 

Runtime 73 ms
Beats 7.92%
Memory 16.7 MB
Beats 17.49%

Explanation:

Using this approach we have a with time complexity of O(N2) and space complexity of O(N).
Because of sum() function, we are doing 2 iterations every time. 
And we are allocating a new Array with N integers to return.

# Best Solution

Using an one-pass approach, using the input array to create the answer.

```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        for i in range(1, len(nums)):
            nums[i] = nums[i-1] + nums[i]
        return nums
```

Runtime 53 ms
Beats 72.57%
Memory 16.3 MB
Beats 98.96%
