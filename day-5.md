# Day 5

Problem:
leetcode link:

```js
//js solution
```

Input:

Output:

Algorith:

Python Solution:

```py
# solution here
```

# Day 5

Problem: Three Sum
LeetCode: https://leetcode.com/problems/3sum/

```js
function threeSum(nums) {
  const result = [];
  nums.sort((a, b) => a - b);
  for (let i = 0; i < nums.length - 2; i++) {
    if (i > 0 && nums[i] === nums[i - 1]) continue;
    let left = i + 1;
    let right = nums.length - 1;
    while (left < right) {
      const sum = nums[i] + nums[left] + nums[right];
      if (sum === 0) {
        result.push([nums[i], nums[left], nums[right]]);
        while (left < right && nums[left] === nums[left + 1]) left++;
        while (left < right && nums[right] === nums[right - 1]) right--;
        left++;
        right--;
      } else if (sum < 0) {
        left++;
      } else {
        right--;
      }
    }
  }
  return result;
}
```

Input: an array of integers

Output: an array of arrays, each containing three numbers that add up to zero (no duplicates)

Algorithm:
Sort the array first, then fix one number and use two pointers on the rest. If the sum is too small move left up, too big move right down, if it hits zero save it and skip duplicates on both sides.

Time: O(n²) | Space: O(1)

Python Solution:

```py
def threeSum(nums):
    result = []
    nums.sort()
    for i in range(len(nums) - 2):
        if i > 0 and nums[i] == nums[i - 1]:
            continue
        left, right = i + 1, len(nums) - 1
        while left < right:
            total = nums[i] + nums[left] + nums[right]
            if total == 0:
                result.append([nums[i], nums[left], nums[right]])
                while left < right and nums[left] == nums[left + 1]:
                    left += 1
                while left < right and nums[right] == nums[right - 1]:
                    right -= 1
                left += 1
                right -= 1
            elif total < 0:
                left += 1
            else:
                right -= 1
    return result
```
