# Day 3

Problem: Reverse String
LeetCode: https://leetcode.com/problems/reverse-string/description/

```js
function reverseString(s) {
  let left = 0;
  let right = s.length - 1;
  while (left < right) {
    let temp = s[left];
    s[left] = s[right];
    s[right] = temp;
    left++;
    right--;
  }
  return s;
}
```

Input: an array of strings

Output: the same array of strings but reversed

Algorithm:
Two pointers starting at both ends, swap and move inward until they meet in the middle. In-place, no extra space needed.

Time: O(n) | Space: O(1)

Python Solution:

```py
def reverseString(s):
    left, right = 0, len(s) - 1
    while left < right:
        s[left], s[right] = s[right], s[left]
        left += 1
        right -= 1
    return s
```
