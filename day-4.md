# Day 4

Problem: Group Anagrams
LeetCode: https://leetcode.com/problems/group-anagrams/

```js
function groupAnagrams(strs) {
  const map = {};
  for (let i = 0; i < strs.length; i++) {
    const key = strs[i].split("").sort().join("");
    if (map[key] === undefined) {
      map[key] = [];
    }
    map[key].push(strs[i]);
  }
  return Object.values(map);
}
```

Input: an array of strings

Output: an array of arrays, where each group contains strings that are anagrams of each other

Algorithm:
For each string, sort its characters to get a key — anagrams will always produce the same sorted key. Group strings by that key using a hashmap, then return all the groups.

Time: O(n \* k log k) | Space: O(n)

Python Solution:

```py
def groupAnagrams(strs):
    map = {}
    for s in strs:
        key = ''.join(sorted(s))
        if key not in map:
            map[key] = []
        map[key].append(s)
    return list(map.values())
```
